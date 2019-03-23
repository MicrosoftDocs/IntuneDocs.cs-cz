---
title: Filtrování zásad pomocí značek oboru v Microsoft Intune – Azure | Microsoft Docs
description: Pomocí značek oboru můžete filtrovat konfigurační profily pro konkrétní role.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2ceba92a48f4ae899b5a645137ec0891a7c16659
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394830"
---
# <a name="use-rbac-and-scope-tags-for-distributed-it"></a>Použití značek RBAC a obor pro distribuované IT

Abyste měli jistotu, že správné Správci mají správný přístup a viditelnost pro správné objekty Intune můžete použít řízení přístupu na základě role (RBAC) a značky oboru. Role určují, jaký přístup do objektů, které mají správci. Značky oboru určit, které objekty se správcům zobrazí.

Například Řekněme, že správce regionální pobočky Seattle má přiřazenou roli správce zásad a profilů. Chcete, aby tento správce zobrazit a spravovat profily a zásady, které se vztahují jenom na zařízení Seattle. Proto byste:

1. Vytvořte značku oboru názvem Seattle.
2. Vytvořte přiřazení role pro roli správce zásad a profilů pomocí: 
    - Členové (skupiny) = skupinu zabezpečení s názvem správcům Seattle IT. Všichni správci v této skupině budou mít oprávnění ke správě zásad a profilů pro uživatele nebo zařízení v rozsah (skupiny).
    - Rozsah (skupiny) = bezpečnostní skupiny s názvem Seattle uživatelů. Všechny uživatele nebo zařízení v této skupině mají jejich profily a zásady, které spravuje správce ve členy (skupiny). 
    - Obor (značky) = Seattle. Správci v členu (skupiny) můžete zobrazit zařízení, které také obsahovat značku oboru Seattle.
3. Přidáte značku oboru Seattle zásady a profily, které chcete, aby správci v členy (skupiny), bude mít přístup.
4. Přidáte značku oboru Seattle do zařízení, která chcete viditelné pro správce v členy (skupiny). 


## <a name="to-create-a-scope-tag"></a>Vytvoření značky oboru

1. V Intune, zvolte **role** > **obor (značky)** > **vytvořit**.

    ![Snímek obrazovky vytvořit značku oboru.](./media/scope-tags/create-scope-tag.png)

2. Zadejte **Název** a **Popis**.
3. Zvolte **Vytvořit**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Přiřazení značky oboru k roli

1. V Intune, zvolte **role** > **všechny role** > vyberte roli > **přiřazení** > **přiřadit**.

    ![Snímek obrazovky přiřazení k roli oboru.](./media/scope-tags/assign-scope-to-role.png)

2. Poskytují **název přiřazení** a **popis**.
3. Zvolte **členy (skupiny)** > **přidat** > vyberte skupiny, které chcete, aby jako součást tohoto přiřazení > **vyberte**  >   **OK**. mUsers do této skupiny mají oprávnění ke správě zásad a profilů pro uživatele nebo zařízení v rozsah (skupiny).

    ![Snímek obrazovky vyberte člena skupiny.](./media/scope-tags/select-member-groups.png)

4. Pokud chcete ke správě uživatelů a zařízení v konkrétní sadu skupin, zvolte **rozsah (skupiny)** > **vybrané skupiny** > **vybrat skupiny, které chcete zahrnout**> zvolte skupiny > **vyberte** > **OK**. Všechny uživatele nebo zařízení v této skupině mají jejich profily a zásady, které spravuje správce ve členy (skupiny).

    ![Snímek obrazovky vyberte oboru skupiny.](./media/scope-tags/select-scope-groups.png)

    Alternativně můžete zvolit **všechna zařízení**, **všichni uživatelé**, nebo **všichni uživatelé a všechna zařízení**.

    ![Snímek obrazovky s další možnosti pro výběr oboru skupiny.](./media/scope-tags/scope-group-other-options.png)
    
5. Zvolte **obor (značky)** > **přidat** > zvolte značky, které chcete přidat do této role > **vyberte** > **OK**. Uživatelé v členy (skupiny) bude mít přístup k zásady a profily, které mají stejnou značku oboru.

    ![Snímek obrazovky s tagy vyberte obor.](./media/scope-tags/select-scope-tags.png)

