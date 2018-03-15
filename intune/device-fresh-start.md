---
title: "Resetování zařízení s Windows 10 přes Intune"
titlesuffix: Azure portal
description: "Informace o tom, jak resetovat počítače s Windows 10, které používají Intune, pomocí akce Začít znovu"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c45d3e47c90ca7739b3aa6eee1bf31d787a82264
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/23/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Resetování zařízení s Windows 10 přes Intune pomocí akce Začít znovu


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce zařízení **Začít znovu** odebere všechny aplikace, které byly nainstalované v počítači s Windows 10 Creators Update, a pak počítač automaticky aktualizuje na nejnovější verzi Windows.
Tato akce se dá využít k odebrání aplikací předem nainstalovaných výrobcem (OEM), které se často dodávají s novým počítačem. Můžete nakonfigurovat, jestli se při provedení této akce mají zachovat uživatelská data. V takovém případě se odeberou aplikace a nastavení, ale obsah domovské složky uživatele se zachová.

## <a name="how-to-use-fresh-start"></a>Použití funkce Začít znovu

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Zařízení**.
4. V podokně **Zařízení** zvolte **Všechna zařízení**.
5. V seznamu zařízení, která spravujete, zvolte zařízení s Windows 10 Desktop a potom zvolte akci se vzdáleným zařízením **Začít znovu**.

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v podokně **Zařízení** zvolíte **Akce zařízení**.

