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
# <a name="create-a-custom-role-in-intune"></a>Vytvoření vlastní role v Intune

Můžete vytvořit vlastní roli Intune, která bude obsahovat všechna oprávnění požadovaná pro konkrétní pracovní funkci. Pokud například skupina oddělení IT spravuje aplikace, zásady a profily konfigurace, můžete všechna tato oprávnění přidat společně v jedné vlastní roli. Po vytvoření vlastní role ji můžete [přiřadit](assign-role.md) všem uživatelům, kteří tato oprávnění potřebují.

Abyste mohli vytvářet, upravovat nebo přiřazovat role, váš účet musí mít ve službě Azure AD jedno z těchto oprávnění:
- **Globální správce**
- **Správce služby Intune**

## <a name="to-create-a-custom-role"></a>Jak vytvořit vlastní roli

1. Přihlaste se na [Azure Portal](https://portal.azure.com) pomocí svých přihlašovacích údajů k Intune.

2. V nabídce vlevo zvolte **Všechny služby** a do filtru textového pole pak zadejte **Intune**.

3. Vyberte **role** > **Intune** > **všechny role** > **Přidat**.

4. V okně **Přidat vlastní roli** zadejte název a popis nové role a klikněte na **Oprávnění**.

5. V okně **Oprávnění** zvolte oprávnění, která chcete v této roli použít.

6. V okně **obor (značky)** vyberte značky pro tuto roli. Tato role má přístup k prostředkům, které mají také tyto značky.

7. Po dokončení vyberte **OK**.

8. V okně **Přidat vlastní roli** klikněte na **Vytvořit**. Nová role se zobrazí v seznamu v okně **role Intune – všechny role** .


## <a name="copy-a-role"></a>Kopírovat roli

Můžete také zkopírovat existující roli.

1. Přihlaste se k [Azure Portal](https://portal.azure.com) s přihlašovacími údaji k Intune a vyberte **Intune**.

2. Vyberte **role** > **všechny role** > v seznamu vyberte roli > **duplicitní**.

3. V části **duplicitní role**zadejte název. Ujistěte se, že používáte jedinečný název.

4. Všechna oprávnění a značky oboru z původní role budou již vybrány. Následně můžete změnit **název**, **Popis**, **oprávnění**a obor duplicitní role **(značky)** .

5. Vyberte **Vytvořit**. 

## <a name="next-steps"></a>Další kroky
- [Přiřazení role uživateli](assign-role.md)
- [Další informace o řízení přístupu na základě role v Intune](role-based-access-control.md)
