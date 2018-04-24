---
title: Konfigurace nastavení omezení zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Přidání profilu zařízení k omezení funkcí v zařízeních s Androidem, macOS, iOSem, Windows Phone a Windows 10 v Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 13f93f9fcf813c2e86809d2cc20991d2fd635187
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Konfigurace nastavení omezení zařízení v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pomocí omezení zařízení můžete ovládat širokou škálu spravovaných nastavení a funkcí v různých kategoriích, jako jsou například:
- Zabezpečení
- Prohlížeč
- Hardware
- Nastavení sdílení dat

Můžete například vytvořit profil omezení zařízení, který uživatelům zařízení s iOSem zabraňuje v přístupu k fotoaparátu.

Naučte se základy o profilech omezení zařízení a pak si přečtěte další články pro jednotlivé platformy, abyste zjistili zvláštnosti zařízení.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení omezení zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
4. Zadejte **název** a **popis** profilu omezení zařízení.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete vlastní nastavení použít. V současné době můžete pro nastavení omezení zařízení zvolit jednu z těchto platforem:
    - **Androidemem**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 a novější**
    - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **Omezení zařízení**. Pokud chcete vytvořit profil omezení zařízení pro zařízení s Windows 10 Team, jako je Surface Hub, zvolte **Omezení zařízení (Windows 10 Team)**.
7. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Podrobnosti o nastaveních na jednotlivých platformách najdete v následujících tématech:
    - [Nastavení Androidu](device-restrictions-android.md)
    - [Nastavení iOSu](device-restrictions-ios.md)
    - [Nastavení macOS](device-restrictions-macos.md)
    - [Nastavení Windows Phone 8.1](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Nastavení Windows 10](device-restrictions-windows-10.md)
    - [Nastavení Windows 10 Team](device-restrictions-windows-10-teams.md)
    - [Nastavení Windows Holographic for Business](device-restrictions-windows-holographic.md)
    - [Nastavení Androidu for Work](device-restrictions-android-for-work.md)
8. Až to budete mít, vraťte se na stránku **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se na stránce se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
