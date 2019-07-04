---
title: Použití certifikační autority (CA) s SCEP v Microsoft Intune – Azure | Dokumentace Microsoftu
description: V Microsoft Intune můžete přidat dodavatele nebo třetích stran certifikační autority (CA) k vydávání certifikátů do mobilních zařízení pomocí protokolu SCEP. V tomto přehledu poskytuje aplikace Azure Active Directory (Azure AD) službě Microsoft Intune oprávnění k ověření certifikátů. Potom při instalaci serveru SCEP k vystavování certifikátů použijete ID aplikace, ověřovací klíč a ID tenanta aplikace AAD.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 058ebc90cc5086aea21e135fc9944c31cf912105
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2019
ms.locfileid: "67547247"
---
# <a name="add-partner-certification-authority-in-intune-using-scep"></a>Přidání partnerské certifikační autority pomocí protokolu SCEP do Intune

Použití certifikační autority (CA) s Intune. Certifikační autority třetích stran můžou poskytovat mobilních zařízení pomocí nové nebo obnovené certifikáty pomocí certifikátu registrace protokolu SCEP (Simple) a může podporovat zařízení s Windows, iOS, Android a macOS.

K použití této funkce potřebujete dvě věci: open-source rozhraní API a úlohy správce Intune.

**Část 1 – použití open-source rozhraní API**  
Společnost Microsoft vytvořila rozhraní API pro integraci s Intune. Rozhraní API můžete ověřit certifikáty, odesílat oznámení o úspěchu nebo neúspěchu a používat protokol SSL, konkrétně SSL soketu objekt pro vytváření, komunikovat s Intune.

Rozhraní API je k dispozici ke stažení z [veřejného úložiště GitHub rozhraní Intune SCEP API](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation), abyste ho mohli použít ve svých řešeních. Pomocí tohoto rozhraní API se servery SCEP třetí strany tím spustíte ověření vlastní výzvy Intune předtím, než se certifikát na zařízení zřídí SCEP.

Článek o [integraci s řešením pro správu Intune SCEP](scep-libraries-apis.md) obsahuje další podrobnosti o použití tohoto rozhraní API, jeho metodách a testování sestaveného řešení.

**Část 2 – Vytvoření aplikace a profilu**  
Pomocí aplikace Azure Active Directory (Azure AD) můžete delegovat práva, aby služba Intune zpracovávala žádosti protokolu SCEP přicházející ze zařízení. Aplikace Azure AD obsahuje hodnoty ID aplikace a ověřovacího klíče, které se používají v rámci řešení rozhraní API vytvořeného vývojářem. Správci pak vytvoření a nasazení profilů certifikátů SCEP pomocí Intune a sestavy můžete zobrazit stav nasazení na zařízení.

Tento článek poskytuje přehled této funkce z pohledu správce, včetně vytvoření aplikace Azure AD.

## <a name="overview"></a>Přehled

Následující kroky poskytují základní informace o vydávání certifikátů SCEP v Intune:

1. Správce v Intune vytvoří profil certifikátu SCEP a potom profil cílí na uživatele nebo zařízení.
2. Zařízení se vrátí se změnami do Intune.
3. Intune vytvoří jedinečnou výzvu SCEP. Zároveň přidá dodatečné informace o kontrole integrity, jako je například očekávaný předmět a alternativní název subjektu.
4. Intune výzvu i informace o kontrole integrity zašifruje a podepíše a pak je odešle do zařízení s požadavkem SCEP.
5. Zařízení vygeneruje žádost o podepsání certifikátu (CSR) a na základě profilu certifikátu SCEP odeslaného z Intune vygeneruje pár veřejného a privátního klíče.
6. Žádost o podepsání certifikátu a zašifrovaná a podepsaná výzva se odešlou koncovému bodu externího serveru SCEP.
7. Server SCEP odešle žádost o podepsání certifikátu a výzvu do Intune. Intune pak podpis ověří, dešifruje datovou část a porovná žádost o podepsání certifikátu s informacemi o kontrole integrity.
8. Intune odešle zpět serveru SCEP odpověď a uvede, zda ověření výzvy proběhlo úspěšně, nebo ne.  
9. Pokud se výzva úspěšně ověřila, pak server SCEP vydá zařízení certifikát.

Následující diagram znázorňuje podrobný tok integrace externího serveru SCEP s Intune:

![Způsob integrace externí certifikační autority SCEP s Microsoft Intune](./media/scep-certificate-vendor-integration.png)

## <a name="set-up-third-party-ca-integration"></a>Nastavení integrace externí certifikační autority

### <a name="validate-third-party-certification-authority"></a>Ověření externí certifikační autority

