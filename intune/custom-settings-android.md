---
title: "Vlastní nastavení pro zařízení s Androidem v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Podívejte se na nastavení, která je možné použít ve vlastním profilu Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ff3d3b1596f58213bed2509b1bfd5ae81c63f440
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Vlastní nastavení pro zařízení s Androidem v Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Pomocí **vlastního** profilu Android v Microsoft Intune přiřaďte nastavení OMA-URI, která se dají používat k ovládání funkcí na zařízeních s Androidem. Jsou to standardní nastavení, která k ovládání funkcí zařízení používá spousta výrobců mobilních zařízení.

Tato vlastnost umožňuje přiřadit nastavení Androidu, která nejdou konfigurovat pomocí zásad Intune.

## <a name="custom-profile-settings-for-android-devices"></a>Nastavení vlastního profilu pro zařízení s Androidem

1. Začněte podle pokynů v tématu [Jak nakonfigurovat vlastní nastavení zařízení v Microsoft Intune](custom-settings-configure.md).
2. Pokud chcete přidat nastavení OMA-URI, vyberte v okně **Vytvořit profil** možnost **Nastavení**.
3. V okně **Upravit řádek** nakonfigurujte u jednotlivých nastavení následující hodnoty:
    - **Název** – zadejte jedinečný název pro nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení.
    - **Popis** – zadejte popis, který nastavení přehledně vystihne, a další důležité informace, které vám ho pomůžou najít.
    - **Datový typ** – vyberte datový typ, ve kterém toto nastavení OMA-URI určíte. Vyberte z možností **Řetězec**, **Řetězec (XML)**, **Datum a čas**, **Celé číslo**, **Plovoucí desetinná čárka** nebo **Logická hodnota**.
    - **OMA-URI** – zadejte OMA-URI, u kterého chcete zadat nastavení.
    - **Hodnota** – zadejte hodnotu, kterou chcete přidružit k uvedenému OMA-URI.
4. Po dokončení klikněte na **OK**. Další nastavení můžete přidávat podle potřeby.

