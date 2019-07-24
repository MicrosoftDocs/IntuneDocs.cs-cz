---
title: Filtrování zásad pomocí značek oboru v Microsoft Intune – Azure | Microsoft Docs
description: Pomocí značek oboru můžete filtrovat konfigurační profily pro konkrétní role.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2019
ms.topic: article
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 627899eafb2175b2d3034045bd765a10f4a203d6
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "67882492"
---
# <a name="use-role-based-access-control-rbac-and-scope-tags-for-distributed-it"></a>Použití řízení přístupu na základě role (RBAC) a značek oboru pro distribuci

Pomocí značek řízení přístupu založených na rolích a oborech můžete zajistit, aby měli oprávnění správce správný přístup a viditelnost správných objektů Intune. Role určují, kteří správci mají přístup k objektům. Značky oboru určují, které objekty můžou správci vidět.

Řekněme například, že je přiřazená role zásady a správce profilu v Seattlu pro regionálního správce. Chcete, aby tento správce mohl zobrazovat a spravovat pouze profily a zásady, které se vztahují pouze na zařízení v Seattlu. K tomu byste měli:

1. Vytvořte značku oboru s názvem Seattle.
2. Vytvořte přiřazení role pro roli Správce profilů a s těmito zásadami: 
    - Členové (skupiny) = skupina zabezpečení s názvem Praha IT Admins. Všichni správci v této skupině budou mít oprávnění ke správě zásad a profilů pro uživatele nebo zařízení v oboru (skupiny).
    - Scope (skupiny) = skupina zabezpečení s názvem uživatelé v Seattlu. Všichni uživatelé nebo zařízení v této skupině můžou mít svoje profily a zásady spravované správci v členech (skupinách). 
    - Scope (značky) = Seattle. Správci v členovi (skupinách) můžou vidět zařízení, která mají také značku oboru Seattle.
3. Přidejte značku oboru Seattle do zásad a profilů, ke kterým chcete, aby měli správci členové (skupiny) přístup.
4. Přidejte značku oboru Seattle do zařízení, která mají být viditelná pro správce v členech (skupinách). 


## <a name="to-create-a-scope-tag"></a>Vytvoření značky oboru

1. V Intune vyberte rozsah **rolí** >  **(značky)**  > **vytvořit**.

    ![Snímek obrazovky s vytvořením značky oboru](./media/scope-tags/create-scope-tag.png)

3. Pokud chcete, aby všechna zařízení byla v určitých skupinách, vyberte možnost **přiřadit značku oboru všem zařízením ve vybraných skupinách**.
    1. Na stránce **Vybrat skupiny, které se mají zahrnout** vyberte skupiny obsahující zařízení, kterým chcete přiřadit tuto značku oboru.
    2. Zvolte **Vybrat**.
4. Zvolte **Vytvořit**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Přiřazení značky oboru k roli

1. V Intune vyberte **role** > **všechny role** > vyberte **přiřazení** > rolí >**přiřazení**.

    ![Snímek obrazovky s přiřazením oboru k roli](./media/scope-tags/assign-scope-to-role.png)

2. Zadejte název a **Popis** **přiřazení** .
3. Zvolte **Členové (skupiny)**  > **Přidat** > vyberte skupiny, které chcete jako součást tohoto přiřazení > **Vyberte** > **OK**. mUsers v této skupině budou mít oprávnění ke správě zásad a profilů pro uživatele nebo zařízení v oboru (skupiny).

    ![Snímek obrazovky s vybranými skupinami členů](./media/scope-tags/select-member-groups.png)

4. Pokud chcete spravovat uživatele nebo zařízení v určité sadě skupin, zvolte **rozsah (skupiny)**  > **vybrané skupiny** > **Vybrat skupiny, které chcete zahrnout** > vyberte skupiny > **Vyberte** > **OK.** . Všichni uživatelé nebo zařízení v této skupině můžou mít svoje profily a zásady spravované správci v členech (skupině).

    ![Snímek obrazovky s vybranými skupinami oborů](./media/scope-tags/select-scope-groups.png)

    Alternativně můžete zvolit **všechna zařízení**, **Všichni uživatelé**nebo **Všichni uživatelé & všechna zařízení**.

    ![Snímek obrazovky s dalšími možnostmi pro vybrané skupiny oborů.](./media/scope-tags/scope-group-other-options.png)
    
