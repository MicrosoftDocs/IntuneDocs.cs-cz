---
title: Při vývoji – Microsoft Intune
titleSuffix: ''
description: Microsoft Intune funkce vývoje
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/27/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7150fd7b930e04b375d402877cfe733bb52e9c84
ms.sourcegitcommit: 01a4e09eb27bfed14121de1a4ad56142b7d56eb2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/28/2019
ms.locfileid: "71481989"
---
# <a name="in-development-for-microsoft-intune---october-2019"></a>Ve vývoji Microsoft Intune – říjen 2019

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
## App management
## Device configuration
## Device enrollment
## Device management
## Intune apps
## Monitor and troubleshoot
## Role-based access control
## Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Správa aplikací

### <a name="additional-app-configuration-variable-available----4969237----"></a>Je dostupná další konfigurační proměnná aplikace. <!-- 4969237  -->
Při vytváření zásad konfigurace aplikací budete moct zahrnout konfigurační proměnnou `AAD Device ID` jako součást nastavení konfigurace. V Intune vyberte **klientské aplikace** >  > **zásady konfigurace aplikace** **Přidat**. Zadejte podrobnosti zásady konfigurace a vyberte **nastavení konfigurace** . zobrazí se okno **nastavení konfigurace** .

### <a name="dark-mode-for-ios-company-portal----4911422----"></a>Tmavý režim pro iOS Portál společnosti <!-- 4911422  -->
Pro iOS Portál společnosti se plánuje tmavý režim. Stáhněte si firemní aplikace, Spravujte svá zařízení a získejte podporu v barevném schématu podle vašeho výběru. Další informace o Portál společnosti pro iOS najdete v tématu [Jak konfigurovat aplikaci Microsoft Intune portál společnosti](company-portal-app.md).

### <a name="prevent-installation-of-apps-from-unknown-sources-on-android-enterprise-devices----4760025----"></a>Zabránit instalaci aplikací z neznámých zdrojů na zařízeních s Androidem Enterprise <!-- 4760025  -->
Pro zařízení se systémem Android Enterprise Work Profiles není nikdy možné, aby koncoví uživatelé instalovali aplikace z neznámých zdrojů do pracovního profilu. Toto omezení budete moct volitelně zvětšit i na osobní profil. Pokud toto omezení povolíte, budou se koncovým uživatelům na zařízení s Androidem Enterprise Work profilů z neznámých zdrojů moct z neznámých zdrojů taky bránit na osobní straně zařízení. 

### <a name="update-to-app-protection-ui-and-ios-app-provisioning-ui----4102027-4102029----"></a>Aktualizace uživatelského rozhraní ochrany aplikací a uživatelského rozhraní pro zřizování aplikací pro iOS <!-- 4102027, 4102029  -->
Aktualizuje se uživatelské rozhraní pro vytváření a úpravu zásad ochrany aplikací a zřizovacích profilů aplikací pro iOS v Intune. Změny uživatelského rozhraní zahrnují:
- Zjednodušené prostředí pomocí formátu na úrovni Průvodce zúženého v jednom okně. 
- Aktualizace toku vytváření, který má být zahrnut do přiřazení
- Souhrnná stránka všech věcí nastavená při zobrazení vlastností, před vytvořením nové zásady nebo úpravou vlastnosti. Také při úpravách vlastností se v souhrnu zobrazí pouze seznam položek z kategorie upravovaných vlastností.

### <a name="create-groups-of-management-objects-called-policy-sets----3762880----"></a>Vytvoření skupin objektů pro správu nazývaných sady zásad <!-- 3762880  -->
Sady zásad umožňují vytvořit sadu odkazů na již existující entity správy, které je třeba identifikovat, cílit a monitorovat jako jednu koncepční jednotku. Sady zásad nenahrazují existující koncepty ani objekty. Správce může nadále přiřazovat jednotlivé objekty, když jsou dnes. Jednotlivé objekty jsou odkazovány sadou zásad. Proto se v sadě zásad projeví všechny změny těchto jednotlivých objektů.  V Intune vyberete **sady zásad** > **vytvořit** k vytvoření nové sady zásad. 

