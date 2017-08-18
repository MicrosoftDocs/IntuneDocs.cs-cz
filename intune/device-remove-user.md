---
title: "Odebrání uživatele ze zařízení s iOSem pomocí Intune"
titleSuffix: Intune on Azure
description: "Zjistěte, jak odebrat uživatele ze sdíleného zařízení s iOSem pomocí Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 00f5898d0f2cc167a66026dd108d6bbd54c39cec
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2017
---
# <a name="remove-a-user-from-a-shared-ios-device-with-intune"></a>Odebrání uživatele ze sdíleného zařízení s iOSem pomocí Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce **Odebrat uživatele** odstraní uživatele, kterého vyberete z místní mezipaměti na sdíleném iPadu nakonfigurovaném ke správě aplikace Classroom pro iOS pomocí [vzdělávacího profilu iOS](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Podporované platformy

- Windows – nepodporováno
- Windows Phone – nepodporováno
- iOS – podporováno v iOSu 9.3 a novějších verzích (jen sdílené iPady)
- macOS – nepodporováno
- Android – nepodporováno

## <a name="how-to-remove-a-user"></a>Odebrání uživatele

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení** zvolte **Všechna zařízení**.
5. Ze seznamu zařízení, která spravujete, vyberte zařízení s iOSem.
6. V okně pro toto zařízení zvolte **Uživatelé**.
7. V seznamu klikněte pravým tlačítkem na uživatele a potom zvolte **Odebrat uživatele**.

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v okně **Zařízení a skupiny** zvolíte **Akce zařízení**.
