---
title: "Vzdálené restartování zařízení přes Intune"
titlesuffix: Azure portal
description: "Informace o tom, jak zařízení vzdáleně restartovat pomocí akce restartování"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9afe804d2f9e48e27ced4bd92959cd065f6ec89a
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="remotely-restart-devices-with-intune"></a>Vzdálené restartování zařízení přes Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce zařízení **Restartovat** způsobí, že se zvolené zařízení restartuje. Vlastník zařízení není na restartování automaticky upozorněn, takže může přijít o to, na čem pracuje.

## <a name="supported-platforms"></a>Podporované platformy

- Windows – podporováno ve Windows 8.1 a novějších verzích
- Windows Phone – podporováno ve Windows Phone 8.1 a novějších verzích
- iOS – podporováno

    > [!Note]  
    > Tento příkaz vyžaduje, aby byla zařízení v režimu pod dohledem, a přístupová práva k **zámku zařízení**. Zařízení se restartuje okamžitě. Zařízení s iOSem zamčená pomocí hesla se po restartování k síti Wi-Fi znovu nepřipojí a je možné, že po restartování nebudou moct komunikovat se serverem.
- macOS – nepodporováno
- Android – nepodporováno

## <a name="how-to-restart-a-device"></a>Restart zařízení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení a skupiny** zvolte **Všechna zařízení**.
5. V seznamu zařízení, která spravujete, zvolte zařízení a potom zvolte akci se vzdáleným zařízením **Restartovat**.

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v okně **Zařízení a skupiny** zvolíte **Akce zařízení**.
