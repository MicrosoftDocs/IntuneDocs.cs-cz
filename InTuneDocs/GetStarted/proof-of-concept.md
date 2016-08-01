---
title: "Testování konceptu | Microsoft Intune"
description: "Doporučení pro fázi ověření konceptu nasazení Intune"
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f3c97380-23ca-40da-acbc-78108507cad7
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c1e215320168c659d5f838355f6350111d6979b0
ms.openlocfilehash: 57f6d51a3f1e05a7edd260b0923d099510114a9f


---

# Testování konceptu (PoC)
Fáze testování konceptu by se měla soustředit na určení toho, jestli vaše nasazení dokáže splnit požadavky vaší společnosti. Tato fáze zahrnuje jednoduchou topologie určenou k ověření konkrétních technických scénářů.  Nasazení by se mělo provádět v testovacím prostředí a nemělo by hostovat žádné uživatele v produkčním nasazení.

## Proč je to důležité?
Testování konceptu je důležité pro zjištění vhodnosti vašeho nasazení, než se použije pro uživatele pilotního nasazení. Mělo by se považovat za malý experiment, ze kterého se dozvíte, jak bude Microsoft Intune fungovat ve vašem prostředí. Testování konceptu by mělo také ověřit konkrétní scénáře, dřív než se začne investovat do prostředků potřebný pro pilotní nasazení. To, co zjistíte při testování konceptu, by mělo ovlivnit návrh pilotního i produkčního nasazení.
Začněte tím, že si projdete zjišťovací otázky, které vám pomůžou vybrat a definovat testování konceptu.

## Zjišťovací otázky
Prodiskutujte tyto otázky se svým projektovým týmem, abyste mohli snadněji určit obor podrobností projektu, odkrýt možná rizika a definovat úkoly.

-   Jaké základní scénáře musí služba Intune splňovat, aby vyhovovala požadavkům vaší organizace na správu zařízení?

-   Které funkce chcete prozkoumat a ověřit?

-   Jaké prostředky musíte mít v testovacím prostředí, aby se daly tyto scénáře ověřit?

## Cíle z hlediska zaměření
V této části najdete pokyny k tomu, na co se v této stanovené fázi zavádění řešení zaměřit.

### Plánování
Před nasazením infrastruktury PoC musíte vědět, jaké scénáře je potřeba ověřit, a co k jejich ověření potřebujete.

### Helpdesk
Helpdesk se nemusí příprav na tuto fázi projektu účastnit, protože se do ní nezapojí žádná zařízení ani uživatelé v produkčním nasazení. Je to ale pro helpdesk příležitost seznámit se s nasazením a provozem Intune.

### Zvyšování povědomí o nasazovaném řešení
Technický tým a garanti z řad výkonného vedení firmy by měli mít přehled o průběhu testování scénářů. Tým, který má na starosti návrh celého řešení, se musí o zjištěných skutečnostech dozvědět, aby je zapracoval do svého návrhu.

### Školení
Správci, kteří budou spravovat uživatele, zařízení, zásady a aplikace, by měli testování konceptu využít jako příležitost, jak se seznámit s funkcemi a konzolou Intune.

### Operace
Testování konceptu nevyžaduje průběžný provoz. Provozní personál se ale může chtít s některými konkrétními scénáři seznámit nebo je ve fázi testování koncepce ověřit.

## Kontrolní seznam pro začátek
Tady je seznam kroků, které vám pomůžou začít s fází **testování konceptu**.

-   Definujte kritéria úspěšného testování koncepce. Měla by být založená na ověření obchodních a technických požadavků.

-   Určete požadované prostředky pro ověření testovacích scénářů.

-   Určete vhodné testovací prostředí, které bude napodobovat provozní prostředí, například potřebný počet zařízení nebo různé operační systémy.

## Běžné problémy
Tady jsou některé běžné problémy, na které můžete ve fázi **testování konceptu** narazit.

-   **Problém:** Zajištění toho, aby lidské a technické zdroje ověřily scénáře, které se podobají produkčním.

    **Zmírnění dopadů:** jasně se vyjádřete, že poznatky získané v prostředí PoC pomohou při vypracování technického návrhu a vylepší kvalitu následných fází. Nedostatek prostředků ve fázi PoC by znamenal, že se tyto poznatky získají až po dokončení technického návrhu a to může znamenat, že se návrh některých prvků bude měnit.

-   **Problém:** Definování testovacích scénářů, které by se vyžadovaly v produkčním prostředí.

    **Zmírnění dopadů:** Pracujte s garanty z řad výkonného vedení firmy a týmy uživatelů na tom, aby pochopili požadavky řešení klientské správy.

### Další kroky
[Pilotní nasazení](pilot.md)



<!--HONumber=Jul16_HO3-->


