---
title: "Přiřazení profilů zařízení v Intune"
titlesuffix: Azure portal
description: "Když v Intune vytvoříte profil zařízení, můžete ho podle tohoto tématu přiřadit k zařízením."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef03eeab32050559d34d3d7d580c06c21f5ffb05
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-assign-microsoft-intune-device-profiles"></a>Přiřazení profilů zařízení v Microsoft Intune

## <a name="assign-a-device-profile"></a>Přiřazení profilu zařízení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
1. V okně **Konfigurace zařízení** vyberte **Spravovat** > **Profily**.
2. V okně se seznamem profilů zvolte profil, který chcete spravovat, a pak v okně *název profilu*> **Sestavy** zvolte **Spravovat** > **Přiřazení**.
3. V dalším okně zvolte buď **Zahrnout** (abyste zahrnuli skupiny), nebo **Vyloučit** (abyste skupiny vyloučili) a potom zvolte **Vybrat skupiny**.
![Zahrňte skupiny do přiřazení profilu nebo je z něj vylučte.](./media/group-include-exclude.png)
4. V okně **Vybrat skupiny** zvolte skupiny Azure AD, které chcete do přiřazení zahrnout nebo je z něj vyloučit. Pokud chcete vybrat více skupin, stiskněte a podržte klávesu **CTRL**.
4. Až budete mít v okně **Vybrat skupiny** vybrané všechny potřebné skupiny, zvolte **Vybrat**.



## <a name="how-to-exclude-groups-from-a-device-profile-assignment"></a>Postup vyloučení skupin z přiřazení profilu zařízení

Profily konfigurace zařízení v Intune vám umožňují vyloučit skupiny z přiřazení zásad. Například můžete profil zařízení přiřadit skupině **Všichni firemní uživatelé** a vyloučit všechny členy skupiny **Členové nejvyššího vedení firmy**.

Když skupiny z přiřazení vylučujete, vylučujte pouze uživatele nebo pouze skupiny zařízení, ne smíšené skupiny. Intune nebere v úvahu žádné přiřazení uživatele k zařízení, když vylučujete skupiny. Zahrnutí skupin uživatelů a současné vyloučení skupin zařízení vám pravděpodobně nepřinese potřebné výsledky. V případě, že použijete smíšené skupiny nebo vyvstanou jiné konflikty, zahrnutí má před vyloučením přednost.

Když například chcete přiřadit profil zařízení všem zařízením ve své organizaci kromě zařízení sloužících jako veřejný terminál. Zahrnete skupinu **Všichni uživatelé**, ale vyloučíte skupinu **Všechna zařízení**.

V takovém případě všichni uživatelé a jejich zařízení tyto zásady získají, přestože zařízení uživatele je součástí skupiny **Všechna zařízení**. 

Vyloučení pouze vyhodnocuje přímé členy skupin a nezahrnuje zařízení, která jsou přidružená uživateli. Zařízení, která však uživatele nemají, tuto zásadu nezískají, protože nejsou přidružené ke skupině **Všichni uživatelé**. 

Pokud zahrnete **Všechna zařízení**, ale vyloučíte **Všechny uživatele**, získají zásady všechna zařízení. V tomto případě je cílem vyloučit ze zásad ta zařízení, která mají přidruženého uživatele. Toto se ale nepovede, protože funkce vyloučení porovnává pouze přímé členy skupiny. 

>[!Tip]
>Vyloučení nejsou v současné době dostupná pro zásady dodržování předpisů a přiřazení aplikací. Pokud chcete vyloučit členy z přiřazení, můžete použít záměry přiřazení K dispozici a Neužívá se. Například přiřadíte aplikaci skupině **Všichni firemní uživatelé** se záměrem **K dispozici** a skupině **Členové nejvyššího vedení firmy** se záměrem **Neužívá se**. Aplikace se přiřadí všem uživatelům *kromě* uživatelů ve skupině **Členové nejvyššího vedení firmy**. Pokud přiřadíte aplikaci skupině **Všichni firemní uživatelé** se záměrem **Povinné**, uživatelé skupiny **Členové nejvyššího vedení firmy** vyloučeni nebudou.
 
    
## <a name="next-steps"></a>Další kroky
Informace, které vám pomůžou s monitorováním přiřazení profilů zařízení, najdete v článku [Jak monitorovat profily zařízení](device-profile-monitor.md).
