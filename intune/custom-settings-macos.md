---
title: Přidání vlastního nastavení do zařízení s macOS v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Nastavení macOS můžete exportovat z nástrojů Apple Configurator nebo Apple Profile Manager a pak je importovat do Microsoft Intune. Díky těmto nastavením můžete vytvářet, používat a ovládat vlastní nastavení a funkce zařízení s macOS. Vlastní profil pak můžete přiřadit zařízením s macOS v organizaci nebo je mezi ně distribuovat, a vytvořit tak základní nebo standardní nastavení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3bb4691ff46b4d28254d11fb94fa5b2fbcffaa6f
ms.sourcegitcommit: c969b596ec0fec227484c50f210ba4e159e2e533
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/24/2018
ms.locfileid: "49983172"
---
# <a name="use-custom-settings-for-macos-devices-in-microsoft-intune"></a>Použití vlastního nastavení u zařízení s macOS v Microsoft Intune

V Microsoft Intune můžete použít vlastní profil k přidání nebo vytvoření vlastního nastavení zařízení s macOS. Vlastní profily jsou funkcí Intune. Jsou navržené tak, aby bylo možné přidat nastavení a funkce zařízení, které nejsou integrované do Intune.

U zařízení s macOS existují dva způsoby, jak do Intune dostat vlastní nastavení:

- [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Apple Profile Manager](https://support.apple.com/profile-manager)

Tyto nástroje můžete použít k exportu nastavení do konfiguračního profilu. Tento soubor importujete do Intune a pak profil přiřadíte uživatelům a zařízením s macOS. Jakmile je profil přiřazený, nastavení se distribuují a vytvoří se základní nebo standardní macOS vaší organizace.

V tomto článku si ukážeme, jak vytvořit vlastní profil pro zařízení s macOS. Článek také obsahuje některé pokyny k používání Apple Configuratoru a Apple Profile Manageru.

## <a name="before-you-begin"></a>Před zahájením

- Pokud k vytvoření konfiguračního profilu použijete **Apple Configurator**, ujistěte se, že je exportované nastavení kompatibilní s verzí macOS na používaných zařízeních. Informace potřebné k řešení nekompatibilních nastavení najdete v **referenčních materiálech k profilu konfigurace** a **referenčních materiálech k protokolu správy mobilních zařízení** na webu pro [vývojáře Apple](https://developer.apple.com/).

- Pokud používáte **Apple Profile Manager**, nezapomeňte:

  - Povolit [správu mobilních zařízení](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C) v Profile Manageru.
  - Přidat [zařízení s macOS](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984) v Profile Manageru.
  - Po přidání zařízení v Profile Manageru přejděte na **Under the Library** (pod Knihovna)  > **Devices** (Zařízení) > vyberte zařízení > **Settings** (Nastavení). Zadejte obecné nastavení, nastavení zabezpečení, ochrany osobních údajů, adresáře a certifikátu zařízení.

    Soubor si stáhněte a uložte. Zadáte ho v profilu Intune. 

  - Nezapomeňte zkontrolovat, jestli je nastavení, které jste exportovali z Apple Profile Manageru, kompatibilní s verzí macOS na používaných zařízeních. Informace potřebné k řešení nekompatibilních nastavení najdete v **referenčních materiálech k profilu konfigurace** a **referenčních materiálech k protokolu správy mobilních zařízení** na webu pro [vývojáře Apple](https://developer.apple.com/).

## <a name="create-the-profile"></a>Vytvoření profilu

1. Na [portálu Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte následující nastavení:

    - **Název:** Zadejte název profilu, třeba `macos custom profile`.
    - **Popis**: Zadejte popis profilu.
    - **Platforma:** Zvolte **macOS**.
    - **Typ profilu:** Zvolte **Vlastní**.

4. V části **Vlastní konfigurace** zadejte následující nastavení:

    - **Název vlastního konfiguračního profilu:** Zadejte název zásady. Tento název se zobrazí na zařízení a ve stavu Intune.
    - **Soubor konfiguračního profilu:** Přejděte ke konfiguračnímu profilu vytvořenému v Apple Configuratoru nebo Apple Profile Manageru. Importovaný soubor se zobrazí v části **Obsah souboru**.

5. Vyberte **OK** > **Vytvořit** a vytvořte profil Intune. Hotový profil se zobrazí v seznamu **Konfigurace zařízení – Profily**.

## <a name="next-steps"></a>Další kroky

Profil je vytvořený, ale zatím se nepoužívá. V dalším kroku [profil přiřadíte](device-profile-assign.md).

Podívejte se, jak [vytvořit profil na zařízeních s iOSem](custom-settings-ios.md).