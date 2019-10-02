---
title: Restartování zařízení pomocí Microsoft Intune – Azure | Microsoft Docs
description: Restartujte zařízení s Windows a iOSem pomocí Microsoft Intune na portálu Azure Portal pomocí vzdálené akce Restartovat.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/21/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d1e13801e3235831081be76ddfe5c8f5872e2077
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732606"
---
# <a name="remotely-restart-devices-with-intune"></a>Vzdálené restartování zařízení přes Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Akce zařízení **Restartovat** způsobí, že se zvolené zařízení restartuje. Vlastník zařízení není na restartování automaticky upozorněn, takže může přijít o to, na čem pracuje.

## <a name="supported-platforms"></a>Podporované platformy

- Windows – podporováno ve Windows 8.1 a novějších verzích
- Windows Phone – podporováno ve Windows Phone 8.1 a novějších verzích
- Veřejná zařízení s Androidem – podpora v Androidu 7,0 a novějších verzích
- iOS – podporováno

    > [!Note]  
    > Tento příkaz vyžaduje, aby bylo zařízení v režimu pod dohledem, a přístupová práva k **zámku zařízení**. Zařízení se restartuje okamžitě. Zařízení s iOSem uzamčená heslem se po restartování znovu nepřipojí k síti Wi-Fi. Po restartování zařízení nemusí být schopné komunikovat se serverem.
- macOS – nepodporováno
- Zařízení s Androidem a pracovním profilem Androidu – nepodporováno

## <a name="restart-a-device"></a>Restart zařízení

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Vyberte **Zařízení** > **Všechna zařízení**.
4. V seznamu zařízení, která spravujete, zvolte zařízení, zvolte **Více** a pak zvolte akci se vzdáleným zařízením **Restartovat**.

## <a name="next-steps"></a>Další kroky

- Pokud chcete zobrazit stav akce **Restartovat**, vyberte **Zařízení** > **Akce zařízení**.
