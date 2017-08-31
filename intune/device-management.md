---
title: "Správa zařízení v Intune"
titleSuffix: Intune on Azure
description: "Zjistěte, jak můžete zobrazit zařízení spravovaná přes Intune a provádět s nimi různé operace."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5d78b4a87eaa366b7bb00356c4b98d609620dcf3
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/25/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Co je správa zařízení v Microsoft Intune?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Úloha **Zařízení** vám poskytuje přehled o spravovaných zařízeních a umožňuje na nich vzdáleně provádět různé úlohy. Tuto úlohu zpřístupníte takto:

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. Zde můžete zobrazit informace o zařízeních nebo se vzdáleným zařízením provádět uvedené akce.

## <a name="available-device-actions"></a>Dostupné akce zařízení
Dostupné akce se liší podle platformy zařízení a jeho konfigurace.

- [Zobrazit inventář zařízení](device-inventory.md)
- Provádění akcí se vzdáleným zařízením:
    - [Odebrat firemní data](devices-wipe.md#remove-company-data)
    - [Obnovení továrního nastavení](devices-wipe.md#factory-reset)
    - [Vzdálené uzamčení](device-remote-lock.md) 
    - [Resetovat heslo](device-passcode-reset.md)
    - [Vynechat zámek aktivace](device-activation-lock-bypass.md) (jenom iOS)
    - [Začít znovu](device-fresh-start.md) (jenom Windows)
    - [Režim ztráty](device-lost-mode.md) (jenom iOS)
    - [Najít zařízení](device-locate.md) (jenom iOS)
    - [Restartovat](device-restart.md) (jenom Windows)
    - [Resetovat PIN kód ve Windows 10](device-windows-pin-reset.md)
    - [Vzdálené řízení pro Android](device-profile-android-teamviewer.md)
    - [Synchronizace zařízení](device-sync.md)


## <a name="next-steps"></a>Další kroky

- Zvolte **Akce zařízení**, abyste si zobrazili stav provedených akcí na spravovaných zařízeních.
![Monitorování akcí zařízení](./media/monitor-device-actions.png)
