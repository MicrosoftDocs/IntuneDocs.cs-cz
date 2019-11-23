---
title: Správa zařízení pomocí Microsoft Intune – Azure | Microsoft Docs
description: Prohlédněte si zařízení, která spravujete v Microsoft Intune (můžete také exportovat jejich seznam do formátu CSV), zobrazte zařízení připojená k Azure Active Directory, prohlédněte si změnový protokol akcí se zařízením, využijte konektor TeamVieweru umožňující správcům IT na dálku řešit problémy v zařízeních s Androidem a prohlédněte si všechny akce, které můžete v zařízeních spouštět.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/14/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: a9937fc25ffa3dc32c1addbf0acc2516000b055b
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390887"
---
# <a name="what-is-microsoft-intune-device-management"></a>Co je správa zařízení v Microsoft Intune?

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Jako správce IT musíte zajistit, aby spravovaná zařízení poskytovala prostředky, které vaši koncoví uživatelé potřebují k práci, a současně ochránit data před možnými riziky.

Úloha **Zařízení** vám poskytuje přehled o spravovaných zařízeních a umožňuje na nich vzdáleně provádět různé úlohy.

## <a name="get-to-your-devices"></a>Přístup k zařízením

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Vyberte **Zařízení**. Toto zobrazení obsahuje podrobné informace o jednotlivých zařízeních a o tom, co s nimi můžete dělat, mimo jiné:

   - **Přehled** zobrazuje grafický snímek zaregistrovaných zařízení včetně informací, kolik zařízení používá jednotlivé platformy (Android, iOS a další).
   - Část **Všechna zařízení** obsahuje seznam zaregistrovaných zařízení, která spravujete.

     Pomocí funkce **Export** vytvoříte seznam všech zařízení ve formátu .csv, a to v přírůstcích po 10 000 (Internet Explorer) nebo 30 000 (Microsoft Edge, Chrome).

     Select any device to [view additional details about that device](device-inventory.md), including hardware details, installed apps, its compliance policy status, and more.

   - Část **Zařízení Azure AD** obsahuje seznam zařízení zaregistrovaných v Azure Active Directory (AD) nebo k této službě připojených. Přečtěte si další informace o [správě zařízení Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
   - Část **Akce zařízení** zahrnuje historii vzdálených akcí spuštěných v jednotlivých zařízeních, včetně akce, jejího stavu, iniciátora a času.

     ![Snímek obrazovky s monitorováním akcí zařízení](./media/device-management/monitor-device-actions.png)

   - **Protokoly auditu** představují záznam aktivity, které v Intune generují změnu. [Protokoly auditu](../fundamentals/monitor-audit-logs.md) obsahují podrobnější informace.
   - **Konektor pro TeamViewer** je služba umožňující uživatelům zařízení s Androidem spravovaných službou Intune získat vzdálenou pomoc od správce IT. Přečtěte si další informace o [TeamVieweru](teamviewer-support.md).
   - **Nápověda a podpora** poskytují rychlý přístup k tipům pro řešení problémů, žádosti o podporu nebo kontrole stavu služby Intune.

## <a name="available-device-actions"></a>Dostupné akce zařízení
Dostupné akce se liší podle platformy zařízení a jeho konfigurace.

- [Zobrazit inventář zařízení](device-inventory.md)
- Spouštění akcí ve vzdáleném zařízení:
  - [Vyřadit](devices-wipe.md#retire)
  - [Vymazání](devices-wipe.md#wipe)
  - [Vzdálené uzamčení](device-remote-lock.md)
  - [Resetovat heslo](device-passcode-reset.md)
  - [Vynechat zámek aktivace](device-activation-lock-bypass.md) (jenom iOS)
  - [Začít znovu](device-fresh-start.md) (jenom Windows)
  - [Režim ztráty](device-lost-mode.md) (jenom iOS)
  - [Najít zařízení](device-locate.md) (jenom iOS)
  - [Restartovat](device-restart.md) (jenom Windows)
  - [Resetování PIN kódu ve Windows 10](device-windows-pin-reset.md)
  - [Vzdálené řízení pro Android](teamviewer-support.md)
  - [Synchronizace zařízení](device-sync.md)
  - [Send custom notification](custom-notifications.md#send-a-custom-notification-to-a-single-device) (Android, iOS)
  - [BitLocker key rotation](../protect/encrypt-devices.md#rotate-bitlocker-recovery-keys) (Windows only)

## <a name="next-steps"></a>Další kroky

- V části **Všechna zařízení** vyberte zařízení, o kterém chcete zobrazit další podrobnosti.
- Zvolte **Akce zařízení**, abyste si zobrazili stav provedených akcí na spravovaných zařízeních.
