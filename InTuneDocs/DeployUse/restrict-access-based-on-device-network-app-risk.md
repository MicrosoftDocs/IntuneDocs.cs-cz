---
title: "Omezení přístupu pomocí ochrany proti mobilním hrozbám | Microsoft Intune"
description: "Omezení přístupu k prostředkům společnosti na základě rizika zařízení, sítě a aplikace."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c3cf5e6b32ad24d4972fd147331dda7d2d43e8c6
ms.openlocfilehash: d4eadb73aac14a375f41c434a4303a885bfbae64


---

# Omezení přístupu k prostředkům společnosti na základě rizika zařízení, sítě a aplikace
Přístup z mobilních zařízení k podnikovým prostředkům můžete regulovat na základě posouzení rizik, které provádí aplikace Lookout. To je řešení ochrany proti mobilním hrozbám (MTP) integrované v Microsoft Intune. Riziko se stanovuje na základě telemetrie, kterou služba Lookout MTP shromažďuje ze zařízení s cílem odhalit slabá místa zabezpečení operačního systému (OS), nainstalované škodlivé aplikace a síťové profily. Na základě posouzení rizik pak můžete v Intune nakonfigurovat zásady podmíněného přístupu a blokovat zařízení, které byla z důvodu zjištěných hrozeb určena jako nevyhovující.  Tato funkce je momentálně podporována pouze pro zařízení s **Androidem** verze **4.1 a novější**, která jsou zaregistrovaná v Microsoft Intune.  
## Jaký problém se tím vyřeší?
Společnosti a organizace potřebují chránit citlivá data před vznikajícími hrozbami, které zahrnují fyzické hrozby, hrozby založené na aplikacích nebo síti i slabá místa operačních systémů.

V minulosti společnosti a organizace před škodlivými útoky aktivně chránily stolní počítače. Mobilní zařízení představují novou oblast, jejíž ochrana často zůstává opomíjená. Přestože mobilní platformy mají integrovanou ochranu operačního systému pomocí metod, jako je například izolace aplikací nebo obchody s aplikacemi pro prověřené spotřebitele, jsou tyto platformy nadále zranitelné vůči sofistikovaným útokům. Protože zaměstnanci stále častěji k práci používají mobilní zařízení a potřebují mít přístup k informacím, které jsou citlivé a hodnotné, je třeba tato zařízení chránit před řadou sofistikovaných útoků.

Intune umožňuje řídit přístup k prostředkům a datům společnosti na základě posouzení rizik od řešení MTP, jako je například Lookout.

## Jak může ochrana Intune a Lookout proti mobilním hrozbám pomoct chránit prostředky společnosti?
Mobilní aplikace Lookout (Lookout for Work) funguje v mobilních zařízeních, zaznamenává systém souborů, síťové protokoly a telemetrii zařízení a aplikací (pokud je k dispozici) a odesílá tyto údaje do cloudové služby Lookout proti MTP, která vypočítá souhrnné riziko mobilních hrozeb pro zařízení. Klasifikaci úrovně rizika hrozeb může také změnit v konzole MTP tak, aby odpovídala vašim požadavkům.  
Zásady dodržování předpisů v Intune nyní obsahují nové pravidlo pro ochranu před mobilními útoky Lookout. To je založené na posouzení rizik službou Lookout MTP. Když je toto pravidlo je aktivní, Microsoft Intune vyhodnocuje soulad zařízení se zásadami, kterou jste povolili.

Pokud aplikace vyhodnotí, že zařízení není v souladu se zásadami dodržování předpisů, může mu být pomocí zásad podmíněného přístupu zablokován přístup k prostředkům jako Exchange Online nebo SharePoint Online. Po zablokování přístupu je koncovým uživatelům při pokusu o přístup zobrazen návod, který jim pomůže problém vyřešit a opětovně získat přístup k prostředkům společnosti. Návod se spustí prostřednictvím aplikace Lookout for Work.

## Příklady scénářů
Níže jsou uvedeny některé obvyklé scénáře:
### Hrozba od škodlivých aplikací:
Pokud jsou v zařízení zjištěny škodlivé aplikace, například malware, můžete zařízení zablokovat možnost:
* Připojení k podnikovému e-mailu do vyřešení hrozby.
* Synchronizace podnikových souborů pomocí aplikace OneDrive for Work.
* Přístupu k důležitým podnikovým aplikacím.

**Přístup zablokován při zjištění škodlivých aplikací:**
![diagram zobrazující zásadu podmíněného přístupu, která blokuje přístup zařízení vyhodnoceného jako nevyhovující z důvodu škodlivých aplikací v zařízení](../media/mtp/malicious-apps-blocked.png)

**Po vyřešení hrozby je zařízení odblokováno a má znovu přístup k prostředkům společnosti:**

![diagram zobrazující zásady podmíněného přístupu udělující přístup zařízení vyhodnocenému po nápravě jako vyhovující](../media/mtp/malicious-apps-unblocked.png)
### Ohrožení sítě:
Zjišťuje ohrožení vaší sítě, například útoky prostředníkem, a omezuje přístup k sítím Wi-Fi na základě rizika zařízení.

**Přístup k síti pomocí Wi-Fi blokovaný:**
![diagram zobrazující zásady podmíněného přístupu, které blokují přístup k Wi-Fi na základě ohrožení sítě](../media/mtp/network-wifi-blocked.png)

**Přístup po nápravě udělen:**

![diagram zobrazuje podmíněný přístup, jak po nápravě hrozby znovu povoluje přístup](../media/mtp/network-wifi-unblocked.png)
### Ohrožení sítě (zabránění přístupu k SharePointu Online):

Zjišťuje ohrožení vaší sítě, například útoky prostředníkem, a zabraňuje synchronizaci podnikových souborů na základě rizika zařízení.

**Zablokován přístup k SharePointu Online na základě ohrožení sítě zjištěného v zařízení:**

![Diagram zobrazuje, jak podmíněný přístup blokuje přístup zařízení k SharePointu Online na základě zjištění hrozby](../media/mtp/network-spo-blocked.png)


**Přístup po nápravě udělen:**

![Diagram zobrazuje, jak podmíněný přístupu po nápravě ohrožení sítě znovu povoluje přístup](../media/mtp/network-spo-unblocked.png)

## Další kroky
Tady jsou hlavní kroky, které je nutné provést při implementaci tohoto řešení:
1.  [Nastavení předplatného pro Lookout MTP](set-up-your-subscription-with-lookout-mtp.md)
2.  [Povolení připojení Lookout MTP v Intune](enable-lookout-mtp-connection-in-intune.md)
3.  [Konfigurace a nasazení aplikace Lookout for Work](configure-and-deploy-lookout-for-work-apps.md)
4.  [Konfigurace zásady dodržování předpisů](enable-device-threat-protection-rule-in-compliance-policy.md)
5.  [Řešení potíží s integrací služby Lookout](http://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration)



<!--HONumber=Sep16_HO3-->


