---
title: Nastavení AirPrintu pro zařízení s iOSem a macOS pomocí Intune
titlesuffix: Microsoft Intune
description: Zjistěte, jak pomocí Microsoft Intune automaticky připojit zařízení s iOSem a macOS k tiskárnám kompatibilním s AirPrintem.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8402ff3631e18ec6169bc96ef1bb7669bdcfbdd8
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/17/2018
---
# <a name="airprint-settings-for-ios-and-macos-devices"></a>Nastavení AirPrintu pro zařízení s iOSem a macOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pomocí těchto nastavení můžete nakonfigurovat zařízení s iOSem nebo macOS tak, aby se automaticky připojovala k tiskárnám ve vaší síti, které jsou kompatibilní s AirPrintem. Budete k tomu potřebovat IP adresy a cesty prostředků tiskáren.

## <a name="find-airprint-printer-information"></a>Vyhledání informací o tiskárně s AirPrintem

Pomocí tohoto postupu můžete přidat informace o AirPrintu do datové části AirPrintu, aby uživatelé zařízení s iOSem mohli používat známé tiskárny s AirPrintem.

1. Na Macu, který je připojený ke stejné místní síti (stejné podsíti) jako tiskárny s AirPrintem, otevřete Terminál (z **/Aplikace/Utility**)
2. V Terminálu zadejte **ippfind** a stiskněte Enter.
3. Poznamenejte si všechny informace o tiskárně, které příkaz vrátí, například: **ipp://myprinter.local.:631/ipp/port1**. První část informací je název tiskárny a druhá část je cesta prostředku.
4. V Terminálu zadejte **ping.myprinter.local** a stiskněte Enter.
5. Poznamenejte si informace o IP adrese vrácené příkazem, například **PING myprinter.local (10.50.25.21)**.
6. Nakonec IP adresu a cestu prostředku použijte v nastavení datové části AirPrintu. Příkladem IP adresy je **10.50.25.21** a příkladem cesty prostředku je **/ipp/port1**.

## <a name="configure-an-airprint-profile"></a>Konfigurace profilu AirPrintu

1. Z [Intune na portálu Azure Portal](https://portal.azure.com) přejděte na [**Funkce zařízení** v oblasti konfigurace zařízení](device-features-configure.md). 
1. V podokně **Funkce zařízení** zvolte **AirPrint**.
2. V podokně **AirPrint** přidáte cíl AirPrintu tak, že zadáte jeho **IP adresu** a **cestu prostředku** a pak kliknete na **Přidat**.
3. Přidejte tolik cílů, kolik potřebujete. Po dokončení zvolte **OK**.

Můžete také importovat seznam tiskáren ze souboru hodnot oddělených čárkami (.csv) nebo seznam exportovat.


## <a name="next-steps"></a>Další kroky

Nyní můžete profil zařízení přiřadit do požadované skupiny. Podrobnosti najdete v tématu [Přiřazení profilů zařízení](device-profile-assign.md).