### <a name="win32-apps-on-windows-10-s-mode-devices----3747604----"></a>Aplikace Win32 na zařízeních S Windows 10 S v režimu <!-- 3747604  --> 
Aplikace Win32 budete moct instalovat a spouštět na zařízeních spravovaných v režimu Windows 10 S. Pomocí nástrojů PowerShellu pro řízení aplikací v programu Windows Defender (WDAC) budete moci vytvořit jednu nebo více doplňkových zásad pro režim S. Přihlaste doplňkové zásady pomocí registračního portálu pro ochranu zařízení a pak tyto zásady nahrajte a distribuujte prostřednictvím Intune. V Intune tuto možnost najdete tak, že vyberete **klientské aplikace**@no__t**doplňkové zásady Windows 10 S Windows 10**. 

### <a name="set-app-availability-based-on-a-date-and-time----3510685----"></a>Nastavení dostupnosti aplikace na základě data a času <!-- 3510685  -->
Jako správce budete moct nakonfigurovat čas zahájení a konečný termín pro požadovanou aplikaci. V počátečním čase rozšíření pro správu Intune spustí stažení obsahu aplikace a uloží je do mezipaměti. Aplikace se nainstaluje v čase konečného termínu. V případě dostupných aplikací se čas spuštění určí, když se aplikace zobrazí v Portál společnosti. V Intune vyberte**aplikace** **klienta** > aplikace. Pak vyberte konkrétní aplikaci ze seznamu nebo vyberte **Přidat** a přidejte novou aplikaci. V okně aplikace vyberte **přiřazení** > **Přidat skupinu**. Nastavte **Typ přiřazení** na **požadováno** a pak vyberte **zahrnuté skupiny**. Nastavte nastavit **tuto aplikaci jako povinnou pro všechny uživatele** na **Ano** a vyberte **Upravit** a upravte možnosti **prostředí pro koncové uživatele** . V okně **činnost koncového uživatele** nastavte **čas dostupný pro software** podle potřeby. Další informace o přidávání aplikací najdete v tématu [Přidání aplikací do Microsoft Intune](apps-add.md).


### <a name="require-win32-apps-to-restart----3136567----"></a>Vyžadovat restartování aplikací Win32 <!-- 3136567  -->
Budete moct vyžadovat, aby se aplikace Win32 po úspěšné instalaci restartovala. Také budete moci zvolit dobu (dobu odkladu), než se musí vykonat restart.

### <a name="company-portal-app-on-windows----1808082----"></a>Aplikace Portál společnosti ve Windows <!-- 1808082  -->
Aplikace Portál společnosti v zařízeních s Windows se aktualizuje tak, aby zobrazovala informační oznámení uživatelům, i když je aplikace zavřená. Tato aktualizace bude zobrazovat oznámení jenom pro dostupné aplikace, když je stav instalace dokončený nebo se nezdařil. Aplikace Portál společnosti nebude zobrazovat oznámení pro požadované aplikace.

### <a name="company-portal-app-installation-status-messages----2514416----"></a>Portál společnosti stavových zpráv instalace aplikace <!-- 2514416  -->
Aplikace Portál společnosti zobrazí koncovým uživatelům další zprávy o stavu instalace aplikace. Následující podmínky se vztahují na nové funkce závislosti Win32:
- Aplikaci se nepovedlo nainstalovat. Nevyhověly závislosti definované správcem.
- Aplikace byla úspěšně nainstalována, ale vyžaduje restart.
- Aplikace se právě instaluje, ale vyžaduje restart, aby bylo možné pokračovat.

