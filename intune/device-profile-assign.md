---
title: Přiřazení profilů zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Pomocí portálu Azure Portal můžete uživatelům a zařízením přiřadit profily a zásady zařízení. Zjistěte, jak z přiřazení profilu v Microsoft Intune vyloučit skupiny.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9840298df981bee6c33d3cb36ec5e4ada46d11bd
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/20/2018
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Přiřazení profilů uživatelů a zařízení v Microsoft Intune

Když vytvoříte profil, můžete ho přiřadit skupinám Azure Active Directory (Azure AD).

## <a name="assign-a-device-profile"></a>Přiřazení profilu zařízení

1. Na portálu [Azure Portal](https://portal.azure.com) vyberte **Všechny služby** a vyhledejte **Microsoft Intune**.
2. V **Microsoft Intune** vyberte **Konfigurace zařízení** a pak **Profily**.
3. V seznamu profilů vyberte profil, který chcete přiřadit, a pak vyberte **Přiřazení**.
4. Zvolte **Zahrnout** skupiny nebo **Vyloučit** skupiny a pak vyberte skupiny.  

    ![Snímek obrazovky s možnostmi zahrnout nebo vyloučit skupiny z přiřazení profilu](./media/group-include-exclude.png)

5. Když skupiny vybíráte, zvolíte skupinu Azure AD. Pokud chcete vybrat více skupin, stiskněte a podržte klávesu **Ctrl**.
6. Po dokončení vyberte **Uložit**.

## <a name="exclude-groups-from-a-profile-assignment"></a>Vyloučení skupin z přiřazení profilu

Profily konfigurace zařízení v Intune vám umožňují vyloučit skupiny z přiřazení zásad. Například můžete profil zařízení přiřadit skupině **Všichni firemní uživatelé** a vyloučit všechny členy skupiny **Členové nejvyššího vedení firmy**.

Když vylučujete skupiny z přiřazení, vylučte jenom uživatele, nebo jenom skupiny zařízení (ne směs skupin) – Intune nebere v úvahu vztahy mezi uživateli a zařízeními. Zahrnutí skupin uživatelů a současné vyloučení skupin zařízení nemusí přinést očekávané výsledky. V případě, že použijete smíšené skupiny nebo vyvstanou jiné konflikty, zahrnutí má před vyloučením přednost.

Když například chcete přiřadit profil zařízení všem zařízením ve své organizaci kromě zařízení sloužících jako veřejný terminál. Zahrnete skupinu **Všichni uživatelé**, ale vyloučíte skupinu **Všechna zařízení**. V takovém případě všichni uživatelé a jejich zařízení tyto zásady získají, přestože zařízení uživatele je součástí skupiny **Všechna zařízení**.

Funkce vyloučení hledá jenom přímé členy skupin, nezahrnuje zařízení, která jsou přidružená k uživateli. Zařízení, která nemají uživatele, ale zásady nezískají. K tomu dochází, protože taková zařízení nemají žádný vztah ke skupině **Všichni uživatelé**.

Pokud zahrnete **Všechna zařízení** a vyloučíte **Všechny uživatele**, získají zásady všechna zařízení. V tomto scénáři je cílem vyloučit ze zásad ta zařízení, která mají přidruženého uživatele. Tím se ale zařízení nevyloučí, protože funkce vyloučení porovnává jenom přímé členy skupiny.

>[!TIP]
>Vyloučení nejsou dostupná pro zásady dodržování předpisů a přiřazení aplikací. Pokud chcete vyloučit členy z přiřazení, můžete použít přiřazení **K dispozici** a **Neužívá se**. Například přiřadíte aplikaci skupině **Všichni firemní uživatelé** se záměrem **K dispozici** a skupině **Členové nejvyššího vedení firmy** se záměrem **Neužívá se**. Aplikace se přiřadí všem uživatelům *kromě* uživatelů ve skupině **Členové nejvyššího vedení firmy**. Pokud přiřadíte aplikaci skupině **Všichni firemní uživatelé** se záměrem **Povinné**, uživatelé skupiny **Členové nejvyššího vedení firmy** jsou také zahrnutí.

## <a name="next-steps"></a>Další kroky
Pokyny k monitorování přiřazení profilů zařízení, najdete v článku [Sledování profilů zařízení](device-profile-monitor.md).
