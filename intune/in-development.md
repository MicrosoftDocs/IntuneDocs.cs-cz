---
title: Při vývoji – Microsoft Intune
titleSuffix: ''
description: Microsoft Intune funkce vývoje
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4bd5392abba3ea22127cb9bcbbb53ec4929f2d5e
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2019
ms.locfileid: "71166352"
---
# <a name="in-development-for-microsoft-intune---september-2019"></a>Ve vývoji Microsoft Intune – září 2019

Tato stránka vám pomůže s vaším připravenostm a plánováním vypisuje aktualizace uživatelského rozhraní Intune a funkce, které jsou ve vývoji, ale ještě nejsou vydané. Navíc platí:

- Pokud předpokládáme, že před změnou budete muset provést nějakou akci, zveřejníme doplňkový příspěvek centra zpráv Office.
- Pokud se funkce spustí v produkčním prostředí, buď jako verze Preview, nebo všeobecně dostupná, popis funkce se přesune mimo tuto stránku a na [stránku co je nového](whats-new.md).
- Tato stránka a [Stránka co je nového](whats-new.md) se pravidelně aktualizují. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.
- Strategické dodávky a časové osy najdete v tématu [Přehled M365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) .

> [!Note]
> Tyto položky odrážejí aktuální očekávání Microsoftu týkající se možností Intune, které přichází v budoucí verzi. Data a jednotlivé funkce se můžou změnit. Ne všechny položky ve vývoji obsahují popis funkce na této stránce.

