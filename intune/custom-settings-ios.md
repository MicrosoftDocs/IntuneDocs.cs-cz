---
title: Přidání vlastního nastavení do zařízení s iOSem v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Exportujte nastavení iOSu z nástrojů Apple Configurator nebo Apple Profile Manager a pak ho naimportujte do Microsoft Intune. S těmito nastaveními můžete vytvářet, používat a ovládat vlastní nastavení a funkce zařízení s iOSem. Tento vlastní profil pak můžete v organizaci přiřadit zařízením s iOSem nebo ho mezi ně distribuovat, abyste vytvořili základní nebo standardní nastavení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8e1edae77144b85d100bf590716768792afd8470
ms.sourcegitcommit: 9a4c5b6c2ce511edaeace25426a23f180cb71e15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/07/2019
ms.locfileid: "57565533"
---
# <a name="use-custom-settings-for-ios-devices-in-microsoft-intune"></a>Použití vlastních nastavení u zařízení s iOSem v Microsoft Intune

V Microsoft Intune můžete vlastní profily použít k přidání nebo vytvoření vlastního nastavení pro zařízení s iOSem. Vlastní profily jsou funkcí Intune. Jsou navržené tak, aby bylo možné přidat nastavení a funkce zařízení, které nejsou integrované do Intune.

U zařízení s iOSem existují dva způsoby, jak do Intune dostat vlastní nastavení:

- [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Apple Profile Manager](https://support.apple.com/profile-manager)

Tyto nástroje můžete použít k exportu nastavení do konfiguračního profilu. Tento soubor naimportujete do Intune a pak profil přiřadíte uživatelům a zařízením s iOSem. Jakmile profil přiřadíte, nastavení se distribuuje a také se vytvoří základní nebo standardní iOS vaší organizace.

V tomto článku si ukážeme, jak vytvořit vlastní profil pro zařízení s iOSem. Článek také obsahuje některé pokyny k používání Apple Configuratoru a Apple Profile Manageru.

## <a name="before-you-begin"></a>Před zahájením

- Pokud k vytvoření konfiguračního profilu použijete **Apple Configurator**, ujistěte se, že je exportované nastavení kompatibilní s verzí iOSu na používaných zařízeních. Informace potřebné k řešení nekompatibilních nastavení najdete v **referenčních materiálech k profilu konfigurace** a **referenčních materiálech k protokolu správy mobilních zařízení** na webu pro [vývojáře Apple](https://developer.apple.com/).

- Pokud používáte **Apple Profile Manager**, nezapomeňte:

  - Povolit v Profile Manageru [správu mobilních zařízení](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C).
  - Přidat v Profile Manageru [zařízení s iOSem](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984).
  - Po přidání zařízení v Profile Manageru přejděte na **Under the Library** (pod Knihovna)  > **Devices** (Zařízení) > vyberte zařízení > **Settings** (Nastavení). Zadejte obecné nastavení zařízení.

    Stáhněte a uložte si tento soubor. Zadáte ho v profilu Intune.

  - Nezapomeňte zkontrolovat, jestli je nastavení, které jste exportovali z Apple Profile Manageru, kompatibilní s verzí iOSu na používaných zařízeních. Informace potřebné k řešení nekompatibilních nastavení najdete v **referenčních materiálech k profilu konfigurace** a **referenčních materiálech k protokolu správy mobilních zařízení** na webu pro [vývojáře Apple](https://developer.apple.com/).

## <a name="create-the-profile"></a>Vytvoření profilu

1. Na [portálu Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte následující nastavení:

    - **Název**: Zadejte název profilu, jako například `ios custom profile`.
    - **Popis**: Zadejte popis profilu.
    - **Platforma**: Zvolte **iOS**.
    - **Typ profilu**: Zvolte **vlastní**.

4. V části **Vlastní konfigurace** zadejte následující nastavení:

    - **Název vlastního konfiguračního profilu**: Zadejte název pro tuto zásadu. Tento název se zobrazí na zařízení a ve stavu Intune.
    - **Soubor konfiguračního profilu**: Přejděte na konfigurační profil, který jste vytvořili pomocí nástroje Apple Configurator nebo Apple profilu správce. Importovaný soubor se zobrazí v části **Obsah souboru**.

5. Vyberte **OK** > **Vytvořit** a vytvořte profil Intune. Hotový profil se zobrazí v seznamu **Konfigurace zařízení – Profily**.

## <a name="next-steps"></a>Další postup

Profil je vytvořený, ale zatím se nepoužívá. V dalším kroku [profil přiřadíte](device-profile-assign.md).

Podívejte se, jak [vytvořit profil na zařízeních s macOS](custom-settings-macos.md). 
