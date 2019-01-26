---
title: Restartování zařízení pomocí Microsoft Intune – Azure | Microsoft Docs
description: Restartujte zařízení s Windows a iOSem pomocí Microsoft Intune na portálu Azure Portal pomocí vzdálené akce Restartovat.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: f814abc4d47517c17e24a188c7efb5da771bc328
ms.sourcegitcommit: 06f62ae989da6c60bac4a52ccd41b429f7367d8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55068267"
---
# <a name="remotely-restart-devices-with-intune"></a>Vzdálené restartování zařízení přes Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Akce zařízení **Restartovat** způsobí, že se zvolené zařízení restartuje. Vlastník zařízení není na restartování automaticky upozorněn, takže může přijít o to, na čem pracuje.

## <a name="supported-platforms"></a>Podporované platformy

- Windows – podporováno ve Windows 8.1 a novějších verzích
- Windows Phone – podporováno ve Windows Phone 8.1 a novějších verzích
- Zařízení v celoobrazovkovém režimu Android – podporováno u Androidu 7.0 a novějších verzích
- iOS – podporováno

    > [!Note]  
    > Tento příkaz vyžaduje, aby bylo zařízení v režimu pod dohledem, a přístupová práva k **zámku zařízení**. Zařízení se restartuje okamžitě. Zařízení s iOSem uzamčená heslem se po restartování znovu nepřipojí k síti Wi-Fi. Po restartování zařízení nemusí být schopné komunikovat se serverem.
- macOS – nepodporováno
- Zařízení s Androidem a pracovním profilem Androidu – nepodporováno

## <a name="restart-a-device"></a>Restart zařízení

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Zařízení** > **Všechna zařízení**.
4. V seznamu zařízení, která spravujete, zvolte zařízení, zvolte **Více** a pak zvolte akci se vzdáleným zařízením **Restartovat**.

## <a name="next-steps"></a>Další postup

- Pokud chcete zobrazit stav akce **Restartovat**, vyberte **Zařízení** > **Akce zařízení**.
