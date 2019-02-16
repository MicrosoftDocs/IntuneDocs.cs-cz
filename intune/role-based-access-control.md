---
title: Řízení přístupu na základě role v Microsoft Intune
description: Přečtěte si, jak vám řízení přístupu na základě role (RBAC) umožňuje řídit, kdo může provádět akce a změny v Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/27/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: a57dca7f6b817177cbd131e969c1b5aa52a248a8
ms.sourcegitcommit: e0374b3ced83c8876a4f78b326869c10588a55e5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56307766"
---
# <a name="role-based-administration-control-rbac-with-microsoft-intune"></a>Řízení správy na základě role (RBAC) v Microsoft Intune

Řízení správy na základě rolí pomáhá řídit, kdo může provádět různé úlohy Intune ve vaší organizaci a koho se tyto úlohy týkají. Můžete buď použít předdefinované role, které vyhovují běžným situacím v Intune, nebo si vytvořit své vlastní role. Roli definuje toto:

- **Definice role**: Název role, prostředky, které spravuje a oprávnění udělená pro jednotlivé prostředky.
- **Členové**: Skupiny uživatelů, kteří jsou udělená oprávnění.
- **Rozsah (skupiny)**: Skupiny uživatelů nebo zařízení, které můžou členové spravovat.
- **[Obor (značky)](https://docs.microsoft.com/intune/scope-tags)**: Značky, kde platí přiřazení role.
- **Přiřazení**: Pokud po nakonfigurování definice, členů a oboru se role přiřadí.

![Příklad řízení správy na základě rolí s Intune](./media/intune-rbac-1.PNG)

Na novém Azure Portalu poskytuje **Azure Active Directory (Azure AD)** dvě role adresáře, které je možné s Intune použít. Tyto role mají přidělena úplná oprávnění provádět v Intune všechny aktivity:

- **Globální správce:** Uživatelé s touto rolí mají přístup ke všem funkcím pro správu v Azure AD, jakož i službám s federováním do Azure AD, jako jsou Exchange Online, SharePoint Online a Skype for Business Online. Osoba, která se zaregistruje k tenantovi Azure AD, se stane globálním správcem. Další role správců můžou přiřazovat jenom globální správci Azure AD. Organizace může mít víc globálních správců. Globální správci můžou resetovat heslo kteréhokoliv uživatele a všech ostatních správců.

- **Správce služby Intune:** Uživatelé s touto rolí mají globální oprávnění v rámci Intune, pokud služba není k dispozici. Kromě všech nahrazujících omezení Azure umožňuje tato role také spravovat uživatele a zařízení a vytvářet a spravovat skupiny Intune.

- **Správce podmíněného přístupu:** Uživatelé s touto rolí mají oprávnění k zobrazení, vytvářet, upravovat a odstraňovat zásady podmíněného přístupu.

    > [!IMPORTANT]
    > Role Správce služby Intune neumožňuje spravovat nastavení podmíněného přístupu k Azure AD.
    > Přiřazení Intune role, uživatel musí mít licenci pro Intune.

    > [!TIP]
    > Intune také ukazuje tři rozšíření Azure AD: **Uživatelé**, **skupiny**, a **podmíněného přístupu**, řízená prostřednictvím Azure AD RBAC. **Správce uživatelských účtů** navíc provádí jenom aktivity uživatele nebo skupiny AAD a nemá úplná oprávnění provádět všechny aktivity v Intune. Další informace najdete v tématu [RBAC s Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles).

## <a name="roles-created-in-the-intune-classic-portal"></a>Role vytvořené na klasickém portálu Intune

Z klasického portálu Intune se do Intune na Azure Portalu migrují jenom **správci služeb** Intune s úplnými oprávněními. Musíte přiřadit Intune **Správci služeb** uživatelé s "Jen pro čtení" nebo "Helpdesku" přístup do role Intune na portálu Azure portal a odebrat z portálu classic.

> [!IMPORTANT]
> Možná bude nutné zachovat přístup správce služby Intune na portálu classic, pokud vaši správci dál potřebovat přístup ke správě počítačů pomocí Intune.

## <a name="built-in-roles"></a>Vestavěné role

Předdefinované role můžete přiřadit ke skupinám bez další konfigurace. Nejde odstranit ani upravit integrované role.

- **Operátor helpdesku**: Provádí vzdálené úlohy u uživatelů a zařízení a může uživatelům a zařízením přiřazovat aplikace nebo zásady.
- **Správce zásad a profilů**: Spravuje zásady dodržování předpisů, konfigurační profily, registrace Apple a identifikátory podnikových zařízení.
- **Operátor pouze pro čtení**: Zobrazení uživatele, zařízení, registraci, konfiguraci a informace o aplikaci. Nelze provádět změny v Intune.
- **Správce aplikací**: Spravuje mobilní a spravované aplikace, může číst informace o zařízení a profily konfigurace zařízení můžete zobrazit.
- **Role Správce služby Intune**: Spravuje vlastní role Intune a přidá přiřazení předdefinované role Intune. Je jediná role Intune, které můžete přiřazovat oprávnění správcům.
- **Správce školy**: Spravuje zařízení s Windows 10 v [Intune for Education](introduction-intune-education.md)a můžete provádět následující akce: 

    |Oprávnění|Operace|
    |---|---|
    |Data auditu|Čtení|
    |Konfigurace zařízení|Přiřadit, vytvořit, odstranit, číst, aktualizovat|
    |Správci registrace zařízení|Číst, aktualizovat|
    |Spravovaná zařízení|Číst, aktualizovat<!--, Delete [To be added in 1803]-->|
    |Mobilní aplikace|Přiřadit, vytvořit, odstranit, číst, aktualizovat|
    |Sestavy|Čtení|
    |Vzdálené akce|Vyčistit počítač, restartovat, vzdáleně uzamknout, vyřadit, synchronizovat zařízení, vymazat|
    |Organizace|Čtení|

### <a name="to-assign-a-built-in-role"></a>Přiřazení předdefinované role

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Na **Intune** okně zvolte **role** > **všechny role**.
4. Na **role Intune – všechny role** okně zvolte předdefinovanou roli, kterou chcete přiřadit.

5. Na <*název role*>- **přehled** okně zvolte **spravovat** > **přiřazení**.

6. V okně vlastní role zvolte **Přiřadit**.

7. Na **přiřazení rolí** okno, zadejte **název přiřazení** a volitelné **popis přiřazení** přiřazení.

8. Pro **členy (skupiny)**, zvolte skupinu, která obsahuje uživatele, kterému chcete udělit oprávnění.

9. Pro **rozsah (skupiny)**, zvolte skupinu obsahuje uživatele, které člen výše bude moct spravovat.

10. Pro **obor (značky)**, zvolte značky, kde se budou aplikovat toto přiřazení role.

11. Po dokončení vyberte **OK**. Nové přiřazení se zobrazí v seznamu přiřazení.

### <a name="intune-rbac-table"></a>Řízení správy na základě rolí s Intune

- Stáhněte si [tabulku Řízení správy na základě rolí s Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a), ve které naleznete další podrobné informace o tom, co můžou dělat jednotlivé role.

## <a name="custom-roles"></a>Vlastní role

Můžete vytvořit vlastní roli, která zahrnuje všechna oprávnění nutná pro konkrétní pracovní funkci. Pokud například skupina oddělení IT spravuje aplikace, zásady a profily konfigurace, můžete všechna tato oprávnění přidat společně v jedné vlastní roli.

> [!IMPORTANT]
> Abyste mohli vytvářet, upravovat nebo přiřazovat role, váš účet musí mít ve službě Azure AD jedno z těchto oprávnění:
> - **Globální správce**
> - **Správce služby Intune**

### <a name="to-create-a-custom-role"></a>Jak vytvořit vlastní roli

1. Přihlaste se na [Azure Portal](https://portal.azure.com) pomocí svých přihlašovacích údajů k Intune.

2. V nabídce vlevo zvolte **Všechny služby** a do filtru textového pole pak zadejte **Intune**.

3. Zvolte **Intune** > **role** > **všechny role** > **přidat**.

4. V okně **Přidat vlastní roli** zadejte název a popis nové role a klikněte na **Oprávnění**.

5. V okně **Oprávnění** zvolte oprávnění, která chcete v této roli použít. Rozhodnout se, která oprávnění chcete použít, vám pomůže [tabulka Řízení správy na základě rolí s Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

6. Na **obor (značky)** okně zvolte značky, kde se budou aplikovat tuto vlastní roli.

7. Po dokončení vyberte **OK**.

7. V okně **Přidat vlastní roli** klikněte na **Vytvořit**. Nová role se zobrazí v seznamu na **role Intune – všechny role** okno.

### <a name="to-assign-a-custom-role"></a>Přiřazení vlastní role

Postupujte stejným způsobem jako [přiřazení předdefinované role](https://docs.microsoft.com/intune/role-based-access-control#to-assign-a-built-in-role) a vyberte vlastní roli.

## <a name="next-steps"></a>Další postup

[Použití role operátora helpdesku v Intune a portálu pro řešení potíží](help-desk-operators.md)

## <a name="see-also"></a>Viz také:

[Přiřazení rolí pomocí služby Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)
