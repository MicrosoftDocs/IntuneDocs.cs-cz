---
title: "Konfigurace vlastního nastavení pro zařízení v Intune"
titleSuffix: Azure portal
description: "Naučte se pomocí Intune nakonfigurovat vlastní nastavení pro zařízení, která spravujete."
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
ms.openlocfilehash: 14c85b04c18edb2dfa9bdf3b73457448ad8ef8c8
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-configure-custom-device-settings-in-microsoft-intune"></a>Konfigurace vlastního nastavení v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="when-to-use-custom-settings"></a>Kdy použít vlastní nastavení

Vlastní nastavení zařízení můžou být užitečná, když nastavení, která chcete nakonfigurovat, nejsou v Intune předdefinovaná, ale jsou dostupná z jiných profilů zařízení.
Vlastní nastavení se konfigurují pro každou platformu jinak. U zařízení s Androidem a Windows můžete například funkce zařízení ovládat zadáním hodnot OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Pro zařízení Apple můžete naimportovat soubor vytvořený pomocí [Apple Configuratoru](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

Informace v tomto tématu vás seznámí se základy konfigurace profilů s vlastními nastaveními. Pak si můžete přečíst další témata pro jednotlivé platformy, kde najdete podrobnosti o specifikách různých zařízení.

## <a name="create-a-device-profile-containing-custom-settings"></a>Vytvoření profilu zařízení obsahujícího vlastní nastavení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
3. V okně profilů zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **název** a **popis** vlastního profilu.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete vlastní nastavení použít. V současné době můžete pro vlastní nastavení zařízení zvolit jednu z následujících platforem:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **Vlastní**.
7. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Podrobnosti o nastaveních na jednotlivých platformách najdete v následujících tématech:
    - [Nastavení Androidu](custom-settings-android.md)
    - [Nastavení iOSu](custom-settings-ios.md)
    - [Nastavení macOS](custom-settings-macos.md)
    - [Nastavení Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
    - [Nastavení Windows 10](custom-settings-windows-10.md)
    - [Nastavení Androidu for Work](custom-settings-android-for-work.md)
8. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).
