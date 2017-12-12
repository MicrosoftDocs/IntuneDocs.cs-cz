---
title: "Vlastní nastavení pro zařízení s Windows Phone 8.1 v Intune"
titleSuffix: Azure portal
description: "Podívejte se na nastavení, která je možné použít ve vlastním profilu Windows Phone 8.1."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 21c55041-3821-4a62-9f85-855b97dba269
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 88de53924e15d1d7934a6c19283f5a1cee053569
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/12/2017
---
# <a name="custom-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Vlastní nastavení pro zařízení Windows Phone 8.1 v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pomocí **vlastního** profilu Windows Phone 8.1 v Microsoft Intune přiřaďte nastavení OMA-URI, která se dají používat k ovládání funkcí na zařízeních s Windows Phone 8.1. Jsou to standardní nastavení, která k ovládání funkcí zařízení používá spousta výrobců mobilních zařízení.

Tato vlastnost umožňuje přiřadit nastavení, která nejdou konfigurovat pomocí jiných zásad Intune.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Nastavení vlastních zásad pro zařízení Windows Phone 8.1

1. Začněte podle pokynů v tématu [Jak nakonfigurovat vlastní nastavení zařízení v Microsoft Intune](custom-settings-configure.md).
2. Pokud chcete přidat nastavení OMA-URI, vyberte v okně **Vytvořit profil** možnost **Nastavení**.
3. V okně **Přidat řádek** nakonfigurujte u jednotlivých nastavení následující hodnoty:
    - **Název** – zadejte jedinečný název pro nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení.
    - **Popis** – zadejte popis, který nastavení přehledně vystihne, a další důležité informace, které vám ho pomůžou najít.
    - **OMA-URI** – zadejte OMA-URI, u kterého chcete zadat nastavení.
    - **Datový typ** – vyberte datový typ, ve kterém toto nastavení OMA-URI určíte. Vyberte z možností **Řetězec**, **Datum a čas**, **Celé číslo**, **Plovoucí desetinná čárka** nebo **Logická hodnota**.
    - **Hodnota** – zadejte hodnotu, kterou chcete přidružit k uvedenému OMA-URI.

4. Po dokončení klikněte na **OK**. Další nastavení můžete přidávat podle potřeby.
