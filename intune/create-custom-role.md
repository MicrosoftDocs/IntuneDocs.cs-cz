---
title: Vytvoření vlastní role v Intune
description: Naučte se, jak vytvořit vlastní roli v Microsoft Intune.
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
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6b7e8f5077f2052a11c980ae3f5629af810a8a0b
ms.sourcegitcommit: 49f25efb9bc0f16f587f27878cf45de5e4e6a27f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/18/2019
ms.locfileid: "71094698"
---
# <a name="create-a-custom-role-in-intune"></a>Vytvoření vlastní role v Intune

Můžete vytvořit vlastní roli Intune, která bude obsahovat všechna oprávnění požadovaná pro konkrétní pracovní funkci. Pokud například skupina oddělení IT spravuje aplikace, zásady a profily konfigurace, můžete všechna tato oprávnění přidat společně v jedné vlastní roli. Po vytvoření vlastní role ji můžete [přiřadit](assign-role.md) všem uživatelům, kteří tato oprávnění potřebují.

Abyste mohli vytvářet, upravovat nebo přiřazovat role, váš účet musí mít ve službě Azure AD jedno z těchto oprávnění:
- **Globální správce**
- **Správce služby Intune**

## <a name="to-create-a-custom-role"></a>Jak vytvořit vlastní roli

1. Přihlaste se na [Azure Portal](https://portal.azure.com) pomocí svých přihlašovacích údajů k Intune.

2. V nabídce vlevo zvolte **Všechny služby** a do filtru textového pole pak zadejte **Intune**.

3. Vyberte**role** >  **Intune** **všechny**rolePřidat > . > 

4. V okně **Přidat vlastní roli** zadejte název a popis nové role a klikněte na **Oprávnění**.

5. V okně **Oprávnění** zvolte oprávnění, která chcete v této roli použít.

6. V okně **obor (značky)** vyberte značky pro tuto roli. Tato role má přístup k prostředkům, které mají také tyto značky.

7. Po dokončení vyberte **OK**.

8. V okně **Přidat vlastní roli** klikněte na **Vytvořit**. Nová role se zobrazí v seznamu v okně **role Intune – všechny role** .

## <a name="next-steps"></a>Další postup
- [Přiřazení role uživateli](assign-role.md)
- [Další informace o řízení přístupu na základě role v Intune](role-based-access-control.md)
