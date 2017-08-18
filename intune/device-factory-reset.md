---
title: "Obnovení továrního nastavení zařízení přes Intune"
titleSuffix: Intune on Azure
description: "Informace o tom, jak u zařízení, která spravujete přes Intune, obnovit jejich tovární nastavení"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8eff9b53-eef2-4c50-8aee-556bc49d69f2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 44f69179f76c8d5eeca1594485ca3a9c1b036188
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2017
---
# <a name="reset-intune-managed-devices-to-factory-settings"></a>Obnovení továrního nastavení u zařízení spravovaných přes Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Možnost **Obnovení továrního nastavení** vrátí zařízení do jeho výchozího nastavení. Zařízení už se nebude spravovat přes Intune a odeberou se jak firemní, tak osobní data. Tuto akci nejde vrátit zpět.

## <a name="supported-platforms"></a>Podporované platformy

- Windows – podporováno ve Windows 8.1 a novějších verzích (zařízení nespravovaná systémem EAS)
- Windows Phone – podporováno
- iOS – podporováno
- macOS – nepodporováno
- Android – podporováno (Android for Work není podporovaný.)

## <a name="how-to-reset-a-device-to-factory-settings"></a>Resetování zařízení do továrního nastavení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení a skupiny** zvolte **Všechna zařízení**.
5. V seznamu zařízení, která spravujete, zvolte zařízení a potom zvolte akci se vzdáleným zařízením **Obnovení továrního nastavení**.

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v okně **Zařízení a skupiny** zvolíte **Akce zařízení**.

