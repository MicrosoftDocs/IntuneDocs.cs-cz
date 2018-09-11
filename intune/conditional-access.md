---
title: Podmíněný přístup s Microsoft Intune
titlesuffix: ''
description: Naučte se v Microsoft Intune definovat podmínky, které uživatelé, zařízení a aplikace musí splnit, aby měli přístup k firemním prostředkům.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 03/06/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: b1da098b0d45ed15abc2a260b84e3ab2f60cc007
ms.sourcegitcommit: 18f51ae8291b57562921e40fc364a5a60a59b139
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2018
ms.locfileid: "44254101"
---
# <a name="whats-conditional-access"></a>Co je podmíněný přístup?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Podmíněný přístup označuje způsoby, jimiž můžete řídit zařízení a aplikace, které se smí připojovat k vašemu e-mailu a firemním prostředkům. V tomto tématu se dozvíte o podmíněném přístupu podle zařízení a podle aplikací a najdete běžné scénáře pro používání podmíněného přístupu v Intune.

Podmíněný přístup v rámci Enterprise Mobility + Security (EMS) není samostatný produkt, ale řešení podílející se na všech službách a produktech, které jsou součástí EMS. Nabízí podrobné řízení přístupu za účelem zabezpečení vašich podnikových dat a současně uživatelům poskytuje prostředí, které jim umožňuje co nejlépe pracovat na všech zařízeních a odkudkoli.

Můžete definovat podmínky, které omezují přístup k podnikovým datům podle polohy, zařízení, stavu uživatele a „choulostivosti“ aplikace.

> [!NOTE] 
> Podmíněný přístup také rozšiřuje své možnosti na [služby Office 365](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/).

![Diagram architektury podmíněného přístupu](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Podmíněný přístup s Intune

Podmíněný přístup je funkce Azure Active Directory, která je zahrnutá v licenci pro Azure Active Directory Premium. Intune tuto funkci vylepšuje tím, že do řešení přidává dodržování předpisů pro mobilní zařízení a správu mobilních aplikací. 

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