### <a name="assign-microsoft-edge-beta-for-macos----4678761----"></a>Přiřadit Microsoft Edge beta pro macOS <!-- 4678761  -->
Do Intune pro zařízení macOS budete moct přidat a přiřadit nejnovější verzi Microsoft Edge beta. V Intune vyberte**aplikace** >  **klienta** > aplikace**Přidat aplikaci** > **Microsoft Edge – MacOS**. Pak přiřaďte aplikaci Microsoft Edge beta k požadovaným skupinám. Microsoft AutoUpdate (MAU) udržuje Microsoft Edge v aktuálním stavu. Další informace o Microsoft Edge najdete v tématu [Správa webového přístupu pomocí Microsoft Edge s Microsoft Intune](manage-microsoft-edge.md).

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Konfigurace obsahu oznámení aplikace pro účty organizace <!-- 2576686 -->
Zásady ochrany aplikací Intune (aplikace) na zařízeních s Androidem a iOS vám umožní řídit obsah oznámení aplikací pro účty org. Tato funkce bude vyžadovat podporu aplikací a nemusí být k dispozici pro všechny aplikace s podporou aplikací. Další informace o aplikaci najdete v tématu [co jsou zásady ochrany aplikací?](app-protection-policy.md).

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Dostupná Google Play vytváření sestav aplikací pro pracovní profily Androidu <!-- 3041956  -->
Pro dostupná instalace aplikací na zařízeních s pracovním profilem Androidu můžete zobrazit stav instalace aplikace a nainstalovanou verzi spravovaných aplikací Google Play. Další informace najdete v tématu [monitorování zásad ochrany aplikací](app-protection-policies-monitor.md), [Správa zařízení s pracovním profilem Androidu pomocí Intune](android-enterprise-overview.md) a [spravovaného Google Play typu aplikace](apps-add-android-for-work.md#managed-google-play-app-types).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfigurace zařízení

### <a name="new-device-configuration-settings-for-supervised-ios-and-ipados-devices----5199328----"></a>Nové nastavení konfigurace zařízení pro zařízení s iOS a iPadOS pod dohledem <!-- 5199328  -->
Na zařízeních s iOS a iPadOS můžete vytvořit profil, který omezí funkce a nastavení na zařízeních (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS/iPadOS** pro > platformy.  **omezení** pro typ profilu). K dispozici jsou nová nastavení, která můžete řídit: 
- Přístup k síťové jednotce v aplikaci soubory  
- Přístup k jednotce USB v aplikaci soubory 
- Wi-Fi vždycky zapnuté 

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s iOS, abyste mohli povolit nebo zakázat funkce využívající Intune](device-restrictions-ios.md).

Platí pro:
- iOS 13,0 a novější
- iPadOS 13,0 a novější

### <a name="connect-automatically-setting-is-removed-in-wi-fi-profiles-on-android-and-android-enterprise----5021055----"></a>Nastavení připojit automaticky se v profilech Wi-Fi v Androidu a Androidu Enterprise odeberou. <!-- 5021055  -->
V zařízeních s Androidem a Androidem Enterprise můžete vytvořit profil Wi-Fi pro konfiguraci různých nastavení (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android** nebo **Android Enterprise.** pro typ profilu platform > **Wi-Fi** ). Nastavení **Připojit automaticky** se odebere, protože ho [Android nepodporuje](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29). 

Pokud použijete toto nastavení v profilu sítě Wi-Fi, můžete si všimnout, že **Automatické připojení** nebude fungovat. Nemusíte nic dělat, ale mějte na paměti, že toto nastavení se odebere v uživatelském rozhraní Intune.

Pokud chcete zobrazit aktuální nastavení, přejděte na nastavení [Androidu Wi-Fi](wi-fi-settings-android.md) nebo [Nastavení Android Enterprise Wi-Fi](wi-fi-settings-android-enterprise.md).

Platí pro:
- Android
- Android Enterprise

### <a name="create-a-global-http-proxy-on-android-enterprise-device-owner-devices----4816339----"></a>Vytvoření globálního proxy serveru HTTP na zařízeních s vlastníkem zařízení s Androidem Enterprise <!-- 4816339  -->
Na zařízeních s Androidem Enterprise můžete vytvořit profil sítě VPN s různými klienty VPN (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** pro > **vlastníka zařízení > Omezení zařízení** pro typ profilu > **připojení**). Globální proxy server HTTP budete moct nakonfigurovat tak, aby splňoval standardy procházení webu ve vaší organizaci. Všechny aplikace, které jdou na weby HTTP, používají tento proxy server.

