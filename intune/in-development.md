---
title: Při vývoji – Microsoft Intune
titleSuffix: ''
description: Microsoft Intune funkce vývoje
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 969e7bc4804e1f66230c76d742bec2c67c2fa006
ms.sourcegitcommit: 99b74d7849fbfc8f5cf99cba33e858eeb9f537aa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/31/2019
ms.locfileid: "68670918"
---
# <a name="in-development-for-microsoft-intune---august-2019"></a>Ve vývoji pro Microsoft Intune – srpen 2019

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

### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment----3504144---"></a>Řízení chování při odinstalaci aplikace pro iOS při zrušení registrace zařízení <!-- 3504144 -->
Správci budou moct spravovat, jestli se aplikace v zařízení odebere nebo zachová, když se zruší registrace zařízení na úrovni uživatele nebo skupiny zařízení. 

### <a name="categorize-microsoft-store-for-business-apps----3926922---"></a>Kategorizace Microsoft Store pro obchodní aplikace <!-- 3926922 -->
Microsoft Store pro obchodní aplikace budete moct zařadit do kategorií. Provedete to tak > , že zvolíte**aplikace** Intune**Client Apps** > > vyberte**kategorii**aplikace Microsoft Store pro firmy > **informace** > . V rozevírací nabídce přiřaďte kategorii.
### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Konfigurace obsahu oznámení aplikace pro účty organizace <!-- 2576686 -->
Zásady ochrany aplikací Intune (aplikace) na zařízeních s Androidem a iOS vám umožní řídit obsah oznámení aplikací pro účty org. Tato funkce bude vyžadovat podporu aplikací a nemusí být k dispozici pro všechny aplikace s podporou aplikací. Další informace o aplikaci najdete v tématu [co jsou zásady ochrany aplikací?](app-protection-policy.md).

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Dostupná Google Play vytváření sestav aplikací pro pracovní profily Androidu <!-- 3041956  -->
Pro dostupná instalace aplikací na zařízeních s pracovním profilem Androidu můžete zobrazit stav instalace aplikace a nainstalovanou verzi spravovaných aplikací Google Play. Další informace najdete v tématu [monitorování zásad ochrany aplikací](app-protection-policies-monitor.md), [Správa zařízení s pracovním profilem Androidu pomocí Intune](android-enterprise-overview.md) a [spravovaného Google Play typu aplikace](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfigurace zařízení

### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release----4867809----"></a>Některá z nesledovaných omezení zařízení s iOS se budou pod dohledem – jenom s vydáním iOS 13,0. <!-- 4867809  -->
Některá nastavení budou platit pro zařízení, která jsou jenom pod dohledem, pomocí verze iOS 13,0. Mezi tato nastavení patří:

- App Store, zobrazování dokumentů, hraní her
  - App Store
  - Explicitní obsah iTunes, hudba, podcast nebo zprávy
  - Přidání přátel Game Center
  - Hry pro více hráčů
- Integrované aplikace
  - Fotoaparát
    - FaceTime
  - Safari
    - Automatické vyplňování
- Cloud a úložiště
  - Zálohování do iCloud
  - Zablokovat synchronizaci dokumentů iCloud
  - Blokovat synchronizaci řetězce klíčů iCloud

Pokud jsou tato nastavení nakonfigurovaná a přiřazená k zařízením, která nejsou pod dohledem před vydáním iOS 13,0, nastavení se pořád aplikují na tato zařízení, která nejsou pod dohledem. I nadále platí i po upgradu zařízení na iOS 13,0. Tato omezení se odeberou na nekontrolovaných zařízeních, která se zálohují a obnovují. 

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s iOS, abyste mohli povolit nebo zakázat funkce využívající Intune](device-restrictions-ios.md).

Platí pro:  
- iOS 13,0 a novější

### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices----4867699-4867709----"></a>Nové nastavení a změny stávajících nastavení pro omezení funkcí v zařízeních s iOS a macOS <!-- 4867699 4867709  -->
Budete moct vytvářet profily pro omezení nastavení na zařízeních s iOS a MacOS (**Konfigurace** > zařízení**profily** > **vytvořit profil** > **iOS** nebo **MacOS** pro platformu). Zadejte > **omezení zařízení**). Budou přidány následující funkce:

- V > případě**omezení**zařízení MacOS Cloud a úložiště pomocí nového nastavení pro zablokování uživatelům zablokujte spouštění práce na jednom zařízení MacOS a pokračujte v práci na jiném zařízení MacOS nebo iOS. > 
  Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení MacOS a povolte nebo omezte funkce pomocí Intune](device-restrictions-macos.md).
