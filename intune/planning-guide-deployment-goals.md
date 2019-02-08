---
title: Vymezení cílů, úkolů a problémů při nasazení
titlesuffix: Microsoft Intune
description: Tento článek pomáhá vymezit cíle, úkoly a problémy spojené s cloudovou implementací Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 24cf9d97-db39-4b95-a664-4aa2e33edb87
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: b30fd61bd00cc32da4d9a85a08ae06327a8aea96
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850671"
---
# <a name="determine-deployment-goals-objectives-and-challenges"></a>Vymezení cílů, úkolů a problémů při nasazení

Dobrý plán nasazení začíná identifikací cílů, úkolů a potenciálních problémů spojených s nasazením řešení v organizaci. Pojďme se na jednotlivé oblasti podívat podrobněji.

## <a name="deployment-goals"></a>Cíle nasazení

Cíle nasazení jsou dlouhodobé výsledky, kterých chcete nasazením Intune v organizaci dosáhnout. Tady je několik příkladů takových cílů, včetně jejich popisu a obchodní hodnoty.

-   **Integrace s Office 365 a podpora použití mobilních aplikací Office**

    -   **Popis:** Zajištění úzké integrace Office 365 a použití mobilních aplikací Office pomocí zásad ochrany aplikací.

    -   **Obchodní hodnota:** Zabezpečené a vylepšené uživatelské prostředí tím, že uživatelům používat aplikace, které znají a dáváte přednost.

-   **Zpřístupnění interních firemních služeb na mobilních zařízeních**

    -   **Popis:** Povolte zaměstnancům, aby byli produktivní všude, kde potřebují pracovat, a s libovolným zařízením je pro ně nejvhodnější. Projekt má zajistit mobilní produktivitu a bezpečný přístup k firemním datům.

    -   **Obchodní hodnota:** Povolení zaměstnanců, kteří budou pracovat odkudkoliv, kde potřebují umožňuje firmám větší konkurenceschopnost a přínosnější pracovní prostředí.

-   **Zajištění ochrany dat v mobilních zařízeních**

    -   **Popis:** Pokud jsou data uložená na mobilních zařízeních, by měly být chráněné proti poškození a náhodné ztrátě nebo sdílení.

    -   **Obchodní hodnota:** Ochrana dat je důležité k zajištění konkurenceschopnosti a organizaci umožňuje zacházet klienty a jejich data s nejvyšší opatrností.

-   **Snižování nákladů**

    -   **Popis:** Pokud je to možné, snižuje projekt nasazení a provozní náklady.

    -    **Obchodní hodnota:** Efektivní využívání prostředků umožňuje podnikům investovat do jiných oblastí, konkurenceschopnost a poskytovat lepší služby klientům.

## <a name="deployment-objectives"></a>Úkoly nasazení

Úkoly nasazení jsou akce, které musí organizace provést, aby dosáhla cílů nasazení Intune. Tady jsou některé příklady úkolů při nasazení, včetně způsobu jejich plnění.

-   **Snížení počtu řešení pro správu zařízení**

    -   **Implementace:** Konsolidovat do řešení pro správu jednoho mobilního zařízení: Microsoft Intune chrání firemní data z aplikací a zařízení.

-   **Zajištění zabezpečeného přístup k Exchangi a SharePointu Online**

    -   **Implementace:** Použití podmíněného přístupu pro Exchange a SharePoint Online.

-   **Zabránění ukládání nebo přeposílání firemních dat v mobilním zařízení jiným než firemním službám**

    -   **Implementace:** Použijte zásady ochrany aplikací Intune pro Microsoft Office a -obchodní aplikace.

-   **Zajistit možnost vymazání firemních dat ze zařízení**

    -   **Implementace:** Registrace zařízení do Intune. V případě potřeby si tím zajistíte možnost vzdáleného vymazání firemních dat a prostředků.

## <a name="deployment-challenges"></a>Aspekty nasazení

Problémy při nasazení mají pro organizaci nejvyšší prioritu, protože mohou negativně ovlivnit nasazení. Někdy souvisejí s minulými problémy z předchozích projektů, kterým byste se chtěli vyhnout, nebo s novými problémy, které se týkají současného nasazení. Tady jsou příklady problémů při nasazení Intune spolu s možnostmi, jak je zmírnit.

-   Při úvodním stanovení rozsahu projektu se nepřihlédlo k připravenosti podpory a zkušenostem koncových uživatelů. To vede k nedostatečnému osvojení koncovými uživateli a k problémům s podporou v organizaci.

    -   **Omezení rizik:** Zahrnout podporu školení. Doplnit plán nasazení o ověření zkušeností koncových uživatelů prostřednictvím měřítek úspěšnosti.

-   Nedostatek jasně definovaných cílů a měřítek úspěšnosti vede k nedefinovatelným výsledkům. Při vzniku problémů se organizace může dostat do situace, kdy na ně reaguje dodatečně.

    -   **Omezení rizik:** Definování cílů a měřítek úspěšnosti již v rané fázi v stanovování oboru projektu a používejte tyto datové body, abyste podpořili další zaváděcí fáze. Zajistěte, aby cíle vyhovovaly pravidlu SMART (Specific = konkrétní, Measurable = měřitelné, Attainable = dosažitelné, Realistic = reálné a Timely = včas). V každé fázi naplánujte měření cílů, abyste zajistili průběh projektu podle plánu.

-   Opomenete vytvořit , ověřit a důsledně sdílet jasný návrh přidané hodnoty, který zajistí podporu celé organizace. Častým důsledkem je omezené osvojení a nedostatečná návratnost investic (ROI).

    -   **Omezení rizik:** Zatímco lze také přejít do vašeho projektu, zkontrolujte, jestli že je máte jasně definované cíle a úkoly. Ty pak uvádějte na všech propagačních akcích a školeních, abyste pomohli uživatelům pochopit, proč organizace vybrala Intune.

## <a name="next-steps"></a>Další postup

Teď, když jste identifikovali cílů nasazení, úkolů a možných problémů při, přejít k další části: [Identifikace scénářů použití](planning-guide-scenarios.md).
