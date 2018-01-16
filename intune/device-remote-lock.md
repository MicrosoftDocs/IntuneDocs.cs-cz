---
title: "Vzdálené uzamčení spravovaných zařízení přes Intune"
titlesuffix: Azure portal
description: "Informace o tom, jak přes Intune vzdáleně uzamknout zařízení, která spravujete"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45d27b709ba8d4ff1d8fb4417a217ad008c19c36
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/12/2018
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Vzdálené uzamčení spravovaných zařízení přes Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce **Vzdálené uzamčení** uzamkne vybrané zařízení. Vlastník zařízení musí k jeho odemčení použít heslo. Vzdáleně můžete uzamknout jen zařízení s nastaveným PIN kódem nebo heslem.

## <a name="supported-platforms"></a>Podporované platformy

- Windows – nepodporováno
- Windows Phone – podporováno ve Windows Phone 8.1 a novějších verzích
- iOS – podporováno
- macOS – podporováno

    > [!Note]  
    > Nastavte šestimístný číselný kód PIN pro obnovení. Když se zařízení zamkne, v okně **přehledu zařízení** se bude zobrazovat kód PIN, dokud se nepošle jiná akce zařízení.
- Android – podporováno

## <a name="how-to-remote-lock-a-device"></a>Vzdálené uzamčení zařízení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení a skupiny** zvolte **Všechna zařízení**.
5. V seznamu zařízení, která spravujete, zvolte zařízení a potom zvolte akci se vzdáleným zařízením **Vzdálené uzamčení**.

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v okně **Zařízení a skupiny** zvolíte **Akce zařízení**.
