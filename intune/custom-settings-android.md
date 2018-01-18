---
title: "Vlastní nastavení pro zařízení s Androidem v Intune"
titleSuffix: Azure portal
description: "Zjistěte, jaká nastavení je možné použít ve vlastním profilu Androidu."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b1ccb3b0b7b2ce024ff6a09d7f9d8366896fb67
ms.sourcegitcommit: 5004b9564915712b41860df20324f39fac3dc27d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/03/2018
---
# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Vlastní nastavení pro zařízení s Androidem v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pomocí **vlastního** profilu Android v Microsoft Intune přiřaďte nastavení OMA-URI, která se dají používat k ovládání funkcí na zařízeních s Androidem. Jsou to standardní nastavení, která k ovládání funkcí zařízení používá spousta výrobců mobilních zařízení.

Tato vlastnost umožňuje přiřadit následující nastavení Androidu, která nejdou konfigurovat pomocí zásad Intune:

- [Vytvoření profilu sítě Wi-Fi s předsdíleným klíčem pomocí vlastního profilu zařízení v Microsoft Intune](/intune/wi-fi-profile-shared-key)
- [Vytvoření profilu VPN pro aplikaci pro zařízení s Androidem můžete pomocí vlastního profilu Microsoft Intune](/intune/android-pulse-secure-per-app-vpn)
- [Použití vlastních zásad, které v Microsoft Intune povolí nebo blokují aplikace pro zařízení se zabezpečením Samsung Knox Standard](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
>Tímto typem profilu se v současnosti dají konfigurovat jenom nastavení uvedená výše. Zařízení s Androidem nezveřejňují úplný seznam nastavení OMA-URI, která můžete konfigurovat. Pokud chcete, abychom přidali další nastavení, požádejte o ně na [webu Intune Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas).

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