Platí pro:
- Vlastník zařízení se systémem Android Enterprise

### <a name="new-device-firmware-configuration-interface-profile-for-windows-10-and-later-devices----2266073----"></a>Nový profil rozhraní pro konfiguraci firmwaru zařízení pro zařízení s Windows 10 a novějším <!-- 2266073  -->
V systému Windows 10 a novějších můžete vytvořit profil konfigurace zařízení pro řízení nastavení a funkcí (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější** pro platformu). Bude se jednat o nový typ profilu rozhraní pro konfiguraci firmwaru zařízení, který umožňuje Intune spravovat nastavení rozhraní UEFI (BIOS).

Přehled všech nastavení, která můžete konfigurovat, najdete v tématu [použití funkcí a nastavení v zařízeních pomocí profilů zařízení v Microsoft Intune](device-profiles.md).

Platí pro:
- Windows 10 RS5 (1809) a novější na některých Výrobcůch OEM

### <a name="pkcs-certificates-for-macos-----1333650------------------"></a>Certifikáty PKCS pro macOS  <!-- 1333650                -->
Do zařízení, na kterých běží macOS, přidáváme plnou podporu certifikátů PKCS. Uživatelé budou moci nasadit certifikáty uživatelů a zařízení s poli přizpůsobení předmět a alternativní název subjektu. Také bude k dispozici nové nastavení Povolit všem aplikacím přístup, což umožňuje všem přidruženým aplikacím přístup k privátnímu klíči. Další podrobnosti o tomto nastavení najdete v následující dokumentaci k Apple: https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf.

###   <a name="derived-credentials-to-provision-mobile-devices-with-certificates----------1736036-1736037-1772050--------"></a>Odvozená pověření pro zřizování mobilních zařízení s certifikáty      <!--  1736036, 1736037, 1772050      --> 
Přidáváme podporu pro odvozené přihlašovací údaje, které pro nasazení certifikátů do zařízení podporují standard *National Institute of Standards and Technology (NIST) 800-157* .  Odvozené přihlašovací údaje spoléhají na použití osobního ověřování identity (PIV) nebo karty Common Access Card (CAC), jako je například čipová karta. Uživatelé se ověřují pomocí své čipové karty v počítači a pak odesílají žádost o certifikát pro spravované zařízení po procesu vyžadovaném odvozeným zprostředkovatelem přihlašovacích údajů.   

Proces použití odvozených přihlašovacích údajů pro získání certifikátu se liší od použití profilů certifikátů SCEP nebo PKCS, ale konečný výsledek je stejný – mobilní zařízení s certifikáty pro ověřování, které se dá použít k ověřování aplikací, VPN, Wi-Fi nebo e-mailu. uživatelů.   

Další informace najdete v tématu [odvozené přihlašovací údaje piv](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) na adrese www.nccoe.nist.gov.

Počáteční verze odvozených přihlašovacích údajů bude podporovat Entrust Datacard, Intercede a DISA purebred v iOS. Další platformy a odvození zprostředkovatelé přihlašovacích údajů budou v novějších verzích podporované.   

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Registrace zařízení

### <a name="specify-which-android-device-operating-system-versions-enroll-with-work-profile-or-device-administrator-enrollment----4350697---"></a>Zadejte, které verze operačního systému zařízení s Androidem se mají zaregistrovat pomocí pracovního profilu nebo registrace Správce zařízení. <!-- 4350697 -->
Pomocí omezení typu zařízení v Intune budete moct použít verzi operačního systému zařízení k určení toho, která zařízení uživatelů budou používat registraci pracovního profilu Android Enterprise nebo Správce zařízení s Androidem. Provedete to tak, že přejdete do služby **Intune** > **registrace zařízení** > **omezení registrace** > **vytvořit omezení** **typu zařízení** >   > **Nastavení platformy**.

