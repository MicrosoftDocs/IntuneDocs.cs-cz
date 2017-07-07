---
title: "Vlastní nastavení pro zařízení s macOS v Intune"
titleSuffix: Intune on Azure
description: "Zjistěte, jaká nastavení je možné použít ve vlastním profilu macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 57c4ec3621ffaef5c1aaffd55c87baac91e50154
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="custom-settings-for-macos-devices-in-microsoft-intune"></a>Vlastní nastavení pro zařízení s macOS v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pomocí vlastního profilu macOS v Microsoft Intune přiřaďte zařízení se systémem macOS nastavení, která jste vytvořili nástrojem [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12). Pomocí tohoto nástroje se dá vytvořit spousta nastavení, která řídí provoz těchto zařízení, a exportovat je do konfiguračního profilu. Potom můžete tento konfigurační profil naimportovat do vlastního profilu macOS v Intune a nastavení přiřadit uživatelům a zařízením v organizaci.

Tato funkce umožňuje přiřadit nastavení macOS, která nejdou konfigurovat pomocí jiných typů profilů Intune.


1. Začněte podle pokynů v tématu [Jak nakonfigurovat vlastní nastavení zařízení v Microsoft Intune](custom-settings-configure.md).
2. V okně **Vytvořit profil** zadejte následující informace:

- **Název vlastního konfiguračního profilu** – zadejte název zásady v podobě, v jaké se bude zobrazovat na zařízení a ve stavu Intune.
- **Soubor konfiguračního profilu** – přejděte na konfigurační profil, který jste vytvořili pomocí Apple Configuratoru.
Nastavení, která exportujete z nástroje Apple Configurator, musí být kompatibilní s verzí macOS na zařízeních, kterým přiřazujete vlastní zásady pro macOS. Informace o tom, jak se řeší nekompatibilní nastavení, najdete v **referenčních materiálech ke konfiguračnímu profil** a **referenčních materiálech k protokolu správy mobilního zařízení** na [webu pro vývojáře Apple](https://developer.apple.com/).

Importovaný soubor se zobrazí v oblasti okna **Obsah souboru**.