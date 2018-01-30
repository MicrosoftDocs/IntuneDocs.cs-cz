---
title: "Ochrana před mobilními hrozbami s Intune"
titleSuffix: Azure portal
description: "Přístup k prostředkům společnosti můžete chránit podle rizika zařízení."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f1d5957acde86b3621009e5c38df42bc894a413c
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="mobile-threat-defense-integration-with-intune"></a>Integrace ochrany před mobilními hrozbami do Intune


Konektory Intune Mobile Threat Defense vám umožňují využívat zvoleného dodavatele Mobile Threat Defense jako zdroje informací pro zásady dodržování předpisů a pravidla podmíněného přístupu. Správci IT tak mohou přidat podnikovým prostředkům, jako je například Exchange a SharePoint, vrstvu ochrany z ohrožených mobilních zařízení.

## <a name="what-problem-does-this-solve"></a>Jaký problém se tím vyřeší?

Společnosti potřebují chránit citlivá data před vznikajícími hrozbami, mezi které patří fyzické hrozby, hrozby založené na aplikacích nebo síti i ohrožení zabezpečení operačních systémů.

V minulosti byly společnosti aktivní při ochraně počítačů před útoky, ale mobilní zařízení zůstávají nemonitorovaná a nechráněná. Mobilní platformy mají integrovanou ochranu, jako je izolace aplikací nebo obchody s aplikacemi pro prověřené spotřebitele, ale přesto jsou tyto platformy nadále zranitelné sofistikovanými útoky. V dnešní době je více zaměstnanců, kteří k práci využívají nějaká zařízení a potřebují přístup k citlivým údajům. Zařízení je nutné chránit před stále důmyslnějšími útoky.

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a>Jak fungují konektory Intune Mobile Threat Defense?

Konektor chrání firemní prostředky tím, že mezi Intune a vaším dodavatelem zvoleného konektoru Mobile Threat Defense vytvoří komunikační kanál. Partneři Intune Mobile Threat Defense nabízejí intuitivní a snadno nasaditelné aplikace pro mobilní zařízení, která aktivně kontrolují a analyzují informace o hrozbách, aby je sdílely s Intune pro účely nahlášení nebo vynucení. 

Pokud třeba připojená aplikace Mobile Threat Defense nahlásí dodavateli Mobile Threat Defense, že telefon ve vaší síti je právě připojený k síti, která se dá snadno napadnout útokem třetí osobou (man-in-the-middle), tyto informace se nasdílí a zařadí do příslušné úrovně rizika (nízké, střední nebo vysoké), která se dá pak porovnat s vaší nakonfigurovanou úrovní rizika v Intune, aby se zjistilo, jestli se má při ohrožení zařízení odvolat přístup k určitým zvoleným zdrojům.

## <a name="what-data-does-intune-collect-for-mobile-threat-defense"></a>Která data Intune shromažďuje z důvodu ochrany před mobilními hrozbami?

Intune shromažďuje informace o inventáři aplikací ze zařízení jak v osobním, tak i firemním vlastnictví, a zpřístupňuje je zprostředkovatelům služby ochrany před mobilními hrozbami, jako je třeba aplikace Lookout for Work. Inventář aplikací můžete shromažďovat od uživatelů zařízení s iOSem 11 a novějším.

**Inventář aplikací**  
Inventáře ze zařízení s iOSem 11 a novějším v osobním i firemním vlastnictví se posílají zprostředkovateli služby ochrany před mobilními hrozbami. Data v inventáři aplikací zahrnují tyto údaje:

 - ID aplikace
 - Verze aplikace
 - Krátká verze aplikace
 - Název aplikace
 - Velikost sady prostředků aplikace
 - Dynamická velikost aplikace
 - Zda je aplikace ověřena nebo ne
 - Zda je aplikace spravována nebo ne

## <a name="sample-scenarios"></a>Ukázkové scénáře

Pokud řešení Mobile Threat Defense považuje zařízení za nakažené:

![Nakažené zařízení s ochranou službou Mobile Threat Defense](./media/MTD-image-1.png)

Přístup se udělí, když je zařízení opravené:

![Udělení přístupu službou Mobile Threat Defense](./media/MTD-image-2.png)

> [!NOTE] 
> Použití více dodavatelů služby Mobile Threat Defense s Intune není podporováno. Zapnutí několika nástrojů služby MTD vynutí instalaci všech aplikací MTD a zjišťování hrozeb napříč různými zařízeními.

## <a name="mobile-threat-defense-partners"></a>Partneři Mobile Threat Defense

Zjistěte, jak zabezpečit přístup k prostředkům společnosti na základě rizika zařízení, sítě a aplikace s:

- [Lookoutem](lookout-mobile-threat-defense-connector.md)
- [Skycure](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
