---
title: nastavení dodržování předpisů zařízení s macOS v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zobrazit seznam všech nastavení, které můžete použít při nastavení dodržování předpisů pro zařízení s macOS v Microsoft Intune. Vyžadovat ochranu integrity systému společnosti Apple, nastavit omezení pro heslo, vyžadují bránu firewall, povolit vrátný a další.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b3224e7400ad56f971488aba53bb073a0d33bb9d
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423641"
---
# <a name="macos-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>nastavení macOS se zařízení označí jako vyhovující nebo nevyhovující předpisům pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek uvádí a popisuje nastavení různých dodržování předpisů, které můžete nakonfigurovat na zařízeních s macOS v Intune. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete nastavit minimální nebo maximální OS verze, sada hesla vyprší a další.

Tato funkce platí pro:

- macOS

Jako správce Intune pomocí těchto nastavení dodržování předpisů pomáhají chránit prostředky organizace. Další informace o zásadách dodržování předpisů a jaké, viz [Začínáme s dodržováním předpisů zařízeními](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte zásadu dodržování předpisů](create-compliance-policy.md#create-the-policy). U možnosti **Platforma** vyberte **macOS**.

## <a name="device-health"></a>Stav zařízení

- **Vyžadovat ochranu integrity systému**: **Vyžadovat** vaše zařízení s macOS měla [ochranu Integrity systému](https://support.apple.com/HT204899) (otevře web společnosti Apple) povolena. Pokud je nastavena na **Nenakonfigurováno** (výchozí), toto nastavení se nevyhodnotí dodržování předpisů nebo nedodržení předpisů.

## <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální verze operačního systému**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nedodržující předpisy. Zobrazí se odkaz s informacemi, jak upgradovat. Koncový uživatel si může zařízení upgradovat. Potom získá přístup k prostředkům společnosti.
- **Maximální verze operačního systému**: Když zařízení používá verzi operačního systému novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nebude mít toto zařízení přístup k prostředkům společnosti.
- **Minimální operační systém sestavení verze**: Jakmile Apple publikuje aktualizace zabezpečení, je obvykle aktualizovat číslo sestavení, nikoli na verzi operačního systému. Pomocí této funkce lze zadat číslo minimální povolenou sestavení na zařízení.
- **Maximální verze operačního systému sestavení verze**: Jakmile Apple publikuje aktualizace zabezpečení, je obvykle aktualizovat číslo sestavení, nikoli na verzi operačního systému. Pomocí této funkce lze zadat maximální povolené sestavení číslo na zařízení.

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadovat** uživatelé zadat heslo, než bude moct svoje zařízení.
- **Jednoduchá hesla**: Nastavte na **bloku** , uživatelé nemůžou vytvářet jednoduchá hesla, jako například **1234** nebo **1111**. Pokud chcete uživatelům umožnit vytváření hesel jako **1234** nebo **1111**, nastavte na **Nenakonfigurováno**.
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Typ hesla**: Zvolte, jestli má heslo obsahovat pouze **číselné** znaků, nebo jestli má obsahovat kombinaci čísel a dalších znaků (**alfanumerické**).
- **Počet nealfanumerických znaků v hesle**: Zadejte minimální počet speciálních znaků, jako například `&`, `#`, `%`, `!`, a tak dále, který musí být v hesle.

    Po nastavení vyššího čísla bude uživatel muset vytvořit složitější heslo.

- **Maximální počet minut nečinnosti před vyžádáním hesla**: Zadejte dobu nečinnosti, než uživatel musí znovu zadat heslo.
- **Vypršení platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která zakázat opakované použití**: Zadejte počet dříve použitých hesel, která nelze použít.

    > [!IMPORTANT]
    > Když se požadavek na heslo na zařízení s macOS změní, projeví se to až při příští změně hesla uživatelem. Pokud třeba nastavíte omezení délky hesla na osm číslic a zařízení s macOS má aktuálně šestičíselné heslo, bude zařízení dál splňovat předpisy až do doby, kdy uživatel heslo na zařízení aktualizuje.

### <a name="encryption"></a>Šifrování

- **Šifrování datového úložiště na zařízení**: Zvolte **vyžadují** a zašifrujte úložiště dat na vašich zařízeních.

### <a name="device-security"></a>Zabezpečení zařízení

Firewall chrání zařízení před neoprávněným přístupem do sítě. Pomocí firewallu můžete ovládat připojení pro jednotlivé aplikace. 

- **Brána firewall**: Vyberte **povolit** k ochraně zařízení před neoprávněným přístupem. Aktivace této funkce vám umožní zpracovávat příchozí internetová připojení a používat neviditelný režim. Nastavení **Nenakonfigurováno** (výchozí) ponechá firewall vypnutý a síťový provoz bude povolený (neblokovaný).
- **Příchozí připojení**: **Blok** všechna příchozí připojení s výjimkou připojení potřebných pro základní internetové služby, například DHCP, Bonjour a IPSec. Toto nastavení také zablokuje všechny služby sdílení, včetně sdílení obrazovky, vzdáleného přístupu, sdílení hudby iTunes a další. Nastavení **Nenakonfigurováno** (výchozí) povoluje příchozí připojení a služby sdílení.
- **Neviditelný režim**: **Povolit** neviditelný režim, který zabrání zařízení v odpovídání na zjišťovací požadavky, které můžou být uživatelé se zlými úmysly. Při aktivaci této možnosti bude zařízení oprávněným aplikacím dále odpovídat na příchozí požadavky. Nastavení **Nenakonfigurováno** (výchozí) ponechá neviditelný režim vypnutý.

### <a name="gatekeeper"></a>Gatekeeper

Další informace najdete v tématu [vrátný v systému macOS](https://support.apple.com/HT202491) (otevře web společnosti Apple).

**Povolit aplikace stažené z těchto míst**: Umožňuje nainstalovat na zařízení z různých míst podporovaných aplikací. Možnosti umístění:

- **Není nakonfigurováno**: Default (Výchozí). Možnost vrátný nemá žádný vliv na dodržování předpisů nebo nedodržení předpisů. 
- **Mac App Store**: Instalovat pouze aplikace pro Mac app storu. Aplikace jiných výrobců ani identifikovaných vývojářů nelze nainstalovat. Pokud uživatel vybere Gatekeeper pro instalaci aplikací z umístění mimo Mac App Store, považuje se zařízení za nevyhovující předpisům.
- **Mac App Store a identifikovaní vývojáři**: Instalovat aplikace do obchodu Mac app Store a identifikovaní vývojáři. macOS zkontroluje identitu vývojářů a provede několik dalších kontrol, aby ověřil integritu aplikace. Pokud uživatel vybere Gatekeeper pro instalaci aplikací z umístění mimo tyto možnosti, považuje se zařízení za nevyhovující předpisům.
- **Kdekoli**: Aplikace můžete nainstalovat z kdekoli a pro všechny vývojáře. Jedná se o nejméně bezpečnou možnost.

Vyberte **OK** > **Vytvořit** a změny uložte.

## <a name="next-steps"></a>Další postup

- [Přidání akcí pro zařízení nedodržující předpisy](actions-for-noncompliance.md) a [pomocí značky oboru filtru zásad](scope-tags.md).
- [Monitorovat zásady dodržování předpisů](compliance-policy-monitor.md).
- Zobrazit [nastavení zásad dodržování předpisů pro iOS](compliance-policy-create-ios.md) zařízení.