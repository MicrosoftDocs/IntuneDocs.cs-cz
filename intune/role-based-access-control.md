---
title: Řízení přístupu na základě role v Microsoft Intune
description: Přečtěte si, jak vám řízení přístupu na základě role (RBAC) umožňuje řídit, kdo může provádět akce a změny v Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/27/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 287e644e50b1f6b41f404cfd2102a8efc0fbaad9
ms.sourcegitcommit: 07528df71460589522a2e1b3e5f9ed63eb773eea
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34474560"
---
# <a name="role-based-administration-control-rbac-with-microsoft-intune"></a>Řízení správy na základě role (RBAC) v Microsoft Intune

Řízení správy na základě rolí pomáhá řídit, kdo může provádět různé úlohy Intune ve vaší organizaci a koho se tyto úlohy týkají. Můžete buď použít předdefinované role, které vyhovují běžným situacím v Intune, nebo si vytvořit své vlastní role. Roli definuje toto:

- **Definice role**: Název role, prostředky, které spravuje, a oprávnění udělená pro jednotlivé prostředky
- **Členové**: Skupiny uživatelů, kterým se přidělují oprávnění
- **Obor**: Skupiny uživatelů nebo zařízení, které můžou členové spravovat
- **Přiřazení**: Přiřazení role po nakonfigurování definice, členů a oboru

![Příklad řízení správy na základě rolí s Intune](./media/intune-rbac-1.PNG)

Na novém Azure Portalu poskytuje **Azure Active Directory (Azure AD)** dvě role adresáře, které je možné s Intune použít. Tyto role mají přidělena úplná oprávnění provádět v Intune všechny aktivity:

- **Globální správce:** Uživatelé s touto rolí mají přístup ke všem funkcím pro správu ve službě Azure AD a službám s federováním do služby Azure AD, jako je Exchange Online, SharePoint Online a Online Skype pro firmy. Osoba, která se zaregistruje k tenantovi Azure AD, se stane globálním správcem. Další role správců můžou přiřazovat jenom globální správci Azure AD. Organizace může mít víc globálních správců. Globální správci můžou resetovat heslo kteréhokoliv uživatele a všech ostatních správců.

- **Správce služby Intune:** Uživatelé s touto rolí mají globální oprávnění v rámci Intune, pokud se tato služba používá. Kromě všech nahrazujících omezení Azure umožňuje tato role také spravovat uživatele a zařízení a vytvářet a spravovat skupiny Intune.

- **Správce podmíněného přístupu:** Uživatelé s touto rolí mají oprávnění zobrazovat, vytvářet, měnit a odstraňovat zásady podmíněného přístupu.

    > [!IMPORTANT]
    > Role Správce služby Intune neumožňuje spravovat nastavení podmíněného přístupu k Azure AD.

    > [!TIP]
    > V Intune jsou také tři rozšíření Azure AD: **Uživatelé**, **Skupiny** a **Podmíněný přístup** řízená prostřednictvím Azure AD RBAC. **Správce uživatelských účtů** navíc provádí jenom aktivity uživatele nebo skupiny AAD a nemá úplná oprávnění provádět všechny aktivity v Intune. Další detaily naleznete v tématu [Řízení správy na základě rolí s Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles).

## <a name="roles-created-in-the-intune-classic-portal"></a>Role vytvořené na klasickém portálu Intune

Z klasického portálu Intune se do Intune na Azure Portalu migrují jenom **správci služeb** Intune s úplnými oprávněními. **Správce služeb** v Intune s přístupem jen pro čtení nebo helpdesk je nutné odebrat z klasického portálu a znovu jim přiřadit role v Intune na portálu Azure.

> [!IMPORTANT]
> Pokud budou vaši správci dál potřebovat přístup ke správě počítačů pomocí Intune, bude nutné zachovat přístup Správce služby Intune na klasickém portálu.

## <a name="built-in-roles"></a>Předdefinované role

Následující role jsou integrované do Intune a můžete je přiřadit ke skupinám, aniž byste dál měnili jejich konfiguraci:

