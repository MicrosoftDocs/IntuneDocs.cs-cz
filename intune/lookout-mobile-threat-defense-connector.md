---
title: Konektor Lookout MTD s Microsoft Intune
titleSuffix: Microsoft Intune
description: Přečtěte si o integraci Intune se službou Lookout Mobile Threat Defense (MTD) za účelem regulace přístupu mobilních zařízení k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3a730a5d-2a90-42b0-aa28-aadfc7a18788
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a6dfce050726cfddadc493f73c91701021dc21ea
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2019
ms.locfileid: "67529809"
---
# <a name="lookout-mobile-endpoint-security-connector-with-intune"></a>Konektor lookout Mobile Endpoint Security s Intune

Přístup mobilních zařízení k firemním prostředkům můžete regulovat na základě posouzení rizik, které provádí ochrana před mobilními hrozbami Lookout integrovaná ve službě Microsoft Intune. Riziko se posuzuje na základě telemetrie, kterou ze zařízení shromažďuje služba Lookout. K ní patří:
- Ohrožení zabezpečení operačního systému
- Nainstalované škodlivé aplikace
- Škodlivé profily sítě

Můžete nakonfigurovat zásady podmíněného přístupu na základě posouzení rizik Lookoutu prostřednictvím zásad dodržování předpisů Intune. V nastaveních můžete povolit nebo blokovat zařízení, která nedodržují předpisy, podle zjištěných hrozeb.

## <a name="how-do-intune-and-lookout-mobile-endpoint-security-help-protect-company-resources"></a>Jak Intune a Lookout Mobile Endpoint Security pomáhají chránit prostředky společnosti?
Na mobilní zařízení se nainstaluje a spustí mobilní aplikace Lookoutu **Lookout for Work**. Tato aplikace zaznamenává telemetrii systému souborů, zásobníku sítě, zařízení a aplikací tam, kde je k dispozici, a posílá ji do cloudové služby Lookout, kde se posoudí ohrožení zařízení mobilními hrozbami. Klasifikace úrovní rizik pro hrozby můžete změnit v konzole Lookoutu tak, aby odpovídaly vašim požadavkům.  

Zásady dodržování předpisů ve službě Intune obsahují pravidlo pro ochranu před mobilními hrozbami Lookout založené na posouzení rizik služby Lookout. Když je toto pravidlo aktivní, Intune vyhodnocuje soulad zařízení se zásadami, které jste povolili.

Pokud zařízení nedodržuje, přístup k prostředkům, jako jsou Exchange Online a SharePoint Online, může být blokováno. Uživatelé zablokovaných zařízení obdrží kroky k vyřešení problému a jak opět získat přístup. Pokyny se spouští z aplikace Lookout for Work.

## <a name="supported-platforms"></a>Podporované platformy  
Pro Lookout se podporují tyto platformy, pokud jsou zaregistrované v Intune:
* **Android 4.1 nebo novější**  
* **iOS 8 nebo novější**  

Další informace o podpoře platforem a jazyků najdete [webu Lookout](https://personal.support.lookout.com/hc/articles/114094140253).  

## <a name="prerequisites"></a>Požadavky
* Předplatné Lookout Mobile Endpoint Security pro podniky  
* Odběr služby Microsoft Intune
* Azure Active Directory Premium
* Enterprise Mobility a Security (EMS) E3 nebo E5, licence přiřazené uživatelům.  

Další informace najdete v tématu [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security).

## <a name="sample-scenarios"></a>Ukázkové scénáře

Zde jsou obvyklé scénáře při používání Mobile Endpoint Security s Intune.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Řízení přístupu na základě hrozeb od škodlivých aplikací
Když se na zařízeních zjistí přítomnost škodlivých aplikací (třeba malwaru), můžete jim až do vyřešení problému zablokovat toto:
* Připojení k firemnímu e-mailu
* Synchronizaci firemních souborů přes OneDrive for Work
* Přístup k aplikacím společnosti

**Zablokování při zjištění přítomnosti škodlivých aplikací:**

![Koncepčního obrázku zásada blokuje přístup z důvodu škodlivých aplikací](./media/malicious-apps-blocked.png)

**Přístup udělený po nápravě:**

![Koncepční obrázek se udělení přístupu k zařízení po nápravě](./media/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Řízení přístupu na základě ohrožení sítě
Zjišťuje ohrožení vaší sítě, například útoky prostředníkem, a chrání přístup k sítím Wi-Fi na základě rizika zařízení.

**Zablokování přístupu k síti prostřednictvím Wi-Fi:**

![Obrázek znázorňující blokuje přístup k Wi-Fi na základě ohrožení sítě](./media/network-wifi-blocked.png)

**Přístup udělený po nápravě:**

![Koncepčního obrázku podmíněný přístup umožňuje přístup po nápravě](./media/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Řízení přístupu k SharePointu Online na základě ohrožení sítě

Zjišťuje ohrožení vaší sítě, například útoky prostředníkem, a zabraňuje synchronizaci podnikových souborů na základě rizika zařízení.

**Zablokování SharePointu Online v případě, že se zjistí ohrožení sítě:**

![Koncepčního obrázku blokování přístupu k Sharepointu Online](./media/network-spo-blocked.png)


**Přístup udělený po nápravě:**

![Koncepční snímek umožňuje přístup po napravit ohrožení sítě](./media/network-spo-unblocked.png)

## <a name="next-steps"></a>Další postup
Tady jsou hlavní kroky, které je nutné provést při implementaci tohoto řešení:
1. [Nastavení integrace služby Lookout](lookout-mtd-connector-integration.md)
2. [Povolit Mobile Endpoint Security v Intune](mtd-connector-enable.md)
3. [Přidání a podepsání aplikace Lookout for Work](mtd-apps-ios-app-configuration-policy-add-assign.md)
4. [Konfigurace zásad dodržování předpisů zařízení služby Lookout](mtd-device-compliance-policy-create.md)
