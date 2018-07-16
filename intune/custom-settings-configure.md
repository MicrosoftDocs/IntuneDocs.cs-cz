---
title: Používání vlastního nastavení zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Přidejte nebo vytvořte profil k používání vlastních nastavení pro zařízení s Windows, Androidem a iOSem pomocí Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d917d2449e75b89db00d453b72940a93efb03321
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/07/2018
ms.locfileid: "37904998"
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Vytvoření profilu s vlastním nastavením v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune nemusí mít všechna předdefinovaná nastavení, která potřebujete nebo chcete. Nebo můžete chtít použít nastavení, které je k dispozici v jiných profilech zařízení. Pokud tato nastavení chcete přidat, vytvořte profil zařízení a nakonfigurujte v něm vlastní nastavení zařízení.

V tomto článku najdete základní kroky k vytvoření profilu s vlastním nastavením. Obsahuje také odkazy na podrobnější informace o vytváření vlastních nastavení s různými platformami.

## <a name="custom-settings-on-different-platforms"></a>Vlastní nastavení na různých platformách
Vlastní nastavení se konfigurují pro každou platformu jinak. Třeba k ovládání funkcí na zařízeních s Androidem a Windows můžete zadat hodnoty OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Pro zařízení Apple můžete naimportovat soubor vytvořený pomocí [Apple Configuratoru](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

## <a name="create-the-profile"></a>Vytvoření profilu

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Konfigurace zařízení**, pak **Profily** a pak zvolte **Vytvořit profil**.
4. Zadejte **Název** a **Popis** vlastního profilu.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, na kterou chcete vlastní nastavení použít. Můžete vybrat kteroukoli z těchto platforem:

    - **Androidemem**
    - **Android Enterprise**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 a novější**
    - **Windows 10 a novější**

6. V rozevíracím seznamu **Typ profilu** zvolte **Vlastní**.
7. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Další podrobnosti o vlastních nastaveních pro každou platformu najdete na těchto odkazech:

    - [Nastavení Androidu](custom-settings-android.md)
    - [Nastavení iOSu](custom-settings-ios.md)
    - [Nastavení macOS](custom-settings-macos.md)
    - [Nastavení Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
    - [Nastavení Windows 10](custom-settings-windows-10.md)
    - [Nastavení Windows Holographic for Business](custom-settings-windows-holographic.md)
    - [Nastavení pracovního profilu Androidu](custom-settings-android-for-work.md)

8. Až budete hotoví, vyberte **Vytvořit**.

Profil se vytvoří a zobrazí se v seznamu profilů. Pokud chcete tento profil přiřadit ke skupinám, přečtěte si článek [Přiřazení profilů zařízení](device-profile-assign.md).
