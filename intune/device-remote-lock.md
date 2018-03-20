---
title: "Uzamčení zařízení pomocí Microsoft Intune – Azure | Microsoft Docs"
description: "Akci Vzdáleného uzamčení v Microsoft Intune použijte k uzamčení zařízení chráněného kódem PIN nebo heslem."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 59a55de54a5a18f5fd1080fefa15c0e4801a1456
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2018
---
# <a name="remotely-lock-devices-with-intune"></a>Vzdálené uzamčení zařízení přes Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce **Vzdálené uzamčení** uzamkne zařízení. Vlastník zařízení musí k jeho odemčení zadat heslo. Vzdáleně uzamknout můžete zařízení, která mají nastavený kód PIN nebo heslo. Zařízení bez kódu PIN nebo hesla nejdou vzdáleně zamknout.

## <a name="supported-platforms"></a>Podporované platformy

Vzdálené uzamčení se podporuje u následujících platforem:

- Android
- iOS
- macOS
- Windows 10 Mobile
- Windows Phone 8.1 nebo novější

**Nepodporuje se** pro:
- Stolní počítač s Windows 10

> [!NOTE]
> Pro zařízení s macOS nastavíte šestimístní číselný kód PIN pro obnovení. Když se zařízení zamkne, **přehled zařízení** bude zobrazovat kód PIN, dokud se nepošle jiná akce zařízení.

## <a name="remote-lock-a-device"></a>Vzdáleně uzamknout zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Zařízení** a potom **Všechna zařízení**.
4. V seznamu zařízení vyberte zařízení a pak vyberte akci **Vzdálené uzamčení**.

## <a name="next-steps"></a>Další kroky

Pokud chcete zobrazit stav této akce, otevřete **Akce zařízení** (Microsoft Intune > Zařízení). Další akce, které vám můžou pomoct se správou zařízení, najdete v tématu [Dostupné akce](device-management.md).