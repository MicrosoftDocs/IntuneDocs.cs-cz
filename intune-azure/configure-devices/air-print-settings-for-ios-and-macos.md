---
title: "Nastavení AirPrintu pro zařízení s iOSem a macOS pomocí Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Zjistěte, jak pomocí Intune automaticky připojit zařízení s iOSem a macOS k tiskárnám kompatibilním s AirPrintem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 4/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: a0f60cad9a5e679c83572375c3dd83bc7aeebd93
ms.lasthandoff: 04/19/2017


---

# <a name="airprint-settings-for-ios-and-macos-devices"></a>Nastavení AirPrintu pro zařízení s iOSem a macOS

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Pomocí těchto nastavení můžete nakonfigurovat zařízení s iOSem nebo macOS tak, aby se automaticky připojovala k tiskárnám ve vaší síti, které jsou kompatibilní s AirPrintem. Budete k tomu potřebovat IP adresy a cesty prostředků tiskáren.

## <a name="find-airprint-printer-information"></a>Vyhledání informací o tiskárně s AirPrintem

Pomocí tohoto postupu můžete přidat informace o AirPrintu do datové části AirPrintu, aby uživatelé zařízení s iOSem mohli používat známé tiskárny s AirPrintem.

1. Na Macu, který je připojený ke stejné místní síti (stejné podsíti) jako tiskárny s Airprintem, otevřete Terminál (z **/Aplikace/Utility**)
2. V Terminálu zadejte **ippfind** a stiskněte Enter.
3. Poznamenejte si všechny informace o tiskárně, které příkaz vrátí, například: **ipp://myprinter.local.:631/ipp/port1**. První část informací je název tiskárny a druhá část je cesta prostředku.
4. V Terminálu zadejte **ping.myprinter.local** a stiskněte Enter.
5. Poznamenejte si informace o IP adrese vrácené příkazem, například **PING myprinter.local (10.50.25.21)**.
6. Nakonec IP adresu a cestu prostředku použijte v nastavení datové části AirPrintu. Příkladem IP adresy je **10.50.25.21** a příkladem cesty prostředku je **/ipp/port1**.

## <a name="configure-an-airprint-profile"></a>Konfigurace profilu AirPrintu

1. V okně **Funkce zařízení** zvolte **AirPrint**.
2. V okně **AirPrint** přidáte cíl AirPrintu tak, že zadáte jeho **IP adresu** a **cestu prostředku**a pak kliknete na **Přidat**.
3. Přidejte tolik cílů, kolik potřebujete. Po dokončení zvolte **OK**.

Můžete také importovat seznam tiskáren ze souboru hodnot oddělených čárkami (.csv) nebo seznam exportovat.

