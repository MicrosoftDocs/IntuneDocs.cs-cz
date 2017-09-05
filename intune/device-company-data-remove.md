---
title: "Odebrání firemních dat ze zařízení s Intune"
titleSuffix: Intune on Azure
description: "Informace o tom, jak ze zařízení, která spravujete přes Intune, odebrat jenom firemní data"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8074d6e7cc0a061a6708f8c8bfae1a4dfcb6daa3
ms.sourcegitcommit: 10e3ab2aeb79a1fb2243bef2748ccc003fdd4cc7
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Odebrání firemních dat ze zařízení spravovaných přes Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce zařízení **Odebrat firemní data** odebere ze zařízení spravovaných přes Intune jenom firemní data. Osobní data ze zařízení neodebere. Po odebrání už zařízení není spravované v Intune a nemá přístup k podnikovým prostředkům.

## <a name="supported-platforms"></a>Podporované platformy

- Windows – podporováno (není podporováno u zařízení s Windows připojených k Azure Active Directory)
- Windows Phone – podporováno
- iOS – podporováno
- macOS – podporováno
- Android – podporováno

## <a name="how-to-remove-company-data"></a>Odebrání firemních dat

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení a skupiny** zvolte **Všechna zařízení**.
5. V seznamu zařízení, která spravujete, zvolte zařízení a potom zvolte akci se vzdáleným zařízením **Odebrat firemní data**.

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v okně **Zařízení a skupiny** zvolíte **Akce zařízení**.
