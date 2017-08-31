---
title: "Podmíněný přístup s Intune"
titleSuffix: Intune on Azure
description: "Naučte se v Microsoft Intune definovat podmínky, které uživatelé a zařízení musí splnit, aby měli přístup k firemním prostředkům."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7f6f7443224b9ec114f0323d1715f343b0adfec4
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/25/2017
---
# <a name="whats-conditional-access"></a>Co je podmíněný přístup?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Toto téma popisuje podmíněný přístup v řešení Enterprise Mobility + Security (EMS) a následně běžné scénáře podmíněného přístupu při používání Intune.

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