6. Zvolte **OK**. 

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Přidaní značky oboru do konfiguračního profilu
1. V Intune, zvolte **konfigurace zařízení** > **profily** > zvolte profil.

    ![Snímek obrazovky vyberte profil.](./media/scope-tags/choose-profile.png)

2. Zvolte **vlastnosti** > **obor (značky)** > **přidat**.

    ![Snímek obrazovky přidání značky oboru.](./media/scope-tags/add-scope-tags.png)

3. V části **vyberte značky**, zvolte značky, které chcete přidat do profilu.
4. Zvolte **vyberte** > **OK** > **Uložit**.

## <a name="to-assign-a-scope-tag-to-an-app-configuration-policy"></a>Přiřadit značky oboru zásady Konfigurace aplikací
Pro zařízení s **typ registrace zařízení** nastavena na **spravovaných zařízeních**, zvolte **klientské aplikace** > **zásady Konfigurace aplikací** > zvolte zásady Konfigurace aplikací > **vlastnosti** > **obor (značky)** > zvolte značky, které chcete přiřadit k zásadám.

Pro zařízení s **typ registrace zařízení** nastavena na **spravované aplikace**, zvolte **klientské aplikace** > **zásady Konfigurace aplikací**> zvolte zásady Konfigurace aplikací > **obor (značky)** > zvolte značky, které chcete přiřadit k zásadám.


## <a name="to-assign-a-scope-tag-to-an-ios-app-provisioning-profile"></a>Přiřadit značky oboru zřizovací profil aplikace pro iOS
1. V Intune, zvolte **klientské aplikace** > **zřizovací profily aplikací pro iOS** > zvolte profil.
2. Zvolte **vlastnosti** > **obor (značky)** > zvolte značky, které chcete přiřadit k profilu.
3. Zvolte **vyberte** > **OK** > **Uložit**.

## <a name="scope-tag-details"></a>Podrobnosti značky oboru
Při práci s značky oboru, mějte na paměti následující informace:

- Nyní můžete přiřadit značky oboru na:
    - Přiřazení rolí
    - Zásady dodržování předpisů pro zařízení
    - Konfigurační profily zařízení
    - Aktualizuje aktualizační kanály Windows 10
    - Spravovaná zařízení
    - Aplikace
    - Zásady Konfigurace aplikací – spravovaná zařízení
    - Skripty prostředí PowerShell
    - Tokeny DEP
- Když správce vytvoří objekt v Intune, všechny značky oboru přiřazeno, kterou správce se automaticky přiřadí nový objekt.
- RBAC v Intune se nevztahuje k rolím Azure Active Directory. Tedy role Správci služby Intune a globální Správci mají přístup správce k Intune bez ohledu na to, co značky oboru mají.
- Správci v přiřazení role pomocí značky oboru můžete také zobrazit objekty Intune se žádné značky oboru.
- Pouze můžete přiřadit značky oboru, který máte v přiřazení role.
- Můžete pouze cílové skupiny, které jsou uvedeny v oboru přiřazení role (skupiny).
- Pokud máte značka oboru přiřazené pro vaši roli nelze odstranit všechny značky oboru objektu Intune. Vyžaduje se aspoň jeden obor značky.
- Pokud má uživatel více přiřazení role, oprávnění v těchto přiřazení rolí následujícím způsobem rozšířit na různé objekty:
    - Přiřazení oprávnění se vztahují jenom na objekty (třeba zásady nebo aplikace) v této roli přiřazení rozsah (skupiny). Přiřazení oprávnění se nevztahují na objekty v jiných přiřazení rolí není-li toto přiřazení je explicitně neudělí.
    - Pro všechny objekty stejného typu (stejně jako všechny zásady nebo všechny aplikace) se vztahují další oprávnění (jako je například vytvoření a čtení), v některém z přiřazení uživatele.
    - Oprávnění pro objekty různé typy (třeba zásady nebo aplikace), nemůžete použít k sobě navzájem. Oprávnění ke čtení pro zásady, například, neposkytuje oprávnění pro čtení k aplikacím v přiřazení uživatele.





## <a name="next-steps"></a>Další postup

Spravujte [role](role-based-access-control.md) a [profily](device-profile-assign.md).
