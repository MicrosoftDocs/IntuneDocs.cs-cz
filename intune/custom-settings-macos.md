---
title: Vlastní nastavení Microsoft Intune pro zařízení s macOS
titleSuffix: ''
description: Podívejte se na nastavení, která je možné použít ve vlastním profilu macOS v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 849bf23429ed689ee995784c3a47a802ba7dbf71
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-macos"></a>Vlastní nastavení Microsoft Intune pro zařízení s macOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pomocí vlastního profilu macOS v Microsoft Intune přiřaďte zařízení se systémem macOS nastavení, která jste vytvořili nástrojem [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12). Pomocí tohoto nástroje se dá vytvořit spousta nastavení, která řídí provoz těchto zařízení, a exportovat je do konfiguračního profilu. Potom můžete tento konfigurační profil naimportovat do vlastního profilu macOS v Intune a nastavení přiřadit uživatelům a zařízením v organizaci.

Tato funkce umožňuje přiřadit nastavení macOS, která nejdou konfigurovat pomocí jiných typů profilů Intune.


1. Začněte podle pokynů v tématu [Jak nakonfigurovat vlastní nastavení zařízení v Microsoft Intune](custom-settings-configure.md).
2. V podokně **Vlastní konfigurační profil** nakonfigurujte všechna tato nastavení:

- **Název vlastního konfiguračního profilu** – zadejte název zásady tak, jak se zobrazí na zařízení a ve stavu Intune.
- **Soubor konfiguračního profilu** – přejděte na konfigurační profil, který jste vytvořili pomocí Apple Configuratoru.
Nastavení, která exportujete z nástroje Apple Configurator, musí být kompatibilní s verzí macOS na zařízeních, kterým přiřazujete vlastní zásady pro macOS. Informace o tom, jak se řeší nekompatibilní nastavení, najdete v **referenčních materiálech ke konfiguračnímu profil** a **referenčních materiálech k protokolu správy mobilního zařízení** na [webu pro vývojáře Apple](https://developer.apple.com/).

Importovaný soubor se zobrazí v oblasti podokna **Obsah souboru**.
