---
title: "Vlastní nastavení pro zařízení s Windows Phone 8.1 v Intune"
titleSuffix: Intune on Azure
description: "Podívejte se na nastavení, která je možné použít ve vlastním profilu Windows Phone 8.1."
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
ms.openlocfilehash: b3dcad95b85d967e48c8b05d655a5e679daa0aee
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
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
