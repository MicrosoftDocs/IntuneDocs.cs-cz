---
title: "Omezení přístupu pomocí ochrany zařízení před internetovými útoky | Microsoft Intune"
description: "Omezení přístupu k prostředkům společnosti na základě rizika zařízení, sítě a aplikace."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: d529bd1c2a281c06f70593e73b71d09962a3c714


---

# <a name="restrict-access-to-company-resource-based-on-device-network-and-application-risk"></a>Omezení přístupu k prostředkům společnosti na základě rizika zařízení, sítě a aplikace
Přístup z mobilních zařízení k podnikovým prostředkům můžete regulovat na základě posouzení rizik, které provádí Lookout. To je řešení ochrany zařízení před internetovými útoky integrované v Microsoft Intune. Riziko se stanovuje na základě telemetrie, kterou služba Lookout shromažďuje ze zařízení s cílem odhalit slabá místa zabezpečení operačního systému, nainstalované škodlivé aplikace a škodlivé síťové profily. Na základě posouzení rizik pomocí zásad dodržování předpisů Intune, které Lookout nahlásí, můžete v Intune nakonfigurovat zásady podmíněného přístupu a povolit nebo zablokovat zařízení, která byla kvůli zjištěným hrozbám určena jako nevyhovující.  

## <a name="what-problem-does-this-solve"></a>Jaký problém se tím vyřeší?
Společnosti a organizace potřebují chránit citlivá data před vznikajícími hrozbami, které zahrnují fyzické hrozby, hrozby založené na aplikacích nebo síti i slabá místa operačních systémů.

V minulosti společnosti a organizace před škodlivými útoky aktivně chránily stolní počítače. Mobilní zařízení představují novou oblast, jejíž ochrana často zůstává opomíjená. Přestože mobilní platformy mají integrovanou ochranu operačního systému pomocí metod, jako je například izolace aplikací nebo obchody s aplikacemi pro prověřené spotřebitele, jsou tyto platformy nadále zranitelné vůči sofistikovaným útokům. Protože zaměstnanci stále častěji k práci používají mobilní zařízení a potřebují mít přístup k informacím, které jsou citlivé a hodnotné, je třeba tato zařízení chránit před řadou sofistikovaných útoků.

Intune umožňuje řídit přístup k prostředkům a datům společnosti na základě posouzení rizik, která poskytují řešení ochrany zařízení před internetovými útoky, jako je například Lookout.

## <a name="how-do-intune-and-lookout-device-threat-protection-help-protect-company-resources"></a>Jak může ochrana Intune a Lookout, chránící zařízení proti hrozbám, pomoct při ochraně prostředků společnosti?
Mobilní aplikace Lookout (Lookout for Work), běžící na mobilních zařízeních, zaznamenává systém souborů, síťové protokoly a telemetrii zařízení a aplikací (pokud je k dispozici) a odesílá tyto údaje do cloudové služby Lookout, která vypočítá souhrnné riziko mobilních hrozeb pro zařízení. Klasifikaci úrovně rizika hrozeb můžete také změnit v konzole Lookout tak, aby odpovídala vašim požadavkům.  

Zásady dodržování předpisů v Intune nyní obsahují nové pravidlo pro ochranu před mobilními útoky Lookout. Toto pravidlo je založené na posouzení rizik službou Lookout. Když je toto pravidlo je aktivní, Microsoft Intune vyhodnocuje soulad zařízení se zásadami, kterou jste povolili.

