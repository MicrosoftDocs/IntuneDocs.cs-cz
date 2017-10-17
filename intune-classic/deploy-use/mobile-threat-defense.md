---
title: "Ochrana před mobilními hrozbami v Intune"
description: "Chraňte přístup k prostředkům společnosti na základě rizika zařízení."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08d87906-8158-4d5e-a49d-ad919efef3d1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ff4595a96d34d30fee05c64fd7f88f564610902c
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2017
---
# <a name="intune-mobile-threat-defense-connectors"></a>Konektory Intune Mobile Threat Defense

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Konektory Intune Mobile Threat Defense vám umožňují využívat zvoleného dodavatele Mobile Threat Defense jako zdroje informací pro zásady dodržování předpisů a pravidla podmíněného přístupu. Správci IT tak můžou přidat podnikovým prostředkům, jako je například Exchange a SharePoint, vrstvu ochrany z ohrožených mobilních zařízení.

## <a name="what-problem-does-this-solve"></a>Jaký problém se tím vyřeší?

Společnosti potřebují chránit citlivá data před vznikajícími hrozbami, mezi které patří fyzické hrozby, hrozby založené na aplikacích nebo síti i ohrožení zabezpečení operačních systémů.
V minulosti byly společnosti aktivní při ochraně počítačů před útoky, ale mobilní zařízení zůstávají nemonitorovaná a nechráněná. Mobilní platformy mají integrovanou ochranu, jako je izolace aplikací nebo obchody s aplikacemi pro prověřené spotřebitele, ale přesto jsou tyto platformy nadále zranitelné sofistikovanými útoky. V dnešní době je více zaměstnanců, kteří k práci využívají nějaká zařízení a potřebují přístup k citlivým údajům. Zařízení je nutné chránit před stále důmyslnějšími útoky.

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a>Jak fungují konektory Intune Mobile Threat Defense?

Konektor chrání firemní prostředky tím, že mezi Intune a vaším dodavatelem zvoleného konektoru Mobile Threat Defense vytvoří komunikační kanál. Partneři Intune Mobile Threat Defense nabízejí intuitivní a snadno nasaditelné aplikace pro mobilní zařízení, která aktivně kontrolují a analyzují informace o hrozbách, aby je sdílely s Intune pro účely nahlášení nebo vynucení. Pokud třeba připojená aplikace Mobile Threat Defense nahlásí dodavateli Mobile Threat Defense, že telefon ve vaší síti je právě připojený k síti, která se dá snadno napadnout útokem třetí osobou (man-in-the-middle), tyto informace se nasdílí a zařadí do příslušné úrovně rizika (nízké, střední nebo vysoké), která se dá pak porovnat s vaší nakonfigurovanou úrovní rizika v Intune, aby se zjistilo, jestli se má při ohrožení zařízení odvolat přístup k určitým zvoleným zdrojům.

## <a name="sample-scenarios"></a>Ukázkové scénáře

Pokud řešení Mobile Threat Defense považuje zařízení za nakažené:

![Nakažené zařízení s ochranou službou Mobile Threat Defense](../media/mtp/MTD-image-1.png)

Přístup se udělí, když je zařízení opravené:

![Udělení přístupu službou Mobile Threat Defense](../media/mtp/MTD-image-2.png)

## <a name="mobile-threat-defense-partners"></a>Partneři Mobile Threat Defense

Zjistěte, jak zabezpečit přístup k prostředkům společnosti na základě rizika zařízení, sítě a aplikace s:

- [Lookoutem](/intune-classic/deploy-use/lookout-mobile-threat-defense-connector)
- [Skycure](/intune-classic/deploy-use/skycure-mobile-threat-defense-connector)
