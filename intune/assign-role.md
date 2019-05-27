---
title: Přiřazení role uživateli s Intune
description: Zjistěte, jak přiřadit vestavěné i vlastní role uživatele v Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: a22fef1c04ae52a8a4cc65eaadc1ef6fcd524c19
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66043600"
---
# <a name="assign-a-role-to-an-intune-user"></a>Přiřazení role uživateli s Intune

Můžete přiřadit [integrované](role-based-access-control.md#built-in-roles) nebo [vlastní](create-custom-role.md) role pro uživatele Intune.

Abyste mohli vytvářet, upravovat nebo přiřazovat role, váš účet musí mít ve službě Azure AD jedno z těchto oprávnění:
- **Globální správce**
- **Správce služby Intune**

Úplný seznam oprávnění pro každou předdefinovaná role, najdete v článku [Intune RBAC tabulky](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).

2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.

3. Na **Intune** okně zvolte **role** > **všechny role**.

4. Na **role Intune – všechny role** okně zvolte předdefinovanou roli, kterou chcete přiřadit.

5. Na <*název role*>- **přehled** okně zvolte **spravovat** > **přiřazení**.

6. V okně vlastní role zvolte **Přiřadit**.

7. Na **přiřazení rolí** okno, zadejte **název přiřazení** a volitelné **popis přiřazení** přiřazení.

8. Pro **členy (skupiny)**, zvolte skupinu, která obsahuje uživatele, kterému chcete udělit oprávnění.

9. Pro **rozsah (skupiny)**, zvolte skupinu obsahující uživatele nebo zařízení, které člen výše bude moct spravovat.

10. Pro **obor (značky)**, zvolte značky, kde se budou aplikovat toto přiřazení role.

11. Po dokončení vyberte **OK**. Nové přiřazení se zobrazí v seznamu přiřazení.


## <a name="next-steps"></a>Další postup
- [Další informace o řízení přístupu na základě rolí v Intune](role-based-access-control.md)
- [Vytvořit vlastní roli](create-custom-role.md)
