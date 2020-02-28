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
ms.openlocfilehash: 03bfdfb87c969381b582481367ab0457f6b50049
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77781880"
---
# <a name="what-is-microsoft-intune-device-management"></a>Co je správa zařízení v Microsoft Intune?

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Jako správce IT musíte zajistit, aby spravovaná zařízení poskytovala prostředky, které vaši koncoví uživatelé potřebují k práci, a současně ochránit data před možnými riziky.

Úloha **Zařízení** vám poskytuje přehled o spravovaných zařízeních a umožňuje na nich vzdáleně provádět různé úlohy.

## <a name="get-to-your-devices"></a>Přístup k zařízením

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Vyberte **Zařízení**. Toto zobrazení obsahuje podrobné informace o jednotlivých zařízeních a o tom, co s nimi můžete dělat, mimo jiné:

   - **Přehled** ukazuje vizuální snímek zaregistrovaných zařízení a také ukazuje, kolik zařízení používá různé platformy, včetně Androidu, iOS/iPadOS a dalších.
   - Část **Všechna zařízení** obsahuje seznam zaregistrovaných zařízení, která spravujete.

     Pomocí funkce **exportu** můžete vytvořit seznam. zip všech zařízení v přírůstcích po 10 000 (Internet Explorer) nebo 30 000 (Microsoft Edge, Chrome).

     Vyberte libovolné zařízení, abyste [si zobrazili další podrobnosti o zařízení](device-inventory.md), včetně podrobností o hardwaru, nainstalovaných aplikací, stavu zásad dodržování předpisů a dalších.

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
  - [Zakázat zámek aktivace](device-activation-lock-bypass.md) (jenom iOS)
  - [Začít znovu](device-fresh-start.md) (jenom Windows)
  - [Režim ztráty](device-lost-mode.md) (jenom iOS)
  - [Najít zařízení](device-locate.md) (jenom iOS)
  - [Restartovat](device-restart.md) (jenom Windows)
  - [Resetovat PIN kód ve Windows 10](device-windows-pin-reset.md)
  - [Vzdálené řízení pro Android](teamviewer-support.md)
  - [Synchronizace zařízení](device-sync.md)
  - [Přejmenování zařízení](device-rename.md)
  - [Poslat vlastní oznámení](custom-notifications.md#send-a-custom-notification-to-a-single-device) (Android, iOS/iPadOS)
  - [Střídání klíčů BitLockeru](../protect/encrypt-devices.md#rotate-bitlocker-recovery-keys) (jenom Windows)

## <a name="next-steps"></a>Další kroky

- V části **Všechna zařízení** vyberte zařízení, o kterém chcete zobrazit další podrobnosti.
- Zvolte **Akce zařízení**, abyste si zobrazili stav provedených akcí na spravovaných zařízeních.
