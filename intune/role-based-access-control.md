---
title: "Řízení správy na základě rolí s Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Informace o tom, jak RBAC umožňuje určovat, kdo může provádět akce a změny."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3aff61f6201d6569e35aa9d556aa655d28775d2f
ms.sourcegitcommit: 18cdbdc226f64368de892a8c5cff157c37986c57
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/03/2017
---
# <a name="role-based-administration-control-rbac-with-intune"></a>Řízení správy na základě rolí (RBAC) s Intune

Řízení správy na základě rolí pomáhá řídit, kdo může provádět různé úlohy Intune ve vaší organizaci a koho se tyto úlohy týkají. Můžete buď použít předdefinované role, které vyhovují běžným situacím v Intune, nebo si vytvořit své vlastní role. Roli definuje toto:

- **Definice role**: Název role, prostředky, které spravuje, a oprávnění udělená pro jednotlivé prostředky
- **Členové**: Skupiny uživatelů, kterým se přidělují oprávnění
- **Obor**: Skupiny uživatelů nebo zařízení, které můžou členové spravovat
- **Přiřazení**: Přiřazení role po nakonfigurování definice, členů a oboru

![Příklad řízení správy na základě rolí s Intune](./media/intune-rbac-1.PNG)

Počínaje novým portálem Intune poskytuje **Azure Active Directory (Azure AD)** dvě role adresáře, které je možné s Intune použít. Tyto role mají přidělena úplná oprávnění provádět v Intune všechny aktivity:

- **Globální správce:** Uživatelé s touto rolí mají přístup ke všem funkcím pro správu ve službě Azure AD a službám s federováním do služby Azure AD, jako je Exchange Online, SharePoint Online a Online Skype pro firmy. Osoba, která se zaregistruje k tenantovi Azure AD, se stane globálním správcem. Další role správců můžou přiřazovat jenom globální správci Azure AD. Organizace může mít víc globálních správců. Globální správci můžou resetovat heslo kteréhokoliv uživatele a všech ostatních správců.

- **Správce služby Intune:** Uživatelé s touto rolí mají globální oprávnění v rámci Intune, pokud se tato služba používá. Kromě toho tato role umožňuje spravovat uživatele, zařízení a vytvářet a spravovat skupiny.

- **Správce podmíněného přístupu:** Uživatelé s touto rolí mají oprávnění zobrazovat, vytvářet, měnit a odstraňovat zásady podmíněného přístupu.

    > [!IMPORTANT]
    > Role Správce služby Intune neumožňuje spravovat nastavení podmíněného přístupu k Azure AD.

    > [!TIP]
    > V Intune jsou také tři rozšíření Azure AD: **Uživatelé**, **Skupiny** a **Podmíněný přístup** řízená prostřednictvím Azure AD RBAC. **Správce uživatelských účtů** navíc provádí jenom aktivity uživatele nebo skupiny AAD a nemá úplná oprávnění provádět všechny aktivity v Intune. Další detaily naleznete v tématu [Řízení správy na základě rolí s Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles).

## <a name="roles-created-in-the-intune-classic-console"></a>Role vytvořené v klasické konzole Intune

Z klasické konzoly Intune do Intune v Azure se migrují jenom **správci služeb** Intune s úplnými oprávněními. **Správce služeb** v Intune s přístupem jen pro čtení nebo helpdesk je nutné odebrat z klasického portálu a znovu jim přiřadit role v Intune na portálu Azure.

> [!IMPORTANT]
> Pokud budou vaši správci dál potřebovat přístup ke správě počítačů pomocí Intune, bude nutné zachovat přístup Správce služby Intune na klasické konzole.

## <a name="built-in-roles"></a>Předdefinované role

Následující role jsou integrované do Intune a můžete je přiřadit ke skupinám, aniž byste dál měnili jejich konfiguraci:

- **Operátor helpdesku**: Provádí vzdálené úlohy u uživatelů a zařízení a může uživatelům a zařízením přiřazovat aplikace nebo zásady.
- **Správce zásad a profilů**: Spravuje zásady dodržování předpisů, konfigurační profily, registrace Apple a identifikátory podnikových zařízení.
- **Operátor s oprávněními pouze ke čtení**: Zobrazuje informace o uživatelích, zařízeních, registraci, konfiguraci a aplikacích. Nemůže provádět změny v Intune.
- **Správce aplikací**: Spravuje mobilní a spravované aplikace a může číst informace o zařízeních.

### <a name="to-assign-a-built-in-role"></a>Přiřazení předdefinované role

1. V části **Role Intune** zvolte předdefinovanou roli, kterou chcete přiřadit.

2. V okně <*název role*> – **Vlastnosti** zvolte **Spravovat**, **Přiřazení**.

    > [!NOTE]
    > Předdefinované role není možné odstranit ani upravit.

3. V okně vlastní role zvolte **Přiřadit**.

4. V okně **Přiřazení rolí** zadejte **Název** a volitelný **Popis** přiřazení a zvolte následující:
    - **Členové** – Vyberte skupinu, která obsahuje uživatele, kterému chcete udělit oprávnění.
    - **Obor** – Vyberte skupinu, která obsahuje uživatele, které člen výše bude moct spravovat.
<br></br>
5. Po dokončení klikněte na **OK**. Nové přiřazení se zobrazí v seznamu přiřazení.

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

2. V nabídce vlevo zvolte **Další služby** a do filtru textového pole pak zadejte **Intune**.

3. Zvolte **Intune**. Na řídicím panelu Intune, který se otevře, zvolte **Role Intune**.

4. V okně **Role Intune** zvolte **Role Intune** a potom **Přidat vlastní**.

5. V okně **Přidat vlastní roli** zadejte název a popis nové role a klikněte na **Oprávnění**.

3. V okně **Oprávnění** zvolte oprávnění, která chcete v této roli použít. Rozhodnout se, která oprávnění chcete použít, vám pomůže [tabulka Řízení správy na základě rolí s Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

4. Když jste hotovi, klikněte na **OK**.

5. V okně **Přidat vlastní roli** klikněte na **Vytvořit**. Nová role se zobrazí v seznamu v okně **Role Intune**.

### <a name="to-assign-a-custom-role"></a>Přiřazení vlastní role

1. V části **Role Intune** zvolte vlastní roli, kterou chcete přiřadit.

2. V okně <*název role*> – **Vlastnosti** zvolte **Spravovat**, **Přiřazení**. V tomto okně můžete navíc upravovat nebo odstraňovat existující role.

3. V okně vlastní role zvolte **Přiřadit**.

4. V okně **Přiřazení rolí** zadejte **Název** a volitelný **Popis** přiřazení a zvolte následující:
    - **Členové** – Vyberte skupinu, která obsahuje uživatele, kterému chcete udělit oprávnění.
    - **Obor** – Vyberte skupinu, která obsahuje uživatele, které člen výše bude moct spravovat.
<br></br>
5. Po dokončení klikněte na **OK**. Nové přiřazení se zobrazí v seznamu přiřazení.

## <a name="next-steps"></a>Další kroky

[Použití role operátora helpdesku v Intune a portálu pro řešení potíží](help-desk-operators.md)

## <a name="see-also"></a>Související témata

[Přiřazení rolí pomocí služby Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)
