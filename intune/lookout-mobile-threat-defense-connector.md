---
title: Konektor lookout MTD s Microsoft Intune | Microsoft Intune
description: Přečtěte si o integraci Intune se službou Lookout Mobile Threat Defense (MTD) za účelem regulace přístupu mobilních zařízení k firemním prostředkům.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/09/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3a730a5d-2a90-42b0-aa28-aadfc7a18788
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fbcd2223ab547eb92c81bb9729143d075d749824
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850603"
---
# <a name="lookout-mobile-threat-defense-connector-with-intune"></a>Konektor Lookout Mobile Threat Defense s Intune

Přístup mobilních zařízení k firemním prostředkům můžete regulovat na základě posouzení rizik, které provádí ochrana před mobilními hrozbami Lookout integrovaná ve službě Microsoft Intune. Riziko se posuzuje na základě telemetrie, kterou ze zařízení shromažďuje služba Lookout. K ní patří:
- Ohrožení zabezpečení operačního systému
- Nainstalované škodlivé aplikace
- Škodlivé profily sítě

Na základě posouzení rizik Lookoutu, které se povoluje přes zásady dodržování předpisů v Intune, můžete nakonfigurovat zásady podmíněného přístupu. V nastaveních můžete povolit nebo blokovat zařízení, která nedodržují předpisy, podle zjištěných hrozeb.

## <a name="how-do-intune-and-lookout-mobile-threat-defense-help-protect-company-resources"></a>Jak může služba Intune a ochrana před mobilními hrozbami Lookout pomoct chránit prostředky společnosti?
Na mobilní zařízení se nainstaluje a spustí mobilní aplikace Lookoutu **Lookout for Work**. Tato aplikace zaznamenává telemetrii systému souborů, zásobníku sítě, zařízení a aplikací tam, kde je k dispozici, a posílá ji do cloudové služby Lookout, kde se posoudí ohrožení zařízení mobilními hrozbami. Klasifikace úrovní rizik pro hrozby můžete změnit v konzole Lookoutu tak, aby odpovídaly vašim požadavkům.  

Zásady dodržování předpisů ve službě Intune obsahují pravidlo pro ochranu před mobilními hrozbami Lookout založené na posouzení rizik služby Lookout. Když je toto pravidlo aktivní, Intune vyhodnocuje soulad zařízení se zásadami, které jste povolili.

Pokud se zjistí, že zařízení dané předpisy nedodržuje, dá se zablokovat přístup k prostředkům, jako jsou Exchange Online a SharePoint Online. Uživatelé dostanou na blokovaná zařízení informace o tom, jak problém vyřešit a jak znovu získat přístup. Pokyny se spouští z aplikace Lookout for Work.

## <a name="supported-platforms"></a>Podporované platformy
Pro Lookout se podporují tyto platformy, pokud jsou zaregistrované v Intune:
* **Android 4.1 nebo novější**
* **iOS 8 a novější** Další informace o podpoře platforem a jazyků najdete na [webu Lookoutu](https://personal.support.lookout.com/hc/articles/114094140253).

## <a name="prerequisites"></a>Požadavky
* Odběr služby Microsoft Intune
* Azure Active Directory
* Předplatné Lookout Mobile Endpoint Security pro podniky  

Další informace najdete v tématu [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security).

## <a name="sample-scenarios"></a>Ukázkové scénáře

Seznamte se s běžnými scénáři při používání Lookout Mobile Threat Defense s Intune.

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
1.  [Nastavení integrace služby Lookout](lookout-mtd-connector-integration.md)
2.  [Povolení ochrany před mobilními hrozbami Lookout ve službě Intune](mtd-connector-enable.md)
3.  [Přidání a podepsání aplikace Lookout for Work](mtd-apps-ios-app-configuration-policy-add-assign.md)
4.  [Konfigurace zásad dodržování předpisů zařízení služby Lookout](mtd-device-compliance-policy-create.md)
