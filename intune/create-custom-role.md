---
title: Vytvořit vlastní roli v Intune
description: Zjistěte, jak vytvořit vlastní roli v Microsoft Intune.
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
ms.openlocfilehash: d053b0b37931443a343c91b5122b7a097d248c51
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66048693"
---
# <a name="create-a-custom-role-in-intune"></a>Vytvořit vlastní roli v Intune

Můžete vytvořit vlastní role Intune, která zahrnuje všechna oprávnění nutná pro konkrétní pracovní funkci. Pokud například skupina oddělení IT spravuje aplikace, zásady a profily konfigurace, můžete všechna tato oprávnění přidat společně v jedné vlastní roli. Po vytvoření vlastní roli, můžete [přiřadit](assign-role.md) ho pro všechny uživatele, kteří potřebují tato oprávnění.

Abyste mohli vytvářet, upravovat nebo přiřazovat role, váš účet musí mít ve službě Azure AD jedno z těchto oprávnění:
- **Globální správce**
- **Správce služby Intune**

## <a name="to-create-a-custom-role"></a>Jak vytvořit vlastní roli

1. Přihlaste se na [Azure Portal](https://portal.azure.com) pomocí svých přihlašovacích údajů k Intune.

2. V nabídce vlevo zvolte **Všechny služby** a do filtru textového pole pak zadejte **Intune**.

3. Zvolte **Intune** > **role** > **všechny role** > **přidat**.

4. V okně **Přidat vlastní roli** zadejte název a popis nové role a klikněte na **Oprávnění**.

5. V okně **Oprávnění** zvolte oprávnění, která chcete v této roli použít. Rozhodnout se, která oprávnění chcete použít, vám pomůže [tabulka Řízení správy na základě rolí s Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

6. Na **obor (značky)** okně zvolte značky pro tuto roli. Tato role mít přístup k prostředkům, které také obsahovat tyto značky.

7. Po dokončení vyberte **OK**.

8. V okně **Přidat vlastní roli** klikněte na **Vytvořit**. Nová role se zobrazí v seznamu na **role Intune – všechny role** okno.

## <a name="next-steps"></a>Další postup
- [Přiřazení role uživateli](assign-role.md)
- [Další informace o řízení přístupu na základě rolí v Intune](role-based-access-control.md)
