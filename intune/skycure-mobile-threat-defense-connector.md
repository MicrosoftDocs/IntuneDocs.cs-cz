---
title: Konektor Skycure s Intune
titlesuffix: Azure portal
description: Integrace konektoru Skycure do Intune
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 333322022882566b55e869e5d6a1a1e2b203b830
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/23/2018
---
# <a name="skycure-mobile-threat-defense-connector"></a>Konektor ochrany před mobilními hrozbami Skycure

Přístup mobilních zařízení k podnikovým prostředkům můžete regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Skycure. Je to řešení ochrany před mobilními hrozbami integrované ve službě Microsoft Intune. Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých běží služba Skycure. Patří do ní:

-   Fyzická ochrana

-   Síťová ochrana

-   Ochrana aplikací

-   Ochrana chyb zabezpečení

Zásady podmíněného přístupu založené na posouzení rizika služby Skycure můžete nakonfigurovat prostřednictvím zásad dodržování předpisů zařízení služby Intune, kterými můžete na základě odhalených hrozeb u zařízení, které nedodržují předpisy, povolit nebo zablokovat přístup k firemním prostředkům.

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a>Jak služby Intune a Skycure pomáhají chránit prostředky společnosti?

Mobilní aplikace Skycure pro Android nebo iOS zaznamenává telemetrii systému souborů, zásobníku sítě, zařízení a aplikací tam, kde je k dispozici, a posílá ji do cloudové služby Skycure, kde se posoudí ohrožení zařízení mobilními hrozbami.

Zásady dodržování předpisů, které platí pro zařízení v Intune, zahrnují pravidlo pro službu ochrany před mobilními hrozbami Skycure. Toto pravidlo je založené na hodnocení rizika službou Skycure. Když je toto pravidlo aktivní, Intune vyhodnocuje soulad zařízení se zásadami, které jste povolili.

Pokud se zjistí, že zařízení dané předpisy nedodržuje, zablokuje se přístup k prostředkům, jako jsou Exchange Online a SharePoint Online. Uživatelé zablokovaných zařízení obdrží od mobilní aplikace Skycure pokyny, jak problém vyřešit a jak opět získat přístup k firemním prostředkům.

Služba Intune podporuje dva způsoby integrace se službou Skycure:

-   **Základní nastavení**: Umožňuje v režimu jen pro čtení službě Skycure viditelnost zařízení ve službě Intune.

-   **Úplná integrace**: Umožňuje službě Skycure nahlásit riziko zařízení a podrobnosti bezpečnostního incidentu službě Intune.

## <a name="sample-scenarios"></a>Ukázkové scénáře

Zde jsou uvedeny některé obvyklé scénáře:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Řízení přístupu na základě hrozeb od škodlivých aplikací

Když se na zařízeních zjistí přítomnost škodlivých aplikací (třeba malwaru), můžete jim až do vyřešení problému zablokovat následující:

-   Připojení k firemnímu e-mailu

-   Synchronizaci firemních souborů přes OneDrive for Work

-   Přístup k aplikacím společnosti

**Zablokování při zjištění přítomnosti škodlivých aplikací:**

![Zjištění přítomnosti škodlivých aplikací](./media/skycure-arch-1.png)

**Přístup udělený po nápravě:**

![Udělení přístupu po zjištění přítomnosti škodlivých aplikací](./media/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Řízení přístupu na základě ohrožení sítě

Zjišťuje hrozby v síti, například **útoky prostředníkem**, a chrání přístup k sítím Wi-Fi na základě rizika zařízení.

**Zablokování přístupu k síti prostřednictvím sítě Wi-Fi:**

![Zablokování přístupu k síti prostřednictvím sítě Wi-Fi](./media/skycure-arch-3.png)

**Přístup udělený po nápravě:**

![Přístup udělený po nápravě](./media/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Řízení přístupu k SharePointu Online na základě ohrožení sítě

Zjišťuje hrozby v síti, například **útoky prostředníkem**, a zabraňuje synchronizaci podnikových souborů na základě rizika zařízení.

**Zablokování SharePointu Online v případě, že se zjistí ohrožení sítě:**

![Zablokování SharePointu Online v případě zjištění ohrožení sítě](./media/skycure-arch-5.png)

**Přístup udělený po nápravě:**

![Sharepointový příklad přístupu uděleného po nápravě](./media/skycure-arch-6.png)

## <a name="supported-platforms"></a>Podporované platformy

-   **Android 4.1 nebo novější**

-   **iOS 8 nebo novější**

## <a name="pre-requisites"></a>Požadavky

-   Azure Active Directory Premium

-   Odběr služby Microsoft Intune

-   Předplatné ochrany před mobilními hrozbami Skycure

Více informací najde na [webu Skycure](https://www.skycure.com/skycure-microsoft-integration/).

## <a name="next-steps"></a>Další kroky

Zde jsou uvedené další kroky, které potřebujete k integraci služby Intune se službou Skycure:

- [Nastavení integrace služby Skycure se službou Intune](skycure-mtd-connector-integration.md)

- [Přidání a přiřazení aplikací Skycure, aplikace Microsoft Authenticator a zásad konfigurace aplikace pro iOS](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Vytvoření zásad dodržování předpisů pro zařízení se službou Skycure v Intune](mtd-device-compliance-policy-create.md)

- [Povolení konektoru MTD Skycure v Intune](mtd-connector-enable.md)