### <a name="edit-device-name-value-for-autopilot-devices----4816775---"></a>Upravit hodnotu názvu zařízení pro zařízení s autopilotem <!-- 4816775 -->
Budete moct upravit hodnotu název zařízení pro zařízení autopilotu připojená k Azure AD. Provedete to tak, že přejdete do služby **Intune** > **registrace zařízení**@no__t- **@no__t 3 Windows** **autopilot** > **zařízení** > vyberte > zařízení změnit hodnotu názvu zařízení v pravém podokně > **Uložit** .

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>Pro zařízení s iOS si Přizpůsobte obrazovku ochrana osobních údajů procesu registrace Portál společnosti <!-- 4394993  -->
Pomocí Markdownu budete moci přizpůsobit obrazovku ochrany osobních údajů v Portál společnosti, kterou koncoví uživatelé uvidí během registrace iOS. Konkrétně budete moct přizpůsobit seznam věcí, které vaše organizace nemůže zobrazit nebo dělat na zařízení.

<!-- ***********************************************-->
## <a name="device-management"></a>Správa zařízení

### <a name="edit-group-tag-value-for-autopilot-devices---4816775---"></a>Upravit hodnotu značky skupiny pro zařízení autopilotu<!-- 4816775 -->
Budete moct upravit hodnotu značky skupiny pro zařízení autopilotu. Provedete to tak, že přejdete do služby **Intune** > **registrace zařízení** >  Windows autopilot **@no__t-** 5**zařízení** s**Windows autopilot** >  > vyberte > zařízení změnit hodnotu značky skupiny v pravém podokně > **Uložit** .

### <a name="ui-update-for-creating-and-editing-windows-10-update-rings-----4099089------------"></a>Aktualizace uživatelského rozhraní pro vytváření a úpravy aktualizačních kanálů Windows 10  <!-- 4099089          -->   
Pro aktualizační kanály Windows 10 pro Intune budeme zavádět aktualizované možnosti uživatelského rozhraní pro vytváření a úpravy.  Změny uživatelského rozhraní budou zahrnovat:  
- Zjednodušte stávající prostředí pomocí formátu stylu, který je v jednom okně zhuštěný. Tato aktualizace uživatelského rozhraní se neukončí s oknem neustálému zvětšování, která vyžaduje, aby IT specialisté přešli k podrobnostem o jízdách hloubkového okna.   
- Revidujte vytvoření toku, aby zahrnoval přiřazení.  
- Přidání shrnuté stránky všech věcí nastavených při zobrazení vlastností, před vytvořením nového aktualizačního kanálu a při úpravách vlastnosti. Při úpravách bude v souhrnu zobrazen pouze seznam položek nastavených v rámci jedné kategorie upravovaných vlastností.

### <a name="ui-update-for-creating-and-editing-ios-software-updates-----4099090----------"></a>Aktualizace uživatelského rozhraní pro vytváření a úpravy aktualizací softwaru pro iOS  <!-- 4099090        -->   
Pro aktualizace softwaru iOS do Intune budeme zavádět aktualizované prostředí uživatelského rozhraní pro vytváření a úpravy. Změny uživatelského rozhraní budou zahrnovat:
- Zjednodušte stávající prostředí pomocí formátu stylu, který je v jednom okně zhuštěný. Tato aktualizace uživatelského rozhraní se neukončí s oknem neustálému zvětšování, která vyžaduje, aby IT specialisté přešli k podrobnostem o jízdách hloubkového okna.  
- Zásady aktualizace softwaru pro iOS vytvořit tok se aktualizují tak, aby zahrnovaly přiřazení. 
- Zásady aktualizace softwaru pro iOS budou zahrnovat shrnutou stránku všech věcí nastavených při zobrazení vlastností, před vytvořením nové zásady a při úpravách vlastnosti. Při úpravách bude v souhrnu zobrazen pouze seznam položek nastavených v rámci jedné kategorie upravovaných vlastností.

