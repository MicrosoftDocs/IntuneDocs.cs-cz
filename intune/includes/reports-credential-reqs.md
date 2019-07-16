---
ms.openlocfilehash: 6ec8f8a613d3b0a0b17f2615de634e70fa282fd7
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "68229319"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Požadavky na přihlašovací údaje pro Azure AD a Intune

Ověřování a autorizace jsou založené na přihlašovacích údajích Azure AD a řízení přístupu na základě role (RBAC) Intune. Ve výchozím nastavení mají všichni globální správci a správci služby Intune pro vašeho tenanta přístup k datovému skladu. Role Intune můžete použít k poskytnutí přístupu pro další uživatele tak, že jim udělíte přístup k prostředku **Datový sklad Intune**.

Požadavky pro přístup k datovému skladu Intune (včetně rozhraní API) jsou:

- Uživatel musí být jedním z těchto uživatelů:
  - Globální správce Azure AD
  - Správce služby Intune
  - Uživatel s přístupem na základě role k prostředku **Datový sklad Intune**
  - Ověření bez účasti uživatele pomocí [ověřování pouze na úrovni aplikace](../data-warehouse-app-only-auth.md) 
