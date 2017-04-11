---
title: "Vymezení cílů, úkolů a problémů při nasazení Intune | Dokumentace Microsoftu"
description: "Tento článek pomáhá určit cíle, úkoly a problémy spojené s cloudovou implementací Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 24cf9d97-db39-4b95-a664-4aa2e33edb87
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: 2e46c5612c120a24d3f8fe32decd3eb7a0d4e709


---

# <a name="determine-intune-deployment-goals-objectives-and-challenges"></a>Vymezení cílů, úkolů a problémů při nasazení Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Dobrý plán nasazení začíná identifikací cílů, úkolů a potenciálních problémů spojených s nasazením řešení v organizaci. Každá organizace je jedinečná, a proto bude mít při nasazení vlastní cíle, úkoly i problémy. Pojďme se na jednotlivé oblasti podívat podrobněji.

## <a name="deployment-goals"></a>Cíle nasazení

Cíle nasazení jsou dlouhodobé výsledky dosažené implementací Microsoft Intune v organizaci. Tady je několik příkladů cílů nasazení Intune v organizaci, včetně jejich popisu a obchodní hodnoty.

-   **Integrace s Office 365 a podpora použití mobilních aplikací Office**

    -   **Popis:** Zajištění úzké integrace Office 365 a použití mobilních aplikací Office, včetně jejich ochrany.

    -   **Obchodní hodnota:** Zabezpečené a vylepšené uživatelské prostředí, které umožňuje uživatelům používat známé a oblíbené aplikace.

-   **Zpřístupnění interních firemních služeb na mobilních zařízeních**

    -   **Popis:** Strategickým cílem organizace je umožnit zaměstnancům, aby byli produktivní všude, kde potřebují pracovat, a s libovolným zařízením, které je pro ně nejvhodnější. Projekt má zajistit mobilní produktivitu a bezpečný přístup k firemním datům.

    -   **Obchodní hodnota:** Umožňuje zaměstnancům, aby byli aktivní a mohli pracovat odkudkoliv. Podnikům zase nabízí větší konkurenceschopnost a přínosnější pracovní prostředí.

-   **Zajištění ochrany dat v mobilních zařízeních**

    -   **Popis:** Pokud jsou data uložená v mobilním zařízení, musí být chráněná proti poškození a náhodné ztrátě nebo sdílení.

    -   **Obchodní hodnota:** Ochrana dat je nezbytným předpokladem zachování konkurenceschopnosti, který organizaci umožňuje zacházet s klienty a jejich daty co nejopatrněji.

-   **Snižování nákladů**

    -   **Popis:** Pokud je to možné, snižuje projekt náklady na nasazení a provoz.

    -    **Obchodní hodnota:** Efektivní využití prostředků umožňuje podnikům investovat do jiných oblastí, zachovat si konkurenceschopnost a poskytovat lepší služby klientům.

## <a name="deployment-objectives"></a>Úkoly nasazení

Úkoly nasazení jsou akce, které může organizace podniknout, aby dosáhla cílů nasazení Microsoft Intune. Tady jsou některé příklady úkolů při nasazení řešení v organizaci, včetně způsobu jejich provedení.

-   **Snížení počtu řešení pro správu zařízení**
<br>
    -   **Způsob provedení:** Sjednocení různých řešení do jediného řešení pro správu mobilních zařízení Microsoft Intune, které chrání firemní data v aplikacích a zařízeních.
<br></br>
-   **Zajištění bezpečného přístupu k Exchangi a SharePointu Online**
<br>
    -   **Způsob provedení:** Implementace podmíněného přístupu v Microsoft Intune pro Exchange a SharePoint Online.
<br></br>
-   **Zabránění ukládání nebo přeposílání firemních dat v mobilním zařízení jiným než firemním službám**
<br>
    -   **Způsob provedení:** Implementovat zásady ochrany aplikací v Microsoft Intune pro Microsoft Office a obchodní aplikace.
<br></br>
-   **Možnost smazání firemních dat ze zařízení**
<br>
    -   **Provedení:** Registrace a správa zařízení v Microsoft Intune, možnost v případě potřeby vzdáleně vymazat firemní data a prostředky.

## <a name="deployment-challenges"></a>Problémy při nasazení

Problémy při nasazení mají pro organizaci nejvyšší prioritu, protože mohou negativně ovlivnit nasazení. Někdy mohou souviset s předchozími problémy, se kterými se organizace potýkala při minulých projektech a teď se jim chce vyhnout. Nebo může jít o nové problémy spojené s aktuálním úsilím o nasazení řešení. Tady je několik příkladů problémů, se kterými se může organizace setkat při nasazování Microsoft Intune, spolu s jejich možným řešením.

-   Do počátečního rozsahu projektu není zahrnuta připravenost podpory a zkušenost koncových uživatelů.  Výsledkem je špatné přijetí řešení koncovými uživateli a problémy s jeho podporou.
<br>
    -   **Zmírnění dopadů:** Zahrňte do plánu nasazení školení podpory a ověřte zkušenosti koncových uživatelů pomocí metrik úspěšnosti.
<br></br>
-   Nedostatek jasně definovaných metrik, které měří úspěšnost projektu, může vést k abstraktním výsledkům a k negativním reakcím v případě problémů.
<br>
    -   **Zmírnění dopadů:** Definujte cíle a metriky úspěšnosti už na začátku projektu a použijte tyto údaje, abyste podpořili další zaváděcí fáze. Zajistěte, aby byly cíle stanoveny podle hodnocení kvality SMART, tzn. byly konkrétní (Smart), měřitelné (Measurable), dosažitelné (Attainable), realistické (Realistic) a ohraničené čase (Time-bound), naplánujte vyhodnocování podle svých cílů v jednotlivých fázích a zajistěte, aby váš projekt probíhal v souladu s plánem.
<br></br>
-   Pokud opomenete vytvořit, ověřit a aktivně sdílet jasný návrh získané hodnoty, který bude v organizaci příznivě přijat, často to povede jen k omezenému přijetí řešení a nedostatečné návratnosti investice (ROI).
<br>
    -   **Zmírnění dopadů:** Pravděpodobně se už nemůžete dočkat, až projekt zahájíte. Předtím se ale ujistěte, že máte jasně definované cíle a úkoly. Ty pak uvádějte na všech propagačních akcích a školeních, abyste pomohli uživatelům pochopit, proč organizace vybrala Intune.

## <a name="next-section"></a>Další část

Po identifikaci cílů, úkolů a možných problémů při nasazení můžete přejít k další části, kterou je [identifikace scénářů použití](section-2-identify-use-case-scenarios.md).



<!--HONumber=Dec16_HO5-->


