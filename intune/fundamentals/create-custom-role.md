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
ms.openlocfilehash: 68c2dc7df123593513c14e16e2626c7426f50b01
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207413"
---
# <a name="create-a-custom-role-in-intune"></a>Vytvoření vlastní role v Intune

Můžete vytvořit vlastní roli Intune, která bude obsahovat všechna oprávnění požadovaná pro konkrétní pracovní funkci. Pokud například skupina oddělení IT spravuje aplikace, zásady a profily konfigurace, můžete všechna tato oprávnění přidat společně v jedné vlastní roli. Po vytvoření vlastní role ji můžete [přiřadit](assign-role.md) všem uživatelům, kteří tato oprávnění potřebují.

Abyste mohli vytvářet, upravovat nebo přiřazovat role, váš účet musí mít ve službě Azure AD jedno z těchto oprávnění:
- **Globální správce**
- **Správce služby Intune**

## <a name="to-create-a-custom-role"></a>Jak vytvořit vlastní roli

1. V [centru pro správu Microsoft Endpoint Manageru](https://go.microsoft.com/fwlink/?linkid=2109431)vyberte **role** > **všechny role** > **Přidat**.

2. V okně **Přidat vlastní roli** zadejte název a popis nové role a klikněte na **Oprávnění**.

3. V okně **Oprávnění** zvolte oprávnění, která chcete v této roli použít.

4. V okně **obor (značky)** vyberte značky pro tuto roli. Tato role má přístup k prostředkům, které mají také tyto značky.

5. Po dokončení vyberte **OK**.

6. V okně **Přidat vlastní roli** klikněte na **Vytvořit**. Nová role se zobrazí v seznamu v okně **role Intune – všechny role** .


## <a name="copy-a-role"></a>Kopírovat roli

Můžete také zkopírovat existující roli.

1. V [centru pro správu Microsoft Endpoint Manageru](https://go.microsoft.com/fwlink/?linkid=2109431)zvolte **role** > **všechny role** > vyberte roli v seznamu > **duplikujte**.

2. V části **duplicitní role**zadejte název. Ujistěte se, že používáte jedinečný název.

3. Všechna oprávnění a značky oboru z původní role budou již vybrány. Následně můžete změnit **název**, **Popis**, **oprávnění**a obor duplicitní role **(značky)**.

4. Vyberte **Vytvořit**. 

## <a name="next-steps"></a>Další kroky
- [Přiřazení role uživateli](assign-role.md)
- [Další informace o řízení přístupu na základě role v Intune](role-based-access-control.md)
