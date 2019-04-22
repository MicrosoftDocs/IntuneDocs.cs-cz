---
title: Nastavení dodržování předpisů pro Windows 8.1 v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zobrazit seznam všech nastavení, které můžete použít při nastavení dodržování předpisů pro zařízení s Windows 8.1 a Windows Phone 8.1 v Microsoft Intune. Zkontrolovat dodržování předpisů na minimální a maximální operační systém, omezení pro heslo sadu a délku, povolit šifrování na úložiště dat a další.
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
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4ed863378616f8001beab89177c642404287e7d3
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59893885"
---
# <a name="windows-81-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Nastavení Windows 8.1 se zařízení označí jako vyhovující nebo nevyhovující předpisům pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek uvádí a popisuje nastavení různých dodržování předpisů, které můžete konfigurovat v zařízeních s Windows 8.1 v Intune. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete blokovat jednoduchá hesla, nastavit minimální a maximální verze operačního systému a další.

Tato funkce platí pro:

- Windows Phone 8.1
- Windows 8.1 a vyšší

Jako správce Intune pomocí těchto nastavení dodržování předpisů pomáhají chránit prostředky organizace. Další informace o zásadách dodržování předpisů a jaké, viz [Začínáme s dodržováním předpisů zařízeními](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte zásadu dodržování předpisů](create-compliance-policy.md#create-the-policy). Pro **platformy**vyberte **Windows Phone 8.1** nebo **Windows 8.1 a novější**.

## <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální požadovaný operační systém**: Zadejte minimální povolenou verzi. Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nedodržující předpisy. Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může zařízení upgradovat. Potom získá přístup k prostředkům společnosti.
- **Maximální povolená verze operačního systému**: Zadejte maximální povolenou verzi. Když zařízení používá verzi operačního systému novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Zařízení nemá přístup k prostředkům organizace, dokud nezměníte pravidlo pro povolení verze operačního systému.

Počítače s Windows 8.1 vrací verzi **3**. Pokud je pravidlo verze operačního systému nastavené na Windows 8.1 pro Windows, je i v případě, že má zařízení Windows 8.1, bude se zařízení uvádět jako nedodržující předpisy.

## <a name="system-security"></a>Zabezpečení systému

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadovat** uživatelé zadat heslo, než bude moct svoje zařízení.
- **Jednoduchá hesla**: Nastavte na **bloku** , uživatelé nemůžou vytvářet jednoduchá hesla, jako například **1234** nebo **1111**. Pokud chcete uživatelům umožnit vytváření hesel jako **1234** nebo **1111**, nastavte na **Nenakonfigurováno**.
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.

  Pro zařízení s Windows, ke kterým uživatelé přistupují pomocí účtu Microsoft, se zásady dodržování předpisů nevyhodnotí správně:
  - Pokud je minimální délka hesla větší než osm znaků
  - Nebo pokud je minimální počet znakových sad větší než dvě

- **Typ hesla**: Zvolte, jestli má heslo obsahovat pouze **číselné** znaků, nebo jestli má obsahovat kombinaci čísel a dalších znaků (**alfanumerické**).
  
  - **Počet nealfanumerických znaků v hesle**: Pokud se **Požadovaný typ hesla** nastaví na **Alfanumerické**, toto nastavení určuje nejmenší počet znakových sad, které musí heslo obsahovat. Jde o tyto čtyři znakové sady:
    - Malá písmena
    - Velká písmena
    - Symboly
    - Numbers

    Po nastavení vyššího čísla bude uživatel muset vytvořit složitější heslo. Pro zařízení s Windows zabezpečených účtem Microsoft se nezdaří zásady dodržování předpisů nevyhodnotí správně:

    - Pokud je minimální délka hesla větší než osm znaků
    - Nebo pokud je minimální počet znakových sad větší než dvě

- **Maximální počet minut nečinnosti před vyžádáním hesla**: Zadejte dobu nečinnosti, než uživatel musí znovu zadat heslo.
- **Vypršení platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která zakázat opakované použití**: Zadejte počet dříve použitých hesel, která nelze použít.

### <a name="encryption"></a>Šifrování

- **Vyžadovat šifrování u mobilního zařízení**: **Vyžadovat** zařízení byly šifrované připojení k prostředkům datového úložiště.

Vyberte **OK** > **Vytvořit** a změny uložte.

## <a name="next-steps"></a>Další postup

- [Přidání akcí pro zařízení nedodržující předpisy](actions-for-noncompliance.md) a [pomocí značky oboru filtru zásad](scope-tags.md).
- [Monitorovat zásady dodržování předpisů](compliance-policy-monitor.md).
- Zobrazit [nastavení zásad dodržování předpisů pro Windows 10 a novější](compliance-policy-create-windows.md) zařízení.