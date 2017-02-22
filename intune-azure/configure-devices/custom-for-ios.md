---
title: "Vlastní nastavení Intune pro zařízení se systémem iOS | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Podívejte se na nastavení, která je možné použít ve vlastním profilu iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6da8caa8-65c2-4f47-842f-9570dcb1ac22
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab494a3dd1e1bdea9703ab314574b192c5208ee
ms.openlocfilehash: cfccdbf34437c5ab23cefba5307c53c60573ddb0


---

# <a name="intune-custom-settings-for-ios-devices-in-intune-azure-preview"></a>Vlastní nastavení pro zařízení se systémem iOS v Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Pomocí vlastního profilu iOS v Microsoft Intune nasaďte do zařízení se systémem iOS nastavení, které jste vytvořili pomocí [Apple Configuratoru](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12). Pomocí tohoto nástroje se dá vytvořit spousta nastavení, která řídí provoz těchto zařízení, a exportovat je do konfiguračního profilu. Potom můžete tento konfigurační profil naimportovat do vlastního profilu iOSu v Intune a nastavení přiřadit uživatelům a zařízením v organizaci.

Díky této funkci můžete nasadit nastavení iOS, která nejdou konfigurovat s jinými typy profilů Intune.


1. Začněte podle pokynů v tématu [Jak nakonfigurovat vlastní nastavení zařízení v Microsoft Intune](how-to-configure-custom-settings.md).
2. V okně **Vytvořit profil** zadejte následující informace:

- **Název vlastního konfiguračního profilu** – zadejte název zásady v podobě, v jaké se bude zobrazovat na zařízení a ve stavu Intune.
- **Soubor konfiguračního profilu** – přejděte na konfigurační profil, který jste vytvořili pomocí Apple Configuratoru.
Nastavení, které exportujete z nástroje Apple Configurator, musí být kompatibilní s verzí iOS na zařízeních, na která nasazujete vlastní zásady pro iOS. Informace o tom, jak se řeší nekompatibilní nastavení, najdete v **referenčních materiálech ke konfiguračnímu profil** a **referenčních materiálech k protokolu správy mobilního zařízení** na [webu pro vývojáře Apple](https://developer.apple.com/).

Importovaný soubor se zobrazí v oblasti okna **Obsah souboru**.



<!--HONumber=Feb17_HO1-->


