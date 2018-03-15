---
title: "Odebrání uživatele ze zařízení s iOSem pomocí Microsoft Intune"
titlesuffix: 
description: "Zjistěte, jak odebrat uživatele ze sdíleného zařízení s iOSem pomocí Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ce1b6b439c287b67a7c9e776edf136e78e5ecf5b
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Odebrání uživatele ze sdíleného zařízení s iOSem


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce **Odebrat uživatele** odstraní uživatele, kterého vyberete z místní mezipaměti na sdíleném iPadu nakonfigurovaném ke správě aplikace Classroom pro iOS pomocí [vzdělávacího profilu iOS](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Podporované platformy

- Windows – nepodporováno
- Windows Phone – nepodporováno
- iOS – podporováno v iOSu 9.3 a novějších verzích (jen sdílené iPady)
- macOS – nepodporováno
- Android – nepodporováno

## <a name="how-to-remove-a-user"></a>Odebrání uživatele

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení** zvolte **Všechna zařízení**.
5. Ze seznamu zařízení, která spravujete, vyberte zařízení s iOSem.
6. V okně pro toto zařízení zvolte **Uživatelé**.
7. V seznamu klikněte pravým tlačítkem na uživatele a potom zvolte **Odebrat uživatele**.

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v okně **Zařízení** zvolíte **Akce zařízení**.
