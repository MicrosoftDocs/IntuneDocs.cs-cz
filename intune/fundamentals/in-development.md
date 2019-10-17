---
title: Při vývoji – Microsoft Intune
titleSuffix: ''
description: Microsoft Intune funkce vývoje
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: fa3309cc1aad3f82499e37cf0d009da336b15cca
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502774"
---
# <a name="in-development-for-microsoft-intune---october-2019"></a>Ve vývoji Microsoft Intune – říjen 2019

Tato stránka vám umožní v rámci připravenosti a plánování vypsat aktualizace uživatelského rozhraní Intune a funkce, které jsou ve vývoji, ale ještě nejsou vydané. Kromě informací na této stránce:

- Pokud předpokládáme, že před změnou budete muset provést nějakou akci, zveřejníme doplňkový příspěvek v centru zpráv Office.
- Pokud funkce vstoupí do produkčního prostředí, ať už je verze Preview, nebo je všeobecně dostupná, popis funkce se přesune z této stránky na [co je nového](whats-new.md).
- Tato stránka a stránka [co je nového](whats-new.md) se pravidelně aktualizují. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.
- Strategické dodávky a časová osa najdete v tématu [Microsoft 365 plán](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) .

> [!NOTE]
> Tato stránka odráží naše aktuální očekávání na možnosti Intune v budoucí verzi. Data a jednotlivé funkce se můžou změnit. Tato stránka nepopisuje všechny funkce vývoje.

**Informační kanál RSS**: Zjistěte, kdy se tato stránka aktualizuje zkopírováním a vložením následující adresy URL do čtečky informačních kanálů: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

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

### <a name="include-another-app-configuration-variable----4969237----"></a>Zahrnout jinou konfigurační proměnnou aplikace <!-- 4969237  -->
Při vytváření zásad konfigurace aplikací budete moct zahrnout konfigurační proměnnou `AAD Device ID` jako součást nastavení konfigurace. 

Postup přidání konfigurační proměnné `AAD Device ID`:
1. V Intune vyberte **klientské aplikace** > **zásady konfigurace aplikace** > **Přidat**. 
1. Zadejte podrobnosti zásad konfigurace.
1. Chcete-li zobrazit okno **nastavení konfigurace** , vyberte možnost **nastavení konfigurace**.

### <a name="apply-dark-mode-in-ios-company-portal----4911422----"></a>Použití tmavého režimu v iOS Portál společnosti <!-- 4911422  -->
Pro iOS Portál společnosti se plánuje tmavý režim. Budete moct stahovat firemní aplikace, spravovat zařízení a získávat podporu v barevném schématu podle vašeho výběru. Další informace o Portál společnosti iOS najdete v tématu [Jak konfigurovat aplikaci Microsoft Intune portál společnosti](../apps/company-portal-app.md).

### <a name="prevent-installation-of-apps-from-unknown-sources-on-android-enterprise-devices----4760025----"></a>Zabránit instalaci aplikací z neznámých zdrojů na zařízeních s Androidem Enterprise <!-- 4760025  -->
Na zařízeních se systémem Android Enterprise Work Profiles můžou koncoví uživatelé nikdy instalovat aplikace z neznámých zdrojů v pracovním profilu. Toto omezení budete moct zvolit i pro toto omezení i na osobní profil. Pokud toto omezení povolíte, koncoví uživatelé na zařízeních s Androidem Enterprise Work profilování nebudou moct aplikace načítat z neznámých zdrojů na osobní stranu zařízení. 

### <a name="use-an-updated-app-protection-ui-and-ios-app-provisioning-ui----4102027-4102029----"></a>Použití aktualizovaného uživatelského rozhraní ochrany aplikací a uživatelského rozhraní pro zřizování aplikací pro iOS <!-- 4102027, 4102029  -->
Aktualizujeme uživatelské rozhraní tak, aby v Intune vytvořil a upravil zásady ochrany aplikací (aplikace) a zřizovací profily aplikací pro iOS. Změny uživatelského rozhraní zahrnují:
- Zjednodušené prostředí, které v jednom okně používá formát ve stylu průvodce. 
- Aktualizace toku vytváření, který má být zahrnut do přiřazení
- Souhrn. Když před vytvořením nové zásady nebo úpravou vlastnosti zobrazíte její vlastnosti, uvidíte stránku souhrnu všech nastavení. V souhrnu se také při úpravách vlastností zobrazí seznam pouze položek z kategorie vlastností, které upravujete.

