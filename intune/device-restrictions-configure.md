---
title: Konfigurace nastavení omezení zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Přidání profilu zařízení k omezení funkcí v zařízeních s Androidem, macOS, iOSem, Windows Phone a Windows 10 v Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6e040743975a482c702e0c0168a4fd6315a2dac8
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61505739"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Konfigurace nastavení omezení zařízení v Microsoft Intune

Pomocí omezení zařízení můžete ovládat širokou škálu spravovaných nastavení a funkcí v různých kategoriích, jako jsou například:
- Zabezpečení
- Prohlížeč
- Hardware
- Nastavení sdílení dat

Můžete například vytvořit profil omezení zařízení, který uživatelům zařízení s iOSem zabraňuje v přístupu k fotoaparátu.

Naučte se základy o profilech omezení zařízení a pak si přečtěte další články pro jednotlivé platformy, abyste zjistili zvláštnosti zařízení.

## <a name="create-the-profile"></a>Vytvoření profilu

1. V k [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte **název** a **popis** profilu omezení zařízení.
4. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete vlastní nastavení použít. V současné době můžete pro nastavení omezení zařízení zvolit jednu z těchto platforem:

    - **Android**
    - **Android Enterprise**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 a novější**
    - **Windows 10 a novější**

5. V rozevíracím seznamu **Typ profilu** zvolte **Omezení zařízení**. Chcete-li vytvořit zařízení omezení profilu pro zařízení s Windows 10 Team, jako je Surface Hub, a pak zvolte **omezení zařízení (Windows 10 Team)**.
6. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Zvolte vaši platformu, pro podrobné informace o nastavení:

    - [Nastavení Androidu](device-restrictions-android.md)
    - [Nastavení androidu enterprise](device-restrictions-android-for-work.md)
    - [Nastavení iOSu](device-restrictions-ios.md)
    - [Nastavení macOS](device-restrictions-macos.md)
    - [Nastavení Windows Phone 8.1](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Nastavení Windows 10](device-restrictions-windows-10.md)
    - [Nastavení Windows 10 Team](device-restrictions-windows-10-teams.md)
    - [Nastavení Windows Holographic for Business](device-restrictions-windows-holographic.md)

7. Až to budete mít, vyberte **OK** > **Vytvořit** a změny uložte.

Profil se vytvoří a zobrazí v seznamu profilů.

## <a name="next-steps"></a>Další postup

Po vytvoření profilu je připraven k přiřazení. Dále [přiřadit profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
