---
title: Přiřazení role uživateli Intune
description: Přečtěte si, jak přiřadit předdefinované nebo vlastní roli uživateli v Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: d9e337d47757e3c5507c94433f90d5c2863bc1b0
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503007"
---
# <a name="assign-a-role-to-an-intune-user"></a>Přiřazení role uživateli Intune

Uživateli Intune můžete přiřadit [integrovanou](role-based-access-control.md#built-in-roles) nebo [vlastní](create-custom-role.md) roli.

Abyste mohli vytvářet, upravovat nebo přiřazovat role, váš účet musí mít ve službě Azure AD jedno z těchto oprávnění:
- **Globální správce**
- **Správce služby Intune**

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).

2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.

3. V okně **Intune** vyberte **role** > **všechny role**.

4. V okně **role Intune – všechny role** vyberte předdefinovanou roli, kterou chcete přiřadit.

5. V okně <*název role*> – **přehled** vyberte **Spravovat** > **přiřazení**.

6. V okně vlastní role zvolte **Přiřadit**.

7. V okně **přiřazení rolí** zadejte **název přiřazení** a nepovinný **Popis přiřazení** .

8. U **členů (skupin)** vyberte skupinu, která obsahuje uživatele, kterému chcete udělit oprávnění.

9. V poli **rozsah (skupiny)** vyberte skupinu obsahující uživatele nebo zařízení, které bude člen výše moci spravovat.

10. V **oblasti rozsah (značky)** vyberte značky, ve kterých se bude toto přiřazení role použít.

11. Po dokončení vyberte **OK**. Nové přiřazení se zobrazí v seznamu přiřazení.


## <a name="next-steps"></a>Další kroky
- [Další informace o řízení přístupu na základě role v Intune](role-based-access-control.md)
- [Vytvoření vlastní role](create-custom-role.md)