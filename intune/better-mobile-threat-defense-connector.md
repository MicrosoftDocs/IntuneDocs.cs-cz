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
ms.openlocfilehash: b8134b9db0e478efa69391edeb570b39c91a41c9
ms.sourcegitcommit: 84c79ceea27f7411528defc5ee8ba35ae2bf473c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2019
ms.locfileid: "67511771"
---
# <a name="better-mobile-threat-defense-connector-with-intune"></a>Konektor Better Mobile Threat Defense s Intune

Můžete řídit přístup mobilních zařízení k firemním prostředkům pomocí podmíněného přístupu na základě posouzení rizik, které provádí lepší mobilní řešení Mobile Threat Defense (MTD), která se integruje s Microsoft Intune. Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých aplikace Better Mobile běží.

Můžete nakonfigurovat zásady podmíněného přístupu založené na posouzení rizika lepší Mobile povolené prostřednictvím zásad dodržování předpisů zařízení Intune, které vám umožní povolit nebo blokovat zařízení nedodržující předpisy přístup k firemním prostředkům na základě zjištěných hrozeb.

## <a name="how-do-intune-and-better-mobile-help-protect-your-company-resources"></a>Jak Intune a Better Mobile pomáhají chránit prostředky společnosti?

Aplikace Better Mobile je nainstalovaná a spuštěná na mobilních zařízeních. Tato aplikace zaznamenává telemetrii systému souborů, zásobníku sítě, zařízení a aplikací tam, kde je k dispozici, a posílá ji do cloudové služby Better Mobile, kde se posoudí ohrožení zařízení mobilními hrozbami.

Zásady dodržování předpisů, které platí pro zařízení v Intune, zahrnují pravidlo pro službu ochrany před mobilními hrozbami. Toto pravidlo je založené na hodnocení rizika službou Better Mobile. Když je toto pravidlo aktivní, Intune vyhodnocuje soulad zařízení se zásadami, které jste povolili. Pokud se zjistí, že zařízení nesplňuje dané předpisy, zablokuje se přístup uživatelů k podnikovým prostředkům, jako jsou Exchange Online a SharePoint Online. Uživatelé dostanou také pokyny z mobilní aplikace Better Mobile nainstalované na jejich zařízeních, jak problém vyřešit a jak opět získat přístup k firemním prostředkům.

## <a name="sample-scenarios"></a>Ukázkové scénáře

Zde jsou uvedeny některé obvyklé scénáře.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Řízení přístupu na základě hrozeb od škodlivých aplikací

Když se na zařízeních zjistí přítomnost škodlivých aplikací (třeba malwaru), můžete jim až do vyřešení problému zablokovat následující akce:

-   Připojení k firemnímu e-mailu

-   Synchronizaci firemních souborů přes OneDrive for Work

-   Přístup k aplikacím společnosti

**Zablokování při zjištění přítomnosti škodlivých aplikací:**

![Obrázek znázorňující zjištění přítomnosti škodlivých aplikací](./media/better_mobile_maliciousapps_blocked.png)

**Přístup udělený po nápravě:**

![Udělení přístupu po zjištění přítomnosti škodlivých aplikací](./media/better_mobile_maliciousapps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Řízení přístupu na základě ohrožení sítě

Zjišťuje ohrožení vaší sítě, například útoky **prostředníkem**, a chrání přístup k sítím Wi-Fi na základě rizika zařízení.

**Zablokování přístupu k síti prostřednictvím sítě Wi-Fi:**

![Zablokování přístupu k síti prostřednictvím sítě Wi-Fi](./media/better_mobile_network_wifi_blocked.png)

**Přístup udělený po nápravě:**

![Obrázek znázorňující udělení přístupu nápravě](./media/better_mobile_network_wifi_unblocked.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Řízení přístupu k SharePointu Online na základě ohrožení sítě

Zjišťuje ohrožení vaší sítě, například útoky **prostředníkem**, a zabraňuje synchronizaci podnikových souborů na základě rizika zařízení.

**Zablokování SharePointu Online v případě, že se zjistí ohrožení sítě:**

![Zablokování SharePointu Online v případě zjištění ohrožení sítě](./media/better_mobile_network_spo_blocked.png)

**Přístup udělený po nápravě:**

![Sharepointový příklad přístupu uděleného po nápravě](./media/better_mobile_network_spo_unblocked.png)

## <a name="supported-platforms"></a>Podporované platformy

-   **Android 4.1 nebo novější**

-   **iOS 8.0 a novější**

## <a name="prerequisites"></a>Požadavky

-   Azure Active Directory Premium

-   Odběr služby Microsoft Intune

-   Předplatné ochrany před mobilními hrozbami Better Mobile

    -   Další informace najdete na [webu Better Mobile](https://www.better.mobi/).

## <a name="next-steps"></a>Další postup

- [Integrace Better Mobile s Intune](better-mobile-mtd-connector-integration.md)

- [Nastavení aplikací Better Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Vytvoření zásad dodržování předpisů pro zařízení s Better Mobile](mtd-device-compliance-policy-create.md)

- [Povolení konektoru MTD Better Mobile](mtd-connector-enable.md)
