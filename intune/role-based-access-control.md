---
title: Řízení přístupu na základě rolí (RBAC) v Microsoft Intune
description: Zjistěte, jak RBAC umožňuje určovat, kdo může provádět akce a změny v Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1efa421b568a5cc28b23859f68de7145b5b4a943
ms.sourcegitcommit: af2512a1342d8037a96a61c8cc2c63e107913733
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/12/2019
ms.locfileid: "59533530"
---
# <a name="role-based-access-control-rbac-with-microsoft-intune"></a>Řízení přístupu na základě rolí (RBAC) v Microsoft Intune

Řízení přístupu na základě role (RBAC) vám pomůže spravovat, kdo má přístup k prostředkům vaší organizace a co dělají pomocí těchto prostředků.  Podle [přiřazení rolí](assign-role.md) Intune uživatelům, můžete omezit, co mohou zobrazit a změnit. Každá role má sadu oprávnění, která určují, co uživatelé s touto rolí mají přístup k a změny v rámci vaší organizace.

Abyste mohli vytvářet, upravovat nebo přiřazovat role, váš účet musí mít ve službě Azure AD jedno z těchto oprávnění:
- **Globální správce**
- **Správce služby Intune** (označované také jako **správce Intune**)

## <a name="roles"></a>Role
Role definuje sadu oprávnění udělit uživatelům, kteří k této roli přiřazení.
Můžete použít předdefinované a vlastní role. Předdefinované role zahrnují některé běžné scénáře s Intune. Je možné [vytvořit vlastní role](create-custom-role.md) s přesnou sadu oprávnění, které potřebujete. Několik rolí Azure Active Directory nemáte oprávnění pro Intune.
Chcete-li zobrazit roli, zvolte **Intune** > **role** > **všechny role** > zvolte roli. Zobrazí se vám na následujících stránkách:

-   **Vlastnosti**: Název, popis, typ, přiřazení a značky oboru role. 
-   **Oprávnění**: Obsahuje přehled dlouhé sady přepíná definování role má oprávnění.
-   **Přiřazení**: Seznam [přiřazení rolí]( assign-role.md) definující, kteří mají přístup na uživatele nebo zařízení, která. Roli můžete mít více přiřazení a uživatel může být ve více přiřazení.

