---
title: Přidání vlastních nastavení do zařízení s Windows Phone 8.1 v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Přidejte nebo vytvořte vlastní profil, abyste v Microsoft Intune mohli u zařízení s Windows Phone 8.1 používat nastavení OMA-URI.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f2202d7abf80c6a78fd365a4629e970bc9ec36ce
ms.sourcegitcommit: c969b596ec0fec227484c50f210ba4e159e2e533
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/24/2018
ms.locfileid: "49983087"
---
# <a name="use-custom-settings-for-windows-phone-81-devices-in-intune"></a>Použití vlastních nastavení pro zařízení s Windows Phone 8.1 v Intune

V Microsoft Intune můžete vlastní profily použít k přidání nebo vytvoření vlastního nastavení u zařízení s Windows Phone 8.1. Vlastní profily jsou funkcí Intune. Jsou navržené tak, aby bylo možné přidat nastavení a funkce zařízení, které nejsou integrované do Intune.

Vlastní profily zařízení s Windows Phone 8.1 používají nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ke konfiguraci různých funkcí. Tato nastavení obvykle používají výrobci mobilních zařízení k řízení funkcí na zařízení.

V tomto článku si ukážeme, jak vytvořit vlastní profil pro zařízení s Windows Phone 8.1. 

## <a name="create-the-profile"></a>Vytvoření profilu

1. Na [portálu Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte následující nastavení:

    - **Název:** Zadejte název profilu, třeba `windows phone custom profile`.
    - **Popis**: Zadejte popis profilu.
    - **Platforma:** Zvolte **Windows Phone 8.1**.
    - **Typ profilu:** Zvolte **Vlastní**.

4. V nabídce **Vlastní nastavení OMA-URI** vyberte **Přidat**. Zadejte následující nastavení:

    - **Název:** Zadejte jedinečný název nastavení OMA-URI, abyste ho v seznamu poznali.
    - **Popis:** Zadejte popis, který přehledně vystihuje nastavení, a další důležité informace kvůli jeho snadnějšímu vyhledání.
    - **OMA-URI** (rozlišuje velká a malá písmena): Zadejte nastavení OMA-URI, které chcete použít.
    - **Datový typ:** Zvolte datový typ, který pro toto nastavení OMA-URI použijete. Možnosti:

        - Řetězec
        - Řetězec (soubor XML)
        - Datum a čas
        - Celé číslo
        - Číslo s plovoucí desetinnou čárkou
        - Logická hodnota
        - Base64 (soubor)

    - **Hodnota:** Zadejte hodnotu dat, kterou chcete přidružit k zadanému nastavení OMA-URI. Hodnota se liší podle vybraného datového typu. Pokud vyberete například **Datum a čas**, použijte k výběru hodnoty ovládací prvek pro výběr data.

    Po přidání nastavení můžete vybrat **Exportovat**. **Export** vytvoří seznam všech hodnot, které jste přidali do souboru hodnot oddělených čárkou (.csv).

5. Výběrem **OK** uložte změny. Podle potřeby přidejte další nastavení.
6. Až to budete mít, zvolte **OK** > **Vytvořit** a vytvořte profil Intune. Hotový profil se zobrazí v seznamu **Konfigurace zařízení – Profily**.

## <a name="next-steps"></a>Další kroky

Profil je vytvořený, ale zatím se nepoužívá. V dalším kroku [profil přiřadíte](device-profile-assign.md).

Podívejte se, jak vytvořit vlastní profil na [zařízeních s Windows 10](custom-settings-windows-10.md).