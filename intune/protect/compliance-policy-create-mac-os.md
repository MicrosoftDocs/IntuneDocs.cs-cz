---
title: nastavení dodržování předpisů pro zařízení macOS v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na seznam všech nastavení, která můžete použít při nastavování dodržování předpisů pro zařízení macOS v Microsoft Intune. Vyžadovat ochranu před integritou systému od společnosti Apple, nastavit omezení hesla, vyžadovat bránu firewall, dovolit server gatekeeper a další.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 22bd3dd50f6c2cbeba59aad4dd00683d52668f72
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729786"
---
# <a name="macos-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>nastavení macOS a označení zařízení jako kompatibilních nebo nekompatibilních s použitím Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Tento článek obsahuje seznam a popis různých nastavení dodržování předpisů, která můžete nakonfigurovat na zařízeních macOS v Intune. Jako součást řešení správy mobilních zařízení (MDM) pomocí těchto nastavení můžete nastavit minimální nebo maximální verzi operačního systému, nastavit vypršení platnosti hesla a další.

Tato funkce platí pro:

- macOS

Jako správce Intune můžete pomocí těchto nastavení dodržování předpisů ochránit prostředky vaší organizace. Další informace o zásadách dodržování předpisů a o tom, co dělají, najdete v tématu [Začínáme s dodržováním předpisů pro zařízení](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte zásadu dodržování předpisů](create-compliance-policy.md#create-the-policy). U možnosti **Platforma** vyberte **macOS**.

## <a name="device-health"></a>Stav zařízení

- **Vyžadování ochrany integrity systému**: **vyžaduje** , aby zařízení MacOS měla [ochranu integrity systému](https://support.apple.com/HT204899) (otevře web společnosti Apple) povoleno. Pokud je nastavené na **Nenakonfigurováno** (výchozí nastavení), toto nastavení se nevyhodnotí pro dodržování předpisů nebo nedodržování předpisů.

## <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální verze OS**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, označí se jako nekompatibilní. Zobrazí se odkaz s informacemi, jak upgradovat. Koncový uživatel si může zařízení upgradovat. Potom získá přístup k prostředkům společnosti.
- **Maximální verze OS**: Pokud zařízení používá verzi operačního systému, která je novější než verze specifikovaná v pravidle, bude přístup k prostředkům společnosti blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně pravidla, které tuto verzi operačního systému povolí, nebude mít toto zařízení přístup k prostředkům společnosti.
- **Minimální verze buildu OS**: když Apple publikuje aktualizace zabezpečení, číslo sestavení se obvykle aktualizuje, nikoli verze operačního systému. Pomocí této funkce můžete zadat minimální povolené číslo sestavení v zařízení.
- **Maximální verze buildu OS**: když Apple publikuje aktualizace zabezpečení, číslo sestavení se obvykle aktualizuje, nikoli verze operačního systému. Pomocí této funkce můžete zadat maximální povolené číslo sestavení v zařízení.

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadujte**, aby uživatelé před získáním přístupu ke svému zařízení zadali heslo.
- **Jednoduchá hesla**: Pokud nastavíte **Blokovat**, nebudou moct uživatelé vytvořit jednoduchá hesla, jako je třeba **1234** nebo **1111**. Pokud chcete uživatelům umožnit vytváření hesel jako **1234** nebo **1111**, nastavte na **Nenakonfigurováno**.
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Typ hesla**: Zvolte, jestli má heslo obsahovat pouze **číselné** znaky, nebo jestli má obsahovat kombinaci čísel a dalších znaků (**alfanumerické**).
- **Počet nealfanumerických znaků v hesle**: zadejte minimální počet speciálních znaků (například `&`, `#`, `%`, `!` atd.), které musí být v hesle.

    Po nastavení vyššího čísla bude uživatel muset vytvořit složitější heslo.

- **Maximální počet minut nečinnosti, po kterém bude nutné zadat heslo**: Zadejte dobu nečinnosti, která musí uplynout, aby se po uživateli znovu požadovalo zadání hesla.
- **Konec platnosti hesla (dny)** : Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která se nedají použít znovu**: zadejte počet dříve použitých hesel, která se nedají použít.

    > [!IMPORTANT]
    > Když se požadavek na heslo na zařízení s macOS změní, projeví se to až při příští změně hesla uživatelem. Pokud třeba nastavíte omezení délky hesla na osm číslic a zařízení s macOS má aktuálně šestičíselné heslo, bude zařízení dál splňovat předpisy až do doby, kdy uživatel heslo na zařízení aktualizuje.

### <a name="encryption"></a>Encryption

- **Šifrování úložiště dat na zařízení**: Vyberte **Vyžadovat** a zašifrujte úložiště dat na vašich zařízeních.

### <a name="device-security"></a>Zabezpečení zařízení

Firewall chrání zařízení před neoprávněným přístupem do sítě. Pomocí firewallu můžete ovládat připojení pro jednotlivé aplikace. 

- **Firewall**: vyberte **Povolit** , pokud chcete chránit zařízení před neoprávněným přístupem. Aktivace této funkce vám umožní zpracovávat příchozí internetová připojení a používat neviditelný režim. Nastavení **Nenakonfigurováno** (výchozí) ponechá firewall vypnutý a síťový provoz bude povolený (neblokovaný).
- **Příchozí připojení**: **blokuje** všechna příchozí síťová připojení s výjimkou připojení požadovaných pro základní internetové služby, jako jsou DHCP, Bonjour a IPSec. Toto nastavení také blokuje všechny služby sdílení, včetně sdílení obrazovky, vzdáleného přístupu, sdílení hudby v iTunes a dalších. Nastavení **Nenakonfigurováno** (výchozí) povoluje příchozí připojení a služby sdílení.
- **Režim utajení**: **umožňuje povolit** neviditelný režim a zabránit tak tomu, aby zařízení reagovala na požadavky na zjišťování, které je možné provést v mých škodlivých uživatelích. Při aktivaci této možnosti bude zařízení oprávněným aplikacím dále odpovídat na příchozí požadavky. Nastavení **Nenakonfigurováno** (výchozí) ponechá neviditelný režim vypnutý.

### <a name="gatekeeper"></a>Gatekeeper

Další informace najdete v tématu [gatekeeper na MacOS](https://support.apple.com/HT202491) (Otevírá web společnosti Apple).

**Povolit aplikace stažené z těchto míst**: Povolí instalaci podporovaných aplikací na vaše zařízení z různých umístění. Možnosti umístění:

- **Nenakonfigurováno**: Toto je výchozí možnost. Možnost serveru gatekeeper nemá žádný vliv na dodržování předpisů nebo nedodržování předpisů. 
- **Mac App Store**: Povolí instalaci aplikací pouze z Mac App Storu. Aplikace jiných výrobců ani identifikovaných vývojářů nelze nainstalovat. Pokud uživatel vybere Gatekeeper pro instalaci aplikací z umístění mimo Mac App Store, považuje se zařízení za nevyhovující předpisům.
- **Mac App Store a identifikovaní vývojáři**: Povolí instalaci aplikací z Mac App Storu a od identifikovaných vývojářů. macOS zkontroluje identitu vývojářů a provede několik dalších kontrol, aby ověřil integritu aplikace. Pokud uživatel vybere Gatekeeper pro instalaci aplikací z umístění mimo tyto možnosti, považuje se zařízení za nevyhovující předpisům.
- **Kdekoli**: Aplikace je možné instalovat odkudkoli a od kteréhokoli vývojáře. Jedná se o nejméně bezpečnou možnost.

Vyberte **OK** > **Vytvořit** a změny uložte.

## <a name="next-steps"></a>Další kroky

- [Přidejte akce pro zařízení nedodržující předpisy](actions-for-noncompliance.md) a [použijte značky oboru k filtrování zásad](../fundamentals/scope-tags.md).
- [Monitorujte zásady dodržování předpisů](compliance-policy-monitor.md).
- Podívejte se na [nastavení zásad dodržování předpisů pro](compliance-policy-create-ios.md) zařízení s iOS.