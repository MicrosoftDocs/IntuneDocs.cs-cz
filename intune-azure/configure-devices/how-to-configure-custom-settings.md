---
title: "Jak nakonfigurovat vlastní nastavení zařízení v Intune | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Naučte se pomocí Intune nakonfigurovat vlastní nastavení pro zařízení, která spravujete."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: d9da3f1c2ccade5391e2e874336802602a016700
ms.lasthandoff: 02/16/2017


---

# <a name="how-to-configure-custom-device-settings-in-microsoft-intune"></a>Konfigurace vlastního nastavení v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="when-to-use-custom-settings"></a>Kdy použít vlastní nastavení

Vlastní nastavení zařízení můžou být užitečná, když nastavení, která chcete nakonfigurovat, nejsou v Intune předdefinovaná, ale jsou dostupná z jiných profilů zařízení.
Vlastní nastavení se konfigurují pro každou platformu jinak. U zařízení s Androidem a Windows můžete například funkce zařízení ovládat zadáním hodnot OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Pro zařízení Apple můžete naimportovat soubor vytvořený pomocí [Apple Configuratoru](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

Informace v tomto tématu vás seznámí se základy konfigurace profilů s vlastními nastaveními. Pak si můžete přečíst další témata pro jednotlivé platformy, kde najdete podrobnosti o specifikách různých zařízení.

## <a name="create-a-device-profile-containing-custom-settings"></a>Vytvoření profilu zařízení obsahujícího vlastní nastavení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Konfigurovat zařízení**.
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
    - [Nastavení Androidu](custom-for-android.md)
    - [Nastavení iOSu](custom-for-ios.md)
    - [Nastavení macOS](custom-for-macos.md)
    - [Nastavení Windows Phone 8.1](custom-for-windows-phone-8-1.md)
    - [Nastavení Windows 10](custom-for-windows-10.md)
8. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](how-to-assign-device-profiles.md).


