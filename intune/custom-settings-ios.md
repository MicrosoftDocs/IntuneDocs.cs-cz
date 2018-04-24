---
title: Vlastní nastavení Microsoft Intune pro zařízení s iOSem
titleSuffix: ''
description: Podívejte se na nastavení, která je možné použít ve vlastním profilu iOS v Microsoft Intune.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ada36b11489adbbcaf67db9192c7dd66caadb525
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-ios"></a>Vlastní nastavení Microsoft Intune pro zařízení s iOSem

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pomocí vlastního profilu iOS v Microsoft Intune přiřaďte zařízením se systémem iOS nastavení, která jste vytvořili nástrojem [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12). Pomocí tohoto nástroje se dá vytvořit spousta nastavení, která řídí provoz těchto zařízení, a exportovat je do konfiguračního profilu. Potom můžete tento konfigurační profil naimportovat do vlastního profilu iOSu v Intune a nastavení přiřadit uživatelům a zařízením v organizaci.

Tato funkce umožňuje přiřadit nastavení iOS, která nejdou konfigurovat pomocí jiných typů profilů Intune.


1. Začněte podle pokynů v tématu [Jak nakonfigurovat vlastní nastavení zařízení v Microsoft Intune](custom-settings-configure.md).
2. V podokně **Vlastní konfigurační profil** nakonfigurujte všechna tato nastavení:

- **Název vlastního konfiguračního profilu** – zadejte název zásady tak, jak se zobrazí na zařízení a ve stavu Intune.
- **Soubor konfiguračního profilu** – přejděte na konfigurační profil, který jste vytvořili pomocí Apple Configuratoru.
Nastavení, která exportujete z nástroje Apple Configurator, musí být kompatibilní s verzí iOS na zařízeních, kterým přiřazujete vlastní zásady pro iOS. Informace o tom, jak se řeší nekompatibilní nastavení, najdete v **referenčních materiálech ke konfiguračnímu profil** a **referenčních materiálech k protokolu správy mobilního zařízení** na [webu pro vývojáře Apple](https://developer.apple.com/).

Importovaný soubor se zobrazí v oblasti podokna **Obsah souboru**.
