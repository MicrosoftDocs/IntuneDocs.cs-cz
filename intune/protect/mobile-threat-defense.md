---
title: Ochrana před mobilními hrozbami pomocí Microsoft Intune
titleSuffix: Microsoft Intune
description: Pomocí služby Intune Mobile Threat Defense (MTD) a partnerem Mobile Threat Defense můžete chránit přístup k podnikovým prostředkům na základě rizika zařízení.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b67e3b14fd94376fb6dacad88fa58ddc460a6bc5
ms.sourcegitcommit: 807ab3e35f4d9ffa18655410b7d61e5e772ab348
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/30/2019
ms.locfileid: "73057585"
---
# <a name="mobile-threat-defense-integration-with-intune"></a>Integrace ochrany před mobilními hrozbami do Intune

Intune může integrovat data od dodavatele ochrany před mobilními hrozbami (MTD) jako zdroj informací pro zásady dodržování předpisů zařízením a pravidla podmíněného přístupu zařízení. Tyto informace můžete použít k ochraně firemních prostředků, jako jsou Exchange a SharePoint, blokováním přístupu z ohrožených mobilních zařízení.

Intune může používat stejná data jako zdroj pro neregistrovaná zařízení pomocí zásad ochrany aplikací Intune. Správci tak můžou tyto informace použít k ochraně podnikových dat v rámci [aplikace Microsoft Intune Protected](~/apps/apps-supported-intune-apps.md)a vystavení bloku nebo selektivního vymazání.

## <a name="protect-corporate-resources"></a>Ochrana firemních prostředků

Integrace informací od dodavatelů MTD vám může přispět k ochraně firemních prostředků před hrozbami, které mají vliv na mobilní platformy.  

Společnosti jsou obvykle aktivní v ochraně počítačů před ohroženími zabezpečení a útokem, zatímco mobilní zařízení se často nemonitorují a nechrání. V případě, že mobilní platformy mají integrovanou ochranu, jako je izolace aplikací a obchody pro aplikace prověřené Consumer, tyto platformy zůstanou zranitelné vůči sofistikovaným útokům. Jak zaměstnanci používají zařízení k práci a k přístupu k citlivým informacím, můžou informace od dodavatelů MTD pomáhat při ochraně zařízení a vašich prostředků před stále sofistikovanými útoky.

## <a name="intune-mobile-threat-defense-connectors"></a>Konektory Intune Mobile Threat Defense

Intune používá konektor ochrany před mobilními hrozbami k vytvoření kanálu komunikace mezi Intune a vybraným dodavatelem MTD. Partneři Intune MTD nabízejí intuitivní a snadno nasazovatelné aplikace pro mobilní zařízení. Tyto aplikace aktivně prohledají a analyzují informace o hrozbách pro sdílení s Intune. Intune může data použít buď pro účely vytváření sestav, nebo pro účely vynucení.

Příklad: připojená aplikace MTD k dodavateli MTD, že telefon ve vaší síti je aktuálně připojený k síti, která je zranitelná vůči útokům prostředníkem. Tyto informace jsou rozdělené na odpovídající úroveň rizika nízká, střední nebo vysoká. Tato úroveň rizika se pak porovnává s přídavky na úrovni rizika, které jste nastavili v Intune. Na základě tohoto porovnání může být přístup k určitým prostředkům podle vašeho výběru odvolán, pokud dojde k ohrožení zabezpečení zařízení.

## <a name="data-that-intune-collects-for-mobile-threat-defense"></a>Data, která Intune shromažďuje pro ochranu před mobilními hrozbami

Pokud je tato možnost povolená, shromažďuje Intune informace o inventáři aplikací z osobních zařízení i ze zařízení vlastněných firmou a zpřístupňuje je, aby je MTD poskytovatelé načetli, například Lookout for Work. Inventář aplikací můžete shromažďovat od uživatelů zařízení s iOSem.

Tato služba vyžaduje výslovný souhlas; žádné informace inventáře aplikací se ve výchozím nastavení nesdílí. Správce Intune musí povolit **synchronizaci aplikací pro zařízení s iOS** v nastavení konektoru ochrany před mobilními hrozbami předtím, než se nasdílí všechny informace o inventáři aplikace.

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

## <a name="sample-scenarios-for-enrolled-devices-using-device-compliance-policies"></a>Ukázkové scénáře zaregistrovaných zařízení pomocí zásad dodržování předpisů pro zařízení

Pokud řešení Mobile Threat Defense považuje zařízení za nakažené:

![Obrázek znázorňující nakažené zařízení s ochranou pomocí služby Mobile Threat Defense](./media/mobile-threat-defense/MTD-image-1.png)

Přístup se udělí, když je zařízení opravené:

![Obrázek znázorňující udělení přístupu službou Mobile Threat Defense](./media/mobile-threat-defense/MTD-image-2.png)

## <a name="sample-scenarios-for-unenrolled-devices-using-intune-app-protection-policies"></a>Ukázkové scénáře neregistrovaných zařízení pomocí zásad ochrany aplikací Intune

Pokud řešení Mobile Threat Defense považuje zařízení za nakažené:<br>
![Obrázek znázorňující napadené zařízení s ochranou před mobilními hrozbami](./media/mobile-threat-defense/MTD-image-3.png)

Přístup se udělí, když je zařízení opravené:<br>
![Obrázek znázorňující přístup k obraně před mobilními hrozbami udělený](./media/mobile-threat-defense/MTD-image-4.png)

> [!NOTE]
> Můžete použít více dodavatelů mobilní ochrany s jedním klientem Intune. Pokud jsou však pro stejnou platformu nakonfigurovány dva nebo více dodavatelů, všechna zařízení, která tuto platformu spouštějí, musí nainstalovat každou aplikaci MTD a vyhledat hrozby. Nepovedlo se odeslat kontrolu z nenakonfigurovaných výsledků aplikace v zařízení, které je označené jako nedodržující předpisy. 

## <a name="mobile-threat-defense-partners"></a>Partneři Mobile Threat Defense

Zjistěte, jak zabezpečit přístup k prostředkům společnosti na základě rizika zařízení, sítě a aplikace s:

- [Lookout for Work](lookout-mobile-threat-defense-connector.md)
- [Symantec Endpoint Protection Mobile](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
- [Pradeo](pradeo-mobile-threat-defense-connector.md)
- [Better Mobile](better-mobile-threat-defense-connector.md)
- [Sophos Mobile](sophos-mtd-connector.md)
- [Obrana proti mobilním hrozbám Wandera](wandera-mtd-connector.md)