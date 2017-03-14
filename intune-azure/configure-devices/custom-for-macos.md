---
title: "Vlastní nastavení pro zařízení s macOS v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Podívejte se na nastavení, která je možné použít ve vlastním profilu macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 84902bb0e7ea67b388debd8bd7992d396d981a7b
ms.lasthandoff: 02/18/2017


---

# <a name="custom-settings-for-macos-devices-in-microsoft-intune"></a>Vlastní nastavení pro zařízení s macOS v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Pomocí vlastního profilu macOS v Microsoft Intune nasaďte do zařízení se systémem macOS nastavení, které jste vytvořili pomocí [Apple Configuratoru](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12). Pomocí tohoto nástroje se dá vytvořit spousta nastavení, která řídí provoz těchto zařízení, a exportovat je do konfiguračního profilu. Potom můžete tento konfigurační profil naimportovat do vlastního profilu macOS v Intune a nastavení přiřadit uživatelům a zařízením v organizaci.

Díky této funkci můžete nasadit nastavení macOS, která nejdou konfigurovat s jinými typy profilů Intune.


1. Začněte podle pokynů v tématu [Jak nakonfigurovat vlastní nastavení zařízení v Microsoft Intune](how-to-configure-custom-settings.md).
2. V okně **Vytvořit profil** zadejte následující informace:

- **Název vlastního konfiguračního profilu** – zadejte název zásady v podobě, v jaké se bude zobrazovat na zařízení a ve stavu Intune.
- **Soubor konfiguračního profilu** – přejděte na konfigurační profil, který jste vytvořili pomocí Apple Configuratoru.
Nastavení, které exportujete z Apple Configuratoru, musí být kompatibilní s verzí macOS na zařízeních, na která nasazujete vlastní zásady pro macOS. Informace o tom, jak se řeší nekompatibilní nastavení, najdete v **referenčních materiálech ke konfiguračnímu profil** a **referenčních materiálech k protokolu správy mobilního zařízení** na [webu pro vývojáře Apple](https://developer.apple.com/).

Importovaný soubor se zobrazí v oblasti okna **Obsah souboru**.

