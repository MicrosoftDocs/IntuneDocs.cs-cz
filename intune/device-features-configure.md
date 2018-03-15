---
title: "Konfigurace nastavení funkcí zařízení v Microsoft Intune"
titleSuffix: 
description: "Naučte se pomocí Microsoft Intune konfigurovat funkce na zařízeních, která spravujete."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6cd646976deb1599c4cbc9154b6f2a487029dd79
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
#<a name="configure-device-feature-settings-in-microsoft-intune"></a>Konfigurace nastavení funkcí zařízení v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Funkcemi zařízení můžete ovládat funkce na zařízeních s iOSem a macOS, jako jsou AirPrint, oznámení a konfigurace sdílených zařízení.

Informace v tomto článku vás seznámí se základy konfigurace profilů funkcí zařízení. Potom si můžete přečíst další články pro jednotlivé platformy, kde najdete podrobnosti o zvláštnostech různých zařízení.

## <a name="create-a-device-profile-containing-device-feature-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení funkcí zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Na stránce **Intune** zvolte **Konfigurace zařízení**.
2. Na stránce **Konfigurace zařízení** v části **Spravovat** zvolte **Profily**.
3. Na stránce profilů zvolte **Vytvořit profil**.
4. Na stránce **Vytvořit profil** zadejte **Název** a **Popis** profilu pro funkce zařízení.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete nastavení použít. V současné době můžete pro funkce zařízení zvolit jednu z následujících platforem:
    - **iOS**
    - **macOS**
6. V rozevíracím seznamu **Typ profilu** zvolte **Funkce zařízení**. 
7. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Podrobnosti o nastaveních na jednotlivých platformách najdete v následujících článcích:
    - [Nastavení AirPrintu pro iOS a MacOS](air-print-settings-ios-macos.md)
    - [Nastavení AirPlay pro iOS](airplay-settings-ios.md)
    - [Nastavení rozložení domovské obrazovky pro iOS](home-screen-settings-ios.md)
    - [Nastavení oznámení aplikace pro iOS](app-notification-settings-ios.md)
    - [Nastavení konfigurace sdíleného zařízení pro iOS](shared-device-settings-ios.md)
    - [Nakonfigurování Intune na jednotné přihlašování pro zařízení s iOSem](sso-ios.md)
    - [Nastavení filtru webového obsahu pro iOS](web-content-filter-settings-ios.md)

8. Až to budete mít, vyberte **OK**, vraťte se na stránku **Vytvořit profil** a zvolte **Vytvořit**.

Profil se vytvoří a zobrazí se na stránce se seznamem profilů.
## <a name="next-steps"></a>Další kroky

Pokud chcete přiřadit tento profil ke skupinám, podívejte se na článek [Přiřazení profilů zařízení](device-profile-assign.md).



