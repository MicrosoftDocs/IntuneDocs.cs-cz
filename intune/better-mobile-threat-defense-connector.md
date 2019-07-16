---
title: Konektor Better Mobile Threat Defense s Intune
titleSuffix: Intune on Azure
description: Nastavte konektor Better Mobile Threat Defense s Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/25/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 55d4e327d99c8987e6fdc0dea0ac046dd0dc167e
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "67883814"
---
# <a name="better-mobile-threat-defense-connector-with-intune"></a>Konektor Better Mobile Threat Defense s Intune

Přístup mobilních zařízení k podnikovým prostředkům můžete řídit pomocí podmíněného přístupu na základě posouzení rizik, které provádí lépe mobilní, řešení ochrany před mobilními hrozbami (MTD), které se integruje s Microsoft Intune. Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých aplikace Better Mobile běží.

Zásady podmíněného přístupu můžete nakonfigurovat na základě lepšího posouzení mobilního rizika prostřednictvím zásad dodržování předpisů zařízením Intune, které můžete použít k povolení nebo blokování zařízení nesplňujících požadavky pro přístup k podnikovým prostředkům na základě zjištěných hrozeb.

## <a name="how-do-intune-and-better-mobile-help-protect-your-company-resources"></a>Jak Intune a Better Mobile pomáhají chránit prostředky společnosti?

Aplikace Better Mobile je nainstalovaná a spuštěná na mobilních zařízeních. Tato aplikace zaznamenává telemetrii systému souborů, zásobníku sítě, zařízení a aplikací tam, kde je k dispozici, a posílá ji do cloudové služby Better Mobile, kde se posoudí ohrožení zařízení mobilními hrozbami.

Zásady dodržování předpisů, které platí pro zařízení v Intune, zahrnují pravidlo pro službu ochrany před mobilními hrozbami. Toto pravidlo je založené na hodnocení rizika službou Better Mobile. Když je toto pravidlo aktivní, Intune vyhodnocuje soulad zařízení se zásadami, které jste povolili. Pokud se zjistí, že zařízení nesplňuje dané předpisy, zablokuje se přístup uživatelů k podnikovým prostředkům, jako jsou Exchange Online a SharePoint Online. Uživatelé dostanou také pokyny z mobilní aplikace Better Mobile nainstalované na jejich zařízeních, jak problém vyřešit a jak opět získat přístup k firemním prostředkům.

## <a name="sample-scenarios"></a>Ukázkové scénáře

Zde jsou uvedeny některé obvyklé scénáře.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Řízení přístupu na základě hrozeb od škodlivých aplikací

Když se na zařízeních zjistí přítomnost škodlivých aplikací (třeba malwaru), můžete jim až do vyřešení problému zablokovat následující akce:

- Připojení k firemnímu e-mailu

- Synchronizaci firemních souborů přes OneDrive for Work

- Přístup k aplikacím společnosti

**Zablokování při zjištění přítomnosti škodlivých aplikací:**

![Obrázek zobrazující zjištěné škodlivé aplikace](./media/better_mobile_maliciousapps_blocked.png)

**Přístup udělený po nápravě:**

![Udělení přístupu po zjištění přítomnosti škodlivých aplikací](./media/better_mobile_maliciousapps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Řízení přístupu na základě ohrožení sítě

Zjišťuje ohrožení vaší sítě, například útoky **prostředníkem**, a chrání přístup k sítím Wi-Fi na základě rizika zařízení.

**Zablokování přístupu k síti prostřednictvím sítě Wi-Fi:**

![Zablokování přístupu k síti prostřednictvím sítě Wi-Fi](./media/better_mobile_network_wifi_blocked.png)

**Přístup udělený po nápravě:**

![Obrázek, který zobrazuje přístup udělený při nápravě](./media/better_mobile_network_wifi_unblocked.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Řízení přístupu k SharePointu Online na základě ohrožení sítě

Zjišťuje ohrožení vaší sítě, například útoky **prostředníkem**, a zabraňuje synchronizaci podnikových souborů na základě rizika zařízení.

**Zablokování SharePointu Online v případě, že se zjistí ohrožení sítě:**

![Zablokování SharePointu Online v případě zjištění ohrožení sítě](./media/better_mobile_network_spo_blocked.png)

**Přístup udělený po nápravě:**

![Sharepointový příklad přístupu uděleného po nápravě](./media/better_mobile_network_spo_unblocked.png)

## <a name="supported-platforms"></a>Podporované platformy

- **Android 4.1 nebo novější**

- **iOS 8.0 a novější**

## <a name="prerequisites"></a>Požadavky

- Azure Active Directory Premium

- Odběr služby Microsoft Intune

- Předplatné ochrany před mobilními hrozbami Better Mobile

  - Další informace najdete na [webu Better Mobile](https://www.better.mobi/).

## <a name="next-steps"></a>Další postup

- [Integrace Better Mobile s Intune](better-mobile-mtd-connector-integration.md)

- [Nastavení aplikací Better Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Vytvoření zásad dodržování předpisů pro zařízení s Better Mobile](mtd-device-compliance-policy-create.md)

- [Povolení konektoru MTD Better Mobile](mtd-connector-enable.md)
