---
title: Konektor Symantec s Microsoft Intune
titleSuffix: Microsoft Intune
description: Přečtěte si o integraci Intune se Symantec Endpoint Protection Mobile za účelem regulace přístupu mobilních zařízení k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/09/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6480c6fb412c12e228b8bc3647045cf15da531e1
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2019
ms.locfileid: "67548016"
---
# <a name="symantec-endpoint-protection-mobile-connector"></a>Konektor Symantec Endpoint Protection Mobile

Můžete řídit přístup mobilních zařízení k firemním prostředkům pomocí podmíněného přístupu na základě posouzení rizik, které provádí aplikace Symantec Endpoint Protection Mobile (SEP Mobile) je řešení ochrany před mobilními hrozbami, která se integruje s Microsoft Intune. Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých běží SEP Mobile. Patří do ní:

- Fyzická ochrana

- Síťová ochrana

- Ochrana aplikací

- Ochrana chyb zabezpečení

Můžete povolit hodnocení rizik SEP Mobile prostřednictvím zásad dodržování předpisů zařízení služby Intune a zásady podmíněného přístupu pak můžete povolit nebo blokovat zařízení nedodržující předpisy přístup k firemním prostředkům na základě odhalených hrozeb.

## <a name="how-do-intune-and-sep-mobile-help-protect-your-company-resources"></a>Jak Intune a SEP Mobile pomáhají chránit prostředky společnosti?

SEP Mobile pro Android nebo iOS zaznamenává telemetrii systému souborů, zásobníku sítě, zařízení a aplikací tam, kde je k dispozici, a posílá ji do cloudové služby Symantec, kde se posoudí ohrožení zařízení mobilními hrozbami.

Zásady dodržování předpisů, které platí pro zařízení v Intune, zahrnují pravidlo pro SEP Mobile, které je založené na hodnocení rizik službou SEP Mobile. Když je toto pravidlo aktivní, Intune vyhodnocuje soulad zařízení se zásadami, které jste povolili.

Pokud se zjistí, že zařízení dané předpisy nedodržuje, zablokuje se přístup k prostředkům, jako jsou Exchange Online a SharePoint Online. Uživatelé zablokovaných zařízení obdrží od aplikace SEP Mobile pokyny, jak problém vyřešit a jak k firemním prostředkům znovu získat přístup.

Intune podporuje dva režimy integrace s SEP Mobile:

- **Základní nastavení**: Umožňuje v režimu jen pro čtení službě SEP Mobile viditelnost zařízení v Intune.

- **Úplná integrace**: Umožňuje službě SEP Mobile nahlásit riziko zařízení a podrobnosti bezpečnostního incidentu službě Intune.

## <a name="sample-scenarios"></a>Ukázkové scénáře

Zde jsou uvedeny některé obvyklé scénáře:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Řízení přístupu na základě hrozeb od škodlivých aplikací

Když se na zařízeních zjistí přítomnost škodlivých aplikací (třeba malwaru), můžete jim až do vyřešení problému zablokovat následující:

- Připojení k firemnímu e-mailu

- Synchronizaci firemních souborů přes OneDrive for Work

- Přístup k aplikacím společnosti

**Zablokování při zjištění přítomnosti škodlivých aplikací:**

![Koncepčního obrázku zjištění přítomnosti škodlivých aplikací](./media/symantec-arch-1.png)

**Přístup udělený po nápravě:**

![Obrázek přistup udělený po nápravě po zjištění přítomnosti škodlivých aplikací](./media/symantec-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Řízení přístupu na základě ohrožení sítě

Zjišťuje hrozby v síti, například **útoky prostředníkem**, a chrání přístup k sítím Wi-Fi na základě rizika zařízení.

**Zablokování přístupu k síti prostřednictvím sítě Wi-Fi:**

![Zablokování přístupu k síti prostřednictvím sítě Wi-Fi](./media/symantec-arch-3.png)

**Přístup udělený po nápravě:**

![Přístup udělený po nápravě](./media/symantec-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Řízení přístupu k SharePointu Online na základě ohrožení sítě

Zjišťuje hrozby v síti, například **útoky prostředníkem**, a zabraňuje synchronizaci podnikových souborů na základě rizika zařízení.

**Zablokování SharePointu Online v případě, že se zjistí ohrožení sítě:**

![Zablokování SharePointu Online v případě zjištění ohrožení sítě](./media/symantec-arch-5.png)

**Přístup udělený po nápravě:**

![Sharepointový příklad přístupu uděleného po nápravě](./media/symantec-arch-6.png)

## <a name="supported-platforms"></a>Podporované platformy

- **Android 4.1 nebo novější**

- **iOS 8 nebo novější**

## <a name="pre-requisites"></a>Požadavky

- Azure Active Directory Premium

- Odběr služby Microsoft Intune

- Předplatné Symantec Endpoint Protection Mobile

Více informací najde na [webu Symantecu](https://www.skycure.com/skycure-microsoft-integration/).

## <a name="next-steps"></a>Další postup

K integraci Intune s SEP Mobile musíte dokončit tyto kroky:

- [Nastavení integrace SEP Mobile s Intune](skycure-mtd-connector-integration.md)

- [Přidání a přiřazení aplikací SEP Mobile, Microsoft Authenticatoru a zásad konfigurace aplikace pro iOS](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Vytvoření zásad dodržování předpisů pro zařízení s SEP Mobile v Intune](mtd-device-compliance-policy-create.md)

- [Povolení konektoru MTD SEP Mobile v Intune](mtd-connector-enable.md)
