---
title: Použití certifikačních autorit (CA) třetích stran s SCEP v Microsoft Intune – Azure | Microsoft Docs
description: V Microsoft Intune můžete přidat dodavatele nebo certifikační autoritu (CA) třetí strany pro vydávání certifikátů do mobilních zařízení pomocí protokolu SCEP. V tomto přehledu aplikace Azure Active Directory (Azure AD) poskytuje Microsoft Intune oprávnění k ověřování certifikátů. Pak použijte ID aplikace, ověřovací klíč a ID klienta aplikace AAD v nastavení serveru SCEP k vystavování certifikátů.
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
ms.openlocfilehash: 4b82124fe8f6da7116c8333e293f219d7c667f9c
ms.sourcegitcommit: a2654f3642b43b29ab0e1cbb2dfa2b56aae18d0e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72310908"
---
# <a name="add-partner-certification-authority-in-intune-using-scep"></a>Přidání certifikační autority pro partnery do Intune pomocí protokolu SCEP

Použijte certifikační autority (CA) třetích stran s Intune. CA třetích stran můžou zřídit mobilní zařízení s novými nebo obnovenými certifikáty pomocí Simple Certificate Enrollment Protocol (SCEP) a můžou podporovat zařízení s Windows, iOS, Androidem a macOS.

Tuto funkci můžete používat dvěma částmi: Open Source API a úlohami správce Intune.

**Část 1 – použití Open Source rozhraní API**  
Microsoft vytvořil rozhraní API pro integraci s Intune. I když rozhraní API můžete ověřovat certifikáty, odesílat oznámení o úspěšnosti nebo neúspěchu a k komunikaci s Intune používat protokol SSL, konkrétně objekt pro vytváření soketů SSL.

Rozhraní API je dostupné ve [veřejném úložišti GITHUB API služby Intune](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation) , které můžete stáhnout a používat ve svých řešeních. Pomocí tohoto rozhraní API se servery SCEP třetích stran spustíte vlastní ověřování výzvou proti Intune před tím, než SCEP zřídí certifikát pro zařízení.

[Integrace s řešením správy SCEP v Intune](scep-libraries-apis.md) poskytuje podrobnější informace o používání rozhraní API, jeho metod a testování vámi sestaveného řešení.

**Část 2 – Vytvoření aplikace a profilu**  
Pomocí aplikace Azure Active Directory (Azure AD) můžete delegovat práva k Intune a zpracovávat požadavky SCEP přicházející ze zařízení. Aplikace Azure AD obsahuje ID aplikace a hodnoty ověřovacího klíče, které se používají v řešení API, které vývojář vytvoří. Správci pak vytvoří a nasadí profily certifikátů SCEP pomocí Intune a můžou si zobrazit sestavy o stavu nasazení na zařízeních.

Tento článek obsahuje přehled této funkce z pohledu správce, včetně vytvoření aplikace Azure AD.

## <a name="overview"></a>Přehled

Následující kroky poskytují přehled použití protokolu SCEP pro certifikáty v Intune:

1. V Intune vytvoří správce profil certifikátu SCEP a pak ho nacílí na uživatele nebo zařízení.
2. Zařízení se vrátí do Intune.
3. Intune vytvoří jedinečnou výzvu SCEP. Přidává taky další informace o kontrole integrity, třeba to, co by měl být očekávaný předmět a síť SAN.
4. Intune šifruje a podepisuje informace o kontrole a kontrole integrity a pak tyto informace pošle do zařízení pomocí žádosti SCEP.
5. Zařízení na zařízení vygeneruje dvojici žádost o podepsání certifikátu (CSR) a veřejný/privátní klíč na základě profilu certifikátu SCEP, který je nabízený z Intune.
6. ZÁSTUPCE a šifrované/podepsané výzvy se odesílají do koncového bodu serveru SCEP třetí strany.
7. Server SCEP pošle CSR a výzvu do Intune. Intune potom ověří podpis, dešifruje datovou část a porovná ho s informacemi o kontrole integrity.
8. Intune pošle zpět odpověď serveru SCEP a určí, jestli je ověření výzvy úspěšné.  
9. Pokud se výzva úspěšně ověří, server SCEP vydá certifikát do zařízení.

Následující diagram znázorňuje podrobný tok integrace SCEP od třetích stran s Intune:

![Jak se certifikační autorita SCEP od třetí strany integruje s Microsoft Intune](./media/certificate-authority-add-scep-overview/scep-certificate-vendor-integration.png)

## <a name="set-up-third-party-ca-integration"></a>Nastavení integrace certifikační autority třetích stran

### <a name="validate-third-party-certification-authority"></a>Ověřit certifikační autoritu třetí strany

