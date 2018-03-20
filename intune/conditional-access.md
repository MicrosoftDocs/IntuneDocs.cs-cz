---
title: "Podmíněný přístup s Microsoft Intune"
titlesuffix: 
description: "Naučte se v Microsoft Intune definovat podmínky, které uživatelé, zařízení a aplikace musí splnit, aby měli přístup k firemním prostředkům."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 03/06/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 08589f3d9186699ce5241579cc1879be2d442e3d
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="whats-conditional-access"></a>Co je podmíněný přístup?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Podmíněný přístup označuje způsoby, jimiž můžete řídit zařízení a aplikace, které se smí připojovat k vašemu e-mailu a firemním prostředkům. V tomto tématu se dozvíte o podmíněném přístupu podle zařízení a podle aplikací a najdete běžné scénáře pro používání podmíněného přístupu v Intune.

Podmíněný přístup v rámci Enterprise Mobility + Security (EMS) není samostatný produkt, ale řešení podílející se na všech službách a produktech, které jsou součástí EMS. Nabízí podrobné řízení přístupu za účelem zabezpečení vašich podnikových dat a současně uživatelům poskytuje prostředí, které jim umožňuje co nejlépe pracovat na všech zařízeních a odkudkoli.

Můžete definovat podmínky, které omezují přístup k podnikovým datům podle polohy, zařízení, stavu uživatele a „choulostivosti“ aplikace.

> [!NOTE] 
> Podmíněný přístup také rozšiřuje své možnosti na [služby Office 365](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/).

![Diagram architektury podmíněného přístupu](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Podmíněný přístup s Intune

Intune v rámci podpory řešení podmíněného přístupu EMS přidává dodržování předpisů pro mobilní zařízení a zásady správy aplikací.

![Intune a podmíněný přístup při používání EMS](./media/intune-with-ca-1.png)

Způsoby používání podmíněného přístupu s Intune:

-   **Podmíněný přístup podle zařízení**

    -   Podmíněný přístup pro místní Exchange

    -   Podmíněný přístup na základě řízení přístupu k síti

    -   Podmíněný přístup na základě rizika zařízení

    -   Podmíněný přístup pro počítače s Windows

        -   Ve vlastnictví firmy

        -   Přineste si vlastní zařízení (BYOD)

-   **Podmíněný přístup založený na aplikacích**

## <a name="next-steps"></a>Další kroky

[Běžné způsoby používání podmíněného přístupu s Intune](conditional-access-intune-common-ways-use.md)
