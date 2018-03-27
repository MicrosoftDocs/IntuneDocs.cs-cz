---
title: Správa zařízení v Microsoft Intune
titleSuffix: ''
description: Přečtěte si, jak můžete zkontrolovat zařízení spravovaná přes Intune a provádět s nimi různé operace.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/21/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 436eeb306bf4ba343ae4d88a824aeed2077a3426
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="what-is-microsoft-intune-device-management"></a>Co je správa zařízení v Microsoft Intune?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako správce IT musíte zajistit, aby spravovaná zařízení poskytovala prostředky, které vaši koncoví uživatelé potřebují k práci, a současně tato data byla chráněná před možnými riziky.

Úloha **Zařízení** vám poskytuje přehled o spravovaných zařízeních a umožňuje na nich vzdáleně provádět různé úlohy. Tuto úlohu zpřístupníte takto:

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V **Intune** zvolte **Zařízení**.
4. Můžete si zobrazit informace o zařízeních nebo se vzdáleným zařízením provádět tyhle akce:
    - **Přehled** – snímek zaregistrovaných zařízení, která můžete spravovat.
    - **Všechna zařízení** – seznam zaregistrovaných zařízení, která spravujete. **Filtr** nebo **Sloupce** vám pomůžou zobrazené informace upřesnit. Vybráním zařízení [zobrazíte inventář zařízení](device-inventory.md).
    - **Zařízení Azure AD** – seznam zařízení zaregistrovaných nebo spojených s Azure Active Directory (AD). Přečtěte si další informace o [správě zařízení Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
    - **Akce zařízení** – historie vzdálených akcí provedených na zařízeních, která zahrnuje akci, její stav, iniciátora akce a čas.

        ![Snímek obrazovky s monitorováním akcí zařízení](./media/monitor-device-actions.png)

    - **Protokoly auditu** – protokoly auditu obsahují zaznamenané aktivity, které v Microsoft Intune generují změnu. Přečtěte si další informace o [protokolech auditu](monitor-audit-logs.md).
    - **Konektor pro TeamViewer** – služba TeamViewer umožňuje uživatelům zařízení s Androidem spravovaných službou Intune získat vzdálenou pomoc od správce IT. Přečtěte si další informace o [TeamVieweru](device-profile-android-teamviewer.md).
    - **Nápověda a podpora** – zde můžete řešit potíže, požádat o podporu nebo zobrazit stav Intune.  
    
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
