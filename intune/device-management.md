---
title: Správa zařízení pomocí Microsoft Intune – Azure | Microsoft Docs
description: Prohlédněte si zařízení, která spravujete v Microsoft Intune (můžete také exportovat jejich seznam do formátu CSV), zobrazte zařízení připojená k Azure Active Directory, prohlédněte si změnový protokol akcí se zařízením, využijte konektor TeamVieweru umožňující správcům IT na dálku řešit problémy v zařízeních s Androidem a prohlédněte si všechny akce, které můžete v zařízeních spouštět.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/02/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9a003b9ec4208bc3449dfb1b3b2ee889a29b742b
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="what-is-microsoft-intune-device-management"></a>Co je správa zařízení v Microsoft Intune?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako správce IT musíte zajistit, aby spravovaná zařízení poskytovala prostředky, které vaši koncoví uživatelé potřebují k práci, a současně ochránit data před možnými riziky.

Úloha **Zařízení** vám poskytuje přehled o spravovaných zařízeních a umožňuje na nich vzdáleně provádět různé úlohy.

## <a name="get-to-your-devices"></a>Přístup k zařízením

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Zařízení**. Toto zobrazení obsahuje podrobné informace o jednotlivých zařízeních a o tom, co s nimi můžete dělat, mimo jiné:

   - **Přehled** zobrazuje grafický snímek zaregistrovaných zařízení včetně informací, kolik zařízení používá jednotlivé platformy (Android, iOS a další).
   - Část **Všechna zařízení** obsahuje seznam zaregistrovaných zařízení, která spravujete.

     Pomocí funkce **Export** vytvoříte seznam všech zařízení ve formátu CSV, a to v přírůstcích po 10 000 (Internet Explorer) nebo 30 000 (Edge, Chrome).

     Když vyberete libovolné zařízení, můžete o něm [zobrazit další podrobnosti](device-inventory.md), včetně podrobných informací o hardwaru, nainstalovaných aplikací, stavu zásad dodržování předpisů a dalších.

   - Část **Zařízení Azure AD** obsahuje seznam zařízení zaregistrovaných v Azure Active Directory (AD) nebo k této službě připojených. Přečtěte si další informace o [správě zařízení Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
   - Část **Akce zařízení** zahrnuje historii vzdálených akcí spuštěných v jednotlivých zařízeních, včetně akce, jejího stavu, iniciátora a času.

     ![Snímek obrazovky s monitorováním akcí zařízení](./media/monitor-device-actions.png)

   - **Protokoly auditu** představují záznam aktivity, které v Intune generují změnu. [Protokoly auditu](monitor-audit-logs.md) obsahují podrobnější informace.
   - **Konektor pro TeamViewer** je služba umožňující uživatelům zařízení s Androidem spravovaných službou Intune získat vzdálenou pomoc od správce IT. Přečtěte si další informace o [TeamVieweru](device-profile-android-teamviewer.md).
   - **Nápověda a podpora** poskytují rychlý přístup k tipům pro řešení problémů, žádosti o podporu nebo kontrole stavu služby Intune.

## <a name="available-device-actions"></a>Dostupné akce zařízení
Dostupné akce se liší podle platformy zařízení a jeho konfigurace.

- [Zobrazit inventář zařízení](device-inventory.md)
- Spouštění akcí ve vzdáleném zařízení:
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

- V části **Všechna zařízení** vyberte zařízení, o kterém chcete zobrazit další podrobnosti.
- Zvolte **Akce zařízení**, abyste si zobrazili stav provedených akcí na spravovaných zařízeních.
