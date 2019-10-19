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
ms.openlocfilehash: ea5fae72f6e2057ef0b03a7bd295085ed1ac3bbd
ms.sourcegitcommit: 5807f4db4a45a093ce2fd6cb0c480bec384ec1ff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72601522"
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

### <a name="apply-dark-mode-in-ios-company-portal----4911422----"></a>Použití tmavého režimu v iOS Portál společnosti <!-- 4911422  -->
Pro iOS Portál společnosti se plánuje tmavý režim. Budete moct stahovat firemní aplikace, spravovat zařízení a získávat podporu v barevném schématu podle vašeho výběru. Další informace o Portál společnosti iOS najdete v tématu [Jak konfigurovat aplikaci Microsoft Intune portál společnosti](../apps/company-portal-app.md).

### <a name="run-win32-apps-on-windows-10-s-mode-devices----3747604----"></a>Spouštění aplikací Win32 v zařízeních S Windows 10 S v režimu <!-- 3747604  --> 
Aplikace Win32 budete moct instalovat a spouštět na zařízeních spravovaných v režimu Windows 10 S. Pomocí nástrojů PowerShellu pro řízení aplikací v programu Windows Defender (WDAC) vytvořte jednu nebo více doplňkových zásad pro režim S. Pro podepsání doplňkových zásad použijte registrační portál pro ochranu zařízení. Pak tyto zásady nahrajte a distribuujte prostřednictvím Intune. 

V Intune tuto možnost najdete tak, že vyberete **klientské aplikace**  > **doplňkové zásady Windows 10 S**. 

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


<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfigurace zařízení

### <a name="new-device-firmware-configuration-interface-profile-for-devices-that-run-windows-10-and-later----2266073----"></a>Nový profil rozhraní pro konfiguraci firmwaru zařízení pro zařízení se systémem Windows 10 nebo novějším <!-- 2266073  -->
V systému Windows 10 a novějších můžete vytvořit profil konfigurace zařízení pro řízení nastavení a funkcí: 

1. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
1. Pro platformu vyberte **Windows 10 a novější**. 
 
Nový typ profilu rozhraní pro konfiguraci firmwaru zařízení umožní, aby Intune spravovalo nastavení rozhraní UEFI (BIOS).

Informace o aktuálních nastaveních, která můžete konfigurovat, najdete v tématu [použití funkcí a nastavení na zařízeních pomocí profilů zařízení v Microsoft Intune](../configuration/device-profiles.md).

Tato funkce se vztahuje na Windows 10 RS5 (1809) a novější na vybraných zařízeních.
 

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Registrace zařízení

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

### <a name="target-macos-user-groups-to-require-jamf-management----4061739---"></a>Cílové skupiny uživatelů macOS, které vyžadují správu Jamf <!-- 4061739 -->
Budete moct cílit na konkrétní skupiny uživatelů, aby se zařízení macOS mohla spravovat pomocí Jamf. Tento cíl vám umožní použít integraci Jamf dodržování předpisů pro podmnožinu zařízení macOS, zatímco ostatní zařízení se budou dál spravovat přes Intune. Cílení taky vám umožní postupně migrovat zařízení uživatelů z jednoho systému správy mobilních zařízení (MDM) do druhého.

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>Nasazení aktualizací softwaru do zařízení macOS <!-- 3194876 -->
Aktualizace softwaru budete moct nasadit do skupin zařízení macOS. Tato funkce zahrnuje kritické, firmware, konfigurační soubor a další aktualizace. Aktualizace můžete odeslat při dalším vrácení se změnami zařízení. Případně můžete vybrat týdenní plán pro nasazení aktualizací do nebo z období, které jste nastavili. 

Tato funkce pomůže, když budete chtít aktualizovat zařízení mimo standardní pracovní dobu nebo mimo pracovní dobu, kdy je vaše oddělení technické podpory plně personální. Zobrazí se také podrobná sestava všech zařízení macOS, ve kterých jsou nasazené aktualizace. Chcete-li zobrazit stav konkrétní aktualizace, můžete přejít k sestavě podle zařízení.

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>Monitorování a řešení potíží

### <a name="android-report-on-the-devices-overview-page----2984353----"></a>Sestava Android na stránce s přehledem zařízení <!-- 2984353  -->
Přidáme novou sestavu na stránku **Přehled zařízení** . V této sestavě se zobrazuje počet zaregistrovaných zařízení s Androidem v jednotlivých řešeních pro správu zařízení. V grafu se zobrazuje počet zařízení pro pracovní profil, plně spravovaný, vyhrazený a registrovaný Správce zařízení. 

Pokud chcete zobrazit sestavu, vyberte  > **zařízení** **Intune**  > **Přehled**.

### <a name="updated-support-experience-------5012398------"></a>Aktualizované prostředí podpory   <!--  5012398    -->
V rámci pokračujících vylepšení aktualizujeme prostředí podpory v konzole pro Intune.  Vyřešíme vyhledávání v konzole a zpětnou vazbu k běžným problémům a my Zjednodušme pracovní postup, abychom kontaktovali podporu.     

<!-- ***********************************************-->
<!--## Security-->


<!-- ***********************************************-->
## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Související témata
Podrobnosti o posledním vývoji najdete v tématu [co je nového v Microsoft Intune](whats-new.md).