- V případě**omezení zařízení**s **iOS** > je k dispozici několik změn:
  - **Integrované aplikace** > **hledají můj iPhone (jenom pod dohledem)** : Nové nastavení, které tuto funkci blokuje v funkci najít aplikaci. 
  - **Integrované aplikace** > **hledají moje přátele (jenom pod dohledem)** : Nové nastavení, které tuto funkci blokuje v funkci najít aplikaci. 
  - Bezdrátová > **Změna stavu Wi-Fi (jenom pod dohledem)** : Nové nastavení, které uživatelům brání v zapnutí nebo vypnutí sítě Wi-Fi na zařízení.
  - **QuickPath klávesnice a slovníku** >  **(jenom pod dohledem)** : Nové nastavení, které blokuje funkci QuickPath.
  - **Cloud a úložiště**: **Pokračování aktivity** se přejmenovalo na **odevzdání**.

  Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s iOS, abyste mohli povolit nebo zakázat funkce využívající Intune](device-restrictions-ios.md).

Platí pro:  
- macOS 10,15 a novější
- iOS 13 a novější

### <a name="control-the-apps-files-documents-and-folders-that-open-when-user-signs-in-to-macos-devices---3914202----"></a>Řízení aplikací, souborů, dokumentů a složek, které se otevřou, když se uživatel přihlásí k zařízení macOS <!--3914202  -->
V zařízeních MacOS budete moct povolit a nakonfigurovat funkce (**profily** > **Konfigurace** > zařízení**vytvořit profil** > **MacOS** pro funkce platformy > **zařízení** pro Typ profilu). 

K dispozici jsou nové nastavení přihlašovacích položek, které určuje, které aplikace, soubory, dokumenty a složky se otevřou, když se uživatel přihlásí k zaregistrovanému zařízení. 

Pokud chcete zobrazit aktuální nastavení, přejděte na [Nastavení funkcí zařízení MacOS v Intune](macos-device-features-settings.md).

Platí pro:  
- macOS

### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode----3755304-3041943-3041946----"></a>Nové funkce pro vyhrazená zařízení s Androidem Enterprise v režimu více aplikací <!-- 3755304 3041943 3041946  -->
Můžete ovládat funkce a nastavení v celoobrazovkovém prostředí na vyhrazených zařízeních s Androidem Enterprise. Provedete to tak, že zvolíte**profily** >  **Konfigurace** > zařízení**vytvořit profil** > pro**Android Enterprise** pro platformu > **jenom pro vlastníka zařízení, omezení** pro typ profilu.

