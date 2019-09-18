---
title: Řízení přístupu na základě role (RBAC) s Microsoft Intune
description: Přečtěte si, jak vám umožňuje řídit, kdo může provádět akce a provádět změny v Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: e636e2df8271210d8938727eb99491e1ffdd5bdc
ms.sourcegitcommit: d2989b9992d10d133573d9bc31479659fb7e242c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/18/2019
ms.locfileid: "71080037"
---
# <a name="role-based-access-control-rbac-with-microsoft-intune"></a>Řízení přístupu na základě role (RBAC) s Microsoft Intune

Řízení přístupu na základě role (RBAC) pomáhá spravovat, kdo má přístup k prostředkům vaší organizace a co s těmito prostředky může dělat.  [Přiřazením rolí](assign-role.md) uživatelům Intune můžete omezit to, co můžou zobrazit a změnit. Každá role má sadu oprávnění, která určují, co můžou uživatelé s touto rolí používat a měnit v rámci vaší organizace.

Abyste mohli vytvářet, upravovat nebo přiřazovat role, váš účet musí mít ve službě Azure AD jedno z těchto oprávnění:
- **Globální správce**
- **Správce služby Intune** (označuje se také jako **správce Intune**)

Pokud potřebujete Rady a návrhy týkající se RBAC v Intune, můžete se podívat na tyto řady pěti videí, které prezentují příklady a návody: [1](https://www.youtube.com/watch?v=5deXLMLcnKY), [2](https://www.youtube.com/watch?v=38dnMBLuxbQ), [3](https://www.youtube.com/watch?v=6vqg9cAkMbY), [4](https://www.youtube.com/watch?v=5yOLajFFMHE), [5](https://www.youtube.com/watch?v=P5DDvsSF4Wk).

## <a name="roles"></a>Role
Role definuje sadu oprávnění udělených uživatelům přiřazeným k této roli.
Můžete použít jak předdefinované, tak i vlastní role. Předdefinované role se týkají některých běžných scénářů Intune. Můžete [vytvořit vlastní role](create-custom-role.md) s přesnou sadou oprávnění, která potřebujete. Několik rolí Azure Active Directory má oprávnění k Intune.
Pokud chcete zobrazit roli,**Vyberte role** >  **Intune** > **všechny role** > zvolit roli. Zobrazí se následující stránky:

- **Vlastnosti**: Značky název, popis, typ, přiřazení a obor pro roli 
- **Oprávnění**: Uvádí dlouhou sadu přepínačů definujících, jaká oprávnění role má.
- **Přiřazení**: Seznam [přiřazení rolí]( assign-role.md) , které definují, kteří uživatelé mají přístup k jakým uživatelům nebo zařízením Role může mít více přiřazení a uživatel může být v několika přiřazeních.

### <a name="built-in-roles"></a>Vestavěné role
Předdefinované role můžete přiřadit skupinám bez další konfigurace. Nemůžete odstranit ani upravit název, popis, typ ani oprávnění předdefinované role. Úplný seznam oprávnění pro jednotlivé předdefinované role najdete v [tabulce RBAC služby Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

- **Operátor helpdesku**: Provede vzdálené úlohy pro uživatele a zařízení a může uživatelům a zařízením přiřazovat aplikace nebo zásady.
- **Správce zásad a profilů**: Spravuje zásady dodržování předpisů, konfigurační profily, registrace Apple, identifikátory podnikových zařízení a směrné plány zabezpečení.
- **Operátor s oprávněními jen pro čtení**: Zobrazí informace o uživatelích, zařízeních, registraci, konfiguraci a aplikacích. Nejde dělat změny v Intune.
- **Správce aplikací**: Spravují mobilní a spravované aplikace, umí číst informace o zařízení a můžou zobrazovat profily konfigurace zařízení.
- **Správce role Intune**: Spravuje vlastní role Intune a přidává přiřazení pro předdefinované role Intune. Je to jediná role Intune, která může přiřazovat oprávnění správcům.
- **Správce školy**: Spravuje zařízení s Windows 10 v [Intune for Education](introduction-intune-education.md).

### <a name="custom-roles"></a>Vlastní role
Můžete vytvořit vlastní role s vlastními oprávněními. Další informace o vlastních rolích najdete v tématu [Vytvoření vlastní role](create-custom-role.md).

### <a name="azure-active-directory-roles-with-intune-access"></a>Azure Active Directory role s přístupem k Intune
| Role Azure Active Directory | Všechna data Intune | Data auditu Intune |
| --- | :---: | :---: |
| Globální správce | Čtení a zápis | Čtení a zápis |
| Správce služby Intune | Čtení a zápis | Čtení a zápis |
| Správce podmíněného přístupu | Žádné | Žádné |
| Správce zabezpečení | Jen pro čtení | Jen pro čtení |
| Operátor zabezpečení | Jen pro čtení | Jen pro čtení |
| Čtecí modul zabezpečení | Jen pro čtení | Jen pro čtení |
| Správce dodržování předpisů | Žádné | Jen pro čtení |
| Správce dat dodržování předpisů | Žádné | Jen pro čtení |

> [!TIP]
> Intune také ukazuje tři rozšíření Azure AD: **Uživatelé**, **skupiny**a **podmíněný přístup**, které jsou ovládány pomocí služby Azure AD RBAC. **Správce uživatelských účtů** navíc provádí jenom aktivity uživatele nebo skupiny AAD a nemá úplná oprávnění provádět všechny aktivity v Intune. Další informace najdete v tématu [RBAC s Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles).
### <a name="roles-created-in-the-intune-classic-portal"></a>Role vytvořené na klasickém portálu Intune
Z klasického portálu Intune se do Intune na Azure Portalu migrují jenom **správci služeb** Intune s úplnými oprávněními. Musíte znovu přiřadit role **správců služby** Intune s přístupem "jen pro čtení" nebo "helpdesk" do rolí Intune v Azure Portal a odebrat je z portálu Classic.
> [!IMPORTANT]
> Pokud budou vaši správci dál potřebovat přístup ke správě počítačů pomocí Intune, může být potřeba zachovat přístup správce služby Intune na klasickém portálu.

## <a name="role-assignments"></a>Přiřazení rolí
Přiřazení role definuje:

- kteří uživatelé jsou přiřazeni k roli
- prostředky, které uvidí
- Jaké prostředky mohou změnit.

Uživatelům můžete přiřadit vlastní i předdefinované role. Uživatel musí mít licenci Intune, aby mu byla přiřazena role Intune.
Pokud chcete zobrazit přiřazení role,**Vyberte role** >  **Intune** > **všechny role** > vyberte roli > zvolit přiřazení. Zobrazí se následující stránky:

- **Vlastnosti**: Název, popis, role, členy, obory a značky přiřazení.
- **Členové**: Všichni uživatelé v uvedených skupinách zabezpečení Azure mají oprávnění ke správě uživatelů nebo zařízení, která jsou uvedená v oboru (skupiny).
- **Rozsah (skupiny)** : Všechny uživatele nebo zařízení v těchto skupinách zabezpečení Azure je možné spravovat pomocí uživatelů v rámci členů.
- **[Scope (značky)](scope-tags.md)** : Uživatelé v členovi mohou zobrazit prostředky, které mají stejné značky oboru.

### <a name="multiple-role-assignments"></a>Přiřazení více rolí
Pokud má uživatel více než jedno přiřazení rolí, oprávnění a značky oboru, přiřazení těchto rolí se rozšiřuje na různé objekty následujícím způsobem:

- Přiřazení oprávnění a značek oboru platí jenom pro objekty (jako jsou zásady nebo aplikace) v oboru přiřazení této role (skupiny). Přiřadit oprávnění a značky oboru se nevztahují na objekty v jiných přiřazeních rolí, pokud jiné přiřazení je výslovně neudělí.
- Další oprávnění (například vytváření, čtení, aktualizace, odstranění) a značky oboru se vztahují na všechny objekty stejného typu (jako jsou všechny zásady nebo všechny aplikace) v libovolném přiřazení uživatele.
- Značky oprávnění a oboru pro objekty různých typů (jako jsou zásady nebo aplikace) se nevztahují na sebe navzájem. Oprávnění ke čtení pro zásady například neposkytuje oprávnění ke čtení pro aplikace v přiřazení uživatele.

## <a name="next-steps"></a>Další kroky
- [Přiřazení role uživateli](assign-role.md)
- [Vytvoření vlastní role](create-custom-role.md)