### <a name="built-in-roles"></a>Vestavěné role
Předdefinované role můžete přiřadit ke skupinám bez další konfigurace. Nejde odstranit ani upravit název, popis, typ nebo oprávnění předdefinovaná role. Úplný seznam oprávnění pro každou předdefinovaná role, naleznete v tématu [RBAC tabulka Intune] ((https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

- **Operátor helpdesku**: Provádí vzdálené úlohy u uživatelů a zařízení a může uživatelům a zařízením přiřazovat aplikace nebo zásady.
- **Správce zásad a profilů**: Spravuje zásady dodržování předpisů, konfigurační profily, registrace Apple, identifikátory podnikových zařízení a standardních hodnot zabezpečení.
- **Operátor pouze pro čtení**: Zobrazení uživatele, zařízení, registraci, konfiguraci a informace o aplikaci. Nelze provádět změny v Intune.
- **Správce aplikací**: Spravuje mobilní a spravované aplikace, může číst informace o zařízení a profily konfigurace zařízení můžete zobrazit.
- **Role Správce služby Intune**: Spravuje vlastní role Intune a přidá přiřazení předdefinované role Intune. Je jediná role Intune, které můžete přiřazovat oprávnění správcům.
- **Správce školy**: Spravuje zařízení s Windows 10 v [Intune for Education](introduction-intune-education.md).

### <a name="custom-roles"></a>Vlastní role
Vlastní role můžete vytvořit pomocí vlastních oprávnění. Další informace o vlastních rolích najdete v tématu [vytvořit vlastní roli](create-custom-role.md).

### <a name="azure-active-directory-roles-with-intune-access"></a>Role služby Azure Active Directory s přístupem k Intune
| Role Azure Active Directory | Všechna data Intune | Data auditu Intune |
| --- | :---: | :---: |
| Globální správce | Čtení/zápisu | Čtení/zápisu |
| Správce služby Intune | Čtení/zápisu | Čtení/zápisu |
| Správce podmíněného přístupu | Žádné | Žádné |
| Správce zabezpečení | Jen pro čtení | Jen pro čtení |
| Operátor zabezpečení | Jen pro čtení | Jen pro čtení |
| Čtenář zabezpečení | Jen pro čtení | Jen pro čtení |
| Globální čtečky | Jen pro čtení | Jen pro čtení |
| Správce dodržování předpisů | Žádné | Jen pro čtení |
| Správce dat dodržování předpisů | Žádný | Jen pro čtení |

> [!TIP]
> Intune také ukazuje tři rozšíření Azure AD: **Uživatelé**, **skupiny**, a **podmíněného přístupu**, řízená prostřednictvím Azure AD RBAC. **Správce uživatelských účtů** navíc provádí jenom aktivity uživatele nebo skupiny AAD a nemá úplná oprávnění provádět všechny aktivity v Intune. Další informace najdete v tématu [RBAC s Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles).
### <a name="roles-created-in-the-intune-classic-portal"></a>Role vytvořené na klasickém portálu Intune
Z klasického portálu Intune se do Intune na Azure Portalu migrují jenom **správci služeb** Intune s úplnými oprávněními. Musíte přiřadit Intune **Správci služeb** uživatelé s "Jen pro čtení" nebo "Helpdesku" přístup do role Intune na portálu Azure portal a odebrat z portálu classic.
> [!IMPORTANT]
> Možná bude nutné zachovat přístup správce služby Intune na portálu classic, pokud vaši správci dál potřebovat přístup ke správě počítačů pomocí Intune.

## <a name="role-assignments"></a>Přiřazení rolí
Definuje přiřazení role:

- kteří uživatelé jsou přiřazení k roli
- jaké prostředky můžete zobrazit
- jaké prostředky mohou změnit.

Uživatelům můžete přiřadit předdefinované i vlastní role. Přiřazení Intune role, uživatel musí mít licenci pro Intune.
Chcete-li zobrazit přiřazení role, zvolte **Intune** > **role** > **všechny role** > vyberte roli > zvolit přiřazení. Zobrazí se vám na následujících stránkách:

-   **Vlastnosti**: Název, popis, role, členy, obory a přiřazení značek.
-   **Členové**: Všichni uživatelé v uvedené skupiny mají oprávnění ke správě uživatelů a zařízení, které jsou uvedeny v rozsah (skupiny).
-   **Rozsah (skupiny)**: Všechny uživatele nebo zařízení v těchto skupinách může být spravován uživatelů ve členech.
-   **[Obor (značky)](scope-tags.md)**: Uživatelé v členové mohou vidět prostředky, které mají stejné značky oboru.

### <a name="multiple-role-assignments"></a>Více přiřazení rolí
Pokud má uživatel více přiřazení role, oprávnění v těchto přiřazení rolí následujícím způsobem rozšířit na různé objekty:

- Přiřazení oprávnění se vztahují jenom na objekty (třeba zásady nebo aplikace) v této roli přiřazení rozsah (skupiny). Přiřazení oprávnění se nevztahují na objekty v jiných přiřazení rolí není-li toto přiřazení je explicitně neudělí.
- Pro všechny objekty stejného typu (stejně jako všechny zásady nebo všechny aplikace) se vztahují další oprávnění (jako je například vytvoření a čtení), v některém z přiřazení uživatele.
- Oprávnění pro objekty různé typy (třeba zásady nebo aplikace), nemůžete použít k sobě navzájem. Oprávnění ke čtení pro zásady, například, neposkytuje oprávnění pro čtení k aplikacím v přiřazení uživatele.

## <a name="next-steps"></a>Další postup
- [Přiřazení role uživateli](assign-role.md)
- [Vytvořit vlastní roli](create-custom-role.md)
