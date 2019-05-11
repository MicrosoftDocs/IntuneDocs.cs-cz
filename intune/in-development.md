---
title: Při vývoji – Microsoft Intune
titleSuffix: ''
description: Microsoft Intune nabízí ve vývoji
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/29/2019
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
ms.openlocfilehash: 7bba992c79f69a126f0199d9cdac52779910ff38
ms.sourcegitcommit: 068c4e4bc6e6d778ece4a83d000128c4d2b732db
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910329"
---
# <a name="in-development-for-microsoft-intune---may-2019"></a>Při vývoji pro Microsoft Intune –. května 2019.

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


<!-- 1905 start-->


### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Odstraňuje se zařízení na portálu Apple se projeví na portálu Intune <!--2489996 -->
Pokud zařízení se odstraní z Apple Device Enrollment Program nebo Apple obchodní ředitel portálů, zařízení automaticky se odstraní ze služby Intune při příští synchronizaci.

### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Hledat směrný plán podpory pro klíčové slovo  <!-- 3082036         -->
Při vytváření nebo úpravu profil standardních hodnot zabezpečení, které už brzy bude možné použít *hledání* vyfiltrujete nastavení, které zobrazují v konzole.   

### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Resetovat a vymazání zařízení hromadně pomocí rozhraní Graph API <!-- 3295288 -->
Budete moct resetovat a vymazání zařízení až 100 hromadně pomocí rozhraní Graph API.

### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Vyhledat čipů TPM v zásadách dodržování předpisů zařízení Windows 10 <!-- 3617671 -->
Mnoho Windows 10 a novější zařízení má čipovými sadami Trusted Platform Module (TPM). Tato aktualizace zahrnuje nové nastavení dodržování předpisů, která kontroluje verze čipu TPM v zařízení. 

[Windows 10 a novější nastavení zásad dodržování předpisů](compliance-policy-create-windows.md#device-security) popisuje toto nastavení.

Platí pro: Windows 10 a novější

### <a name="intune-management-extension-powershell-scripts-----3734186------"></a>Skripty Powershellu rozšíření správy Intune  <!-- 3734186    -->
Budete moct konfigurovat skripty prostředí PowerShell, spusťte s oprávněními správce uživatele na zařízení. Další informace najdete v tématu [skripty prostředí PowerShell použít na zařízeních s Windows 10 v Intune](intune-management-extension.md).

### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-supervised-devices----4097904----"></a>Koncovým uživatelům zabránit ve změně jejich osobní HotSpot a zakázat protokolování v systému iOS zařízení pod dohledem server Siri <!-- 4097904  --> 
Vytvořit profil omezení zařízení na zařízení s Iosem (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **iOS** pro platformu > **omezení zařízení** pro typ profilu). Tato aktualizace zahrnuje nové nastavení, které můžete nakonfigurovat:

- Osobní HotSpot
- Protokolování serveru Siri

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s Iosem k povolení nebo zakázání funkce](device-restrictions-ios.md). 

Platí pro: iOS 12.2 a novější

### <a name="new-classroom-app-device-restriction-settings-for-dep-enrolled-macos-devices----4097905----"></a>Nová Učebna aplikace nastavení omezení zařízení pro zařízení macOS zaregistrovaných v programu DEP <!-- 4097905  --> 
Zařízení můžete vytvořit konfigurační profily pro zařízení s macOS (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **macOS** pro platformu > **omezení zařízení** pro typ profilu). Tato aktualizace zahrnuje nové nastavení aplikace classroom pro zařízení zaregistrovaná v programu DEP a možnost zakázat knihovnu fotografií na Icloudu.

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s macOS k povolení nebo zakázání funkcí pomocí Intune](device-restrictions-macos.md).

Platí pro: macOS 10.14.4 a novější

### <a name="android-enterprise-app-management----4459905-idready---"></a>Správa aplikací androidu Enterprise <!-- 4459905 idready -->
Aby bylo snazší pro správce IT ke konfiguraci a použití správy Androidu Enterprise, Intune automaticky přidá čtyři běžné Androidu Enterprise související s aplikací do konzoly pro správu Intune. Čtyři aplikace Android Enterprise jsou následující:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**  – používá se pro scénáře s Androidem Enterprise, plně spravovaná.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)**  – pomáhá vám přihlášení k účtům používáte dvojúrovňového ověřování.
- **[Portál společnosti Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)**  – používá se pro zásady ochrany aplikací (aplikace) a Android Enterprise pracovní profil scénáře.
- [Spravované domovskou obrazovku](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) – používá se pro scénáře vyhrazeného/veřejný terminál s Androidem Enterprise.

Dříve by správci IT musí ručně vyhledejte a schvalte tyto aplikace [spravovaný obchod Google Play storu](https://play.google.com/store/apps) jako součást instalace. Tato změna odebere tyto dříve Ruční postup snadnější a rychlejší pro zákazníky, kteří pro použití správy Androidu.

Správci uvidí tyto čtyři aplikace automaticky přidá do seznamu svých aplikací pro Intune v době, že nejprve připojit svého tenanta Intune do spravovaného obchodu Google Play. Další informace najdete v tématu [připojte si účet Intune ke svému účtu spravovaný obchod Google Play](connect-intune-android-enterprise.md). U klientů, který je již připojen svého tenanta nebo který už používáte Android Enterprise nic, co správce potřeba. Tyto čtyři aplikace se automaticky zobrazí během 7 dnů od konce května 2019 služby zavedení.

<!-- 1904 start-->

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Pokročilé nastavení firewallu v programu Windows Defender <!-- 1311949 -->
Brzy budete moct používat Intune ke správě vlastních pravidel brány firewall na klientech pro program Windows Defender. Pravidla můžete zadat příchozí a odchozí chování aplikací, síťové adresy a porty. 


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



## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).


