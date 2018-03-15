---
title: "Přidání skupin pro uspořádání uživatelů a zařízení"
titlesuffix: Microsoft Intune
description: "Přidejte skupiny pro uspořádání uživatelů a zařízení podle zeměpisné oblasti, oddělení a hardwarových zvláštností."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 42e7e2c8d239b8150f67a699ba6fef156b3e1a7d
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
# <a name="add-groups-to-organize-users-and-devices"></a>Přidání skupin pro uspořádání uživatelů a zařízení
Služba Intune používá ke správě zařízení a uživatelů skupiny Azure Active Directory (AD). Jako správce Intune můžete nastavit skupiny tak, aby odpovídaly potřebám vaší organizace. Vytvořte skupiny, které uživatele nebo zařízení uspořádají podle zeměpisné polohy, oddělení nebo vlastností hardwaru. Skupiny použijte ke spravování úloh se škálováním. Například můžete nastavit zásady pro mnoho uživatelů nebo nasadit aplikace řadě zařízení.

Toto téma vysvětluje, jak do Intune přidat skupiny, které se mají používat.

Můžete přidat následující typy skupin:
- **Přiřazené skupiny** – Přidejte uživatele nebo zařízení do statické skupiny ručně.
- **Dynamické skupiny** – (pomocí Azure Active Directory Premium) Umožňují vytvořit skupiny pro uživatele nebo zařízení definované jednoduchými nebo pokročilými pravidly.

## <a name="add-a-new-group"></a>Přidání nové skupiny

Pomocí následujícího postupu vytvořte novou skupinu.
1. Na Azure Portalu přejděte na **Skupiny** a potom v okně **Všechny skupiny** zvolte **Nová skupina**.
  ![Snímek obrazovky Uživatelé a skupiny s vybranou položkou Nová skupina](./media/groups-add-new.png)
2. Zadejte **název** a **popis** nové skupiny. Tyto vlastnosti se objeví jenom na portálu správy a uživatelům se nezobrazí.

3. Zvolte **typ členství**:
  - **Přiřazené** – vytvoří skupinu z ručně přiřazených členů. Další informace o [přiřazených skupinách Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
  - **Dynamický uživatel** – vytvoří skupinu uživatelů definovanou **dynamickým dotazem**.
  - **Dynamické zařízení** – vytvoří skupinu zařízení definovanou **dynamickým dotazem**.

  ![Snímek obrazovky s vlastnostmi skupiny v Intune](./media/groups-add-properties.png)

  Azure AD vám umožňuje vytvořit dynamické skupiny na základě pravidel, která definují členství. Naučte se [vytvářet dynamické skupiny podle atributů](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

4. Pokud chcete dát členům skupiny uživatelů přístup ke sdíleným aplikacím Office 365, můžete vybrat **Povolit funkce Office**. Přečtěte si další informace o [Skupinách Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).
5. Novou skupinu přidáte tlačítkem **Vytvořit**.

## <a name="see-also"></a>Viz taky
- [Správa přístupu k prostředkům prostřednictvím skupin Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Skupiny Intune Classic na portálu Azure Portal](groups-get-started.md)
