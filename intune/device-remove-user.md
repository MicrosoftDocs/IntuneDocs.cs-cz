---
title: Odebrání uživatele ze zařízení s iOSem pomocí Microsoft Intune
titlesuffix: ''
description: Zjistěte, jak odebrat uživatele ze sdíleného zařízení s iOSem pomocí Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 01928439f3a4d9280036b2e1a9576175ef425050
ms.sourcegitcommit: 390a4be5aa36007c36fb6a5abcfe8d20bc862a4b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Odebrání uživatele ze sdíleného zařízení s iOSem


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce **Odebrat uživatele** odstraní vybraného uživatele z místní mezipaměti sdíleného zařízení iPad. Zařízení iPad musí být nastavené ke správě aplikace Classroom pro iOS pomocí [vzdělávacího profilu iOS](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Podporované platformy

- Windows – nepodporováno
- Windows Phone – nepodporováno
- iOS – podporováno v iOSu 9.3 a novějších verzích (jen sdílené iPady)
- macOS – nepodporováno
- Android – nepodporováno

## <a name="remove-a-user"></a>Odebrání uživatele

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Zařízení**.
4. V podokně **Zařízení** zvolte **Všechna zařízení**.
5. Ze seznamu zařízení, která spravujete, vyberte zařízení s iOSem.
6. V podokně pro zařízení vyberte **Uživatelé**.
7. V seznamu klikněte pravým tlačítkem na uživatele, kterého chcete odebrat, a pak zvolte **Odebrat uživatele**.

## <a name="next-steps"></a>Další kroky

- Pokud chcete zobrazit stav akce **Odebrat uživatele**, vyberte **Zařízení** > **Akce zařízení**.
