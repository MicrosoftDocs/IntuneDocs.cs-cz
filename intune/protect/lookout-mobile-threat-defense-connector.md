---
title: Konektor Lookout MTD s Microsoft Intune
titleSuffix: Microsoft Intune
description: Přečtěte si o integraci Intune se službou Lookout Mobile Threat Defense (MTD) za účelem regulace přístupu mobilních zařízení k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/21/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3a730a5d-2a90-42b0-aa28-aadfc7a18788
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 628aa93af912d6c50a6897dbf871702e46b4893e
ms.sourcegitcommit: 25e4847ead0f56c269cfefe1e01c1b9106a28cf1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2020
ms.locfileid: "78368509"
---
# <a name="lookout-mobile-endpoint-security-connector-with-intune"></a>Podívejte se na mobilní koncový bod Security Connector s Intune

Přístup mobilních zařízení k firemním prostředkům můžete regulovat na základě posouzení rizik, které provádí ochrana před mobilními hrozbami Lookout integrovaná ve službě Microsoft Intune. Riziko se posuzuje na základě telemetrie, kterou ze zařízení shromažďuje služba Lookout. K ní patří:
- Ohrožení zabezpečení operačního systému
- Nainstalované škodlivé aplikace
- Škodlivé profily sítě

Zásady podmíněného přístupu můžete nakonfigurovat na základě posouzení rizik ve vyhledávání, které se povoluje v zásadách dodržování předpisů Intune pro zaregistrovaná zařízení, která můžete použít k povolení nebo blokování zařízení nesplňujících požadavky pro přístup k podnikovým prostředkům na základě zjištěných hrozeb. U neregistrovaných zařízení můžete zásady ochrany aplikací použít k vykonání bloku nebo selektivního vymazání na základě zjištěných hrozeb.

## <a name="how-do-intune-and-lookout-mobile-endpoint-security-help-protect-company-resources"></a>Jak Intune a Prohlédněte si Mobile Endpoint Security, jak zajistit ochranu firemních prostředků?
Na mobilní zařízení se nainstaluje a spustí mobilní aplikace Lookoutu **Lookout for Work**. Tato aplikace zaznamenává telemetrii systému souborů, zásobníku sítě, zařízení a aplikací tam, kde je k dispozici, a posílá ji do cloudové služby Lookout, kde se posoudí ohrožení zařízení mobilními hrozbami. Klasifikace úrovní rizik pro hrozby můžete změnit v konzole Lookoutu tak, aby odpovídaly vašim požadavkům.  

Zásady dodržování předpisů ve službě Intune obsahují pravidlo pro ochranu před mobilními hrozbami Lookout založené na posouzení rizik služby Lookout. Když je toto pravidlo aktivní, Intune vyhodnocuje soulad zařízení se zásadami, které jste povolili.

Pokud zařízení nedodržuje předpisy, přístup k prostředkům, jako je Exchange Online a SharePoint Online, je možné zablokovat. Uživatelům blokovaných zařízení se dostanou kroky k vyřešení problému a k opětovnému získání přístupu. Pokyny se spouští z aplikace Lookout for Work.

## <a name="supported-platforms"></a>Podporované platformy  
Pro Lookout se podporují tyto platformy, pokud jsou zaregistrované v Intune:
* **Android 4.1 nebo novější**  
* **iOS 8 nebo novější**  

Další informace o podpoře platforem a jazyků najdete na webu pro [hledání](https://personal.support.lookout.com/hc/articles/114094140253).  

## <a name="prerequisites"></a>Požadavky
* Předplatné Lookout Mobile Endpoint Security pro podniky  
* Odběr služby Microsoft Intune
* Azure Active Directory Premium
* Enterprise mobility and Security (EMS) E3 nebo E5 s licencemi přiřazenými uživatelům.  

Další informace najdete v tématu [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security).

## <a name="sample-scenarios"></a>Ukázkové scénáře

Tady jsou běžné scénáře použití služby Mobile Endpoint Security s Intune.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Řízení přístupu na základě hrozeb od škodlivých aplikací
Když se na zařízeních zjistí přítomnost škodlivých aplikací (třeba malwaru), můžete jim až do vyřešení problému zablokovat toto:
* Připojení k firemnímu e-mailu
* Synchronizaci firemních souborů přes OneDrive for Work
* Přístup k aplikacím společnosti

**Zablokování při zjištění přítomnosti škodlivých aplikací:**

![Koncepční obrázek zásad blokující přístup z důvodu škodlivých aplikací](./media/lookout-mobile-threat-defense-connector/malicious-apps-blocked.png)

**Přístup udělený po nápravě:**

![Koncepční obrázek ukazující přístup k zařízením po opravě](./media/lookout-mobile-threat-defense-connector/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Řízení přístupu na základě ohrožení sítě
Zjišťuje ohrožení vaší sítě, například útoky prostředníkem, a chrání přístup k sítím Wi-Fi na základě rizika zařízení.

**Zablokování přístupu k síti prostřednictvím Wi-Fi:**

![Obrázek znázorňující blokování přístupu Wi-Fi na základě hrozeb sítě](./media/lookout-mobile-threat-defense-connector/network-wifi-blocked.png)

**Přístup udělený po nápravě:**

![Koncepční obrázek podmíněného přístupu umožňující přístup po nápravě](./media/lookout-mobile-threat-defense-connector/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Řízení přístupu k SharePointu Online na základě ohrožení sítě

Zjišťuje ohrožení vaší sítě, například útoky prostředníkem, a zabraňuje synchronizaci podnikových souborů na základě rizika zařízení.

**Zablokování SharePointu Online v případě, že se zjistí ohrožení sítě:**

![Koncepční obrázek blokující přístup k SharePointu Online](./media/lookout-mobile-threat-defense-connector/network-spo-blocked.png)


**Přístup udělený po nápravě:**

![Koncepční obrázek povolení přístupu po nápravě síťové hrozby](./media/lookout-mobile-threat-defense-connector/network-spo-unblocked.png)

## <a name="next-steps"></a>Další kroky
Tady jsou hlavní kroky, které je nutné provést při implementaci tohoto řešení:
- [Nastavení integrace služby Lookout](lookout-mtd-connector-integration.md)
- [Povolení mobilního koncového bodu zabezpečení v Intune](mtd-connector-enable.md)
- [Přidání a podepsání aplikace Lookout for Work](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Konfigurace zásad dodržování předpisů zařízení služby Lookout](mtd-device-compliance-policy-create.md)
- [Vytvoření zásady ochrany aplikací MTD](mtd-app-protection-policy.md)

