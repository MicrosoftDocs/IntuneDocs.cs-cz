---
title: Vytvoření profilu Wi-Fi pro zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Projděte si postup vytvoření konfiguračního profilu zařízení v Microsoft Intune. Můžete vytvořit profily pro Android, Android Enterprise, beznabídkový režim Androidu, iOS, macOS, Windows 10 a novější a Windows Holographic for Business. Pomocí těchto profilů můžete vytvořit připojení Wi-Fi pro použití certifikátů, volbu typu protokolu EAP, výběr metody ověřování, povolení proxy a další.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 16273910220dae238e15910af0557dd8b73646b9
ms.sourcegitcommit: cff65435df070940da390609d6376af6ccdf0140
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2018
ms.locfileid: "49425253"
---
# <a name="add-and-use-wi-fi-settings-on-your-devices-in-microsoft-intune"></a>Přidání a použití nastavení Wi-Fi na zařízeních v Microsoft Intune

Pomocí profilů Wi-Fi v Intune můžete přiřadit nastavení bezdrátové sítě pro uživatele a zařízení ve vaší organizaci. Při přiřazení profilu Wi-Fi budou mít uživatelé přístup k síti Wi-Fi vaší organizace, aniž by ji museli sami konfigurovat.

Můžete třeba nainstalovat novou Wi-Fi síť nazvanou Contoso Wi-Fi. Potom můžete třeba nastavit, že se všechna zařízení s iOSem mají připojovat k této síti. Postup je následující:

1. Vytvořte profil Wi-Fi, který obsahuje nastavení potřebná pro připojení k bezdrátové síti Contoso Wi-Fi.
2. Přiřaďte tento profil skupině obsahující všechny uživatele zařízení s iOSem.
3. Uživatelé najdou novou síť Contoso Wi-Fi v seznamu bezdrátových sítí na svém zařízení. Potom se mohou k této síti připojit s využitím metody ověřování, kterou zvolíte.

Pomocí postupu v tomto článku vytvořte profil Wi-Fi. Potom si projděte témata týkající se nastavení a podrobností ke konkrétním platformám.

## <a name="supported-device-platforms"></a>Podporované platformy zařízení

Profily Wi-Fi podporují zařízení s následujícími platformami:

- Android 4 a novější
- Android Enterprise a beznabídkový režim
- iOS 8.0 a novější
- macOS (Mac OS X 10.11 a novější)
- Windows 10 a novější, Windows 10 Mobile a Windows Holographic for Business

> [!NOTE]
> Pro zařízení s Windows 8.1 můžete importovat konfiguraci Wi-Fi, kterou předtím vyexportujete z jiného zařízení.

## <a name="create-a-wi-fi-device-profile"></a>Vytvoření profilu zařízení Wi-Fi

1. Na webu [Azure Portal](https://portal.azure.com) vyberte **Všechny služby** > vyfiltrujte **Intune** a vyberte **Microsoft Intune**. 
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte **Název** a **Popis** profilu Wi-Fi.
4. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, na kterou chcete nastavení Wi-Fi použít. Možnosti:

    - **Androidemem**
    - **Android Enterprise**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 a novější**
    - **Windows 10 a novější**

5. Jako **Typ profilu** zvolte **Wi-Fi**.

    - U zařízení s **Androidem Enterprise**, která se používají jako veřejný terminál, můžete zvolit **Jen vlastník zařízení** > **Wi-Fi**.
    - U **Windows 8.1 a novějších verzí** můžete zvolit **Import Wi-Fi**. Tato možnost umožňuje importovat nastavení Wi-Fi jako soubor XML, který jste předtím vyexportovali z jiného zařízení.

6. Některá nastavení Wi-Fi se u jednotlivých platforem liší. Pokud se chcete podívat na nastavení pro konkrétní platformu, zvolte:

    - [Androidemem](wi-fi-settings-android.md)
    - [Android Enterprise a beznabídkový režim](wi-fi-settings-android-enterprise.md)
    - [iOS](wi-fi-settings-ios.md)
    - [macOS](wi-fi-settings-macos.md)
    - [Windows 10 a novější](wi-fi-settings-windows.md)
    - [Windows 8.1 a novější](wi-fi-settings-import-windows-8-1.md) (včetně Windows Holographic for Business)

    Většina platforem má nastavení **Základní** a **Enterprise**. **Základní** nastavení obsahuje funkce, jako je název sítě a SSID. Možnost **Enterprise** umožňuje nastavit rozšířené informace, například k protokolu EAP (Extensible Authentication Protocol).

7. Až přidáte veškerá nastavení Wi-Fi, vyberte **Vytvořit profil** > **Vytvořit** a přidejte konfigurační profil. Profil se vytvoří a zobrazí se v seznamu profilů (**Konfigurace zařízení** > **Profily**).

## <a name="next-steps"></a>Další kroky

Profil se vytvoří, ale nic nedělá. Dále [tento profil přiřaďte](device-profile-assign.md).
