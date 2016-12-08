---
title: "Zavedení aplikace | Microsoft Intune"
description: "Doporučení pro postupné zavádění aplikací v Microsoft Intune"
keywords: 
author: Nbigman
ms.author: nbigman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0fc32ed3-bcf4-472a-80e7-eb20986f78fa
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8921043334630bbd2955c0423ca9cd1b76c27758
ms.openlocfilehash: aea7c235ad643a2a03ac7b3ea68c6b8c717bcd48


---

# Zavedení aplikace
Toto téma poskytuje konkrétní doporučení pro postupné zavádění aplikací v Microsoft Intune. Obecné informace o fázích zavedení najdete v tématu [Fáze zavedení pro nasazení Microsoft Intune](rollout-phases-for-microsoft-intune-deployment.md).

### Fáze zavedení aplikace
Fáze zavedení aplikace jsou následující:

-   Stanovení rozsahu projektu

-   Ověření konceptu

-   Pilotní nasazení

-   Podnikové zavedení

-   Provoz a údržba

## Stanovení rozsahu projektu
Vezměte v úvahu tyto informace:

-   Úlohy uživatele, které má tato aplikace umožňovat.

-   Vhodnosti aplikace pro uživatele a jejich zařízení (všechny operační systémy, které se můžou použít).

-   Zkontrolujte, že instalační program aplikace, který jste zvolili, je podporován distribucí aplikací Intune, jak je popsáno v tématu [Přidávání aplikací s Microsoft Intune](/intune/deploy-use/add-apps).

-   Ověřte, že jsou nainstalované požadavky distribuce aplikací. <!---, as described in [Plan for app deployment in Microsoft Intune](plan-for-app-deployment-in-microsoft-intune.md).--->

-   Ujistěte se, že je typ aplikace podporovaný v Intune.

-   Zkontrolujte, že máte v cloudovém úložišti dost místa pro nahrání aplikace. Pokyny k nákupu dalšího úložiště jsou uvedeny v tématu [Přidávání aplikací s Microsoft Intune](/intune/deploy-use/add-apps).

> [!NOTE]           
> Můžete si stáhnout tuto [šablonu plánování pro mobilní aplikace](https://gallery.technet.microsoft.com/Mobile-app-planning-18689d59), která vám usnadní proces zavádění.

## Ověření konceptu
Ve fázi ověření konceptu otestujte nasazení aplikace v testovacím prostředí na zařízeních a uživatelích, které jste nakonfigurovali výhradně pro účely testování.

-   Do této fáze zapojte helpdesk, abyste zjistili, jaké problémy můžou nastat během pilotního a produkčního nasazení. Informace o řešení potíží jsou k dispozici v tématu [Řešení problémů s nasazením aplikací v Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune).

-   V tomto okamžiku byste měli vytvořit informační plány pro uživatele v pilotním i produkčním nasazení. Tyto plány by měly minimálně zahrnovat to, jaká aplikace se nasazuje, jak a kdy ji uživatelé obdrží, jaký je obchodní účel tohoto nasazení a co dělat, když narazí na problémy (informace o samoobslužné pomoci i postup kontaktování helpdesku).

## Pilotní nasazení
V průběhu pilotní fáze nasadíte aplikaci pro malou skupinu testovacích uživatelů a zařízení. Vezměte v úvahu tyto informace:

-   Zajistěte, aby testovací skupina reprezentovala zařízení a uživatele, kteří budou aplikaci po produkčním zavedení používat.

-   Informujte pracovníky helpdesku o nasazení aplikace a zajistěte, aby byli připravení pomáhat uživatelům v testovací skupině.

-   Zvolte testovací uživatele, kteří podrobí aplikaci typickému využití a budou spolehlivě hlásit problémy správcům pilotního nasazení.

-   Aktivujte informační plán pro pilotní uživatele.

## Podnikové zavedení

-   Výsledky pilotního nasazení slouží k úpravě podnikového zavedení.

-   Informujte pracovníky helpdesku o plánovaném zavedení aplikace. Mějte připravené mechanismy, které vám umožní reagovat na požadavky a zavedení podle potřeby upravit.

-   Připravte se na řešení potíží s nasazením (pokud k nim dojde).

-   Aktivujte informační plán pro produkční uživatele.

-   Použijte při nasazení aplikace postupnou metodu, přidávejte skupiny po krocích, aby bylo zajištěno, že zavedení plynule pokračuje.

## Provoz a údržba
**Provoz:** Monitorujte konzolu Intune, jestli neobsahuje výstrahy nebo problémy s uživateli nebo zařízeními, a ujistěte se, že distribuce aplikace probíhá podle vašeho návrhu.

**Helpdesk:** Zajistěte, aby pracovníci helpdesku věděli o všech změnách dostupnosti aplikace, které by mohly způsobit vznik požadavků na podporu.

### Viz taky
[Nasazení aplikací](/intune/deploy-use/deploy-apps)

[Řešení problémů s nasazením aplikací v Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune)



<!--HONumber=Oct16_HO4-->