### <a name="create-groups-of-management-objects-called-policy-sets----3762880----"></a>Vytvoření skupin objektů pro správu nazývaných sady zásad <!-- 3762880  -->
*Sady zásad* budete moct použít k vytvoření sady odkazů na existující entity správy, které je potřeba identifikovat, cílit a monitorovat jako jednu koncepční jednotku. Sady zásad nenahrazují existující koncepty ani objekty. Správci mohou nadále přiřazovat jednotlivé objekty, když jsou dnes. Sady zásad odkazují na jednotlivé objekty. Proto se v sadě zásad projeví všechny změny těchto jednotlivých objektů. 

Pokud chcete v Intune vytvořit sadu zásad, vyberte **sady zásad** > **vytvořit**. 

### <a name="run-win32-apps-on-windows-10-s-mode-devices----3747604----"></a>Spouštění aplikací Win32 v zařízeních S Windows 10 S v režimu <!-- 3747604  --> 
Aplikace Win32 budete moct instalovat a spouštět na zařízeních spravovaných v režimu Windows 10 S. Pomocí nástrojů PowerShellu pro řízení aplikací v programu Windows Defender (WDAC) vytvořte jednu nebo více doplňkových zásad pro režim S. Pro podepsání doplňkových zásad použijte registrační portál pro ochranu zařízení. Pak tyto zásady nahrajte a distribuujte prostřednictvím Intune. 

V Intune tuto možnost najdete tak, že vyberete **klientské aplikace**@no__t**doplňkové zásady Windows 10 S Windows 10**. 

### <a name="set-app-availability-based-on-a-date-and-time----3510685----"></a>Nastavení dostupnosti aplikace na základě data a času <!-- 3510685  -->
Jako správce budete moct nakonfigurovat čas zahájení a termín pro požadovanou aplikaci. V počátečním čase rozšíření pro správu Intune stáhne obsah aplikace a uloží je do mezipaměti. Aplikace se nainstaluje v čase konečného termínu. V případě dostupných aplikací se čas spuštění určí při zobrazení aplikace v Portál společnosti. 

Nastavení dostupnosti aplikace na základě data a času:

1. V Intune vyberte **klientské aplikace** > **aplikace**. 
1. Vyberte aplikaci ze seznamu nebo přidejte novou kliknutím na tlačítko **Přidat**. 
1. V okně aplikace vyberte **přiřazení** > **Přidat skupinu**. 
1. Nastavte **Typ přiřazení** na **požadováno** a pak vyberte **zahrnuté skupiny**. 
1. Nastavte nastavit **tuto aplikaci jako povinnou pro všechny uživatele** na **Ano**. 
1. Vyberte **Upravit** a upravte možnosti **prostředí pro koncové uživatele** . 
1. V okně **činnost koncového uživatele** nastavte **čas dostupný pro software** podle potřeby. 

Další informace najdete v článku [Přidání aplikací do Microsoft Intune](../apps/apps-add.md).

### <a name="require-win32-apps-to-restart----3136567----"></a>Vyžadovat restartování aplikací Win32 <!-- 3136567  -->
Po úspěšné instalaci budete moct vyžadovat, aby se aplikace Win32 restartovala. Můžete zvolit dobu (dobu odkladu) před restartováním.

### <a name="display-notifications-for-the-company-portal-app-on-windows----1808082----"></a>Zobrazit oznámení pro aplikaci Portál společnosti ve Windows <!-- 1808082  -->
Aplikaci Portál společnosti na zařízeních s Windows aktualizujeme tak, aby zobrazovala informační oznámení uživatelům, a to i v případě, že je aplikace uzavřená. Tato aktualizace bude zobrazovat oznámení pro dostupné aplikace pouze v případě, že je stav instalace dokončen nebo se nezdařil. Aplikace Portál společnosti nebude zobrazovat oznámení pro požadované aplikace.

### <a name="display-installation-status-messages-for-the-company-portal-app----2514416----"></a>Zobrazit stavové zprávy instalace pro aplikaci Portál společnosti <!-- 2514416  -->
Aplikace Portál společnosti zobrazí koncovým uživatelům další zprávy o stavu instalace aplikace. Následující podmínky se vztahují na nové funkce závislosti Win32:
- Aplikaci se nepovedlo nainstalovat. Nevyhověly závislosti definované správcem.
- Aplikace byla úspěšně nainstalována, ale vyžaduje restart.
- Aplikace se právě instaluje, ale vyžaduje restart, aby bylo možné pokračovat.

