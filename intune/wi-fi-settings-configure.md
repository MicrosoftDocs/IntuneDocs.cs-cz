---
title: Jak nakonfigurovat nastavení Wi-Fi v Intune
titleSuffix: Microsoft Intune
description: Naučte se pomocí Microsoft Intune nakonfigurovat připojení Wi-Fi pro zařízení, která spravujete.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9a550e2963fa60a91db3ef63f7771bc4ca352d98
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a>Jak nakonfigurovat nastavení Wi-Fi v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pomocí profilů Wi-Fi v Intune můžete přiřadit nastavení bezdrátové sítě pro uživatele a zařízení ve vaší organizaci. Při přiřazení profilu Wi-Fi budou mít uživatelé přístup k vaší podnikové síti Wi-Fi, aniž by ji museli sami konfigurovat.

Nainstalujete třeba novou síť Wi-Fi s názvem Contoso Wi-Fi a chcete nastavit všechna zařízení s iOSem na připojování k této síti. Postup je následující:

1. Vytvoříte profil Wi-Fi obsahující nastavení potřebná pro připojení k bezdrátové síti Contoso Wi-Fi.
2. Přiřadíte tento profil skupině obsahující všechny uživatele zařízení s iOSem.
3. Uživatelé najdou novou síť Contoso Wi-Fi v seznamu bezdrátových sítí na svém zařízení a můžou se k ní snadno připojit.

## <a name="supported-device-platforms"></a>Podporované platformy zařízení

Profily Wi-Fi podporují zařízení s následujícími platformami:

- Android 4 a novější
- Android for Work
- iOS 8.0 a novější
- macOS (Mac OS X 10.9 a novější)

Pro zařízení s Windows 8.1, Windows 10, Windows 10 Mobile a Windows Holographic for Business můžete importovat konfiguraci Wi-Fi, kterou předtím vyexportujete z jiného zařízení.

Informace v tomto tématu vás seznámí se základy konfigurace profilu Wi-Fi. Pak si můžete přečíst další témata pro jednotlivé platformy, kde najdete podrobnosti o specifikách různých zařízení.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení Wi-Fi

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Konfigurace zařízení**.
2. V podokně **Konfigurace zařízení** v části **Spravovat** zvolte **Profily**.
3. V podokně profilů zvolte **Vytvořit profil**.
4. V podokně **Vytvořit profil** zadejte **název** a **popis** profilu Wi-Fi.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete použít nastavení Wi-Fi. V současné době můžete pro nastavení Wi-Fi na zařízení zvolit jednu z následujících platforem:
    - **Androidemem**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 a novější**
    - **Windows 10 a novější**

   > [!IMPORTANT]
   > Pokud chcete vytvořit profil pro zařízení se systémem Windows 10, včetně Windows Holographic for Business, musíte zvolit platformu **Windows 8.1 a novější**. Platforma **Windows 10 a novější** nezahrnuje typ profilu sítě Wi-Fi. 

6. Pro zařízení Apple nebo Android vyberte v rozevíracím seznamu **Typ Wi-Fi** možnost **Základní** nebo **Enterprise**. Možnost **Základní** umožňuje nastavit základní funkce, jako je název sítě a SSID. Možnost **Enterprise** umožňuje nastavit rozšířené informace, například o protokolu EAP (Extensible Authentication Protocol), pokud ho vaše síť Wi-Fi využívá. 

   Profil **Import Wi-Fi** (pro Windows 8.1 a novější verze) umožňuje importovat nastavení Wi-Fi jako soubor XML, který jste předtím vyexportovali z jiného zařízení.
1. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Podrobnosti o nastaveních na jednotlivých platformách najdete v následujících tématech:
    - [Nastavení Androidu a Androidu for Work](wi-fi-settings-android.md)
    - [Nastavení iOSu](wi-fi-settings-ios.md)
    - [Nastavení macOS](wi-fi-settings-macos.md)
    - [Nastavení Windows 8.1 a novějších verzí](wi-fi-settings-import-windows-8-1.md) (včetně Windows Holographic for Business)
1. Až to budete mít, vraťte se do podokna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v podokně se seznamem profilů.

## <a name="next-steps"></a>Další kroky

Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).
