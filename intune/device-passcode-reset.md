---
title: "Resetování hesel u zařízení v Microsoft Intune – Azure | Microsoft Docs"
description: "Odeberte nebo resetujte heslo pomocí akce kódu Odebrat heslo na zařízeních v Intune, která spravujete nebo monitorujete."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f23a79bbe72d12750ef642226aefd1e11dcac24
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Resetování nebo odebrání hesla zařízení v Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pokud chcete vytvořit nové heslo pro zařízení, použijte akci **Odebrat heslo**.

## <a name="supported-platforms"></a>Podporované platformy

- Windows Phone 8.1 až Windows 10 Creators Update bez připojení k Azure AD, Windows 10 Creators Update a novější
- iOS
- Verze Androidu starší než Android 7

Tato funkce se **nepodporuje** u následujících systémů:

- Windows
- macOS
- Android for Work

## <a name="reset-a-passcode"></a>Resetování hesla

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a potom vyberte **Microsoft Intune**.
3. Vyberte **Zařízení** a potom **Všechna zařízení**.
4. V seznamu zařízení, která spravujete, zvolte zařízení, zvolte **Více** a pak zvolte vzdálenou akci **Odebrat heslo**.

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v podokně **Zařízení** vyberete **Akce zařízení**.
