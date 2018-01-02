---
title: "Přehled životního cyklu aplikací pro Intune"
description: "Přečtěte si informace o životním cyklu aplikací spravovaných pomocí Intune od jejich přidávání po jejich případné vyřazení z provozu."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1e50e3af525be48bf058dd32bfb7b93508d500a3
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/08/2017
---
# <a name="overview-of-the-app-lifecycle"></a>Přehled životního cyklu aplikace

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Životní cyklus aplikace Intune začíná, když je aplikace přidána, a postupuje dalšími fázemi, dokud ji neodeberete.

![Životní cyklus aplikace](./media/app-lifecycle.png "Životní cyklus aplikace Intune")

## <a name="add"></a>Přidání

Prvním krokem při nasazení aplikací je přidání aplikací, které chcete spravovat a přiřazovat, do Intune. Můžete pracovat s mnoha různými typy aplikací, ale základní postupy jsou stejné. S Intune můžete přidávat aplikace pro [registrovaná zařízení](apps-add.md) ([portál Classic](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)) i pro [počítače s Windows spravované klientským softwarem Intune](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune).

## <a name="deploy"></a>Nasazení

Po přidání aplikace do Intune ji pak můžete [přiřadit uživatelům a zařízením, která spravujete](apps-deploy.md) ([portál Classic](/intune-classic/deploy-use/deploy-apps)). Intune usnadňuje tento proces a po nasazení aplikace můžete [monitorovat úspěšnost](apps-monitor.md) nasazení ([portál Classic](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune)) z konzoly pro správu Intune. Kromě toho některé obchody s aplikacemi, jako jsou obchody pro [Apple](vpp-apps-ios.md) ([portál Classic](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)) a [Windows](windows-store-for-business.md) ([portál Classic](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)), umožňují vaší společnosti nákup hromadných licencí k aplikaci. Intune může synchronizovat data s těmito obchody, abyste mohli nasazovat a sledovat využití licencí pro tyto typy aplikací přímo z konzoly pro správu Intune.

## <a name="configure"></a>Konfigurace

Jako součást životního cyklu aplikace jsou pravidelně vydávány nové verze aplikace. Intune poskytuje nástroje ke snadné [aktualizaci nasazených aplikací](apps-add.md) ([portál Classic](/intune-classic/deploy-use/update-apps-using-microsoft-intune)) na novější verzi. Kromě toho můžete pro některé aplikace konfigurovat další funkce, například:
- [Zásady konfigurace aplikací pro iOS](app-configuration-policies-use-ios.md) ([portál Classic](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)) určují nastavení pro aplikace kompatibilní s iOSem, které se používají při spuštění aplikace. Aplikace může například vyžadovat konkrétní nastavení brandingu nebo název serveru, ke kterému se připojuje.
- [Zásady spravovaného prohlížeče](app-configuration-managed-browser.md) ([portál Classic](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)) vám pomůžou při konfiguraci nastavení pro spravovaný prohlížeč Intune, která nahradí výchozí prohlížeč zařízení a umožní omezit weby, které mohou uživatelé navštěvovat.

## <a name="protect"></a>Ochrana

Intune poskytuje mnoho způsobů, jak pomoci chránit data ve vašich aplikacích. Hlavní metody jsou následující:
- [Podmíněný přístup](conditional-access.md) ([portál Classic](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)) řídí přístup k e-mailu a dalším službám v závislosti na zadaných podmínkách. Příkladem podmínek může být typ zařízení nebo shoda se [zásadami dodržování předpisů zařízení](device-compliance.md) ([portál Classic](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)), které jste nasadili.
- [Zásady ochrany aplikací](app-protection-policy.md) ([portál Classic](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)) spolupracují s jednotlivými aplikacemi a pomáhají chránit firemní data, která používají. Například můžete omezit kopírování dat mezi nespravovanými a spravovanými aplikacemi, nebo můžete zabránit aplikacím ve spuštění v zařízeních s jailbreakem nebo rootem.

## <a name="retire"></a>Vyřazení

Nakonec pravděpodobně dojde k tomu, že nasazené aplikace začnou být zastaralé a bude třeba je odebrat. Intune umožňuje snadno [vyřazovat aplikace z provozu](device-management.md) ([portál Classic](/intune-classic/deploy-use/retire-apps-using-microsoft-intune)).
