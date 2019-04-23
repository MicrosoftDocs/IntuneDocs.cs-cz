---
ms.openlocfilehash: 015e50d24149a6b6242eda86d5f3d62489e9955d
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511319"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Požadavky na přihlašovací údaje pro Azure AD a Intune

Ověřování a autorizace jsou založené na přihlašovacích údajích Azure AD a řízení přístupu na základě role (RBAC) Intune. Ve výchozím nastavení mají všichni globální správci a správci služby Intune pro vašeho tenanta přístup k datovému skladu. Role Intune můžete použít k poskytnutí přístupu pro další uživatele tak, že jim udělíte přístup k prostředku **Datový sklad Intune**.

Požadavky pro přístup k datovému skladu Intune (včetně rozhraní API) jsou:

  -  Uživatel musí být jedním z těchto uživatelů:
      -  Globální správce Azure AD
      -  Správce služby Intune
      -  Uživatel s přístupem na základě role k prostředku **Datový sklad Intune**
      -  Ověření bez účasti uživatele pomocí [ověřování pouze na úrovni aplikace](../data-warehouse-app-only-auth.md) 
