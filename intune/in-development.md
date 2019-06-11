---
title: Při vývoji – Microsoft Intune
titleSuffix: ''
description: Microsoft Intune nabízí ve vývoji
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4e9a640a343efd4ad786d7697439531de3cd4ed3
ms.sourcegitcommit: 2f32f6d2129bc10cc4a02115732e995edceb37d6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2019
ms.locfileid: "66828958"
---
# <a name="in-development-for-microsoft-intune---june-2019"></a>Při vývoji pro Microsoft Intune – červen 2019

Pomáhat při vaší připravenosti a plánování, tato stránka seznamy uživatelské rozhraní Intune aktualizuje a funkce, které jsou ve vývoji, ale ještě není. Navíc platí:

- Pokud předpokládáme, že budete muset udělat před změnu, budeme publikovat doplňkové příspěvek Centru zpráv Office.
- Když funkce se spustí v produkčním prostředí, buď ve verzi preview nebo obecně k dispozici, popis funkce se přesune mimo tuto stránku a na [stránce s novinkami](whats-new.md).
- Na této stránce a [stránce s novinkami](whats-new.md) jsou pravidelně aktualizovány. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.
- Odkazovat [M365 plán](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) pro strategické dodávky a časovými osami.

> [!Note]
> Tyto položky odrážejí aktuální očekávání společnosti Microsoft o možnostech Intune v budoucí verzi. Data a jednotlivé funkce mohou změnit. Ne všechny položky ve vývoji mají popis funkce na této stránce.

**Informační kanál RSS**: Nechte se informovat Tato stránka se aktualizuje zkopírováním a vložením do informačního kanálu čtečky na následující adrese URL: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune na portálu Azure Portal

<!-- ***********************************************-->
### <a name="app-management"></a>Správa aplikací

#### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Uživatelé zařízení můžete zobrazit všechny spravované aplikace, které jste nainstalovaná nebo se pokusila o instalaci <!-- 2352913 -->
Portál společnosti pro Windows se zobrazí seznam všech spravovaných aplikací (požadovaná i dostupná), které jsou nainstalované na zařízení uživatele. Uživatelé budou moct k pokusu o zobrazení a probíhající instalace aplikací a jejich aktuální stavy. Pokud vaše organizace nemá vytvořit obdobné aplikace vyžaduje nebo jsou dostupné, uživatelům se zobrazí se zpráva s vysvětlením, že nebyly nainstalovány žádné aplikace společnosti. Uživatelé budou také moct seřadíte nebo vyfiltrujete podle stavu instalace aplikace.

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data----3145939---"></a>Konfigurace webového prohlížeče může připojit k datům organizace <!-- 3145939 -->
Intune App Protection zásady (aplikace) na zařízeních s Androidem a iOS vám umožní přenést organizace webové odkazy do určitého webového prohlížeče nad rámec Intune Managed Browser nebo Microsoft Edge.  Další informace o aplikaci, najdete v článku [co jsou zásady ochrany aplikací?](app-protection-policy.md).

