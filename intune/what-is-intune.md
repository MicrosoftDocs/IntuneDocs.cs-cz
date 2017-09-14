---
title: "Úvod do Intune na Azure Portalu"
titlesuffix: Azure portal
description: "Získejte základní informace o Intune na Azure Portalu a o tom, jak vám pomůže se správou zařízení."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 07/17/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: 
ms.openlocfilehash: 6150434620f055f17563da6269c85c89c70b8e2b
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a>Úvod do Microsoft Intune na portálu Azure Portal


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune je teď na portálu Azure Portal, což znamená, že se mění pracovní postupy a funkce, na které jste zvyklí.
Nový portál nabízí nové a aktualizované funkce portálu Azure Portal, na kterém můžete spravovat mobilní zařízení, počítače a aplikace svojí organizace.

* Téma [Kde v Azure najdu svoje funkce](ui-changes.md) obsahuje referenční informace, kde můžete vidět konkrétní pracovní postupy a uživatelská rozhraní, která se změnila s přechodem na Azure.
* V tématu [Skupiny klasického Intune na portálu Azure](groups-get-started.md) je vysvětlené, jaký dopad má přechod na skupiny zabezpečení Azure Active Directory na správu skupin.




V této knihovně může najít průběžně aktualizované informace o novém portálu. Pokud máte nějaké návrhy, poskytněte nám zpětnou vazbu v komentářích k tomuto tématu. Rádi bychom znali vaše názory.

K tomu nejdůležitějšímu v novém prostředí patří:

- Integrovaná konzola pro všechny součásti EMS (Enterprise Mobility + Security)
- Konzola HTML postavená na webových standardech
- Podpora rozhraní Microsoft Graph API pro automatizaci mnoha akcí
- Skupiny Azure Active Directory (AD) pro zajištění kompatibility mezi všemi aplikacemi Azure
- Podpora většiny moderních prohlížečů

> [!IMPORTANT]
> **Ještě nový portál nevidíte?**<br>
> Provádí se migrace stávajících tenantů do nového prostředí. Před migrací tenanta se v Office Message Center zobrazí oznámení.
>
> Zpřístupnění pracovních postupů registrace Apple v Azure u účtů Intune vytvořených před lednem 2017 vyžaduje jednorázovou migraci. Plán pro migraci ještě nebyl oznámen. Pokud váš stávající účet nemá k portálu Azure Portal přístup, doporučujeme vytvořit zkušební účet.
>
> Podívejte se na seznam potenciálních problémů, které mohou migraci zablokovat: https://blogs.technet.microsoft.com/intunesupport/2017/05/17/intune-migration-blockers-for-grouping-targeting/


## <a name="before-you-start"></a>Než začnete

K použití Intune na portálu Azure Portal potřebujete účet správce a tenanta Intune. [Zaregistrujte si účet](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20), pokud ho ještě nemáte.

## <a name="supported-web-browsers-for-the-azure-portal"></a>Prohlížeče, které portál Azure Portal podporuje

Azure Portal funguje na většině moderních počítačů PC, Mac a tabletech. Mobilní telefony nejsou podporované.
V současnosti se podporují následující prohlížeče:

- Microsoft Edge (nejnovější verze)
- Microsoft Internet Explorer 11
- Safari (nejnovější verze, jen Mac)
- Chrome (nejnovější verze)
- Firefox (nejnovější verze)

Nejnovější informace o podporovaných prohlížečích najdete na portálu [Azure Portal](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices).

## <a name="whats-in-this-library"></a>Co je v této knihovně?

Do této dokumentace je promítnuto rozložení Azure Portalu, abyste mohli snadněji najít informace, které potřebujete.

![Úlohy portálu Azure Portal](./media/azure-portal-workloads.png)

### <a name="introduction-and-get-started"></a>Úvod a začínáme
Tato část obsahuje [úvodní informace](introduction-intune.md), které vám pomůžou v začátcích používání Intune.
### <a name="plan-and-design"></a>Plánování a navrhování
Informace, které vám usnadní [plánování a navrhování](/intune-classic/plan-design/introduction) prostředí Intune
### <a name="device-enrollment"></a>Registrace zařízení
[Zjistěte, jak zajistíte správu zařízení přes Intune](device-enrollment.md).
### <a name="device-compliance"></a>Dodržování předpisů zařízení
[Definujte úroveň dodržování předpisů pro svá zařízení a dostávejte zprávy o všech zařízeních, která je nedodržují](device-compliance.md).
### <a name="device-configuration"></a>Konfigurace zařízení
[Informace o profilech, s jejichž pomocí můžete na spravovaných zařízeních nakonfigurovat nastavení a funkce](device-profiles.md)
### <a name="devices"></a>Zařízení
[Inventář a sestavy vám poskytnou přehled o spravovaných zařízeních](device-management.md).
### <a name="mobile-apps"></a>Mobilní aplikace
[Informace o publikování, správě, konfiguraci a ochraně aplikací](app-management.md)
### <a name="conditional-access"></a>Podmíněný přístup
[Omezte přístup ke službám Exchange na základě určených podmínek](conditional-access.md).
### <a name="on-premises-access"></a>Místní přístup
[Konfigurace přístupu k Exchangi ActiveSync a místnímu Exchangi](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a>Uživatelé
[Další informace o uživatelích zařízení, která spravujete, a řazení prostředků do skupin](users-add.md)
### <a name="groups"></a>Skupiny
[Informace o tom, jak můžete používat skupiny Azure Active Directory s Intune](groups-get-started.md)
### <a name="intune-roles"></a>Role Intune
[Určete, kdo může v Intune provádět různé akce a na koho se tyto akce vztahují](role-based-access-control.md). Můžete buď použít předdefinované role, které vyhovují běžným situacím v Intune, nebo si vytvořit své vlastní role.
### <a name="software-updates"></a>Aktualizace softwaru
[Informace o tom, jak nakonfigurovat aktualizace softwaru pro zařízení s Windows 10](windows-update-for-business-configure.md)



## <a name="whats-new"></a>Co je nového

[Zjistěte, co je nového v Intune](whats-new.md).
