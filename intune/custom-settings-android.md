---
title: "Vlastní nastavení pro zařízení s Androidem v Intune"
titleSuffix: Intune on Azure
description: "Zjistěte, jaká nastavení je možné použít ve vlastním profilu Androidu."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45a3a8fe4960cc1bb8c5f2150f57d34d59c08e0a
ms.sourcegitcommit: 1c71fff769ca0097faf46fc2b58b953ff28386e8
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/08/2017
---
# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Vlastní nastavení pro zařízení s Androidem v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

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

## <a name="next-steps"></a>Další kroky

Po dokončení nastavení se vytvoří profil, který se zobrazí v okně se seznamem profilů. Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).

Některé příklady užitečných vlastních nastavení najdete v částech:

- [Vytvoření profilu sítě Wi-Fi s předsdíleným klíčem pomocí vlastního profilu zařízení v Microsoft Intune](/intune/wi-fi-profile-shared-key)
- [Vytvoření profilu VPN pro aplikaci pro zařízení s Androidem můžete pomocí vlastního profilu Microsoft Intune](/intune/android-pulse-secure-per-app-vpn)
- [Použití vlastních zásad pro povolení a blokování aplikací pro zařízení se Samsung KNOX Standardem v Microsoft Intune](/intune/samsung-knox-apps-allow-block)
