---
title: "Zavedení zásad | Microsoft Intune"
description: "Doporučení pro postupné zavádění zásad v Microsoft Intune"
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 390d5adf-86d2-4e23-ba93-1e61e6b1028b
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2a192c71b1b82f59b34ea614d09d895174f8112b
ms.openlocfilehash: 0c23fdd5f5e6bc1b50dda56fe2135e8cc24b5e26


---

# Zavedení zásad
Toto téma poskytuje konkrétní doporučení pro postupné zavádění zásad v Microsoft Intune. Vztahuje se na první zásady, které použijete v novém nasazení Intune, i na zásady, které přidáte k už existujícímu nasazení.

Obecné informace o fázích zavedení najdete v tématu [Fáze zavedení pro nasazení Microsoft Intune](rollout-phases-for-microsoft-intune-deployment.md).

### Fáze zavedení zásad
Fáze zavedení zásad jsou tyto:

-   Stanovení oboru projektu

-   Ověření konceptu

-   Pilotní nasazení

-   Podnikové zavedení

-   Provoz a údržba

## Stanovení oboru projektu
Definujte rozsah nasazení zásad Intune:

-   U nové implementace bude nutné definovat všechny požadované způsoby chování jednotlivých zařízení a požadavky na zabezpečení, které chcete pomocí sady zásad vytvořit.

-   Rozhodněte se, kterých uživatelů a zařízení by se tyto zásady měly týkat.

-   Navrhněte skupiny uživatelů a zařízení, které vám umožní použít nové zásady odpovídajícím způsobem.

-   Zjistěte, jestli jsou k jednotlivým operačním systémům přidružené nějaké požadavky nebo omezení, které ovlivní vaše zásady.

-   Vezměte v úvahu specifika návrhu zásad, například typ zásad a šablony, které se mají použít.

-   Zvažte, jak budou různé zásady vzájemně interagovat a jaké bude pravděpodobné chování jednotlivých zařízení (bez ohledu na to, jestli vytváříte svou první sadu zásad nebo přidáváte nové zásady k už existujícím). Konflikty a problémy se vzájemnou interakcí zásad se dají zjistit ve fázi pilotního nasazení, ale pokud je zjistíte až na začátku plánování, pilotní fázi si tak zjednodušíte.

## Ověření konceptu
Ve fázi ověření konceptu otestujte nasazení zásad v testovacím prostředí na zařízeních a uživatelích, které jste nakonfigurovali výhradně pro účely testování.

-   Do této fáze zapojte helpdesk, abyste zjistili, jaké problémy můžou nastat během pilotního a produkčního nasazení. Informace o řešení potíží najdete v tématu [Řešení potíží se zásadami v Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune).

-   V tomto okamžiku byste měli vytvořit informační plány pro uživatele v pilotním i produkčním nasazení. Tyto plány by měly minimálně zahrnovat to, jak a kdy se změní chování jednotlivých zařízení, jaký je obchodní účel této změny a co dělat, když uživatelé nebo pracovníci IT narazí na problémy (informace o samoobslužné pomoci i postup kontaktování helpdesku).

## Pilotní nasazení
V průběhu pilotní fáze nasadíte zásady pro malou skupinu testovacích uživatelů a zařízení. Při pilotním nasazení zásad v Intune byste měli vzít konkrétně v úvahu:

-   Testovací skupina by měla vystihovat skupinu, pro kterou se zásady použijí při uvedení do provozu.

-   Informujte pracovníky helpdesku o změnách zásad a zajistěte, aby byli připravení pomáhat uživatelům v testovací skupině.

-   Aktivujte informační plán pro pilotní uživatele.

-   Pilotní nasazení můžete nejdřív využít v izolovaném režimu, kde se na zařízení nevztahují jiné zásady, které by mohly způsobit konflikty a nežádoucí chování.

-   Finální testování musí vzít v úvahu nové zásady a všechny už existující zásady, které se pro jednotlivá zařízení použijí.

## Podnikové zavedení

-   Na základě výsledků pilotního nasazení upravte naplánované zásady a opravte případné konflikty zásad a neočekávané chování.

-   Informujte pracovníky helpdesku o plánovaném podnikovém zavedení. Mějte připravené mechanismy, které vám umožní reagovat na požadavky a zavedení podle potřeby upravit.

-   Připravte se na řešení potíží se zásadami (pokud k nim dojde).

-   Aktivujte informační plán pro produkční uživatele.

-   Postupně použijte zásady pro další skupiny, monitorujte stav zásad u příslušných zařízení a sledujte požadavky na helpdesk, které se mohou vztahovat k novým zásadám.

## Provoz a údržba
**Provoz:** Monitorujte konzolu Intune, jestli neobsahuje výstrahy nebo problémy s uživateli nebo zařízeními, a kontrolujte, že zásady fungují tak, jak jste zamýšleli.

**Helpdesk:** Zajistěte, aby pracovníci helpdesku věděli o všech změnách zásad, které ovlivní uživatelské prostředí, protože by mohly způsobit vznik požadavků na podporu.


### Související témata
[Příprava před konfigurací zásad správy mobilních aplikací pomocí Microsoft Intune](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

[Řešení potíží se zásadami v Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune)



<!--HONumber=Jul16_HO4-->


