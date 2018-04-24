---
title: Přidání skupin pro uspořádání uživatelů a zařízení
titlesuffix: Microsoft Intune
description: Přidejte skupiny pro uspořádání uživatelů a zařízení podle zeměpisné oblasti, oddělení a hardwarových zvláštností.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 613d64e396e969b8b6bde76ee6c4474a60be8ba9
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="add-groups-to-organize-users-and-devices"></a>Přidání skupin pro uspořádání uživatelů a zařízení
Služba Intune používá ke správě zařízení a uživatelů skupiny Azure Active Directory (AD). Jako správce Intune můžete nastavit skupiny tak, aby odpovídaly potřebám vaší organizace. Vytvořte skupiny, které uživatele nebo zařízení uspořádají podle zeměpisné polohy, oddělení nebo vlastností hardwaru. Skupiny použijte ke spravování úloh se škálováním. Například můžete nastavit zásady pro mnoho uživatelů nebo nasadit aplikace řadě zařízení.

Toto téma vysvětluje, jak do Intune přidat skupiny, které se mají používat.

Můžete přidat následující typy skupin:
- **Přiřazené skupiny** – Přidejte uživatele nebo zařízení do statické skupiny ručně.
- **Dynamické skupiny** – (pomocí Azure Active Directory Premium) Umožňují vytvořit skupiny pro uživatele nebo zařízení definované jednoduchými nebo pokročilými pravidly.

## <a name="add-a-new-group"></a>Přidání nové skupiny

Pomocí následujícího postupu vytvořte novou skupinu.
1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Skupiny** a potom v podokně **Všechny skupiny** zvolte **Nová skupina**.
   ![Snímek obrazovky Azure Portalu s vybranou možností Nová skupina](./media/groups-add-new.png)
4. Zadejte **typ**, **název** a **popis** nové skupiny. Tyto vlastnosti se objeví jenom na portálu správy a uživatelům se nezobrazí.

5. Zvolte **typ členství**:
   - **Přiřazené** – vytvoří skupinu z ručně přiřazených členů. Další informace o [přiřazených skupinách Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
   - **Dynamický uživatel** – vytvoří skupinu uživatelů definovanou **dynamickým dotazem**.
   - **Dynamické zařízení** – vytvoří skupinu zařízení definovanou **dynamickým dotazem**.

   ![Snímek obrazovky s vlastnostmi skupiny v Intune](./media/groups-add-properties.png)

   Azure AD vám umožňuje vytvořit dynamické skupiny na základě pravidel, která definují členství. Naučte se [vytvářet dynamické skupiny podle atributů](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

6. Pokud chcete dát členům skupiny uživatelů přístup ke sdíleným aplikacím Office 365, můžete vybrat **Povolit funkce Office**. Přečtěte si další informace o [Skupinách Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).
7. Novou skupinu přidáte tlačítkem **Vytvořit**.

## <a name="see-also"></a>Viz taky
- [Správa přístupu k prostředkům prostřednictvím skupin Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Skupiny Intune Classic na portálu Azure Portal](groups-get-started.md)
