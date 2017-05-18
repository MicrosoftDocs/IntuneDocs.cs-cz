---
title: "Přehled životního cyklu aplikace | Dokumentace Microsoftu"
description: "Přečtěte si informace o životním cyklu aplikací spravovaných pomocí Intune od jejich přidávání po jejich případné vyřazení z provozu."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: c3394663b234ada70f724b750dfdffc8369cb203


---

# <a name="overview-of-the-app-lifecycle"></a>Přehled životního cyklu aplikace

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Životní cyklus aplikace Intune začíná, když je aplikace přidána, a postupuje dalšími fázemi, dokud ji neodeberete.

![Životní cyklus aplikace](./media/app-lifecycle.png "Životní cyklus aplikace Intune")

## <a name="add"></a>Přidání

Prvním krokem při nasazení aplikací je přidání aplikací, které chcete spravovat a nasazovat, do Intune. Můžete pracovat s mnoha různými typy aplikací, ale základní postupy jsou stejné. S Intune můžete přidávat aplikace pro [registrovaná zařízení](add-apps-for-mobile-devices-in-microsoft-intune.md) i pro [počítače s Windows spravované klientským softwarem Intune](add-apps-for-windows-pcs-in-microsoft-intune.md).

## <a name="deploy"></a>Nasazení

Po přidání aplikace do Intune ji pak můžete [nasadit do zařízení, která spravujete](deploy-apps.md). Intune usnadňuje tento proces a po nasazení aplikace můžete [monitorovat úspěšnost](monitor-apps-in-microsoft-intune.md) nasazení z konzoly pro správu Intune. Kromě toho některé obchody s aplikacemi, jako jsou obchody pro [Apple](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md) a [Windows](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md), umožňují vaší společnosti nákup hromadných licencí k aplikaci. Intune může synchronizovat data s těmito obchody, abyste mohli nasazovat a sledovat využití licencí pro tyto typy aplikací přímo z konzoly pro správu Intune.

## <a name="configure"></a>Konfigurace

Jako součást životního cyklu aplikace jsou pravidelně vydávány nové verze aplikace. Intune poskytuje nástroje ke snadné [aktualizaci aplikací](update-apps-using-microsoft-intune.md), které jste nasadili, na novější verzi. Kromě toho můžete pro některé aplikace konfigurovat další funkce, například:
- [Zásady konfigurace aplikací pro iOS](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md) určují nastavení pro aplikace kompatibilní s iOS, které se používají při spuštění aplikace. Aplikace může například vyžadovat konkrétní nastavení brandingu nebo název serveru, ke kterému se připojuje.
- [Zásady spravovaného prohlížeče](manage-internet-access-using-managed-browser-policies.md) vám pomůžou při konfiguraci nastavení pro spravovaný prohlížeč Intune, která nahradí výchozí prohlížeč zařízení a umožní omezit weby, které mohou uživatelé navštěvovat.

## <a name="protect"></a>Ochrana

Intune poskytuje mnoho způsobů, jak pomoci chránit data ve vašich aplikacích. Hlavní metody jsou následující:
- [Podmíněný přístup](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) řídí přístup k e-mailu a dalším službám v závislosti na zadaných podmínkách. Příkladem podmínek může být typ zařízení nebo shoda se [zásadami dodržování předpisů zařízení](introduction-to-device-compliance-policies-in-microsoft-intune.md), které jste nasadili.
- [Správa mobilních aplikací (MAM)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) spolupracuje s jednotlivými aplikacemi a pomáhá chránit firemní data, která používají. Například můžete omezit kopírování dat mezi nespravovanými a spravovanými aplikacemi, nebo můžete zabránit aplikacím ve spuštění v zařízeních s jailbreakem nebo rootem.

## <a name="retire"></a>Vyřazení

Nakonec pravděpodobně dojde k tomu, že nasazené aplikace začnou být zastaralé a bude třeba je odebrat. Intune umožňuje snadno [vyřazovat aplikace z provozu](retire-apps-using-microsoft-intune.md).



<!--HONumber=Dec16_HO5-->

