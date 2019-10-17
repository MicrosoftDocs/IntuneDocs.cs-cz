---
title: Použití programu Sophos Mobile s Intune
titleSuffix: Intune on Azure
description: Jak používat mobilní řešení Sophos s Microsoft Intune k řízení přístupu mobilních zařízení k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: e8823aa8467ef380223a486874c68d52926db733
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503743"
---
# <a name="sophos-mobile-threat-defense-connector-with-intune"></a>Nastavení konektoru ochrany před mobilními hrozbami v Intune
Přístup mobilních zařízení k podnikovým prostředkům můžete řídit pomocí podmíněného přístupu na základě posouzení rizik, které provádí společnost Sophos Mobile, řešení ochrany před mobilními hrozbami (MTD), které se integruje s Microsoft Intune. Riziko se vyhodnocuje na základě telemetrie shromážděných ze zařízení s mobilní aplikací Sophos.
Na základě zásad dodržování předpisů zařízením v Intune můžete nakonfigurovat zásady podmíněného přístupu, které jsou založené na nástroji Sophos Mobile Threat Assessment, které můžete použít k povolení nebo blokování zařízení nesplňujících požadavky pro přístup k podnikovým prostředkům na základě zjištěných hrozeb.

## <a name="how-do-intune-and-sophos-mobile-help-protect-your-company-resources"></a>Jak Intune a Sophos Mobile chrání firemní prostředky?
Mobilní aplikace Sophos pro Android a iOS zaznamenává telemetrii systému souborů, zásobníku sítě, zařízení a aplikací tam, kde je k dispozici, a poté odesílá data telemetrie do mobilní cloudové služby Sophos, aby zhodnotila riziko zařízení pro mobilní hrozby.
Zásady dodržování předpisů pro zařízení v Intune obsahují pravidlo pro ochranu před mobilními hrozbami, které je založené na posouzení rizikového mobilního rizika pro Sophos. Když je toto pravidlo aktivní, Intune vyhodnocuje soulad zařízení se zásadami, které jste povolili. Pokud se zjistí, že zařízení nesplňuje dané předpisy, zablokuje se přístup uživatelů k podnikovým prostředkům, jako jsou Exchange Online a SharePoint Online. Uživatelé také dostanou pokyny z mobilní aplikace Sophos nainstalované ve svých zařízeních k vyřešení problému a opětovnému získání přístupu k podnikovým prostředkům.  

## <a name="sample-scenarios"></a>Ukázkové scénáře
Zde jsou uvedeny některé obvyklé scénáře.  
### <a name="control-access-based-on-threats-from-malicious-apps"></a>Řízení přístupu na základě hrozeb od škodlivých aplikací
Když se na zařízeních zjistí přítomnost škodlivých aplikací (třeba malwaru), můžete jim až do vyřešení problému zablokovat následující akce:
- Připojení k firemnímu e-mailu
- Synchronizaci firemních souborů přes OneDrive for Work
- Přístup k aplikacím společnosti

**Blokovat při zjištění škodlivých aplikací**:
 
![Zjistila se koncepční bitová kopie škodlivých aplikací.](./media/sophos-mtd-connector/sophos_malicious_apps_blocked.png)  

**Přístup udělen při nápravě**:  
@no__t – bitová kopie přístupu udělená po nápravě @ no__t-1

### <a name="control-access-based-on-threat-to-network"></a>Řízení přístupu na základě ohrožení sítě  
Detekuje hrozby pro vaši síť, jako jsou útoky prostředníkem, a chrání přístup k sítím Wi-Fi na základě rizika zařízení.  

**Blokovat přístup k síti přes Wi-Fi**:  
přístup k síti @no__t 0Block prostřednictvím Wi-Fi @ no__t-1

**Přístup udělen při nápravě**:   
@no__t – 0Access udělené při nápravě @ no__t-1  

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Řízení přístupu k SharePointu Online na základě ohrožení sítě  
Detekuje hrozby pro vaši síť, jako jsou útoky prostředníkem, a zabraňuje synchronizaci podnikových souborů na základě rizika zařízení.  

**Zablokovat SharePoint Online, když jsou zjištěny hrozby sítě**:   
@no__t – 0Block SharePoint Online, když se zjistí hrozby sítě @ no__t-1  

**Přístup udělen při nápravě**:  
@no__t – 0Access udělené při nápravě pro SharePoint – příklad @ no__t-1  

## <a name="supported-platforms"></a>Podporované platformy  
- Android 5,0 a novější
- iOS 11,0 a novější

## <a name="prerequisites"></a>Požadované součásti  
- Azure Active Directory Premium
- Odběr služby Microsoft Intune 
- Předplatné ochrany před mobilními hrozbami v Sophos

Další informace najdete na [webu Sophos](https://www.sophos.com/products/mobile-control).  

## <a name="next-steps"></a>Další kroky  
- [Integrace Sophos s Intune](sophos-mtd-connector-integration.md)
- [Nastavení aplikací Sophos](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Vytvořit zásady dodržování předpisů zařízením Sophos](mtd-device-compliance-policy-create.md)
- [Povolit konektor Sophos MTD](mtd-connector-enable.md)
