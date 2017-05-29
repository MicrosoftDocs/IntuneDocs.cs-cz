---
title: "Konektor ochrany před mobilními hrozbami Skycure| Dokumentace Microsoftu"
description: "Chraňte přístup k firemním prostředkům podle rizika zařízení, sítě a aplikace prostřednictvím konektoru ochrany před mobilními hrozbami Skycure a služby Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7a004e6c-604a-448c-bfb8-cfda63749f5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 15b00957f694863bb10ee32162eb20fc39bcda88
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="skycure-mobile-threat-defense-connector"></a>Konektor ochrany před mobilními hrozbami Skycure

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Přístup mobilních zařízení k podnikovým prostředkům můžete regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Skycure. Je to řešení ochrany před mobilními hrozbami integrované ve službě Microsoft Intune. Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých běží služba Skycure. Patří do ní:

-   Fyzická ochrana

-   Síťová ochrana

-   Ochrana aplikací

-   Ochrana chyb zabezpečení

Zásady podmíněného přístupu založené na posouzení rizika služby Skycure můžete nakonfigurovat prostřednictvím zásad dodržování předpisů zařízení služby Intune, kterými můžete na základě odhalených hrozeb u zařízení, které nedodržují předpisy, povolit nebo zablokovat přístup k firemním prostředkům.

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a>Jak služby Intune a Skycure pomáhají chránit prostředky společnosti?

Mobilní aplikace Skycure pro Android nebo iOS zaznamenává telemetrii systému souborů, zásobníku sítě, zařízení a aplikací tam, kde je k dispozici, a posílá ji do cloudové služby Skycure, kde se posoudí ohrožení zařízení mobilními hrozbami.

Zásady dodržování předpisů zařízení služby Intune zahrnují pravidlo pro ochranu proti mobilním hrozbám Skycure, která funguje na základě posouzení rizika služby Skycure. Když je toto pravidlo aktivní, Intune vyhodnocuje soulad zařízení se zásadami, které jste povolili.

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

![Zjištění přítomnosti škodlivých aplikací](../media/mtp/skycure-arch-1.png)

**Přístup udělený po nápravě:**

![Udělení přístupu po zjištění přítomnosti škodlivých aplikací](../media/mtp/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Řízení přístupu na základě ohrožení sítě

Zjišťuje hrozby v síti, například **útoky prostředníkem**, a chrání přístup k sítím Wi-Fi na základě rizika zařízení.

**Zablokování přístupu k síti prostřednictvím sítě Wi-Fi:**

![Zablokování přístupu k síti prostřednictvím sítě Wi-Fi](../media/mtp/skycure-arch-3.png)

**Přístup udělený po nápravě:**

![Přístup udělený po nápravě](../media/mtp/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Řízení přístupu k SharePointu Online na základě ohrožení sítě

Zjišťuje hrozby v síti, například **útoky prostředníkem**, a zabraňuje synchronizaci podnikových souborů na základě rizika zařízení.

**Zablokování SharePointu Online v případě, že se zjistí ohrožení sítě:**

![Zablokování SharePointu Online v případě zjištění ohrožení sítě](../media/mtp/skycure-arch-5.png)

**Přístup udělený po nápravě:**

![Sharepointový příklad přístupu uděleného po nápravě](../media/mtp/skycure-arch-6.png)

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

1.  [Konfigurace Skycure na použití jednotného přihlašování ke službě Azure Active Directory /intune-classic/deploy-use/configure-skycure-to-use-azure-active-directory-single-sign-on)

2.  [Stažení zásad konfigurace aplikace Skycure pro iOS](/intune-classic/deploy-use/download-skycure-ios-app-configuration-policy)

3.  [Přidání aplikací Skycure, aplikace Microsoft Authenticator a zásad konfigurace aplikace pro iOS](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)

4.  [Nasazení aplikací Skycure, aplikace Microsoft Authenticator a zásad konfigurace aplikace pro iOS](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)

5.  [Nastavení integrace služby Skycure se službou Intune](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

6.  [Povolení ochrany před mobilními hrozbami Skycure ve službě Intune](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

7.  [Vytvoření zásad dodržování předpisů pro ochranu před mobilními hrozbami Skycure ve službě Intune](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)

