---
title: Odebrání uživatele ze zařízení s iOS/iPadOS pomocí Microsoft Intune
titleSuffix: ''
description: Naučte se, jak odebrat uživatele ze sdíleného zařízení s iOS nebo iPadOS v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8b6b2b3492b9edece6b69e4b302741c0443c0a3e
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415564"
---
# <a name="remove-a-user-from-a-shared-iosipados-device"></a>Odebrání uživatele ze sdíleného zařízení s iOS/iPadOS


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Akce **Odebrat uživatele** odstraní vybraného uživatele z místní mezipaměti sdíleného zařízení iPad. Zařízení iPad musí být nastavené pro správu aplikace pro iOS/iPadOS pomocí [vzdělávacího profilu iOS/iPadOS](../fundamentals/education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Podporované platformy

- Windows – nepodporováno
- Windows Phone – nepodporováno
- iOS/iPadOS – podporováno v systémech iOS/iPadOS 9,3 a novějších (pouze sdílená zařízení iPad)
- macOS – nepodporováno
- Android – nepodporováno

## <a name="remove-a-user"></a>Odebrání uživatele

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vyberte **Zařízení** > **Všechna zařízení**.
3. V seznamu zařízení, která spravujete, vyberte zařízení s iOS/iPadOS.
4. V podokně pro zařízení vyberte **Uživatelé**.
5. V seznamu klikněte pravým tlačítkem na uživatele, kterého chcete odebrat, a pak zvolte **Odebrat uživatele**.

## <a name="next-steps"></a>Další kroky

- Pokud chcete zobrazit stav akce **Odebrat uživatele**, vyberte **Zařízení** > **Akce zařízení**.
