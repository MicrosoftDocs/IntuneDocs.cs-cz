---
title: "Vlastní nastavení Intune pro zařízení s iOSem"
titleSuffix: Azure portal
description: "Zjistěte, jaká nastavení je možné použít ve vlastním profilu iOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6da8caa8-65c2-4f47-842f-9570dcb1ac22
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 761b19de8442e88717a5dcd52f7f0375bace91da
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="microsoft-intune-custom-settings-for-ios-devices"></a>Vlastní nastavení Microsoft Intune pro zařízení s iOSem

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pomocí vlastního profilu iOS v Microsoft Intune přiřaďte zařízením se systémem iOS nastavení, která jste vytvořili nástrojem [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12). Pomocí tohoto nástroje se dá vytvořit spousta nastavení, která řídí provoz těchto zařízení, a exportovat je do konfiguračního profilu. Potom můžete tento konfigurační profil naimportovat do vlastního profilu iOSu v Intune a nastavení přiřadit uživatelům a zařízením v organizaci.

Tato funkce umožňuje přiřadit nastavení iOS, která nejdou konfigurovat pomocí jiných typů profilů Intune.


1. Začněte podle pokynů v tématu [Jak nakonfigurovat vlastní nastavení zařízení v Microsoft Intune](custom-settings-configure.md).
2. V okně **Vytvořit profil** zadejte následující informace:

- **Název vlastního konfiguračního profilu** – zadejte název zásady v podobě, v jaké se bude zobrazovat na zařízení a ve stavu Intune.
- **Soubor konfiguračního profilu** – přejděte na konfigurační profil, který jste vytvořili pomocí Apple Configuratoru.
Nastavení, která exportujete z nástroje Apple Configurator, musí být kompatibilní s verzí iOS na zařízeních, kterým přiřazujete vlastní zásady pro iOS. Informace o tom, jak se řeší nekompatibilní nastavení, najdete v **referenčních materiálech ke konfiguračnímu profil** a **referenčních materiálech k protokolu správy mobilního zařízení** na [webu pro vývojáře Apple](https://developer.apple.com/).

Importovaný soubor se zobrazí v oblasti okna **Obsah souboru**.
