---
title: Přidání skupin pro uspořádání uživatelů a zařízení
titlesuffix: Microsoft Intune
description: Přidejte skupiny pro uspořádání uživatelů a zařízení podle zeměpisné oblasti, oddělení a hardwarových zvláštností.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/13/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fb9ccc2f2a14f554f0f48674efe06b2935242238
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57461307"
---
# <a name="add-groups-to-organize-users-and-devices"></a>Přidání skupin pro uspořádání uživatelů a zařízení
Služba Intune používá ke správě zařízení a uživatelů skupiny Azure Active Directory (AD). Jako správce Intune můžete nastavit skupiny tak, aby odpovídaly potřebám vaší organizace. Vytvořte skupiny, které uživatele nebo zařízení uspořádají podle zeměpisné polohy, oddělení nebo vlastností hardwaru. Skupiny použijte ke spravování úloh se škálováním. Například můžete nastavit zásady pro mnoho uživatelů nebo nasadit aplikace řadě zařízení.

Můžete přidat následující typy skupin:
- **Přiřazené skupiny** – Přidejte uživatele nebo zařízení do statické skupiny ručně.
- **Dynamické skupiny** – (pomocí Azure Active Directory Premium) Umožňují vytvořit skupiny pro uživatele nebo zařízení definované jednoduchými nebo pokročilými pravidly.

## <a name="add-a-new-group"></a>Přidání nové skupiny

Pomocí následujícího postupu vytvořte novou skupinu.
1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Skupiny** a potom v podokně **Všechny skupiny** zvolte **Nová skupina**.
   ![Snímek obrazovky Azure Portalu s vybranou možností Nová skupina](./media/groups-add-new.png)
4. Pro **typ skupiny**, zvolte jednu z následujících možností:
    - **Zabezpečení**: Skupiny zabezpečení jsou dobrý prostředek pro naplňování skupin uživatelů. Vzhledem k tomu, že skupiny zabezpečení definují, kdo má přístup k jakým prostředkům, jsou dobře převeditelné i na skupiny uživatelů Intune. Skupiny zabezpečení, které jsou synchronizované z Active Directory do Azure Active Directory nebo které lze vytvořit přímo v Azure Active Directory pomocí centra pro správu služeb Microsoft 365 nebo na webu Azure portal jsou k dispozici pro použití při vytváření skupin uživatelů v Intune.
    - **Office 365**

5. Zadejte **název** a **popis** nové skupiny. Tyto vlastnosti se objeví jenom na portálu správy a uživatelům se nezobrazí.

6. Zvolte **typ členství**:
   - **Přiřazené** – vytvoří skupinu z ručně přiřazených členů. Další informace o [přiřazených skupinách Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
   - **Dynamický uživatel** – vytvoří skupinu uživatelů definovanou **dynamickým dotazem**.
   - **Dynamické zařízení** – vytvoří skupinu zařízení definovanou **dynamickým dotazem**.

   ![Snímek obrazovky s vlastnostmi skupiny v Intune](./media/groups-add-properties.png)

   Azure AD vám umožňuje vytvořit dynamické skupiny na základě pravidel, která definují členství. Naučte se [vytvářet dynamické skupiny podle atributů](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

7. Pokud chcete dát členům skupiny uživatelů přístup ke sdíleným aplikacím Office 365, můžete vybrat **Povolit funkce Office**. Přečtěte si další informace o [Skupinách Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).
8. Novou skupinu přidáte tlačítkem **Vytvořit**.

## <a name="groups-and-policies"></a>Skupiny a zásady

Při vytváření skupin vezměte v úvahu jak použijete [zásady](device-compliance-get-started.md). Můžete mít například zásady specifické pro operační systém zařízení a zásady specifické pro různé role ve vaší organizaci nebo organizační jednotky, které už jste ve službě Active Directory definovali dříve. Může být užitečné používat oddělené skupiny zařízení pro iOS, Android a Windows a oddělené skupiny uživatelů pro jednotlivé organizační role.

Budete taky nejspíš chtít vytvořit výchozí zásady, které budou platit pro všechny skupiny a zařízení, aby se stanovily základní požadavky na dodržování předpisů vaší organizace. Poté můžete vytvořit konkrétnější zásady pro nejširší kategorie uživatelů a zařízení. Můžete například vytvořit zásady e-mailů pro každý operační systém zvlášť.



## <a name="see-also"></a>Viz také:
- [Správa přístupu k prostředkům prostřednictvím skupin Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Skupiny Intune Classic na portálu Azure Portal](groups-get-started.md)
