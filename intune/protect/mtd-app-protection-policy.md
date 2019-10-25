---
title: Vytvoření zásad ochrany aplikací ochrany před mobilními hrozbami (MTD) v Intune
titleSuffix: Microsoft Intune
description: Vytvořte zásady ochrany aplikací ochrany před mobilními hrozbami (MTD) pomocí Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 15d986bc5017a44571c6194f9c6b53167b671349
ms.sourcegitcommit: 06a1fe83fd95c9773c011690e8520733e1c031e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2019
ms.locfileid: "72795309"
---
# <a name="create-mobile-threat-defense-app-protection-policy-with-intune"></a>Vytvoření zásad ochrany aplikací ochrany před mobilními hrozbami v Intune

> [!NOTE] 
> Tento článek se týká všech partnerů ochrany před mobilními hrozbami (MTD), které podporují zásady ochrany aplikací: lepší mobilní zařízení (Android), Zimperium (iOS), Lookout for Work (Android/iOS).

Intune s MTD vám pomůže odhalit hrozby a posoudit rizika u mobilních zařízení. Můžete vytvořit zásady ochrany aplikací Intune, které posuzují riziko, abyste zjistili, jestli má zařízení povolený přístup k podnikovým datům. 

## <a name="before-you-begin"></a>Před zahájením

V rámci nastavení ochrany před mobilními hrozbami (MTD) jste v konzole partnera MTD vytvořili zásadu, která klasifikuje různé hrozby jako vysoké, střední nebo nízké. V zásadách ochrany aplikací Intune je teď potřeba nastavit úroveň ochrany před mobilními hrozbami.

Předpoklady pro zásady ochrany aplikací pomocí MTD:

- Nastavte integraci MTD s Intune. Bez této integrace nebudou zásady ochrany aplikací MTD nijak ovlivněny.

## <a name="to-create-an-mtd-app-protection-policy"></a>Vytvoření zásady ochrany aplikací MTD

1. Přejděte na portál [Azure Portal](https://portal.azure.com/) a přihlaste se pomocí svých přihlašovacích údajů k Intune.

2. Na **Řídicím panelu Azure** zvolte v nabídce vlevo **Všechny služby** a potom do filtru textového pole zadejte **Intune**.

3. Zvolte **Intune** a zobrazí se **řídicí panel Intune**.

4. Na **řídicím panelu Intune**zvolte **klientské aplikace**a pak v části **Spravovat** zvolte **Zásady ochrany aplikací** .

5. Zvolte **vytvořit zásadu**, zadejte **název**, **Popis**a vyberte **platformu**. 

6. V podokně **podmíněné spuštění** pod tabulkou **podmínky zařízení** v rozevíracím seznamu pod položkou **maximální povolená úroveň hrozby zařízení**vyberte úroveň mobilní hrozby.

    a.  **Zabezpečeno:** Tato úroveň poskytuje nejvyšší zabezpečení. Zařízení nemůže přistupovat k prostředkům společnosti, pokud je vystavené nějakým hrozbám. Pokud se najde jakákoli hrozba, zařízení se vyhodnotí jako nevyhovující.

    b.  **Nízká:** Zařízení se vyhodnotí jako vyhovující i v případě, že se v něm nachází jenom hrozby nízké úrovně. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.

    c.  **Střední:** Zařízení vyhovuje, pokud se v něm přítomné hrozby pohybují na střední nebo nízké úrovni. Pokud se v zařízení zjistí hrozby vysoké úrovně, vyhodnotí se jako nevyhovující.

    d.  **Vysoká:** Tato úroveň poskytuje nejnižší zabezpečení. Tato možnost povoluje všechny úrovně hrozeb, protože používá ochranu před mobilními hrozbami jenom ke generování sestav. Při tomto nastavení musejí mít zařízení aplikaci pro ochranu před mobilními hrozbami aktivovanou.

7. Dvakrát klikněte na **Uložit** a pak zvolte **vytvořit**.

## <a name="to-assign-an-mtd-app-protection-policy"></a>Přiřazení zásad ochrany aplikací MTD

Pokud chcete přiřadit zásady dodržování předpisů zařízením uživatelům, vyberte zásady, které jste už nakonfigurovali. Existující zásady najdete v podokně **Dodržování předpisů zařízením – Zásady**.

1. Vyberte zásady, které chcete přiřadit uživatelům, a zvolte **Přiřazení**. Tato akce otevře podokno, kde můžete vybrat **Azure Active Directory skupiny zabezpečení** a přiřadit je k zásadám.

2. Zvolte **Vybrat skupiny** , které se mají zahrnout, a otevřete tak podokno, ve kterém se zobrazí skupiny zabezpečení Azure AD. Zvolením **možnosti vybrat** nasadíte zásadu uživatelům.

> [!NOTE] 
> Tím jste zásady uplatnili u uživatelů. U zařízení používaných uživateli, na které zásady cílí, se vyhodnotí přístup k podnikovým datům na cílových aplikacích prostřednictvím ochrany aplikací Intune.

## <a name="next-steps"></a>Další kroky  

- Přečtěte si další informace o [ochrany před mobilními hrozbami](~/protect/mobile-threat-defense.md) v Microsoft Intune.
