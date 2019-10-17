---
title: Přidání skupin pro uspořádání uživatelů a zařízení
titleSuffix: Microsoft Intune
description: Přidejte skupiny pro uspořádání uživatelů a zařízení podle zeměpisné oblasti, oddělení a hardwarových zvláštností.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/13/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: altsou
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0702eebdd3899c6da527af0078e5e7d47cf95194
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72510232"
---
# <a name="add-groups-to-organize-users-and-devices"></a>Přidání skupin pro uspořádání uživatelů a zařízení
Služba Intune používá ke správě zařízení a uživatelů skupiny Azure Active Directory (AD). Jako správce Intune můžete nastavit skupiny tak, aby odpovídaly potřebám vaší organizace. Vytvořte skupiny, které uživatele nebo zařízení uspořádají podle zeměpisné polohy, oddělení nebo vlastností hardwaru. Skupiny použijte ke spravování úloh se škálováním. Například můžete nastavit zásady pro mnoho uživatelů nebo nasadit aplikace řadě zařízení.

Můžete přidat následující typy skupin:
- **Přiřazené skupiny** – Přidejte uživatele nebo zařízení do statické skupiny ručně.
- **Dynamické skupiny** – (pomocí Azure Active Directory Premium) Umožňují vytvořit skupiny pro uživatele nebo zařízení definované jednoduchými nebo pokročilými pravidly.

## <a name="add-a-new-group"></a>Přidání nové skupiny

Pomocí následujícího postupu vytvořte novou skupinu.
1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** zvolte **Skupiny** a potom v podokně **Všechny skupiny** zvolte **Nová skupina**.
   ![Snímek obrazovky Azure Portalu s vybranou možností Nová skupina](./media/groups-add/groups-add-new.png)
4. Jako **typ skupiny**vyberte jednu z následujících možností:
    - **Zabezpečení**: skupiny zabezpečení jsou dobrým prostředkem, který se má použít při naplňování skupin uživatelů. Vzhledem k tomu, že skupiny zabezpečení definují, kdo má přístup k jakým prostředkům, jsou dobře převeditelné i na skupiny uživatelů Intune. Skupiny zabezpečení, které se synchronizují ze služby Active Directory do Azure Active Directory nebo které vytvoříte přímo v Azure Active Directory prostřednictvím centra pro správu Microsoft 365, nebo Azure Portal jsou k dispozici pro použití při vytváření skupin uživatelů v Intune.
    - **Office 365**

5. Zadejte **název** a **Popis** nové skupiny. Tyto vlastnosti se objeví jenom na portálu správy a uživatelům se nezobrazí.

6. Zvolte **typ členství**:
   - **Přiřazené** – vytvoří skupinu z ručně přiřazených členů. Další informace o [přiřazených skupinách Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
   - **Dynamický uživatel** – vytvoří skupinu uživatelů definovanou **dynamickým dotazem**.
   - **Dynamické zařízení** – vytvoří skupinu zařízení definovanou **dynamickým dotazem**.

   ![Snímek obrazovky s vlastnostmi skupiny v Intune](./media/groups-add/groups-add-properties.png)

   Azure AD vám umožňuje vytvořit dynamické skupiny na základě pravidel, která definují členství. Naučte se [vytvářet dynamické skupiny podle atributů](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

7. Pokud chcete dát členům skupiny uživatelů přístup ke sdíleným aplikacím Office 365, můžete vybrat **Povolit funkce Office**. Přečtěte si další informace o [Skupinách Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).
8. Novou skupinu přidáte tlačítkem **Vytvořit**.

## <a name="groups-and-policies"></a>Skupiny a zásady

Při vytváření skupin Vezměte v úvahu, jak budete [zásady](../protect/device-compliance-get-started.md)používat. Můžete mít například zásady specifické pro operační systém zařízení a zásady specifické pro různé role ve vaší organizaci nebo organizační jednotky, které už jste ve službě Active Directory definovali dříve. Může být užitečné používat oddělené skupiny zařízení pro iOS, Android a Windows a oddělené skupiny uživatelů pro jednotlivé organizační role.

Budete taky nejspíš chtít vytvořit výchozí zásady, které budou platit pro všechny skupiny a zařízení, aby se stanovily základní požadavky na dodržování předpisů vaší organizace. Poté můžete vytvořit konkrétnější zásady pro nejširší kategorie uživatelů a zařízení. Můžete například vytvořit zásady e-mailů pro každý operační systém zvlášť.



## <a name="see-also"></a>Související témata
- [Správa přístupu k prostředkům prostřednictvím skupin Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Skupiny Intune Classic na portálu Azure Portal](groups-get-started.md)
