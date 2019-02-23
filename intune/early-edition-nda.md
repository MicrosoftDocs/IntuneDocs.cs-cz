---
title: Časná edice – Microsoft Intune
titlesuffix: ''
description: Časná edice Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b1ff65e1b48815cd5964aa7498fa6ba54df50e09
ms.sourcegitcommit: e5f501b396cb8743a8a9dea33381a16caadc51a9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/23/2019
ms.locfileid: "56742291"
---
# <a name="the-early-edition-for-microsoft-intune---february-2019"></a>Časná edice Microsoft Intune –. února 2019

> [!Note]
> Smlouvu NDA pro oznámení: Následující změny v Intune jsou ve vývoji. Tyto informace jsou sdíleny ve velmi omezeném rozsahu a platí pro ně dohoda o mlčenlivosti (NDA). Nepublikujte žádné z těchto informací na sociálních sítích nebo veřejných webech, jako jsou Twitter, UserVoice, Reddit apod. 

**Časná edice** poskytuje seznam funkcí, sdílený na základě dohody o mlčenlivosti (NDA), které se chystají v nadcházejících vydáních služby Microsoft Intune. Tyto informace jsou poskytovány v omezené míře a můžou podléhat změnám. Tyto informace netweetujte, nepublikujte na webu UserVoice ani jinak nesdílejte mimo vaši společnost. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a můžou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moct zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se na příslušný kontakt pro skupinu produktů společnosti Microsoft.

Tato stránka se pravidelně aktualizuje. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune na portálu Azure Portal
<!-- 1902 start-->


<!-- 1901 start -->

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Nasazení služby online licenci pro obchodní aplikace pro Microsoft Store <!-- 1672660  -->
Budete moct přiřadit vyžaduje online licencovaných Microsoft Store pro obchodní aplikace v kontextu zařízení. Nasazení Microsoft Store pro firmy díky tomu umožní aplikaci nainstalují pro všechny uživatele v zařízení. Tento krok platí jenom na Windows 10 RS4 + desktopových zařízeních. Možnost instalace v kontextu zařízení je k dispozici na stránce pro přiřazení klientské aplikace pro MSFB Online licencované aplikace.

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Aplikace pro Android Enterprise-jsme nasazení aplikace <!-- 1171203 -->
Pro zařízení s Androidem v neregistrovaných ochrany zásady bez registrace aplikace (APP-jsme) scénář nasazení, které budete moct pomocí spravovaného obchodu Google Play můžete nasadit aplikace pro store a obchodní aplikace pro uživatele. Konkrétně může oddělení IT koncovým uživatelům poskytnout aplikaci katalogu a instalace prostředí, které už vyžaduje, aby koncoví uživatelé zmírnit stav zabezpečení svých zařízeních tím, že instalace z neznámých zdrojů. Kromě toho tento scénář nasazení bude poskytovat Vylepšené uživatelské prostředí.

### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Aktualizovat zásady Intune metodu ověřování a instalace aplikace portál společnosti  <!-- 1927359 -->
Na zařízení už zaregistrované prostřednictvím pomocníka prostřednictvím jednoho z metody registrace podnikového zařízení společnosti Apple Intune nebude podporovat aplikace portál společnosti nainstalovaný ručně koncovými uživateli z app storu. Tato změna platí pouze v Apple Pomocníka s nastavením ověřování během registrace. Tato změna ovlivní také pouze zařízení s Iosem zaregistrovaná prostřednictvím:  
* Apple configurator
* Obchodní ředitel společnosti Apple
* Apple School Manager
* Program registrace zařízení Apple (DEP)

Pokud je uživatelé nainstalovat aplikaci portál společnosti z App storu a potom se pokuste registraci těchto zařízení jeho prostřednictvím, dojde k chybě. Tato zařízení bude očekávat, jenom když ho se převede, automaticky, pomocí Intune během registrace použijí portál společnosti. Profily registrace v Intune na portálu Azure portal bude aktualizován, takže můžete určit, jak ověřovat zařízení a pokud se zobrazí v aplikaci portál společnosti. Pokud chcete, aby uživatelé zařízení DEP budou používat aplikaci portál společnosti, musíte zadat předvolby v registrační profil. Kromě toho **identifikaci vašeho zařízení** obrazovky v aplikaci portál společnosti bude brzo zastaralá.  
Chcete-li nainstalovat portál společnosti na již zaregistrované zařízení DEP, budete muset přejít do Intune > klientských aplikací a poslat ho jako spravovaná aplikace pomocí zásad Konfigurace aplikací. Podrobnosti o tom, jak provést tyto kroky budou uvedené v budoucích dokumentace.

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Šablony pro správu jsou ve verzi public preview a přesunout do své vlastní konfigurační profil <!-- 3322847 -->
Šablony pro správu v Intune (**konfigurace zařízení** > **šablony pro správu**) jsou aktuálně ve verzi private preview. Od této aktualizace: Šablony pro správu zahrnuje přibližně 300 nastavení, které jde spravovat v Intune. Dříve tato nastavení existuje pouze v editoru zásad skupiny.
Šablony pro správu jsou k dispozici ve verzi public preview pro správu šablon se přesouvají z **konfigurace zařízení** > **šablony pro správu** k **zařízení konfigurace** > **profily** >**vytvořit profil** > v **platformy**, zvolte  **Windows 10 a novější**v **typ profilu**, zvolte **šablony pro správu**.
Je povoleno oznamování platí pro: Windows 10 a novější

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>MacOS tmavě režimu portál společnosti Intune <!-- 3300524 -->
Portál společnosti pro macOS Intune teď podporuje tmavě režim pro macOS. Když zapnete režim tmavé na zařízení s macOS 10.14 +, portál společnosti upraví jeho vzhled barvy, které odpovídají tohoto režimu.

<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Nastavení zásady ochrany aplikací (APP) pro webová data <!-- 2662995 -->
Nastavení zásad ochrany aplikací (APP) pro webový obsah na zařízeních s Androidem a iOS bude aktualizované, aby lépe pracovalo s webovými odkazy http a https a také s přenosy dat prostřednictvím univerzálních odkazů iOS a odkazů aplikací pro Android.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token Apple VPP používá jiný produkt MDM <!-- 1488946 -->
Intune rozpozná situaci, kdy se token programu hromadných nákupů (VPP) společnosti Apple používá v Intune a zároveň v jiném produktu MDM, a zobrazí podrobnosti.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Vyřazená zařízení na řídicím panelu Dodržování předpisů zařízením <!-- 1981119 -->
V budoucí aktualizaci se z řídicího panelu Dodržování předpisů zařízením odeberou vyřazená zařízení. Změní se tím číselné údaje týkající se dodržování předpisů.

## <a name="notices"></a>Sdělení

V současné době nejsou aktivní žádná sdělení.

### <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).
