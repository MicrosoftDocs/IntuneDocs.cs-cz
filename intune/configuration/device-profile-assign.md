---
title: Přiřazení profilů zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Pomocí portálu Azure Portal můžete uživatelům a zařízením přiřadit profily a zásady zařízení. Přečtěte si, jak vyloučit skupiny z přiřazení profilu v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: altsou
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 50b91251572e45669f197df7ac4e5ff94caf47a1
ms.sourcegitcommit: 1a7f04c80548e035be82308d2618492f6542d3c0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2019
ms.locfileid: "73755335"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Přiřazení profilů uživatelů a zařízení v Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Vytvoříte profil a zahrnete do něj všechna nastavení, která jste zadali. V dalším kroku nasadíte nebo "přiřadíte" profil k vašim skupinám uživatelů a zařízení Azure Active Directory (Azure AD). Po přiřazení uživatelé a zařízení obdrží váš profil a nastavení, které jste zadali, se použije.

V tomto článku se dozvíte, jak přiřadit profil, a obsahuje některé informace o použití značek oboru v profilech.

> [!NOTE]  
> Když zásadu odeberete nebo už není přiřazená k zařízení, nastavení může zachovat stávající hodnotu. Nastavení se nevrátí na výchozí hodnotu. Chcete-li změnit nastavení na jinou hodnotu, vytvořte novou zásadu a přiřaďte ji.

## <a name="before-you-begin"></a>Před zahájením

Ujistěte se, že máte odpovídající roli pro přiřazení zásad. Další informace najdete v tématu [řízení přístupu na základě role (RBAC) pomocí Microsoft Intune](../fundamentals/role-based-access-control.md).

## <a name="assign-a-device-profile"></a>Přiřazení profilu zařízení

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vyberte **zařízení** > **konfigurační profily**. Zobrazí se všechny profily.
3. Vyberte profil, který chcete přiřadit > **přiřazení**.
4. Zvolte **Zahrnout** skupiny nebo **vyloučit** skupiny a pak vyberte své skupiny. Když skupiny vybíráte, zvolíte skupinu Azure AD. Pokud chcete vybrat více skupin, podržte stisknutou klávesu **CTRL** a vyberte vaše skupiny.

    ![Snímek obrazovky s možnostmi zahrnout nebo vyloučit skupiny z přiřazení profilu](./media/device-profile-assign/group-include-exclude.png)

5. **Uložte** provedené změny.

### <a name="evaluate-how-many-users-are-targeted"></a>Vyhodnocení počtu cílových uživatelů

Když přiřadíte profil, můžete také **vyhodnotit** , kolik uživatelů je ovlivněno. Tato funkce vypočítává uživatele. nepočítá zařízení.

1. V centru pro správu vyberte **zařízení** > **konfigurační profily**.
2. Vyberte profil > **přiřazení** > **vyhodnotit**. Zobrazí se zpráva o tom, kolik uživatelů cílí na tento profil.

Pokud je tlačítko **vyhodnotit** zobrazené šedě, ujistěte se, že je profil přiřazený k jedné nebo více skupinám.

## <a name="use-scope-tags-or-applicability-rules"></a>Použití značek oboru nebo pravidel použitelnosti

Když vytváříte nebo aktualizujete profil, můžete do profilu přidat také značky oboru a pravidla použitelnosti.

**Značky oboru** jsou skvělým způsobem, jak přiřadit a filtrovat zásady pro konkrétní skupiny, jako jsou lidské zdroje nebo všichni zaměstnanci s námi-NC. [Pro distribuci použijte značky RBAC a Scope](../fundamentals/scope-tags.md) s více informacemi.

Na zařízeních s Windows 10 můžete přidat **pravidla použitelnosti** , aby se profil mohl vztahovat jenom na konkrétní verzi operačního systému nebo na konkrétní edici Windows. [Pravidla použitelnosti](device-profile-create.md#applicability-rules) obsahují další informace.

## <a name="exclude-groups-from-a-profile-assignment"></a>Vyloučení skupin z přiřazení profilu

Profily konfigurace zařízení v Intune umožňují zahrnout a vyloučit skupiny z přiřazení zásad.

Osvědčeným postupem je vytváření a přiřazování zásad konkrétně pro vaše skupiny uživatelů. A vytvořte a přiřaďte jiné zásady konkrétně pro vaše skupiny zařízení. Další informace o skupinách najdete v tématu [Přidání skupin pro uspořádání uživatelů a zařízení](../fundamentals/groups-add.md).

Když přiřadíte zásady, použijte následující tabulku při zahrnutí a vyloučení skupin. Značka zaškrtnutí znamená, že je přiřazení podporováno:

![Podporované možnosti zahrnují nebo vylučují skupiny z přiřazení profilu.](./media/device-profile-assign/include-exclude-user-device-groups.png)

### <a name="what-you-should-know"></a>Co byste měli znát

- Vyloučení má přednost před zahrnutím do následujících scénářů stejného typu skupiny:

  - Zahrnutí skupin uživatelů a vyloučení skupin uživatelů
  - Zahrnutí skupin zařízení a vyloučení skupiny zařízení

  Například přiřadíte profil zařízení skupině uživatelů **Všichni firemní uživatelé** , ale vyloučíte členy ve skupině uživatelů **správce vyšších zaměstnanců** . Vzhledem k tomu, že obě skupiny jsou skupiny uživatelů, získají zásady **Všichni firemní uživatelé** s výjimkou **pracovníků hlavní správy** .

- Intune nevyhodnocuje vztahy mezi uživateli a zařízeními. Pokud přiřadíte zásady ke smíšeným skupinám, výsledky nemusí být to, co chcete, nebo očekávat.

  Například přiřadíte profil zařízení skupině uživatelů **Všichni uživatelé** , ale vyloučíte skupinu zařízení **všechna osobní zařízení** . V tomto kombinovaném přiřazení zásad skupiny získají **Všichni uživatelé** zásadu. Vyloučení nelze použít.

  V důsledku toho se nedoporučuje přiřazování zásad ke smíšeným skupinám.

## <a name="next-steps"></a>Další kroky

Pokyny k monitorování profilů a zařízení, ve kterých jsou spuštěny vaše profily, najdete v tématu [monitorování profilů zařízení](device-profile-monitor.md) .
