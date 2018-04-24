---
title: Vlastní nastavení Microsoft Intune pro zařízení s Windows Phone 8.1
titleSuffix: ''
description: Podívejte se na nastavení, která je možné použít ve vlastním profilu Windows Phone 8.1.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 83c123f3752680dbc7faca76aa525a0f035831d7
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-phone-81"></a>Vlastní nastavení zařízení v Microsoft Intune pro zařízení s Windows Phone 8.1

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pomocí **vlastního** profilu Windows Phone 8.1 v Microsoft Intune přiřaďte nastavení OMA-URI, která se dají používat k ovládání funkcí na zařízeních s Windows Phone 8.1. Jsou to standardní nastavení, která k ovládání funkcí zařízení používá spousta výrobců mobilních zařízení.

Tato vlastnost umožňuje přiřadit nastavení, která nejdou konfigurovat pomocí jiných zásad Intune.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Nastavení vlastních zásad pro zařízení Windows Phone 8.1

1. Začněte podle pokynů v tématu [Jak nakonfigurovat vlastní nastavení zařízení v Microsoft Intune](custom-settings-configure.md).
2. V podokně **Vlastní nastavení OMA-URI** pomocí **Přidat** přidejte jedno nebo více nastavení OMA-URI.
3. V podokně **Přidat řádek** nakonfigurujte u jednotlivých nastavení tyto hodnoty:
    - **Název** – zadejte jedinečný název pro nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení.
    - **Popis** – zadejte popis, který nastavení přehledně vystihne, a další důležité informace, které vám ho pomůžou najít.
    - **OMA-URI** – zadejte OMA-URI, u kterého chcete zadat nastavení.
    - **Datový typ** – vyberte datový typ, ve kterém se má toto nastavení OMA-URI zadat. Vyberte z možností **Řetězec**, **Řetězec (XML)**, **Datum a čas**, **Celé číslo**, **Plovoucí desetinná čárka**, **Logická hodnota** nebo **Base64**.
    - **Hodnota** – zadejte hodnotu nebo soubor, který chcete přidružit k uvedenému OMA-URI.

4. Po dokončení klikněte na **OK**. Další nastavení můžete přidávat podle potřeby.