**Informační kanál RSS**: Po aktualizaci této stránky se zobrazí oznámení zkopírováním a vložením následující adresy URL do čtečky informačních kanálů:`https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
#### App management
#### Device configuration
#### Device enrollment
#### Device management
#### Intune apps
#### Monitor and troubleshoot
#### Role-based access control
#### Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Správa aplikací

### <a name="managed-google-play-private-lob-apps----1464182----"></a>Spravované Google Play soukromé obchodní aplikace <!-- 1464182  -->
Intune umožní správcům IT publikovat privátní obchodní aplikace pro Android do spravovaných Google Play prostřednictvím IFRAME vloženého v konzole Intune.  V současné době potřebují správci IT publikovat obchodní aplikace přímo do konzoly pro publikování Google, která vyžaduje mnoho kroků a je velmi časově náročná.  Tato nová funkce umožňuje snadno publikovat obchodní aplikace s minimální sadou kroků, aniž byste museli opustit konzolu Intune.  Tato funkce může využít některý ze scénářů správy Android Enterprise, které používají spravované Google Play (pracovní profil, vyhrazená, plně spravovaná a neregistrovaná zařízení).  V Intune vyberte**aplikace** >  **klientské aplikace** > **Přidat**. Pak v seznamu **Typ aplikace** vyberte **spravovaná Google Play** . Další informace o spravovaných aplikacích Google Play najdete v tématu [Přidání spravovaných Google Play aplikací do zařízení s Androidem Enterprise v Intune](apps-add-android-for-work.md).

### <a name="company-portal-app-installation-status-messages----2514416----"></a>Portál společnosti stavových zpráv instalace aplikace <!-- 2514416  -->
Aplikace Portál společnosti zobrazí koncovým uživatelům další zprávy o stavu instalace aplikace. Následující podmínky se vztahují na nové funkce závislosti Win32:
- Aplikaci se nepovedlo nainstalovat. Nevyhověly závislosti definované správcem.
- Aplikace byla úspěšně nainstalována, ale vyžaduje restart.
- Aplikace se právě instaluje, ale vyžaduje restart, aby bylo možné pokračovat.

### <a name="managed-google-play-iframe-support----2871756----"></a>Podpora spravované Google Play IFRAME <!-- 2871756  -->
Intune bude poskytovat podporu pro přidávání a správu webových odkazů přímo v konzole Intune prostřednictvím spravovaného Google Play IFRAME.  To umožňuje správcům IT odeslat obrázek adresy URL a ikony a potom tyto odkazy nasadit na zařízení stejně jako běžné aplikace pro Android. Tato funkce může využít některý ze scénářů správy Android Enterprise, které používají spravované Google Play (pracovní profil, vyhrazená, plně spravovaná a neregistrovaná zařízení).  V Intune vyberte**aplikace** >  **klientské aplikace** > **Přidat**. Pak v seznamu **Typ aplikace** vyberte **spravovaná Google Play** . Další informace o spravovaných aplikacích Google Play najdete v tématu [Přidání spravovaných Google Play aplikací do zařízení s Androidem Enterprise v Intune](apps-add-android-for-work.md).

### <a name="macos-support-for-vpp-apps----3173501----"></a>Podpora macOS pro aplikace VPP <!-- 3173501  -->
aplikace macOS, které jste zakoupili pomocí Apple Business Manageru, se zobrazí v konzole nástroje, když se v Intune synchronizují tokeny programu Apple VPP. Pomocí konzoly nástroje můžete přiřadit a odvolat a znovu přiřadit licence na zařízení a uživatele pro skupiny. Microsoft Intune pomáhá spravovat aplikace VPP zakoupené pro použití ve vaší společnosti:
- Vykazuje informace o licencích z App Storu.
- Sleduje počet použitých licencí.
- Pomáhá zajistit, abyste nenainstalovali více kopií aplikace, než vlastníte.
Další informace o Intune a VPP najdete v tématu [Správa hromadně zakoupených aplikací a knih pomocí Microsoft Intune](vpp-apps.md).

### <a name="macos-support-for-web-apps----3174427----"></a>Podpora macOS pro webové aplikace <!-- 3174427  -->
Budete moct nainstalovat webové aplikace, které vám umožní přidat zástupce na adresu URL na webu do Docku pomocí Portál společnosti macOS. Koncoví uživatelé mohou získat přístup k akci **instalace** ze stránky s podrobnostmi o aplikaci pro webovou aplikaci ve MacOS portál společnosti. Další informace o typu aplikace **webový odkaz** najdete v tématu [přidání aplikací do Microsoft Intune](apps-add.md).

#### <a name="assign-microsoft-edge-beta-for-macos----4678761----"></a>Přiřadit Microsoft Edge beta pro macOS <!-- 4678761  -->
Do Intune pro zařízení macOS budete moct přidat a přiřadit nejnovější verzi Microsoft Edge beta. V Intune vyberte**aplikace** >  **klienta** > aplikace**Přidat aplikaci** > **Microsoft Edge – MacOS**. Pak přiřaďte aplikaci Microsoft Edge beta k požadovaným skupinám. Microsoft AutoUpdate (MAU) udržuje Microsoft Edge v aktuálním stavu. Další informace o Microsoft Edge najdete v tématu [Správa webového přístupu pomocí Microsoft Edge s Microsoft Intune](manage-microsoft-edge.md).

### <a name="read-and-write-graph-api-operations-for-intune-apps----5031704----"></a>Čtení a zápis Graph APIch operací pro aplikace Intune <!-- 5031704  -->
Aplikace budou moci volat Graph API Intune pomocí operací čtení i zápisu pomocí identity aplikace bez přihlašovacích údajů uživatele. Další informace o přístupu k rozhraní Microsoft Graph API pro Intune najdete [v tématu práce s Intune v Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Konfigurace obsahu oznámení aplikace pro účty organizace <!-- 2576686 -->
Zásady ochrany aplikací Intune (aplikace) na zařízeních s Androidem a iOS vám umožní řídit obsah oznámení aplikací pro účty org. Tato funkce bude vyžadovat podporu aplikací a nemusí být k dispozici pro všechny aplikace s podporou aplikací. Další informace o aplikaci najdete v tématu [co jsou zásady ochrany aplikací?](app-protection-policy.md).

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Dostupná Google Play vytváření sestav aplikací pro pracovní profily Androidu <!-- 3041956  -->
Pro dostupná instalace aplikací na zařízeních s pracovním profilem Androidu můžete zobrazit stav instalace aplikace a nainstalovanou verzi spravovaných aplikací Google Play. Další informace najdete v tématu [monitorování zásad ochrany aplikací](app-protection-policies-monitor.md), [Správa zařízení s pracovním profilem Androidu pomocí Intune](android-enterprise-overview.md) a [spravovaného Google Play typu aplikace](apps-add-android-for-work.md#managed-google-play-app-types).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfigurace zařízení

### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type----4886161----"></a>Funkce zařízení, omezení zařízení a profily rozšíření pro nastavení iOS a macOS se zobrazují podle typu registrace. <!-- 4886161  -->

V Intune vytvoříte profily pro zařízení s iOS a MacOS (**profily** > **Konfigurace** > zařízení**vytvořit profil** > pro**iOS** nebo **MacOS** pro funkce platforem > zařízení)., **Omezení zařízení**nebo **rozšíření** pro typ profilu). V současné době jsou uvedená dostupná nastavení v těchto profilech. 

V budoucí aktualizaci budou dostupná nastavení na portálu Intune zařazená do kategorie podle typu registrace, který platí pro:

- iOS
  - Všechny typy registrace
  - Registrace zařízení a automatizované registrace zařízení
  - Automatický zápis zařízení

- macOS
  - Všechny typy registrace
  - Registrace zařízení
  - Uživatelem schválené a automatizované registrace zařízení
  - Automatický zápis zařízení

Platí pro:

- iOS
  - [Funkce zařízení](ios-device-features-settings.md)
  - [Omezení zařízení](device-restrictions-ios.md)

- macOS
  - [Funkce zařízení](macos-device-features-settings.md)
  - [Omezení zařízení](device-restrictions-macos.md)
  - [Rozšíření](kernel-extensions-settings-macos.md)

### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode----4892835----"></a>Nové nastavení ovládání hlasu pro zařízení s iOS běžící v celoobrazovkovém režimu <!-- 4892835  -->

V Intune můžete vytvořit zásady pro spuštění zařízení se systémem iOS pod dohledem jako veřejného terminálu nebo vyhrazeného zařízení (**Konfigurace** > zařízení**profily** > **vytvořit profil** > **iOS** pro > **platforem). Omezení zařízení** pro typ profilu > veřejného **terminálu (jenom pod dohledem)** ). 

V budoucí aktualizaci budou k dispozici nová nastavení, která můžete řídit:

- **Ovládání hlasu**: Povolí ovládání hlasu na zařízení v celoobrazovkovém režimu.
- **Změna ovládacího prvku hlas**: Umožňuje uživatelům změnit nastavení ovládacího prvku hlasu v zařízení v celoobrazovkovém režimu.

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení pro veřejného terminálu iOS (jenom pod dohledem)](device-restrictions-ios.md#kiosk).

Platí pro:

- iOS 13,0 a novější

### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices----4893175----"></a>Použití jednotného přihlašování pro aplikace a weby na zařízeních s iOS a macOS <!-- 4893175  -->
V budoucí aktualizaci bude k dispozici několik nových nastavení jednotného přihlašování pro zařízení s iOS a MacOS (**Konfigurace** > zařízení**profily** > **vytvořit profil** > **iOS** nebo **MacOS** pro **funkce** > platforem pro typ profilu).

Pomocí těchto nastavení můžete nakonfigurovat jednotné přihlašování, zejména pro aplikace a weby, které používají ověřování pomocí protokolu Kerberos. Můžete si vybrat mezi obecnými přihlašovacími údaji jednotného přihlašování aplikace a integrovaným rozšířením Kerberos společnosti Apple.

Pokud chcete zobrazit aktuální funkce zařízení, které můžete konfigurovat, přejděte na [funkce zařízení s iOS](ios-device-features-settings.md) a [MacOS funkce zařízení](macos-device-features-settings.md).

Platí pro:

- iOS 13,0 a novější
- macOS 10,15 a novější

### <a name="associate-domains-to-apps-on-macos-1015-devices----4898079----"></a>Přidružení domén k aplikacím na macOS 10.15 a zařízeních <!-- 4898079  -->
Na zařízeních MacOS můžete konfigurovat různé funkce a nasdílením těchto funkcí do zařízení pomocí zásad (**Konfigurace** > zařízení**profily** > **vytvořit profil** > **MacOS** pro **funkce** > platforem pro typ profilu). V budoucí aktualizaci budete moct přidružit domény k vašim aplikacím. Tato funkce pomáhá sdílet přihlašovací údaje s weby souvisejícími s vaší aplikací a lze ji použít s rozšířením jednotného přihlašování společnosti Apple, univerzálními odkazy a automatického vyplňování hesel. 

Pokud chcete zobrazit aktuální funkce, které můžete nakonfigurovat, přejděte na [Nastavení funkcí zařízení MacOS v Intune](macos-device-features-settings.md).

Platí pro:

- macOS 10,15 a novější

### <a name="use-itunes-and-apps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices----4928474----"></a>Při zobrazování nebo skrývání aplikací na zařízeních s iOS pod dohledem použijte v adrese URL obchodu iTunes aplikace iTunes a aplikace. <!-- 4928474  --> 
V Intune můžete vytvářet zásady pro zobrazování nebo skrývání aplikací na zařízeních s iOS pod dohledem (**Konfigurace** > zařízení**profily** > **vytvořit profil** > **iOS** pro zařízení > platformy.  **omezení** pro typ profilu > **Zobrazit nebo skrýt aplikace (jenom pod dohledem)** ). 

Můžete zadat adresu URL obchodu s aplikacemi iTunes, například `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`. V budoucí aktualizaci budete moci použít obojí `apps` i `itunes` v adrese URL, například:

- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

Další informace o těchto nastaveních najdete v tématu [zobrazení nebo skrytí aplikací](device-restrictions-ios.md#show-or-hide-apps).

Platí pro:

- iOS

### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Podpora pro profily IKEv2 VPN pro iOS <!-- 1943438 -->
Pomocí protokolu IKEv2 budete moct vytvořit profily sítě VPN pro klienta iOS Native. IKEv2 je nový typ připojení v**profilech** >  **Konfigurace** > zařízení**vytvořit profil** > **iOS** pro Platform > **VPN** pro typ profilu > **Nastavení**.

Tyto profily sítě VPN konfigurují nativního klienta VPN. Žádné klientské aplikace VPN proto nejsou nainstalované ani vložené do spravovaných zařízení. Tato funkce vyžaduje, aby byla zařízení zaregistrovaná v Intune (registrace MDM).

Chcete-li zobrazit aktuální nastavení sítě VPN, která můžete konfigurovat, přejděte na téma [Konfigurace nastavení sítě VPN na zařízeních s iOS v Microsoft Intune](vpn-settings-ios.md).

Platí pro: iOS


<!-- ***********************************************-->
## <a name="device-enrollment"></a>Registrace zařízení

### <a name="new-tenants-will-default-away-from-android-device-administrator-management----4869790----"></a>Ve výchozím nastavení budou noví klienti pryč ze správy zařízení s Androidem. <!-- 4869790  -->
Možnosti Správce zařízení s Androidem jsou nahrazené Androidem Enterprise. Proto doporučujeme místo toho použít Android Enterprise pro nové registrace. V budoucí aktualizaci bude potřeba, aby noví klienti v rámci registrace Androidu při použití správy správců zařízení dokončili následující nezbytné kroky: Přejít na **Intune** > **registrace** > zařízení registrace zařízení s**Androidem** > **osobní a zařízení vlastněná společností pomocí oprávnění** > pro správu zařízení**použití zařízení správce ke správě zařízení**.

Stávající klienti nebudou mít ve svých prostředích žádné změny. 

Další informace o Správci zařízení s Androidem v Intune najdete v tématu [registrace Správce zařízení s Androidem](android-enroll-device-administrator.md).

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>Pro zařízení s iOS si Přizpůsobte obrazovku ochrana osobních údajů procesu registrace Portál společnosti <!-- 4394993  -->
Pomocí Markdownu budete moci přizpůsobit obrazovku ochrany osobních údajů v Portál společnosti, kterou koncoví uživatelé uvidí během registrace iOS. Konkrétně budete moct přizpůsobit seznam věcí, které vaše organizace nemůže zobrazit nebo dělat na zařízení.

<!-- ***********************************************-->
## <a name="device-management"></a>Správa zařízení

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>Nasazení aktualizací softwaru do zařízení macOS <!-- 3194876 -->
Aktualizace softwaru budete moct nasadit do skupin zařízení macOS. Tato funkce zahrnuje kritické, firmware, konfigurační soubor a další aktualizace. V příští registraci zařízení budete moct odesílat aktualizace, nebo můžete vybrat týdenní plán pro nasazení aktualizací do nebo z časového intervalu, který jste nastavili. To pomáhá při aktualizaci zařízení mimo standardní pracovní dobu nebo v případě, že je vaše Helpdesk plně přiřazená. Zobrazí se vám také podrobná sestava všech zařízení macOS s nasazenými aktualizacemi. Pokud chcete zobrazit stav konkrétních aktualizací, můžete přejít k sestavě podle jednotlivých zařízení.

### <a name="send-custom-notifications-to-a-device----4928910----"></a>Odesílání vlastních oznámení do zařízení <!-- 4928910  -->
Budete moct odesílat vlastní oznámení na konkrétní zařízení, ve kterých je nainstalovaná Portál společnosti nebo aplikace Intune. Provedete to tak, že přejdete na**zařízení** >  **Intune** > **všechna zařízení** > zvolit zařízení > **více** > **Odeslat vlastní oznámení**. 

### <a name="updates-to-android-enterprise-fully-managed-features----3464667-5227935-4062195-4631425-4631440---"></a>Aktualizace funkcí pro plně spravované verze Android Enterprise <!-- 3464667, 5227935, 4062195, 4631425, 4631440 -->

Do zařízení s Androidem spravovaná pro Android přidáváme následující podporu:

- Certifikáty SCEP pro plně spravovanou Android budou k dispozici pro ověřování certifikátů na zařízeních spravovaných jako vlastník zařízení. Certifikáty SCEP jsou už na zařízeních pracovního profilu podporované.  Pomocí certifikátů SCEP pro vlastníka zařízení budete moct: <!-- 5227935 -->
    - Vytvoření profilu SCEP v části DO v Androidu Enterprise
    - propojení certifikátů SCEP s profilem Wi-Fi pro ověřování
    - propojení certifikátů SCEP a provádění profilů sítě VPN pro ověřování
    - připojení certifikátů SCEP k e-mailovým profilům pro ověřování (prostřednictvím konfigurace aplikace)
- Systémové aplikace budou podporované na zařízeních s Androidem Enterprise. V Intune přidáte aplikaci pro Android Enterprise System tak, že vyberete**aplikace** >  **klientské aplikace** > **Přidat**. V seznamu **Typ aplikace** vyberte aplikace pro **Android Enterprise System**. Další informace o přidávání aplikací do Intune najdete v článku [Přidání aplikací do Microsoft Intune](apps-add.md). <!-- 4062195 -->
- V **části dodržování předpisů** > zařízení –**vlastník zařízení**s**Androidem Enterprise** > budete moct vytvořit zásady dodržování předpisů, které nastaví úroveň ověření Google SafetyNet.   <!-- 4631425 -->
- Na zařízeních se systémem Android Enterprise s plnou správou se budou podporovat poskytovatelé ochrany před mobilními hrozbami. V **Možnosti dodržování předpisů** > zařízením v zařízení s**Androidem Enterprise** > **Owner**si můžete vybrat přijatelnou úroveň hrozeb. <!-- 4631440 --> [Nastavení Androidu Enterprise k označení zařízení jako kompatibilních nebo nekompatibilních s použitím Intune](compliance-policy-create-android-for-work.md#device-owner) seznam aktuálních nastavení.


Platí pro: 
- Zařízení se systémem Android Enterprise s plnou správou

<!-- ***********************************************-->
## <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

### <a name="updated-support-experience-------5012398------"></a>Aktualizované prostředí podpory   <!--  5012398    -->
V rámci pokračujících vylepšení budeme aktualizovat prostředí podpory v konzole pro Intune.  Budeme zdokonalovat hledání v konzole a zpětná vazba pro běžné problémy a zjednodušit pracovní postup, aby kontaktoval podporu.     

<!-- ***********************************************-->
## <a name="security"></a>Zabezpečení

### <a name="tamper-protection-for-windows-defender-antivirus-----4705448---------"></a>Ochrana proti úmyslné ochraně pro antivirovou ochranu v programu Windows Defender  <!-- 4705448       -->
Do nastavení, které Intune může spravovat pro antivirovou ochranu v programu Windows Defender, přidáváme *ochranu proti falšování* . K zapnutí nebo vypnutí ochrany před zneužitím budete moct použít konfigurační profil zařízení pro Windows 10 Endpoint Protection.  Další informace o ochraně před zneužitím najdete v dokumentaci k Windows v tématu [zabránění změnám nastavení zabezpečení pomocí ochrany před neoprávněnými](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) změnami. 


<!-- ***********************************************-->
## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).




