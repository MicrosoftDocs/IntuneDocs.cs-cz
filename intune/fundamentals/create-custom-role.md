---
title: Create a custom role in Intune
description: Learn how to create a custom role in Microsoft Intune.
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
ms.openlocfilehash: 3ca83287c58f8d2fb7c8eec5f8cc793e2c67b77a
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390703"
---
# <a name="create-a-custom-role-in-intune"></a>Create a custom role in Intune

You can create a custom Intune role that includes any permissions required for a specific job function. Pokud například skupina oddělení IT spravuje aplikace, zásady a profily konfigurace, můžete všechna tato oprávnění přidat společně v jedné vlastní roli. After creating a custom role, you can [assign](assign-role.md) it to any users that need those permissions.

Abyste mohli vytvářet, upravovat nebo přiřazovat role, váš účet musí mít ve službě Azure AD jedno z těchto oprávnění:
- **Globální správce**
- **Správce služby Intune**

## <a name="to-create-a-custom-role"></a>Jak vytvořit vlastní roli

1. Přihlaste se na [Azure Portal](https://portal.azure.com) pomocí svých přihlašovacích údajů k Intune.

2. V nabídce vlevo zvolte **Všechny služby** a do filtru textového pole pak zadejte **Intune**.

3. Choose **Intune** > **Roles** > **All roles** > **Add**.

4. V okně **Přidat vlastní roli** zadejte název a popis nové role a klikněte na **Oprávnění**.

5. V okně **Oprávnění** zvolte oprávnění, která chcete v této roli použít.

6. On the **Scope (Tags)** blade, choose the tags for this role. This role can access resources that also have these tags.

7. Po dokončení vyberte **OK**.

8. V okně **Přidat vlastní roli** klikněte na **Vytvořit**. The new role is displayed in the list on the **Intune roles - All roles** blade.


## <a name="copy-a-role"></a>Copy a role

You can also copy an existing role.

1. Sign into the [Azure portal](https://portal.azure.com) with your Intune credentials and select **Intune**.

2. Select **Roles** > **All roles** > select a role in the list > **Duplicate**.

3. Under **Duplicate role**, enter a name. Make sure to use a unique name.

4. All the permissions and scope tags from the original role will already be selected. You can subsequently change the duplicate role's **Name**, **Description**, **Permissions**, and **Scope (Tags)** .

5. Vyberte **Vytvořit**. 

## <a name="next-steps"></a>Další kroky
- [Assign a role to a user](assign-role.md)
- [Learn more about role-based access control in Intune](role-based-access-control.md)
