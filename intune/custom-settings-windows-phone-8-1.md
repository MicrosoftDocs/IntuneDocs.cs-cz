---
title: Přidání vlastních nastavení do zařízení s Windows Phone 8.1 v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Přidejte nebo vytvořte vlastní profil, abyste v Microsoft Intune mohli u zařízení s Windows Phone 8.1 používat nastavení OMA-URI.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 97d656db3e828ef3377b927395a283fe995bb8a4
ms.sourcegitcommit: a63b9eaa59867ab2b0a6aa415c19d9fff4fda874
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2019
ms.locfileid: "67389286"
---
# <a name="use-custom-settings-for-windows-phone-81-devices-in-intune"></a>Použití vlastních nastavení pro zařízení s Windows Phone 8.1 v Intune

V Microsoft Intune můžete vlastní profily použít k přidání nebo vytvoření vlastního nastavení u zařízení s Windows Phone 8.1. Vlastní profily jsou funkcí Intune. Jsou navržené tak, aby bylo možné přidat nastavení a funkce zařízení, které nejsou integrované do Intune.

Vlastní profily zařízení s Windows Phone 8.1 používají nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ke konfiguraci různých funkcí. Tato nastavení obvykle používají výrobci mobilních zařízení k řízení funkcí na zařízení. [Dokumentace k Windows Phone 8.1 MDM protokolu](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-phone/dn499787(v=technet.10)) uvádí nastavení.

V tomto článku si ukážeme, jak vytvořit vlastní profil pro zařízení s Windows Phone 8.1. 

## <a name="create-the-profile"></a>Vytvoření profilu

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte následující nastavení:

    - **Název**: Zadejte název profilu, jako například `windows phone custom profile`.
    - **Popis**: Zadejte popis profilu.
    - **Platforma**: Zvolte **Windows Phone 8.1**.
    - **Typ profilu**: Zvolte **vlastní**.

4. V nabídce **Vlastní nastavení OMA-URI** vyberte **Přidat**. Zadejte následující nastavení:

    - **Název**: Zadejte jedinečný název nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení.
    - **Popis**: Zadejte popis, který bude shrnovat účel nastavení a další relevantní informace, abychom vám pomohli najít profil.
    - **OMA-URI** (rozlišuje velikost písmen): Zadejte OMA-URI, které chcete použít jako nastavení.
    - **Datový typ**: Vyberte datový typ, který budete používat pro toto nastavení OMA-URI. Možnosti:

        - Řetězec
        - Řetězec (soubor XML)
        - Datum a čas
        - Celé číslo
        - Číslo s plovoucí desetinnou čárkou
        - Logická hodnota
        - Base64 (soubor)

    - **Hodnota**: Zadejte hodnotu dat, které chcete přidružit k uvedenému OMA-URI. Hodnota závisí na vybraném datovém typu. Pokud vyberete například **Datum a čas**, použijte k výběru hodnoty ovládací prvek pro výběr data.

    Po přidání nastavení můžete vybrat **Exportovat**. **Export** vytvoří seznam všech hodnot, které jste přidali do souboru hodnot oddělených čárkou (.csv).

5. Vyberte **OK** uložte provedené změny. Podle potřeby přidejte další nastavení.
6. Až to budete mít, zvolte **OK** > **Vytvořit** a vytvořte profil Intune. Hotový profil se zobrazí v seznamu **Konfigurace zařízení – Profily**.

## <a name="example"></a>Příklad

V následujícím příkladu se zařízení s Windows 8.1 phone bránit v cestách mimo oblasti pokrytí dopravce změna mobilní sítě.

- **Název**: Povolit mobilní datový Roaming
- **Popis**: Povolí nebo zakáže mobilní datový roaming
- **OMA-URI** (rozlišuje velikost písmen): ./Vendor/MSFT/PolicyManager/My/Connectivity/AllowCellularDataRoaming
- **Datový typ**: Integer
- **Hodnota**: 0

## <a name="next-steps"></a>Další postup

Profil je vytvořený, ale zatím se nepoužívá. V dalším kroku [profil přiřadíte](device-profile-assign.md).

Podívejte se, jak na [zařízeních s Windows 10](custom-settings-windows-10.md) vytvořit vlastní profil.
