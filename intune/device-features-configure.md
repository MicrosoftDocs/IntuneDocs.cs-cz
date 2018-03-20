---
title: "Vytvoření profilu zařízení se systémem iOS nebo macOS pomocí Microsoft Intune – Azure | Microsoft Docs"
description: "Přidejte nebo vytvořte profil zařízení se systémem iOS nebo macOS a potom nakonfigurujte nastavení pro AirPrint, AirPlay, rozložení domovské obrazovky, oznámení aplikací, sdílené zařízení, jednotné přihlašování a nastavení filtru webového obsahu v Microsoft Intune."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e3de7d1bccd57da1290987a714416373cbdd2b0d
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2018
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Přidání nastavení funkcí zařízení se systémem iOS nebo macOS v Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Funkce zařízení umožňují řídit celou řadu nastavení a funkcí na zařízeních se systémy iOS a macOS, jako jsou například:

- Nastavení AirPrint a AirPlay
- Rozložení domovské obrazovky
- Oznámení z aplikací
- Konfigurace sdíleného zařízení
- Konfigurace jednotného přihlašování
- Filtrování webového obsahu

Tento článek obsahuje základní informace o konfiguraci profilů funkcí zařízení s iOSem. Potom můžete pokračovat dalšími články a konfigurovat nastavení specifická pro danou platformu vašeho zařízení.

## <a name="create-a-device-profile"></a>Vytvoření profilu zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a potom vyberte **Microsoft Intune**.
3. Vyberte **Konfigurace zařízení**, pak **Profily** a pak zvolte **Vytvořit profil**.
4. Zadejte následující vlastnosti:

  - **Název** – Zadejte popisný název nového profilu.
  - **Popis**: (nepovinné – ale doporučené) Zadejte popis profilu.
  - **Platforma**: Vyberte typ platformy:
    - **iOS**
    - **macOS**
  - **Typ profilu**: Vyberte **Funkce zařízení**.
  - **Nastavení**: Nastavení závisí na vámi zvolené platformě. Informace o nastaveních pro jednotlivé typy profilů najdete v následujících článcích:

    - [Nastavení AirPrintu pro iOS a MacOS](air-print-settings-ios-macos.md)
    - [Nastavení AirPlay pro iOS](airplay-settings-ios.md)
    - [Nastavení rozložení domovské obrazovky pro iOS](home-screen-settings-ios.md)
    - [Nastavení oznámení aplikace pro iOS](app-notification-settings-ios.md)
    - [Nastavení konfigurace sdíleného zařízení pro iOS](shared-device-settings-ios.md)
    - [Nakonfigurování Intune na jednotné přihlašování pro zařízení s iOSem](sso-ios.md)
    - [Nastavení filtru webového obsahu pro iOS](web-content-filter-settings-ios.md)

5. Až skončíte, vyberte **OK** a zvolte **Vytvořit**. Provedené změny tak uložíte.

Profil se vytvoří a zobrazí se v seznamu.

## <a name="next-step"></a>Další krok

Pokud chcete přiřadit tento profil ke skupinám, podívejte se na téma [Přiřazení profilů zařízení](device-profile-assign.md).