---
title: Odebrání uživatele ze zařízení s iOSem pomocí Microsoft Intune
titleSuffix: ''
description: Zjistěte, jak odebrat uživatele ze sdíleného zařízení s iOSem pomocí Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f418149d8640f7fd663f0bbf4b3151ffb428a75e
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732594"
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Odebrání uživatele ze sdíleného zařízení s iOSem


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Akce **Odebrat uživatele** odstraní vybraného uživatele z místní mezipaměti sdíleného zařízení iPad. Zařízení iPad musí být nastavené ke správě aplikace Classroom pro iOS pomocí [vzdělávacího profilu iOS](../fundamentals/education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Podporované platformy

- Windows – nepodporováno
- Windows Phone – nepodporováno
- iOS – podporováno v iOSu 9.3 a novějších verzích (jen sdílené iPady)
- macOS – nepodporováno
- Android – nepodporováno

## <a name="remove-a-user"></a>Odebrání uživatele

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** zvolte **Zařízení**.
4. V podokně **Zařízení** zvolte **Všechna zařízení**.
5. Ze seznamu zařízení, která spravujete, vyberte zařízení s iOSem.
6. V podokně pro zařízení vyberte **Uživatelé**.
7. V seznamu klikněte pravým tlačítkem na uživatele, kterého chcete odebrat, a pak zvolte **Odebrat uživatele**.

## <a name="next-steps"></a>Další kroky

- Pokud chcete zobrazit stav akce **Odebrat uživatele**, vyberte **Zařízení** > **Akce zařízení**.
