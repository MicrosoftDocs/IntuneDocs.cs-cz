---
title: Použití externí certifikační autority s protokolem SCEP v Microsoft Intune – Azure | Microsoft Docs
description: Do Microsoft Intune můžete přidat dodavatele nebo externí certifikační autoritu (CA), která bude pomocí protokolu SCEP vydávat certifikáty mobilním zařízením. V tomto přehledu poskytuje aplikace Azure Active Directory (Azure AD) službě Microsoft Intune oprávnění k ověření certifikátů. Potom při instalaci serveru SCEP k vystavování certifikátů použijete ID aplikace, ověřovací klíč a ID tenanta aplikace AAD.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ee5a39ee8a146fbc6a85a9f4438b8e14a408a735
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321622"
---
# <a name="add-partner-certification-authority-in-intune-using-scep"></a>Přidání partnerské certifikační autority pomocí protokolu SCEP do Intune

Do Microsoft Intune můžete přidat externí certifikační autority (CA). Tyto certifikační autority mohou mobilním zařízením pomocí protokolu SCEP (Simple Certificate Enrollment Protocol) poskytovat certifikáty. Tato funkce může na zařízeních se systémy Windows, iOS, Android a macOS vydávat nové certifikáty a prodlužovat platnost těch stávajících.

K použití této funkce potřebujete dvě věci: open-source rozhraní API a úlohy správce Intune.

**Část 1 – použití open-source rozhraní API**  
Společnost Microsoft vytvořila rozhraní API, které po integraci s Intune může ověřovat certifikáty, odesílat oznámení o úspěchu či neúspěchu a používat protokol SSL, konkrétně objekt pro vytváření soketu SSL, pro komunikaci s Intune.

Rozhraní API je k dispozici ke stažení z [veřejného úložiště GitHub rozhraní Intune SCEP API](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation), abyste ho mohli použít ve svých řešeních. Toto rozhraní API použijete na externích serverech SCEP ke spuštění vlastního ověření výzvy, které provede srovnání s Intune, než certifikát doručí zařízení.

Článek o [integraci s řešením pro správu Intune SCEP](scep-libraries-apis.md) obsahuje další podrobnosti o použití tohoto rozhraní API, jeho metodách a testování sestaveného řešení.

**Část 2 – Vytvoření aplikace a profilu**  
Pomocí aplikace Azure Active Directory (Azure AD) můžete delegovat práva, aby služba Intune zpracovávala žádosti protokolu SCEP přicházející ze zařízení. Aplikace Azure AD obsahuje hodnoty ID aplikace a ověřovacího klíče, které se používají v rámci řešení rozhraní API vytvořeného vývojářem. Správci pak mohou pomocí Intune vytvořit a nasadit profily certifikátů SCEP. Na zařízeních si také můžete zobrazit sestavy o stavu nasazení.

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

Ujistěte se, že máte k registraci aplikace Azure AD potřebná oprávnění. Postup najdete v části s [požadovanými oprávněními](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions).

**Krok 1: Vytvoření aplikace služby Azure AD**

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Azure Active Directory** > **Registrace aplikací** > **Registrace nové aplikace**.
3. Zadejte název a přihlašovací adresu URL. Jako typ aplikace vyberte **Webová aplikace / webové rozhraní API**.
4. Vyberte **Vytvořit**.

V článku o [integraci aplikací pomocí Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications) najdete některé pokyny týkající se vytváření aplikace, včetně rad ohledně adresy URL a názvu.

**Krok 2: Udělení oprávnění**

Po vytvoření aplikace poskytněte rozhraní API Microsoft Intune požadovaná oprávnění:

1. V aplikaci Azure AD otevřete **Nastavení** > **Požadovaná oprávnění**.  
2. Vyberte **Přidat** > **Vyberte rozhraní API.** > vyberte **Rozhraní API Microsoft Intune** > **Vybrat**.
3. V část **Vybrat oprávnění** zvolte **Ověření výzvy SCEP** > **Vybrat**.
4. Zvolením možnosti **Hotovo** uložte změny.

**Krok 3: Získání ID aplikace a ověřovacího klíče**

V dalším kroku získáte hodnoty ID a klíče aplikace Azure AD. Budete potřebovat následující hodnoty:

- ID aplikace
- Ověřovací klíč
- ID tenanta

**Způsob získání ID aplikace a ověřovacího klíče**:

1. Vyberte v Azure AD svou novou aplikaci (**Registrace aplikací**).
2. Zkopírujte **ID aplikace** a uložte ho do kódu aplikace.
3. Poté vygenerujte ověřovací klíč. V aplikaci Azure AD otevřete **Nastavení** > **Klíče**.
4. V části **Hesla** zadejte popis a zvolte dobu platnosti klíče. **Uložte** provedené změny. Zkopírujte a uložte zobrazenou hodnotu.

    > [!IMPORTANT]
    > Klíč okamžitě zkopírujte a uložte, protože se už znovu nezobrazí. Tuto hodnotu klíče potřebujete k implementaci externí certifikační autority. Nezapomeňte si přečíst pokyny certifikační autority, jak se mají ID aplikace, ověřovací klíč a ID tenanta nakonfigurovat.

**ID tenanta** je text domény za znakem @ při přihlašování k účtu. Pokud je váš účet například `admin@name.onmicrosoft.com`, pak je ID tenanta **name.onmicrosoft.com**.

Pokyny k získání těchto hodnot a více podrobností o aplikacích Azure AD najdete v článku o [získání ID aplikace a ověřovacího klíče](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#get-application-id-and-authentication-key).

### <a name="configure-and-deploy-a-scep-certificate-profile"></a>Konfigurace a nasazení profilu certifikátu SCEP
Vytvořte jako správce profil certifikátu SCEP, který bude cílit na uživatele nebo zařízení. Pak profil přiřaďte.

- [Vytvoření profilu certifikátu SCEP](certificates-scep-configure.md#create-a-scep-certificate-profile)

- [Přiřazení profilu certifikátu](certificates-scep-configure.md#assign-the-certificate-profile)

## <a name="removing-certificates"></a>Odebrání certifikátů

Po zrušení registrace nebo vymazání zařízení se certifikáty odeberou. Certifikátů se neodvolávají.

## <a name="third-party-certification-authority-partners"></a>Partneři externí certifikační autority
Následující externí certifikační autority podporují Intune:

- [Entrust Datacard](http://www.entrustdatacard.com/resource-center/documents/documentation)

Pokud jste externí certifikační autoritou a máte zájem o integraci svého produktu s Intune, projděte si pokyny rozhraní API:

- [Úložiště GitHub rozhraní Intune SCEP API](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Pokyny pro externí certifikační autority k rozhraní Intune SCEP API](scep-libraries-apis.md)

## <a name="see-also"></a>Viz taky

- [Konfigurace a používání certifikátů SCEP s Intune](certificates-scep-configure.md)
- [Úložiště GitHub rozhraní Intune SCEP API](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Pokyny pro externí certifikační autority k rozhraní Intune SCEP API](scep-libraries-apis.md)
