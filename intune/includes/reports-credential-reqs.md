---
ms.openlocfilehash: 8483ed3d4198e228bdaaf4723b2c9c0dca9cecfc
ms.sourcegitcommit: fc356fd69beaeb3d69982b47e2bdffb6f7127f8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/03/2019
ms.locfileid: "71830510"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Požadavky na přihlašovací údaje pro Azure AD a Intune

Ověřování a autorizace jsou založené na přihlašovacích údajích Azure AD a řízení přístupu na základě role (RBAC) Intune. Všichni globální správci a správci služby Intune pro vašeho tenanta mají ve výchozím nastavení přístup k datovému skladu. Použijte role Intune k poskytnutí přístupu pro další uživatele tak, že jim udělíte přístup k prostředku **datového skladu Intune** .

Požadavky pro přístup k datovému skladu Intune (včetně rozhraní API) jsou:

- Uživatel musí být jedním z těchto:
  - Globální správce Azure AD
  - Správce služby Intune
  - Uživatel s přístupem na základě role k prostředku **datového skladu Intune**
  - Ověřování bez uživatelů pomocí [ověřování pouze aplikací](../developer/data-warehouse-app-only-auth.md) 
