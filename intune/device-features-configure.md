---
title: "Konfigurace nastavení funkce zařízení ve službě Intune"
titleSuffix: Intune on Azure
description: "Naučte se pomocí služby Intune konfigurovat funkce na zařízeních, která spravujete."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f286119019bb26d8851c766a9d88ad818d7e600b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a>Konfigurace nastavení funkce zařízení ve službě Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Omezení zařízení vám umožní regulovat funkce na zařízeních s iOSem a macOS, jako jsou AirPrint, oznámení a konfigurace sdílených zařízení.

Informace v tomto tématu vás seznámí se základy konfigurace profilů funkce zařízení. Potom si můžete přečíst další témata pro jednotlivé platformy, kde najdete podrobnosti o specifikách různých zařízení.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení omezení zařízení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
3. V okně profilů zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **Název** a **Popis** profilu pro funkce zařízení.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete nastavení použít. V současné době můžete pro funkce zařízení zvolit jednu z následujících platforem:
    - **iOS**
    - **macOS**
6. V rozevíracím seznamu **Typ profilu** zvolte **Funkce zařízení**. 
7. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Podrobnosti o nastaveních na jednotlivých platformách najdete v následujících tématech:
    - [Nastavení AirPrintu pro iOS a MacOS](air-print-settings-ios-macos.md)
    - [Nastavení AirPlay pro iOS](airplay-settings-ios.md)
    - [Nastavení rozložení domovské obrazovky pro iOS](home-screen-settings-ios.md)
    - [Nastavení oznámení aplikace pro iOS](app-notification-settings-ios.md)
    - [Nastavení konfigurace sdíleného zařízení pro iOS](shared-device-settings-ios.md)
    - [Nastavení filtru webového obsahu pro iOS](web-content-filter-settings-ios.md)

8. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).



