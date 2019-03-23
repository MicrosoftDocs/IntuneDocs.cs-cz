---
title: Přiřazení profilů zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Pomocí portálu Azure Portal můžete uživatelům a zařízením přiřadit profily a zásady zařízení. Zjistěte, jak vyloučit skupiny z přiřazení profilu v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1d77308e010b71ec076f33b669674ce1252937f9
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394844"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Přiřazení profilů uživatelů a zařízení v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Vytvoření profilu a obsahuje všechna nastavení, které jste zadali. Dalším krokem je nasazení nebo "" profil přiřadit do skupin uživatelů nebo zařízení Azure Active Directory (Azure AD). Jakmile bude přiřazena, uživatele a zařízení, přijímat svůj profil a použijí se nastavení, které jste zadali.

Tento článek ukazuje, jak přiřadit profil a zahrnuje některé informace o použití značky oboru vašich profilů.

## <a name="assign-a-device-profile"></a>Přiřazení profilu zařízení

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily**. Jsou uvedeny všechny profily.
3. Vyberte profil, který chcete přiřadit > **přiřazení**.
4. Zvolit **zahrnout** skupiny nebo **vyloučit** skupiny a pak vyberte skupiny. Když skupiny vybíráte, zvolíte skupinu Azure AD. Chcete-li vybrat více skupin, podržte **Ctrl** klíče a skupiny.

    ![Snímek obrazovky s možnostmi zahrnout nebo vyloučit skupiny z přiřazení profilu](./media/group-include-exclude.png)

5. **Uložte** provedené změny.

## <a name="use-scope-tags"></a>Použití značek oboru

Při vytváření nebo aktualizaci profilu, můžete také přidat značky oboru profilu.

**Značky oboru** jsou skvělý způsob, jak přiřadit a filtrovat zásady na konkrétní skupiny, jako jsou lidské zdroje nebo všechny USA síťovým Adaptérem zaměstnanci. [Použití značek RBAC a obor pro distribuované IT](scope-tags.md) obsahuje další informace.

## <a name="exclude-groups-from-a-profile-assignment"></a>Vyloučení skupin z přiřazení profilu

Profily konfigurace zařízení v Intune vám umožňují vyloučit skupiny z přiřazení zásad. Například můžete profil zařízení přiřadit **všechny firemní uživatele** skupině, ale vyloučit členy **nejvyššího vedení** skupiny.

Při vyloučení skupin, vylučte jenom uživatele nebo z přiřazení vyloučit pouze skupiny zařízení (ne směs skupin), Intune nebere v úvahu žádný vztah uživatel zařízení. Zahrnutí skupin uživatelů a současné vyloučení skupin zařízení nemusí získat přinést očekávané výsledky. Při použití smíšené skupiny nebo vyvstanou jiné konflikty, zahrnutí má přednost před vyloučením.

Když například chcete přiřadit profil zařízení všem zařízením ve své organizaci kromě zařízení sloužících jako veřejný terminál. Zahrnete skupinu **Všichni uživatelé**, ale vyloučíte skupinu **Všechna zařízení**. V takovém případě všichni uživatelé a jejich zařízení tyto zásady získají, i když v zařízení uživatele **všechna zařízení** skupiny.

Vyloučení zjistí pouze přímé členy skupiny. To nezahrnuje zařízení, která jsou přidružená k uživateli. Zařízení, která nemají uživatele, ale zásady nezískají. K tomu dojde, protože taková zařízení nemají žádný vztah ke **všichni uživatelé** skupiny.

Pokud zahrnete **Všechna zařízení** a vyloučíte **Všechny uživatele**, získají zásady všechna zařízení. V tomto scénáři je cílem vyloučit ze zásad ta zařízení, která mají přidruženého uživatele. Tím se ale zařízení nevyloučí, protože funkce vyloučení porovnává jenom přímé členy skupiny.

## <a name="next-steps"></a>Další postup

Zobrazit [monitorovat profily zařízení](device-profile-monitor.md) pokyny k monitorování vašich profilů a zařízení s profily.