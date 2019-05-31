---
title: Vytvoření profilu Wi-Fi pro zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Projděte si postup vytvoření konfiguračního profilu zařízení v Microsoft Intune. Vytvořte profily pro Android, Android Enterprise, veřejný terminál s Androidem, iOS, macOS, Windows 10 a novější a Windows Holographic for Business. Pomocí těchto profilů můžete vytvořit připojení Wi-Fi pro použití certifikátů, volbu typu protokolu EAP, výběr metody ověřování, povolení proxy a další.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7dc28a614514bf9b1a4987976cb057529b75a5fc
ms.sourcegitcommit: 063177c6c365fef3642edd7c455790958469aad9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412001"
---
# <a name="add-and-use-wi-fi-settings-on-your-devices-in-microsoft-intune"></a>Přidání a použití nastavení Wi-Fi na zařízeních v Microsoft Intune

Wi-Fi je bezdrátové sítě, který používá mnoho mobilních zařízení získat přístup k síti. Microsoft Intune zahrnuje předdefinované nastavení Wi-Fi, které se dají nasadit pro uživatele a zařízení ve vaší organizaci. Tato skupina nastavení se nazývá "profil" a je možné přiřadit různým uživatelům a skupinám. Po přiřazení, získají uživatelé přístup síť Wi-Fi ve vaší organizaci bez konfigurace sami.

Můžete třeba nainstalovat novou Wi-Fi síť nazvanou Contoso Wi-Fi. Potom můžete třeba nastavit, že se všechna zařízení s iOSem mají připojovat k této síti. Postup je následující:

1. Vytvoření profilu Wi-Fi obsahující nastavení, která se připojují k bezdrátové síti Contoso Wi-Fi.
2. Přiřaďte profil ke skupině, která obsahuje všechny uživatele zařízení s Iosem.
3. Uživatelé najdou novou síť Contoso Wi-Fi v seznamu bezdrátových sítí na svém zařízení. Potom se mohou k této síti připojit s využitím metody ověřování, kterou zvolíte.

V tomto článku jsou uvedené kroky k vytvoření profilu sítě Wi-Fi. Obsahuje také odkazy, které popisují různá nastavení pro každou platformu.

## <a name="supported-device-platforms"></a>Podporované platformy zařízení

Profily Wi-Fi podporují zařízení s následujícími platformami:

- Android 4 a novější
- Android Enterprise a beznabídkový režim
- iOS 8.0 a novější
- macOS (Mac OS X 10.11 a novější)
- Windows 10 a novější, Windows 10 Mobile a Windows Holographic for Business

> [!NOTE]
> Pro zařízení s Windows 8.1 můžete importovat konfiguraci Wi-Fi, kterou předtím vyexportujete z jiného zařízení.

## <a name="create-a-device-profile"></a>Vytvoření profilu zařízení

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte **Název** a **Popis** profilu Wi-Fi.
4. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, na kterou chcete nastavení Wi-Fi použít. Možnosti:

    - **Android**
    - **Android Enterprise**
    - **iOS**
    - **macOS**
    - **Windows 8.1 a novější**
    - **Windows 10 a novější**

5. Jako **Typ profilu** zvolte **Wi-Fi**.

    - U zařízení s **Androidem Enterprise**, která se používají jako veřejný terminál, můžete zvolit **Jen vlastník zařízení** > **Wi-Fi**.
    - U **Windows 8.1 a novějších verzí** můžete zvolit **Import Wi-Fi**. Tato možnost umožňuje importovat nastavení Wi-Fi jako soubor XML, který jste předtím vyexportovali z jiného zařízení.

6. Některá nastavení Wi-Fi se u jednotlivých platforem liší. Pokud se chcete podívat na nastavení pro konkrétní platformu, zvolte:

    - [Android](wi-fi-settings-android.md)
    - [Android Enterprise a beznabídkový režim](wi-fi-settings-android-enterprise.md)
    - [iOS](wi-fi-settings-ios.md)
    - [macOS](wi-fi-settings-macos.md)
    - [Windows 10 a novější](wi-fi-settings-windows.md)
    - [Windows 8.1 a novější](wi-fi-settings-import-windows-8-1.md) (včetně Windows Holographic for Business)

    Většina platforem má nastavení **Základní** a **Enterprise**. **Základní** nastavení obsahuje funkce, jako je název sítě a SSID. Možnost **Enterprise** umožňuje nastavit rozšířené informace, například k protokolu EAP (Extensible Authentication Protocol).

7. Až přidáte veškerá nastavení Wi-Fi, vyberte **Vytvořit profil** > **Vytvořit** a přidejte konfigurační profil. Profil se vytvoří a zobrazí se v seznamu profilů (**Konfigurace zařízení** > **Profily**).

## <a name="next-steps"></a>Další postup

Profil se vytvoří, ale nic nedělá. Dále [tento profil přiřadit](device-profile-assign.md) a [monitorování jejího stavu.](device-profile-monitor.md).
