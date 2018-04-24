---
title: Přehled životního cyklu aplikace pro Microsoft Intune
description: Přečtěte si o životním cyklu spravovaných aplikací v Microsoft Intune. Životní cyklus aplikace zahrnuje přidání, nasazení, konfiguraci, ochranu a vyřazení aplikací.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: apps
ms.openlocfilehash: 853873480beb5e95a195e04e251cea9975ce03b4
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="overview-of-the-app-lifecycle-in-microsoft-intune"></a>Přehled životního cyklu aplikace v Microsoft Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Životní cyklus aplikace Microsoft Intune začíná, když je aplikace přidána, a postupuje dalšími fázemi, dokud ji neodeberete. Když těmto fázím porozumíte, budete znát potřebné podrobnosti, abyste mohli začít se správou aplikací v Intune.

![Životní cyklus aplikace](./media/app-lifecycle.png "Životní cyklus aplikace Intune")

## <a name="add"></a>Přidání

Prvním krokem při nasazení aplikací je přidání aplikací, které chcete spravovat a přiřazovat, do Intune. Můžete pracovat s mnoha různými typy aplikací, ale základní postupy jsou stejné. Pomocí Intune můžete přidávat různé typy aplikací včetně aplikací napsaných interně (obchodních), aplikací z obchodu, aplikací, které jsou integrované, a aplikací na webu. Další informace o těchto typech aplikací najdete v článku [Přidání aplikací do Microsoft Intune](apps-add.md). 

## <a name="deploy"></a>Nasazení

Po přidání aplikace do Intune ji pak můžete [přiřadit uživatelům a zařízením, která spravujete](apps-deploy.md). Intune tento proces usnadňuje a po nasazení aplikace můžete [monitorovat úspěšnost](apps-monitor.md) nasazení z Intune na portálu Azure Portal. Kromě toho některé obchody s aplikacemi, jako jsou obchody pro [Apple](vpp-apps-ios.md) a [Windows](windows-store-for-business.md), umožňují vaší společnosti nákup hromadných licencí k aplikaci. Intune může synchronizovat data s těmito obchody, abyste mohli nasazovat a sledovat využití licencí pro tyto typy aplikací přímo z konzoly pro správu Intune.

## <a name="configure"></a>Konfigurace

Jako součást životního cyklu aplikace jsou pravidelně vydávány nové verze aplikace. Intune poskytuje nástroje ke snadné [aktualizaci aplikací](apps-add.md), které jste nasadili, na novější verzi. Kromě toho můžete pro některé aplikace konfigurovat další funkce, například:
- [Zásady konfigurace aplikací pro iOS](app-configuration-policies-use-ios.md) určují nastavení pro aplikace kompatibilní s iOS, které se používají při spuštění aplikace. Aplikace může například vyžadovat konkrétní nastavení brandingu nebo název serveru, ke kterému se musí připojit.
- [Zásady spravovaného prohlížeče](app-configuration-managed-browser.md) vám pomůžou při konfiguraci nastavení pro spravovaný prohlížeč Intune, která nahradí výchozí prohlížeč zařízení a umožní omezit weby, které mohou uživatelé navštěvovat.

## <a name="protect"></a>Ochrana

Intune poskytuje mnoho způsobů, jak pomoci chránit data ve vašich aplikacích. Hlavní metody jsou následující:
- [Podmíněný přístup](conditional-access.md), který řídí přístup k e-mailu a dalším službám v závislosti na zadaných podmínkách. Příkladem podmínek může být typ zařízení nebo shoda se [zásadami dodržování předpisů zařízení](device-compliance.md), které jste nasadili.
- [Zásady ochrany aplikací](app-protection-policy.md) spolupracují s jednotlivými aplikacemi a pomáhají chránit firemní data, která používají. Například můžete omezit kopírování dat mezi nespravovanými a spravovanými aplikacemi, nebo můžete zabránit aplikacím ve spuštění v zařízeních s jailbreakem nebo rootem.

## <a name="retire"></a>Vyřazení

Nakonec pravděpodobně dojde k tomu, že nasazené aplikace začnou být zastaralé a bude třeba je odebrat. Intune umožňuje snadno [vyřazovat aplikace z provozu](device-management.md).

## <a name="next-steps"></a>Další kroky:

- Přečtěte si další informace o [správě aplikací v Microsoft Intune](app-management.md).