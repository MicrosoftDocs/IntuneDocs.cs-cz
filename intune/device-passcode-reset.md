---
title: "Resetování nebo odebrání hesel zařízení s Intune"
titlesuffix: Azure portal
description: "Informace o tom, jak resetovat nebo odebrat heslo na zařízeních spravovaných přes Intune"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4e1496d24fd9d3bb636a4eab00c254b753210f63
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/23/2018
---
# <a name="reset-and-remove-the-passcode-on-intune-managed-devices"></a>Resetování nebo odebrání hesla na zařízeních spravovaných přes Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Termíny *odebrání* a *resetování*  se v tomto článku používají se zaměnitelným významem.

Akce **Odebrat heslo** vygeneruje pro zařízení nové heslo, které se zobrazí v okně <*název zařízení*> **Přehled**.

## <a name="supported-platforms"></a>Podporované platformy

- Windows – nepodporováno
- Windows Phone – podporováno ve verzích Windows Phone 8.1 až Windows 10 Creators Update bez připojení k Azure AD, ve Windows 10 Creators Update a novějších verzích
- iOS – podporováno
- macOS – nepodporováno
- Android – podporováno ve verzích starších než Android 7. Android for Work není podporovaný.

## <a name="how-to-reset-a-passcode"></a>Resetování hesla

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení** zvolte **Všechna zařízení**.
5. V seznamu zařízení, která spravujete, zvolte zařízení, zvolte **Více** a pak zvolte vzdálenou akci **Odebrat heslo**.

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v okně **Zařízení** zvolíte **Akce zařízení**.
