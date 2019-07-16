---
title: Ochrana před mobilními hrozbami pomocí Microsoft Intune
titleSuffix: Microsoft Intune
description: Pomocí služby Intune Mobile Threat Defense (MTD) a partnerem Mobile Threat Defense můžete chránit přístup k podnikovým prostředkům na základě rizika zařízení.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 73c8167c91129d79a98674a92e7ccc5487a6b283
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "67885085"
---
# <a name="what-is-mobile-threat-defense-integration-with-intune"></a>Co je integrace služby Mobile Threat Defense s Intune?
Intune může integrovat data od dodavatele ochrany před mobilními hrozbami jako zdroj informací pro zásady dodržování předpisů a pravidla podmíněného přístupu. Tyto informace můžete použít k ochraně firemních prostředků, jako jsou Exchange a SharePoint, blokováním přístupu z ohrožených mobilních zařízení.  

## <a name="what-problem-does-this-solve"></a>Jaký problém se tím vyřeší?
Integrace informací od dodavatele ochrany před mobilními hrozbami vám může přispět k ochraně firemních prostředků před hrozbami, které mají vliv na mobilní platformy.  

Společnosti jsou obvykle aktivní v ochraně počítačů před ohroženími zabezpečení a útokem, zatímco mobilní zařízení se často nemonitorují a nechrání. V případě, že mobilní platformy mají integrovanou ochranu, jako je izolace aplikací a obchody pro aplikace prověřené Consumer, tyto platformy zůstanou zranitelné vůči sofistikovaným útokům. Jak zaměstnanci používají zařízení k práci a přístup k citlivým informacím, může vám informace od dodavatele ochrany před mobilními hrozbami chránit zařízení a prostředky před stále sofistikovanými útoky.  

## <a name="how-do-the-intune-mobile-threat-defense-connectors-work"></a>Jak fungují konektory Intune Mobile Threat Defense?

Intune používá konektor pro ochranu před mobilními hrozbami k vytvoření kanálu komunikace mezi Intune a vybraným dodavatelem ochrany před mobilními hrozbami. Partneři ochrany před mobilními hrozbami Intune nabízejí intuitivní a snadno nasazovatelné aplikace pro mobilní zařízení. Tyto aplikace aktivně prohledají a analyzují informace o hrozbách pro sdílení s Intune. Intune může data použít buď pro účely vytváření sestav, nebo pro účely vynucení.  

Příklad: Mobilní aplikace pro ochranu před mobilními hrozbami oznamuje dodavateli ochrany před mobilními hrozbami, že telefon ve vaší síti je aktuálně připojený k síti, která je v prostředním útoku zranitelná pro člověka. Tyto informace jsou rozdělené na odpovídající úroveň rizika nízká, střední nebo vysoká. Tato úroveň rizika se pak porovnává s přídavky na úrovni rizika, které jste nastavili v Intune. Na základě tohoto porovnání může být přístup k určitým prostředkům podle vašeho výběru odvolán, pokud dojde k ohrožení zabezpečení zařízení.

## <a name="what-data-does-intune-collect-for-mobile-threat-defense"></a>Která data Intune shromažďuje z důvodu ochrany před mobilními hrozbami?

Pokud je to povoleno, Intune shromažďuje informace o inventáři aplikací ze zařízení jak v osobním, tak i firemním vlastnictví, a zpřístupňuje je zprostředkovatelům služby ochrany před mobilními hrozbami, jako je třeba aplikace Lookout for Work. Inventář aplikací můžete shromažďovat od uživatelů zařízení s iOSem.

Tato služba vyžaduje výslovný souhlas; žádné informace inventáře aplikací se ve výchozím nastavení nesdílí. Jako správce Intune musíte v nastavení služby povolit synchronizaci aplikací pro zařízení s iOSem, než se budou informace inventáře aplikací sdílet.

**Inventář aplikací**  
Pokud synchronizaci aplikací pro zařízení s iOSem povolíte, inventáře ze zařízení s iOSem v osobním i firemním vlastnictví se budou odesílat zprostředkovateli služby ochrany před mobilními hrozbami. Data v inventáři aplikací zahrnují tyto údaje:

- ID aplikace
- Verze aplikace
- Krátká verze aplikace
- Název aplikace
- Velikost sady prostředků aplikace
- Dynamická velikost aplikace
- Jestli je aplikace ověřená nebo ne
- Jestli je aplikace spravovaná nebo ne

## <a name="sample-scenarios"></a>Ukázkové scénáře

Pokud řešení Mobile Threat Defense považuje zařízení za nakažené:

![Obrázek znázorňující nakažené zařízení s ochranou pomocí služby Mobile Threat Defense](./media/MTD-image-1.png)

Přístup se udělí, když je zařízení opravené:

![Obrázek znázorňující udělení přístupu službou Mobile Threat Defense](./media/MTD-image-2.png)

> [!NOTE] 
> Použití více dodavatelů služby Mobile Threat Defense s Intune není podporováno. Zapnutí několika nástrojů služby MTD vynutí instalaci všech aplikací MTD a zjišťování hrozeb napříč různými zařízeními.

## <a name="mobile-threat-defense-partners"></a>Partneři Mobile Threat Defense

Zjistěte, jak zabezpečit přístup k prostředkům společnosti na základě rizika zařízení, sítě a aplikace s:

- [Lookoutem](lookout-mobile-threat-defense-connector.md)
- [Symantec Endpoint Protection Mobile](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
- [Pradeo](pradeo-mobile-threat-defense-connector.md)
- [Better Mobile](better-mobile-threat-defense-connector.md)
- [Sophos Mobile](sophos-mtd-connector.md)
- [Obrana proti mobilním hrozbám Wandera](wandera-mtd-connector.md)
