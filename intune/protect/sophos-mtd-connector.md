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
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9bacc784b9d9498196186b1fac0ef948789832b5
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306836"
---
# <a name="sophos-mobile-threat-defense-connector-with-intune"></a>Nastavení konektoru ochrany před mobilními hrozbami v Intune
Přístup mobilních zařízení k podnikovým prostředkům můžete řídit pomocí podmíněného přístupu na základě posouzení rizik, které provádí společnost Sophos Mobile, řešení ochrany před mobilními hrozbami (MTD), které se integruje s Microsoft Intune. Riziko se vyhodnocuje na základě telemetrie shromážděných ze zařízení s mobilní aplikací Sophos.
Na základě zásad dodržování předpisů zařízením v Intune můžete nakonfigurovat zásady podmíněného přístupu, které jsou založené na nástroji Sophos Mobile Threat Assessment, které můžete použít k povolení nebo blokování zařízení nesplňujících požadavky pro přístup k podnikovým prostředkům na základě zjištěných hrozeb.

## <a name="how-do-intune-and-sophos-mobile-help-protect-your-company-resources"></a>Jak Intune a Sophos Mobile chrání firemní prostředky?
Mobilní aplikace Sophos pro Android a iOS zaznamenává telemetrii systému souborů, zásobníku sítě, zařízení a aplikací tam, kde je k dispozici, a poté odesílá data telemetrie do mobilní cloudové služby Sophos, aby zhodnotila riziko zařízení pro mobilní hrozby.
Zásady dodržování předpisů pro zařízení v Intune obsahují pravidlo pro ochranu před mobilními hrozbami, které je založené na posouzení rizikového mobilního rizika pro Sophos. Když je toto pravidlo povolené, Intune vyhodnotí dodržování předpisů zařízením pomocí zásad, které jste povolili. Pokud zařízení nedodržuje předpisy, uživatelé budou mít blokovaný přístup k firemním prostředkům, jako je Exchange Online a SharePoint Online. Uživatelé také dostanou pokyny z mobilní aplikace Sophos nainstalované ve svých zařízeních k vyřešení problému a opětovnému získání přístupu k podnikovým prostředkům.  

## <a name="sample-scenarios"></a>Ukázkové scénáře
Tady je několik běžných scénářů.  
### <a name="control-access-based-on-threats-from-malicious-apps"></a>Řízení přístupu na základě hrozeb ze škodlivých aplikací
Když se na zařízeních zjistí škodlivá aplikace, jako je malware, můžete zablokovat zařízení z následujících akcí, dokud se hrozby nevyřeší:
- Připojení k firemnímu e-mailu
- Synchronizace podnikových souborů pomocí aplikace OneDrive for Work
- Přístup k podnikovým aplikacím

**Blokovat při zjištění škodlivých aplikací**:
 
![Zjistila se koncepční bitová kopie škodlivých aplikací.](./media/sophos-mtd-connector/sophos_malicious_apps_blocked.png)  

**Přístup udělen při nápravě**:  
@no__t – bitová kopie přístupu udělená po nápravě @ no__t-1

### <a name="control-access-based-on-threat-to-network"></a>Řízení přístupu na základě hrozeb v síti  
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

## <a name="prerequisites"></a>Předpoklady  
- Azure Active Directory Premium
- Předplatné Microsoft Intune 
- Předplatné ochrany před mobilními hrozbami v Sophos

Další informace najdete na [webu Sophos](https://www.sophos.com/products/mobile-control).  

## <a name="next-steps"></a>Další kroky  
- [Integrace Sophos s Intune](sophos-mtd-connector-integration.md)
- [Nastavení aplikací Sophos](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Vytvořit zásady dodržování předpisů zařízením Sophos](mtd-device-compliance-policy-create.md)
- [Povolit konektor Sophos MTD](mtd-connector-enable.md)
