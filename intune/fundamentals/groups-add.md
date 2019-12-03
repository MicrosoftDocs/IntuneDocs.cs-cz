---
title: Přidání skupin pro uspořádání uživatelů a zařízení
titleSuffix: Microsoft Intune
description: Přidejte skupiny pro uspořádání uživatelů a zařízení podle zeměpisné oblasti, oddělení a hardwarových zvláštností.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: altsou
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6e3219e32ef9bea838f0c19258d0b22a99083a12
ms.sourcegitcommit: 1a22b8b31424847d3c86590f00f56c5bc3de2eb5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2019
ms.locfileid: "74261585"
---
# <a name="add-groups-to-organize-users-and-devices"></a>Přidání skupin pro uspořádání uživatelů a zařízení

Intune používá ke správě zařízení a uživatelů skupiny Azure Active Directory (Azure AD). Jako správce Intune můžete nastavit skupiny tak, aby odpovídaly potřebám vaší organizace. Vytvořte skupiny, které uživatele nebo zařízení uspořádají podle zeměpisné polohy, oddělení nebo vlastností hardwaru. Skupiny použijte ke spravování úloh se škálováním. Můžete například nastavit zásady pro mnoho uživatelů nebo nasazovat aplikace do sady zařízení.

Můžete přidat následující typy skupin:

- **Přiřazené skupiny** – přidejte uživatele nebo zařízení do statické skupiny ručně. 
- **Dynamické skupiny** (vyžadují Azure AD Premium) – umožňuje automaticky přidat uživatele nebo zařízení do skupin uživatelů nebo skupin zařízení na základě vámi vytvořeného výrazu.

  Když se například přidá uživatel s názvem manažera, uživatel se automaticky přidá do skupiny **všichni správci** . Nebo pokud má zařízení typ operačního systému zařízení s iOS, zařízení se automaticky přidá do skupiny všechna zařízení s **iOS** .

## <a name="add-a-new-group"></a>Přidání nové skupiny

Pomocí následujícího postupu vytvořte novou skupinu.

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vyberte **skupiny** > **Nová skupina**:

   ![Snímek obrazovky Azure Portal s vybranou novou skupinou](./media/groups-add/groups-add-new.png)

3. V poli **typ skupiny**vyberte jednu z následujících možností:

    - **Zabezpečení**: skupiny zabezpečení definují, kdo má přístup k prostředkům a jsou doporučováni pro skupiny v Intune. Můžete například vytvořit skupiny pro uživatele, jako jsou **Všichni Charlotte zaměstnanci** nebo **Všichni ženy ve společnosti Contoso**. Nebo můžete vytvořit skupiny pro zařízení, například **všechna zařízení** se systémem iOS nebo **všechna zařízení s Windows 10 pro studenty**.

        > [!TIP]
        > Vytvořené uživatele a skupiny lze také zobrazit v [centru pro správu Microsoft 365](https://admin.microsoft.com), v centru pro správu Azure Active Directory a [Microsoft Intune v Azure Portal](https://go.microsoft.com/fwlink/?linkid=2090973). V tenantovi vaší organizace můžete vytvářet a spravovat skupiny ve všech těchto oblastech.
        >
        > Pokud je vaše primární role správou zařízení, doporučujeme použít Centrum pro [správu Microsoft Endpoint Manageru](https://go.microsoft.com/fwlink/?linkid=2109431).

    - **Office 365**: tyto skupiny jsou navržené pro řízení přístupu a sdílení prostředků Office 365. Můžete například vytvořit skupinu Office 365 pro sdílení doručené pošty nebo kalendáře aplikace Outlook. Další informace najdete v tématu [informace o skupinách Office 365](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

4. Zadejte **název skupiny** a **Popis skupiny** pro novou skupinu. Musí být specifické a zahrnovat informace, aby ostatní věděli, pro které skupiny jsou.

    Zadejte například **všechna zařízení s Windows 10 Students** pro název skupiny a **všechna zařízení s Windows 10 používaná studenty ve společnosti Contoso úrovně High School 9-12** pro popis skupiny.

5. Zadejte **typ členství**. Možnosti:

    - **Přiřazeno**: Správci ručně přiřazují uživatele nebo zařízení do této skupiny a ručně odeberou uživatele nebo zařízení.
    - **Dynamický uživatel**: Správci vytvářejí pravidla členství pro automatické přidávání a odebírání členů.
    - **Dynamické zařízení**: Správci vytvářejí pravidla dynamické skupiny k automatickému přidávání a odebírání zařízení.

        ![Snímek obrazovky s vlastnostmi skupiny v Intune](./media/groups-add/groups-add-properties.png)

    Další informace o těchto typech členství a vytváření dynamických výrazů naleznete v tématu:

    - [Vytvoření základní skupiny a přidání členů pomocí Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    - [Pravidla dynamického členství pro skupiny v Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)

    > [!NOTE]
    > V tomto centru pro správu se při vytváření uživatelů nebo skupin nemusí zobrazovat značka **Azure Active Directory** . Ale to je to, co právě používáte.

6. Novou skupinu přidáte tlačítkem **Vytvořit**. Vaše skupina se zobrazí v seznamu.

> [!TIP]
> Vezměte v úvahu některé z ostatních dynamických skupin uživatelů a zařízení, které můžete vytvořit, například:
>
> - Všichni studenti ve společnosti Contoso High School
> - Všechna zařízení s Androidem Enterprise
> - Všechna zařízení se systémem iOS 11 a starším
> - Marketing
> - Personální oddělení
> - Všichni zaměstnanci Charlotte
> - Všichni zaměstnanci v WA

## <a name="groups-and-policies"></a>Skupiny a zásady

Přístup k prostředkům vaší organizace se řídí uživateli a skupinami, které vytvoříte.

Při vytváření skupin Vezměte v úvahu, jak budete uplatňovat [zásady dodržování předpisů](../protect/device-compliance-get-started.md) a [konfigurační profily](../configuration/device-profiles.md). Můžete mít například:

- Zásady, které jsou specifické pro operační systém zařízení.
- Zásady, které jsou specifické pro různé role ve vaší organizaci.
- Zásady, které jsou specifické pro organizační jednotky, které jste definovali ve službě Active Directory.

Pokud chcete vytvořit základní požadavky vaší organizace na dodržování předpisů, můžete vytvořit výchozí zásadu, která bude platit pro všechny skupiny a zařízení. Pak vytvořte konkrétnější zásady pro nejširší kategorie uživatelů a zařízení. Můžete například vytvořit zásady e-mailů pro každý operační systém zvlášť.

Doporučení a pokyny ke konfiguračnímu profilu najdete v tématu [přiřazení zásad ke skupinám uživatelů nebo skupinám zařízení](../configuration/device-profile-assign.md#user-groups-vs-device-groups) a [doporučením profilu](../configuration/device-profile-create.md#recommendations).

## <a name="see-also"></a>Viz taky

- [Řízení přístupu na základě role (RBAC) s Microsoft Intune](role-based-access-control.md)
- [Správa přístupu k prostředkům pomocí skupin Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)