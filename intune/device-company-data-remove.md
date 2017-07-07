---
title: "Odebrání firemních dat ze zařízení s Intune"
titleSuffix: Intune on Azure
description: "Informace o tom, jak ze zařízení, která spravujete přes Intune, odebrat jenom firemní data"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 39acd12333e9685f94d23416fb1a61ce93f45476
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Odebrání firemních dat ze zařízení spravovaných přes Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Možnost **Odebrat firemní data** odebere ze zařízení spravovaných přes Intune jenom firemní data. Osobní data ze zařízení neodebere. Zařízení už nebude spravované přes Intune a nebude mít přístup k podnikovým prostředkům (nepodporuje se u zařízení s Windows, která jsou připojená ke službě Azure Active Directory).

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.
4. V okně **Zařízení a skupiny** zvolte **Všechna zařízení**.
5. V seznamu zařízení, která spravujete, zvolte zařízení a potom zvolte akci se vzdáleným zařízením **Odebrat firemní data**.

Stav akce, kterou jste spustili, zobrazíte tak, že v okně **Zařízení a skupiny** zvolíte **Akce zařízení**.
