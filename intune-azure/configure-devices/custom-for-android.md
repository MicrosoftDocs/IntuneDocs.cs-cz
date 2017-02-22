---
title: "Vlastní nastavení Intune pro zařízení s Androidem | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Podívejte se na nastavení, která je možné použít ve vlastním profilu Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab494a3dd1e1bdea9703ab314574b192c5208ee
ms.openlocfilehash: 3a80a69a27b540b66fb96e098c0b0f66a0854297


---

# <a name="custom-settings-for-android-devices-in-intune-azure-preview"></a>Vlastní nastavení pro zařízení s Androidem v Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Použijte **vlastní** profil Microsoft Intune pro zařízení s Androidem a nasaďte nastavení OMA-URI, které se dá používat k ovládání funkcí na zařízeních s Androidem. Jsou to standardní nastavení, která k ovládání funkcí zařízení používá spousta výrobců mobilních zařízení.

Díky této vlastnosti můžete nasadit nastavení Androidu, která nejde konfigurovat se zásadami Intune.

## <a name="custom-profile-settings-for-android-devices"></a>Nastavení vlastního profilu pro zařízení s Androidem

1. Začněte podle pokynů v tématu [Jak nakonfigurovat vlastní nastavení zařízení v Microsoft Intune](how-to-configure-custom-settings.md).
2. Pokud chcete přidat nastavení OMA-URI, vyberte v okně **Vytvořit profil** možnost **Nastavení**.
3. V okně **Upravit řádek** nakonfigurujte u jednotlivých nastavení následující hodnoty:
    - **Název** – zadejte jedinečný název pro nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení.
    - **Popis** – zadejte popis, který nastavení přehledně vystihne, a další důležité informace, které vám ho pomůžou najít.
    - **Datový typ** – vyberte datový typ, ve kterém toto nastavení OMA-URI určíte. Vyberte z možností **Řetězec**, **Řetězec (XML)**, **Datum a čas**, **Celé číslo**, **Plovoucí desetinná čárka** nebo **Logická hodnota**.
    - **OMA-URI** – zadejte OMA-URI, u kterého chcete zadat nastavení.
    - **Hodnota** – zadejte hodnotu, kterou chcete přidružit k uvedenému OMA-URI.
4. Po dokončení klikněte na **OK**. Další nastavení můžete přidávat podle potřeby.



<!--HONumber=Feb17_HO1-->