#### <a name="installed-apps-page-on-the-company-portal-website-----4224326---"></a>Na webu portál společnosti nainstalovaný stránky aplikace  <!-- 4224326 -->
[Webu portál společnosti](https://portal.manage.microsoft.com/) nové stránky do zobrazit uživatele bude obsahovat všechny aplikace, které byly nainstalovány na svých zařízeních. Tento seznam obsahuje dostupné aplikace a na aplikace, které vyžadují jejich organizace. Na této stránce Uživatelé budou moci zobrazit stavy instalace a požadavky aplikací na svém zařízení. Další informace o webu portál společnosti, naleznete v tématu [použití webu portál společnosti Intune](/intune-user-help/using-the-intune-company-portal-website.md) a [konfigurace aplikace portál společnosti Microsoft Intune](company-portal-app.md).

#### <a name="call-graph-api-read-operations-from-an-application-without-user-credentials----4655885---"></a>Volání rozhraní Graph API, operace čtení z aplikace bez přihlašovacích údajů uživatele <!-- 4655885 -->
Aplikace bude moct volat rozhraní Intune Graph API s identitou aplikace bez přihlašovacích údajů uživatele operace čtení. Další informace najdete v tématu [získat přístup bez uživatele](https://docs.microsoft.com/graph/auth-v2-service).

<!-- ***********************************************-->
### <a name="device-configuration"></a>Konfigurace zařízení


#### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Podpora IKEv2 VPN profily pro iOS <!-- 1943438 -->
Budete mít k vytvoření profilů sítě VPN pro iOS nativního klienta VPN pomocí protokolu IKEv2. IKEv2 je nový typ připojení v **konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS**  pro platformu > **VPN** pro typy profilů > **nastavení**.

Tyto profily sítě VPN nakonfigurovat nativního klienta VPN. Ano žádné aplikace klienta VPN jsou nainstalovány nebo nahrány do spravovaných zařízení. Tato funkce vyžaduje, aby zařízení zaregistrovaná v Intune (registrace MDM).

Pokud chcete zobrazit aktuální nastavení sítě VPN můžete nakonfigurovat, přejděte na [nastavení konfigurace sítě VPN na zařízeních s Iosem v Microsoft Intune](vpn-settings-ios.md).

Platí pro: iOS

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices----20430240---"></a>Konfigurace nastavení pro rozšíření jádra na zařízeních s macOS <!-- 20430240 -->
Na zařízeních s macOS, můžete vytvořit profil konfigurace zařízení (**konfigurace zařízení** > **profily** > **vytvořit profil** > Zvolte **macOS** pro platformu). Budoucí aktualizace, která bude obsahovat novou skupinu nastavení, která umožňují nakonfigurovat a používat rozšíření jádra na vašich zařízeních.

Platí pro: macOS 10.13.2 a novější

#### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Hledat směrný plán podpory pro klíčové slovo  <!-- 3082036         -->
Při vytváření nebo úpravu profil standardních hodnot zabezpečení, které už brzy bude možné použít *hledání* vyfiltrujete nastavení, které zobrazují v konzole.   

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Použijte "pravidla použitelnosti" při vytváření profilů konfigurace zařízení s Windows 10 <!-- 2549910 -->
Vytváření profilů konfigurace zařízení s Windows 10 (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **Windows 10** pro platformu). Budete moct vytvořit **pravidla použitelnosti** tak profil, který se vztahuje pouze na konkrétní edici nebo konkrétní verzi. Například vytvořit profil, který umožňuje některá nastavení nástroje BitLocker. Po přidání profilu použijte použije pravidlo použitelnosti, tak profil, který platí jenom pro zařízení s Windows 10 Enterprise.

Platí pro: 
- Windows 10 a novější

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options----2697002----"></a>Aplikace ze storu jenom nastavení pro zařízení s Windows 10 obsahuje další možnosti konfigurace <!-- 2697002  -->

Když vytvoříte profil omezení zařízení pro zařízení s Windows, můžete použít **aplikace ze storu jenom** nastavení, takže uživatelé instalují jenom aplikace z App Store Windows (**konfigurace zařízení**  >  **Profily** > **vytvořit profil** > **Windows 10 a novější** pro platformu > **zařízení omezení** pro typ profilu). Toto nastavení bude v budoucí aktualizaci rozšířena do další možnosti podpory. 

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení Windows 10 (a novějších) zařízení a povolení nebo zakázání funkcí pomocí Intune](device-restrictions-windows-10.md#app-store).

Platí pro: Windows 10 a novější

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group----4089955---"></a>Více Zebra mobility rozšíření zařízení profily nasadit do zařízení, stejnou skupinu uživatelů nebo stejné skupiny zařízení <!-- 4089955 -->
V Intune můžete použít rozšíření mobility Zebra (MX) v profilu konfigurace zařízení k nastavení nebo přidat nastavení nejsou integrované do Intune. V současné době můžete nasadit jeden profil pro jedno zařízení. V budoucí aktualizaci budete moct nasadit více profilů, můžete:

- Stejnou skupinu uživatelů
- Do stejné skupiny zařízení
- Jedno zařízení

[Použití a správa zařízení Zebra s příponami Zebra nastavení mobilních zařízení v Microsoft Intune](android-zebra-mx-overview.md) ukazuje způsob použití MX v Intune.

Platí pro: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow----4404075----"></a>Některá nastavení beznabídkového režimu na zařízeních s Iosem jsou nastaveny pomocí "Blok" nahrazuje "Povolit" <!-- 4404075  -->
Když vytvoříte profil omezení zařízení na zařízeních s Iosem (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **iOS** pro platformu > **omezení zařízení** pro typy profilů > **veřejného terminálu**), můžete nastavit **automatické zamykání**, **Vyzvánění**, **otočení obrazovky**, **tlačítko pro režim spánku obrazovky**, a **hlasitosti**. 

V současné době tato nastavení jsou konfigurována pomocí **povolit** (zablokuje funkci) nebo **Nenakonfigurováno** (umožňuje funkci). V budoucí aktualizaci hodnoty budou **bloku** (zablokuje funkci) nebo **Nenakonfigurováno** (umožňuje funkci).

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s Iosem k povolení nebo zakázání funkce](device-restrictions-ios.md). 

Platí pro: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices----4490704----"></a>Pro ověřování pomocí hesla na zařízeních s Iosem pomocí Face ID. <!-- 4490704  -->
Když vytvoříte profil omezení zařízení pro zařízení s Iosem, můžete použít otisk prstu k zadání hesla. V budoucí aktualizaci nastavení hesla otisk prstu také povolit rozpoznávání obličeje (**konfigurace zařízení** > **profily** > **vytvořit profil**   >  **iOS** pro platformu > **omezení zařízení** pro typy profilů > **heslo**). V důsledku toho se mění následující nastavení:

- **Odemknutí pomocí otisků prstů** je nyní **Touch ID a Face ID odemknout**.
- **Otisků prstů (jenom pod dohledem)** je nyní **změny Touch ID a Face ID (jenom pod dohledem)** .

Face ID je k dispozici v Iosu 11.0 a novějších. Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s Iosem k povolení nebo zakázání funkcí pomocí Intune](device-restrictions-ios.md#password).

Platí pro: iOS

#### <a name="apps-feature-is-dependent-on-ratings-region-when-restricting-gaming-and-app-store-features-on-ios-devices----4593948----"></a>Funkce aplikace je závislá na oblast hodnocení, když omezíte hry a aplikace ukládat funkce na zařízeních s Iosem <!-- 4593948  -->
Na zařízeních s Iosem, můžete povolit nebo omezit funkce související s hry, app storu a zobrazování dokumentů (**konfigurace zařízení** > **profily**  >   **Vytvoření profilu** > **iOS** pro platformu > **omezení zařízení** pro typy profilů > **App Store, zobrazování dokumentů, hraní her**). Můžete také oblast hodnocení, jako jsou USA. V budoucí aktualizaci **aplikace** funkce se přesune na podřízené **oblast hodnocení**a je závislý na **oblast hodnocení**.

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s Iosem k povolení nebo zakázání funkcí pomocí Intune](device-restrictions-ios.md#app-store-doc-viewing-gaming).

Platí pro: iOS

#### <a name="administrative-templates-for-group-policy---------3510695---"></a>Šablony pro správu zásad skupiny     <!--  3510695 -->
K vylepšení zabezpečení pro zařízení v cloudu, Připravujeme k vydání šablony pro správu, které vám umožní nakonfigurovat vyberte nastavení zásad skupiny pro počítače s Windows pomocí Intune.  Tyto šablony pomocí zásad poskytovatele konfiguračních služeb (CSP) můžete poskytnout až 2 500 dalších nastavení z Onedrivu, Office a Windows.

####  <a name="new-settings-for-the-windows-security-baseline-----3534649-4217151------------"></a>Nová nastavení pro požadovaný směrný plán zabezpečení Windows  <!-- 3534649, 4217151          -->
Přidáváme nová nastavení do tohoto směrného plánu zabezpečení Windows. První nastavení je určené pro zabezpečení na základě virtualizace, která vyžaduje zabezpečené spouštění. Druhé nastavení umožňují spravovat hlasové aktivace aplikací pro Windows, když se uzamkne jeho obrazovka.

#### <a name="security-baselines-will-be-generally-available------3785395---------"></a>Základní nastavení zabezpečení bude obecně dostupná  <!--  3785395       -->
Základní nastavení zabezpečení funkce bude brzy z verze preview a obecně dostupná. 

#### <a name="the-windows-security-baseline-template-will-be-generally-available-------3794072---------"></a>Šablona základního zabezpečení Windows bude obecně dostupná   <!--  3794072       -->
Šablona základního zabezpečení Windows bude brzy z verze preview a obecně dostupná. Šablony ve verzi preview skončí a nová šablona bude k dispozici.

<!-- ***********************************************-->
### <a name="device-management"></a>Správa zařízení

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group----3173810---"></a>Přiřadit značky oboru všech spravovaných zařízení ve skupině zabezpečení <!-- 3173810 -->
V současné době můžete přiřadit značky oboru do zařízení tak, že přejdete do každé jednotlivé zařízení **vlastnosti** stránky a výběru značek oboru. V budoucí aktualizaci budete moct přiřadit značky oboru do skupiny zabezpečení a všechna zařízení ve skupině zabezpečení se také přidruží tyto značky oboru. Chcete-li to provést, zvolte **Intune** > **role** > **obor (značky)**  > **vytvořit**  >  **Obor (značky)** > vyberte skupiny, ke kterým chcete přiřadit značky oboru. Všechna zařízení v těchto skupinách budou také přiřadit značky oboru. Značky oboru, nastavit pomocí této funkce dojde k přepsání značky oboru, nastavte pomocí aktuální flow značky oboru zařízení. (V budoucí aktualizaci, aktuální tok přiřadit značky oboru zařízení budou jen pro čtení.)

#### <a name="see-the-security-patch-level-for-android-devices----4461911----"></a>Zobrazit úroveň opravy zabezpečení pro zařízení s Androidem <!-- 4461911  -->
Budete moci zobrazit úroveň opravy zabezpečení pro zařízení s Androidem. Chcete-li to provést, zvolte **Intune** > **zařízení** > **všechna zařízení** > zvolte zařízení > **monitorování**  >  **Hardwaru**.


<!-- ***********************************************-->
## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).


