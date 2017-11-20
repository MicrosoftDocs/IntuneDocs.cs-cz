---
title: "Jak nakonfigurovat nastavení Wi-Fi v Intune"
titleSuffix: Azure portal
description: "Naučte se pomocí Intune nakonfigurovat připojení Wi-Fi pro zařízení, která spravujete."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae5210cb3da5503c4cf1b85be8b8522fa1cfd6ce
ms.sourcegitcommit: 1df625330f4e8f7f661b5f2b9f16b5590971838d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/10/2017
---
# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a>Jak nakonfigurovat nastavení Wi-Fi v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pomocí profilů Wi-Fi v Intune můžete přiřadit nastavení bezdrátové sítě pro uživatele a zařízení ve vaší organizaci. Při přiřazení profilu Wi-Fi budou mít uživatelé přístup k vaší podnikové síti Wi-Fi, aniž by ji museli konfigurovat sami.

Nainstalujete třeba novou síť Wi-Fi s názvem Contoso Wi-Fi a chcete nastavit všechna zařízení s iOSem na připojování k této síti. Postup je následující:

1. Vytvoříte profil Wi-Fi obsahující nastavení potřebná pro připojení k bezdrátové síti Contoso Wi-Fi.
2. Přiřadíte tento profil skupině obsahující všechny uživatele zařízení s iOSem.
3. Uživatelé najdou novou síť Contoso Wi-Fi v seznamu bezdrátových sítí na svém zařízení a můžou se k ní snadno připojit.

Profily Wi-Fi podporují zařízení s následujícími platformami:

- Android 4 nebo novější
- Android for Work
- iOS 8.0 a novější
- macOS (Mac OS X 10.9 a novější)

Pro zařízení s Windows 8.1, Windows 10 a Windows 10 Mobile můžete importovat konfiguraci Wi-Fi, kterou předtím vyexportujete z jiného zařízení.

Informace v tomto tématu vás seznámí se základy konfigurace profilu Wi-Fi. Pak si můžete přečíst další témata pro jednotlivé platformy, kde najdete podrobnosti o specifikách různých zařízení.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení Wi-Fi

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
3. V okně profilů zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **název** a **popis** profilu Wi-Fi.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete použít nastavení Wi-Fi. V současné době můžete pro nastavení Wi-Fi na zařízení zvolit jednu z následujících platforem:
    - **Android**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows 8.1 a novější (import profilu)**
6. V rozevíracím seznamu **Typ profilu** zvolte **Základní Wi-Fi** nebo **Podniková Wi-Fi**. Možnost **Základní Wi-Fi** umožňuje nastavit základní funkce, jako je název sítě a SSID. Možnost **Podniková Wi-Fi** umožňuje nastavit rozšířené informace, například o protokolu EAP (Extensible Authentication Protocol), pokud ho vaše síť Wi-Fi využívá. **Import Wi-Fi** (pro Windows 8.1 a Windows 10) umožňuje importovat nastavení Wi-Fi jako soubor XML, který jste předtím vyexportovali z jiného zařízení.
7. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Podrobnosti o nastaveních na jednotlivých platformách najdete v následujících tématech:
    - [Nastavení Androidu a Androidu for Work](wi-fi-settings-android.md)
    - [Nastavení iOSu](wi-fi-settings-ios.md)
    - [Nastavení macOS](wi-fi-settings-macos.md)
    - [Nastavení Windows Phone 8.1](wi-fi-settings-import-windows-8-1.md)
8. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).
