---
title: Přiřazení profilů zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Pomocí portálu Azure Portal můžete uživatelům a zařízením přiřadit profily a zásady zařízení. Přečtěte si, jak vyloučit skupiny z přiřazení profilu v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: db1f0944a6725d1f361ea20c972d8ffa8f5d9035
ms.sourcegitcommit: a50a1ca123ecc2c5ac129f112f73838748f56476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2019
ms.locfileid: "72237216"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Přiřazení profilů uživatelů a zařízení v Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Vytvoříte profil a zahrnete do něj všechna nastavení, která jste zadali. V dalším kroku nasadíte nebo "přiřadíte" profil k vašim skupinám uživatelů a zařízení Azure Active Directory (Azure AD). Po přiřazení uživatelé a zařízení obdrží váš profil a nastavení, které jste zadali, se použije.

V tomto článku se dozvíte, jak přiřadit profil, a obsahuje některé informace o použití značek oboru v profilech.

> [!NOTE]  
> Když zásadu odeberete nebo už není přiřazená k zařízení, nastavení může zachovat stávající hodnotu. Nastavení se nevrátí na výchozí hodnotu. Chcete-li změnit nastavení na jinou hodnotu, vytvořte novou zásadu a přiřaďte ji.

## <a name="assign-a-device-profile"></a>Přiřazení profilu zařízení

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace zařízení** > **Profily**. Zobrazí se všechny profily.
3. Vyberte profil, který chcete přiřadit > **přiřazení**.
4. Zvolte **Zahrnout** skupiny nebo **vyloučit** skupiny a pak vyberte své skupiny. Když skupiny vybíráte, zvolíte skupinu Azure AD. Pokud chcete vybrat více skupin, podržte stisknutou klávesu **CTRL** a vyberte vaše skupiny.

    ![Snímek obrazovky s možnostmi zahrnout nebo vyloučit skupiny z přiřazení profilu](./media/device-profile-assign/group-include-exclude.png)

5. **Uložte** provedené změny.

### <a name="evaluate-how-many-users-are-targeted"></a>Vyhodnocení počtu cílových uživatelů

Když přiřadíte profil, můžete také **vyhodnotit** , kolik uživatelů je ovlivněno. Tato funkce vypočítává uživatele. nepočítá zařízení.

1. V Intune vyberte **Konfigurace zařízení** > **profily**.
2. Vyberte profil > **přiřazení** > **vyhodnotit**. Zobrazí se zpráva o tom, kolik uživatelů cílí na tento profil.

Pokud je tlačítko **vyhodnotit** zobrazené šedě, ujistěte se, že je profil přiřazený k jedné nebo více skupinám.

## <a name="use-scope-tags-or-applicability-rules"></a>Použití značek oboru nebo pravidel použitelnosti

Když vytváříte nebo aktualizujete profil, můžete do profilu přidat také značky oboru a pravidla použitelnosti.

**Značky oboru** jsou skvělým způsobem, jak přiřadit a filtrovat zásady pro konkrétní skupiny, jako jsou lidské zdroje nebo všichni zaměstnanci s námi-NC. [Pro distribuci použijte značky RBAC a Scope](../fundamentals/scope-tags.md) s více informacemi.

Na zařízeních s Windows 10 můžete přidat **pravidla použitelnosti** , aby se profil mohl vztahovat jenom na konkrétní verzi operačního systému nebo na konkrétní edici Windows. [Pravidla použitelnosti](device-profile-create.md#applicability-rules) obsahují další informace.

## <a name="exclude-groups-from-a-profile-assignment"></a>Vyloučení skupin z přiřazení profilu

Profily konfigurace zařízení v Intune vám umožňují vyloučit skupiny z přiřazení zásad.

Intune se nezobrazuje v relacích skupin uživatelů a zařízení. Zahrnutí skupin uživatelů bez skupin zařízení nemusí získat očekávané výsledky. V případě scénářů skupiny uživatelů a skupin zařízení a skupin zařízení má vyloučení přednost před zařazením.

Například přiřadíte profil zařízení skupině uživatelů **Všichni firemní uživatelé** , ale vyloučíte členy ve skupině uživatelů **správce vyšších zaměstnanců** . Vzhledem k tomu, že obě skupiny jsou skupiny uživatelů, jsou ze zásad vyloučeni všichni členové **vyšších zaměstnanců správy** , i když jsou členy skupiny **Všichni podnikoví uživatelé** .

Zahrnutí má při použití smíšených skupin přednost před vyloučením, jako je skupina uživatelů pro zařízení nebo skupina zařízení – uživatel.

Například chcete přiřadit profil zařízení všem uživatelům ve vaší organizaci, s výjimkou zařízení veřejného terminálu. Zahrnete skupinu **Všichni uživatelé**, ale vyloučíte skupinu **Všechna zařízení**. V takovém případě všichni uživatelé a jejich zařízení získají zásady, i když je zařízení uživatele ve skupině **všechna zařízení** .

Vyloučení prohlíží pouze přímé členy skupiny. Nezahrnuje zařízení, která jsou přidružená k uživateli. Zařízení, která nemají uživatele, ale nezískají zásady. K tomuto chování dochází, protože zařízení bez uživatelů nemají žádný vztah ke skupině **Všichni uživatelé** .

Pokud zahrnete **Všechna zařízení** a vyloučíte **Všechny uživatele**, získají zásady všechna zařízení. V tomto scénáři je cílem vyloučit ze zásad ta zařízení, která mají přidruženého uživatele. Tím se ale zařízení nevyloučí, protože funkce vyloučení porovnává jenom přímé členy skupiny.

## <a name="next-steps"></a>Další kroky

Pokyny k monitorování profilů a zařízení, ve kterých jsou spuštěny vaše profily, najdete v tématu [monitorování profilů zařízení](device-profile-monitor.md) .
