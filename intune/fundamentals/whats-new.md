---
title: Novinky v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Zjistěte, jaké novinky přináší portál Intune Azure.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d9bbe916314d5571dccf3c073f735c6448226e6
ms.sourcegitcommit: 4bf23327af734a9811d555fbd566c31239e2acd6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "72999493"
---
# <a name="whats-new-in-microsoft-intune"></a>Co je nového v Microsoft Intune

Zjistěte, jaké novinky každý týden přináší Microsoft Intune. Můžete také najít [důležitá oznámení](#notices), [Minulá vydání](whats-new-archive.md)a informace o [tom, jak jsou aktualizace služby Intune vydané](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728).

> [!Note]
> Zavedení každé [měsíční aktualizace](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) může trvat až tři dny a bude v tomto pořadí:
>
> - Den 1: Asie a Tichomoří (APAC)
> - Den 2: Evropa, Střední východ, Afrika (Evropa)
> - Den 3: Severní Amerika
>
> Některé funkce můžou vycházet v průběhu několika týdnů a nemusí být k dispozici všem zákazníkům hned první týden.
>
> Seznam nadcházejících funkcí ve verzi najdete na [stránce pro vývoj na webu](in-development.md) .

**Informační kanál RSS**: po aktualizaci této stránky se zobrazí upozornění zkopírováním a vložením následující adresy URL do čtečky informačních kanálů: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Device security
### Intune apps
### Monitor and troubleshoot
### Role-based access control
-->  


## <a name="week-of-october-28-2019"></a>Týden od 28. října 2019

### <a name="app-management"></a>Správa aplikací 

#### <a name="dark-mode-for-ios-company-portal----4911422---"></a>Tmavý režim pro iOS Portál společnosti <!-- 4911422 -->
Pro iOS Portál společnosti je k dispozici tmavý režim. Uživatelé můžou stahovat firemní aplikace, spravovat jejich zařízení a získávat v nich podporu v barevném schématu podle nastavení zařízení. Portál společnosti pro iOS bude automaticky odpovídat nastavení zařízení koncového uživatele pro tmavý nebo lehký režim. Další informace najdete v tématu [představení tmavého režimu Microsoft Intune portál společnosti pro iOS](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Introducing-dark-mode-on-Microsoft-Intune-Company-Portal-for-iOS/ba-p/918453). Další informace o Portál společnosti pro iOS najdete v tématu [Jak konfigurovat aplikaci Microsoft Intune portál společnosti](~/apps/company-portal-app.md).

#### <a name="android-company-portal-enforced-minimum-app-version----2378776---"></a>Minimální verze aplikace pro Android Portál společnosti vynutila <!-- 2378776 -->
Pomocí nastavení **Minimální verze portál společnosti** zásady ochrany aplikací můžete zadat konkrétní minimální verzi portál společnosti, která se vynutila na zařízení koncového uživatele. Toto nastavení podmíněného spuštění umožňuje **blokovat přístup**, **Vymazat data**nebo **upozorňovat** jako na možné akce, pokud není hodnota splněna. Možné formáty pro tuto hodnotu se řídí vzorem *[hlavní]. [ Vedlejší]* , *[hlavní]. [ Vedlejší]. [Build]* nebo *[hlavní]. [ Vedlejší]. [Build]. [Revize]* . 

Nastavení **Minimální verze portál společnosti** , pokud je nakonfigurováno, bude mít vliv na každého koncového uživatele, který získá 5.0.4560.0 verze portál společnosti a jakékoli budoucí verze portál společnosti. Toto nastavení nebude mít žádný vliv na uživatele, kteří používají verzi Portál společnosti, která je starší než verze, ve které byla tato funkce vydána. Koncoví uživatelé, kteří používají automatické aktualizace aplikace na jejich zařízení, nejspíš neuvidí žádná dialogová okna této funkce, protože budou pravděpodobně na nejnovější verzi Portál společnosti. Toto nastavení platí jenom pro Android s ochranou aplikací pro zapsaná a neregistrovaná zařízení. Další informace najdete v tématu [nastavení zásad ochrany aplikací pro Android – podmíněné spuštění](~/apps/app-protection-policy-settings-android.md#conditional-launch).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Správa zařízení 
#### <a name="intune-supports-ios-11-and-later----4665324-idready-wnready---"></a>Intune podporuje iOS 11 a novější. <!-- 4665324 idready wnready -->
Registrace a Portál společnosti v Intune teď podporují iOS verze 11 a novější. Starší verze se nepodporují.

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="updated-support-experience------5012398---"></a>Aktualizované prostředí podpory   <!-- 5012398 -->

Prostředí v konzole pro [Získání pomoci a podpory pro Intune](get-support.md) se aktualizuje a zjednodušuje.  Vylepšili jsme vyhledávání v konzole a zpětnou vazbu pro běžné problémy a pracovní postup, pomocí kterého se obrátíte na podporu. Při otevírání problému podpory uvidíte odhady v reálném čase, kdy můžete očekávat zpětné volání nebo e-mailovou odpověď, a zákazníci s plánem Premier a Unified support můžou pro svůj problém snadno zadat závažnost, abyste mohli rychleji získat podporu.

<!-- ########################## -->
## <a name="week-of-october-21-2019"></a>Týden od 21. října 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="microsoft-365-device-management"></a>Správa zařízení Microsoft 365

#### <a name="improved-administration-experience-in-microsoft-365-device-management"></a>Vylepšené možnosti správy v Microsoft 365 správě zařízení

Aktualizované a zjednodušené prostředí pro správu je teď všeobecně dostupné v pracovním prostoru specialista správy zařízení Microsoft 365 v [https://devicemanagement.microsoft.com](https://devicemanagement.microsoft.com), včetně těchto:

- **Aktualizovaná navigace**: najdou se Zjednodušená navigace na první úrovni, která logicky seskupuje funkce.
- **Nové filtry platformy**: můžete vybrat jednu platformu, která na stránkách zařízení a aplikace zobrazuje jenom zásady a aplikace pro vybranou platformu.
- **Nová Domovská stránka**: rychlé zobrazení stavu služby, stavu vašeho tenanta, zpráv atd. na nové domovské stránce.

Další informace o těchto vylepšeních najdete v [blogovém příspěvku Enterprise mobility + Security](https://go.microsoft.com/fwlink/?linkid=2109094) na webu Microsoft Tech Community.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Správa aplikací

#### <a name="add-mobile-threat-defense-apps-to-unenrolled-devices----3005337---"></a>Přidání aplikací ochrany před mobilními hrozbami do neregistrovaných zařízení <!-- 3005337 -->
Můžete vytvořit zásady ochrany aplikací Intune, které můžou blokovat nebo selektivně vymazat podniková data uživatelů na základě stavu zařízení. Stav zařízení se určí pomocí vašeho zvoleného řešení ochrany před mobilními hrozbami (MTD). Tato funkce existuje v současnosti se zaregistrovanými zařízeními Intune jako nastavením dodržování předpisů pro zařízení. Díky této nové funkci rozšiřujeme detekci hrozeb od dodavatele ochrany před mobilními hrozbami, aby fungovalo na nezaregistrovaných zařízeních. V Androidu Tato funkce vyžaduje nejnovější Portál společnosti na zařízení. V systému iOS bude tato funkce dostupná pro použití v případě, že aplikace integrují nejnovější sadu Intune SDK (v 12.0.15 +). V případě, že první aplikace přijme nejnovější sadu Intune SDK, aktualizujeme téma Co je nového. Zbývající aplikace budou k dispozici na určitou bázi. Další informace najdete v tématu [Vytvoření zásady ochrany aplikací ochrany před mobilními hrozbami v Intune](~/protect/mtd-app-protection-policy.md).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="new-device-firmware-configuration-interface-profile-for-windows-10-and-later-devices----2266073----"></a>Nový profil rozhraní pro konfiguraci firmwaru zařízení pro zařízení s Windows 10 a novějším <!-- 2266073  -->

V systému Windows 10 a novějších můžete vytvořit profil konfigurace zařízení pro řízení nastavení a funkcí (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější** pro platformu). V této aktualizaci je k dispozici nový typ profilu rozhraní konfigurace firmwaru zařízení, který umožňuje Intune spravovat nastavení rozhraní UEFI (BIOS). Právě probíhá zavádění této funkce pro všechny zákazníky a očekává se, že bude dokončená na konci příštího týdne.

Další informace o této funkci najdete v tématu [použití profilů DFCI na zařízeních s Windows v Microsoft Intune](../configuration/device-firmware-configuration-interface-windows.md).

Platí pro:
- Windows 10 RS5 (1809) a novější v podporovaném firmwaru

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="toggle-to-only-show-enrollment-status-page-on-devices-provisioned-by-out-of-box-experience-oobe---3959566--"></a>Přepnout na zobrazení stránky stav registrace na zařízeních, která se zřídila při spuštění předpřipraveného prostředí (OOBE) <!--3959566-->
Nyní se můžete rozhodnout, že se stránka stavu registrace zobrazí jenom na zařízeních zřízených pomocí příkazu autopilot OOBE.

Pokud se chcete podívat na nový přepínač, vyberte > **Intune** **registrace zařízení** > **registrace systému Windows** > **Stránka stav registrace** > **vytvořit profil** > **Nastavení** ** > Zobrazit stránku se zařízeními zřízenými při prvním zapnutí prostředí (OOBE)** .


<!-- ########################## -->
## <a name="week-of-october-14-2019"></a>Týden od 14. října 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Správa aplikací 

#### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956-----"></a>Dostupná Google Play vytváření sestav aplikací pro pracovní profily Androidu <!-- 3041956   -->
Pro instalaci dostupné aplikace na firemním profilu Androidu Enterprise, vyhrazená a plně spravovaná zařízení můžete zobrazit stav instalace aplikace a také nainstalovanou verzi spravovaných aplikací Google Play. Další informace najdete v tématu [monitorování zásad ochrany aplikací](~/apps/app-protection-policies-monitor.md), [Správa zařízení s pracovním profilem Androidu pomocí Intune](~/enrollment/android-enterprise-overview.md) a [spravovaného Google Play typu aplikace](~/apps/apps-add-android-for-work.md#managed-google-play-app-types).

#### <a name="microsoft-edge-version-77-and-later-for-windows-10-and-macos-public-preview----3872025-4678761----"></a>Microsoft Edge verze 77 a novější pro Windows 10 a macOS (Public Preview) <!-- 3872025, 4678761  -->
Microsoft Edge verze 77 a novější bude k dispozici pro nasazení na počítačích se systémy Windows 10 a macOS. 

>[!NOTE]
>Zavedení této funkce bylo zpožděno až do konce tohoto měsíce.

Verze Public Preview nabízí **vývoj** a **beta** kanály pro Windows 10 a **beta** kanál pro MacOS. Nasazení je pouze anglické (EN), ale koncoví uživatelé mohou změnit jazyk zobrazení v prohlížeči v části **nastavení**  > **jazyky**. Microsoft Edge je aplikace Win32 nainstalovaná v kontextu systému a jako architektury (aplikace x86 v operačním systému x86 a x64 v operačním systému x64). Automatické aktualizace prohlížeče jsou navíc ve výchozím nastavení **zapnuté** a Microsoft Edge nejde odinstalovat. Další informace najdete v tématu [Přidání Microsoft Edge pro Windows 10 do Microsoft Intune](~/apps/apps-windows-edge.md) a [dokumentace k Microsoft Edge](https://go.microsoft.com/fwlink/?linkid=2103823).

#### <a name="update-to-app-protection-ui-and-ios-app-provisioning-ui----4102027-4102029-----"></a>Aktualizace uživatelského rozhraní ochrany aplikací a uživatelského rozhraní pro zřizování aplikací pro iOS <!-- 4102027, 4102029   -->
Aktualizovali jsme uživatelské rozhraní pro vytváření a úpravu zásad ochrany aplikací a zřizovacích profilů aplikací pro iOS v Intune. Změny uživatelského rozhraní zahrnují:
- Zjednodušené prostředí pomocí formátu na úrovni Průvodce zúženého v jednom okně. 
- Aktualizace toku vytváření, který má být zahrnut do přiřazení
- Souhrnná stránka všech věcí nastavená při zobrazení vlastností, před vytvořením nové zásady nebo úpravou vlastnosti. Také při úpravách vlastností se v souhrnu zobrazí pouze seznam položek z kategorie upravovaných vlastností.

Další informace najdete v tématech [Vytvoření a přiřazení zásad ochrany aplikací](~/apps/app-protection-policies.md) a [používání zřizovacích profilů aplikací pro iOS](~/apps/app-provisioning-profile-ios.md).

#### <a name="intune-guided-scenarios----4850318-4831296-3610611----"></a>Scénáře s asistencí pro Intune <!-- 4850318, 4831296, 3610611  -->
Intune teď poskytuje scénáře s asistencí, které vám pomůžou dokončit konkrétní úkol nebo sadu úkolů v rámci Intune. Scénář s asistencí je přizpůsobený sled kroků (pracovní postup), který se nachází na středovém prostředí pro případ celého použití. Běžné scénáře jsou definovány na základě role, kterou správce, uživatel nebo zařízení přehrává ve vaší organizaci. Tyto pracovní postupy obvykle vyžadují kolekci pečlivě Orchestrované profily, nastavení, aplikace a řízení zabezpečení, které poskytují nejlepší uživatelské prostředí a zabezpečení. Mezi nové scénáře s asistencí patří:
- [Nasazení Microsoft Edge pro mobilní zařízení](~/fundamentals/guided-scenarios-edge.md)
- [Zabezpečené systém Microsoft Office mobilní aplikace](~/fundamentals/guided-scenarios-office-mobile.md) 
- [Moderní plocha spravovaná cloudem](~/fundamentals/guided-scenarios-cloud-managed-pc.md)

Další informace najdete v článku [Přehled scénářů s asistencí pro Intune](guided-scenarios-overview.md).

#### <a name="additional-app-configuration-variable-available----4969237-----"></a>Je dostupná další konfigurační proměnná aplikace. <!-- 4969237   -->
Při vytváření zásad konfigurace aplikací můžete zahrnout proměnnou konfigurace `AAD Device ID` jako součást nastavení konfigurace. V Intune vyberte **klientské aplikace** > **zásady konfigurace aplikace** > **Přidat**. Zadejte podrobnosti zásady konfigurace a vyberte **nastavení konfigurace** . zobrazí se okno **nastavení konfigurace** . Další informace najdete v tématu [zásady konfigurace aplikací pro spravovaná zařízení s Androidem Enterprise – použijte návrháře konfigurace](~/apps/app-configuration-policies-use-android.md#use-the-configuration-designer).


#### <a name="create-groups-of-management-objects-called-policy-sets----3762880----"></a>Vytvoření skupin objektů pro správu nazývaných sady zásad <!-- 3762880  -->
Sady zásad umožňují vytvořit sadu odkazů na již existující entity správy, které je třeba identifikovat, cílit a monitorovat jako jednu koncepční jednotku. Sady zásad nenahrazují existující koncepty ani objekty. V Intune můžete dál přiřazovat jednotlivé objekty a v rámci sady zásad můžete odkazovat na jednotlivé objekty. Proto se v sadě zásad projeví všechny změny těchto jednotlivých objektů.  V Intune vyberete **sady zásad** > **vytvořit** k vytvoření nové sady zásad. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="ui-update-for-creating-and-editing-windows-10-update-rings-----4099089-----------"></a>Aktualizace uživatelského rozhraní pro vytváření a úpravy aktualizačních kanálů Windows 10  <!-- 4099089         -->
Aktualizovali jsme prostředí uživatelského rozhraní pro [vytváření a úpravy aktualizačních kanálů Windows 10](../protect/windows-update-for-business-configure.md#create-and-assign-update-rings) pro Intune. Změny uživatelského rozhraní zahrnují:  
- Formát na úrovni průvodce je zúžený do jediného okna konzoly, ve kterém se při konfiguraci aktualizačních kanálů zobrazí okno neustálému zvětšování, které jste předtím viděli.   
- Revidovaný pracovní postup obsahuje přiřazení před dokončením počáteční konfigurace prstence.
- Souhrnná stránka, kterou můžete použít ke kontrole všech konfigurací, které jste provedli, před uložením a nasazením nového aktualizačního kanálu. Při úpravách aktualizačního kanálu zobrazuje souhrn pouze seznam položek nastavených v kategorii vlastností, které jste upravili.

#### <a name="ui-update-for-creating-and-editing-ios-software-update-policy-----4099090---------"></a>Aktualizace uživatelského rozhraní pro vytváření a úpravy zásad aktualizace softwaru pro iOS  <!-- 4099090       --> 
Aktualizovali jsme prostředí uživatelského rozhraní pro [vytváření](../protect/software-updates-ios.md#configure-the-policy) a [úpravu](../protect/software-updates-ios.md#edit-a-policy) zásad aktualizace softwaru iOS pro Intune.  Změny uživatelského rozhraní zahrnují:  
- Formát na úrovni průvodce je zhuštěný do jediného okna konzoly, ve kterém se při konfiguraci zásad aktualizace nezobrazuje okno neustálému zvětšování.   
- Revidovaný pracovní postup zahrnuje přiřazení před dokončením počáteční konfigurace zásady.
- Souhrnná stránka, kterou můžete použít ke kontrole všech konfigurací, které jste provedli, před uložením a nasazením nové zásady. V rámci úpravy zásady se v souhrnu zobrazí jenom seznam položek nastavených v kategorii vlastností, které jste upravili.

#### <a name="engaged-restart-settings-are-removed-from-windows-update-rings------4464404---wnready-----"></a>Nastavení připraveného restartování se z web Windows Updatech okruhů odeberou.  <!--  4464404   WNReady   -->
Jak už bylo oznámeno, aktualizační kanály Windows 10 v Intune teď [podporují nastavení pro konečné termíny](../protect/windows-update-settings.md) a už nepodporují *restart*. Nastavení pro probíhající *restart* již není k dispozici při konfiguraci nebo správě aktualizačních kroužků v Intune.  

Tato změna se zarovnává s posledními [změnami údržby Windows](https://docs.microsoft.com//windows/whats-new/whats-new-windows-10-version-1903#servicing) a na zařízeních s Windows 10 1903 nebo novějším, přičemž *termíny* nahrazují konfigurace pro *následné restartování*.

#### <a name="prevent-installation-of-apps-from-unknown-sources-on-android-enterprise-work-profile-devices----4760025-----"></a>Zabránit instalaci aplikací z neznámých zdrojů na zařízeních s pracovními profily Android Enterprise <!-- 4760025   -->
Na zařízeních s pracovním profilem Android Enterprise uživatelé nemůžou instalovat aplikace aplikací z neznámých zdrojů. V této aktualizaci se nachází nové nastavení – **Zakázat instalaci aplikací z neznámých zdrojů v osobním profilu**. Ve výchozím nastavení toto nastavení brání uživatelům v nasazování aplikací z neznámých zdrojů do osobního profilu na zařízení.

Pokud chcete zobrazit nastavení, které můžete nakonfigurovat, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-android-for-work.md).

Platí pro:
- Pracovní profil Android Enterprise

#### <a name="create-a-global-http-proxy-on-android-enterprise-device-owner-devices----4816339-----"></a>Vytvoření globálního proxy serveru HTTP na zařízeních s vlastníkem zařízení s Androidem Enterprise <!-- 4816339   -->
Na zařízeních s Androidem Enterprise můžete nakonfigurovat globální proxy server HTTP tak, aby splňoval standardy procházení webu vaší organizace (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** for **> omezení zařízení** > Platform pro typ profilu > **konektivita**zařízení. Po nakonfigurování budou všechny přenosy HTTP používat tento proxy server.

Pokud chcete tuto funkci nakonfigurovat a zobrazit všechna nakonfigurovaná nastavení, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-android-for-work.md).

Platí pro:
- Vlastník zařízení se systémem Android Enterprise

#### <a name="connect-automatically-setting-is-removed-in-wi-fi-profiles-on-android-device-administrator-and-android-enterprise----5021055-----"></a>Nastavení připojit automaticky se odebere v profilech sítě Wi-Fi na správce zařízení s Androidem a na Androidu Enterprise. <!-- 5021055   -->
Na zařízeních s Androidem pro správce zařízení a Androidem Enterprise můžete vytvořit profil Wi-Fi, který bude konfigurovat různá nastavení (**Konfigurace zařízení**  > **profily**  > **vytvořit profil**  > **zařízení s Androidem. Správce** nebo **Android Enterprise** for Platform > **Wi-Fi** pro typ profilu). V této aktualizaci se nastavení **Připojit automaticky** odebere, protože ho [nepodporuje Android](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29). 

Pokud použijete toto nastavení v profilu Wi-Fi, možná jste si všimli, že se **připojení automaticky** nepracuje. Nemusíte nic dělat, ale mějte na paměti, že toto nastavení se odebere v uživatelském rozhraní Intune.

Pokud chcete zobrazit aktuální nastavení, přejděte na nastavení [Androidu Wi-Fi](../configuration/wi-fi-settings-android.md) nebo [Nastavení Android Enterprise Wi-Fi](../configuration/wi-fi-settings-android-enterprise.md).

Platí pro:
- Správce zařízení s Androidem 
- Android Enterprise


#### <a name="new-device-configuration-settings-for-supervised-ios-and-ipados-devices----5199328-----"></a>Nové nastavení konfigurace zařízení pro zařízení s iOS a iPadOS pod dohledem <!-- 5199328   -->
Na zařízeních s iOS a iPadOS můžete vytvořit profil, který omezí funkce a nastavení na zařízeních (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS/iPadOS** pro > platformy.  **omezení** pro typ profilu). V této aktualizaci můžete řídit nová nastavení: 
- Přístup k síťové jednotce v aplikaci soubory  
- Přístup k jednotce USB v aplikaci soubory 
- Wi-Fi vždycky zapnuté 

Tato nastavení zobrazíte tak, že přejdete na [nastavení zařízení s iOS a povolíte nebo zakážete funkce využívající Intune](../configuration/device-restrictions-ios.md).

Platí pro:
- iOS 13,0 a novější
- iPadOS 13,0 a novější

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="specify-which-android-device-operating-system-versions-enroll-with-work-profile-or-device-administrator-enrollment----4350697-----"></a>Zadejte, které verze operačního systému zařízení s Androidem se mají zaregistrovat pomocí pracovního profilu nebo registrace Správce zařízení. <!-- 4350697   -->
Pomocí omezení typu zařízení v Intune můžete použít verzi operačního systému zařízení k určení toho, která zařízení uživatelů budou používat registraci pracovního profilu Android Enterprise nebo Správce zařízení s Androidem.  Další informace najdete v tématu [Nastavení omezení registrace](../enrollment/enrollment-restrictions-set.md).

#### <a name="windows-autopilot-deployment-reports----3856172---"></a>Sestavy nasazení Windows autopilot <!-- 3856172 -->
Nová sestava podrobně popisuje každé zařízení nasazené prostřednictvím Windows autopilotu. Další informace najdete v tématu [Sestava nasazení autopilotu](../enrollment/enrollment-autopilot.md#autopilot-deployments-report). Právě probíhá zavádění této funkce pro všechny zákazníky a očekává se, že bude dokončená na konci příštího týdne.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Správa zařízení

#### <a name="new-restrictions-for-renaming-windows-devices----3478938----"></a>Nová omezení pro přejmenování zařízení s Windows <!-- 3478938  -->
Při přejmenování zařízení s Windows musíte dodržovat nová pravidla:
- maximálně 15 znaků (musí být menší než nebo rovno 63 bajtů, včetně koncové hodnoty NULL)
- Není null nebo prázdný řetězec
- Povolené znakové sady ASCII: písmena (a-z, A – Z), číslice (0-9) a spojovníky
- Povolené kódování Unicode: znaky > = 0x80, musí být platný UTF8, musí být možné mapovat na IDN (to znamená, že RtlIdnToNameprepUnicode je úspěšných, viz RFC 3492)
- Názvy nesmí obsahovat jenom číslice.
- Žádné mezery v názvu
- Nepovolené znaky: {|} ~ [\] ^ ':; < = >? & @! " # $ % ` ( ) + / , . _ *)

 Další informace najdete v tématu [přejmenování zařízení v Intune](../remote-actions/device-rename.md).

### <a name="new-android-report-on-devices-overview-page----4924364---"></a>Stránka Přehled nové sestavy pro Android na zařízeních <!-- 4924364 -->
Nová sestava na stránce Přehled zařízení zobrazuje počet zaregistrovaných zařízení s Androidem v jednotlivých řešeních pro správu zařízení. Tento graf zobrazuje počet zaregistrovaných zařízení v pracovním profilu, plně spravovaných, vyhrazených a správcích zařízení. Pokud chcete zobrazit sestavu, vyberte  > **zařízení** **Intune**  > **Přehled**.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Zabezpečení zařízení 

#### <a name="pkcs-certificates-for-macos-----1333650---------"></a>Certifikáty PKCS pro macOS  <!-- 1333650       -->
[Certifikáty PKCS teď můžete používat s MacOS](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile). Můžete vybrat certifikát PKCS jako typ profilu pro macOS a nasadit certifikáty uživatelů a zařízení, které mají [přizpůsobená pole Předmět a alternativní název subjektu](../protect/certficates-pfx-configure.md#subject-name-format-for-macos).  

Certifikát PKCS pro macOS podporuje také nové nastavení a _povoluje přístup všem aplikacím_. Pomocí tohoto nastavení můžete všem přidruženým aplikacím povolit přístup k privátnímu klíči certifikátu.  Další informace o tomto nastavení najdete v dokumentaci Apple na adrese https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf.

####   <a name="derived-credentials-to-provision-ios-mobile-devices-with-certificates----------1736036-1736037-1772050-2777333-----------"></a>Odvozená pověření pro zřizování mobilních zařízení s iOS pomocí certifikátů      <!--  1736036, 1736037, 1772050, 2777333         -->  
Intune podporuje použití [odvozených přihlašovacích údajů](../protect/derived-credentials.md) jako metody ověřování a pro podepisování a šifrování S/MIME pro zařízení S iOS. Odvozené přihlašovací údaje jsou implementací standardu *NIST (National Institute of Standards and Technology) 800-157* pro nasazení certifikátů do zařízení.  

Odvozené přihlašovací údaje spoléhají na použití osobního ověřování identity (PIV) nebo karty Common Access Card (CAC), jako je například čipová karta. Pokud chcete získat odvozené přihlašovací údaje pro své mobilní zařízení, uživatelé začnou v aplikaci Portál společnosti a dodržujte pracovní postup registrace, který je jedinečný pro poskytovatele, kterého používáte.  Společný pro všechny poskytovatele je požadavek na použití čipové karty v počítači k ověření pro odvozeného zprostředkovatele přihlašovacích údajů. Poskytovatel pak vydá certifikát zařízení, které je odvozeno od čipové karty uživatele.  

Intune podporuje následující odvozené zprostředkovatele přihlašovacích údajů:   
- DISA purebred
- Entrust Datacard
- Intercede

Odvozené přihlašovací údaje použijete jako metodu ověřování pro profily konfigurace zařízení VPN, Wi-Fi a e-mailu. Můžete je také použít k ověřování aplikací a k podepisování a šifrování S/MIME.  

Další informace o standardu najdete v tématu [odvozené piv přihlašovací údaje](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) na adrese www.nccoe.nist.gov.

#### <a name="use-graph-api-to-specify-a-on-premises-user-principal-name-as-a-variable-for-scep-certificates--------5437939----------"></a>Pomocí Graph API zadat hlavní název uživatele místního uživatele jako proměnnou pro certifikáty SCEP.    <!--  5437939        -->  
Když použijete [Graph API Intune](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0), můžete jako proměnnou alternativní název subjektu (San) pro certifikáty SCEP zadat onPremisesUserPrincipalName.



<!-- ########################## -->

## <a name="week-of-september-23-2019"></a>Týden od 23. září 2019

#### <a name="ios-user-enrollment-in-preview----4817900---"></a>Registrace uživatele pro iOS ve verzi Preview <!-- 4817900 -->
Verze iOS 13,1 od společnosti Apple zahrnuje registraci uživatelů, novou formu zjednodušené správy pro zařízení s iOS. Dá se použít místo registrace zařízení nebo automatického zápisu zařízení (dříve Program registrace zařízení) pro osobní zařízení vlastněná společností. Intune Preview podporuje tuto sadu funkcí tím, že vám umožní:

- Registrace cílového uživatele pro skupiny uživatelů.
- Poskytněte koncovým uživatelům možnost výběru mezi jednodušším zápisem uživatele nebo silnějším zápisem zařízení při registraci svých zařízení.

Od verze 9/24/2019 s vydáním iOS 13,1 jsme v procesu zavedli tyto aktualizace všem zákazníkům a očekáváme, že budou dokončeny na konci příštího týdne.
Platí pro:

iOS 13,1 a novější

#### <a name="intune-support-for-ipados-and-ios-131-devices---5439574--"></a>Podpora Intune pro zařízení iPadOS a iOS 13,1 <!--5439574-->
Intune teď podporuje správu zařízení iPadOS i iOS 13,1. Další informace najdete v [tomto příspěvku blogu](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-1-and-iPadOS/ba-p/873094).

<!-- ########################## -->

## <a name="week-of-september-16-2019"></a>Týden od 16. září 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Správa aplikací 

#### <a name="managed-google-play-private-lob-apps----1464182----"></a>Spravované Google Play soukromé obchodní aplikace <!-- 1464182  -->
Intune teď umožňuje správcům IT publikovat soukromé obchodní aplikace pro Android do spravovaných Google Play prostřednictvím IFRAME vloženého v konzole Intune.  Dříve museli správci IT publikovat obchodní aplikace přímo do konzoly pro publikování Google, která vyžadovala několik kroků a byla časově náročná. Tato nová funkce umožňuje snadno publikovat obchodní aplikace s minimální sadou kroků, aniž byste museli opustit konzolu Intune.  Správci už nebudou muset ručně registrovat jako vývojáře s Google a nebude už muset platit poplatek za registraci Google $25.  Tato funkce může využít některý ze scénářů správy Android Enterprise, které používají spravované Google Play (pracovní profil, vyhrazená, plně spravovaná a neregistrovaná zařízení). V Intune vyberte **klientské aplikace** > **aplikace** > **Přidat**. Pak v seznamu **Typ aplikace** vyberte **spravovaná Google Play** . Další informace o spravovaných aplikacích Google Play najdete v tématu [Přidání spravovaných Google Play aplikací do zařízení s Androidem Enterprise v Intune](../apps/apps-add-android-for-work.md).

#### <a name="windows-company-portal-experience----1473353-3598357---"></a>Prostředí Windows Portál společnosti <!-- 1473353, 3598357 -->
Probíhá aktualizace Windows Portál společnosti. Na stránce aplikace v rámci Windows Portál společnosti budete moct používat víc filtrů. Stránka s podrobnostmi o zařízení se taky aktualizuje s vylepšeným uživatelským prostředím. Právě probíhá zavádění těchto aktualizací pro všechny zákazníky a očekává se dokončení na konci příštího týdne.

#### <a name="macos-support-for-web-apps----3174427---"></a>Podpora macOS pro webové aplikace <!-- 3174427 -->
Webové aplikace, které umožňují přidat zástupce na adresu URL na webu, lze nainstalovat do Docku pomocí Portál společnosti macOS. Koncoví uživatelé mohou získat přístup k akci **instalace** ze stránky s podrobnostmi o aplikaci pro webovou aplikaci ve MacOS portál společnosti. Další informace o typu aplikace **webový odkaz** najdete v tématu [přidání aplikací do Microsoft Intune](../apps/apps-add.md) a [Přidání webových aplikací do Microsoft Intune](../apps/web-app.md).

#### <a name="macos-support-for-vpp-apps----3173501----"></a>Podpora macOS pro aplikace VPP <!-- 3173501  -->
aplikace macOS, zakoupené pomocí Apple Business Manageru, se v konzole zobrazí, když se tokeny programu Apple VPP synchronizují v Intune. Pomocí konzoly služby Intune můžete přiřadit, odvolat a znovu přiřadit licence na zařízení a uživatele pro skupiny. Microsoft Intune pomáhá spravovat aplikace VPP zakoupené pro použití ve vaší společnosti:

- Vykazuje informace o licencích z App Storu.
- Sleduje počet použitých licencí.
- Pomůže vám zabránit instalaci více kopií aplikace, než na kolik máte licence.

Další informace o Intune a VPP najdete v tématu [Správa hromadně zakoupených aplikací a knih pomocí Microsoft Intune](../apps/vpp-apps.md).

#### <a name="managed-google-play-iframe-support----2871756----"></a>Podpora spravované Google Play IFRAME <!-- 2871756  -->
Intune teď poskytuje podporu pro přidávání a správu webových odkazů přímo v konzole Intune prostřednictvím spravovaného Google Play IFRAME.  To umožňuje správcům IT odeslat obrázek adresy URL a ikony a potom tyto odkazy nasadit na zařízení stejně jako běžné aplikace pro Android. Tato funkce může využít některý ze scénářů správy Android Enterprise, které používají spravované Google Play (pracovní profil, vyhrazená, plně spravovaná a neregistrovaná zařízení). V Intune vyberte **klientské aplikace** > **aplikace** > **Přidat**. Pak v seznamu **Typ aplikace** vyberte **spravovaná Google Play** . Další informace o spravovaných aplikacích Google Play najdete v tématu [Přidání spravovaných Google Play aplikací do zařízení s Androidem Enterprise v Intune](../apps/apps-add-android-for-work.md).

#### <a name="silently-install-android-lob-apps-on-zebra-devices----4252734----"></a>Tichá instalace obchodních aplikací pro Android na zařízeních Zebra <!-- 4252734  -->
Při instalaci obchodních aplikací (LOB) pro Android do [zařízení Zebra](../configuration/android-zebra-mx-overview.md)se místo výzvy ke stažení a instalaci obchodní aplikace budete moct aplikaci nainstalovat tiše. V Intune vyberte **klientské aplikace** > **aplikace** > **Přidat**. V podokně **Přidat aplikaci** vyberte **Obchodní aplikace**. Další informace najdete v tématu [Přidání obchodní aplikace pro Android do Microsoft Intune](../apps/lob-apps-android.md).

V současné době se po stažení aplikace LOB na zařízení uživatele zobrazí oznámení o **úspěšném stažení** . Oznámení se může zrušit jenom klepnutím na **Vymazat vše** v odstínu oznámení. Tento problém s oznámením bude opraven v nadcházející verzi a instalace bude zcela tichá bez vizuálních indikátorů.

#### <a name="read-and-write-graph-api-operations-for-intune-apps----5031704----"></a>Čtení a zápis Graph APIch operací pro aplikace Intune <!-- 5031704  -->
Aplikace můžou volat Graph API Intune s použitím identity čtení i zápisu pomocí identity aplikace bez přihlašovacích údajů uživatele. Další informace o přístupu k rozhraní Microsoft Graph API pro Intune najdete [v tématu práce s Intune v Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="protected-data-sharing-and-encryption-for-intune-app-sdk-for-ios----3586942----"></a>Chráněné sdílení a šifrování dat pro sadu Intune App SDK pro iOS <!-- 3586942  -->
Intune App SDK pro iOS bude používat 256 šifrovacích klíčů, pokud je šifrování povolené zásadami ochrany aplikací. Aby bylo možné chráněné sdílení dat, bude nutné, aby všechny aplikace měly sadu SDK verze 8.1.1.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438-----"></a>Podpora pro profily IKEv2 VPN pro iOS <!-- 1943438   -->
V této aktualizaci můžete vytvořit profily sítě VPN pro nativního klienta VPN iOS pomocí protokolu IKEv2. IKEv2 je nový typ připojení v **konfiguraci zařízení** > **profily** > **vytvořit profil** > **iOS** pro typ profilu > **Typ připojení**> **VPN** .

Tyto profily sítě VPN konfigurují nativního klienta VPN, takže nebudou nainstalovány ani vloženy žádné klientské aplikace VPN do spravovaných zařízení. Tato funkce vyžaduje, aby byla zařízení zaregistrovaná v Intune (registrace MDM).

Aktuální nastavení sítě VPN, která můžete nakonfigurovat, najdete v tématu [Konfigurace nastavení sítě VPN na zařízeních s iOS](../configuration/vpn-settings-ios.md).

Platí pro:
- iOS

#### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type----4886161-----"></a>Funkce zařízení, omezení zařízení a profily rozšíření pro nastavení iOS a macOS se zobrazují podle typu registrace. <!-- 4886161   -->

V Intune vytvoříte profily pro zařízení s iOS a macOS (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** nebo **MacOS** pro **funkce zařízení**>, **zařízení omezení**nebo **rozšíření** pro typ profilu). 

V této aktualizaci jsou dostupná nastavení na portálu Intune zařazená do kategorie podle typu registrace, na který se vztahují:

- iOS
  - Zápis uživatele
  - Registrace zařízení
  - Automatický zápis zařízení (pod dohledem)
  - Všechny typy registrace

- macOS
  - Schválené uživatelem
  - Registrace zařízení
  - Automatický zápis zařízení
  - Všechny typy registrace

Platí pro:
- iOS

#### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode----4892835-----"></a>Nové nastavení ovládání hlasu pro zařízení s iOS běžící v celoobrazovkovém režimu <!-- 4892835   -->
V Intune můžete vytvářet zásady, které budou spouštět zařízení se systémem iOS pod dohledem jako veřejný terminál nebo vyhrazené zařízení (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro > **omezení zařízení s platformou.** pro typ profilu > veřejného **terminálu**). 

V této aktualizaci můžete řídit nová nastavení:
- **Ovládání hlasu**: povolí hlasové ovládání zařízení v celoobrazovkovém režimu.
- **Změna ovládání hlasu**: umožňuje uživatelům změnit nastavení hlasového ovládacího prvku v zařízení v celoobrazovkovém režimu.

Aktuální nastavení zobrazíte tak, že přejdete na [Nastavení veřejného terminálu iOS](../configuration/device-restrictions-ios.md#kiosk).

Platí pro:
- iOS 13,0 a novější

#### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices----4893175-----"></a>Použití jednotného přihlašování pro aplikace a weby na zařízeních s iOS a macOS <!-- 4893175   -->
V této aktualizaci je k dispozici několik nových nastavení jednotného přihlašování pro zařízení s iOS a macOS (**Konfigurace zařízení**  > **profily**  > **vytváření profilů**  > **iOS** nebo **MacOS** pro funkce platformy >ch **zařízení.** pro typ profilu).

Pomocí těchto nastavení můžete nakonfigurovat jednotné přihlašování, zejména pro aplikace a weby, které používají ověřování pomocí protokolu Kerberos. Můžete si vybrat mezi obecnými přihlašovacími údaji jednotného přihlašování aplikace a integrovaným rozšířením Kerberos společnosti Apple.

Pokud chcete zobrazit aktuální funkce zařízení, které můžete konfigurovat, přejděte na [funkce zařízení s iOS](../configuration/ios-device-features-settings.md) a [MacOS funkce zařízení](../configuration/macos-device-features-settings.md).

Platí pro:
- iOS 13,0 a novější
- macOS 10,15 a novější

#### <a name="associate-domains-to-apps-on-macos-1015-devices----4898079-----"></a>Přidružení domén k aplikacím na macOS 10.15 a zařízeních <!-- 4898079   -->
Na zařízeních macOS můžete nakonfigurovat různé funkce a pomocí zásad (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **MacOS** pro zařízení > platformy.  **funkce** pro typ profilu). V této aktualizaci můžete k aplikacím přidružit domény. Tato funkce pomáhá sdílet přihlašovací údaje s weby souvisejícími s vaší aplikací a lze ji použít s rozšířením jednotného přihlašování společnosti Apple, univerzálními odkazy a automatického vyplňování hesel. 

Pokud chcete zobrazit aktuální funkce, které můžete nakonfigurovat, přejděte na [Nastavení funkcí zařízení MacOS v Intune](../configuration/macos-device-features-settings.md).

Platí pro:
- macOS 10,15 a novější

#### <a name="use-itunes-and-apps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices----4928474-----"></a>Při zobrazování nebo skrývání aplikací na zařízeních s iOS pod dohledem použijte v adrese URL obchodu iTunes aplikace iTunes a aplikace. <!-- 4928474   --> 
V Intune můžete vytvářet zásady pro zobrazování nebo skrývání aplikací na zařízeních s iOS pod dohledem (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro > **omezení zařízení** s platformou pro Typ profilu > **Zobrazit nebo skrýt aplikace**). 

Můžete zadat adresu URL obchodu s aplikacemi iTunes, například `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`. V této aktualizaci lze v adrese URL použít `apps` a `itunes`, například:
- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

Další informace o těchto nastaveních najdete v tématu [zobrazení nebo skrytí aplikací](../configuration/device-restrictions-ios.md#show-or-hide-apps).

Platí pro:
- iOS

#### <a name="windows-10-compliance-policy-password-type-values-are-clearer-and-match-csp---5138985---"></a>Hodnoty typu hesla zásad dodržování předpisů ve Windows 10 jsou jasné a neshodné s poskytovatelem CSP.<!-- 5138985 -->
Na zařízeních s Windows 10 můžete vytvořit zásady dodržování předpisů, které vyžadují konkrétní funkce pro heslo (**zásady**  > **dodržování předpisů zařízením**  > **vytvořit zásadu**  > **Windows 10 a novější** pro platformu > System).  **Zabezpečení**). V této aktualizaci:
- Hodnoty **typu hesla** jsou jasné a aktualizované tak, aby ODPOVÍDALy [zprostředkovateli DeviceLock/AlphanumericDevicePasswordRequired](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired).
- Nastavení **vypršení platnosti hesla (dny)** se aktualizuje, aby se povolily hodnoty z 1-730 dnů. 

Další informace o nastavení dodržování předpisů ve Windows 10 najdete v tématu [nastavení Windows 10 a novějších k označení zařízení jako odpovídajících nebo nevyhovujících](../protect/compliance-policy-create-windows.md)předpisům. 

Platí pro:
- Windows 10 a novější

 #### <a name="updated-ui-for-configuring-microsoft-exchange-on-premises-access-------4092920---"></a>Aktualizované uživatelské rozhraní pro konfiguraci přístupu k místnímu systému Microsoft Exchange    <!-- 4092920 -->  
Aktualizovali jsme konzolu, kde jste [nakonfigurovali přístup k místnímu přístupu Microsoft Exchange](../protect/conditional-access-exchange-create.md). Všechny konfigurace pro přístup k místnímu Exchangi jsou teď dostupné ve stejném podokně konzoly, kde můžete *Povolit řízení přístupu k místnímu Exchangi*.  

#### <a name="allow-or-restrict-adding-app-widgets-to-the-home-screen-on-android-enterprise-work-profile-devices----1109650----"></a>Povolení nebo omezení přidání widgetů aplikací na domovskou obrazovku na zařízeních s pracovními profily Android Enterprise <!-- 1109650  --> 
Na zařízeních s Androidem Enterprise můžete nakonfigurovat funkce v pracovním profilu (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** for Platform > **Work Profile > Omezení zařízení** pro typ profilu). V této aktualizaci můžete uživatelům dovolit přidávat widgety, které jsou zpřístupněny aplikacemi pracovní profil na domovské obrazovce zařízení.

Pokud chcete zobrazit nastavení, která můžete nakonfigurovat, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-android-for-work.md).

Platí pro:
- Pracovní profil Android Enterprise

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="new-tenants-will-default-away-from-android-device-administrator-management----4869790-----"></a>Ve výchozím nastavení budou noví klienti pryč ze správy zařízení s Androidem. <!-- 4869790   -->
Možnosti Správce zařízení s Androidem jsou nahrazené Androidem Enterprise. Proto doporučujeme místo toho použít Android Enterprise pro nové registrace. V budoucí aktualizaci budou muset noví klienti v rámci registrace Androidu v případě použití správy správců zařízení provést následující nezbytné kroky: Přejít na **Intune**  > **registrace zařízení**  > **Androidu**  >  **Osobní zařízení a zařízení vlastněná společností pomocí oprávnění pro správu zařízení**  > **ke správě zařízení použít Správce zařízení**.

Stávající klienti nebudou mít ve svých prostředích žádné změny. 

Další informace o Správci zařízení s Androidem v Intune najdete v tématu [registrace Správce zařízení s Androidem](https://docs.microsoft.com/intune/android-enroll-device-administrator).

#### <a name="list-of-dep-devices-associated-with-a-profile----5012045-idmiss---"></a>Seznam zařízení DEP přidružených k profilu <!-- 5012045 idmiss -->
Teď můžete zobrazit stránkovaný seznam zařízení Apple automatizované Program registrace zařízení (DEP), která jsou přidružená k profilu. Seznam můžete vyhledat na libovolné stránce v seznamu. Pokud chcete zobrazit seznam, přejděte na **Intune** > **registrace zařízení** >  registrace**Apple** > **tokeny programu registrace** > vyberte **profily** >ch profilů > vyberte profil > **přiřazená zařízení** ( v části **monitor**). 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Správa zařízení

#### <a name="more-android-fully-managed-support----3464667-4631425-4631440-5227935-4062195-----"></a>Další plně spravovaná podpora Androidu <!-- 3464667, 4631425, 4631440, 5227935, 4062195   -->
Přidali jsme následující podporu pro plně spravovaná zařízení s Androidem:

- Certifikáty SCEP pro plně spravovanou Android jsou k dispozici pro ověřování certifikátů na zařízeních spravovaných jako vlastník zařízení. Certifikáty SCEP jsou už na zařízeních pracovního profilu podporované.  Pomocí certifikátů SCEP pro vlastníka zařízení budete moct: <!-- 5227935 -->
    - Vytvoření profilu SCEP v části DO v Androidu Enterprise
    - propojení certifikátů SCEP s profilem Wi-Fi pro ověřování
    - propojení certifikátů SCEP a provádění profilů sítě VPN pro ověřování
    - propojení certifikátů SCEP pro ověřování e-mailových profilů (přes AppConfig)
- Systémové aplikace jsou podporované na zařízeních s Androidem Enterprise. V Intune přidejte aplikaci pro Android Enterprise System tak, že vyberete **klientské aplikace** > **aplikace** > **Přidat**. V seznamu **Typ aplikace** vyberte aplikace pro **Android Enterprise System**. Další informace najdete v tématu [Přidání aplikací pro Android Enterprise System do Microsoft Intune](../apps/apps-ae-system.md). <!-- 4062195 -->
- V části **dodržování předpisů zařízením**  > **vlastníka zařízení**pro**Android Enterprise**  >  můžete vytvořit zásady dodržování předpisů, které nastaví úroveň ověření Google SafetyNet.   <!-- 4631425 -->
- Na zařízeních s plnou správou Androidu Enterprise se podporují poskytovatelé ochrany před mobilními hrozbami. V **dodržování předpisů zařízením**  > **vlastníka zařízení**s**Androidem Enterprise**  >  můžete vybrat přijatelnou úroveň hrozeb. <!-- 4631440 --> [Nastavení Androidu Enterprise k označení zařízení jako kompatibilních nebo nekompatibilních s použitím Intune](../protect/compliance-policy-create-android-for-work.md#device-owner) seznam aktuálních nastavení.
- Na zařízeních s plnou správou Androidu Enterprise se teď dá nakonfigurovat aplikace spouštěče Microsoftu prostřednictvím zásad konfigurace aplikací, které umožňují standardizované prostředí koncového uživatele na plně spravovaném zařízení. K přizpůsobení zařízení s Androidem se dá použít aplikace Microsoft spouštěče. Pomocí aplikace spolu s účet Microsoft nebo pracovním nebo školním účtem máte přístup k vašemu kalendáři, dokumentům a posledním aktivitám v přizpůsobeném kanálu. <!-- 5334044 -->

V této aktualizaci jsme spokojeni s oznámením, že podpora Intune pro plně spravovanou platformu Android Enterprise je teď všeobecně dostupná.

Platí pro:

- Zařízení se systémem Android Enterprise s plnou správou

#### <a name="send-custom-notifications-to-a-single-device-----4928910---"></a>Odesílání vlastních oznámení na jedno zařízení  <!-- 4928910 -->
Teď můžete vybrat jedno zařízení a pak použít akci vzdáleného zařízení k [odeslání vlastního oznámení jenom na toto zařízení](../remote-actions/custom-notifications.md#send-a-custom-notification-to-a-single-device).

#### <a name="wipe-and-passcode-reset-actions-arent-available-for-ios-devices-that-are-enrolled-by-using-user-enrollment----4950491---"></a>Akce vymazání a resetování hesla nejsou k dispozici pro zařízení s iOS, která jsou zaregistrovaná pomocí zápisu uživatelů. <!-- 4950491 -->
Zápis uživatele je nový typ registrace zařízení Apple. Při registraci zařízení pomocí registrace uživatele nebudou pro taková zařízení k dispozici vzdálené akce resetování a resetování hesla.

#### <a name="intune-support-for-ios-13-and-macos-catalina-devices----4665317---"></a>Podpora Intune pro zařízení s iOS 13 a macOS Catalina <!-- 4665317 -->
Intune teď podporuje správu zařízení se systémem iOS 13 i macOS Catalina. Další informace najdete v [příspěvku na blogu Microsoft Intune podpoře pro iOS 13 a iPadOS](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-and-iPadOS/ba-p/861998).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Zabezpečení zařízení

#### <a name="bitlocker-support-for-client-driven-recovery-password-rotation-------3444125---"></a>Podpora BitLockeru pro otočení hesla pro obnovení na základě klienta   <!--  3444125 -->
Použijte nastavení Endpoint Protection Intune ke konfiguraci [rotace hesla pro obnovení](../protect/endpoint-protection-windows-10.md#windows-encryption) na zařízeních s Windows verze 1909 nebo novějším na základě klienta.

Toto nastavení inicializuje obnovení hesla na základě klienta po obnovení jednotky operačního systému (buď pomocí programu Bootmgr nebo WinRE) a odemknutí hesla pro obnovení na pevné datové jednotce. Toto nastavení aktualizuje specifické heslo pro obnovení, které bylo použito, a jiná nepoužívaná hesla na svazku zůstanou beze změny. Další informace najdete v dokumentaci k nástroji BitLocker CSP pro [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp).

#### <a name="tamper-protection-for-windows-defender-antivirus-----4705448----------"></a>Ochrana proti úmyslné ochraně pro antivirovou ochranu v programu Windows Defender  <!-- 4705448        -->
Použijte Intune ke správě *ochrany před zneužitím antivirové ochrany* v programu Windows Defender. Pokud použijete konfigurační profily zařízení pro Windows 10 Endpoint Protection, najdete [nastavení pro ochranu proti falšování](../protect/endpoint-protection-windows-10.md#windows-defender-security-center) ve skupině Security Center programu Microsoft Defender. Ochranu proti neoprávněným nastavením ochrany proti chybám můžete *nastavit tak, aby se* zapnulo omezení ochrany před odesláním, nastavení *zakázáno* pro jejich vypnutí, nebo nastavit, aby se zařízení*nenakonfigurovalo* jako aktuální konfigurace.  

Další informace o ochraně před zneužitím najdete v dokumentaci k Windows v tématu [zabránění změnám nastavení zabezpečení pomocí ochrany před neoprávněnými](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) změnami. 

#### <a name="advanced-settings-for-windows-defender-firewall-are-now-generally-available-----5317392---------"></a>Rozšířená nastavení pro firewall v programu Windows Defender jsou teď všeobecně dostupná. <!--  5317392       -->  
[Vlastní pravidla brány firewall v programu Windows Defender pro službu Endpoint Protection](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices), která konfigurujete jako součást profilu konfigurace zařízení, jsou ve verzi Public Preview a jsou všeobecně dostupná (GA).  Tato pravidla můžete použít k určení příchozího a odchozího chování aplikací, síťových adres a portů. Tato pravidla byla vydaná v červenci jako verze Public Preview. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="scope-tags-now-support-terms-of-use-policies----2358863-idmiss---"></a>Značky oboru teď podporují zásady používání podmínek použití <!-- 2358863 idmiss -->
Nyní můžete přiřadit [značky oboru](scope-tags.md) k zásadám použití. Provedete to tak, že přejdete na **Intune**  > **registrace zařízení**  > **podmínky** > vyberte položku v seznamu > **vlastnosti**  > **značky oboru** > vyberte značku oboru.

## <a name="week-of-september-9-2019"></a>Týden od 9. září 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="updates-to-microsoft-intune-app----4997846---"></a>Aktualizace aplikace Microsoft Intune <!-- 4997846 -->
Microsoft Intune aplikace pro Android se aktualizovala s následujícími vylepšeními:
- Aktualizace a vylepšení rozložení tak, aby obsahovalo Dolní navigační údaje nejdůležitějších akcí.
- Přidala se další stránka, která zobrazuje profil uživatele.
- Do aplikace pro uživatele se přidalo zobrazování oznámení s možnou akcí, například nutnost aktualizovat nastavení zařízení.
- Přidali jsme zobrazení vlastních nabízených oznámení a zarovnejte aplikaci s podporou, která byla nedávno přidaná v aplikaci Portál společnosti pro iOS a Android. Další informace najdete v tématu [odesílání vlastních oznámení v Intune](../remote-actions/custom-notifications.md).

#### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993---"></a>Pro zařízení s iOS si Přizpůsobte obrazovku ochrana osobních údajů procesu registrace Portál společnosti <!-- 4394993 -->
Pomocí Markdownu můžete přizpůsobit obrazovku osobních údajů Portál společnosti, kterou koncoví uživatelé uvidí během registrace iOS. Konkrétně budete moct přizpůsobit seznam věcí, které vaše organizace nemůže zobrazit nebo dělat na zařízení. Další informace najdete v tématu [Konfigurace aplikace Portál společnosti Intune](../apps/company-portal-app.md#privacy-statement-customization).


## <a name="week-of-september-2-2019"></a>Týden od 2. září 2019

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="intune-user-interface-update--tenant-status-dashboard-----5273210----"></a>Aktualizace uživatelského rozhraní Intune – řídicí panel stavu tenanta  <!-- 5273210  -->
Uživatelské rozhraní pro řídicí panel stavu tenanta se aktualizovalo tak, aby bylo zarovnané na styly uživatelského rozhraní Azure. Další informace najdete v tématu [stav tenanta](../tenant-status.md).


## <a name="week-of-august-26-2019"></a>Týden od 26. srpna 2019

### <a name="configure-microsoft-edge-settings-using-administrative-templates-for-windows-10-and-newer----5228061---"></a>Konfigurace nastavení Microsoft Edge pomocí šablon pro správu pro Windows 10 a novější <!-- 5228061 -->

V zařízeních s Windows 10 a novějších můžete vytvořit šablony pro správu a nakonfigurovat nastavení zásad skupiny v Intune. V této aktualizaci můžete nakonfigurovat nastavení, která se vztahují na Microsoft Edge verze 77 a novější.

Další informace o šablonách pro správu najdete v tématu [použití šablon Windows 10 ke konfiguraci nastavení zásad skupiny v Intune](../configuration/administrative-templates-windows.md).

Platí pro:

- Windows 10 a novější (Windows RS4 +)

## <a name="week-of-august-12-2019"></a>Týden od 12. srpna 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment----3504144-----"></a>Řízení chování při odinstalaci aplikace pro iOS při zrušení registrace zařízení <!-- 3504144   -->
Správci mohou spravovat, zda je aplikace v zařízení odebrána nebo udržována v případě, že je zařízení odregistrováno na úrovni uživatele nebo skupiny zařízení. 

#### <a name="categorize-microsoft-store-for-business-apps----3926922---"></a>Kategorizace Microsoft Store pro obchodní aplikace <!-- 3926922 -->
Microsoft Store pro obchodní aplikace můžete zařadit do kategorií. Provedete to tak, že v **Intune**  > **klientských aplikacích**  > **aplikace** > vyberete**kategorii**> **informace o aplikaci** Microsoft Store pro obchodní aplikace  > . V rozevírací nabídce přiřaďte kategorii.

#### <a name="customized-notifications-for-microsoft-intune-app-users----4843354----"></a>Přizpůsobená oznámení pro uživatele aplikací Microsoft Intune <!-- 4843354  -->
Microsoft Intune aplikace pro Android teď podporuje zobrazení vlastních nabízených oznámení a jejich vyrovnání s podporou, která se nedávno přidala v Portál společnosti aplikacích pro iOS a Android. Další informace najdete v tématu [odesílání vlastních oznámení v Intune](../remote-actions/custom-notifications.md).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode----3755304-3041943-3041946-----"></a>Nové funkce pro vyhrazená zařízení s Androidem Enterprise v režimu více aplikací <!-- 3755304 3041943 3041946   -->

V Intune můžete ovládat funkce a nastavení v celoobrazovkovém prostředí na vyhrazených zařízeních s Androidem Enterprise (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** pro Platform > **pouze vlastník zařízení, omezení zařízení** pro typ profilu).

V této aktualizaci se přidávají následující funkce:

- **Vyhrazená zařízení** > **více aplikací**: **tlačítko virtuální domů** se dá na zařízení zobrazit na obrazovce nebo na plovoucí obrazovce, aby je uživatelé mohli přesunout.
- **Vyhrazená zařízení** > **multi-App**: **přístup svítící** umožňuje uživatelům používat svítící. 
- **Vyhrazená zařízení** > **více aplikací**: **ovládání hlasitosti médií** umožňuje uživatelům řídit hlasitost média zařízení pomocí posuvníku. 
- **Vyhrazená zařízení** > **více aplikací**: **Povolte šetřič obrazovky**, nahrajte vlastní obrázek a ovládací prvek, když se zobrazí spořič obrazovky.

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).

Platí pro:

- Zařízení se systémem Android Enterprise vyhrazená

#### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices----3574215-3574238-3574235-3574232-----"></a>Nové aplikace a konfigurační profily pro zařízení s plnou správou pro Android Enterprise <!-- 3574215 3574238 3574235 3574232   -->
Pomocí profilů můžete nakonfigurovat nastavení, která použijí nastavení sítě VPN, e-mailu a Wi-Fi, na zařízení s vlastníkem zařízení s Androidem Enterprise (plně spravovaná). V této aktualizaci můžete:

- Pomocí [zásad konfigurace aplikací](../apps/app-configuration-policies-use-android.md) nasaďte nastavení Outlooku, Gmail a devět pracovních e-mailů.
- Pomocí profilů konfigurace zařízení nasaďte [Nastavení důvěryhodných kořenových certifikátů](../protect/certificates-configure.md).
- Pomocí profilů konfigurace zařízení nasaďte nastavení [sítě VPN](../configuration/vpn-settings-android-enterprise.md) a [Wi-Fi](../configuration/wi-fi-settings-android-enterprise.md) .

> [!IMPORTANT]
> S touto funkcí se uživatelé ověřují pomocí svého uživatelského jména a hesla pro profily sítě VPN, Wi-Fi a e-mailu. V současné době není ověřování založené na certifikátech k dispozici.

Platí pro:  
- Vlastník zařízení se systémem Android Enterprise (plně spravovaný)

#### <a name="control-the-apps-files-documents-and-folders-that-open-when-users-sign-in-to-macos-devices---3914202-----"></a>Řízení aplikací, souborů, dokumentů a složek, které se otevřou, když se uživatelé přihlásí k zařízením macOS <!--3914202   -->
Můžete povolit a nakonfigurovat funkce na zařízeních macOS (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **MacOS** pro **funkce zařízení** > pro typ profilu). 

V této aktualizaci se nachází nové nastavení přihlašovacích položek, které určuje, které aplikace, soubory, dokumenty a složky se otevřou, když se uživatel přihlásí k zaregistrovanému zařízení. 

Pokud chcete zobrazit aktuální nastavení, přejděte na [Nastavení funkcí zařízení MacOS v Intune](../configuration/macos-device-features-settings.md).

Platí pro:  
- macOS

#### <a name="deadlines-replace-engaged-restart-settings-for-windows-update-rings------4464404----------"></a>Konečné termíny nahrazují nastavení opětovného spuštění pro web Windows Update okruhy   <!-- 4464404        -->
Pro zajištění souladu s nejnovějšími [změnami údržby Windows](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903#servicing)teď aktualizační kanály Windows 10 v Intune [podporují nastavení pro konečné termíny](../protect/windows-update-settings.md). *Konečné termíny* určují, kdy zařízení nainstaluje funkce a aktualizace zabezpečení.  V zařízeních se systémem Windows 10 1903 nebo novějším mají *termíny* přednost před konfiguracemi pro *následné restartování*.  V budoucnu se *konečné termíny* *nahrazují i v dřívějších* verzích Windows 10.  

Když nebudete konfigurovat *konečné termíny*, budou se zařízení dál používat s nastavením jejich nastavení, ale Intune bude v budoucí aktualizaci zastaralá o podporu *pro nastavení.*  

Naplánujte použití *konečných termínů* pro všechna vaše zařízení s Windows 10. Po nastavení *konečných termínů* můžete změnit konfigurace Intune, aby se *restarty* nenakonfigurovaly. Pokud je nastavené na Nenakonfigurováno, Intune zastaví správu těchto nastavení na zařízeních, ale neodebere poslední konfigurace nastavení ze zařízení. Poslední konfigurace, které byly nastavené pro probíhající *restart* , zůstávají aktivní a používají se na zařízeních, dokud se tato nastavení neupraví jinou metodou než Intune. Později, když se změní verze Windows, nebo když se u *konečných termínů* podpora Intune dokončí rozšíření zařízení na verzi Windows, začne používat nové nastavení, které už jsou na svém místě.

#### <a name="support-for-multiple-microsoft-intune-certificate-connectors--------4704642--------"></a>Podpora více Microsoft Intunech konektorů certifikátů   <!--   4704642      -->
Intune teď podporuje instalaci a používání více [Microsoft Intunech konektorů certifikátů pro operace PKCS](../protect/certficates-pfx-configure.md). Tato změna podporuje vyrovnávání zatížení a vysokou dostupnost konektoru. Každá instance konektoru může zpracovávat žádosti o certifikát z Intune.  Pokud jeden konektor není k dispozici, ostatní konektory pokračují v zpracování požadavků. 

Chcete-li použít více konektorů, nemusíte upgradovat na nejnovější verzi softwaru konektoru.  

#### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices----4867699-4867709-----"></a>Nové nastavení a změny stávajících nastavení pro omezení funkcí v zařízeních s iOS a macOS <!-- 4867699 4867709   -->
Můžete vytvořit profily k omezení nastavení na zařízeních s iOS a macOS (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** nebo **MacOS** pro typ platformy > **zařízení. omezení**). Tato aktualizace obsahuje následující funkce:

- V **macOS** > **omezení zařízení** > **Cloud a úložiště**můžete **pomocí nového nastavení** pro zablokování uživatelům zablokovat spouštění práce na jednom zařízení macOS a pokračovat v práci na jiném zařízení MacOS nebo iOS.

  Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení MacOS a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-macos.md).

- V případě**zařízení**se **systémem iOS** >  jsou k dispozici několik změn:

  - **Integrované aplikace** > **Najít iPhone (jenom pod dohledem)** : nové nastavení, které tuto funkci blokuje v funkci najít aplikaci. 
  - **Integrované aplikace** > **Najít přátele (jenom pod dohledem)** : nové nastavení, které tuto funkci blokuje v funkci najít aplikaci. 
  - **Bezdrátová**  > **Změna stavu Wi-Fi (jenom pod dohledem)** : nové nastavení, které uživatelům brání v zapnutí nebo vypnutí Wi-Fi na zařízení.
  - **Klávesnice a slovník** > **QuickPath (jenom pod dohledem)** : nové nastavení, které blokuje funkci QuickPath.
  - **Cloud a úložiště**: **pokračování aktivity** se přejmenovalo na **odevzdání**.

  Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s iOS, abyste mohli povolit nebo zakázat funkce využívající Intune](../configuration/device-restrictions-ios.md).

Platí pro:  
- macOS 10,15 a novější
- iOS 13 a novější

#### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release----4867809-----"></a>Některá z nesledovaných omezení zařízení s iOS se budou pod dohledem – jenom s vydáním iOS 13,0. <!-- 4867809   -->
V této aktualizaci se některá nastavení vztahují na zařízení, která jsou jenom pod dohledem, pomocí verze iOS 13,0. Pokud jsou tato nastavení nakonfigurovaná a přiřazená k zařízením, která nejsou pod dohledem před vydáním iOS 13,0, nastavení se pořád aplikují na tato zařízení, která nejsou pod dohledem. I nadále platí i po upgradu zařízení na iOS 13,0. Tato omezení se odeberou na nekontrolovaných zařízeních, která se zálohují a obnovují. 

Mezi tato nastavení patří:

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

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s iOS, abyste mohli povolit nebo zakázat funkce využívající Intune](../configuration/device-restrictions-ios.md).

Platí pro:  
- iOS 13,0 a novější

#### <a name="improved-device-status-for-macos-filevault-encryption-----4944983-----------"></a>Vylepšený stav zařízení pro šifrování trezoru macOS  <!-- 4944983         -->
Aktualizovali jsme několik zpráv o [stavu zařízení](../protect/encryption-monitor.md#device-encryption-status) pro šifrování trezoru úložiště na zařízeních MacOS.

#### <a name="some-windows-defender-antivirus-scan-settings-in-the-reporting-show-a-failed-status----5119229---"></a>Některá nastavení kontroly antivirové ochrany v programu Windows Defender v hlášení zobrazují stav selhání <!-- 5119229 -->
V Intune můžete vytvořit zásady, které budou používat antivirovou ochranu v programu Windows Defender ke skenování zařízení s Windows 10 (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější** pro platformu >  **Omezení zařízení** pro typ profilu > **antivirová ochrana v programu Windows Defender**). Čas, kdy **má probíhat každodenní Rychlá kontrola** a **typ Systémové kontroly k provedení** sestav, zobrazuje stav selhání, pokud je ve skutečnosti stav úspěch. 

V této aktualizaci je toto chování opraveno. Takže když se nastavení úspěšně dokončí, zobrazí se při úspěšném prověřování stav úspěch a v případě, že se nastavení nepovede, zobrazí se stav úspěšného provedení **každodenní rychlé kontroly** a **typ kontroly prováděné systémem** . 

Další informace o nastavení antivirové ochrany v programu Windows Defender najdete v tématu [nastavení zařízení s Windows 10 (a novější) k povolení nebo omezení funkcí v Intune](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus). 

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="default-scope-tags----3702875----"></a>Výchozí značky oboru <!-- 3702875  -->
Nově integrovaná značka výchozího oboru je nyní k dispozici. Všechny neoznačené objekty Intune, které podporují značky oboru, se automaticky přiřazují k výchozí značce oboru. **Výchozí** značka oboru je přidána do všech existujících přiřazení rolí, aby bylo udržování parity s prostředím pro správu v současnosti. Pokud nechcete, aby správce viděli objekty Intune s výchozím označením oboru, odeberte z přiřazení role výchozí značku oboru. Tato funkce je podobná funkci obory zabezpečení v System Center Configuration Manager. Další informace najdete v tématu [použití značek RBAC a Scope k distribuci](scope-tags.md).

#### <a name="android-enrollment-device-administrator-support----4869749-----"></a>Podpora Správce zařízení registrace Androidu <!-- 4869749   -->
Do registrační stránky pro Android se přidala možnost registrace Správce zařízení s Androidem (**Intune** > **registrace zařízení** > **registrace v Androidu**). Správce zařízení s Androidem bude ve výchozím nastavení pro všechny klienty stále povolen.  Další informace najdete v tématu [registrace Správce zařízení s Androidem](../enrollment/android-enroll-device-administrator.md).

#### <a name="skip-more-screens-in-setup-assistant---4877451----"></a>Přeskočit další obrazovky v Průvodci nastavením <!--4877451  -->
Můžete nastavit Program registrace zařízení profily pro přeskočení následujících obrazovek pomocníka s nastavením:
- Pro iOS
    - Příznaky
    - Jazyk Express
    - Preferovaný jazyk
    - Migrace zařízení do zařízení
- Pro macOS
    - Čas obrazovky
    - Nastavení Touch ID

Další informace o přizpůsobení pomocníka s nastavením najdete v tématu [vytvoření registračního profilu Apple pro iOS](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) a [vytvoření registračního profilu Apple pro MacOS ](../enrollment/device-enrollment-program-enroll-macos.md#create-an-apple-enrollment-profile).

#### <a name="add-a-user-column-to-the-autopilot-device-csv-upload-process----3823054---"></a>Přidání uživatelského sloupce do procesu nahrání souboru CSV pro zařízení s autopilotem <!-- 3823054 -->
Nyní můžete přidat uživatelský sloupec do nahrávání sdíleného svazku clusteru pro zařízení s autopilotem. To vám umožní hromadně přiřazovat uživatele v době, kdy naimportujete sdílený svazek clusteru. Další informace najdete v tématu [registrace zařízení s Windows v Intune pomocí automatických pilotů Windows](../enrollment/enrollment-autopilot.md).


### <a name="device-management"></a>Správa zařízení

#### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Nakonfigurujte automatický časový limit pro vyčištění zařízení na 30 dní. <!--4231059  -->
Můžete nastavit automatický časový limit pro vyčištění zařízení, který je kratší než 30 dní (místo předchozího limitu 90 dní) po posledním přihlášení. Provedete to tak, že přejdete na **Intune** > **zařízení** > **Nastavení** > **zařízení vyčistit pravidla**.

#### <a name="build-number-included-on-android-device-hardware-page----4461910-----"></a>Číslo sestavení zahrnuté na stránce hardware pro zařízení s Androidem <!-- 4461910   -->
Nová položka na stránce hardware pro každé zařízení s Androidem zahrnuje číslo buildu operačního systému daného zařízení. Další informace najdete v tématu [zobrazení podrobností o zařízení v Intune](../remote-actions/device-inventory.md).


<!-- ########################## -->

## <a name="week-of-august-5-2019"></a>Týden od 5. srpna 2019

### <a name="zebra-technologies-is-a-supported-oem-for-oemconfig-on-android-enterprise-devices-----4843713---"></a>Technologie Zebra je podporovaným výrobcem OEM pro OEMConfig na zařízeních s Androidem Enterprise.  <!-- 4843713 -->

V Intune můžete vytvořit profily konfigurace zařízení a použít nastavení pro zařízení s Androidem Enterprise pomocí OEMConfig (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** . pro Platform > **OEMConfig** pro typ profilu).

V této aktualizaci je Zebra technologie podporovaným výrobcem OEM (Original Equipment Manufacturer) pro OEMConfig. Další informace o OEMConfig najdete v tématu [použití a Správa zařízení s Androidem Enterprise pomocí OEMConfig](../configuration/android-oem-configuration-overview.md).

Platí pro:  
- Android Enterprise

<!-- ########################## -->

## <a name="week-of-july-22-2019"></a>Týden od 22. července 2019 

### <a name="app-management"></a>Správa aplikací

#### <a name="customized-notifications-for-users-and-groups-------16766574------------"></a>Přizpůsobená oznámení pro uživatele a skupiny    <!-- 16766574          -->
Odešlete vlastní nabízená oznámení z aplikace Portál společnosti uživatelům na zařízeních s iOS a Androidem, která spravujete pomocí Intune. Tato mobilní nabízená oznámení jsou vysoce přizpůsobitelná s bezplatným textem a lze je použít pro libovolný účel. Můžete je cílit na různé skupiny uživatelů ve vaší organizaci. Další informace najdete v tématu [vlastní oznámení](../remote-actions/custom-notifications.md).

#### <a name="googles-device-policy-controller-app----3041950----"></a>Aplikace kontroleru zásad zařízení Google <!-- 3041950  -->
Aplikace spravované domovské obrazovky teď poskytuje přístup k aplikaci zásad zařízení s Androidem. Spravovaná aplikace pro domovskou obrazovku je vlastní spouštěč používaný pro zařízení zaregistrovaná v Intune jako vyhrazená zařízení Android Enterprise (AE) pomocí celoobrazovkového režimu s více aplikacemi. K aplikaci zásad pro zařízení s Androidem můžete získat přístup, nebo se uživatelé k aplikaci zásad zařízení s Androidem pořídit pro účely podpory a ladění. Tato funkce je k dispozici v době, kdy se zařízení zaregistruje a zamkne do spravované domovské obrazovky. K použití této funkce nejsou potřeba žádné další instalace.

#### <a name="outlook-protection-settings-for-ios-and-android-devices----3212619---"></a>Nastavení ochrany Outlooku pro zařízení s iOS a Androidem <!-- 3212619 -->
Pro Outlook pro iOS a Android teď můžete nakonfigurovat obecná nastavení konfigurace aplikací a ochrany dat, a to pomocí jednoduchých ovládacích prvků pro správu Intune bez registrace zařízení. Obecné nastavení konfigurace aplikací poskytuje paritu nastavení správci můžou povolit při správě Outlooku pro iOS a Android na zaregistrovaných zařízeních. Další informace o nastavení aplikace Outlook najdete v tématu [nasazení aplikace Outlook pro iOS a nastavení konfigurace aplikací pro Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910-eeready---idstaged---"></a>Při vytváření profilů konfigurace zařízení s Windows 10 použít pravidla použitelnosti <!-- 2549910 eeready   idstaged -->

Vytvoříte konfigurační profily zařízení s Windows 10 (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10** pro **pravidla použitelnosti**platformy >). V této aktualizaci můžete vytvořit **pravidlo použitelnosti** , aby se profil mohl vztahovat jenom na konkrétní edici nebo konkrétní verzi. Můžete například vytvořit profil, který povolí některá nastavení nástroje BitLocker. Po přidání profilu použijte pravidlo použitelnosti, aby se profil mohl vztahovat jenom na zařízení s Windows 10 Enterprise.

Pokud chcete přidat pravidlo použitelnosti, přečtěte si téma [pravidla použitelnosti](../configuration/device-profile-create.md#applicability-rules).

Platí pro: Windows 10 a novější

#### <a name="use-tokens-to-add-device-specific-information-in-custom-profiles-for-ios-and-macos-devices----3330008----"></a>Použití tokenů k přidání informací specifických pro zařízení v uživatelských profilech pro zařízení s iOS a macOS <!-- 3330008  -->
Pomocí vlastních profilů na zařízeních s iOS a macOS můžete nakonfigurovat nastavení a funkce, které nejsou součástí Intune (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** nebo **MacOS** pro platformu. > **Vlastní** pro typ profilu). V této aktualizaci můžete přidat tokeny do souborů `.mobileconfig` a přidat informace specifické pro zařízení. Můžete například přidat `Serial Number: {{serialnumber}}` do konfiguračního souboru, chcete-li zobrazit sériové číslo zařízení.

Pokud chcete vytvořit vlastní profil, přečtěte si téma [vlastní nastavení pro iOS](../configuration/custom-settings-ios.md) nebo [MacOS vlastní nastavení](../configuration/custom-settings-macos.md).

Platí pro:
- iOS
- macOS

#### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise----3712769-----"></a>Nový Návrhář konfigurace při vytváření profilu OEMConfig pro Android Enterprise <!-- 3712769   -->
V Intune můžete vytvořit konfigurační profil zařízení, který používá aplikaci OEMConfig (konfigurace zařízení > Profily > vytvořit profil > Android Enterprise for Platform > OEMConfig pro typ profilu). Když to uděláte, otevře se Editor JSON se šablonou a hodnotami, které můžete změnit. 

Tato aktualizace obsahuje návrháře konfigurace s vylepšeným uživatelským prostředím, které zobrazuje podrobnosti vložené do aplikace včetně nadpisů, popisů a dalších. Editor JSON je stále k dispozici a zobrazuje všechny změny, které provedete v Návrháři konfigurace.

Pokud chcete zobrazit aktuální nastavení, přejděte na [používání a Správa zařízení s Androidem Enterprise pomocí OEMConfig](../configuration/android-oem-configuration-overview.md).

Platí pro: Android Enterprise

#### <a name="updated-ui-for-configuring-windows-hello-----4089576--------------"></a>Aktualizované uživatelské rozhraní pro konfiguraci Windows Hello  <!-- 4089576            -->
Aktualizovali jsme konzolu, ve které [nakonfigurujete Intune tak, aby používala Windows Hello pro firmy](../protect/windows-hello.md). Všechna nastavení konfigurace jsou nyní k dispozici ve stejném podokně konzoly, kde povolíte podporu pro Windows Hello. 


#### <a name="intune-powershell-sdk----4924113---"></a>Sada Intune PowerShell SDK <!-- 4924113 --> 
Sada Intune PowerShell SDK, která poskytuje podporu pro rozhraní Intune API prostřednictvím Microsoft Graph, se aktualizovala na verzi 6.1907.1.0. Sada SDK teď podporuje následující:
- Funguje s Azure Automation.
- Podporuje operace čtení jenom pro aplikace. 
- Podporuje popisné zkrácené názvy jako aliasy.
- Vyhovuje konvencím pojmenování PowerShellu. Konkrétně je parametr `PSCredential` (na rutině `Connect-MSGraph`) přejmenovaný na `Credential`.
- Při použití rutiny `Invoke-MSGraphRequest` podporuje Ruční určení hodnoty hlavičky `Content-Type`.

Další informace najdete v tématu [sada PowerShell SDK pro Microsoft Intune Graph API](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune).


### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="updates-for-enrollment-restrictions-----2871968---"></a>Aktualizace pro omezení registrace  <!-- 2871968 -->
Byla aktualizována omezení registrace pro nové klienty, aby byly ve výchozím nastavení povoleny pracovní profily Android Enterprise. Stávající klienti nebudou mít žádné změny. Pokud chcete používat pracovní profily Android Enterprise, musíte [svůj účet Intune připojit k vašemu spravovanému účtu Google Play](../enrollment/connect-intune-android-enterprise.md).

#### <a name="ui-updates-for-apple-enrollment-and-enrollment-restrictions---4089575-4089579----"></a>Aktualizace uživatelského rozhraní pro registrace Apple a omezení registrace <!--4089575, 4089579  -->
Oba následující procesy používají uživatelské rozhraní ve stylu Průvodce:
- Registrace zařízení Apple. Další informace najdete v tématu [Automatická registrace zařízení s iOS pomocí program registrace zařízení společnosti Apple](../enrollment/device-enrollment-program-enroll-ios.md).
- Vytvoření omezení registrace. Další informace najdete v tématu [Nastavení omezení registrace](../enrollment/enrollment-restrictions-set.md).

#### <a name="handling-pre-configuration-of-corporate-device-identifiers-for-android-q-devices----4711509--idmiss---"></a>Zpracování předběžné konfigurace identifikátorů podnikových zařízení pro zařízení s Androidem Q <!-- 4711509  idmiss -->
V Androidu Q (v10 za účelem) bude Google odebrat možnost agentů MDM na starších zařízeních s Androidem spravovaná (Správce zařízení), aby shromáždila informace o identifikátoru zařízení.  Intune obsahuje funkci, která správcům IT umožňuje [předem nakonfigurovat seznam sériových čísel zařízení nebo IMEI](../enrollment/corporate-identifiers-add.md#identify-corporate-owned-devices-with-imei-or-serial-number) , aby tato zařízení mohla automaticky označovat jako vlastněná společností. Tato funkce nebude fungovat pro zařízení s Androidem Q, která jsou spravovaná správcem zařízení.  Bez ohledu na to, jestli se sériové číslo nebo IMEI zařízení nahraje, se při registraci v Intune vždycky považuje za osobní.  Po registraci můžete vlastnictví ručně přepínat na podnik.  To má vliv pouze na nové registrace a stávající zaregistrovaná zařízení ovlivněna nebudou.  Tato změna nemá vliv na zařízení s Androidem spravovaná pomocí pracovních profilů a bude dál fungovat, jak ještě dnes.  Zařízení se systémem Android Q zaregistrovaná jako správce zařízení už navíc nebudou moct v konzole Intune hlásit sériové číslo nebo IMEI jako vlastnosti zařízení.

#### <a name="icons-have-changed-for-android-enterprise-enrollments-work-profile-dedicated-devices-and-fully-managed-devices----4977730---"></a>Změnily se ikony pro registrace Android Enterprise (pracovní profil, vyhrazená zařízení a plně spravovaná zařízení). <!-- 4977730 -->
Změnili jsme ikony profilů registrace pro Android Enterprise. Pokud chcete zobrazit nové ikony, přejděte na **Intune**  > **registrace**  > **registraci v Androidu** > v části **profily zápisu**.


#### <a name="windows-diagnostic-data-collection-change----4113859---"></a>Změna shromažďování diagnostických dat Windows <!-- 4113859 -->
Výchozí hodnota pro shromažďování diagnostických dat se změnila pro zařízení s Windows 10 verze 1903 a novější. Počínaje systémem Windows 10 1903 je shromažďování diagnostických dat ve výchozím nastavení povoleno. Diagnostická data Windows jsou důležitá technická data ze zařízení s Windows, která se týkají zařízení a způsobu provádění Windows a souvisejícího softwaru. Další informace najdete v tématu [Konfigurace diagnostických dat Windows ve vaší organizaci](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization). V případě, že se v profilu autopilotu pomocí [System/AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry)nenastavuje jinak, zařízení autopilotu se také přihlásí do "plné" telemetrie.

### <a name="device-management"></a>Správa zařízení

#### <a name="improve-device-location---3855417----"></a>Vylepšit umístění zařízení<!-- 3855417  -->
Pomocí akce **Najít zařízení** můžete přiblížit přesnou souřadnici zařízení. Další informace o vyhledání ztracených zařízení s iOS najdete v tématu [vyhledání ztracených zařízení s iOS](../remote-actions/device-locate.md).


### <a name="device-security"></a>Zabezpečení zařízení

#### <a name="advanced-settings-for-windows-defender-firewall--public-preview------1311949-------"></a>Rozšířená nastavení pro firewall v programu Windows Defender (Public Preview)  <!--  1311949     -->  
Pomocí Intune můžete spravovat [vlastní pravidla brány firewall jako součást profilu konfigurace zařízení](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) pro službu Endpoint Protection ve Windows 10. Pravidla mohou určovat příchozí a odchozí chování aplikací, síťových adres a portů. 

#### <a name="updated-ui-for-managing-security-baselines------4091125-------"></a>Aktualizované uživatelské rozhraní pro správu standardních hodnot zabezpečení   <!-- 4091125     -->
Aktualizovali jsme [prostředí pro vytváření a úpravy](../protect/security-baselines.md#create-the-profile) v konzole Intune pro naše základní směry zabezpečení. Změny zahrnují:

Jednodušší formát ve stylu průvodce, který je zúžený na jedno okno. v jednom okně. Tento nový návrh se zapíná s oknem neustálému zvětšování, který vyžaduje, aby odborníci na IT přešli do několika samostatných podoken.  
Nyní můžete vytvářet přiřazení v rámci prostředí vytváření a úprav, aniž byste se museli vracet později, aby bylo možné přiřadit směrné plány. Přidali jsme souhrn nastavení, která můžete zobrazit před vytvořením nového směrného plánu a úpravou stávajícího. Při úpravách zobrazuje souhrn pouze seznam položek, které jsou nastaveny v rámci jedné kategorie upravovaných vlastností.



<!-- ########################## -->

## <a name="week-of-july-15-2019"></a>Týden od 15. července 2019 

### <a name="app-management"></a>Správa aplikací

#### <a name="managed-home-screen-and-managed-settings-icons----4918107---"></a>Ikony spravované domovské obrazovky a spravovaného nastavení <!-- 4918107 -->
Ikona spravované aplikace na domovské obrazovce a ikona **spravovaného nastavení** se aktualizovaly. Spravovaná aplikace pro domovskou obrazovku se používá jenom u zařízení zaregistrovaných v Intune jako vyhrazená zařízení s Androidem Enterprise (AE) a provozovaná v celoobrazovkovém režimu s více aplikacemi. Další informace o spravované aplikaci pro domovskou obrazovku najdete v tématu [Konfigurace aplikace pro domovskou obrazovku spravované Microsoftem pro Android Enterprise](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="android-device-policy-on-android-enterprise-dedicated-devices----4918136---"></a>Zásady zařízení s Androidem na vyhrazených zařízeních s Androidem Enterprise <!-- 4918136 -->
Přístup k aplikaci zásad zařízení s Androidem můžete získat z obrazovky ladění aplikace pro správu domácí obrazovky. Spravovaná aplikace pro domovskou obrazovku se používá jenom u zařízení zaregistrovaných v Intune jako vyhrazená zařízení s Androidem Enterprise (AE) a provozovaná v celoobrazovkovém režimu s více aplikacemi. Další informace najdete v tématu [Konfigurace aplikace pro domovskou obrazovku spravované Microsoftem pro Android Enterprise](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="ios-company-portal-updates----3902931---"></a>aktualizace pro iOS Portál společnosti <!-- 3902931 -->
Název vaší společnosti při výzvě ke správě aplikací pro iOS nahradí aktuální text "i.manage.microsoft.com". V případě, že se uživatel pokusí nainstalovat aplikaci pro iOS z Portál společnosti nebo když uživatelé povolí správu aplikace, uvidí například název společnosti namísto "i.manage.microsoft.com". Tato akce bude zahrnuta pro všechny zákazníky za několik následujících dní.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="manage-filevault-for-macos-------3858502--4557986--1210104----"></a>Správa trezoru pro macOS   <!--  3858502 + 4557986 + 1210104  -->
Pomocí Intune můžete [Spravovat šifrování klíčů trezoru úložiště pro zařízení MacOS](../protect/encrypt-devices.md). K šifrování zařízení použijte konfigurační profil zařízení Endpoint Protection.

Naše podpora pro trezor souborů obsahuje šifrování nešifrovaných zařízení, v úschově zařízení pro osobní obnovení, automatické nebo ruční střídání osobních šifrovacích klíčů a načtení klíčů pro podniková zařízení. Koncoví uživatelé můžou k získání osobního obnovovacího klíče pro svá zašifrovaná zařízení použít taky web Portál společnosti. 

Také jsme rozšířili sestavu šifrování tak, aby obsahovala informace o souběžných informacích [o trezoru úložiště](../protect/encryption-monitor.md) pro BitLocker, takže můžete zobrazit všechny podrobnosti o šifrování zařízení na jednom místě. 

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="windows-autopilot-reset-removes-the-devices-primary-user----4156123---"></a>Resetování Windows autopilotu odebere primárního uživatele zařízení. <!-- 4156123 -->
Když se na zařízení používá resetování autopilotního projektu, primární uživatel zařízení se odebere. Další uživatel, který se přihlásí po obnovení, se nastaví jako primární uživatel. Tato funkce bude zahrnuta pro všechny zákazníky za několik následujících dní.

## <a name="week-of-july-8-2019"></a>Týden od 8. července 2019

### <a name="new-office-windows-and-onedrive-settings-in-windows-10-administrative-templates----3510695---"></a>Nové nastavení Office, Windows a OneDrivu v šablonách pro správu Windows 10 <!-- 3510695 -->

V Intune můžete vytvářet šablony pro správu, které napodobují místní správu zásad skupiny (**Správa zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější** pro platformu >  **Šablona pro správu** pro typ profilu).

Tato aktualizace zahrnuje další nastavení Office, Windows a OneDrivu, která můžete přidat do šablon. S těmito novými nastaveními teď můžete nakonfigurovat více než 2500 nastavení, která jsou na bázi 100% cloudu.

Další informace o této funkci najdete v tématu [použití šablon Windows 10 ke konfiguraci nastavení zásad skupiny v Intune](../configuration/administrative-templates-windows.md).

Platí pro: Windows 10 a novější

## <a name="week-of-july-1-2019"></a>Týden od 1. července 2019 

### <a name="app-management"></a>Správa aplikací

#### <a name="aad-and-app-on-android-enterprise-devices----3574267---"></a>AAD a aplikace na zařízeních s Androidem Enterprise <!-- 3574267 -->
Při připojování plně spravovaných zařízení s Androidem Enterprise se uživatelé teď při počátečním nastavení nového zařízení nebo obnovení továrního nastavení registrují s Azure Active Directory (AAD). Předtím, než se pro plně spravované zařízení dokončí, musí uživatel ručně spustit aplikaci Microsoft Intune a spustit registraci AAD. Když se teď uživatel při počátečním nastavení zaregistruje na domovské stránce zařízení, zařízení se zaregistruje i zaregistruje.

Kromě aktualizací AAD se teď podporují zásady ochrany aplikací Intune (aplikace) na plně spravovaných podnikových zařízeních s Androidem. Tato funkce bude k dispozici, jakmile ji nasadíme. Další informace najdete v tématu [Přidání spravovaných Google Play aplikací do zařízení s Androidem Enterprise pomocí Intune](../apps/apps-add-android-for-work.md).

## <a name="week-of-june-24-2019"></a>Týden od 24. června 2019 

### <a name="app-management"></a>Správa aplikací

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data----3145939---"></a>Nakonfigurovat, který prohlížeč smí propojit s daty organizace <!-- 3145939 -->
Zásady Intune App Protection (aplikace) na zařízeních s Androidem a iOS teď umožňují přenášet webové odkazy organizace na konkrétní prohlížeč mimo Intune Managed Browser nebo Microsoft Edge.  Další informace o aplikaci najdete v tématu [co jsou zásady ochrany aplikací?](../apps/app-protection-policy.md).

#### <a name="all-apps-page-identifies-onlineoffline-microsoft-store-for-business-apps--4089647---"></a>Stránka všechny aplikace identifikuje online nebo offline Microsoft Store pro obchodní aplikace.<!--4089647 -->
Stránka **všechny aplikace** teď obsahuje popis, který identifikuje aplikace Microsoft Store pro firmy (MSFB) jako online nebo offline aplikace. Každá aplikace MSFB teď obsahuje příponu pro **online** nebo **offline**. Stránka s podrobnostmi o aplikaci zahrnuje také **typ licence** a **podporuje instalaci kontextu zařízení** (pouze offline licencované aplikace).

#### <a name="company-portal-app-on-windows-shared-devices---4393553---"></a>Portál společnosti aplikace na sdílených zařízeních s Windows <!--4393553 -->
Uživatelé teď můžou k aplikaci Portál společnosti přistupovat na sdílených zařízeních se systémem Windows. Koncovým uživatelům se na dlaždici zařízení zobrazí **sdílený** popisek. To platí pro Windows Portál společnosti app verze 10.3.45609.0 a novější.

#### <a name="view-all-installed-apps-from-new-company-portal-web-page----4224326---"></a>Zobrazit všechny nainstalované aplikace z nové Portál společnosti webové stránky <!-- 4224326 -->
Stránka Portál společnosti nové **nainstalované aplikace** na webu obsahuje seznam všech spravovaných aplikací (požadovaných i dostupných), které jsou nainstalovány na zařízeních uživatele. Kromě typu přiřazení uživatelé uvidí vydavatele aplikace, datum publikování a aktuální stav instalace. Pokud jste neudělali žádné aplikace, které uživatelé potřebují nebo nejsou k dispozici, zobrazí se zpráva s vysvětlením, že nebyly nainstalovány žádné aplikace společnosti. Pokud chcete zobrazit novou stránku na webu, přejděte na [web portál společnosti](https://portal.manage.microsoft.com) a klikněte na **nainstalované aplikace**.  

#### <a name="new-view-lets-app-users-see-all-managed-apps-installed-on-device----2352913---"></a>Nové zobrazení umožňuje uživatelům aplikace zobrazit všechny spravované aplikace nainstalované na zařízení. <!-- 2352913 -->  
Aplikace Portál společnosti pro Windows teď obsahuje seznam všech spravovaných aplikací (požadovaných i dostupných), které jsou nainstalované na zařízení uživatele. Uživatelé můžou také zobrazit pokusy o instalaci aplikací a jejich aktuální stavy. Pokud jste neudělali aplikace, které uživatelé potřebují nebo k nim nejsou k dispozici, zobrazí se zpráva s vysvětlením, že nebyly nainstalovány žádné aplikace společnosti. Chcete-li zobrazit nové zobrazení, přejděte do navigačního podokna Portál společnosti a vyberte **aplikace** > **nainstalované aplikace**.    

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>Konfigurace nastavení pro rozšíření jádra na zařízeních macOS <!-- 2043024 -->
Na zařízeních macOS můžete vytvořit konfigurační profil zařízení (**Konfigurace zařízení** > **profily** > **vytvořit profil** > zvolit **MacOS** pro platformu). Tato aktualizace zahrnuje novou skupinu nastavení, která vám umožní nakonfigurovat a používat na svých zařízeních rozšíření jádra. Můžete přidat konkrétní rozšíření nebo povolíte všechna rozšíření od konkrétního partnera nebo vývojáře.

Další informace o této funkci najdete v tématu [Přehled rozšíření jádra](../configuration/kernel-extensions-overview-macos.md) a [nastavení rozšíření jádra](../configuration/kernel-extensions-settings-macos.md).

Platí pro: macOS 10.13.2 a novější

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options----2697002---"></a>Aplikace z nastavení jenom pro Store pro zařízení s Windows 10 obsahují další možnosti konfigurace. <!-- 2697002 -->
Když vytvoříte profil omezení zařízení pro zařízení s Windows, můžete použít **aplikace z nastavení jenom úložiště** , aby uživatelé mohli instalovat jenom aplikace z Windows Storu (**Konfigurace zařízení**  > **profily**  > **vytvořit. Profil**  > **Windows 10 a novější** pro omezení platforem > **zařízení** pro typ profilu). V této aktualizaci je toto nastavení rozšířeno na podporu více možností. 

Nové nastavení zobrazíte tak, že přejdete na [nastavení zařízení s Windows 10 (a novější) a povolíte nebo zakážete funkce](../configuration/device-restrictions-windows-10.md#app-store).

Platí pro: Windows 10 a novější

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group----4089955---"></a>Nasazení více profilů zařízení rozšíření Zebra mobility na zařízení, stejnou skupinu uživatelů nebo stejnou skupinu zařízení <!-- 4089955 -->
V Intune můžete použít rozšíření Zebra mobility (MX) v profilu konfigurace zařízení k přizpůsobení nastavení pro Zebra zařízení, která nejsou integrovaná do Intune. V současné době můžete nasadit jeden profil na jedno zařízení. V této aktualizaci můžete nasadit několik profilů do:
- Stejná skupina uživatelů
- Stejná skupina zařízení
- Jedno zařízení

[Používání a Správa zařízení Zebra pomocí rozšíření Zebra mobility v Microsoft Intune](../configuration/android-zebra-mx-overview.md) ukazuje, jak používat MX v Intune.

Platí pro: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow----4404075----"></a>Některá nastavení veřejného terminálu na zařízeních s iOS se nastavují pomocí Block, kde se nahrazuje "povolení". <!-- 4404075  -->
Když vytvoříte profil omezení zařízení na zařízeních s iOS (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro > **omezení zařízení** pro typ profilu > veřejný **terminál** ) nastavíte **Automatické uzamčení**, **přepínač vyzvánění**, **otočení obrazovky**, **tlačítko přechodu na obrazovku**a **tlačítka hlasitosti**. 

V této aktualizaci jsou hodnoty **zablokované** (blokuje funkci) a **nejsou nakonfigurované** (umožňuje funkci). Nastavení zobrazíte tak, že přejdete na [nastavení zařízení s iOS a povolíte nebo zakážete funkce](../configuration/device-restrictions-ios.md#kiosk). 

Platí pro: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices----4490704---"></a>Použití ID obličeje pro ověřování hesla na zařízeních s iOS <!-- 4490704 -->
Když vytvoříte profil omezení zařízení pro zařízení s iOS, můžete pro heslo použít otisk prstu. V této aktualizaci nastavení hesla otisku prstu taky povoluje rozpoznávání obličeje (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro > **omezení zařízení** s platformou pro profil Zadejte > **heslo**). V důsledku toho se změnila následující nastavení:

- **Odemčení otiskem prstu** je teď **dotykové ID a odemknutí ID obličeje**.
- **Úprava otisku prstu (jenom pod dohledem)** je teď **dotykové ID a úprava ID obličeje (jenom pod dohledem)** .

ID obličeje je dostupné v iOS 11,0 a novějších verzích. Nastavení zobrazíte tak, že přejdete na [nastavení zařízení s iOS a povolíte nebo zakážete funkce využívající Intune](../configuration/device-restrictions-ios.md#password).

Platí pro: iOS

#### <a name="restricting-gaming-and-app-store-features-on-ios-devices-is-now-dependent-on-ratings-region----4593948---"></a>Omezení her a funkcí pro obchod s aplikacemi na zařízeních s iOS je teď závislé na oblasti hodnocení. <!-- 4593948 -->
Na zařízeních s iOS můžete povolit nebo omezit funkce týkající se her, App Storu a zobrazení dokumentů (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro > zařízení platformy.  **omezení** pro typ profilu > **App Store, zobrazování dokumentů, hraní her**). Můžete také zvolit oblast hodnocení, například USA. 

V této aktualizaci se funkce **aplikace** přesune, aby byla podřízená **oblasti hodnocení**a byla závislá na **oblasti hodnocení**. Nastavení zobrazíte tak, že přejdete na [nastavení zařízení s iOS a povolíte nebo zakážete funkce využívající Intune](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Platí pro: iOS

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="windows-autopilot-support-for-hybrid-azure-ad-join----4809146--"></a>Podpora Windows autopilotu pro hybridní službu Azure AD JOIN <!-- 4809146-->
Windows autopilot pro stávající zařízení teď podporuje hybridní připojení ke službě Azure AD (kromě stávající podpory Azure AD JOIN). Platí pro zařízení s Windows 10 verze 1809 a novější. Další informace najdete v tématu věnovaném [autopilotu Windows pro existující zařízení](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices).



### <a name="device-management"></a>Správa zařízení

#### <a name="see-the-security-patch-level-for-android-devices----4461911---"></a>Zobrazit úroveň opravy zabezpečení pro zařízení s Androidem <!-- 4461911 -->
Teď můžete zobrazit úroveň opravy zabezpečení pro zařízení s Androidem. Pokud to chcete udělat, vyberte**zařízení**  >  **Intune**  > **všechna zařízení** > vyberte **hardware**> zařízení.
Úroveň opravy je uvedena v části **operační systém** .

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group----3173810---"></a>Přiřadit značky oboru všem spravovaným zařízením ve skupině zabezpečení <!-- 3173810 -->
Nyní můžete přiřadit značky oboru ke skupině zabezpečení a všechna zařízení ve skupině zabezpečení budou také přidružena k těmto značkám oboru. Všechna zařízení v těchto skupinách budou mít také přiřazenou značku oboru. Tagy oboru nastavené touto funkcí přepíší sadu značek oboru s aktuálním tokem značek oboru zařízení. Další informace najdete v tématu [použití značek RBAC a Scope pro distribuci](scope-tags.md).

### <a name="device-security"></a>Zabezpečení zařízení

#### <a name="use-keyword-search-with-security-baselines-------"></a>Použití hledání klíčových slov pomocí standardních hodnot zabezpečení <!--  -->
Když vytváříte nebo upravujete [profily standardních hodnot zabezpečení](../protect/security-baselines.md#create-the-profile), můžete zadat klíčová slova na novém panelu *hledání* a vyfiltrovat dostupné skupiny nastavení na ty, které obsahují vaše kritéria hledání. 

#### <a name="the-security-baselines-feature-is-now-generally-available-----3785395---"></a>Funkce standardních hodnot zabezpečení je teď všeobecně dostupná.  <!-- 3785395 -->
Funkce **standardních hodnot zabezpečení** není ve verzi Preview a je teď obecně dostupná (GA).  To znamená, že funkce je připravena k použití v produkčním prostředí. Jednotlivé základní šablony ale mohou zůstat ve verzi Preview a jsou vyhodnoceny a vydány pro GA na základě vlastních plánů.

#### <a name="the-mdm-security-baseline-template-is-now-generally-available------3794072-4217151--3534649---"></a>Šablona standardních hodnot zabezpečení MDM je teď všeobecně dostupná.   <!-- 3794072, 4217151,  3534649 -->
Šablona základní hodnoty zabezpečení MDM se přesunula z verze Preview a teď je všeobecně dostupná (GA). Šablona GA je **pro květen 2019**označena jako základní hodnota zabezpečení MDM.  Jedná se o novou šablonu, která není upgradem z verze Preview.  Jako novou šablonu budete muset zkontrolovat nastavení, která [obsahuje](../protect/security-baseline-settings-mdm.md), a pak vytvořit nové profily, pomocí kterých šablonu nasadíte do svého zařízení. Další šablony standardních hodnot zabezpečení mohou zůstat ve verzi Preview. Seznam dostupných směrných plánů najdete v tématu [dostupné standardní hodnoty zabezpečení](../protect/security-baselines.md#available-security-baselines).  

Kromě nové šablony obsahuje *základní plán zabezpečení MDM pro květen 2019* dvě nastavení, která jsme nedávno oznámili v našem vývojovém článku:  
- Nad zámkem: hlas – aktivovat aplikace z uzamčené obrazovky  
- DeviceGuard: při příštím restartování zařízení použijte zabezpečení na základě virtualizace (VBS).  

*Základní hodnota zabezpečení MDM pro květen 2019* obsahuje také přidání několika nových nastavení, odebrání ostatních a revizi výchozí hodnoty jednoho nastavení. Podrobný seznam změn z verze Preview na GA najdete v tématu **co se změnilo v nové šabloně**.

#### <a name="security-baseline-versioning-----3194322---"></a>Základní verze zabezpečení  <!-- 3194322 -->
Standardní hodnoty zabezpečení pro Intune podporují správu verzí. V rámci této podpory platí, že při vydání nových verzí jednotlivých standardních hodnot zabezpečení můžete aktualizovat stávající základní profily zabezpečení tak, aby používaly novější základní verzi bez nutnosti opětovného vytvoření a nasazení nového směrného plánu od začátku. Kromě toho můžete v konzole Intune zobrazit informace o jednotlivých standardních hodnotách, jako je počet jednotlivých profilů, u kterých používáte základní hodnoty, kolik z různých základních verzí vaše profily používá a kdy nejnovější vydání konkrétního zabezpečení. směrný plán byl.  Další informace najdete v tématu **základní hodnoty zabezpečení**.

#### <a name="the-use-security-keys-for-sign-in-setting-has-moved-----4501151---"></a>Bylo přesunuto nastavení použít klíče zabezpečení pro přihlášení.  <!-- 4501151 -->
Nastavení konfigurace zařízení pro ochranu identity s názvem **použít klíče zabezpečení pro přihlášení** se už nenašlo jako dílčí nastavení *Konfigurace Windows Hello pro firmy*. Teď je to nastavení nejvyšší úrovně, které je vždycky dostupné, a to i v případě, že nepovolíte používání Windows Hello pro firmy. Další informace najdete v tématu [Identita Protection](../protect/identity-protection-windows-settings.md).

### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="new-permissions-for-assigned-group-admins------4504437-----"></a>Nová oprávnění pro přiřazené správce skupiny   <!-- 4504437   -->
Integrovaná role školního správce Intune teď má oprávnění k vytváření, čtení, aktualizaci a odstraňování (CRUD) pro spravované aplikace. Tato aktualizace znamená, že pokud jste přihlášeni jako správce skupiny v Intune for Education, můžete teď vytvářet, zobrazovat, aktualizovat a odstraňovat MDM Push Certificate iOS, tokeny MDM serveru iOS a tokeny VPP pro iOS společně se [všemi stávajícími oprávněními](https://docs.microsoft.com/intune-education/group-admin-delegate#group-admin-permissions), která máte. Chcete-li provést některou z těchto akcí, použijte **nastavení klienta** > **Správa zařízení iOS**.  

#### <a name="applications-can-use-the-graph-api-to-call-read-operations-without-user-credentials----4655885---"></a>Aplikace můžou použít Graph API k volání operací čtení bez přihlašovacích údajů uživatele. <!-- 4655885 -->
Aplikace můžou volat Intune Graph API operace čtení pomocí identity aplikace bez přihlašovacích údajů uživatele. Další informace o přístupu k rozhraní Microsoft Graph API pro Intune najdete [v tématu práce s Intune v Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="apply-scope-tags-to-microsoft-store-for-business-apps----4392555---"></a>Použití značek oboru na Microsoft Store pro obchodní aplikace <!-- 4392555 -->
Pro Microsoft Store pro obchodní aplikace teď můžete použít značky oboru. Další informace o značkách oboru najdete v tématu [použití řízení přístupu na základě role (RBAC) a značek oboru pro distribuci](scope-tags.md).

## <a name="week-of-june-17-2019"></a>Týden od 17. června 2019 

### <a name="app-management"></a>Správa aplikací

#### <a name="new-features-in-microsoft-intune-app"></a>Nové funkce v aplikaci Microsoft Intune App
Přidali jsme nové funkce do aplikace Microsoft Intune (Preview) pro Android. Uživatelé na plně spravovaných zařízeních s Androidem teď můžou:  

* Umožňuje zobrazit a spravovat zařízení, která zaregistrovali prostřednictvím aplikace Portál společnosti Intune nebo Microsoft Intune.    
* Pro podporu se obraťte na svou organizaci.    
* Poslat svůj názor Microsoftu.    
* Zobrazit podmínky a ujednání, pokud je nastavila jejich organizace.    

## <a name="week-of-june-10-2019"></a>Týden od 10. června 2019 

### <a name="app-management"></a>Správa aplikací

#### <a name="new-sample-apps-showing-intune-sdk-integration-available-on-github----2653471---"></a>Nové ukázkové aplikace ukazující integraci sady Intune SDK dostupnou na GitHubu <!-- 2653471 -->
Účet GitHub msintuneappsdk přidal nové ukázkové aplikace pro iOS (SWIFT), Android, Xamarin. iOS, Xamarin Forms a Xamarin. Android. Tyto aplikace jsou určeny k doplnění naší stávající dokumentace a poskytnutí ukázek, jak integrovat sadu Intune APP SDK do vašich vlastních mobilních aplikací. Pokud jste vývojář aplikací, který potřebuje další pokyny pro sadu Intune SDK, přečtěte si následující propojené ukázky:
- [Chat](https://github.com/msintuneappsdk/Chatr-Sample-Intune-iOS-App) – nativní aplikace pro zasílání rychlých zpráv pro iOS (SWIFT), která pro zprostředkované ověřování používá službu Azure Active Directory Authentication Library (ADAL).
- [Tasker](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App) – nativní aplikace seznamu úkolů pro Android, která používá ADAL pro zprostředkované ověřování.
- [Tasker](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps) – aplikace seznamu úkolů Xamarin. Android, která používá ADAL pro zprostředkované ověřování, toto úložiště má také aplikaci Xamarin. Forms.
- [Ukázková aplikace Xamarin. iOS](https://github.com/msintuneappsdk/sample-intune-xamarin-ios) – ukázková aplikace Barebones Xamarin. iOS

## <a name="week-of-may-27-2019"></a>Týden od 27. května 2019 

### <a name="app-management"></a>Správa aplikací

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices----4223162---"></a>Vytváření sestav pro potenciálně škodlivé aplikace na zařízeních s Androidem <!-- 4223162 -->
Intune teď poskytuje další informace o potenciálně škodlivých aplikacích na zařízeních s Androidem. 

## <a name="week-of-may-20-2019"></a>Týden od 20. května 2019 

### <a name="app-management"></a>Správa aplikací

#### <a name="windows-company-portal-app----3316993---"></a>Aplikace Portál společnosti pro Windows <!-- 3316993 -->
Aplikace pro Windows Portál společnosti teď bude mít novou stránku označenou jako **zařízení**. Na stránce **zařízení** se zobrazí koncoví uživatelé všechna zaregistrovaná zařízení. Uživatelům se tato změna v Portál společnosti uvidí, když používají verzi 10.3.4291.0 a novější. Informace o konfiguraci Portál společnosti naleznete v tématu [How to Configure a Microsoft Intune portál společnosti App](../apps/company-portal-app.md).

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>Název atributu KódObjednávky zařízení pro Autopilot se změnil na značku Group <!-- 4659453 -->

Aby byl název atributu **KódObjednávky** v zařízeních pro autopiloti intuitivnější, byl změněn na **značku Group**. Při použití CSV k nahrávání informací o zařízeních autopilotu je nutné použít značku skupiny jako záhlaví sloupce, nikoli ČísloObjednávky.  

## <a name="week-of-may-13-2019"></a>Týden od 13. května 2019 

### <a name="app-management"></a>Správa aplikací

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359----"></a>Zásady služby Intune aktualizují metodu ověřování a instalaci aplikace Portál společnosti.  <!-- 1927359  -->
V zařízeních, která jsou už zaregistrovaná prostřednictvím pomocníka s nastavením prostřednictvím některého z metod registrace podnikových zařízení společnosti Apple, Intune už nebude podporovat Portál společnosti, když je ručně nainstalují koncoví uživatelé z App Storu. Tato změna je relevantní jenom v případě, že při registraci ověříte pomocí Pomocníka s nastavením Apple. Tato změna také ovlivňuje jenom zařízení s iOS zaregistrovaná prostřednictvím:  
* Apple Configuratoru

* Apple Business Manager

* Apple School Manager

* Apple Program registrace zařízení (DEP)

Pokud si uživatelé nainstalují aplikaci Portál společnosti z App Storu a pokusí se je pomocí ní zaregistrovat, dostanou chybu. U těchto zařízení se očekává, že bude používat jenom Portál společnosti, když ho služba Intune po registraci automaticky dokončí. Profily registrace v Intune ve Azure Portal budou aktualizované, abyste mohli určit, jak se zařízení ověřují a jestli obdrží Portál společnosti aplikaci. Pokud chcete, aby uživatelé zařízení DEP měli Portál společnosti, budete muset zadat předvolby v registračním profilu. 

Kromě toho se odebírá obrazovka **identifikace zařízení** v iOS portál společnosti. Proto správci, kteří chtějí povolit podmíněný přístup nebo nasazovat firemní aplikace, musí aktualizovat profil zápisu DEP. Tento požadavek platí jenom v případě, že se registrace DEP ověřuje pomocí Pomocníka s nastavením. V takovém případě musíte Portál společnosti do zařízení vložit. Pokud to chcete udělat, vyberte v **Intune** > **registrace zařízení** >  registrace**Apple** > **tokeny programu registrace** > vyberte **profily > profilů** > vyberte profil > **vlastnosti** > sada **. Nainstalujte Portál společnosti** na **Ano**.

Pokud chcete Portál společnosti nainstalovat do již zaregistrovaných zařízení DEP, budete muset přejít na > klientských aplikací Intune a vložit ho jako spravovanou aplikaci se zásadami konfigurace aplikace. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy----3568384---"></a>Konfigurace způsobu, jakým koncoví uživatelé aktualizují obchodní aplikaci (LOB) pomocí zásad ochrany aplikací <!-- 3568384 -->
Teď můžete nakonfigurovat, kde můžou koncoví uživatelé získat aktualizovanou verzi obchodní aplikace (LOB). Koncovým uživatelům se tato funkce zobrazí v dialogovém okně pro podmíněné spuštění podmíněné **verze aplikace** , ve kterém se koncovým uživatelům zobrazí výzva k aktualizaci na minimální verzi aplikace LOB. Tyto podrobnosti o aktualizaci musíte zadat v rámci zásad ochrany aplikací LOB (aplikace). Tato funkce je dostupná v iOS a Androidu. V systému iOS Tato funkce vyžaduje, aby byla aplikace integrovaná (nebo zabalená pomocí nástroje pro zabalení) se sadou Intune SDK pro iOS v. 10.0.7 nebo vyšší. V Androidu by tato funkce vyžadovala nejnovější Portál společnosti. Pokud chcete nakonfigurovat, jak koncový uživatel aktualizuje obchodní aplikaci, potřebuje, aby se do ní poslala zásada konfigurace spravované aplikace s klíčem, `com.microsoft.intune.myappstore`. Hodnota odeslané bude určovat, ze kterého Storu bude koncový uživatel aplikaci stahovat. Pokud je aplikace nasazená prostřednictvím Portál společnosti, musí být hodnota `CompanyPortal`. Pro jakékoli jiné úložiště musíte zadat úplnou adresu URL.

#### <a name="intune-management-extension-powershell-scripts-----3734186----"></a>Skripty PowerShellu pro rozšíření správy Intune  <!-- 3734186  -->
Skripty PowerShellu můžete nakonfigurovat tak, aby se spouštěly s oprávněními správce uživatele v zařízení. Další informace najdete v tématu [použití skriptů PowerShellu na zařízeních s Windows 10 v Intune a ve](../apps/intune-management-extension.md) [správě aplikací Win32](../apps/app-management.md).

#### <a name="android-enterprise-app-management----4459905---"></a>Správa firemních aplikací pro Android <!-- 4459905 -->
Aby správci IT usnadnili konfiguraci a používání správy Android Enterprise managementu, Intune do konzoly pro správu Intune automaticky přidá čtyři běžné aplikace pro Android Enterprise. Čtyři aplikace pro Android Enterprise jsou tyto aplikace:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** – používá se pro plně spravované scénáře pro Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** – vám pomůže se přihlašovat k vašim účtům, pokud použijete dvojúrovňové ověřování.
- **[Portál společnosti Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** – používá se pro scénáře zásad ochrany aplikací (App) a Android Enterprise Work Profile.
- [Spravovaná Domovská obrazovka](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) – používá se pro scénáře podnikových scénářů nebo veřejného terminálu pro Android.

Dříve museli správci IT v rámci instalace ručně najít a schválit tyto aplikace v rámci [spravovaného Google Play Storu](https://play.google.com/store/apps) . Tato změna odstraní výše popsané kroky, aby zákazníci usnadnili používání Enterprise managementu v Androidu, aby je bylo snazší a rychlejší.

Správci uvidí tyto čtyři aplikace automaticky přidané do jejich seznamu aplikací Intune v době, kdy poprvé připojí svého tenanta Intune ke spravovaným Google Play. Další informace najdete v tématu [připojení účtu Intune ke spravovanému účtu Google Play](../enrollment/connect-intune-android-enterprise.md). Pro klienty, kteří už připojili svého tenanta nebo kteří už používají Android Enterprise, nemusíte dělat žádné správce. Tyto čtyři aplikace se automaticky zobrazí do 7 dnů od dokončení zavedení služby květen 2019.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune-----1533038---"></a>Aktualizovaný konektor certifikátu PFX pro Microsoft Intune  <!-- 1533038 -->
Vydali jsme aktualizaci [konektoru PFX Certificate Connector pro Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors) , která řeší problém, kdy se stávající certifikáty PFX budou dál zpracovávat, což způsobí, že konektor přestane zpracovávat nové požadavky.

#### <a name="intune-security-tasks-for-defender-atp-in-public-preview--------3208597---"></a>Úkoly zabezpečení Intune pro program Defender ATP (ve verzi Public Preview)     <!-- 3208597 -->
Ve verzi Public Preview můžete pomocí Intune spravovat [úlohy zabezpečení pro Microsoft Defender Advanced Threat Protection (ATP)](../protect/atp-manage-vulnerabilities.md). Tato integrace s ATP a přináší přístup založený na riziku pro zjišťování, stanovení priorit a nápravu chyb zabezpečení koncových bodů a chybných konfigurací a zároveň zkracuje dobu mezi zjišťováním a omezením jejich zmírnění.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---idstaged--"></a>Zjištění sady čipů TPM v zásadách dodržování předpisů pro zařízení s Windows 10 <!-- 3617671   idstaged-->
Mnoho zařízení s Windows 10 a novějším má čipové sady TPM (Trusted Platform Module). Tato aktualizace obsahuje nové nastavení dodržování předpisů, které kontroluje verzi čipu TPM v zařízení. 

Toto nastavení popisuje [nastavení zásad dodržování předpisů pro Windows 10 a novější](../protect/compliance-policy-create-windows.md#device-security) .

Platí pro: Windows 10 a novější

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices----4097904-----"></a>Zabránit koncovým uživatelům v úpravách jejich osobního HotSpotu a zakázat přihlašování Siri serveru na zařízeních s iOS <!-- 4097904   -->  
Vytvoříte profil omezení zařízení na zařízení s iOS (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro > **omezení zařízení** pro typ profilu). Tato aktualizace obsahuje nová nastavení, která můžete nakonfigurovat:

- **Integrované aplikace**: protokolování na straně serveru pro příkazy Siri
- **Bezdrátové**: Změna uživatele osobní hotspotu (jenom pod dohledem)

Tato nastavení zobrazíte tak, že přejdete na [integrovaná nastavení aplikace pro iOS](../configuration/device-restrictions-ios.md#built-in-apps) a [nastavení bezdrátové sítě pro iOS](../configuration/device-restrictions-ios.md#wireless).

Platí pro: iOS 12,2 a novější

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices----4097905-----"></a>Nová nastavení omezení pro zařízení macOS v aplikaci učeben <!-- 4097905   --> 
Můžete vytvořit profily konfigurace zařízení pro zařízení macOS (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **MacOS** pro **omezení** platformy > pro typ profilu). Tato aktualizace zahrnuje nová nastavení aplikace učebny, možnost blokovat snímky obrazovky a možnost zakázat knihovnu fotografií iCloud.

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení MacOS a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-macos.md).

Platí pro: macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>Heslo pro iOS pro přístup k nastavení obchodu s aplikacemi se přejmenuje.<!-- 4557891  -->
**Heslo pro přístup k nastavení obchodu s aplikacemi** je přejmenované na **vyžadovat heslo pro úložiště iTunes pro všechny nákupy** (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro platformu > **Omezení zařízení** pro typ profilu > **App Storu, zobrazení dokumentů a hraní her**).

Dostupná nastavení zobrazíte tak, že přejdete do [App Storu, zobrazení dokumentů a herního nastavení iOS](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Platí pro: iOS

#### <a name="microsoft-defender-advanced-threat-protection--baseline--preview------3754134---"></a>Směrný plán Microsoft Defender Advanced Threat Protection (Preview)  <!--  3754134 -->
Přidali jsme náhled základní úrovně zabezpečení pro nastavení [rozšířené ochrany před internetovými útoky v programu Microsoft Defender](../protect/security-baseline-settings-defender-atp.md) . Tato standardní hodnota je dostupná, když vaše prostředí splňuje požadavky na používání [rozšířené ochrany před internetovými útoky v programu Microsoft Defender](../protect/advanced-threat-protection.md#prerequisites).

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available----3605348---"></a>Stránka stavu registrace systému Windows (ESP) je nyní obecně dostupná. <!-- 3605348 -->
Stránka stavu registrace je nyní mimo verzi Preview. Další informace najdete v tématu [nastavení stránky stavu registrace](../enrollment/windows-enrollment-status.md).


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation-----4593669---"></a>Aktualizace uživatelského rozhraní Intune – vytvoření profilu registrace autopilotu  <!-- 4593669 -->
Uživatelské rozhraní pro vytvoření profilu registrace autopilotu se aktualizovalo tak, aby bylo zarovnané na styly uživatelského rozhraní Azure. Další informace najdete v tématu [Vytvoření profilu registrace autopilotu](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile). Další scénáře Intune se budou aktualizovat na tento nový styl uživatelského rozhraní.

#### <a name="enable-autopilot-reset-for-all-windows-devices----4225665---"></a>Povolit resetování autopilotu pro všechna zařízení s Windows <!-- 4225665 -->
Automatické vynulování pilotního nasazení teď funguje pro všechna zařízení s Windows, i když nejsou nakonfigurovaná na použití stránky stavu registrace. Pokud se stránka stavu registrace pro zařízení nenakonfigurovala při počáteční registraci zařízení, bude po přihlášení zařízení po přihlášení přímo na plochu. Synchronizace a zobrazení kompatibility v Intune může trvat až osm hodin. Další informace najdete v tématu [resetování zařízení pomocí vzdálené správy Windows autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote).

#### <a name="exact-imei-format-not-required-when-searching-all-devices---30407680---"></a>Při hledání všech zařízení se nevyžaduje přesný formát IMEI. <!--30407680 -->
Při hledání **všech zařízení**nebudete muset vkládat mezery do čísel IMEI.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Odstranění zařízení na portálu Apple se projeví na portálu Intune. <!--2489996 -->
Pokud se zařízení odstraní z portálu od společnosti Apple Program registrace zařízení nebo z portálu Apple Business Manager, zařízení se během další synchronizace automaticky odstraní z Intune.

### <a name="the-enrollment-status-page-now-tracks-win32-apps----2714451---"></a>Stránka stavu registrace teď sleduje aplikace Win32. <!-- 2714451 -->
To platí jenom pro zařízení s Windows 10 verze 1903 a novější. Další informace najdete v tématu [nastavení stránky stavu registrace](../enrollment/windows-enrollment-status.md).

### <a name="device-management"></a>Správa zařízení

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Hromadné resetování a vymazání zařízení pomocí Graph API <!-- 3295288 -->
Při hromadném obnovení a vymazání zařízení 100 můžete použít Graph API.


### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="the-encryption-report-is-out-of-public-preview------4587546--------"></a>Zpráva o šifrování není Public Preview.   <!-- 4587546      -->
[Sestava pro šifrování nástrojem BitLocker a zařízení](../protect/encryption-monitor.md) je nyní všeobecně dostupná a již není součástí verze Public Preview. 

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices----4050557---"></a>Podpis Outlooku a biometrické nastavení pro zařízení s iOS a Androidem <!-- 4050557 -->
Teď můžete určit, jestli je výchozí podpis povolený v Outlooku na zařízeních s iOS a Androidem. Kromě toho můžete zvolit, aby uživatelé mohli měnit nastavení biometriky v Outlooku v iOS.

## <a name="week-of-may-6-2019"></a>Týden od 6. května 2019 

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices----4500808---"></a>Podpora NAC (Network Access Control) pro přístup F5 pro zařízení s iOS <!-- 4500808 -->

F5 vydala aktualizaci BIG-IP 13, která umožňuje funkci NAC pro přístup F5 v systému iOS v Intune. Chcete-li použít tuto funkci:

- Aktualizujte BIG-IP na 13.1.1.5 Refresh. BIG-IP 14 se nepodporuje.
- Integrujte BIG-IP s Intune for NAC. Postup v článku [Přehled: Konfigurace APM pro zařízení stav kontrol pomocí systémů správy koncových bodů](https://techdocs.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html).
- Zaškrtněte nastavení **povolit Access Control sítě (NAC)** v profilu sítě VPN v Intune.

Dostupná nastavení zobrazíte tak, že přejdete na [Konfigurace nastavení sítě VPN na zařízeních s iOS](../configuration/vpn-settings-ios.md).

Platí pro: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune----doc-vso-1521237----"></a>Aktualizovaný konektor certifikátu PFX pro Microsoft Intune <!-- doc-vso 1521237  -->  
Vydali jsme aktualizaci [konektoru certifikátů PFX pro Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors) , který předává interval dotazování od 5 minut do 30 sekund.

## <a name="week-of-april-22-2019"></a>Týden od 22. dubna 2019

### <a name="use-compliance-manager-to-create-assessments-for-microsoft-intune---4404750---"></a>Použití Správce dodržování předpisů k vytváření posouzení pro Microsoft Intune<!-- 4404750 -->

[Správce dodržování předpisů](https://servicetrust.microsoft.com/ComplianceManager) (otevře další web společnosti Microsoft) je nástroj pro vyhodnocení rizik na základě pracovního postupu na portálu Microsoft Trust Service. Umožňuje sledovat, přiřazovat a ověřovat aktivity dodržování předpisů právními předpisy vaší organizace týkající se služeb Microsoftu. Můžete si vytvořit vlastní posouzení dodržování předpisů pomocí služeb Office 365, Azure, Dynamics, Professional Services a Intune. V Intune jsou k dispozici dvě posouzení – FFIEC a GDPR.

Správce dodržování předpisů vám pomůže zaměřit se na vaše úsilí tím, že rozbalí ovládací prvky spravované společností Microsoft a řídí ovládací prvky spravované vaší organizací. Posouzení můžete dokončit a pak vyexportovat a vytisknout posouzení.

[Rada pro posuzování federálních finančních institucí (FFIEC)](https://www.microsoft.com/trustcenter/compliance/FFIEC) (otevírá jiný web společnosti Microsoft) je sada standardů pro online bankovnictví vydaná FFIEC. Je to nejvíce požadované posouzení finančních institucí, které používají Intune. Interpretuje, jak Intune pomáhá splňovat FFIEC kyberbezpečnosti pokyny týkající se úloh veřejných cloudů. Posuzování FFIEC služby Intune je druhé hodnocení FFIEC ve Správci dodržování předpisů.

V následujícím příkladu vidíte rozpis pro ovládací prvky FFIEC. Microsoft pokrývá ovládací prvky 64. Zodpovídáte za zbývající 12 kontrol.

![Podívejte se na ukázku posouzení Intune pro FFIEC, včetně akcí zákazníků a akcí Microsoftu.](./media/whats-new/intune-ffiec-assessment-status.png)

[Obecné nařízení o ochraně osobních údajů (GDPR)](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-overview) (otevře další web společnosti Microsoft) je právní právo Evropské unie (EU), které pomáhá chránit práva jednotlivců a jejich dat. GDPR je nejužitečnější hodnocení, které je užitečné při dodržování předpisů týkajících se ochrany osobních údajů. 

V následujícím příkladu vidíte rozpis pro ovládací prvky GDPR. Microsoft pokrývá ovládací prvky 49. Zodpovídáte za zbývající ovládací prvky 66.

![Podívejte se na ukázku posouzení Intune pro GDPR, včetně akcí zákazníků a akcí Microsoftu.](./media/whats-new/intune-assessment-status.png)

## <a name="week-of-april-15-2019"></a>Týden od 15. dubna 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="openssl-encryption-for-android-app-protection-policies----3747362---"></a>OpenSSL šifrování pro zásady ochrany aplikací pro Android <!-- 3747362 -->
Zásady ochrany aplikací Intune (aplikace) na zařízeních s Androidem teď používají knihovnu šifrování OpenSSL, která je kompatibilní se standardem FIPS 140-2. Další informace najdete v části [šifrování](../apps/app-protection-policy-settings-android.md#encryption) [v tématu Nastavení zásad ochrany aplikací pro Android v Microsoft Intune](../apps/app-protection-policy-settings-android.md).

#### <a name="enable-win32-app-dependencies----2617348----"></a>Povolit závislosti aplikací Win32 <!-- 2617348  -->
Jako správce můžete vyžadovat, aby byly před instalací aplikace Win32 nainstalovány jako závislosti jiné aplikace. Konkrétně musí zařízení před instalací aplikace Win32 nainstalovat závislé aplikace. V Intune vyberte **klientské aplikace** > **aplikace** > **Přidat** , aby se zobrazilo okno **Přidat aplikaci** . Jako **Typ aplikace**vyberte **aplikace pro Windows (Win32)** . Po přidání aplikace můžete vybrat **závislosti** a přidat tak závislé aplikace, které musí být nainstalovány, než bude možné nainstalovat aplikaci Win32. Další informace najdete v tématu [samostatná verze Intune – Správa aplikací Win32](./../apps/app-management.md). 

#### <a name="app-version-installation-information-for-microsoft-store-for-business-apps----3537391-----"></a>Informace o instalaci verze aplikace pro aplikace Microsoft Store for Business <!-- 3537391   -->
Sestavy instalace aplikací obsahují informace o verzi aplikace Microsoft Store pro obchodní aplikace. V Intune vyberte **klientské aplikace** > **aplikace**. Vyberte **aplikaci Microsoft Store pro firmy** a potom v části **monitorování** vyberte **stav instalace zařízení** .

#### <a name="additions-to-win32-apps-requirement-rules----3676883-----"></a>Přidání pravidel požadavků pro aplikace Win32 <!-- 3676883   -->
Pravidla požadavků můžete vytvořit na základě PowerShellových skriptů, hodnot registru a informací o systému souborů. V Intune vyberte **klientské aplikace** > **aplikace** > **Přidat**. Pak jako **Typ aplikace** v okně **Přidat aplikaci** vyberte **aplikace pro Windows (Win32)** .  Vyberte **požadavky** > **Přidat** a nakonfigurujte další pravidla požadavků. Pak jako **typ požadavku**vyberte buď **typ souboru**, **registr**, nebo **skript** . Další informace najdete v tématu [Správa aplikací Win32](./../apps/app-management.md).

#### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227----"></a>Konfigurace aplikací Win32, které se mají nainstalovat na zařízení připojená k Azure AD zaregistrovaným v Intune <!-- 3695227  -->
Můžete přiřadit aplikace Win32, které se mají nainstalovat do zaregistrovaných zařízení připojených k Azure AD v Intune. Další informace o aplikacích Win32 v Intune najdete v tématu [Správa aplikací Win32](./../apps/app-management.md).

#### <a name="device-overview-shows-primary-user---3794259----"></a>Přehled zařízení zobrazuje primárního uživatele <!--3794259  -->
Na stránce s přehledem zařízení se zobrazí primární uživatel, který se taky označuje jako uživatel spřažení zařízení a uživatele (UDA). Pokud chcete zobrazit primárního uživatele pro zařízení, vyberte zařízení  >  **Intune**  > **všechna zařízení** >**zvolit zařízení.** Primární uživatel se zobrazí v horní části stránky s **přehledem** .

#### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925----"></a>Další spravované Google Play vytváření sestav aplikací pro zařízení s Androidem Enterprise Work Profile <!-- 4105925  -->
U spravovaných aplikací Google Play nasazených do zařízení se systémem Android Enterprise Work profilů můžete zobrazit konkrétní číslo verze aplikace nainstalované na zařízení. To platí jenom pro požadované aplikace.  

#### <a name="ios-third-party-keyboards----4111843-----"></a>Klávesnice třetích stran iOS <!-- 4111843   -->
Podpora zásad ochrany aplikací Intune pro nastavení **klávesnice třetích stran** pro iOS už není podporovaná kvůli změně platformy iOS. Toto nastavení nebudete moct konfigurovat v konzole pro správu Intune a na klientovi se v sadě Intune App SDK neuplatní.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083----"></a>Nastavení přihlašovacích nastavení a řízení možností restartování na zařízeních macOS <!-- 1210083  -->
Na zařízeních macOS můžete vytvořit konfigurační profil zařízení (**Konfigurace zařízení** > **profily** > **vytvořit profil** > zvolit **MacOS** pro **funkce zařízení** > pro typ profilu). Tato aktualizace zahrnuje nové nastavení přihlašovacího okna, jako je například zobrazení vlastního nápisu, výběr způsobu přihlášení uživatelů, zobrazení nebo skrytí nastavení napájení a další.

Pokud se chcete podívat na tato nastavení, přejděte na [Nastavení funkcí zařízení MacOS](../configuration/macos-device-features-settings.md).

#### <a name="configure-wifi-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode---3041940----"></a>Konfigurace Wi-Fi v Androidu Enterprise, vyhrazená zařízení vlastníka zařízení, která běží v celoobrazovkovém režimu s více aplikacemi <!--3041940  -->
V celoobrazovkovém režimu s více aplikacemi můžete povolit nastavení v systému Android Enterprise a vlastníka zařízení v případě, že běží jako vyhrazené zařízení. V této aktualizaci můžete uživatelům povolit konfiguraci a připojení k sítím Wi-Fi (v**Intune** > **Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** pro platformu >  **Jenom vlastník zařízení, omezení zařízení** pro typ profilu > **vyhrazená zařízení**1**beznabídkového režimu**: konfigurace s **více aplikacemi**4**Wi-Fi**. 

Pokud chcete zobrazit všechna nastavení, která můžete nakonfigurovat, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo zakažte funkce](../configuration/device-restrictions-android-for-work.md).

Platí pro: zařízení se systémem Android Enterprise vyhrazená v celoobrazovkovém režimu s více aplikacemi


#### <a name="configure-bluetooth-and-pairing-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode----3041941----"></a>Konfigurace Bluetooth a párování v Androidu Enterprise, vyhrazená zařízení vlastníka zařízení, která běží v celoobrazovkovém režimu s více aplikacemi <!-- 3041941  -->
V celoobrazovkovém režimu s více aplikacemi můžete povolit nastavení v systému Android Enterprise a vlastníka zařízení v případě, že běží jako vyhrazené zařízení. V této aktualizaci můžete koncovým uživatelům povolit Bluetooth a spárovat zařízení přes**Bluetooth ( > ** **Konfigurace zařízení**  > **profily**  > **vytvořit profil**  > **Android Enterprise** for Platform > **jenom vlastník zařízení, omezení zařízení** pro typ profilu > **vyhrazená zařízení** 1**celoobrazovkový režim**: konfigurace s **více aplikacemi** 4**Bluetooth**). 

Pokud chcete zobrazit všechna nastavení, která můžete nakonfigurovat, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo zakažte funkce](../configuration/device-restrictions-android-for-work.md).

Platí pro: zařízení se systémem Android Enterprise vyhrazená v celoobrazovkovém režimu s více aplikacemi

#### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883----"></a>Vytvoření a použití profilů konfigurace zařízení OEMConfig v Intune <!-- 3305883  -->
V této aktualizaci Intune podporuje konfiguraci zařízení se systémem Android Enterprise pomocí OEMConfig. Konkrétně můžete vytvořit konfigurační profil zařízení a použít nastavení pro zařízení s Androidem Enterprise pomocí OEMConfig (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise.** pro platformu).

Podpora pro výrobce OEM je aktuálně založená na jednotlivých DODAVATELích. Pokud není požadovaná aplikace OEMConfig v seznamu aplikací OEMConfig dostupná, kontaktujte `IntuneOEMConfig@microsoft.com`.

Další informace o této funkci najdete [v Microsoft Intune používání a Správa zařízení se systémem Android Enterprise pomocí OEMConfig](../configuration/android-oem-configuration-overview.md).

Platí pro: Android Enterprise

#### <a name="windows-update-notifications-----3316758-3316782----"></a>Oznámení web Windows Update  <!-- 3316758, 3316782  -->
Přidali jsme dvě *Nastavení uživatelského prostředí* do konfigurací web Windows Update Ring, které můžete spravovat v konzole Intune. Teď můžete:
- Zablokuje nebo povolí uživatelům [vyhledávání aktualizací Windows](../protect/windows-update-settings.md).
- Spravujte [web Windows Update úroveň oznámení](../protect/windows-update-settings.md) , kterou uživatelé uvidí.

#### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254----"></a>Nová nastavení omezení pro zařízení s Androidem Enterprise, vlastníkem zařízení <!-- 3574254  -->
Na zařízeních s Androidem Enterprise můžete vytvořit profil omezení zařízení, abyste povolili nebo omezili funkce, nastavili pravidla hesel a další (**Konfigurace zařízení** > **profily** > **vytvořit profil** > zvolit **Android. Enterprise** pro > pro **vlastníka zařízení > jenom omezení zařízení** pro typ profilu). 

Tato aktualizace zahrnuje nastavení nového hesla, umožňuje úplný přístup k aplikacím v Obchod Google Play pro plně spravovaná zařízení a další. Pokud chcete zobrazit aktuální seznam nastavení, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo zakažte funkce](../configuration/device-restrictions-android-for-work.md). 

Platí pro: zařízení se systémem Android Enterprise s plnou správou

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Zjištění sady čipů TPM v zásadách dodržování předpisů pro zařízení s Windows 10 <!-- 3617671 -->

Tato funkce je zpožděná a plánuje se pozdější vydání.

#### <a name="updated-ui-changes-for-microsoft-edge-browser-on-windows-10-and-later-devices----3775833-----"></a>Aktualizované změny uživatelského rozhraní pro prohlížeč Microsoft Edge v zařízeních s Windows 10 a novějším <!-- 3775833   -->
Když vytváříte konfigurační profil zařízení, můžete povolit nebo zakázat funkce Microsoft Edge na zařízeních s Windows 10 a novějších (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější.** pro platformu > **omezení zařízení** pro typ profilu > **prohlížeč Microsoft Edge**). V této aktualizaci jsou nastavení Microsoft Edge výstižnější a usnadňuje pochopení. 

Tyto funkce zobrazíte tak, že přejdete na [Nastavení omezení pro zařízení v prohlížeči Microsoft Edge](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser).

Platí pro: Windows 10 a novější

#### <a name="expanded-support-for-android-enterprise-fully-managed-devices--preview-------3903241-3903244-3903246-----"></a>Rozšířená podpora pro plně spravovaná zařízení s Androidem Enterprise (Preview)  <!--   3903241, 3903244, 3903246   -->
Pořád ve veřejné verzi Preview rozšířili jsme naši podporu zařízení s plnou správou Androidu Enterprise ([poprvé oznámenou v lednu od 2019 do 1. ledna](whats-new.md#week-of-january-14-2019) ), která zahrnují následující: 

- Na plně spravovaných a vyhrazených zařízeních můžete vytvořit [zásady dodržování předpisů](../protect/compliance-policy-create-android-for-work.md) , které budou zahrnovat pravidla hesel a požadavky na operační systém (**zásady**  > **dodržování předpisů zařízením**  > **vytvořit zásadu**  > **Androidu. Enterprise** pro > **vlastníka zařízení** pro typ profilu). 

  Na vyhrazených zařízeních se může zařízení zobrazovat jako **nevyhovující**. Podmíněný přístup není k dispozici na vyhrazených zařízeních. Ujistěte se, že jste dokončili všechny úkoly nebo akce, abyste získali vyhrazená zařízení, která vyhovují vašim přiřazeným zásadám.

- [Podmíněný přístup](../protect/conditional-access.md) – zásady podmíněného přístupu, které se vztahují na Android, se vztahují také na zařízení se systémem Android Enterprise s plnou správou. Uživatelé teď můžou zaregistrovat svoje plně spravované zařízení v Azure Active Directory pomocí **Microsoft Intune aplikace**. Pak si přečtěte a vyřešte všechny problémy dodržování předpisů pro přístup k prostředkům organizace.

- Nová aplikace pro koncové uživatele (Microsoft Intune aplikace) – je k dispozici nová aplikace koncového uživatele pro zařízení s Androidem spravovaná s názvem **Microsoft Intune**. Tato nová aplikace je lehká a moderní a poskytuje podobné funkce jako aplikace Portál společnosti, ale pro plně spravovaná zařízení. Další informace najdete v tématu [Microsoft Intune aplikace na Google Play](https://play.google.com/store/apps/details?id=com.microsoft.intune).

Pokud chcete nastavit zařízení s plnou správou Androidu, přečtěte si **registrace zařízení** >  registrace zařízení s**Androidem** > **ve vlastnictví podnikových a plně spravovaných uživatelských zařízení**. Podpora plně spravovaných zařízení s Androidem zůstává ve verzi Preview a některé funkce Intune nemusí být plně funkční.  

Další informace o této verzi Preview najdete v našem blogu [Microsoft Intune-Preview 2 pro zařízení s plnou správou Android Enterprise](https://aka.ms/preview2_AE_fullymanaged).


### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470----"></a>Nakonfigurovat profil pro přeskočení některých obrazovek během Průvodce nastavením <!-- 2276470  -->
Když vytváříte profil registrace macOS, můžete ho nakonfigurovat tak, aby po absolvování Průvodce nastavením přeskočil kteroukoli z následujících obrazovek:
- Příznaky
- Tón zobrazení
- iCloudStorage Pokud vytvoříte nový profil nebo upravíte profil, je nutné, aby se vybrané přeskočené obrazovky synchronizovaly se serverem Apple MDM.  Uživatelé můžou vydat ruční synchronizaci zařízení, aby při vybírání změn profilu nedocházelo k žádnému zpoždění.
Další informace najdete v tématu [Automatická registrace zařízení MacOS pomocí program registrace zařízení nebo Apple School Manageru](../enrollment/device-enrollment-program-enroll-macos.md).

#### <a name="bulk-device-naming-when-enrolling-corporate-ios-devices--3566569----"></a>Při registraci firemních zařízení s iOS se hromadně pojmenování zařízení<!--3566569  -->
Pokud používáte jednu z podnikových metod registrace společnosti Apple (DEP/ABM/ASM), můžete nastavit formát názvu zařízení tak, aby automaticky pojmenovaná příchozí zařízení s iOS. V šabloně můžete zadat formát, který zahrnuje typ zařízení a sériové číslo. Provedete to tak, že zvolíte **Intune** > **registrace zařízení** >  registrace**Apple** > **tokeny programu registrace** > **Vyberte token** >**vytvořit profil**1**pojmenování zařízení. Formát**: Můžete upravovat stávající profily, ale název se použije jenom u nově synchronizovaných zařízení.

#### <a name="updated-default-timeout-message-on-enrollment-status-page----3959331---"></a>Aktualizovaná výchozí zpráva s časovým limitem na stránce stavu registrace <!-- 3959331 -->
Aktualizovali jsme výchozí zprávu s časovým limitem, kterou uživatelé uvidí, když stránka stavu registrace (ESP) překračuje hodnotu časového limitu zadanou v profilu ESP. Nová výchozí zpráva se uživatelům zobrazí a pomůže jim pochopit další akce, které je potřeba provést s nasazením ESP.  

### <a name="device-management"></a>Správa zařízení

#### <a name="retire-noncompliant-devices-----1827291-----"></a>Vyřazení zařízení nesplňujících požadavky  <!-- 1827291   -->
Tato funkce byla zpožděna a plánuje se pro budoucí verzi.


### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="intune-data-warehouse-v10-changes-reflecting-back-to-beta----4403765---"></a>Změny V datovém skladu Intune V 1.0 odrážející zpátky do beta verze <!-- 4403765 -->
V případě, že verze 1.0 byla poprvé představena v 1808, liší se v několika významných způsobech z verze beta rozhraní API. V 1903 se tyto změny projeví zpátky v beta verzi rozhraní API. Pokud máte důležité sestavy, které používají verzi beta rozhraní API, důrazně doporučujeme, abyste tyto sestavy přepnuli na V 1.0, aby nedocházelo k nepodstatným změnám. Další informace najdete v tématu [protokol změn pro rozhraní API datového skladu Intune](../developer/reports-changelog.md#1903-part-2).

#### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Monitorovat stav standardních hodnot zabezpečení (Public Preview) <!-- 3082047 --> 
Přidali jsme zobrazení pro [jednotlivé kategorie](../protect/security-baselines-monitor.md#per-category-view) do monitorování standardních hodnot zabezpečení. (Standardní hodnoty zabezpečení zůstávají ve verzi Preview.) Zobrazení podle kategorií zobrazuje každou kategorii ze směrného plánu společně s procentem zařízení, která spadají do každé skupiny stavů pro danou kategorii. Teď můžete zjistit, kolik zařízení se neshoduje s jednotlivými kategoriemi, jsou nesprávně nakonfigurované nebo se nedají použít.

### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="scope-tags-for-apple-vpp-tokens---2371886----"></a>Značky oboru pro tokeny programu Apple VPP <!--2371886  -->
Nyní můžete přidat značky oboru do tokenů programu Apple VPP. K tokenu Apple VPP s touto značkou budou mít přístup jenom uživatelé přiřazení se stejnou značkou Scope. Aplikace VPP a e-knihy zakoupené s tímto tokenem zdědí značky oboru. Další informace o značkách oboru najdete v tématu [použití značek RBAC a Scope](scope-tags.md).







## <a name="week-of-april-1-2019"></a>Týden od 1. dubna 2019

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="updated-certificate-connectors-----icm-113304612---"></a>Aktualizované konektory certifikátů  <!-- ICM 113304612 -->
Pro Microsoft Intune jsme vydali aktualizace pro [Intune Certificate Connector i pro Certificate connectory PFX](../protect/certficates-pfx-configure.md#whats-new-for-connectors). Nové verze opraví několik známých problémů.  

### <a name="app-management"></a>Správa aplikací

#### <a name="user-experience-update-for-the-company-portal-app-for-ios----2536024---"></a>Aktualizace uživatelského prostředí pro aplikaci Portál společnosti pro iOS <!-- 2536024 -->
Změnila se Domovská stránka aplikace Portál společnosti pro zařízení s iOS. Tato změna způsobí, že se Domovská stránka bude lépe řídit vzorci uživatelského rozhraní iOS a zároveň poskytuje vylepšenou zjistitelnost pro aplikace a e-knihy.

#### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Změny registrace Portál společnosti pro uživatele zařízení s iOS 12 <!--3448635 -->  
Portál společnosti na obrazovkách a krocích pro registraci zařízení s iOS byly aktualizovány aktualizace pro změny v registraci MDM vydané v Apple iOS 12,2. Aktualizovaný pracovní postup vyzve uživatele k zadání těchto akcí:  

* Umožněte prohlížeči Safari otevřít web Portál společnosti a před návratem do aplikace Portál společnosti stáhnout profil pro správu.  
* Otevřete aplikaci nastavení a nainstalujte na jejich zařízení profil správy.
* Vraťte se do aplikace Portál společnosti, abyste mohli dokončit registraci.  

Aktualizované kroky a obrazovky registrace najdete v tématu [registrace zařízení se systémem iOS v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).  

## <a name="week-of-march-25-2019"></a>Týden od 25. března 2019

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

### <a name="support-for-the-power-bi-compliance-app-from-the-data-warehouse-blade-in-microsoft-intune----4260871---"></a>Podpora aplikace Power BI dodržování předpisů z okna datového skladu v Microsoft Intune <!-- 4260871 -->
Dříve se odkaz **stáhnout Power BI soubor** v okně **datového skladu Intune** stáhl do sestavy datového skladu Intune (soubor. pbix). Tato sestava byla nahrazena aplikací Power BI dodržování předpisů. Aplikace Power BI dodržování předpisů nebude vyžadovat zvláštní načítání nebo instalaci. Otevře se přímo na online portálu Power BI a zobrazí data speciálně pro vašeho tenanta Intune na základě vašich přihlašovacích údajů. V Intune vyberte odkaz **nastavit datový sklad Intune** na pravé straně okna Intune. Pak klikněte na **získat Power BI aplikaci**. Další informace najdete v tématu [připojení k datovému skladu pomocí Power BI](../developer/reports-proc-get-a-link-powerbi.md).

## <a name="week-of-march-18-2019"></a>Týden od 18. března 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="deploy-microsoft-visio-and-microsoft-project----3725386----"></a>Nasazení aplikace Microsoft Visio a aplikace Microsoft Project <!-- 3725386  -->
V případě, že vlastníte licence pro tyto aplikace, teď můžete nasadit Microsoft Visio pro pro Office 365 a desktopový klient Microsoft Project Online jako nezávislé aplikace na zařízení s Windows 10 pomocí Microsoft Intune. V Intune vyberte **klientské aplikace** > **aplikace** > **Přidat** , aby se zobrazilo okno **Přidat aplikaci** . V okně **Přidat aplikaci** vyberte jako **Typ aplikace**možnost **Windows 10** . Pak vyberte **Konfigurovat sadu aplikací** a vyberte aplikace, které chcete nainstalovat. Další informace o aplikacích Office 365 pro zařízení s Windows 10 najdete v článku [přiřazení aplikací office 365 k zařízením s Windows 10 pomocí Microsoft Intune](../apps/apps-add-office365.md).

#### <a name="microsoft-visio-pro-for-office-365-product-name-change----3593653----"></a>Změna názvu produktu Microsoft Visio pro pro Office 365 <!-- 3593653  -->
**Microsoft Visio pro for Office 365** se teď označuje jako **Microsoft Visio Online Plan 2**.  Další informace o aplikaci Microsoft Visio najdete v tématu [plán 2 pro Visio online](https://products.office.com/visio/visio-online-plan-2). Další informace o aplikacích Office 365 pro zařízení s Windows 10 najdete v článku [přiřazení aplikací office 365 k zařízením s Windows 10 pomocí Microsoft Intune](../apps/apps-add-office365.md).

#### <a name="intune-app-protection-policy-app-character-limit-setting----3291302----"></a>Nastavení limitu počtu znaků v zásadách ochrany aplikací Intune (APP) <!-- 3291302  -->
Správci Intune můžou zadat výjimku pro aplikaci Intune omezit nastavení zásad **vyjmutí, kopírování a vložení s jinými aplikacemi** .  Jako správce můžete zadat počet znaků, které mohou být vyjmuty nebo zkopírovány ze spravované aplikace. Toto nastavení umožní sdílet zadaný počet znaků do libovolné aplikace bez ohledu na nastavení omezit vyjmutí, kopírování a vložení s jinými aplikacemi. Všimněte si, že verze Portál společnosti Intune aplikace pro Android vyžaduje verzi 5.0.4364.0 nebo novější. Další informace najdete v tématech [Ochrana dat iOS](../apps/app-protection-policy-settings-ios.md#data-protection), [Ochrana dat Android](../apps/app-protection-policy-settings-android.md#data-protection)a [Kontrola protokolů ochrany klientských aplikací](../apps/app-protection-policy-settings-log.md#app-protection-policy-settings).

#### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477-----"></a>Office Deployment Tool (ODT) XML pro nasazení Office ProPlus <!-- 3192477   -->
Při vytváření instance Office pro plus v konzole pro správu Intune budete moct zadat XML nástroje pro nasazení Office (ODT). To umožní větší úpravou, pokud existující možnosti uživatelského rozhraní Intune nevyhovují vašim potřebám. Další informace najdete v tématu [přiřazení aplikací Office 365 k zařízením s Windows 10 pomocí Microsoft Intune](../apps/apps-add-office365.md) a [možností konfigurace pro nástroj pro nasazení Office](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool).

#### <a name="app-icons-will-now-be-displayed-with-an-automatically-generated-background----1429026----"></a>Ikony aplikací se nyní zobrazí s automaticky generovaným pozadím <!-- 1429026  -->
V aplikaci pro Windows Portál společnosti se teď ikony aplikací zobrazí s automaticky generovaným pozadím na základě dominantní barvy ikony (Pokud se dá detekovat). V případě potřeby bude toto pozadí nahrazovat šedé ohraničení, které bylo dříve viditelné na dlaždicích aplikace. Uživatelům se tato změna projeví ve verzích Portál společnosti novějších než 10.3.3451.0.

#### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523-----"></a>Instalace dostupných aplikací pomocí aplikace Portál společnosti po hromadné registraci Windows <!-- 2751523   -->
Zařízení s Windows, která jsou registrovaná v Intune pomocí [hromadné registrace Windows](../enrollment/windows-bulk-enroll.md) (zřizovací balíčky), budou moct používat aplikaci Portál společnosti k instalaci dostupných aplikací. Další informace o aplikaci Portál společnosti najdete v tématu [Ruční přidání portál společnosti Windows 10](../apps/store-apps-company-portal-app.md) a [postup konfigurace aplikace Microsoft Intune portál společnosti](../apps/company-portal-app.md).

#### <a name="the-microsoft-teams-app-can-be-selected-as-part-of-the-office-app-suite----3828932----"></a>Aplikace Microsoft Teams se dá vybrat jako součást sady Office App Suite. <!-- 3828932  -->
Aplikace Microsoft Teams se dá zahrnout nebo vyloučit jako součást instalace sady Office pro plus a sady aplikací. Tato funkce funguje pro sadu Office pro plus číslo buildu 16.0.11328.20116 +. Uživatel se musí odhlásit a pak přihlásit k zařízení, aby se instalace dokončila. V Intune vyberte **klientské aplikace** > **aplikace** > **Přidat**. Vyberte jednu z typů aplikace **sady Office 365** a potom vyberte možnost **Konfigurovat sadu aplikací**.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="automatically-start-an-app-when-running-multiple-apps-in-kiosk-mode-on-windows-10-and-later-devices----2351390---"></a>Automatické spuštění aplikace při spuštění více aplikací v celoobrazovkovém režimu na zařízeních s Windows 10 a novějším <!-- 2351390 -->

V zařízeních se systémem Windows 10 a novějším můžete spustit zařízení v celoobrazovkovém režimu a spustit spoustu aplikací. V této aktualizaci existuje nastavení automatického **spuštění** (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější** **pro > Platform** pro typ profilu >  **Veřejný terminál s více aplikacemi**. Toto nastavení slouží k automatickému spuštění aplikace, když se uživatel přihlásí k zařízení.

Pokud chcete zobrazit seznam a popis všech nastavení veřejného terminálu, přečtěte si téma [nastavení zařízení s Windows 10 a novějším, která se mají spustit jako veřejný terminál v Intune](../configuration/kiosk-settings-windows.md).

Platí pro: Windows 10 a novější

#### <a name="operational-logs-also-show-details-on-non-compliant-devices----4063755----"></a>Provozní protokoly také zobrazují podrobnosti o nevyhovujících zařízeních. <!-- 4063755  -->
Při směrování protokolů Intune do funkce Azure monitor můžete také směrovat provozní protokoly. V této aktualizaci poskytují provozní protokoly také informace o zařízeních, která nedodržují předpisy. 

Další informace o této funkci najdete v tématu [odeslání dat protokolu do úložiště, centra událostí nebo Log Analytics v Intune](../review-logs-using-azure-monitor.md).

#### <a name="route-logs-to-azure-monitor-in-more-intune-workloads----3804627---"></a>Směrování protokolů pro Azure Monitor v dalších úlohách Intune <!-- 3804627 -->
V Intune můžete směrovat audit a provozní protokoly na centra událostí, úložiště a Log Analytics v Azure Monitor (**Intune**  > **monitorování** **nastavení diagnostiky** > ). V této aktualizaci můžete tyto protokoly směrovat ve více úlohách Intune, včetně dodržování předpisů, konfigurací, klientských aplikací a dalších. 

Další informace o protokolech směrování a Azure Monitor najdete v tématu [posílání dat protokolu do úložiště, centra událostí nebo Log Analytics](../review-logs-using-azure-monitor.md).

#### <a name="create-and-use-mobility-extensions-on-android-zebra-devices-in-intune----3305880-----"></a>Vytváření a používání rozšíření mobility na zařízeních s Androidem Zebra v Intune <!-- 3305880   -->
V této aktualizaci podporuje Intune konfiguraci zařízení se systémem Android zebra. Konkrétně můžete vytvořit profil konfigurace zařízení a použít nastavení pro zařízení s Androidem Zebra pomocí profilů mobility (mobility) vygenerovaných StageNow (**Konfigurace zařízení** > **profily** > **vytvořit profil**  > **Android** for Platform > **MX Profile (jenom Zebra)** pro typ profilu).

Další informace o této funkci najdete v tématu [používání a Správa zařízení Zebra s rozšířeními mobility v Intune](../configuration/android-zebra-mx-overview.md).

Platí pro: Android

### <a name="device-management"></a>Správa zařízení

#### <a name="encryption-report-for-windows-10-devices-in-public-preview---2351538---"></a>Sestava šifrování pro zařízení s Windows 10 (ve verzi Public Preview)<!-- 2351538 -->  
Chcete-li zobrazit podrobnosti o stavu šifrování zařízení s Windows 10, použijte novou [sestavu šifrování (Preview)](../protect/encryption-monitor.md) . K dispozici jsou podrobnosti o zařízeních, verzi TPM, připravenosti na šifrování a stavu, zasílání zpráv o chybách a dalších.  

#### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-in-public-preview----2351547-----"></a>Přístup k obnovovacím klíčům BitLockeru z portálu Intune (ve verzi Public Preview) <!-- 2351547   -->  
Pomocí Intune teď můžete [Zobrazit podrobnosti](../protect/encryption-monitor.md) o ID klíče BitLockeru a obnovovacích klíčích BitLockeru z Azure Active Directory.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Podpora Microsoft Edge pro scénáře Intune na zařízeních s iOS a Androidem <!-- 3411007 -->
Microsoft Edge bude podporovat všechny stejné scénáře správy jako Intune Managed Browser s přidáním vylepšení pro činnost koncového uživatele. Mezi funkce Microsoft Edge Enterprise, které jsou povolené v zásadách Intune, patří podpora duální identity, integrace zásad ochrany aplikací, integrace služby Azure Application proxy a spravovaných zástupců a domovské stránky. Další informace najdete v tématu [Podpora Microsoft Edge](../apps/app-configuration-managed-browser.md#microsoft-edge-support).

#### <a name="exchange-onlineintune-connector-deprecate-support-for-eas-only-devices---3105122----"></a>Exchange Online/Intune Connector zastaralá podpora pro zařízení jenom s EAS <!--3105122  -->
Konzola Intune už nepodporuje prohlížení a správu zařízení jenom pro EAS připojených k Exchangi Online s konektorem Intune. Místo toho máte následující možnosti:
- Registrace zařízení ve správě mobilních zařízení (MDM)
- Použití zásad Intune App Protection ke správě zařízení
- Používat ovládací prvky Exchange, jak je uvedeno v [klientech a mobilních zařízeních v Exchangi Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online)

### <a name="search-the-all-devices-page-for-an-exact-device-by-using-name---4254930---"></a>Na stránce všechna zařízení vyhledejte přesná zařízení pomocí [name]. <!--4254930 -->
Teď můžete vyhledat přesný název zařízení. Přejít na**zařízení**  >  **Intune**  > **všechna zařízení** > do vyhledávacího pole, abyste mohli vyhledat přesnou shodu s názvem zařízení {}. Například **{Device12345}** .

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202----"></a>Podpora dalších konektorů na stránce stavu tenanta <!-- 3617202  -->
[Stránka stav tenanta](../tenant-status.md) teď zobrazuje informace o stavu dalších konektorů, včetně *rozšířené ochrany před internetovými útoky v programu Windows Defender* (ATP) a dalších konektorů ochrany před mobilními hrozbami.

### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917----"></a>Udělení přístupu k některým rolím Azure Active Directory k Intune jen pro čtení <!-- 3637917  -->
K těmto rolím Azure AD se udělil přístup jenom pro čtení Intune. Oprávnění udělená rolím Azure AD nahrazují oprávnění udělená pomocí řízení přístupu na základě role (RBAC) Intune.

Přístup k datům auditu Intune jen pro čtení:

- Správce dodržování předpisů
- Správce dat dodržování předpisů

Přístup ke všem datům Intune je určený jen pro čtení:

- Správce zabezpečení
- Operátor zabezpečení
- Čtecí modul zabezpečení

Další informace najdete v tématu [řízení přístupu na základě role](role-based-access-control.md).

#### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430-----"></a>Značky oboru pro zřizovací profily aplikací pro iOS <!--2934430   -->
Do zřizovacího profilu aplikace pro iOS můžete přidat značku oboru, aby k němu měl přístup jenom lidé s rolemi přiřazenými k zřizovacímu profilu aplikace pro iOS. Další informace najdete v tématu [použití značek RBAC a Scope](scope-tags.md).

#### <a name="scope-tags-for-app-configuration-policies---2371891-----"></a>Značky oboru pro zásady konfigurace aplikací <!--2371891   -->
Můžete přidat značku oboru do zásad konfigurace aplikace, aby k zásadám konfigurace aplikací měli přístup jenom lidé s rolemi přiřazenými k této značce oboru. Zásady konfigurace aplikací se můžou zaměřit na nebo přidružit k aplikacím, které mají přiřazenou stejnou značku oboru. Další informace najdete v tématu [použití značek RBAC a Scope](scope-tags.md).

### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Podpora Microsoft Edge pro scénáře Intune na zařízeních s iOS a Androidem <!-- 3411007 -->
Microsoft Edge bude podporovat všechny stejné scénáře správy jako Intune Managed Browser s přidáním vylepšení prostředí pro koncové uživatele. Mezi funkce Microsoft Edge Enterprise, které jsou povolené v zásadách Intune, patří podpora duální identity, integrace zásad ochrany aplikací, integrace služby Azure Application proxy a spravovaných zástupců a domovské stránky. Další informace najdete v tématu [Podpora Microsoft Edge](../apps/app-configuration-managed-browser.md#microsoft-edge-support).

## <a name="week-of-february-25-2019"></a>Týden od 25. února 2019

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="intune-powershell-module----951068----"></a>Modul Intune PowerShell <!-- 951068  -->
Modul Intune PowerShell, který poskytuje podporu rozhraní Intune API prostřednictvím Microsoft Graph, je teď k dispozici v [Microsoft Galerie prostředí PowerShell](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10).

- [Podrobnosti o tom, jak používat tento modul](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/README.md)
- [Příklady scénářů, které používají tento modul](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/Samples/README.md)

#### <a name="improved-support-for-delivery-optimization----3183757----"></a>Vylepšená podpora pro optimalizaci doručování  <!--3183757  -->
V Intune jsme rozšířili podporu pro konfiguraci optimalizace doručování. Teď můžete v konzole Intune nakonfigurovat rozšířený seznam [nastavení Optimalizace doručení](../configuration/delivery-optimization-settings.md) a směrovat ho přímo na vaše zařízení.


## <a name="week-of-february-18-2019"></a>Týden od 18. února 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355-----"></a>Intune bude využívat Google Play chránit rozhraní API na zařízeních s Androidem. <!-- 2577355   -->
Někteří správci IT mají na BYODou šířku místa, kde můžou koncoví uživatelé ukončit root nebo jailbreaking svůj mobilní telefon. Toto chování, ale někdy nechtěně úmyslné, má za následek obejít mnoho zásad Intune, které jsou nastavené tak, aby chránily data organizace na zařízeních koncových uživatelů. Proto Intune poskytuje základní a jailbreaků detekci registrovaných i neregistrovaných zařízení. V této verzi bude Intune využívat Google Play chránit rozhraní API, aby je bylo možné přidat k existujícím kontrolám zjišťování kořenu pro nezaregistrovaná zařízení. I když Google nesdílí celou řadu kontrol, ke kterým dojde, očekáváme, že tato rozhraní API zjišťují uživatele, kteří si svá zařízení rootují z jakéhokoli důvodu, aby mohli na starších zařízeních získat novější aktualizace operačního systému. Tito uživatelé si pak můžou zablokovat přístup k firemním datům, jinak se jejich firemní účty můžou vymazat z aplikací s povolenými zásadami. Pro další hodnotu bude mít správce IT nyní několik aktualizací sestav v rámci okna Intune App Protection – sestava "uživatelé s příznakem" zobrazí informace o tom, kteří uživatelé se budou zjišťovat prostřednictvím služby Google Play SafetyNet prověřování rozhraní API. "potenciálně škodlivé aplikace" budou zobrazuje, které aplikace se zjišťují přes kontrolu rozhraní API pro ověřování aplikací přes Google. Tato funkce je dostupná na Androidu.

#### <a name="win32-app-information-available-in-troubleshooting-blade----2617342-----"></a>Informace o aplikaci Win32 dostupné v okně Poradce při potížích <!-- 2617342   -->
V okně pro **řešení potíží s** aplikací Intune teď můžete shromažďovat soubory protokolu chyb pro instalaci aplikace Win32. Další informace o řešení potíží s instalací aplikací najdete v tématu řešení potíží s [instalací aplikací](./../apps/troubleshoot-app-install.md) a [odstraňování potíží s aplikacemi Win32](./../apps/troubleshoot-app-install.md#win32-app-installation-troubleshooting).

#### <a name="app-status-details-for-ios-apps----3761235-----"></a>Podrobnosti o stavu aplikace pro aplikace pro iOS <!-- 3761235   -->
K dispozici jsou nové zprávy o chybách instalace aplikací, které souvisejí s následujícími:
- Selhání pro aplikace VPP při instalaci na sdíleném iPadu
- Chyba při zakázaném App Storu
- Nepovedlo se najít licenci VPP pro aplikaci.
- Nepovedlo se nainstalovat systémové aplikace pomocí poskytovatele MDM.
- Nepovedlo se nainstalovat aplikace, když je zařízení v režimu ztráty nebo celoobrazovkovém režimu.
- Nepovedlo se nainstalovat aplikaci, když uživatel není přihlášený k App Storu.

V Intune vyberte **klientské aplikace** > **aplikace** > název aplikace > **stav instalace zařízení**. Ve sloupci **Podrobnosti o stavu** budou k dispozici nové chybové zprávy.

#### <a name="new-app-categories-screen-in-the-company-portal-app-for-windows-10---3834780----"></a>Obrazovka nové kategorie aplikací v aplikaci Portál společnosti pro Windows 10<!-- 3834780  -->
Přidala se nová obrazovka s názvem **kategorie aplikací** , která vylepšuje možnosti procházení a výběru aplikací v portál společnosti pro Windows 10. Uživatelé teď uvidí své aplikace seřazené pod kategoriemi, jako jsou **Doporučené**, **vzdělávání**a **produktivita**. Tato změna se zobrazí v Portál společnosti verzích 10.3.3451.0 a novějším. Pokud si chcete zobrazit novou obrazovku, přečtěte si téma [co je nového v uživatelském rozhraní aplikace](whats-new-app-ui.md). Další informace o aplikacích v Portál společnosti najdete v tématu [instalace a sdílení aplikací na vašem zařízení](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).  

#### <a name="power-bi-compliance-app----1455231-doc-work-item---"></a>Aplikace Power BI dodržování předpisů <!-- 1455231 doc-work-item -->
Přístup k datovému skladu Intune v Power BI online pomocí aplikace [Intune pro dodržování předpisů (datový sklad)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) . Pomocí této Power BI aplikace teď můžete přistupovat k předem vytvořeným sestavám a sdílet je bez jakéhokoli nastavení a bez nutnosti opustit webový prohlížeč. Další informace najdete v tématu [Změna aplikace pro dodržování předpisů Power BIm protokolu](../developer/reports-changelog.md#power-bi-compliance-app).


### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675-----"></a>Skripty PowerShellu se můžou spouštět na 64 hostitele na 64 zařízeních. <!-- 1862675   -->
Když přidáte skript prostředí PowerShell do konfiguračního profilu zařízení, skript se vždy spustí v 32-bit i v 64 operačních systémech. V rámci této aktualizace může správce spustit skript v 64ovém hostiteli PowerShellu na 64 zařízeních (**Konfigurace zařízení** > **skripty PowerShellu** > **Přidat** > **Konfigurovat**skript  > **v 64 bit. Hostitel PowerShellu**).

Další informace o používání PowerShellu najdete [v tématu skripty PowerShellu v Intune](../apps/intune-management-extension.md).

Platí pro: Windows 10 a novější

#### <a name="macos-users-are-prompted-to-update-their-password----1873216---"></a>uživatelům macOS se zobrazí výzva k aktualizaci hesla. <!-- 1873216 -->
Intune vynucuje nastavení **ChangeAtNextAuth** na zařízeních MacOS. Toto nastavení má vliv na koncové uživatele a zařízení, které mají zásady hesel dodržování předpisů nebo profily hesel omezení zařízení. Koncovým uživatelům se zobrazí výzva, aby si aktualizovali heslo. K této výzvě dochází vždy, když uživatel poprvé spustí úkol, který vyžaduje ověření, například přihlášení k zařízení. Uživatelům se taky může zobrazit výzva k aktualizaci hesla při jakékoli akci, která vyžaduje oprávnění správce, třeba pro vyžadování přístupu k řetězci klíčů. 

Všechny nové nebo existující změny zásad hesla vyzve správce k aktualizaci hesla koncovými uživateli.

Platí pro:  
macOS

#### <a name="assign-scep-certificates-to-a-userless-macos-device-------2340521------"></a>Přiřazení certifikátů SCEP k zařízení macOS pro uživatele    <!-- 2340521    -->
Pomocí atributů zařízení macOS zařízení, včetně zařízení bez přidružení uživatele, můžete přiřadit certifikáty Simple Certificate Enrollment Protocol (SCEP) a přidružit profil certifikátu k profilům sítě Wi-Fi nebo VPN. Tím se rozšíří podpora, kterou už potřebujeme k [přiřazení certifikátů SCEP k zařízením s přidružením uživatele a bez něj](../protect/certificates-profile-scep.md) , na kterém běží Windows, iOS a Android.  Tato aktualizace přidává možnost výběru typu *certifikátu při konfiguraci* profilu certifikátu SCEP pro MacOS.

Platí pro: 
- macOS

#### <a name="intune-conditional-access-ui-update------2432313-----"></a>Aktualizace uživatelského rozhraní pro podmíněný přístup v Intune   <!-- 2432313   -->
Provedli jsme vylepšení uživatelského rozhraní pro podmíněný přístup v konzole Intune. Mezi ně patří:
- Okno *podmíněného přístupu* v Intune se nahradilo oknem z Azure Active Directory. Tím zajistíte, že v konzole Intune budete mít přístup k celé škále nastavení a konfigurací pro [podmíněný přístup](../protect/conditional-access.md) (což zůstává technologie Azure AD). 
- Přejmenovali jsme *místní okno přístupu* na přístup k *Exchangi*a přejmenovali jste nastavení *konektoru Exchange Service Connector* na toto přejmenované okno.  Tato změna slučuje, kde [konfigurujete a sledujete podrobnosti týkající se Exchange Online a místního](../protect/exchange-connector-install.md)prostředí.  

#### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135-----"></a>Prohlížeč veřejného terminálu a aplikace pro prohlížeč Microsoft Edge se můžou spouštět na zařízeních s Windows 10 v celoobrazovkovém režimu. <!-- 2935135   -->
Zařízení s Windows 10 můžete používat v celoobrazovkovém režimu ke spuštění jedné aplikace nebo mnoha aplikací. Tato aktualizace zahrnuje několik změn v aplikacích prohlížeče v celoobrazovkovém režimu, včetně těchto:

- Přidat prohlížeč Microsoft Edge nebo webový prohlížeč na veřejném počítači, aby se spouštěl jako aplikace na veřejném zařízení (**Konfigurace zařízení** > **profily** > **Nový profil** > **Windows 10 a novější** **pro platformu > pro** typ profilu ).
- K dispozici jsou nové funkce a nastavení pro povolení nebo omezení (**Konfigurace zařízení**  > **profily**  > **novém profilu**  > **Windows 10 a novější** pro > **omezení zařízení** pro typ profilu). obsahující

- Prohlížeč Microsoft Edge:
  - Použít celoobrazovkový režim Microsoft Edge
  - Aktualizovat prohlížeč po době nečinnosti

- Oblíbené položky a hledání:
  - Povolí změny vyhledávacího modulu.

Seznam těchto nastavení najdete tady:

- [Nastavení zařízení s Windows 10 a novějším, která se mají spustit jako veřejný terminál](../configuration/kiosk-settings-windows.md)
- [Omezení zařízení prohlížeče Microsoft Edge](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser)
- [Oblíbené a hledání v omezeních zařízení](../configuration/device-restrictions-windows-10.md##favorites-and-search)

Platí pro: Windows 10 a novější

#### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774-----"></a>Nová nastavení omezení pro zařízení s iOS a macOS <!-- 3448774   -->
Můžete omezit některá nastavení a funkce na zařízeních s iOS a macOS (**Konfigurace zařízení** >  profily  > **nové** **profily** > **iOS** nebo **MacOS** pro **omezení** platformy > pro typ profilu). Tato aktualizace přidává další funkce a nastavení, která můžete ovládat, včetně nastavení času obrazovky, změny nastavení karty a mobilních plánů a dalších na zařízeních s iOS. Také se zpožděním viditelnosti aktualizací softwaru uživatelů a blokování ukládání obsahu do mezipaměti na zařízeních macOS. 

Informace o funkcích a nastaveních, které můžete omezit, najdete v těchto tématech:

- [nastavení omezení pro zařízení s iOS](../configuration/device-restrictions-ios.md)
- [nastavení omezení pro zařízení macOS](../configuration/device-restrictions-macos.md)

Platí pro:

- iOS
- macOS

#### <a name="kiosk-devices-are-now-called-dedicated-devices-on-android-enterprise-devices----3598402-----"></a>Zařízení s veřejným veřejným zařízením se teď na zařízeních s Androidem Enterprise označují jako vyhrazená zařízení. <!-- 3598402   -->
V souladu s terminologií Androidu se veřejný **terminál** změní na **vyhrazená zařízení** pro zařízení s Androidem enterprise (**Konfigurace zařízení** > **profily** > **vytvořit profil** > * * Android Enterprise for Platform > **Pouze vlastník zařízení** > **omezení zařízení**0**vyhrazených zařízení**).

Dostupná nastavení zobrazíte tak, že přejdete na [nastavení zařízení a povolíte nebo zakážete funkce](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).

Platí pro:  
Android Enterprise

#### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850-3803313-----"></a>Prohlížeč Safari a zpoždění viditelnosti aktualizace softwaru uživatele v uživatelském rozhraní Intune se pohybují. <!-- 3640850, 3803313   -->
U zařízení se systémem iOS můžete nastavit nastavení Safari a nakonfigurovat aktualizace softwaru. V této aktualizaci se tato nastavení pohybují do různých částí uživatelského rozhraní Intune:

- Nastavení Safari přesunuté z **prohlížeče Safari** (**Konfigurace zařízení**  > **profily**  > **novém profilu**  > **iOS** pro **omezení** platformy > pro typ profilu) do **[integrovaných aplikací](../configuration/device-restrictions-ios.md#built-in-apps)** .
- Nastavení **zpoždění aktualizace softwaru uživatele pro zařízení s iOS v režimu pod dohledem** (**aktualizace softwaru** > **zásady aktualizace pro iOS**) se přesouvá na **omezení zařízení** >  **[Obecné](../configuration/device-restrictions-ios.md#general)** .  Podrobnosti o dopadu na stávající zásady najdete v tématu [aktualizace softwaru pro iOS](../protect/software-updates-ios.md#configure-the-policy). 

Seznam nastavení najdete v tématu:

- [omezení zařízení s iOS](../configuration/device-restrictions-ios.md) 
- [aktualizace softwaru iOS](../protect/software-updates-ios.md)

Tato funkce platí pro: 

- iOS

#### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164-----"></a>Povolení omezení v nastavení zařízení se přejmenují na čas obrazovky na zařízeních s iOS. <!-- 3699164   -->
Můžete nakonfigurovat **omezení povolení v nastavení zařízení** pro zařízení s iOS (**Konfigurace zařízení** > **profily** > **nový profil** > **iOS** pro > zařízení platformy.  **omezení** pro typ profilu > **Obecné**). V této aktualizaci je toto nastavení přejmenováno na **čas obrazovky (jenom pod dohledem)** . 

Chování je stejné. Určen 

- iOS 11.4.1 a starší: **blok** brání koncovým uživatelům v nastavení vlastních omezení v nastavení zařízení. 
- iOS 12,0 a novější: **blok** znemožní koncovým uživatelům v nastavení zařízení nastavit vlastní **čas obrazovky** , včetně obsahu & omezení ochrany osobních údajů. V zařízeních upgradovaných na iOS 12,0 se už nebudou zobrazovat karty omezení v nastavení zařízení. Tato nastavení se nacházejí v **čase obrazovky**. 

Seznam nastavení najdete v tématu [omezení pro zařízení s iOS](../configuration/device-restrictions-ios.md#general).

Platí pro: 
- iOS


### <a name="device-management"></a>Správa zařízení

#### <a name="rename-an-enrolled-windows-device----1911112----"></a>Přejmenování zaregistrovaného zařízení se systémem Windows <!-- 1911112  -->
Teď můžete přejmenovat zaregistrované zařízení s Windows 10 (RS4 nebo novější). Pokud to chcete udělat, vyberte zařízení ** > ** **Intune**  > **všechna zařízení** > vyberte zařízení > **Přejmenovat zařízení**. Tato funkce v současné době nepodporuje přejmenování hybridních zařízení se systémem Windows Azure AD.

#### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Automaticky přiřadí značky oboru k prostředkům vytvořeným správcem s tímto oborem. <!-- 3173823  -->
Když správce vytvoří prostředek, všechny značky oboru přiřazené správci se automaticky přiřadí těmto novým prostředkům.

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202----"></a>Zpráva o selhání registrace se přesune do okna registrace zařízení. <!-- 3560202  -->
Sestava **neúspěšné registrace** byla přesunuta do části **monitorování** okna **registrace zařízení** . Byly přidány dva nové sloupce (metoda registrace a verze operačního systému).

#### <a name="company-portal-abandonment-report-renamed-to-incomplete-user-enrollments---3815076-eemiss---"></a>Sestava opuštění Portál společnosti přejmenována na nedokončené registrace uživatelů <!--3815076 eemiss -->
Sestava o **opuštění portál společnosti** byla přejmenována na **nedokončené registrace uživatele**.


<!-- ########################## -->
## <a name="week-of-february-4-2019"></a>Týden od 4. února 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="intune-macos-company-portal-dark-mode----3300524----"></a>Tmavý režim Intune macOS Portál společnosti <!-- 3300524  -->
Intune macOS Portál společnosti teď podporuje tmavý režim pro macOS. Když povolíte tmavý režim na macOS 10.14 + +, Portál společnosti upraví jeho vzhled na barvy, které se projeví v tomto režimu.

<!-- ########################## -->
## <a name="week-of-january-21-2019"></a>Týden od 21. ledna 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Oznámení informačních zpráv pro aplikace Win32 <!-- 3136566   -->
Můžete potlačit zobrazování oznámení informační zprávy koncového uživatele na přiřazení aplikace. V Intune vyberte **klientské aplikace**  > **aplikace** > vyberte **přiřazení** > aplikací  > **Zahrnout skupiny**. 

#### <a name="intune-app-protection-policies-ui-update----3251427----"></a>Aktualizace uživatelského rozhraní zásad ochrany aplikací Intune <!-- 3251427  -->
Změnili jsme štítky pro nastavení a tlačítka pro ochranu aplikací Intune, aby bylo snazší porozumět. Mezi tyto změny patří:  
- Ovládací prvky se změní z **yes**  /  žádné ovládací prvky, které**by** měly **blokovat**  / **Povolit** a **Zakázat** ovládací prvky**Povolit**  / . Popisky jsou také aktualizovány.  
- Nastavení se přeformátují, takže nastavení a jeho popisek jsou vedle sebe v ovládacím prvku k zajištění lepší navigace.   

Výchozí nastavení a počet nastavení zůstávají stejné, ale tato změna umožňuje uživateli pochopit, Procházet a používat nastavení snadněji, aby bylo možné použít vybrané zásady ochrany aplikací. Informace najdete v tématu [Nastavení iOS](../apps/app-protection-policy-settings-ios.md) a [nastavení Androidu](../apps/app-protection-policy-settings-android.md).

### <a name="additional-settings-for-outlook----3301182----"></a>Další nastavení pro Outlook <!-- 3301182  -->
V Intune teď můžete nakonfigurovat následující další nastavení pro Outlook pro iOS a Android:

- Povoluje použití pracovních nebo školních účtů v Outlooku v iOS a Androidu.
- Nasazení moderního ověřování pro Office 365 a hybridních moderních ověřování v místních účtech
- Při výběru základního ověřování použít `SAMAccountName` pro pole username v e-mailovém profilu
- Povoluje uložení kontaktů.
- Konfigurace externích příjemců s upozorněním na upozornění
- Konfigurovat **prioritní doručenou poštu**
- Vyžadovat pro přístup k Outlooku pro iOS biometrika
- Blokovat externí image

> [!NOTE]
> Pokud používáte zásady Intune App Protection ke správě přístupu k podnikovým identitám, měli byste zvážit, že nepovolíte možnost **vyžadovat biometrika**. Další informace najdete v tématu **vyžadování podnikových přihlašovacích údajů pro** přístup k [nastavení přístupu iOS](../apps/app-protection-policy-settings-ios.md#access-requirements) a [nastavení přístupu pro Android](../apps/app-protection-policy-settings-android.md#access-requirements).

Další informace najdete v tématu [nastavení konfigurace aplikace Microsoft Outlook](../apps/app-configuration-policies-outlook.md).

#### <a name="delete-android-enterprise-apps----1352553---"></a>Odstranění podnikových aplikací pro Android <!-- 1352553 -->
Spravované aplikace Google Play můžete z Microsoft Intune odstranit. Pokud chcete odstranit spravovanou aplikaci Google Play, otevřete Microsoft Intune v Azure Portal a vyberte **klientské aplikace**  > **aplikace**. V seznamu aplikace vyberte tři tečky (...) napravo od spravované aplikace Google Play a pak v zobrazeném seznamu vyberte **Odstranit** . Při odstranění spravované aplikace Google Play ze seznamu aplikací se spravovaná aplikace Google Play automaticky neschválí.

#### <a name="managed-google-play-app-type----1352580---"></a>Typ spravované aplikace Google Play <!-- 1352580 -->
Typ **spravované aplikace Google Play** vám umožní přidat [spravované aplikace Google Play](https://play.google.com/work/search?q=microsoft&c=apps) do Intune. Jako správce Intune teď můžete v Intune Procházet, vyhledávat, schvalovat, synchronizovat a přiřazovat schválené spravované Google Play aplikace.  Už nemusíte procházet konzolu spravované Google Play samostatně a už se nemusíte znovu ověřovat.  V Intune vyberte **klientské aplikace** > **aplikace** > **Přidat**. V seznamu **Typ aplikace** vyberte **spravované Google Play** jako typ aplikace.

### <a name="default-android-pin-keyboard----3802457---"></a>Výchozí klávesnice pro PIN kód pro Android <!-- 3802457 -->
U koncových uživatelů, kteří na svých zařízeních s Androidem nastavili kód PIN pro Intune App Protection (APP) s typem PIN typu numeric, se teď zobrazí výchozí klávesnice pro Android namísto pevného uživatelského rozhraní klávesnice s Androidem, které jste předtím navrhli. Tato změna byla provedena konzistentně při používání výchozích klávesnic pro Android i iOS pro oba typy kódu PIN typu "numeric" nebo "heslo". Další informace o nastavení přístupu koncového uživatele v Androidu, například PIN kódu aplikace, najdete v tématu [požadavky na přístup k Androidu](../apps/app-protection-policy-settings-android.md#access-requirements).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="use-microsoft-recommended-settings-with-security-baselines-public-preview----2055484-----"></a>Použít nastavení Doporučené Microsoftem se standardními hodnotami zabezpečení (Public Preview) <!-- 2055484   -->

Intune se integruje s dalšími službami, které se zaměřují na zabezpečení, včetně Ochrany ATP v programu Windows Defender a Ochrany ATP v Office 365. Zákazníci požadují ve službách Microsoft 365 společnou strategii a soudržnější sadu ucelených bezpečnostních pracovních postupů. Naším cílem je srovnat strategie tak, abychom mohli vytvářet řešení přemosťující operace zabezpečení a běžné úlohy správy. V Intune se snažíme tohoto cíle dosáhnout prostřednictvím publikování sady Standardních hodnot zabezpečení doporučených Microsoftem (**Intune** > **Standardní hodnoty zabezpečení**).  Správce může vytvořit zásady zabezpečení přímo z těchto směrných plánů a pak je nasadit na své uživatele. Můžete také přizpůsobit doporučení osvědčených postupů pro splnění potřeb vaší organizace. Intune zajišťuje, že zařízení zůstávají v souladu s těmito standardními hodnotami, a upozorní správce, pokud uživatelé nebo zařízení tyto hodnoty nedodržují.

Tato funkce je ve verzi Public Preview, takže všechny vytvořené profily nyní nebudou přesunuty do šablon standardních hodnot zabezpečení, které jsou všeobecně dostupné (GA). Neměli byste v produkčním prostředí používat tyto šablony verze Preview.

Další informace o standardních hodnotách zabezpečení najdete [v tématu vytvoření směrného plánu zabezpečení Windows 10 v Intune](../protect/security-baselines-monitor.md).

Tato funkce se týká: Windows 10 a novější

#### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379-----"></a>Uživatelé bez oprávnění správce můžou povolit BitLocker na zařízeních s Windows 10, která jsou připojená k Azure AD.<!-- 2147379   -->
Pokud povolíte nastavení BitLockeru na zařízeních s Windows 10 (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější** pro Platform > **Endpoint Protection** pro typ profilu > **Šifrování systému Windows**), přidáte nastavení nástroje BitLocker. 

Tato aktualizace obsahuje nové nastavení BitLockeru, které umožňuje standardním uživatelům (nikoli správcům) povolit šifrování. 

Nastavení zobrazíte tak, že přejdete na [nastavení ochrany koncových bodů pro Windows 10](../protect/endpoint-protection-windows-10.md#windows-encryption).

#### <a name="check-for-configuration-manager-compliance----2192052--eepublished----"></a>Ověřit Configuration Manager dodržování předpisů <!-- 2192052  eepublished  -->
Tato aktualizace zahrnuje nové nastavení dodržování předpisů System Center Configuration Manager (**zásady** > **dodržování předpisů zařízením** > **vytvořit zásadu** > **Windows 10 a novější** > **Configuration Manager Dodržování předpisů**). Configuration Manager bude posílat signály funkci dodržování předpisů v Intune. Pomocí tohoto nastavení můžete vyžadovat, aby všechny signály Configuration Manager vracely "vyhovující".

Můžete například vyžadovat, aby v zařízeních byly nainstalované všechny aktualizace softwaru. V Configuration Manageru má tento požadavek stav Nainstalováno. Pokud jsou některé programy v zařízení v neznámém stavu, zařízení nedodržuje předpisy v Intune.

[Configuration Manager dodržování předpisů](../protect/compliance-policy-create-windows.md#configuration-manager-compliance) popisuje toto nastavení.

Platí pro: Windows 10 a novější

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324-----"></a>Přizpůsobení tapety na zařízeních s iOS pod dohledem pomocí profilu konfigurace zařízení <!-- 2809324   -->
Když vytváříte konfigurační profil zařízení pro zařízení s iOS, můžete si přizpůsobit některé funkce (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro funkce platformy >ch **zařízení** . pro typ profilu). Tato aktualizace zahrnuje nová nastavení **tapety** , která umožní správci použít na domovské obrazovce nebo na zamykací obrazovce obrázek. png,. jpg nebo. jpeg. Tato nastavení tapety se vztahují jenom na zařízení pod dohledem. 

Seznam těchto nastavení najdete v tématu [Nastavení funkcí pro zařízení s iOS](../configuration/ios-device-features-settings.md).

#### <a name="windows-10-kiosk-is-generally-available----3594661----"></a>Veřejné terminály s Windows 10 jsou všeobecně dostupné <!-- 3594661  -->
V této aktualizaci je k dispozici beznabídková funkce na zařízeních s Windows 10 a novějším (GA). Všechna nastavení, která můžete přidat a nakonfigurovat, najdete v tématu [Nastavení veřejného terminálu pro Windows 10 (a novější)](../configuration/kiosk-settings.md).

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396-----"></a>Sdílení kontaktů přes Bluetooth se odebírá v omezeních zařízení > vlastník zařízení pro Android Enterprise. <!-- 3598396   -->
Když vytvoříte profil omezení zařízení pro zařízení s Androidem Enterprise, budete mít k dispozici **Sdílení kontaktů prostřednictvím nastavení Bluetooth** . V této aktualizaci se odstraní **Sdílení kontaktů prostřednictvím nastavení Bluetooth** (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** for Platform > **omezení zařízení. > Vlastníka zařízení** pro typ profilu > **Obecné**). 

**Sdílení kontaktů prostřednictvím nastavení Bluetooth** není pro správu vlastníka zařízení s Androidem Enterprise podporováno. Takže když se toto nastavení odebere, nebude mít vliv na žádná zařízení ani klienty, ani když je toto nastavení povolené a nakonfigurované ve vašem prostředí.

Pokud chcete zobrazit aktuální seznam nastavení, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo zakažte funkce](../configuration/device-restrictions-android-for-work.md).

Platí pro: vlastník zařízení se systémem Android Enterprise

### <a name="device-management"></a>Správa zařízení

#### <a name="selective-wipe-support-for-wip-without-enrollment-devices----1434452---"></a>Podpora selektivního vymazání pro Nedokončená práce bez registračních zařízení <!-- 1434452 -->
Windows Information Protection bez registrace (NV) umožňuje zákazníkům chránit podniková data na zařízeních s Windows 10 bez nutnosti úplné registrace MDM. Po ochraně dokumentů pomocí zásad pro nedokončené výroby může být chráněná data selektivně smazána správcem služby Intune. Když vyberete uživatele a zařízení a odešlete žádost o vymazání, všechna data, která byla chráněná prostřednictvím zásad výroby, se nedají použít. V Intune na portálu Azure Portal vyberte **Mobilní aplikace** > **Selektivní vymazání aplikace**.

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="new-operational-logs-and-ability-to-send-logs-to-azure-monitor-services----3762211----"></a>Nové provozní protokoly a možnost odesílat protokoly do služby Azure Monitor Services <!-- 3762211  -->
Intune obsahuje integrované protokolování auditu, které sleduje události při provádění změn. Tato aktualizace zahrnuje nové funkce protokolování, včetně: 
- Provozní protokoly (Preview), které zobrazují podrobnosti o uživatelích a zařízeních, která jsou zaregistrovaná, včetně úspěšných a neúspěšných pokusů.
- Protokoly auditu a provozní protokoly je možné odesílat do Azure Monitor, včetně účtů úložiště, Center událostí a Log Analytics. Tyto služby umožňují ukládat, používat analýzy jako Splunk a QRadar a získávat vizualizace dat protokolování.

Další informace o této funkci najdete [v posílání dat protokolu do úložiště, centra událostí nebo Log Analytics v Intune](../review-logs-using-azure-monitor.md) .

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509----"></a>Přeskočit další obrazovky pomocníka s nastavením na zařízení se systémem iOS DEP <!-- 2687509  -->
Kromě obrazovek, které můžete v současnosti přeskočit, můžete nastavit zařízení se systémem iOS DEP, aby při zápisu zařízení do pomocníka s nastavením přeskočili následující obrazovky: tónový displej, ochrana osobních údajů, migrace Androidu, tlačítko domů, iMessage & FaceTime, zprovoznění, sledování Migrace, vzhled, čas zobrazení, aktualizace softwaru, Nastavení SIM.
Pokud chcete vybrat, které obrazovky se mají přeskočit, přejděte na **registrace zařízení**  >  registrace**Apple**  > **tokeny programu registrace** > vyberte **profily > profilů** > vyberte profil > **vlastnosti**  > **nastavení. Přizpůsobení asistenta** > pro všechny obrazovky, které chcete přeskočit > **OK**, zvolit **Skrýt** .
Pokud vytvoříte nový profil nebo upravíte profil, je nutné, aby se vybrané přeskočené obrazovky synchronizovaly se serverem Apple MDM. Uživatelé můžou vydat ruční synchronizaci zařízení, aby při vybírání změn profilu nedocházelo k žádnému zpoždění.

#### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Enterprise APP – nasazení aplikace v aplikaci <!-- 1171203 -->
U zařízení s Androidem v zaregistrovaných zásadách ochrany aplikací, ale ve scénáři nasazení (App-We), teď můžete použít spravovaný Google Play k nasazení aplikací pro Store a obchodních aplikací uživatelům. Konkrétně můžete koncovým uživatelům poskytnout katalog aplikací a prostředí pro instalaci, které už nevyžadují, aby koncoví uživatelé vystavi zabezpečení jejich zařízení tím, že umožňují instalaci z neznámých zdrojů. Tento scénář nasazení navíc poskytuje vylepšené prostředí pro koncové uživatele.

<!-- ########################## -->
## <a name="week-of-january-14-2019"></a>Týden od 14. ledna 2019

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Verze Preview podpory pro zařízení s Androidem, která jsou ve vlastnictví společnosti, plně spravovaná <!-- 1574342  -->
Intune teď podporuje plně spravovaná zařízení s Androidem, scénář "vlastník zařízení ve vlastnictví firmy", ve kterém jsou zařízení úzce spravovaná IT a přidružená k jednotlivým uživatelům. To správcům umožňuje spravovat celé zařízení, vynutilo rozšířené množství ovládacích prvků zásad nedostupných pro pracovní profily a omezuje uživatelům instalovat aplikace jenom ze spravovaných Google Play. Další informace najdete v tématu [Nastavení registrace Intune pro zařízení s Androidem s plnou správou](../enrollment/android-fully-managed-enroll.md) a [registrace vyhrazených zařízení nebo plně spravovaných zařízení](../enrollment/android-dedicated-devices-fully-managed-enroll.md).  Upozorňujeme, že tato funkce je ve verzi Preview. Některé možnosti Intune, jako jsou certifikáty, dodržování předpisů a podmíněný přístup, nejsou aktuálně k dispozici u zařízení s plně spravovanými uživateli Androidu.

<!-- ########################## -->
## <a name="week-of-january-7-2019"></a>Týden od 7. ledna 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="intune-app-pin----2298397---"></a>PIN kód aplikace Intune <!-- 2298397 -->
Jako správce IT teď můžete nakonfigurovat počet dní, po které může koncový uživatel čekat, než bude nutné změnit PIN kód aplikace Intune. Nové nastavení má *za následek Resetování PIN kódu po několika dnech* a je dostupné v Azure Portal tak, že  > **klientské aplikace** **Intune**  > **Zásady ochrany aplikací**  > **vytvořit zásadu**  > **Nastavení** . 0**požadavky na přístup**. Tato funkce, která je dostupná pro zařízení s [iOS](../apps/app-protection-policy-settings-ios.md) a [Androidem](../apps/app-protection-policy-settings-android.md) , podporuje kladnou celočíselnou hodnotu.


#### <a name="intune-device-reporting-fields----2748738---"></a>Pole pro vytváření sestav zařízení v Intune <!-- 2748738 -->
Intune poskytuje další pole pro vytváření sestav zařízení, včetně ID registrace aplikace, výrobce Androidu, modelu a verze opravy zabezpečení i modelu iOS. V Intune jsou tato pole dostupná, a to tak, že vyberete **klientské aplikace**  > **stav ochrany aplikací** a zvolíte **sestavu ochrana aplikací: iOS, Android**. Kromě toho vám tyto parametry pomůžou nakonfigurovat nastavení seznam **povolených** pro výrobce zařízení (Android), seznam **povolených** pro model zařízení (Android a iOS) a minimální verzi opravy zabezpečení Androidu. 


### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Šablony pro správu jsou ve verzi Public Preview a přesunuté do vlastního konfiguračního profilu. <!-- 3322847 -->

Šablony pro správu v Intune (**Konfigurace zařízení** > **šablony pro správu**) jsou momentálně ve verzi Public Preview. S touto aktualizací:

- Šablony pro správu zahrnují nastavení 300, která se dají spravovat v Intune. Dříve tato nastavení existovala pouze v editoru zásad skupiny.
- Šablony pro správu jsou k dispozici ve verzi Public Preview.
- Šablony pro správu se pohybují z **Konfigurace zařízení** > **šablony pro správu** do **Konfigurace zařízení** > **profily** > **vytvořit profil** > na **platformě**, vyberte  **Windows 10 a novější** > v **typu profilu**vyberte **šablony pro správu**.
- Vytváření sestav je povolené.

Další informace o této funkci najdete v článku [šablony Windows 10, kde můžete nakonfigurovat nastavení zásad skupiny](../configuration/administrative-templates-windows.md).

Platí pro: Windows 10 a novější

#### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user-----1333642---"></a>Použít S/MIME k šifrování a podepsání více zařízení pro uživatele  <!-- 1333642 -->
Tato aktualizace zahrnuje šifrování S/MIME e-mailů pomocí nového profilu importovaného certifikátu (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > vyberte platformu > typ profilu **Importovaný certifikát PKCS**). V Intune můžete importovat certifikáty ve formátu PFX. Intune pak může doručit stejné certifikáty do více zařízení zaregistrovaných jedním uživatelem. To také zahrnuje:
- Nativní e-mailový profil v iOS podporuje povolení šifrování S/MIME pomocí importovaných certifikátů ve formátu PFX.
- Nativní e-mailová aplikace v zařízeních Windows Phone 10 automaticky používá certifikát S/MIME.
- Privátní certifikáty je možné doručit na různé platformy. Některé e-mailové aplikace ale S/MIME nepodporují.
- Na jiných platformách může být nutné ručně nakonfigurovat e-mailovou aplikaci a povolit S/MIME.  
- E-mailové aplikace, které podporují šifrování S/MIME, můžou zpracovávat načítání certifikátů pro šifrování S/MIME e-mailů způsobem, který MDM nepodporuje (například ho načítají z úložiště certifikátů svého vydavatele).
Další informace o této funkci najdete v tématu [S/MIME – přehled pro podepsání a šifrování e-mailu](../protect/certificates-s-mime-encryption-sign.md).
Podporováno v systémech: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Nové možnosti pro automatické připojení a zachování pravidel při použití nastavení DNS v zařízeních se systémem Windows 10 nebo novějším <!-- 1333665, 2999078 -->
V zařízeních se systémem Windows 10 a novějším můžete vytvořit konfigurační profil sítě VPN, který obsahuje seznam serverů DNS k překladu domén, například contoso.com. Tato aktualizace obsahuje nová nastavení pro překlad názvů (**Konfigurace zařízení** > **profily** > **vytvořit profil** > vyberte **Windows 10 a novější** pro platformu > vyberte možnost **VPN** pro typ profilu > **DNS. nastavení** >**Přidat**): 
- **Automaticky připojit**: Pokud je tato možnost **povolena**, zařízení se automaticky připojí k síti VPN, když zařízení kontaktuje doménu, kterou zadáte, například contoso.com.
- **Persistent**: ve výchozím nastavení jsou všechna pravidla tabulky zásad překladu IP adres (NRPT) aktivní, pokud je zařízení připojené pomocí tohoto profilu sítě VPN. Pokud je toto nastavení **povolené** u pravidla NRPT, zůstane toto pravidlo aktivní na zařízení, i když se VPN odpojí. Pravidlo zůstane, dokud se neodebere profil sítě VPN nebo dokud se pravidlo ručně neodebere, což se dá udělat pomocí PowerShellu.
Nastavení [sítě VPN pro Windows 10](../configuration/vpn-settings-windows-10.md) popisují nastavení. 

#### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Použití zjišťování důvěryhodných sítí pro profily sítě VPN na zařízeních s Windows 10 <!-- 1500165 -->
Při použití zjišťování důvěryhodných sítí můžete zabránit tomu, aby profily sítě VPN automaticky vytvářely připojení VPN, když je uživatel již v důvěryhodné síti. Pomocí této aktualizace můžete přidat přípony DNS, které umožní detekci důvěryhodných sítí na zařízeních s Windows 10 a novějším (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější** pro Platforma > **VPN** pro typ profilu).
[Nastavení sítě VPN pro Windows 10](../configuration/vpn-settings-windows-10.md) uvádí aktuální nastavení sítě VPN.

#### <a name="manage-windows-holographic-for-business-devices-used-by-multiple-users----1907917-1063203---"></a>Správa zařízení s Windows holografickým pro firmy používaných více uživateli <!-- 1907917, 1063203 -->
V současné době můžete nakonfigurovat nastavení sdílených počítačů na zařízeních s Windows 10 a Windows holografickým pro firmy pomocí vlastního nastavení OMA-URI. V této aktualizaci se přidá nový profil pro konfiguraci nastavení sdíleného zařízení (**Konfigurace zařízení**  > **profily**  > **vytvořit profil**  > **Windows 10 a novější**  > **sdílené zařízení s více uživateli**).
Další informace o této funkci najdete v [Nastavení Intune, kde můžete spravovat sdílená zařízení](../configuration/shared-user-device-settings.md).
Platí pro: Windows 10 a novější, Windows Holografick pro firmy

#### <a name="new-windows-10-update-settings---2626030--2512994----"></a>Nová nastavení aktualizací Windows 10 <!--2626030  2512994  -->
Pro [aktualizační kanály Windows 10](../protect/windows-update-for-business-configure.md)můžete nakonfigurovat:
- **Chování Automatické aktualizace** – použijte novou možnost, *Obnovit výchozí* nastavení pro obnovení původních nastavení automatických aktualizací na počítači s Windows 10 na počítačích, na kterých běží *aktualizace z října 2018* .
- **Blokování uživatele při pozastavení aktualizací Windows** – umožňuje nakonfigurovat nové nastavení aktualizací softwaru, které vám umožní zablokovat nebo nechat uživatelům pozastavit instalaci aktualizací z *Nastavení* jejich počítačů. 

#### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>e-mailové profily pro iOS můžou používat podepisování a šifrování S/MIME. <!-- 2662949 -->
Můžete vytvořit e-mailový profil, který obsahuje různá nastavení. Tato aktualizace zahrnuje nastavení S/MIME, která se dají použít k podepisování a šifrování e-mailových komunikací na zařízeních s iOS (**Konfigurace zařízení** > **profily** > **vytvořit profil** > zvolit **iOS** pro platformu >  **E-mail** pro typ profilu).
[nastavení konfigurace e-mailu pro iOS](../configuration/email-settings-ios.md) zobrazí seznam nastavení.

#### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Některá nastavení BitLockeru podporují edici Windows 10 pro.<!-- 2727036 -->
Můžete vytvořit konfigurační profil, který nastaví nastavení ochrany koncových bodů na zařízeních s Windows 10, včetně BitLockeru. Tato aktualizace přidává pro některá nastavení BitLockeru podporu pro Windows 10 Professional Edition. Tato nastavení ochrany zobrazíte tak, že přejdete na [nastavení ochrany koncového bodu pro Windows 10](../protect/endpoint-protection-windows-10.md#windows-encryption).

#### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal---2809362---"></a>Konfigurace sdíleného zařízení se přejmenovala na zprávu zamykací obrazovky pro zařízení s iOS v Azure Portal<!-- 2809362 -->
Když vytváříte konfigurační profil pro zařízení s iOS, můžete přidat nastavení **Konfigurace sdíleného zařízení** a zobrazit konkrétní text na zamykací obrazovce. Tato aktualizace obsahuje následující změny: 
- Nastavení **Konfigurace sdíleného zařízení** v Azure Portal se přejmenují na "zpráva na zamykací obrazovce (jenom pod dohledem)" (**Konfigurace zařízení** > **profily** > **vytvořit profil** > vyberte **iOS** pro platformu > Zvolit **funkce zařízení** pro typ profilu > **zpráva zamykací obrazovky**).
- Při přidávání zpráv na zamykací obrazovce můžete do **informací o značce assetu** a na **zamykací obrazovce**vložit sériové číslo, název zařízení nebo jinou hodnotu specifickou pro zařízení jako proměnnou. Můžete například zadat `Device name: {{devicename}}` nebo `Serial number is {{serialnumber}}` pomocí složených závorek. [tokeny iOS](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) vypisuje dostupné tokeny, které se dají použít.
[Nastavení pro zobrazení zpráv na zamykací obrazovce](../configuration/ios-device-features-settings.md#lock-screen-message) obsahuje seznam nastavení.

#### <a name="new-app-store-doc-viewing-gaming-device-restriction-settings-added-to-ios-devices----2827760--"></a>Nové App Storu, zobrazení dokumentů, nastavení omezení herních zařízení přidaná do zařízení se systémem iOS <!-- 2827760-->
V části **Konfigurace zařízení**  > **profily**  > **vytvoření profilu**  > **iOS** pro > **omezení zařízení** pro typ profilu > **App Store, zobrazování dokumentů, hry**, následující nastavení: Přidáno: povolení spravovaných aplikací pro zápis kontaktů na nespravované účty kontaktů umožňuje nespravovaným aplikacím číst ze spravovaných účtů kontaktů, aby se tato nastavení zobrazila, přejděte na [omezení zařízení s iOS](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

#### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Nové oznámení, doporučení a nastavení pro ochranu zařízení pro zařízení s Androidem Enterprise Device Owner <!-- 3201839 3201843 -->
Tato aktualizace zahrnuje několik nových funkcí na zařízeních s Androidem Enterprise, když se spouští jako vlastník zařízení. Chcete-li tyto funkce použít, klikněte na položku **Konfigurace zařízení** > **profily** > **vytvořit profil** **> v možnosti**typ profilu vyberte možnost **Android Enterprise** > v **typu profilu**, vyberte **pouze vlastník zařízení**@no__ **omezení zařízení**v t-9.

Obsahuje například tyto nové funkce: 

- Zakažte zobrazování systémových oznámení, včetně příchozích volání, systémových výstrah, systémových chyb a dalších.
- Navrhuje přeskočit úvodní kurzy a tipy pro aplikace, které se otevřou poprvé.
- Zakažte Pokročilá nastavení ochrany před internetovými ochranou, jako je fotoaparát, oznámení, odemknutí otiskem prstu a další.


Nastavení zobrazíte tak, že přejdete na [Nastavení omezení pro zařízení s Androidem Enterprise](../configuration/device-restrictions-android-for-work.md).

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Zařízení vlastníka zařízení s Androidem Enterprise můžou používat připojení VPN typu Always On. <!-- 3202194 -->
V této aktualizaci můžete použít připojení VPN typu Always On na zařízeních vlastníka zařízení s Androidem Enterprise. Neustále aktivní připojení VPN zůstávají ve spojení nebo se ihned znovu připojí, jakmile uživatel odemkne zařízení, zařízení se restartuje nebo se změní bezdrátová síť. Připojení také můžete přepnout do „zamčeného“ režimu, který blokuje veškerý síťový provoz, dokud není připojení VPN zase aktivní.
V **konfiguraci zařízení**můžete povolit možnost vždycky ZAPNUTOU síť VPN  > **profily** > **vytvořit profil** > **Android Enterprise** for platform > **omezení zařízení** jenom pro vlastníka zařízení > **připojení.** nastavení. Nastavení zobrazíte tak, že přejdete na [Nastavení omezení pro zařízení s Androidem Enterprise](../configuration/device-restrictions-android-for-work.md).

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Nové nastavení pro koncové procesy ve Správci úloh na zařízeních s Windows 10 <!-- 3285177 --> 
Tato aktualizace zahrnuje nové nastavení pro ukončení procesů pomocí Správce úloh na zařízeních s Windows 10. Pomocí konfiguračního profilu zařízení (**Konfigurace zařízení** > **profily** > **vytvořit profil** > na **platformě**vyberte v možnosti **typ profilu**> **Windows 10** , vyberte **omezení zařízení** .  > **Obecné** nastavení), můžete zvolit možnost povolení nebo zabránění tomuto nastavení.
Pokud se chcete podívat na tato nastavení, přejděte na [Nastavení omezení pro zařízení s Windows 10](../configuration/device-restrictions-windows-10.md).
Platí pro: Windows 10 a novější

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564---"></a>Podrobnější zasílání zpráv o selhání omezení registrace <!-- 3111564 -->
Podrobnější chybové zprávy jsou k dispozici v případě, že nejsou splněna omezení registrace. Pokud se chcete podívat na tyto zprávy, přejděte na **Intune**  > **řešení potíží** > a zkontrolujte tabulku selhání registrace. Další informace najdete v [seznamu selhání registrace](help-desk-operators.md#enrollment-failure-reference).

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="tenant-status-dashboard-----1124854---"></a>Řídicí panel stavu tenanta  <!-- 1124854 -->
Stránka nový [stav tenanta](tenant-status.md) poskytuje jedno umístění, kde můžete zobrazit stav a související podrobnosti pro vašeho tenanta.  Řídicí panel je rozdělen na čtyři oblasti:
- **Podrobnosti o tenantovi** – zobrazí informace, které obsahují název a umístění tenanta, vaši autoritu MDM, celkový počet zaregistrovaných zařízení ve vašem tenantovi a počet licencí. Tato část uvádí také aktuální verzi služby pro vašeho tenanta.
- **Stav konektoru** – zobrazí informace o dostupných konektorech, které jste nakonfigurovali, a můžete také zobrazit seznam těch, které jste ještě nepovolili.  
   V závislosti na aktuálním stavu každého konektoru jsou označeny jako v pořádku, varování nebo není v pořádku. Vyberte spojnici, pro kterou chcete procházet, a zobrazte podrobnosti nebo nakonfigurujte další informace.
- **Intune Service Health** – zobrazí podrobnosti o aktivních incidentech nebo výpadkech pro vašeho tenanta. Informace v této části jsou načteny přímo z centra zpráv Office.
- **Novinky Intune** – zobrazí aktivní zprávy pro vašeho tenanta. Zprávy zahrnují například oznámení, když váš tenant obdrží nejnovější funkce Intune.  Informace v této části jsou načteny přímo z centra zpráv Office.

#### <a name="new-help-and-support-experience-in-company-portal-for-windows-10----1488939--"></a>Nové prostředí pro nápovědu a podporu v Portál společnosti pro Windows 10 <!-- 1488939-->
Nová stránka podpory & Portál společnosti pomoc pomáhá uživatelům při řešení potíží a vyžádat si nápovědu k problémům s aplikacemi a přístupem. Na nové stránce můžou e-maily Odeslat podrobnosti o chybě a diagnostickém protokolu a najít podrobnosti o helpdesku své organizace. V části Nejčastější dotazy najdete také odkazy na příslušnou dokumentaci k Intune. 

#### <a name="new-help-and-support-experience-for-intune------3307080---"></a>Nové prostředí pro nápovědu a podporu pro Intune   <!-- #3307080 -->
Zavádíme nové prostředí pro pomoc a podporu pro všechny klienty za několik dalších dní. Toto nové prostředí je dostupné pro Intune a k němu se dá získat přístup při použití oken Intune v [Azure Portal](https://portal.azure.com/).
Nové prostředí vám umožňuje popsat problém vlastními slovy a získat přehled možností řešení potíží a postupy z webu, jak problém opravit. Tato řešení jsou nabízená pomocí algoritmu strojového učení založeného na pravidlech, která se řídí dotazy uživatelů. Kromě pokynů specifických pro vydání můžete použít pracovní postup vytvoření nového případu k otevření případu podpory e-mailem nebo telefonem. Toto nové prostředí nahrazuje předchozí pomoc a podporu pro statickou sadu předdefinovaných možností, které jsou založeny na oblasti konzoly, kterou jste v nástroji, když otevřete pomoc a podpora. Další informace najdete v tématu [Jak získat podporu pro Microsoft Intune](get-support.md).

### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="scope-tags-for-apps----1081941---"></a>Značky oboru pro aplikace <!-- 1081941 -->
Můžete vytvořit značky oboru pro omezení přístupu k rolím a aplikacím. Do aplikace můžete přidat značku oboru, aby k ní měl přístup jenom lidé s rolemi přiřazenými k této značce oboru. V současné době se aplikace přidané do Intune ze spravovaných Google Play nebo aplikace zakoupené pomocí Apple Volume Purchase Program (VPP) nedají přiřadit ke značkám oboru (budoucí podpora se plánuje). Další informace najdete v tématu [použití značek oboru k filtrování zásad](scope-tags.md).

## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](../includes/intune-notices.md)]
