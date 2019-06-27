---
title: Nastavení zabezpečení Wandera Mobile s Intune
titleSuffix: Intune on Azure
description: Jak nastavit zabezpečení Wandera mobilní zařízení pomocí Microsoft Intune pro řízení přístupu mobilních zařízení k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6219d4a176eebf81747461b3cc8b478e46e86898
ms.sourcegitcommit: 6bba9f2ef4d1ec699f5713a4da4f960e7317f1cd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2019
ms.locfileid: "67407691"
---
# <a name="wandera-mobile-threat-defense-connector-with-intune"></a>Konektor Wandera Mobile Threat Defense s Intune  

Řízení přístupu mobilních zařízení k firemním prostředkům pomocí podmíněného přístupu na základě posouzení rizik, které provádí Wandera. Wandera je řešení ochrany před mobilními hrozbami (MTD), která se integruje s Microsoft Intune.  Riziko se posuzuje na základě telemetrie ze zařízení shromažďuje služba Wandera, včetně:
- Ohrožení zabezpečení operačního systému
- Nainstalované škodlivé aplikace
- Škodlivé profily sítě
- Cryptojacking

Můžete nakonfigurovat *podmíněného přístupu* zásady, které jsou založeny na jeho Wandera rizika posouzení, se povoluje přes zásady dodržování předpisů zařízeními v Intune. Zásady rizik posouzení můžete povolit nebo blokovat zařízení nedodržující předpisy přístup k firemním prostředkům na základě zjištěných hrozeb.  


## <a name="how-do-intune-and-wandera-mobile-threat-defense-help-protect-your-company-resources"></a>Jak Intune a Wandera Mobile Threat Defense pomáhají chránit prostředky společnosti?  

Wandera vaší mobilní aplikace se nainstaluje bez problémů pomocí Microsoft Intune. Tato aplikace zaznamenává systém souborů, síťové protokoly a telemetrii zařízení a aplikací (Pokud je k dispozici). Tyto informace se synchronizují do cloudové služby Wandera se posoudí ohrožení zařízení mobilními hrozbami. Je možné konfigurovat tak, aby odpovídala vašim potřebám, konzole Wandera této možnosti taky PŘEMÝŠLÍTE tyto klasifikace úrovní rizik.

Zásady dodržování předpisů v Intune obsahují pravidlo pro MTD na základě posouzení rizik od Wandera. Když je toto pravidlo aktivní, Intune vyhodnocuje soulad zařízení se zásadami, které jste povolili.

Pro zařízení, která nejsou kompatibilní můžete blokovat přístup k prostředkům, jako je Office 365. Uživatelé zablokovaných zařízení přijímat pokyny z aplikace Wandera k vyřešení problému a jak opět získat přístup.

## <a name="supported-platforms"></a>Podporované platformy  

Pro Wandera při registraci v Intune se podporují tyto platformy:

- Android 5.0 nebo novější  
- iOS 10.2 a novější  

Další informace o platformě a zařízení, najdete v článku [Wandera webu](https://www.wandera.com/why-wandera/features/device-support/).

## <a name="prerequisites"></a>Požadavky  

- Odběr služby Microsoft Intune  
- Azure Active Directory  
- Wandera Mobile Threat Defense (dříve Wandera zabezpečení)  

Další informace najdete v tématu [Wandera Mobile Security](https://www.wandera.com/mobile-security/).
 
## <a name="sample-scenarios"></a>Ukázkové scénáře

Zde jsou obvyklé scénáře při používání Wandera MTD s Intune.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Řízení přístupu na základě hrozeb od škodlivých aplikací  

Při zjištění škodlivých aplikací, jako je například malware na zařízeních, můžete blokovat zařízení z běžné nástroje, dokud lze vyřešit hrozbu. Společné bloky patří:  
- Připojení k firemnímu e-mailu  
- Synchronizaci firemních souborů přes OneDrive for Work  
- Přístup k aplikacím společnosti  

**Zablokování, když se zjistí škodlivé aplikace**:

![Koncepčního obrázku zjištění přítomnosti škodlivých aplikací](./media/wandera-mtd-connector/wandera-malicious-apps-blocked.png)  

**Přístup udělený po nápravě**: 

![Koncepčního obrázku povoleného přístupu po nápravě](./media/wandera-mtd-connector/wandera-malicious-apps-unblocked.png)


### <a name="control-access-based-on-threat-to-network"></a>Řízení přístupu na základě ohrožení sítě  

Zjišťuje ohrožení vaší sítě, například útoky man-in-the-middle a chrání přístup k sítím Wi-Fi na základě rizika zařízení.  

**Zablokování přístupu k síti prostřednictvím sítě Wi-Fi**:  

![Zablokování přístupu k síti prostřednictvím sítě Wi-Fi](./media/wandera-mtd-connector/wandera-network-wifi-blocked.png)

**Přístup udělený po nápravě**:  

![Přístup udělený po nápravě](./media/wandera-mtd-connector/wandera-network-wifi-unblocked.png)  

## <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Řízení přístupu k SharePointu Online na základě ohrožení sítě

Zjišťuje ohrožení vaší sítě, například útoky prostředníkem, a zabraňuje synchronizaci podnikových souborů na základě rizika zařízení.

**Zablokování Sharepointu Online v případě zjištění ohrožení sítě**:  

![Zablokování SharePointu Online v případě zjištění ohrožení sítě](./media/wandera-mtd-connector/wandera-network-spo-blocked.png)  


**Přístup udělený po nápravě**:  

![Přístup udělený po nápravě Sharepointový příklad](./media/wandera-mtd-connector/wandera-network-spo-unblocked.png)  

## <a name="next-steps"></a>Další postup

- [Integrace Wandera s Intune](Wandera-mtd-connector-integration.md)
- [Nastavení Wandera aplikací](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Vytvoření zásad dodržování předpisů zařízení Wandera](mtd-device-compliance-policy-create.md)
- [Povolení konektoru Wandera MTD](mtd-connector-enable.md)