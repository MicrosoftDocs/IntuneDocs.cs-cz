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
ms.openlocfilehash: 19fff092f7eccfc6de2a027c7834c52698176cbf
ms.sourcegitcommit: 5881979c45fc973cba382413eaa193d369b8dcf6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/24/2020
ms.locfileid: "77569162"
---
# <a name="assign-a-role-to-an-intune-user"></a>Přiřazení role uživateli Intune

Uživateli Intune můžete přiřadit [integrovanou](role-based-access-control.md#built-in-roles) nebo [vlastní](create-custom-role.md) roli.

Abyste mohli vytvářet, upravovat nebo přiřazovat role, váš účet musí mít ve službě Azure AD jedno z těchto oprávnění:
- **Globální správce**
- **Správce služby Intune**

1. V [centru pro správu Microsoft Endpoint Manageru](https://go.microsoft.com/fwlink/?linkid=2109431)vyberte možnost **Správa tenanta** > **role** > **všechny role**.

2. V okně **role Intune – všechny role** vyberte předdefinovanou roli, kterou chcete přiřadit > **přiřazení** > **přiřadit**.

5. Na stránce **základy** zadejte **název přiřazení** a volitelný **Popis přiřazení**a klikněte na tlačítko **Další**.

6. Na stránce **skupiny pro správu** vyberte skupinu, která obsahuje uživatele, kterému chcete udělit oprávnění. Klikněte na **Další**.

7. Na stránce **rozsah (skupiny)** vyberte skupinu obsahující uživatele nebo zařízení, které bude člen výše moci spravovat. Zvolte **Další**.

8. Na stránce **obor (značky)** vyberte značky, ve kterých se bude toto přiřazení role použít. Zvolte **Další**.

9. Po dokončení na stránce **Revize + vytvořit** klikněte na **vytvořit**. Nové přiřazení se zobrazí v seznamu přiřazení.

## <a name="next-steps"></a>Další postup
- [Další informace o řízení přístupu na základě role v Intune](role-based-access-control.md)
- [Vytvoření vlastní role](create-custom-role.md)


