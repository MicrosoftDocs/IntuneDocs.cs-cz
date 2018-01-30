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
ms.openlocfilehash: dce888c1985ff4761100d15d898b654d77318b65
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Resetování zařízení s Windows 10 přes Intune pomocí akce Začít znovu


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce zařízení **Začít znovu** odebere všechny aplikace, které byly nainstalované v počítači s Windows 10 Creators Update, a pak počítač automaticky aktualizuje na nejnovější verzi Windows.
To se dá využít k odebrání aplikací předem nainstalovaných výrobcem (OEM), které se často dodávají s novým počítačem. Můžete nakonfigurovat, jestli se při provedení této akce mají zachovat uživatelská data. V takovém případě se odeberou aplikace a nastavení, ale obsah domovské složky uživatele se zachová.

## <a name="how-to-use-fresh-start"></a>Použití funkce Začít znovu

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení a skupiny** zvolte **Všechna zařízení**.
5. V seznamu zařízení, která spravujete, zvolte zařízení s Windows 10 Desktop a potom zvolte akci se vzdáleným zařízením **Začít znovu**.

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v okně **Zařízení a skupiny** zvolíte **Akce zařízení**.