Pokud aplikace vyhodnotí, že zařízení není v souladu se zásadami dodržování předpisů, může mu být pomocí zásad podmíněného přístupu zablokován přístup k prostředkům jako Exchange Online nebo SharePoint Online. Po zablokování přístupu je koncovým uživatelům při pokusu o přístup zobrazen návod, který jim pomůže problém vyřešit a opětovně získat přístup k prostředkům společnosti. Návod se spustí prostřednictvím aplikace Lookout for Work.
## <a name="supported-platforms"></a>Podporované platformy:
* **Android 4.1 a novější** s registrací v Microsoft Intune
* **iOS 8 a novější** s registrací v Microsoft Intune
Informace o platformách a jazycích, které aplikace Lookout podporuje, najdete v tomto [článku](https://personal.support.lookout.com/hc/en-us/articles/114094140253).

## <a name="prerequisites"></a>Požadavky:
* Předplatné Microsoft Intune a Azure Active Directory
* Předplatné Lookout Mobile Endpoint Security pro podniky  Další informace najdete v tématu [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security).

## <a name="example-scenarios"></a>Příklady scénářů
Níže jsou uvedeny některé obvyklé scénáře:
### <a name="control-access-based-on-threat-from-malicious-apps"></a>Řízení přístupu na základě hrozeb od škodlivých aplikací:
Pokud jsou v zařízení zjištěny škodlivé aplikace, například malware, můžete zařízení zablokovat možnost:
* Připojení k podnikovému e-mailu do vyřešení hrozby.
* Synchronizace podnikových souborů pomocí aplikace OneDrive for Work.
* Přístupu k důležitým podnikovým aplikacím.

**Zablokovaný přístup, když se zjistí škodlivé aplikace:**
![diagram zobrazující zásadu podmíněného přístupu, která blokuje přístup zařízení vyhodnoceného jako nevyhovující z důvodu škodlivých aplikací v zařízení](../media/mtp/malicious-apps-blocked.png)

**Až se hrozba vyřeší, zařízení se odblokuje a má znovu přístup k prostředkům společnosti:**

![diagram zobrazující zásady podmíněného přístupu udělující přístup zařízení vyhodnocenému po nápravě jako vyhovující](../media/mtp/malicious-apps-unblocked.png)
### <a name="control-access-based-on-threat-to-network"></a>Řízení přístupu na základě hrozeb v síti:
Zjišťuje ohrožení vaší sítě, například útoky prostředníkem, a omezuje přístup k sítím Wi-Fi na základě rizika zařízení.

**Zablokovaný přístup k síti přes Wi-Fi:**
![diagram zobrazující zásady podmíněného přístupu, které blokují přístup k Wi-Fi na základě ohrožení sítě](../media/mtp/network-wifi-blocked.png)

**Přístup udělený po nápravě:**

![diagram zobrazuje podmíněný přístup, jak po nápravě hrozby znovu povoluje přístup](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Řízení přístupu k SharePointu Online na základě hrozeb v síti:

Zjišťuje ohrožení vaší sítě, například útoky prostředníkem, a zabraňuje synchronizaci podnikových souborů na základě rizika zařízení.

**Zablokovaný přístup k SharePointu Online na základě ohrožení sítě zjištěného v zařízení:**

![Diagram zobrazuje, jak podmíněný přístup blokuje přístup zařízení k SharePointu Online na základě zjištění hrozby](../media/mtp/network-spo-blocked.png)


**Přístup udělený po nápravě:**

![Diagram zobrazuje, jak podmíněný přístupu po nápravě ohrožení sítě znovu povoluje přístup](../media/mtp/network-spo-unblocked.png)

## <a name="next-steps"></a>Další kroky
Tady jsou hlavní kroky, které je nutné provést při implementaci tohoto řešení:
1.  [Nastavení předplatného pro Lookout MTP](set-up-your-subscription-with-lookout-mtp.md)
2.  [Povolení připojení Lookout MTP v Intune](enable-lookout-mtp-connection-in-intune.md)
3.  [Konfigurace a nasazení aplikace Lookout for Work](configure-and-deploy-lookout-for-work-apps.md)
4.  [Konfigurace zásady dodržování předpisů](enable-device-threat-protection-rule-in-compliance-policy.md)
5.  [Řešení problémů s Lookout Integration](http://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration)



<!--HONumber=Dec16_HO2-->


