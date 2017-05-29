---
title: "Konfigurace nastavení omezení zařízení v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Naučte se pomocí Intune konfigurovat nastavení a funkce na zařízeních, která spravujete."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 600ff92bf1b53800712fc2e77fef7158ab765970
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-configure-device-restriction-settings-in-microsoft-intune"></a>Konfigurace nastavení omezení zařízení v Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Pomocí omezení zařízení můžete ovládat širokou škálu nastavení a funkcí v různých kategoriích včetně nastavení zabezpečení, prohlížeče, hardwaru a sdílení dat. Můžete například vytvořit profil omezení zařízení, který uživatelům zařízení s iOSem zabraňuje v přístupu k fotoaparátu.

Informace v tomto tématu vás seznámí se základy konfigurace profilů omezení zařízení. Pak si můžete přečíst další témata pro jednotlivé platformy, kde najdete podrobnosti o specifikách různých zařízení.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení omezení zařízení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Konfigurovat zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
3. V okně profilů zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **Název** a **Popis** profilu pro omezení zařízení.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete vlastní nastavení použít. V současné době můžete pro nastavení omezení zařízení zvolit jednu z těchto platforem:
    - **Android**
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
    - [Nastavení Androidu for Work](device-restrictions-android-for-work.md)
8. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).

## <a name="example-of-device-restriction-settings"></a>Příklad nastavení omezení zařízení

V tomto příkladu vytvoříte zásadu omezení zařízení, která zablokuje použití integrované aplikace Fotoaparát na zařízeních s Androidem.

![Jak zakázat fotoaparát na zařízeních s Androidem](./media/disable-android-camera.png)


