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
ms.openlocfilehash: 6c88dca505c3ef9d9d552e55e9991679f5f5e0fa
ms.sourcegitcommit: 5968a38c302394d4b0cf81156e7b52531cdec107
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/23/2019
ms.locfileid: "71198819"
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

### <a name="company-portal-app-installation-status-messages----2514416----"></a>Portál společnosti stavových zpráv instalace aplikace <!-- 2514416  -->
Aplikace Portál společnosti zobrazí koncovým uživatelům další zprávy o stavu instalace aplikace. Následující podmínky se vztahují na nové funkce závislosti Win32:
- Aplikaci se nepovedlo nainstalovat. Nevyhověly závislosti definované správcem.
- Aplikace byla úspěšně nainstalována, ale vyžaduje restart.
- Aplikace se právě instaluje, ale vyžaduje restart, aby bylo možné pokračovat.

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

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Konfigurace obsahu oznámení aplikace pro účty organizace <!-- 2576686 -->
Zásady ochrany aplikací Intune (aplikace) na zařízeních s Androidem a iOS vám umožní řídit obsah oznámení aplikací pro účty org. Tato funkce bude vyžadovat podporu aplikací a nemusí být k dispozici pro všechny aplikace s podporou aplikací. Další informace o aplikaci najdete v tématu [co jsou zásady ochrany aplikací?](app-protection-policy.md).

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Dostupná Google Play vytváření sestav aplikací pro pracovní profily Androidu <!-- 3041956  -->
Pro dostupná instalace aplikací na zařízeních s pracovním profilem Androidu můžete zobrazit stav instalace aplikace a nainstalovanou verzi spravovaných aplikací Google Play. Další informace najdete v tématu [monitorování zásad ochrany aplikací](app-protection-policies-monitor.md), [Správa zařízení s pracovním profilem Androidu pomocí Intune](android-enterprise-overview.md) a [spravovaného Google Play typu aplikace](apps-add-android-for-work.md#managed-google-play-app-types).

<!-- ***********************************************-->
<!--## Device configuration-->

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Registrace zařízení

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>Pro zařízení s iOS si Přizpůsobte obrazovku ochrana osobních údajů procesu registrace Portál společnosti <!-- 4394993  -->
Pomocí Markdownu budete moci přizpůsobit obrazovku ochrany osobních údajů v Portál společnosti, kterou koncoví uživatelé uvidí během registrace iOS. Konkrétně budete moct přizpůsobit seznam věcí, které vaše organizace nemůže zobrazit nebo dělat na zařízení.

<!-- ***********************************************-->
## <a name="device-management"></a>Správa zařízení

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>Nasazení aktualizací softwaru do zařízení macOS <!-- 3194876 -->
Aktualizace softwaru budete moct nasadit do skupin zařízení macOS. Tato funkce zahrnuje kritické, firmware, konfigurační soubor a další aktualizace. V příští registraci zařízení budete moct odesílat aktualizace, nebo můžete vybrat týdenní plán pro nasazení aktualizací do nebo z časového intervalu, který jste nastavili. To pomáhá při aktualizaci zařízení mimo standardní pracovní dobu nebo v případě, že je vaše Helpdesk plně přiřazená. Zobrazí se vám také podrobná sestava všech zařízení macOS s nasazenými aktualizacemi. Pokud chcete zobrazit stav konkrétních aktualizací, můžete přejít k sestavě podle jednotlivých zařízení.

<!-- ***********************************************-->
## <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

### <a name="updated-support-experience-------5012398------"></a>Aktualizované prostředí podpory   <!--  5012398    -->
V rámci pokračujících vylepšení budeme aktualizovat prostředí podpory v konzole pro Intune.  Budeme zdokonalovat hledání v konzole a zpětná vazba pro běžné problémy a zjednodušit pracovní postup, aby kontaktoval podporu.     

<!-- ***********************************************-->
<!--## Security-->


<!-- ***********************************************-->
## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).




