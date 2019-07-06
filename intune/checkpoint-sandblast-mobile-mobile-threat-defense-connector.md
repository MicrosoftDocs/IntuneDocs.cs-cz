---
title: Nastavení Check Point SandBlast MTD
titleSuffix: Microsoft Intune
description: Přečtěte si o integraci Intune se službou Check Point SandBlast Mobile Threat Defense za účelem regulace přístupu mobilních zařízení k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/03/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 706a4228-9bdf-41e0-b8d1-64c923dd2d2b
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f9438c3c566dc62acfa7567428ebe3a6a6be4777
ms.sourcegitcommit: ede86a3cb094c12e3e218b956abb9935bec76902
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/05/2019
ms.locfileid: "67572564"
---
# <a name="check-point-sandblast-mobile-threat-defense-connector-with-intune"></a>Konektor Check Point SandBlast Mobile Threat Defense s Intune

Můžete řídit přístup mobilních zařízení k firemním prostředkům pomocí podmíněného přístupu založené na posouzení rizik, které Check Point SandBlast Mobile, je řešení ochrany před mobilními hrozbami, která se integruje s Microsoft Intune. Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých běží služba Check Point SandBlast Mobile.

Můžete nakonfigurovat zásady podmíněného přístupu založené na posouzení rizika služby Check Point SandBlast Mobile povolené prostřednictvím zásad dodržování předpisů zařízení Intune, která vám umožní povolit nebo blokovat zařízení nedodržující předpisy přístup k firemním prostředkům na základě zjistil hrozby.

## <a name="how-do-intune-and-check-point-sandblast-mobile-help-protect-your-company-resources"></a>Jak pomáhají služby Intune a Check Point SandBlast Mobile chránit prostředky společnosti?

Aplikace Check Point Sandblast Mobile pro Android a iOS zaznamenává telemetrii systému souborů, zásobníku sítě, zařízení a aplikací tam, kde je k dispozici, a posílá ji do cloudové služby Check Point SandBlast, kde se posoudí ohrožení zařízení mobilními hrozbami.

Zásady dodržování předpisů zařízení služby Intune zahrnují pravidlo pro ochranu před mobilními hrozbami Check Point SandBlast, která je založená na posouzení rizika službou Check Point SandBlast. Když je toto pravidlo aktivní, Intune vyhodnocuje soulad zařízení se zásadami, které jste povolili. Pokud se zjistí, že zařízení nesplňuje dané předpisy, zablokuje se přístup uživatelů k podnikovým prostředkům, jako jsou Exchange Online a SharePoint Online. Uživatelé dostanou také pokyny z mobilní aplikace Check Point SandBlast nainstalované na jejich zařízeních, jak problém vyřešit a jak opět získat přístup k firemním prostředkům.

<!-- ## Sample scenarios 
closing syntax for comment above is missing. Please insert closing syntax at intended location. -->

Zde jsou uvedeny některé obvyklé scénáře:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Řízení přístupu na základě hrozeb od škodlivých aplikací

Když se na zařízeních zjistí přítomnost škodlivých aplikací (třeba malwaru), můžete jim až do vyřešení problému zablokovat následující:

- Připojení k firemnímu e-mailu

- Synchronizaci firemních souborů přes OneDrive for Work

- Přístup k aplikacím společnosti

**Zablokování při zjištění přítomnosti škodlivých aplikací:**

![Check Point MTD – zablokování při zjištění škodlivých aplikací](./media/checkpoint-MTD-2.PNG)

**Přístup udělený po nápravě:**

![Check Point MTD – udělení přístupu](./media/checkpoint-MTD-3.PNG)

### <a name="control-access-based-on-threat-to-network"></a>Řízení přístupu na základě ohrožení sítě

Zjišťuje hrozby v síti, například **útoky prostředníkem**, a chrání přístup k sítím Wi-Fi na základě rizika zařízení.

**Zablokování přístupu k síti prostřednictvím sítě Wi-Fi:**

![Check Point MTD – zablokování přístupu k síti přes Wi-Fi](./media/checkpoint-MTD-4.PNG)

**Přístup udělený po nápravě:**

![Check Point MTD – udělení přístupu přes Wi-Fi](./media/checkpoint-MTD-5.PNG)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Řízení přístupu k SharePointu Online na základě ohrožení sítě

Zjišťuje hrozby v síti, například **útoky prostředníkem**, a zabraňuje synchronizaci podnikových souborů na základě rizika zařízení.

**Zablokování SharePointu Online v případě, že se zjistí ohrožení sítě:**

![Check Point MTD – zablokování přístupu SharePointu Online](./media/checkpoint-MTD-6.PNG)

**Přístup udělený po nápravě:**

![Check Point MTD – udělení přístupu SharePointu Online](./media/checkpoint-MTD-7.PNG)

## <a name="supported-platforms"></a>Podporované platformy

- **Android 4.1 nebo novější**

- **iOS 8 nebo novější**

## <a name="pre-requisites"></a>Požadavky

- Azure Active Directory Premium

- Odběr služby Microsoft Intune

- Předplatné ochrany před mobilními hrozbami Check Point SandBlast
    - Další informace najdete na [webu služby CheckPoint SandBlast](https://www.checkpoint.com/).

## <a name="next-steps"></a>Další postup

- [Integrace služby CheckPoint SandBlast s Intune](checkpoint-sandblast-mobile-mtd-connector-integration.md)

- [Nastavení aplikace CheckPoint SandBlast Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Vytvoření zásad dodržování předpisů pro zařízení s CheckPoint SandBlast Mobile](mtd-device-compliance-policy-create.md)

- [Povolení konektoru CheckPoint SandBlast Mobile MTD](mtd-connector-enable.md)