### <a name="assign-the-microsoft-edge-beta-for-macos----4678761----"></a>Přiřadit Microsoft Edge beta pro macOS <!-- 4678761  -->
Do Intune pro zařízení macOS budete moct přidat a přiřadit nejnovější verzi Microsoft Edge beta. 

Přiřazení Microsoft Edge beta pro zařízení macOS:
1. V Intune vyberte **klientské aplikace** > **aplikace** > **Přidat aplikaci** > **Microsoft Edge-MacOS**. 
1. Přiřaďte Microsoft Edge beta k určeným skupinám. Microsoft AutoUpdate (MAU) udržuje Microsoft Edge v aktuálním stavu. 
 
Další informace o Microsoft Edge najdete v tématu [Správa webového přístupu pomocí Microsoft Edge s Microsoft Intune](../apps/manage-microsoft-edge.md).

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Konfigurace obsahu oznámení aplikace pro účty organizace <!-- 2576686 -->
APLIKACE Intune na zařízeních s Androidem a iOS vám umožní řídit obsah oznámení aplikací pro účty organizace. Tato funkce bude vyžadovat podporu aplikací a nemusí být k dispozici pro všechny aplikace s podporou aplikací. Další informace o aplikaci najdete v tématu [co jsou zásady ochrany aplikací?](../apps/app-protection-policy.md)

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Dostupná Google Play vytváření sestav aplikací pro pracovní profily Androidu <!-- 3041956  -->
Pro dostupné instalace aplikací na zařízeních s pracovním profilem Androidu můžete zobrazit stav instalace aplikace a nainstalovanou verzi spravovaných aplikací Google Play. Další informace najdete v tématech [monitorování zásad ochrany aplikací](../apps/app-protection-policies-monitor.md), [Správa zařízení s pracovním profilem Androidu pomocí Intune](../enrollment/android-enterprise-overview.md)a [spravovaných Google Play typů aplikací](../apps/apps-add-android-for-work.md#managed-google-play-app-types).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfigurace zařízení


### <a name="new-device-configuration-settings-for-supervised-ios-and-ipados-devices----5199328----"></a>Nové nastavení konfigurace zařízení pro zařízení s iOS a iPadOS pod dohledem <!-- 5199328  -->
Na zařízeních s iOS a iPadOS můžete vytvořit profil, který omezí funkce a nastavení na zařízeních:

1. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
1. Pro platformu vyberte **iOS/iPadOS**.
1. Jako typ profilu vyberte **omezení zařízení**.

Budete moci řídit nová nastavení: 
- Přístup k síťové jednotce v aplikaci soubory  
- Přihlaste se k jednotce USB v aplikaci soubory. 
- Udržujte Wi-Fi na. 

Informace o aktuálním nastavení najdete v tématu [nastavení zařízení s iOS pro povolení nebo omezení funkcí využívajících Intune](../configuration/device-restrictions-ios.md).

Nové nastavení platí pro:
- iOS 13,0 a novější.
- iPadOS 13,0 a novější.

### <a name="removal-of-automatic-connection-in-wi-fi-profiles-on-android-and-android-enterprise----5021055----"></a>Odebrání automatického připojení v profilech sítě Wi-Fi v Androidu a Androidu Enterprise <!-- 5021055  -->
V zařízeních s Androidem a Androidem Enterprise můžete vytvořit profil Wi-Fi pro konfiguraci různých nastavení: 

1. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
1. Jako platformu vyberte **Android** nebo **Android Enterprise**.
1. Jako typ profilu vyberte **Wi-Fi**. 

Nastavení **Připojit automaticky** se odebere, protože ho nepodporuje [Android](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29).

Pokud použijete toto nastavení v profilu sítě Wi-Fi, může se stát, že se **připojení automaticky** nepracuje. Nemusíte provádět žádnou akci, ale mějte na paměti, že toto nastavení se odebere z uživatelského rozhraní Intune.

Informace o aktuálním nastavení najdete v nastavení [Wi-Fi nastavení pro Android](../configuration/wi-fi-settings-android.md) nebo v [Nastavení Android Enterprise Wi-Fi](../configuration/wi-fi-settings-android-enterprise.md).

Odebrání tohoto nastavení platí pro:
- Svém.
- Android Enterprise.

### <a name="global-http-proxy-on-android-enterprise-devices----4816339----"></a>Globální proxy server HTTP na zařízeních s Androidem Enterprise <!-- 4816339  -->
Na zařízeních s Androidem Enterprise budete moct nakonfigurovat globální proxy server HTTP tak, aby splňoval standardy procházení webu ve vaší organizaci:

1. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
1. V části platforma vyberte **Android Enterprise**.
1. Vyberte **vlastníka zařízení**.
1. Jako typ profilu vyberte **omezení zařízení**. 
1. Vyberte možnost **připojení**. 
 
Po nakonfigurování proxy serveru ho budou používat všechny přenosy HTTP. Tato funkce se vztahuje na zařízení s Androidem Enterprise, která jsou v režimu vlastníka zařízení.

### <a name="new-device-firmware-configuration-interface-profile-for-devices-that-run-windows-10-and-later----2266073----"></a>Nový profil rozhraní pro konfiguraci firmwaru zařízení pro zařízení se systémem Windows 10 nebo novějším <!-- 2266073  -->
V systému Windows 10 a novějších můžete vytvořit profil konfigurace zařízení pro řízení nastavení a funkcí: 

1. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
1. Pro platformu vyberte **Windows 10 a novější**. 
 
Nový typ profilu rozhraní pro konfiguraci firmwaru zařízení umožní, aby Intune spravovalo nastavení rozhraní UEFI (BIOS).

Informace o aktuálních nastaveních, která můžete konfigurovat, najdete v tématu [použití funkcí a nastavení na zařízeních pomocí profilů zařízení v Microsoft Intune](../configuration/device-profiles.md).

Tato funkce se vztahuje na Windows 10 RS5 (1809) a novější na vybraných zařízeních.

### <a name="pkcs-certificates-for-macos-----1333650------------------"></a>Certifikáty PKCS pro macOS  <!-- 1333650                -->
Do zařízení, na kterých běží macOS, přidáme plnou podporu certifikátů PKCS (Public Key Cryptography Standards). Uživatelé budou moci nasadit certifikáty uživatelů a zařízení s poli pro **Předmět přizpůsobení** a **alternativní název subjektu**. 

Také bude k dispozici nové nastavení s názvem **Povolení přístupu ke všem aplikacím**. Povolením tohoto nastavení udělíte všem přidruženým aplikacím přístup k privátnímu klíči. Další informace o tomto nastavení najdete v tématu [Referenční dokumentace ke konfiguračnímu profilu](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf) na Developer.Apple.com.

### <a name="derived-credentials-to-provision-mobile-devices-with-certificates----------1736036-1736037-1772050--------"></a>Odvozená pověření pro zřizování mobilních zařízení s certifikáty      <!--  1736036, 1736037, 1772050      --> 
Přidáváme podporu pro odvozené přihlašovací údaje, které pro nasazení certifikátů do zařízení podporují standard *National Institute of Standards and Technology (NIST) 800-157* .  Odvozené přihlašovací údaje spoléhají na použití osobního ověřování identity (PIV) nebo Common Access Card (CAC), jako je například čipová karta. Uživatelé se ověřují pomocí své čipové karty v počítači. Pak si vyžádají certifikát pro své spravované zařízení podle procesu, který vyžaduje odvozený zprostředkovatel přihlašovacích údajů.   

Proces použití odvozených přihlašovacích údajů pro získání certifikátu se liší od procesů, které používají profily certifikátů SCEP nebo PKCS. Ale výsledek je stejný: mobilní zařízení s ověřovacími certifikáty, které se dají použít pro ověřování aplikací, sítě VPN, Wi-Fi nebo e-mailové profily. Další informace najdete v tématu [odvozené přihlašovací údaje piv](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) v NCCOE. NIST.gov.

Počáteční verze odvozených přihlašovacích údajů bude podporovat Entrust Datacard, Intercede a DISA purebred v iOS. Další platformy a odvození zprostředkovatelé přihlašovacích údajů budou v novějších verzích podporované.   

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Registrace zařízení

### <a name="specify-which-android-device-os-versions-enroll-through-the-work-profile-and-which-enroll-through-the-device-administrator----4350697---"></a>Zadejte, které verze operačních systémů zařízení s Androidem se mají zapsat přes pracovní profil a které se zapisují přes Správce zařízení. <!-- 4350697 -->
Když použijete omezení typu zařízení v Intune, budete moct použít verzi operačního systému zařízení a určit, jestli se bude používat registrace pracovního profilu Android Enterprise nebo Správce zařízení s Androidem. Provedete to tak, že v Intune vyberete **registrace zařízení** > **omezení registrace**@no__t **-3** **Nastavení platformy**omezení @no__t**typu** > .

### <a name="edit-the-device-name-value-for-autopilot-devices----4816775---"></a>Upravit hodnotu názvu zařízení pro zařízení s autopilotem <!-- 4816775 -->
Pro zařízení s autopilotem připojená k Azure AD budete moct upravit hodnotu **název zařízení** :

1. Vyberte **Intune** > **registrace zařízení** >  registrace**Windows** > **zařízení**s Windows**autopilot** > .
1. Vyberte zařízení.
1. V pravém podokně změňte hodnotu **název zařízení** .
1. Vyberte **Uložit**.

### <a name="for-ios-devices-customize-the-enrollment-privacy-window-of-company-portal----4394993----"></a>V případě zařízení se systémem iOS upravte okno soukromí registrace Portál společnosti <!-- 4394993  -->
Pomocí Markdownu budete moci přizpůsobit okno ochrany osobních údajů Portál společnosti, které koncoví uživatelé uvidí během registrace iOS. Konkrétně můžete přizpůsobit seznam věcí, které vaše organizace nemůže zobrazit nebo dělat na zařízení.

<!-- ***********************************************-->
## <a name="device-management"></a>Správa zařízení


### <a name="edit-the-group-tag-value-for-autopilot-devices---4816775---"></a>Úprava hodnoty značky skupiny pro zařízení autopilotu<!-- 4816775 -->
Budete moct upravit hodnotu **značky skupiny** pro zařízení autopilotu:

1. Vyberte **Intune** > **registrace zařízení** >  registrace**Windows** > **zařízení**s Windows**autopilot** > .
1. Vyberte zařízení.
1. V pravém podokně změňte hodnotu **značky skupiny** .
1. Vyberte **Uložit**.

### <a name="ui-update-for-creating-and-editing-windows-10-update-rings-----4099089------------"></a>Aktualizace uživatelského rozhraní pro vytváření a úpravy aktualizačních kanálů Windows 10  <!-- 4099089          -->   
Pro aktualizační kanály Windows 10 zavedeme aktualizované prostředí pro vytváření a úpravu uživatelského rozhraní. Nové uživatelské rozhraní bude:  
- Zjednodušte stávající prostředí pomocí formátu na jednom okně v podobě stylu průvodce. Tato aktualizace uživatelského rozhraní eliminuje okno neustálému zvětšování, které vyžaduje, aby odborníci na IT přijali hloubkovou jízdu.   
- Revidujte vytvoření toku, aby zahrnoval přiřazení.  
- Přidejte stránku souhrnu. Shrnutí bude zahrnovat všechna nastavení při prohlížení vlastností, při přípravě na vytvoření aktualizačního kanálu a při úpravách vlastnosti. Při úpravách bude v souhrnu uveden seznam pouze položek v kategorii vlastností, které upravujete.

### <a name="ui-update-for-creating-and-editing-ios-software-updates-----4099090----------"></a>Aktualizace uživatelského rozhraní pro vytváření a úpravy aktualizací softwaru pro iOS  <!-- 4099090        -->   
Pro aktualizace softwaru pro iOS v Intune zavedeme aktualizované prostředí pro vytváření a úpravu uživatelského rozhraní. Nové uživatelské rozhraní bude:
- Zjednodušte stávající prostředí pomocí formátu na jednom okně v podobě stylu průvodce. Tato aktualizace uživatelského rozhraní eliminuje okno neustálému zvětšování, které vyžaduje, aby odborníci na IT přijali hloubkovou jízdu.  
- Zahrnout přiřazení do zásad aktualizace softwaru pro iOS vytvořit tok. 
- V zásadách aktualizace softwaru pro iOS zahrňte stránku souhrnu. Shrnutí bude zahrnovat všechna nastavení při prohlížení vlastností, při přípravě na vytvoření zásady a při úpravách vlastnosti. Při úpravách bude v souhrnu uveden seznam pouze položek v kategorii vlastností, které upravujete.

### <a name="target-macos-user-groups-to-require-jamf-management----4061739---"></a>Cílové skupiny uživatelů macOS, které vyžadují správu Jamf <!-- 4061739 -->
Budete moct cílit na konkrétní skupiny uživatelů, aby se zařízení macOS mohla spravovat pomocí Jamf. Tento cíl vám umožní použít integraci Jamf dodržování předpisů pro podmnožinu zařízení macOS, zatímco ostatní zařízení se budou dál spravovat přes Intune. Cílení taky vám umožní postupně migrovat zařízení uživatelů z jednoho systému správy mobilních zařízení (MDM) do druhého.

### <a name="new-restrictions-for-renaming-windows-devices----3478938---"></a>Nová omezení pro přejmenování zařízení s Windows <!-- 3478938 -->
Názvy zařízení budou muset dodržovat tato pravidla:
- maximálně 15 znaků (je menší než nebo rovno 63 bajtů, včetně koncové hodnoty NULL)
- Žádné hodnoty null ani prázdné řetězce
- Povolené znakové sady ASCII: písmena (a-z, A – Z), číslice (0-9) a spojovníky
- Povolené kódování Unicode: znaků > = 0x80, platný UTF8, namapovatelné na IDN (RtlIdnToNameprepUnicode se podařilo; viz RFC 3492)
- Názvy nesmí obsahovat jenom čísla nebo začínat číslicí.
- Žádné mezery v názvu
- Nepovolené znaky: {|} ~ [\] ^ ':; < = >? & @! " # $ % ` ( ) + / , . _ *

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>Nasazení aktualizací softwaru do zařízení macOS <!-- 3194876 -->
Aktualizace softwaru budete moct nasadit do skupin zařízení macOS. Tato funkce zahrnuje kritické, firmware, konfigurační soubor a další aktualizace. Aktualizace můžete odeslat při dalším vrácení se změnami zařízení. Případně můžete vybrat týdenní plán pro nasazení aktualizací do nebo z období, které jste nastavili. 

Tato funkce pomůže, když budete chtít aktualizovat zařízení mimo standardní pracovní dobu nebo mimo pracovní dobu, kdy je vaše oddělení technické podpory plně personální. Zobrazí se také podrobná sestava všech zařízení macOS, ve kterých jsou nasazené aktualizace. Chcete-li zobrazit stav konkrétní aktualizace, můžete přejít k sestavě podle zařízení.

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>Monitorování a řešení potíží

### <a name="android-report-on-the-devices-overview-page----2984353----"></a>Sestava Android na stránce s přehledem zařízení <!-- 2984353  -->
Přidáme novou sestavu na stránku **Přehled zařízení** . V této sestavě se zobrazuje počet zaregistrovaných zařízení s Androidem v jednotlivých řešeních pro správu zařízení. V grafu se zobrazuje počet zařízení pro pracovní profil, plně spravovaný, vyhrazený a registrovaný Správce zařízení. 

Pokud chcete zobrazit sestavu, vyberte @no__t**zařízení** **Intune**– 1  >  **– Přehled**.

### <a name="windows-autopilot-deployment-reports----3856172----"></a>Sestavy nasazení Windows autopilot <!-- 3856172  -->
Nová sestava podrobná na každé zařízení nasazené prostřednictvím Windows autopilotu. Tato data budou k dispozici po dobu 30 dnů od nasazení. 

Pokud chcete zobrazit sestavu, přejděte na **Intune** > **registrace zařízení** > **monitorovat** **nasazení autopilotu** > .

### <a name="updated-support-experience-------5012398------"></a>Aktualizované prostředí podpory   <!--  5012398    -->
V rámci pokračujících vylepšení aktualizujeme prostředí podpory v konzole pro Intune.  Vyřešíme vyhledávání v konzole a zpětnou vazbu k běžným problémům a my Zjednodušme pracovní postup, abychom kontaktovali podporu.     

<!-- ***********************************************-->
<!--## Security-->


<!-- ***********************************************-->
## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Související témata
Podrobnosti o posledním vývoji najdete v tématu [co je nového v Microsoft Intune](whats-new.md).
