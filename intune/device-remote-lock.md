---
title: Uzamčení zařízení pomocí Microsoft Intune – Azure | Microsoft Docs
description: Můžete použít akci Vzdáleného uzamčení v Microsoft Intun k uzamčení zařízení chráněného kódem PIN nebo heslem.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/07/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e4d0443b100a4a973161ddcbf5e445c4b6136e6f
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57394228"
---
# <a name="remotely-lock-devices-with-intune"></a>Vzdálené uzamčení zařízení přes Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Akce zařízení **Vzdálené uzamčení** uzamkne zařízení. Vlastník zařízení musí k jeho odemčení zadat heslo. Vzdáleně uzamknout můžete zařízení, která mají nastavený kód PIN nebo heslo. Zařízení bez kódu PIN nebo hesla nejdou vzdáleně zamknout.

## <a name="supported-platforms"></a>Podporované platformy

**Vzdálené uzamčení** je podporované u těchto platforem:

- Android
- Zařízení s Androidem Enterprise v beznabídkovém režimu
- Zařízení Android Enterprise s pracovním profilem
- iOS
- macOS
- Windows 10 Mobile
- Windows Phone 8.1 nebo novější

**Vzdálené uzamčení** není podporované pro:
- Stolní počítač s Windows 10

> [!NOTE]
> Pro zařízení s macOS nastavíte šestimístní číselný kód PIN pro obnovení. Když se zařízení zamkne, **přehled zařízení** bude zobrazovat kód PIN, dokud se nepošle jiná akce zařízení.

## <a name="remote-lock-a-device"></a>Vzdáleně uzamknout zařízení

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a potom vyberte **Microsoft Intune**.
3. Vyberte **Zařízení** > **Všechna zařízení**.
4. V seznamu zařízení vyberte zařízení a pak vyberte akci **Vzdálené uzamčení**.

## <a name="next-steps"></a>Další postup

- Pokud chcete zobrazit stav akce, vyberte **Microsoft Intune** > **Zařízení** > **Akce zařízení**. 
- Další akce, které vám můžou pomoct se správou zařízení, najdete v tématu [Dostupné akce](device-management.md).