Budou přidány následující funkce:
-  > **Multi-aplikace**vyhrazených zařízení: **Tlačítko virtuální domů** se dá zobrazit tak, že se na zařízení přetáhne nahoru nebo se na obrazovce zobrazí plovoucí, aby ho uživatelé mohli přesunout.
-  > **Multi-aplikace**vyhrazených zařízení: **Svítící Access** umožňuje uživatelům používat svítící. 
-  > **Multi-aplikace**vyhrazených zařízení: **Ovládání hlasitosti médií** umožňuje uživatelům řídit hlasitost média zařízení pomocí posuvníku. 
-  > **Multi-aplikace**vyhrazených zařízení:  Povolte šetřič obrazovky, nahrajte vlastní obrázek a ovládací prvek, když se zobrazí spořič obrazovky.

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo omezte funkce pomocí Intune](device-restrictions-android-for-work.md#dedicated-device-settings).

Platí pro:  
- Zařízení se systémem Android Enterprise vyhrazená

### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices----3574215----"></a>Nové aplikace a konfigurační profily pro zařízení s plnou správou pro Android Enterprise <!-- 3574215  -->
Pomocí profilů budete moct nakonfigurovat nastavení, která použijí nastavení VPN, e-mailu a Wi-Fi pro plně spravovaná zařízení s Androidem Enterprise. Budete moci:
- Pomocí profilů aplikací nasaďte nastavení Outlooku, Gmail a devět pracovních e-mailů.
- Pomocí profilů konfigurace zařízení nasaďte nastavení důvěryhodných kořenových certifikátů.
- Pomocí profilů konfigurace zařízení nasaďte nastavení sítě VPN a Wi-Fi.

Uživatelé se budou ověřovat pomocí svého uživatelského jména a hesla pro profily sítě VPN, Wi-Fi a e-mailu. V současné době není ověřování založené na certifikátech k dispozici. 

Platí pro:  
- Plně spravovaná platforma Android Enterprise

### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Podpora pro profily IKEv2 VPN pro iOS <!-- 1943438 -->
Pomocí protokolu IKEv2 budete moct vytvořit profily sítě VPN pro klienta iOS Native. IKEv2 je nový typ připojení v**profilech** >  **Konfigurace** > zařízení**vytvořit profil** > **iOS** pro Platform > **VPN** pro typ profilu > **Nastavení**.

Tyto profily sítě VPN konfigurují nativního klienta VPN. Žádné klientské aplikace VPN proto nejsou nainstalované ani vložené do spravovaných zařízení. Tato funkce vyžaduje, aby byla zařízení zaregistrovaná v Intune (registrace MDM).

Chcete-li zobrazit aktuální nastavení sítě VPN, která můžete konfigurovat, přejděte na téma [Konfigurace nastavení sítě VPN na zařízeních s iOS v Microsoft Intune](vpn-settings-ios.md).

Platí pro: iOS

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Registrace zařízení

### <a name="skip-more-screens-in-setup-assistant---4877451---"></a>Přeskočit další obrazovky v Průvodci nastavením <!--4877451 -->
Budete moct nastavit profily Program registrace zařízení, abyste mohli přeskočit následující obrazovky Průvodce nastavením: 
- Čas obrazovky
- Nastavení Touch ID

Provedete to tak, že přejdete na **registrace** > zařízení registrace**Apple** > **tokeny programu registrace** > vyberte profil > **profily** > vyberte profil > **vlastnosti** > **Upravit** vedle **Možnosti přizpůsobení pomocníka s nastavením**.
Další informace o přizpůsobení pomocníka s nastavením najdete v tématu [vytvoření registračního profilu Apple ](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile).

### <a name="android-enrollment-device-administrator-support----4869749----"></a>Podpora Správce zařízení registrace Androidu <!-- 4869749  -->
Možnost registrace Správce zařízení s Androidem se přidá na stránku registrace Androidu ( > **registrace**zařízení s Androidem**pro registraci** > zařízení v Intune). Správce zařízení s Androidem bude ve výchozím nastavení pro všechny klienty stále povolen.  

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>Pro zařízení s iOS si Přizpůsobte obrazovku ochrana osobních údajů procesu registrace Portál společnosti <!-- 4394993  -->
Pomocí Markdownu budete moci přizpůsobit obrazovku ochrany osobních údajů v Portál společnosti, kterou koncoví uživatelé uvidí během registrace iOS. Konkrétně budete moct přizpůsobit seznam věcí, které vaše organizace nemůže zobrazit nebo dělat na zařízení.

<!-- ***********************************************-->
## <a name="device-management"></a>Správa zařízení

### <a name="build-number-included-on-android-device-hardware-page----4461910----"></a>Číslo sestavení zahrnuté na stránce hardware pro zařízení s Androidem <!-- 4461910  -->
Nová položka na stránce hardware pro každé zařízení s Androidem bude obsahovat číslo buildu operačního systému daného zařízení.

### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Nakonfigurujte automatický časový limit pro vyčištění zařízení na 30 dní. <!--4231059  -->
Po posledním přihlášení budete moct nastavit automatický časový limit pro vyčištění zařízení, který je kratší než 30 dní (místo aktuálního limitu 90 dní). Provedete to tak, > že přejdete na**zařízení** > Intune**Nastavení** > **pravidla vyčistit zařízení**.

<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Řízení přístupu na základě role

### <a name="default-scope-tag----3702875---"></a>Výchozí značka oboru <!-- 3702875 -->
K dispozici je nově integrovaná značka výchozího oboru. Všechny neoznačené objekty Intune, které podporují značky oboru, se automaticky přiřazují k výchozí značce oboru. **Výchozí** značka oboru bude přidána do všech existujících přiřazení rolí, aby bylo možné zachovat v současnosti paritu s prostředím pro správu. Pokud nechcete, aby správce viděli objekty Intune s výchozími značkami oboru, odeberte výchozí značku oboru z přiřazení role. Tato funkce je podobná funkci obory zabezpečení v System Center Configuration Manager.

<!-- ***********************************************-->
## <a name="security"></a>Zabezpečení

### <a name="import-and-export-security-baselines------3408610------------"></a>Import a export standardních hodnot zabezpečení    <!--3408610          -->  
Přidáváme možnost exportu a importu standardních hodnot zabezpečení. Tato funkce vám umožní převzít vlastní nastavení a sdílet je mezi prostředími Intune.

<!-- ***********************************************-->
## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).




