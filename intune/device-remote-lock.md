---
title: "Vzdálené uzamčení spravovaných zařízení přes Intune"
titlesuffix: Azure portal
description: "Informace o tom, jak přes Intune vzdáleně uzamknout zařízení, která spravujete"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 01/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ecd7fa03b35e91b5a77906858fb251348796704d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Vzdálené uzamčení spravovaných zařízení přes Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akce **Vzdálené uzamčení** uzamkne vybrané zařízení. Vlastník zařízení musí k jeho odemčení použít heslo. Vzdáleně můžete uzamknout jen zařízení s nastaveným PIN kódem nebo heslem.

## <a name="supported-platforms"></a>Podporované platformy

Vzdálené uzamčení se podporuje u následujících platforem:

|Platforma|Stav podpory|
|---|---|
|Android|Ano|
|iOS|Ano|
|macOS|Ano|
|Windows 10|Ano|
|Windows 10 Mobile|Ano|
|Windows Phone|Ano, pro Windows Phone 8.1 a novější|

> [!NOTE]  
> Pro zařízení s macOS nastavíte šestimístní číselný kód PIN pro obnovení. Když se zařízení zamkne, v okně **přehledu zařízení** se bude zobrazovat kód PIN, dokud se nepošle jiná akce zařízení.

## <a name="how-to-remote-lock-a-device"></a>Vzdálené uzamčení zařízení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení a skupiny** zvolte **Všechna zařízení**.
5. V seznamu zařízení, která spravujete, zvolte zařízení a potom zvolte akci se vzdáleným zařízením **Vzdálené uzamčení**.

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v okně **Zařízení a skupiny** zvolíte **Akce zařízení**.
