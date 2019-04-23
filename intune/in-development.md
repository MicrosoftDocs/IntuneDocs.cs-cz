---
title: Při vývoji – Microsoft Intune
titleSuffix: ''
description: Microsoft Intune nabízí ve vývoji
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/15/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 004ebad5276575fe9f5b580d13db188f297424fb
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61513671"
---
# <a name="in-development-for-microsoft-intune---april-2019"></a>Při vývoji pro Microsoft Intune – duben 2019

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

<!-- 1904 start-->

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Pokročilé nastavení firewallu v programu Windows Defender <!-- 1311949 -->
Brzy budete moct používat Intune ke správě vlastních pravidel brány firewall na klientech pro program Windows Defender. Pravidla můžete zadat příchozí a odchozí chování aplikací, síťové adresy a porty. 

### <a name="require-app-protection-conditional-access----1634317---"></a>Vyžadují podmíněný přístup ochrany aplikací  <!--1634317 -->
Budete moct použít *zásady ochrany aplikací vyžadují*, tím se potvrdí zásad se použije pro uživatele aplikace před dokončením přihlášení uživatelům zabránit v přístupu k datům můžete chránit pomocí podmíněného přístupu. Při zabezpečování zásad může zpomalit první prostředí použijte, pomáhá chránit před problémy se sítí, správu chyb v konfiguraci nebo úmyslné úsilí o čáru přes rozpočet zásady ochrany aplikací. 

### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>Konfigurace nastavení pro rozšíření jádra na zařízeních s macOS <!-- 2043024 -->
Na zařízeních s macOS, můžete vytvořit profil konfigurace zařízení (**konfigurace zařízení** > **profily** > **vytvořit profil** > Zvolte **macOS** pro platformu). Nová skupina nastavení vám umožní nakonfigurovat a používat rozšíření jádra na vašich zařízeních.

Platí pro: macOS 10.13.2 a novější

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Uživatelé zařízení můžete zobrazit všechny spravované aplikace, které jste nainstalovaná nebo se pokusila o instalaci <!-- 2352913 -->
Portál společnosti pro Windows se zobrazí seznam všech spravovaných aplikací&ndash; povinné a k dispozici&ndash; které se instalují na zařízení uživatele. Uživatelé budou moct k pokusu o zobrazení a probíhající instalace aplikací a jejich aktuální stavy. Pokud vaše organizace nemá vytvořit obdobné aplikace vyžaduje nebo jsou dostupné, uživatelům se zobrazí se zpráva s vysvětlením, že nebyly nainstalovány žádné aplikace společnosti. Uživatelé budou také moct seřadíte nebo vyfiltrujete podle stavu instalace aplikace.

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Použijte "pravidla použitelnosti" při vytváření profilů konfigurace zařízení s Windows 10 <!-- 2549910 -->
Vytváření profilů konfigurace zařízení s Windows 10 (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **Windows 10** pro platformu). Budete moct vytvořit **pravidla použitelnosti** tak profil, který se vztahuje pouze na konkrétní edici nebo konkrétní verzi. Například vytvořit profil, který umožňuje některá nastavení nástroje BitLocker. Po přidání profilu použijte použije pravidlo použitelnosti, tak profil, který platí jenom pro zařízení s Windows 10 Enterprise.

Platí pro: 
- Windows 10 a novější

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Zabezpečení úloh Intune pro ochrany ATP v programu Defender (ve verzi public preview) <!-- 3208597 -->
Už jako verze public preview, Intune brzo přidávat úkoly zabezpečení pro nově oznámené Microsoft Defender Threat & Správa ohrožení zabezpečení.  Tato integrace správce operací zabezpečení v systému Windows Defender ATP (WDATP) efektivněji komunikaci doporučené nápravy nově vznikající hrozby pro správce Intune. Přidání zabezpečení úloh přidá a přístup na základě rizik zjistit, prioritu a náprava ohrožení zabezpečení koncového bodu a chyby v konfiguraci.

Další informace o zabezpečení úloh v Intune, najdete v blogovém příspěvku o [rozšíření Microsoft Defender ATP Správa ohrožení zabezpečení a používání Intune zabezpečení úloh](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>Rozšířené ochrany před internetovými útoky programu Windows Defender směrného plánu <!-- 3754134 -->
Chceme přidat nový směrný plán můžete nakonfigurovat nastavení rozšířené ochrany před internetovými útoky programu Windows Defender.


### <a name="ios-third-party-keyboards----4111843---"></a>iOS klávesnice třetích stran <!-- 4111843 -->
Podpora pro zásady ochrany aplikací Intune (aplikace) **třetích stran klávesnice** nastavení skončí kvůli o změnu pro platformu iOS. Nebude moct nakonfigurovat toto nastavení v konzole správce Intune a neuplatní se na klientovi v sadě Intune App SDK.

<!-- 1903 start-->

### <a name="windows-update-notifications----3316782---"></a>Oznámení o aktualizaci Windows <!-- 3316782 -->
Konfigurace aktualizačního kanálu Windows Update Doplňujeme podporu, takže budete moci konfigurovat oznámení o aktualizacích Windows, které se uživatelům zobrazí. Toto nastavení nebude k dispozici v rámci portálu, ale dá se s použitím rozhraní Intune Graph API.

### <a name="easier-access-to-diagnostic-settings----3804627---"></a>Jednodušší přístup k nastavení diagnostiky <!-- 3804627 -->
Přidáváme novou možnost, jak **protokoly auditu** okno v každé úloze protokolu auditu v konzole Intune, který vám umožní otevřít přímo *nastavení diagnostiky* stránky.

## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).


