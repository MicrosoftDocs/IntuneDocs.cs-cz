---
title: Podmíněný přístup s Microsoft Intune
titleSuffix: Microsoft Intune
description: Naučte se v Microsoft Intune definovat podmínky, které uživatelé, zařízení a aplikace musí splnit, aby měli přístup k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/06/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: fb9dd31c87d27ec7885d25269988cfd968e81e08
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504560"
---
# <a name="learn-about-conditional-access-and-intune"></a>Další informace o podmíněném přístupu a Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Podmíněný přístup označuje způsoby, kterými můžete řídit zařízení a aplikace, které se můžou připojovat k e-mailu a prostředkům společnosti. V tomto tématu se dozvíte o podmíněném přístupu založeném na zařízeních a aplikacích a najdete běžné scénáře použití podmíněného přístupu s Intune.

Podmíněný přístup v rámci Enterprise Mobility + Security (EMS) není samostatný produkt, ale řešení podílející se na všech službách a produktech, které jsou součástí EMS. Nabízí podrobné řízení přístupu za účelem zabezpečení vašich podnikových dat a současně uživatelům poskytuje prostředí, které jim umožňuje co nejlépe pracovat na všech zařízeních a odkudkoli.

Můžete definovat podmínky, které omezují přístup k podnikovým datům podle polohy, zařízení, stavu uživatele a „choulostivosti“ aplikace.

> [!NOTE] 
> Podmíněný přístup také rozšiřuje své možnosti na [služby Office 365](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access).

![Diagram architektury podmíněného přístupu](./media/conditional-access/ca-diagram-1.png)

## <a name="use-conditional-access-with-intune"></a>Použití podmíněného přístupu s Intune

Podmíněný přístup je Azure Active Directory funkce, která je součástí licence Azure Active Directory Premium. Intune tuto funkci vylepšuje tím, že do řešení přidává dodržování předpisů pro mobilní zařízení a správu mobilních aplikací. 

![Intune a podmíněný přístup při použití EMS](./media/conditional-access/intune-with-ca-1.png)

Způsoby použití podmíněného přístupu s Intune:

- **Podmíněný přístup podle zařízení**

  - Podmíněný přístup pro místní Exchange

  - Podmíněný přístup na základě řízení přístupu k síti

  - Podmíněný přístup na základě rizika zařízení

  - Podmíněný přístup pro počítače s Windows

    - Ve vlastnictví firmy

    - Přineste si vlastní zařízení (BYOD)

- **Podmíněný přístup na základě aplikace**

## <a name="next-steps"></a>Další kroky

[Běžné způsoby použití podmíněného přístupu s Intune](conditional-access-intune-common-ways-use.md)