- **Operátor helpdesku**: Provádí vzdálené úlohy u uživatelů a zařízení a může uživatelům a zařízením přiřazovat aplikace nebo zásady.
- **Správce zásad a profilů**: Spravuje zásady dodržování předpisů, konfigurační profily, registrace Apple a identifikátory podnikových zařízení.
- **Operátor s oprávněními pouze ke čtení**: Zobrazuje informace o uživatelích, zařízeních, registraci, konfiguraci a aplikacích. Nemůže provádět změny v Intune.
- **Správce aplikací**: Spravuje mobilní a spravované aplikace, může číst informace o zařízeních a zobrazit konfigurační profily zařízení.
- **Správce role Intune**: Spravuje vlastní role Intune a přidává přiřazení pro předdefinované role Intune. Toto je jediná role Intune, která smí přiřazovat oprávnění správcům.
- **Správce školy**: Spravuje zařízení s Windows 10 v [Intune for Education](introduction-intune-education.md) a může provádět následující akce: 

|Oprávnění|Operace|
|---|---|
|Data auditu|Číst|
|Konfigurace zařízení|Přiřadit, vytvořit, odstranit, číst, aktualizovat|
|Správci registrace zařízení|Číst, aktualizovat|
|Spravovaná zařízení|Číst, aktualizovat<!--, Delete [To be added in 1803]-->|
|Mobilní aplikace|Přiřadit, vytvořit, odstranit, číst, aktualizovat|
|sestavy|Číst|
|Vzdálené akce|Vyčistit počítač, restartovat, vzdáleně uzamknout, vyřadit, synchronizovat zařízení, vymazat|
|Organizace|Číst|

### <a name="to-assign-a-built-in-role"></a>Přiřazení předdefinované role

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** vyberte **Role Intune** a pak **Všechny role**.
1. V podokně **Role Intune – Všechny role** zvolte předdefinovanou roli, kterou chcete přiřadit.

2. V podokně <*název role*> – **Přehled** zvolte **Spravovat** a pak **Přiřazení**.

    > [!NOTE]
    > Předdefinované role není možné odstranit ani upravit.

3. V podokně vlastní role zvolte **Přiřadit**.

4. V podokně **Přiřazení rolí** zadejte **Název** a volitelný **Popis** přiřazení a pak zvolte následující:
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

2. V nabídce vlevo zvolte **Všechny služby** a do filtru textového pole pak zadejte **Intune**.

3. Zvolte **Intune**. Na řídicím panelu Intune, který se otevře, zvolte **Role Intune**.

4. V podokně **Role Intune** zvolte **Všechny role** a pak **Přidat vlastní**.

5. V podokně **Přidat vlastní roli** zadejte název a popis nové role a klikněte na **Oprávnění**.

3. V podokně **Oprávnění** zvolte oprávnění, která chcete v této roli použít. Rozhodnout se, která oprávnění chcete použít, vám pomůže [tabulka Řízení správy na základě rolí s Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

4. Když jste hotovi, klikněte na **OK**.

5. V podokně **Přidat vlastní roli** klikněte na **Vytvořit**. Nová role se zobrazí v seznamu v podokně **Role Intune – Všechny role**.

### <a name="to-assign-a-custom-role"></a>Přiřazení vlastní role

1. V podokně **Role Intune – Všechny role** zvolte vlastní roli, kterou chcete přiřadit.

2. V podokně <*název role*> – **Přehled** zvolte **Spravovat** a pak **Přiřazení**. V tomto podokně můžete také existující role upravovat nebo odstraňovat.

3. V podokně vlastní role zvolte **Přiřadit**.

4. V podokně **Přiřazení rolí** zadejte **Název** a volitelný **Popis** přiřazení a pak zvolte následující:
    - **Členové** – Vyberte skupinu, která obsahuje uživatele, kterému chcete udělit oprávnění.
    - **Obor** – Vyberte skupinu, která obsahuje uživatele, které člen výše bude moct spravovat.
<br></br>
5. Po dokončení klikněte na **OK**. Nové přiřazení se zobrazí v seznamu přiřazení.

## <a name="next-steps"></a>Další kroky

[Použití role operátora helpdesku v Intune a portálu pro řešení potíží](help-desk-operators.md)

## <a name="see-also"></a>Viz taky

[Přiřazení rolí pomocí služby Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)