Před provedení integrace externích certifikačních autorit s Intune zkontrolujte, že vybraná certifikační autorita podporuje Intune. Zde je seznam [partnerů externí certifikační autority](#third-party-certification-authority-partners) (v tomto článku). Další informace můžete také získat z pokynů vaší certifikační autority. Certifikační autorita může obsahovat specifické instalační pokyny pro implementaci.

### <a name="authorize-communication-between-ca-and-intune"></a>Autorizace komunikace mezi certifikační autoritou a Intune

Pokud chcete externímu serveru SCEP povolit spuštění vlastního ověření výzvy pomocí Intune, vytvořte aplikaci ve službě Azure AD. Tato aplikace poskytne Intune delegovaná práva k ověřování žádostí protokolu SCEP.

Ujistěte se, že máte k registraci aplikace Azure AD potřebná oprávnění. Zobrazit [požadovaná oprávnění](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions), v dokumentaci k Azure AD.

#### <a name="create-an-application-in-azure-active-directory"></a>Vytvoření aplikace v Azure Active Directory  

1. V [webu Azure portal](https://portal.azure.com), přejděte na stránku **Azure Active Directory** > **registrace aplikací**a pak vyberte **registrace nové**.  

2. Na **zaregistrovat aplikaci** stránky, zadejte následující podrobnosti:  
   - V **název** části, zadejte název smysluplné aplikace.  
   - Pro **podporovaných typů účtu** vyberte **účty v libovolném adresáři organizace**.  
   - Pro **identifikátor URI pro přesměrování**, ponechte výchozí Web, a pak zadejte přihlašovací adresu URL serveru SCEP třetích stran.  

3. Vyberte **zaregistrovat** vytvořit aplikaci a otevřete stránku přehled pro novou aplikaci.  

4. V aplikaci **přehled** stránky, zkopírujte **ID aplikace (klient)** hodnotu a uložte ho pro pozdější použití. Tuto hodnotu budete potřebovat později.  

5. V navigačním podokně pro aplikaci, přejděte na **certifikáty a tajné kódy** pod **spravovat**. Vyberte **nový tajný kód klienta** tlačítko. Zadejte hodnotu do pole Popis, vyberte možnosti pro **Expires**a pak a zvolte **přidat** ke generování *hodnotu* tajný kód klienta. 
   > [!IMPORTANT]  
   > Než odejdete z této stránky, zkopírujte hodnotu pro tajný kód klienta a poznamenejte si ho pro pozdější použití s vaší implementace certifikační Autority třetích stran. Tato hodnota se znovu nezobrazí. Nezapomeňte si přečtěte poučení certifikační autority třetích stran na to, jak chtějí ID aplikace, ověřovací klíč a ID Tenanta, které jsou nakonfigurované.  

6. Záznam vaší **ID Tenanta**. ID Tenanta je text domény po se ve vašem účtu znak @. Například, pokud je váš účet *admin@name.onmicrosoft.com* , pak je vaše ID tenanta **name.onmicrosoft.com**.  

7. V navigačním podokně pro aplikaci, přejděte na **oprávnění k rozhraní API** pod **spravovat**a pak vyberte **přidat oprávnění**.  

8. Na **žádosti rozhraní API oprávnění** stránce **Intune**a pak vyberte **oprávnění aplikace**. Zaškrtněte políčko pro **scep_challenge_provider** (SCEP výzvu ověřování).  

   Vyberte **přidat oprávnění** tuto konfiguraci uložíte.  

9. Zůstat na **oprávnění k rozhraní API** stránku a vybrat **udělit souhlas správce služby pro Microsoft**a pak vyberte **Ano**.  
   
   Byl dokončen proces registrace aplikace ve službě Azure AD.





### <a name="configure-and-deploy-a-scep-certificate-profile"></a>Konfigurace a nasazení profilu certifikátu SCEP
Vytvořte jako správce profil certifikátu SCEP, který bude cílit na uživatele nebo zařízení. Pak profil přiřaďte.

- [Vytvoření profilu certifikátu SCEP](certificates-scep-configure.md#create-a-scep-certificate-profile)

- [Přiřazení profilu certifikátu](certificates-scep-configure.md#assign-the-certificate-profile)

## <a name="removing-certificates"></a>Odebrání certifikátů

Po zrušení registrace nebo vymazání zařízení se certifikáty odeberou. Certifikátů se neodvolávají.

## <a name="third-party-certification-authority-partners"></a>Partneři externí certifikační autority
Následující externí certifikační autority podporují Intune:

- [Entrust Datacard](https://info.entrustdatacard.com/pki-eval-tool)
- [GitHub EJBCA – verze open-source](https://github.com/agerbergt/intune-ejbca-connector)
- [EverTrust](https://evertrust.fr/en/products/)
- [GlobalSign](https://downloads.globalsign.com/acton/attachment/2674/f-6903f60b-9111-432d-b283-77823cc65500/1/-/-/-/-/globalsign-aeg-microsoft-intune-integration-guide.pdf)
- [IDnomic](https://www.idnomic.com/)
- [Sectigo](https://sectigo.com/products)
- [DigiCert](https://knowledge.digicert.com/tutorials/microsoft-intune.html)

Pokud jste externí certifikační autoritou a máte zájem o integraci svého produktu s Intune, projděte si pokyny rozhraní API:

- [Úložiště GitHub rozhraní Intune SCEP API](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Pokyny pro externí certifikační autority k rozhraní Intune SCEP API](scep-libraries-apis.md)

## <a name="see-also"></a>Viz také:

- [Konfigurace a používání certifikátů SCEP s Intune](certificates-scep-configure.md)
- [Úložiště GitHub rozhraní Intune SCEP API](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Pokyny pro externí certifikační autority k rozhraní Intune SCEP API](scep-libraries-apis.md)
