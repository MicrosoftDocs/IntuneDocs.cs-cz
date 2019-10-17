---
title: Windows 8.1 nastavení dodržování předpisů v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na seznam všech nastavení, která můžete použít při nastavení dodržování předpisů pro Windows 8.1 a zařízení Windows Phone 8,1 v Microsoft Intune. Ověřte kompatibilitu s minimálním a maximálním operačním systémem, nastavte omezení a délku hesla, povolte šifrování pro úložiště dat a další.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 322d6f1e23464f1f75cc79346d839a9ccdbd7bc7
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504641"
---
# <a name="windows-81-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Nastavení Windows 8.1 pro označení zařízení jako kompatibilních nebo nekompatibilních s použitím Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Tento článek obsahuje seznam a popis různých nastavení dodržování předpisů, která můžete nakonfigurovat na zařízeních Windows 8.1 v Intune. Jako součást řešení správy mobilních zařízení (MDM) použijte Tato nastavení k blokování jednoduchých hesel, nastavení minimální a maximální verze operačního systému a dalších.

Tato funkce platí pro:

- Wvdows Phone 8.1
- Windows 8.1 a vyšší

Jako správce Intune můžete pomocí těchto nastavení dodržování předpisů ochránit prostředky vaší organizace. Další informace o zásadách dodržování předpisů a o tom, co dělají, najdete v tématu [Začínáme s dodržováním předpisů pro zařízení](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte zásadu dodržování předpisů](create-compliance-policy.md#create-the-policy). V části **platforma**vyberte **Windows Phone 8,1** nebo **Windows 8.1 a novější**.

## <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální požadovaný operační systém**: zadejte minimální povolenou verzi. Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, nahlásí se jako nevyhovující. Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může zařízení upgradovat. Potom získá přístup k prostředkům společnosti.
- **Maximální povolená verze operačního systému**: zadejte maximální povolenou verzi. Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Zařízení nemá přístup k prostředkům organizace, dokud nezměníte pravidlo, které povoluje verzi operačního systému.

Počítače s Windows 8.1 vrací verzi **3**. Pokud je pravidlo verze operačního systému pro Windows nastavené na Windows 8.1, zařízení se nahlásí jako nedodržující předpisy i v případě, že má zařízení Windows 8.1.

## <a name="system-security"></a>Zabezpečení systému

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadujte**, aby uživatelé před získáním přístupu ke svému zařízení zadali heslo.
- **Jednoduchá hesla**: Pokud nastavíte **Blokovat**, nebudou moct uživatelé vytvořit jednoduchá hesla, jako je třeba **1234** nebo **1111**. Pokud chcete uživatelům umožnit vytváření hesel jako **1234** nebo **1111**, nastavte na **Nenakonfigurováno**.
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.

  Pro zařízení s Windows, ke kterým uživatelé přistupují pomocí účtu Microsoft, se zásady dodržování předpisů nevyhodnotí správně:
  - Pokud je minimální délka hesla větší než osm znaků
  - Nebo pokud je minimální počet znakových sad větší než dvě

- **Typ hesla**: Zvolte, jestli má heslo obsahovat pouze **číselné** znaky, nebo jestli má obsahovat kombinaci čísel a dalších znaků (**alfanumerické**).
  
  - **Počet nealfanumerických znaků v hesle**: Pokud se **Požadovaný typ hesla** nastaví na **Alfanumerické**, určuje toto nastavení minimální počet znakových sad, které musí heslo obsahovat. Jde o tyto čtyři znakové sady:
    - Malá písmena
    - Velká písmena
    - Symboly
    - Numbers

    Po nastavení vyššího čísla bude uživatel muset vytvořit složitější heslo. U zařízení, ke kterým se používá účet Microsoft, se zásady dodržování předpisů nevyhodnotí správně:

    - Pokud je minimální délka hesla větší než osm znaků
    - Nebo pokud je minimální počet znakových sad větší než dvě

- **Maximální počet minut nečinnosti, po kterém bude nutné zadat heslo**: Zadejte dobu nečinnosti, která musí uplynout, aby se po uživateli znovu požadovalo zadání hesla.
- **Konec platnosti hesla (dny)** : Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která se nedají použít znovu**: zadejte počet dříve použitých hesel, která se nedají použít.

### <a name="encryption"></a>Encryption

- **Vyžadovat šifrování u mobilního zařízení:** **Vyžaduje**, aby zařízení přistupující k prostředkům datového úložiště bylo šifrované.

Vyberte **OK** > **Vytvořit** a změny uložte.

## <a name="next-steps"></a>Další kroky

- [Přidejte akce pro zařízení nedodržující předpisy](actions-for-noncompliance.md) a [použijte značky oboru k filtrování zásad](../fundamentals/scope-tags.md).
- [Monitorujte zásady dodržování předpisů](compliance-policy-monitor.md).
- Podívejte se na [nastavení zásad dodržování předpisů pro zařízení s Windows 10 a novějším](compliance-policy-create-windows.md) .