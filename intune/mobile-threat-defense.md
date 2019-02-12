---
title: Mobile Threat Defense s Microsoft Intune | Microsoft Intune
description: Pomocí služby Intune Mobile Threat Defense (MTD) a partnerem Mobile Threat Defense můžete chránit přístup k podnikovým prostředkům na základě rizika zařízení.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/11/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cfe74086393ab3583c6238e6f252406665a3d17f
ms.sourcegitcommit: c0b954c82cd732b5328f92b618947bf425bf0a91
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/12/2019
ms.locfileid: "56086025"
---
# <a name="what-is-mobile-threat-defense-integration-with-intune"></a>Co je integrace služby Mobile Threat Defense s Intune?
Intune můžete integrovat data od dodavatele Mobile Threat Defense jako zdroje informací pro zásady dodržování předpisů a pravidla podmíněného přístupu. Tyto informace můžete použít k ochraně podnikovým prostředkům jako Exchange a SharePoint, protože blokují přístup z ohrožených mobilních zařízení.  

## <a name="what-problem-does-this-solve"></a>Jaký problém se tím vyřeší?
Integrování informací od dodavatele Mobile Threat Defense můžete chránit prostředky společnosti před hrozbami, které ovlivňují mobilní platformy.  

Společnosti obvykle jsou aktivní při ochraně počítačů před chybami zabezpečení a útokům, ale mobilní zařízení často zůstávají nemonitorovaná a nechráněná. Pokud mobilní platformy mají integrovanou ochranu, jako je například izolace aplikací nebo obchody s aplikacemi pro prověřené spotřebitele, tyto platformy nadále zranitelné vůči sofistikovaným útokům. Jako další zaměstnanci použít zařízení pro pracovní a přístup k citlivým informacím, informací od dodavatele Mobile Threat Defense můžete chránit před stále důmyslnějšími útoky zařízení a prostředky.  

## <a name="how-do-the-intune-mobile-threat-defense-connectors-work"></a>Jak fungují konektory Intune Mobile Threat Defense?

Intune používá k vytvoření kanálu komunikace mezi Intune a zvoleného dodavatele Mobile Threat Defense konektoru Mobile Threat Defense. Partneři Intune Mobile Threat Defense nabízejí intuitivní a snadno nasaditelné aplikace pro mobilní zařízení. Tyto aplikace aktivně kontrolují a analyzují informace o hrozbách do sdílely s Intune. Intune může využívat data pro účely nahlášení nebo vynucení.  

Příklad: Připojená aplikace Mobile Threat Defense sestavy dodavateli Mobile Threat Defense, že telefon ve vaší síti je připojen k síti, která je zranitelný vůči Man útocích střední. Tyto informace jsou k příslušné riziko úrovně nízké, rozdělené do kategorií, střední nebo vysoká. Tato úroveň rizika se následně porovnává s příspěvky úrovně rizika, nastavit v Intune. Založené na toto porovnání, přístup k určitým prostředkům podle vašeho výběru můžete odvolat, když dojde k ohrožení zařízení.

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
