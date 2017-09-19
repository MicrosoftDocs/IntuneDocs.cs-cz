---
title: "Resetování hesla zařízení přes Intune"
titlesuffix: Azure portal
description: "Informace o tom, jak resetovat heslo na zařízeních, která spravujete přes Intune"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3defec3624944918d14b9c4527487c368c487dd6
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/15/2017
---
# <a name="reset-the-passcode-on-intune-managed-devices"></a>Resetování hesla na zařízeních spravovaných přes Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce **Resetovat heslo** vygeneruje pro zařízení nové heslo, které se zobrazí v okně <*název zařízení*> **Přehled**.

## <a name="supported-platforms"></a>Podporované platformy

- Windows – nepodporováno
- Windows Phone – podporováno ve verzích Windows Phone 8.1 až Windows 10 Creators Update bez připojení k Azure AD, ve Windows 10 Creators Update a novějších verzích
- iOS – podporováno
- macOS – nepodporováno
- Android – podporováno ve verzích starších než Android 7. Android for Work není podporovaný.

## <a name="how-to-reset-a-passcode"></a>Resetování hesla

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení a skupiny** zvolte **Všechna zařízení**.
5. V seznamu zařízení, která spravujete, zvolte zařízení a potom zvolte akci se vzdáleným zařízením **Resetovat heslo**.

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v okně **Zařízení a skupiny** zvolíte **Akce zařízení**.
