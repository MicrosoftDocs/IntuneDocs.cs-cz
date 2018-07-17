---
title: Konektor Pradeo Mobile Threat Defense s Intune
titleSuffix: Intune on Azure
description: Nastavte konektor Pradeo Mobile Threat Defense s Intune.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 06/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cde4d389-1770-4226-85a3-a2f3b3fb92a3
ms.openlocfilehash: b518c51cb49fe8a70c6ed8918c0c88dcd599d915
ms.sourcegitcommit: f70d6aaea59b52cd0d7bd3008afd243868967fd6
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2018
ms.locfileid: "37067456"
---
# <a name="pradeo-mobile-threat-defense-connector-with-intune"></a>Konektor Pradeo Mobile Threat Defense s Intune

Přístup mobilních zařízení k podnikovým prostředkům můžete regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Pradeo. Je to řešení ochrany před mobilními hrozbami (MTD), které se integruje s Microsoft Intune. Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých aplikace Pradeo běží.

Zásady podmíněného přístupu založené na posouzení rizika služby Pradeo můžete nakonfigurovat prostřednictvím zásad dodržování předpisů zařízení služby Intune, kterými můžete na základě odhalených hrozeb u zařízení nedodržujících předpisy povolit nebo zablokovat přístup k firemním prostředkům.

## <a name="how-do-intune-and-pradeo-help-protect-your-company-resources"></a>Jak služby Intune a Pradeo pomáhají chránit prostředky společnosti?

Aplikace Pradeo pro Android a iOS zaznamenává telemetrii systému souborů, zásobníku sítě, zařízení a aplikací tam, kde je k dispozici, a potom ji posílá do cloudové služby Pradeo, kde se posoudí ohrožení zařízení mobilními hrozbami.

Zásady dodržování předpisů, které platí pro zařízení v Intune, zahrnují pravidlo pro službu ochrany před mobilními hrozbami Pradeo. Toto pravidlo je založené na hodnocení rizika službou Pradeo. Když je toto pravidlo aktivní, Intune vyhodnocuje soulad zařízení se zásadami, které jste povolili. Pokud se zjistí, že zařízení nesplňuje dané předpisy, zablokuje se přístup uživatelů k podnikovým prostředkům, jako jsou Exchange Online a SharePoint Online. Uživatelé dostanou také pokyny z mobilní aplikace Pradeo nainstalované na jejich zařízeních, jak problém vyřešit a jak opět získat přístup k firemním prostředkům.

## <a name="sample-scenarios"></a>Ukázkové scénáře

Zde jsou uvedeny některé obvyklé scénáře.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Řízení přístupu na základě hrozeb od škodlivých aplikací

Když se na zařízeních zjistí přítomnost škodlivých aplikací (třeba malwaru), můžete jim až do vyřešení problému zablokovat následující akce:

-   Připojení k firemnímu e-mailu

-   Synchronizaci firemních souborů přes OneDrive for Work

-   Přístup k aplikacím společnosti

**Zablokování při zjištění přítomnosti škodlivých aplikací:**

![Zjištění přítomnosti škodlivých aplikací](./media/pradeo_maliciousapps_blocked.png)

**Přístup udělený po nápravě:**

![Udělení přístupu po zjištění přítomnosti škodlivých aplikací](./media/pradeo_maliciousapps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Řízení přístupu na základě ohrožení sítě

Zjišťuje ohrožení vaší sítě, například útoky **prostředníkem**, a chrání přístup k sítím Wi-Fi na základě rizika zařízení.

**Zablokování přístupu k síti prostřednictvím sítě Wi-Fi:**

![Zablokování přístupu k síti prostřednictvím sítě Wi-Fi](./media/pradeo_network_wifi_blocked.png)

**Přístup udělený po nápravě:**

![Přístup udělený po nápravě](./media/pradeo_network_wifi_unblocked.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Řízení přístupu k SharePointu Online na základě ohrožení sítě

Zjišťuje ohrožení vaší sítě, například útoky **prostředníkem**, a zabraňuje synchronizaci podnikových souborů na základě rizika zařízení.

**Zablokování SharePointu Online v případě, že se zjistí ohrožení sítě:**

![Zablokování SharePointu Online v případě zjištění ohrožení sítě](./media/pradeo_network_spo_blocked.png)

**Přístup udělený po nápravě:**

![Sharepointový příklad přístupu uděleného po nápravě](./media/pradeo_network_spo_unblocked.png)

## <a name="supported-platforms"></a>Podporované platformy

-   **Android 4.0.3 nebo novější**

-   **iOS 7 nebo novější**

## <a name="prerequisites"></a>Požadavky

-   Azure Active Directory Premium

-   Odběr služby Microsoft Intune

-   Předplatné služby Pradeo Security for Mobile Threat Defense

    -   Další informace naleznete na [webu Pradeo](https://www.pradeo.com/en-US/mobile-threat-protection).

## <a name="next-steps"></a>Další kroky

- [Integrace služby Pradeo s Intune](pradeo-mtd-connector-integration.md)

- [Nastavení aplikací Pradeo](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Vytvoření zásady dodržování předpisů zařízení služby Pradeo](mtd-device-compliance-policy-create.md)

- [Povolení konektoru Pradeo MTD](mtd-connector-enable.md)