---
title: "Odebrání uživatele ze zařízení s iOSem pomocí Intune"
titlesuffix: Azure portal
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
ms.openlocfilehash: 2dd6f4fab1d21d3fd40c3ec6abd4be44cff5212e
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
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
