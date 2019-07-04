---
title: Vytvoření zásad dodržování předpisů pro ochranu zařízení před mobilními hrozbami (MTD) v Microsoft Intune
titleSuffix: Microsoft Intune
description: Vytvořte zásady dodržování předpisů zařízením v Intune, které využívají úrovně hrozby partnerů MTD k určení, jestli má mobilní zařízení přístup k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2315136fe277f06f6dbb11c13139a9dc193ce6f7
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2019
ms.locfileid: "67549372"
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>Vytvoření zásad dodržování předpisů pro ochranu zařízení před mobilními hrozbami (MTD) v Intune

> [!NOTE] 
> Tyto informace se týkají všech partnerů ochrany před mobilními hrozbami.

Intune s MTD vám pomůže odhalit hrozby a posoudit rizika u mobilních zařízení. Můžete vytvořit pravidlo zásad dodržování předpisů zařízení služby Intune, které posuzuje rizika a zjišťuje, jestli zařízení předpisy dodržuje, nebo ne. Pak můžete použít [zásady podmíněného přístupu](create-conditional-access-intune.md) a zablokovat přístup ke službám podle toho, nakolik zařízení.

## <a name="before-you-begin"></a>Před zahájením

V rámci nastavení ochrany před mobilními hrozbami (MTD) jste v konzole partnera MTD vytvořili zásadu, která klasifikuje různé hrozby jako vysoké, střední nebo nízké. V zásadách dodržování předpisů zařízením služby Intune je teď potřeba nastavit úroveň ochrany zařízení před mobilními hrozbami.

Předpoklady zásad dodržování předpisů zařízením pro MTD:

- Nastavení integrace MTD se službou Intune

## <a name="to-create-an-mtd-device-compliance-policy"></a>Vytvoření zásad dodržování předpisů zařízením pro MTD

1. Přejděte na portál [Azure Portal](https://portal.azure.com/) a přihlaste se pomocí svých přihlašovacích údajů k Intune.

2. Na **Řídicím panelu Azure** zvolte v nabídce vlevo **Všechny služby** a potom do filtru textového pole zadejte **Intune**.

3. Zvolte **Intune** a zobrazí se **řídicí panel Intune**.

4. Na **řídicím panelu Intune** zvolte **Dodržování předpisů zařízením** a potom v části **Zásady** zvolte **Mobile Threat Defense**.

5. Zvolte **Vytvořit zásadu**, zadejte **Název** a **Popis** dodržování předpisů zařízením a vyberte **Platformu**. Potom zvolte **Konfigurovat** v části **Nastavení**.

6. V podokně **zásad dodržování předpisů** zvolte **Stav zařízení**.

7. V podokně **Stav zařízení** vyberte v části **Vyžadovat, aby zařízení bylo na určité úrovni hrozby pro zařízení nebo pod ní** z rozevíracího seznamu úroveň mobilní hrozby.

    a.  **Zabezpečené**: Tato úroveň je nejbezpečnější úroveň. Zařízení nemůže přistupovat k prostředkům společnosti, pokud je vystavené nějakým hrozbám. Pokud se najde jakákoli hrozba, zařízení se vyhodnotí jako nevyhovující.

    b.  **Nízká**: Zařízení splňuje předpisy, pokud jen hrozby nízké úrovně jsou k dispozici. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.

    c.  **Střední**: Zařízení splňuje předpisy, pokud jsou hrozby pohybují na střední nebo nízké úrovni. Pokud se v zařízení zjistí hrozby vysoké úrovně, vyhodnotí se jako nevyhovující.

    d.  **Vysoká**: Tato úroveň je nejméně bezpečná. Tato možnost povoluje všechny úrovně hrozeb, protože používá ochranu před mobilními hrozbami jenom ke generování sestav. Při tomto nastavení musejí mít zařízení aplikaci pro ochranu před mobilními hrozbami aktivovanou.

8. Dvakrát klikněte na **OK** a potom zvolte **Vytvořit**.

> [!IMPORTANT]
> Pokud vytvoříte zásady podmíněného přístupu pro Office 365 nebo jiné služby, je použit k vyhodnocení vyhodnocení dodržování předpisů zařízením a nedodržující předpisy zařízením se zablokuje přístup k podnikovým prostředkům, dokud se hrozby nevyřeší v zařízení.

## <a name="to-assign-an-mtd-device-compliance-policy"></a>Přiřazení zásad dodržování předpisů zařízením pro MTD

Pokud chcete přiřadit zásady dodržování předpisů zařízením uživatelům, vyberte zásady, které jste už nakonfigurovali. Existující zásady najdete v podokně **Dodržování předpisů zařízením – Zásady**.

1. Vyberte zásady, které chcete přiřadit uživatelům, a zvolte **Přiřazení**. Tato akce otevře podokno, kde můžete vybrat **skupiny zabezpečení Azure Active Directory** a přiřadit je k zásadám.

2. Zvolte **Vybrat skupiny, které se zahrnou** a otevřete tak podokno, ve kterém se zobrazí skupiny zabezpečení v Azure AD.  Po zvolení možnosti **Vybrat** se zásady nasadí u uživatelů.

    > [!NOTE] 
    > Tím jste zásady uplatnili u uživatelů. U zařízení používaných uživateli, na které zásady cílí, se vyhodnotí dodržování předpisů.

## <a name="next-steps"></a>Další postup

- [Povolení MTD v Intune](mtd-connector-enable.md)
