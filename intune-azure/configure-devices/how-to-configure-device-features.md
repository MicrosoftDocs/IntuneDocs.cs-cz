---
title: "Konfigurace nastavení funkce zařízení ve službě Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Naučte se pomocí služby Intune konfigurovat funkce na zařízeních, která spravujete."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: dd53e547a8f834eff528e79cf2506be1e6c2dc2a
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a>Konfigurace nastavení funkce zařízení ve službě Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Omezení zařízení vám umožní regulovat funkce na zařízeních s iOSem a macOS, jako jsou AirPrint, oznámení a konfigurace sdílených zařízení.

Informace v tomto tématu vás seznámí se základy konfigurace profilů funkce zařízení. Potom si můžete přečíst další témata pro jednotlivé platformy, kde najdete podrobnosti o specifikách různých zařízení.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení omezení zařízení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
3. V okně profilů zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **Název** a **Popis** profilu pro funkce zařízení.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete nastavení použít. V současné době můžete pro funkce zařízení zvolit jednu z následujících platforem:
    - **iOS**
    - **macOS**
6. V rozevíracím seznamu **Typ profilu** zvolte **Funkce zařízení**. 
7. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Podrobnosti o nastaveních na jednotlivých platformách najdete v následujících tématech:
    - [Nastavení iOSu](device-features-for-ios.md)
    - [Nastavení macOS](device-features-for-macos.md)

8. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](how-to-assign-device-profiles.md).




