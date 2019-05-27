---
title: Nastavení integrace Sophos Mobile s Intune
titleSuffix: Intune on Azure
description: Jak nastavit řešení Sophos Mobile v Microsoft Intune pro řízení přístupu mobilních zařízení k firemním prostředkům.
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
ms.openlocfilehash: 4363bb4feba52c15b8918a7c6ea02fa2917a00de
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66044943"
---
# <a name="sophos-mobile-threat-defense-connector-with-intune"></a>Konektor Sophos Mobile Threat Defense s Intune
Můžete řídit přístup mobilních zařízení k firemním prostředkům pomocí podmíněného přístupu založené na posouzení rizik, které Sophos Mobile řešení Mobile Threat Defense (MTD), která se integruje s Microsoft Intune. Riziko se posuzuje na základě telemetrie se shromažďuje ze zařízení se systémem Sophos mobilní aplikace.
Můžete nakonfigurovat zásady podmíněného přístupu založené na posouzení rizika Sophos Mobile povolené prostřednictvím zásad dodržování předpisů zařízení Intune, které vám umožní povolit nebo blokovat zařízení nedodržující předpisy přístup k firemním prostředkům na základě zjištěných hrozeb.

## <a name="how-do-intune-and-sophos-mobile-help-protect-your-company-resources"></a>Jak Intune a mobilní zařízení Sophos pomáhají chránit prostředky společnosti?
Sophos mobilní aplikace pro Android a iOS zaznamenává systém souborů, zásobníku sítě, zařízení a telemetrie application, pokud je k dispozici a potom odesílá telemetrická data do cloudové služby Sophos Mobile se posoudí ohrožení zařízení mobilními hrozbami.
Zásady dodržování předpisů zařízení služby Intune zahrnují pravidlo pro Sophos Mobile Threat Defense, který je založen na posouzení rizika Sophos Mobile. Když je toto pravidlo aktivní, Intune vyhodnocuje soulad zařízení se zásadami, které jste povolili. Pokud se zjistí, že zařízení nesplňuje dané předpisy, zablokuje se přístup uživatelů k podnikovým prostředkům, jako jsou Exchange Online a SharePoint Online. Uživatelé dostanou také pokyny z mobilní zařízení Sophos aplikace nainstalované na jejich zařízeních, jak problém vyřešit a jak opět získat přístup k firemním prostředkům.  

## <a name="sample-scenarios"></a>Ukázkové scénáře
Zde jsou uvedeny některé obvyklé scénáře.  
### <a name="control-access-based-on-threats-from-malicious-apps"></a>Řízení přístupu na základě hrozeb od škodlivých aplikací
Když se na zařízeních zjistí přítomnost škodlivých aplikací (třeba malwaru), můžete jim až do vyřešení problému zablokovat následující akce:
- Připojení k firemnímu e-mailu
- Synchronizaci firemních souborů přes OneDrive for Work
- Přístup k aplikacím společnosti

**Zablokování, když se zjistí škodlivé aplikace**:
 
![Koncepčního obrázku zjištění přítomnosti škodlivých aplikací](./media/sophos-mtd-connector/sophos_malicious_apps_blocked.png)  

**Přístup udělený po nápravě**:  
![Koncepčního obrázku povoleného přístupu po nápravě](./media/sophos-mtd-connector/sophos_malicious_apps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Řízení přístupu na základě ohrožení sítě  
Zjišťuje ohrožení vaší sítě, jako jsou útoky Man-in-the-middle a chrání přístup k sítím Wi-Fi na základě rizika zařízení.  

**Zablokování přístupu k síti prostřednictvím sítě Wi-Fi**:  
![Zablokování přístupu k síti prostřednictvím sítě Wi-Fi](./media/sophos-mtd-connector/sophos_network_wifi_blocked.png)

**Přístup udělený po nápravě**:   
![Přístup udělený po nápravě](./media/sophos-mtd-connector/sophos_network_wifi_unblocked.png)  

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Řízení přístupu k SharePointu Online na základě ohrožení sítě  
Zjišťuje ohrožení vaší sítě, jako jsou útoky Man-in-the-middle a zabraňuje synchronizaci podnikových souborů na základě rizika zařízení.  

**Zablokování Sharepointu Online v případě zjištění ohrožení sítě**:   
![Zablokování Sharepointu Online v případě zjištění ohrožení sítě](./media/sophos-mtd-connector/sophos_network_spo_blocked.png)  

**Přístup udělený po nápravě**:  
![Přístup udělený po nápravě Sharepointový příklad](./media/sophos-mtd-connector/sophos_network_spo_unblocked.png)  

## <a name="supported-platforms"></a>Podporované platformy  
- Android 5.0 nebo novější
- Iosu 11.0 a novějších

## <a name="prerequisites"></a>Požadavky  
- Azure Active Directory Premium
- Odběr služby Microsoft Intune 
- Předplatné Sophos Mobile Threat Defense

Další informace najdete v tématu [Sophos webu](https://www.sophos.com/products/mobile-control).  

## <a name="next-steps"></a>Další postup  
- [Sophos integrace s Intune](sophos-mtd-connector-integration.md)
- [Nastavení Sophos aplikací](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Vytvoření zásad dodržování předpisů zařízení Sophos](mtd-device-compliance-policy-create.md)
- [Povolení konektoru Sophos MTD](mtd-connector-enable.md)
