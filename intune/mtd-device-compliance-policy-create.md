---
title: "Vytvoření zásad dodržování předpisů pro ochranu zařízení před mobilními hrozbami v Intune"
titleSuffix: Intune on Azure
description: "Vytvoření zásad dodržování předpisů pro ochranu zařízení před mobilními hrozbami v Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1354d3170f007af2a4bf7f5b2f233a186175c621
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>Vytvoření zásad dodržování předpisů pro ochranu zařízení před mobilními hrozbami (MTD) v Intune

Intune s MTD vám pomůže odhalit hrozby a posoudit rizika u mobilních zařízení. Můžete vytvořit pravidlo zásad dodržování předpisů zařízení služby Intune, které posuzuje rizika a zjišťuje, jestli zařízení předpisy dodržuje, nebo ne. Pomocí zásad podmíněného přístupu pak můžete zablokovat přístup ke službám podle toho, jestli zařízení dodržuje předpisy.

## <a name="before-you-begin"></a>Před zahájením

V rámci nastavení ochrany před mobilními hrozbami (MTD) jste v konzole partnera MTD vytvořili zásadu, která klasifikuje různé hrozby jako vysoké, střední nebo nízké. V zásadách dodržování předpisů zařízením služby Intune je teď potřeba nastavit úroveň ochrany zařízení před mobilními hrozbami.

Předpoklady zásad dodržování předpisů zařízením pro MTD:

-   Nastavení integrace MTD se službou Intune

-   Povolení konektoru MTD v Intune

## <a name="to-create-a-mtd-device-compliance-policy"></a>Vytvoření zásad dodržování předpisů zařízením pro MTD

1.  Přejděte na portál [Azure Portal](https://portal.azure.com/) a přihlaste se pomocí svých přihlašovacích údajů k Intune.

2.  Na **řídicím panelu Azure** zvolte v nabídce vlevo **Další služby** a do filtru textového pole zadejte **Intune**.

3.  Zvolte **Intune** a zobrazí se **řídicí panel Intune**.

4. Na **řídicím panelu Intune** zvolte **Dodržování předpisů zařízením** a potom v části **Zásady** zvolte **Mobile Threat Defense**.

5.  Zvolte **Vytvořit zásadu**, zadejte **Název** a **Popis** dodržování předpisů zařízením a vyberte **Platformu**. Potom zvolte **Konfigurovat** v části **Nastavení**.

6.  V okně **zásady dodržování předpisů** zvolte **Stav zařízení**.

7.  V okně **Stav zařízení** vyberte z rozevíracího seznamu **Vyžadovat, aby zařízení bylo na určité úrovni mobilních hrozeb nebo pod ní**.

    a.  **Zabezpečeno:** Toto je nejbezpečnější úroveň. Zařízení nemůže přistupovat k prostředkům společnosti, pokud je vystavené nějakým hrozbám. Pokud se najde jakákoli hrozba, zařízení se vyhodnotí jako nevyhovující.

    b.  **Nízká:** Zařízení se vyhodnotí jako vyhovující i v případě, že se v něm nachází jenom hrozby nízké úrovně. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.

    c.  **Střední:** Zařízení vyhovuje, pokud se v něm přítomné hrozby pohybují na střední nebo nízké úrovni. Pokud budou v zařízení zjištěny hrozby vysoké úrovně, bude vyhodnoceno jako nevyhovující.

    d.  **Vysoká**: Jedná se o nejméně bezpečnou možnost. Tato možnost povoluje všechny úrovně hrozeb, protože používá ochranu před mobilními hrozbami Skycure jenom ke generování sestav.

8.  Dvakrát klikněte na **OK** a potom zvolte **Vytvořit**.

> [!IMPORTANT]
> Pokud vytvoříte zásady podmíněného přístupu pro Office 365 nebo jiné služby, posoudí se toto vyhodnocení dodržování předpisů zařízením. Nevyhovujícím zařízením se zablokuje přístup k prostředkům společnosti, dokud se hrozby v zařízení nevyřeší.

## <a name="to-assign-a-mtd-device-compliance-policy"></a>Přiřazení zásad dodržování předpisů zařízením pro MTD

Pokud chcete přiřadit zásady dodržování předpisů zařízením uživatelům, vyberte zásady, které jste už nakonfigurovali. Existující zásady najdete v okně **Zásady dodržování předpisů zařízením**.

1. Vyberte zásady, které chcete přiřadit uživatelům, a zvolte **Přiřazení**. Otevře se okno, kde můžete vybrat **skupiny zabezpečení Azure Active Directory** a přiřadit je k zásadám.

2. Zvolte **Vybrat skupiny** a otevřete tak okno, ve kterém se zobrazí skupiny zabezpečení v Azure AD.  Po zvolení možnosti **Vybrat** se zásady nasadí u uživatelů.

    > [!NOTE] 
    > Zásady jsou teď použité u uživatelů. U zařízení používaných uživateli, kteří jsou cílem zásad, se bude vyhodnocovat dodržování předpisů.