Před integrací certifikačních autorit třetích stran s Intune potvrďte, že certifikační autorita, kterou používáte, podporuje Intune. [Partneři CA třetích stran](#third-party-certification-authority-partners) (v tomto článku) obsahují seznam. Další informace najdete také v pokynech k certifikační autoritě. Certifikační autorita může obsahovat pokyny k instalaci, které jsou specifické pro jejich implementaci.

### <a name="authorize-communication-between-ca-and-intune"></a>Autorizovat komunikaci mezi certifikační autoritou a Intune

Pokud chcete, aby server SCEP třetí strany spouštěl vlastní ověřování výzvou v Intune, vytvořte v Azure AD aplikaci. Tato aplikace poskytuje delegovaná práva k Intune, aby ověřila požadavky SCEP.

Ujistěte se, že máte požadovaná oprávnění k registraci aplikace služby Azure AD. Viz [požadovaná oprávnění](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions)v dokumentaci k Azure AD.

#### <a name="create-an-application-in-azure-active-directory"></a>Vytvoření aplikace v Azure Active Directory  

1. V [Azure Portal](https://portal.azure.com)klikněte na**registrace aplikací** **Azure Active Directory** >  a pak vyberte **Nová registrace**.  

2. Na stránce **zaregistrovat aplikaci** zadejte následující podrobnosti:  
   - V části **název** zadejte smysluplný název aplikace.  
   - V části **podporované typy účtů** vyberte **účty v libovolném organizačním adresáři**.  
   - Pro **identifikátor URI přesměrování**ponechte výchozí nastavení web a potom zadejte adresu URL pro přihlášení k serveru SCEP třetí strany.  

3. Vyberte **Registrovat** , chcete-li vytvořit aplikaci a otevřít stránku Přehled pro novou aplikaci.  

4. Na stránce **Přehled** aplikace ZKOPÍRUJTE hodnotu **ID aplikace (klienta)** a zaznamenejte ji pro pozdější použití. Tuto hodnotu budete potřebovat později.  

5. V navigačním podokně pro aplikaci přejdete na **certifikáty & tajných** kódů v části **Spravovat**. Vyberte tlačítko **nový tajný klíč klienta** . Zadejte hodnotu v popisu, vyberte libovolnou možnost pro **vypršení platnosti**a pak zvolte **Přidat** , aby se vygenerovala *hodnota* pro tajný klíč klienta. 
   > [!IMPORTANT]  
   > Než tuto stránku opustíte, zkopírujte hodnotu pro tajný klíč klienta a zaznamenejte ho pro pozdější použití s implementací CA třetí strany. Tato hodnota se znovu nezobrazí. Nezapomeňte si projít doprovodné materiály k vaší certifikační autoritě od třetí strany, jak si přeje nakonfigurovat ID aplikace, ověřovací klíč a ID tenanta.  

6. Poznamenejte si **ID tenanta**. ID tenanta je text domény po přihlášení @ účtu. Pokud je váš účet například *admin@name.onmicrosoft.com* , bude vaše ID tenanta **Name.onmicrosoft.com**.  

7. V navigačním podokně aplikace otevřete v nabídce **Spravovat** **oprávnění rozhraní API** a pak vyberte **Přidat oprávnění**.  

8. Na stránce **požádat o oprávnění API** vyberte **Intune**a pak vyberte **oprávnění aplikace**. Zaškrtněte políčko pro **scep_challenge_provider** (ověření výzvou SCEP).  

   Pokud chcete tuto konfiguraci uložit, vyberte **Přidat oprávnění** .  

9. Zůstat na stránce **oprávnění rozhraní API** a vyberte možnost **udělit souhlas správce pro Microsoft**a potom vyberte **Ano**.  
   
   Proces registrace aplikace v Azure AD je dokončený.





### <a name="configure-and-deploy-a-scep-certificate-profile"></a>Konfigurace a nasazení profilu certifikátu SCEP
Jako správce vytvořte profil certifikátu SCEP pro cílení na uživatele nebo zařízení. Pak přiřaďte profil.

- [Vytvoření profilu certifikátu SCEP](certificates-profile-scep.md#create-a-scep-certificate-profile)

- [Přiřazení profilu certifikátu](certificates-profile-scep.md#assign-the-certificate-profile)

## <a name="removing-certificates"></a>Odebírání certifikátů

Když zrušíte registraci nebo vymazání zařízení, certifikáty se odeberou. Certifikáty nejsou odvolány.

## <a name="third-party-certification-authority-partners"></a>Partneři certifikační autority od jiných výrobců
Intune podporují tyto certifikační autority od jiných výrobců:

- [Entrust Datacard](https://info.entrustdatacard.com/pki-eval-tool)
- [Verze open-source na GitHubu EJBCA](https://github.com/agerbergt/intune-ejbca-connector)
- [EverTrust](https://evertrust.fr/en/products/)
- [GlobalSign](https://downloads.globalsign.com/acton/attachment/2674/f-6903f60b-9111-432d-b283-77823cc65500/1/-/-/-/-/globalsign-aeg-microsoft-intune-integration-guide.pdf)
- [IDnomic](https://www.idnomic.com/)
- [Sectigo](https://sectigo.com/products)
- [DigiCert](https://knowledge.digicert.com/tutorials/microsoft-intune.html)
- [Venafi](https://www.venafi.com/platform/enterprise-mobility)
- [SCEPman](https://azuremarketplace.microsoft.com/marketplace/apps/gluckkanja.scepman)

Pokud jste si od jiné certifikační autority zajímá integraci produktu s Intune, přečtěte si pokyny k rozhraní API:

- [Úložiště GitHub rozhraní API pro SCEP v Intune](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Doprovodné materiály k rozhraní SCEP API pro Intune pro certifikační autority třetích stran](scep-libraries-apis.md)

## <a name="see-also"></a>Další informace najdete v tématech

- [Konfigurace profilů certifikátů](certificates-scep-configure.md)
- [Úložiště GitHub rozhraní API pro SCEP v Intune](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Doprovodné materiály k rozhraní SCEP API pro Intune pro certifikační autority třetích stran](scep-libraries-apis.md)
