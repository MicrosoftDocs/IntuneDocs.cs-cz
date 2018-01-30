---
title: "Ochrana Office 365 Exchange Online bez nutnosti správy zařízení"
description: "Zaměstnancům můžete umožnit přístup k pracovnímu e-mailu. Nemusíte přitom zavádět správu zařízení."
keywords: "Přístup k e-mailu Office 365 Exchange"
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88a0d3b9-2622-403b-8374-1396afd8066e
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 53872921bc4c7a52224741ab3b743a1d9ac52f42
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="protect-office-365-exchange-online-without-requiring-device-management"></a>Ochrana Office 365 Exchange Online bez nutnosti správy zařízení

Pokud chcete zaměstnancům umožnit přístup k pracovnímu e-mailu a nezabývat se přitom zavedením systému pro správu zařízení, můžete. Přístup k Office 365 Exchange Online je možné poskytnout prostřednictvím Intune. Před provedením potřebných kroků ověřte, že máte licence na Microsoft 365 nebo Azure Active Directory (Premium) a Intune. Zaměstnanci musí mít [podporovaná zařízení s iOS nebo Androidem](supported-devices-browsers.md). 

Pokud se rozhodnete zavést systém pro správu zřízení, můžete. Tento typ ochrany aplikací funguje nezávisle na správě zařízení. 

## <a name="action-plan"></a>Akční plán

1. [Prostudujte si podmíněný přístup](conditional-access.md). 
2. [Prostudujte si podmíněný přístup na základě aplikací](app-based-conditional-access-intune.md).
3. [Nastavte zásady podmíněného přístupu na základě aplikací pro Exchange Online](app-based-conditional-access-intune-create.md).
4. [Zablokujte aplikace, které nelze spravovat](app-modern-authentication-block.md), konkrétně aplikace, které nepoužívají ADAL (Azure Active Directory Authentication Library).
5. (Volitelné) [Nastavte zásady podmíněného přístupu na základě aplikací pro SharePoint Online](app-based-conditional-access-intune-create.md). Tyto zásady blokují přístup k firemním datům z aplikací, které nelze spravovat a zabezpečit. Tyto zásady také omezují přístup přes mobilní SharePoint. 

## <a name="what-to-tell-employees-and-students"></a>Co sdělit zaměstnancům a studentům

* Požádejte zaměstnance a studenty, aby si stáhli a nainstalovali Microsoft Outlook nebo Microsoft SharePoint pro iOS z Apple App Storu, nebo pro Android z Obchodu Google Play. 
* Pokud zablokujete přístup k aplikacím, které nepoužívají moderní ověřování, nezapomeňte se zaměstnancům a studentům o tomto omezení zmínit. 

## <a name="next-steps"></a>Další kroky

Podmíněný přístup na základě aplikací používáte k lepšímu zabezpečení firemních dat. V dalších krocích se dozvíte o jiných způsobech, jakými můžete zlepšit ochranu firemních dat, mezi které patří: 

* Nastavení [podmíněného přístupu na základě dodržování předpisů zařízením, rizika zařízení, polohy a uživatelských atributů ve službě Active Directory a Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)  
* Nastavení zásad ochrany aplikací, které pomáhají chránit firemní data před úmyslným nebo neúmyslným únikem informací 
* Využití služby Azure Information Protection k ochraně firemních dat mimo vaši síť 

Potřebujete pomoc s povolením této funkce nebo jiných scénářů EMS nebo Office 365? Pokud máte alespoň 150 licencí na Microsoft 365, Enterprise Mobility + Security nebo Azure Active Directory Premium, využijte [výhod služby FastTrack](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program). 