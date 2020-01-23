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
ms.openlocfilehash: 780a248f16a8a5028875c9c2401921ea23d0af24
ms.sourcegitcommit: 70b40aa4743c8396f8d6a0163893c4a337d67c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2020
ms.locfileid: "76540924"
---
# <a name="assign-a-role-to-an-intune-user"></a>Přiřazení role uživateli Intune

Uživateli Intune můžete přiřadit [integrovanou](role-based-access-control.md#built-in-roles) nebo [vlastní](create-custom-role.md) roli.

Abyste mohli vytvářet, upravovat nebo přiřazovat role, váš účet musí mít ve službě Azure AD jedno z těchto oprávnění:
- **Globální správce**
- **Správce služby Intune**

1. V [centru pro správu Microsoft Endpoint Manageru](https://go.microsoft.com/fwlink/?linkid=2109431)vyberte možnost **Správa tenanta** > **role** > **všechny role**.

2. V okně **role Intune – všechny role** vyberte předdefinovanou roli, kterou chcete přiřadit.

3. V okně <*název role*> – **přehled** vyberte **Spravovat** > **přiřazení**.

4. V okně vlastní role zvolte **Přiřadit**.

5. V okně **přiřazení rolí** zadejte **název přiřazení** a nepovinný **Popis přiřazení** .

6. U **členů (skupin)** vyberte skupinu, která obsahuje uživatele, kterému chcete udělit oprávnění.

7. V poli **rozsah (skupiny)** vyberte skupinu obsahující uživatele nebo zařízení, které bude člen výše moci spravovat.

8. V **oblasti rozsah (značky)** vyberte značky, ve kterých se bude toto přiřazení role použít.

9. Po dokončení vyberte **OK**. Nové přiřazení se zobrazí v seznamu přiřazení.


## <a name="next-steps"></a>Další kroky
- [Další informace o řízení přístupu na základě role v Intune](role-based-access-control.md)
- [Vytvoření vlastní role](create-custom-role.md)
