---
title: Resetování hesel u zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Odeberte nebo resetujte heslo pomocí akce Odebrat heslo na zařízeních v Intune, která spravujete nebo monitorujete.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4cca5922f036711093469e71489e267af53f05a9
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/20/2018
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Resetování nebo odebrání hesla zařízení v Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pokud chcete vytvořit nové heslo pro zařízení, použijte akci **Odebrat heslo**.

## <a name="supported-platforms"></a>Podporované platformy

- Windows Phone 8.1 (nepřipojené k Azure Active Directory), včetně verzí až do Windows 10 Creators Update
- Windows 10 Creators Update a novější
- iOS
- Verze Androidu starší než Android 7

Tato funkce není podporovaná pro tyto systémy:

- Windows
- macOS
- Android for Work

## <a name="reset-a-passcode"></a>Resetování hesla

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a potom vyberte **Microsoft Intune**.
3. Vyberte **Zařízení** a potom **Všechna zařízení**.
4. Ze seznamu zařízení, která spravujete, vyberte zařízení a vyberte **...Další**. Pak zvolte vzdálenou akci zařízení **Odebrat heslo**.

## <a name="next-steps"></a>Další kroky

Stav akce, kterou jste spustili, zobrazíte tak, že v podokně **Zařízení** vyberete **Akce zařízení**.
