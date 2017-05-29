---
title: "Vlastní nastavení pro zařízení s Windows Phone 8.1 v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Podívejte se na nastavení, která je možné použít ve vlastním profilu Windows Phone 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 646d0ec4274e068487ad9546ff0b5dabfc815e46
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="custom-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Vlastní nastavení pro zařízení Windows Phone 8.1 v Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

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