### <a name="target-macos-user-groups-to-require-jamf-management----4061739---"></a>Cílové skupiny uživatelů macOS, které vyžadují správu Jamf <!-- 4061739 -->
Budete moct cílit na konkrétní skupiny uživatelů a vyžadovat, aby jejich zařízení macOS byla spravovaná pomocí Jamf. Tento cíl vám umožní použít integraci Jamf dodržování předpisů pro podmnožinu zařízení macOS, zatímco ostatní zařízení se budou dál spravovat přes Intune. Umožní vám taky postupně migrovat zařízení uživatelů z jedné MDM do druhé.

### <a name="new-restrictions-for-renaming-windows-devices----3478938---"></a>Nová omezení pro přejmenování zařízení s Windows <!-- 3478938 -->
Názvy zařízení budou muset dodržovat tato pravidla:
- maximálně 15 znaků (musí být menší než nebo rovno 63 bajtů, včetně koncové hodnoty NULL)
- Není null nebo prázdný řetězec
- Povolený formát ASCII: Písmena (a-z, A – Z), číslice (0-9) a spojovníky
- Povolené kódování Unicode: znaky > = 0x80, musí být platný UTF8, musí být možné mapovat na IDN (RtlIdnToNameprepUnicode se podařit, viz RFC 3492)
- Názvy nesmí obsahovat jenom čísla nebo začínat číslicí.
- Žádné mezery v názvu
- Nepovolené znaky: {|} ~ [\] ^ ':; < = >? & @! " # $ % ` ( ) + / , . _ *)

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>Nasazení aktualizací softwaru do zařízení macOS <!-- 3194876 -->
Aktualizace softwaru budete moct nasadit do skupin zařízení macOS. Tato funkce zahrnuje kritické, firmware, konfigurační soubor a další aktualizace. V příští registraci zařízení budete moct odesílat aktualizace, nebo můžete vybrat týdenní plán pro nasazení aktualizací do nebo z časového intervalu, který jste nastavili. Tato funkce pomáhá při aktualizaci zařízení mimo standardní pracovní dobu nebo v případě, že je vaše oddělení technické podpory plně personální. Zobrazí se vám také podrobná sestava všech zařízení macOS s nasazenými aktualizacemi. Pokud chcete zobrazit stav konkrétních aktualizací, můžete přejít k sestavě podle jednotlivých zařízení.

<!-- ***********************************************-->
## <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

### <a name="new-android-report-on-devices-overview-page----2984353----"></a>Stránka Přehled nové sestavy pro Android na zařízeních <!-- 2984353  -->
Na stránku Přehled zařízení přidáváme novou sestavu, která zobrazuje počet zaregistrovaných zařízení s Androidem v jednotlivých řešeních pro správu zařízení. V tomto grafu se zobrazí počet zaregistrovaných zařízení s profilem práce, plně spravovaným, vyhrazeným a správcem zařízení. Pokud chcete zobrazit sestavu, vyberte @no__t**zařízení** **Intune**– 1  >  **– Přehled**.

### <a name="windows-autopilot-deployment-reports----3856172----"></a>Sestavy nasazení Windows autopilot <!-- 3856172  -->
Nová sestava podrobná na každé zařízení nasazené prostřednictvím Windows autopilotu. Tato data budou k dispozici po dobu 30 dnů od nasazení. Pokud chcete zobrazit sestavu, přejděte na **Intune** > **registrace zařízení** > **monitorovat** **nasazení autopilotu** > .

### <a name="updated-support-experience-------5012398------"></a>Aktualizované prostředí podpory   <!--  5012398    -->
V rámci pokračujících vylepšení budeme aktualizovat prostředí podpory v konzole pro Intune.  Budeme zdokonalovat hledání v konzole a zpětná vazba pro běžné problémy a zjednodušit pracovní postup, aby kontaktoval podporu.     

<!-- ***********************************************-->
<!--## Security-->


<!-- ***********************************************-->
## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).




