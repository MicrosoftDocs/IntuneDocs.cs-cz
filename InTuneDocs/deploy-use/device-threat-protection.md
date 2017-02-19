---
title: "Ochrana přístupu pomocí ochrany zařízení před internetovými útoky | Dokumentace Microsoftu"
description: "Chraňte přístup k prostředkům společnosti na základě rizika zařízení, sítě a aplikace."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 931f222898a224c2f646ad203f12676c39b78946
ms.openlocfilehash: aaa0965c2bd4d4093da0c57eaa2e3bd05eb6779a


---

# <a name="protect-access-to-company-resource-based-on-device-network-and-application-risk"></a>Ochrana přístupu k prostředkům společnosti na základě rizika zařízení, sítě a aplikace

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Přístup mobilních zařízení k podnikovým prostředkům můžete regulovat na základě posouzení rizik, které provádí Lookout. To je řešení ochrany zařízení před internetovými útoky integrované v Microsoft Intune. Riziko se posuzuje na základě telemetrie, kterou ze zařízení shromažďuje služba Lookout. K ní patří:
- Ohrožení zabezpečení operačního systému
- Nainstalované škodlivé aplikace
- Škodlivé profily sítě

Na základě posouzení rizik Lookoutu, které se povoluje přes zásady dodržování předpisů v Intune, můžete nakonfigurovat zásady podmíněného přístupu. V nastaveních můžete povolit nebo blokovat zařízení, která nedodržují předpisy, podle zjištěných hrozeb.  

## <a name="what-problem-does-this-solve"></a>Jaký problém se tím vyřeší?
Společnosti potřebují chránit citlivá data před vznikajícími hrozbami, mezi které patří fyzické hrozby, hrozby založené na aplikacích nebo síti i ohrožení zabezpečení operačních systémů.

V minulosti byly společnosti aktivní při ochraně počítačů před útoky, ale mobilní zařízení zůstávají nemonitorovaná a nechráněná. Mobilní platformy mají integrovanou ochranu, jako je izolace aplikací nebo obchody s aplikacemi pro prověřené spotřebitele, ale přesto jsou tyto platformy nadále zranitelné sofistikovanými útoky. V dnešní době je více zaměstnanců, kteří k práci využívají nějaká zařízení a potřebují přístup k citlivým údajům. Zařízení je nutné chránit před stále důmyslnějšími útoky.

Intune umožňuje řídit přístup k prostředkům společnosti na základě posouzení rizik, která získáte od řešení ochrany zařízení před hrozbami. Takovým řešením je třeba Lookout.

## <a name="how-do-intune-and-lookout-device-threat-protection-help-protect-company-resources"></a>Jak může ochrana Intune a Lookout, chránící zařízení proti hrozbám, pomoct při ochraně prostředků společnosti?
Na mobilní zařízení se nainstaluje a spustí mobilní aplikace Lookoutu **Lookout for Work**. Tato aplikace zaznamenává telemetrii systému souborů, zásobníku sítě, zařízení a aplikací tam, kde je k dispozici, a posílá ji do cloudové služby Lookout, kde se posoudí ohrožení zařízení mobilními hrozbami. Klasifikace úrovní rizik pro hrozby můžete změnit v konzole Lookoutu tak, aby odpovídaly vašim požadavkům.  

Zásady dodržování předpisů v Intune obsahují pravidlo pro Lookout Mobile Threat Protection založené na posouzení rizik Lookoutu. Když je toto pravidlo aktivní, Intune vyhodnocuje soulad zařízení se zásadami, které jste povolili.

Pokud se zjistí, že zařízení dané předpisy nedodržuje, dá se zablokovat přístup k prostředkům, jako jsou Exchange Online a SharePoint Online. Uživatelé dostanou na blokovaná zařízení informace o tom, jak problém vyřešit a jak znovu získat přístup. Pokyny se spouští z aplikace Lookout for Work.

## <a name="supported-platforms"></a>Podporované platformy:
Pro Lookout se podporují tyto platformy, pokud jsou zaregistrované v Intune:
* **Android 4.1 nebo novější**
* **iOS 8 a novější** Další informace o podpoře platforem a jazyků najdete na [webu Lookoutu](https://personal.support.lookout.com/hc/en-us/articles/114094140253).

## <a name="prerequisites"></a>Požadavky:
* Odběr služby Microsoft Intune
* Azure Active Directory
* Předplatné Lookout Mobile Endpoint Security pro podniky  

Další informace najdete v tématu [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security).

## <a name="sample-scenarios"></a>Ukázkové scénáře
Níže jsou uvedeny některé obvyklé scénáře:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Řízení přístupu na základě hrozeb od škodlivých aplikací
Když se na zařízeních zjistí přítomnost škodlivých aplikací (třeba malwaru), můžete jim až do vyřešení problému zablokovat toto:
* Připojení k firemnímu e-mailu
* Synchronizaci firemních souborů přes OneDrive for Work
* Přístup k aplikacím společnosti

**Zablokování, když se zjistí škodlivé aplikace:**
![diagram zobrazující zásady podmíněného přístupu, které blokují přístup zařízení vyhodnoceného jako nevyhovující z důvodu škodlivých aplikací v zařízení](../media/mtp/malicious-apps-blocked.png)

**Přístup udělený po nápravě:**

![diagram zobrazující zásady podmíněného přístupu udělující přístup zařízení vyhodnocenému po nápravě jako vyhovující](../media/mtp/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Řízení přístupu na základě ohrožení sítě
Zjišťuje ohrožení vaší sítě, například útoky prostředníkem, a chrání přístup k sítím Wi-Fi na základě rizika zařízení.

**Zablokování přístupu k síti přes Wi-Fi:**
![diagram zobrazující zásady podmíněného přístupu, které blokují přístup k Wi-Fi na základě ohrožení sítě](../media/mtp/network-wifi-blocked.png)

**Přístup udělený po nápravě:**

![diagram zobrazuje podmíněný přístup, jak po nápravě hrozby znovu povoluje přístup](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Řízení přístupu k SharePointu Online na základě ohrožení sítě

Zjišťuje ohrožení vaší sítě, například útoky prostředníkem, a zabraňuje synchronizaci podnikových souborů na základě rizika zařízení.

**Zablokování SharePointu Online v případě, že se zjistí ohrožení sítě:**

![Diagram zobrazuje, jak podmíněný přístup blokuje přístup zařízení k SharePointu Online na základě zjištění hrozby](../media/mtp/network-spo-blocked.png)


**Přístup udělený po nápravě:**

![Diagram zobrazuje, jak podmíněný přístupu po nápravě ohrožení sítě znovu povoluje přístup](../media/mtp/network-spo-unblocked.png)

## <a name="next-steps"></a>Další kroky
Tady jsou hlavní kroky, které je nutné provést při implementaci tohoto řešení:
1.    [Nastavení předplatného s ochranou zařízení před internetovými útoky](device-threat-protection-subscription-setup.md)
2.    [Povolení připojení s ochranou zařízení před internetovými útoky v Intune](device-threat-protection-enable.md)
3.  [Konfigurace a nasazení aplikace ochrany zařízení před internetovými útoky](device-threat-protection-apps.md)
4.    [Konfigurace zásad dodržování předpisů pro ochranu zařízení před internetovými útoky](device-threat-protection-policy.md)
5.    [Řešení problémů s integrací ochrany zařízení před internetovými útoky](http://docs.microsoft.com/intune/troubleshoot/device-threat-protection-troubleshooting)



<!--HONumber=Jan17_HO4-->