5. Zvolte **rozsah (značky)**  > **Přidat** > vyberte značky, které chcete přidat do této role > **Vyberte** > **OK**. Uživatelé v členech (skupinách) budou mít přístup k zásadám a profilům, které mají také stejnou značku oboru.

    ![Snímek obrazovky s vybranými značkami oboru](./media/scope-tags/select-scope-tags.png)

6. Zvolte **OK**. 

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Přidaní značky oboru do konfiguračního profilu
1. V Intune vyberte**profily** **Konfigurace** > zařízení > zvolit profil.

    ![Snímek obrazovky s vybraným profilem](./media/scope-tags/choose-profile.png)

2. Vyberte **vlastnosti** > **obor (značky)**  > **Přidat**.

    ![Snímek obrazovky s přidáním značek oboru](./media/scope-tags/add-scope-tags.png)

3. V části **Vybrat značky**zvolte značky, které chcete přidat do profilu.
4. Zvolte **Vybrat** > okUložit > .

## <a name="to-assign-a-scope-tag-to-an-app-configuration-policy"></a>Přiřazení značky oboru k zásadě konfigurace aplikace
U zařízení s **typem registrace zařízení** nastaveným na **spravovaná zařízení**:
1. Vyberte **klientské aplikace** > **zásady konfigurace aplikace** > vyberte zásadu konfigurace aplikace.
2. Vyberte možnost obor **vlastností** >  **(značky)** > vyberte značky, které chcete zásadám přiřadit.

U zařízení s **typem registrace zařízení** nastaveným na **spravované aplikace**:
1. Vyberte **klientské aplikace** > **zásady konfigurace aplikace** > vyberte zásadu konfigurace aplikace.
2. Vyberte **rozsah (značky)** > vyberte značky, které chcete zásadám přiřadit.


## <a name="to-assign-a-scope-tag-to-an-ios-app-provisioning-profile"></a>Přiřazení značky oboru k zřizovacímu profilu aplikace pro iOS
1. V Intune vyberte pro **klientské aplikace** > **iOS profily zřizování aplikace** > vyberte profil.
2. Vyberte možnost rozsah **vlastností** >  **(značky)** > vyberte značky, které chcete přiřadit k profilu.
3. Zvolte **Vybrat** > okUložit > .

## <a name="to-assign-a-scope-tag-to-an-apple-volume-purchase-program-vpp-token"></a>Přiřazení značky oboru k tokenu Apple Volume Purchase Program (VPP)
1. V Intune vyberte **klientské aplikace** > tokeny programu**Apple VPP** > vyberte token VPP.
2. Vyberte **rozsah (značky)** > zvolte značky, které chcete přiřadit k profilu. Přiřazené značky dědí aplikace VPP a e-knihy přidružené k tokenu VPP.
3. Zvolte **Vybrat** > okUložit > .

## <a name="scope-tag-details"></a>Podrobnosti o značce oboru
Při práci s štítky oboru si pamatujte tyto podrobnosti:

- V současné době můžete přiřazovat značky oboru:
  - Přiřazení rolí
  - Zásady dodržování předpisů pro zařízení
  - Konfigurační profily zařízení
  - Aktualizační kanály Windows 10
  - Spravovaná zařízení
  - Aplikace
  - Zásady konfigurace aplikací – spravovaná zařízení
  - Powershellové skripty
  - Tokeny DEP
  - Zřizovací profil aplikace pro iOS
  - Tokeny programu Volume purchase program (VPP)
- Když správce vytvoří v Intune objekt, všechny značky oboru přiřazené tomuto správci se automaticky přiřadí k novému objektu.
- Pro role Azure Active Directory se nepoužívá nastavení RBAC pro Intune. Role Správci služby Intune a globální Správci proto mají úplný přístup správce k Intune bez ohledu na to, jaké obory mají.
- Správci v přiřazení role s značkami Scope můžou taky zobrazovat objekty Intune bez značek oboru.
- Můžete přiřadit pouze značku oboru, kterou máte v přiřazení role.
- Můžete cílit jenom na skupiny, které jsou uvedené v oboru (skupiny) přiřazení role.
- Pokud máte ke své roli přiřazenou značku oboru, nemůžete odstranit všechny značky oboru v objektu Intune. Vyžaduje se aspoň jedna značka oboru.

## <a name="next-steps"></a>Další postup

Spravujte [role](role-based-access-control.md) a [profily](device-profile-assign.md).
