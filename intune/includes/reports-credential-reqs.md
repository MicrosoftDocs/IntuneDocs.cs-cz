---
ms.openlocfilehash: 76706fb39c3c5a69cba4fbf3f57c0b58d92e4a27
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2019
ms.locfileid: "67559986"
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
