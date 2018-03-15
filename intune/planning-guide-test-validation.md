---
title: "Testování a ověřování Intune"
titlesuffix: Microsoft Intune
description: "Postup testování a ověřování čistě cloudového řešení Intune ve vašem prostředí"
keywords: 
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.openlocfilehash: 1346c0f5b0e1665e49e09fc566b9ff3da17fc17a
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2018
---
# <a name="intune-testing-and-validation"></a>Testování a ověřování Intune

Při testování implementace Microsoft Intune zvažte ověřování funkčnosti a ověřování případů použití. Ověřování funkčnosti spočívá v testování každé součásti a konfigurace, abyste zjistili, jestli fungují správně. Ověřování případů použití zahrnuje testování k ověření toho, že scénáře zahrnující řadu úkolů fungují podle očekávání. 

Doporučujeme do testovací fáze zapojit pracovníky IT, kteří mají na starosti podporu a helpdesk, aby vytvořili podpůrnou dokumentaci a zvykli si na podporou produktu. Pokud fungování součásti nebo scénáře neodpovídá případu použití, popište potřebné změny a uveďte důvod provedené změny.

## <a name="before-you-begin"></a>Před zahájením

Doporučujeme vytvořit následující dokumentaci:

-   **Testovací kritéria:** Identifikujte srovnávací testy pro měření.

-   **Součásti návrhu:** Musí existovat minimálně v jednom testovacím kritériu.

Pokud součást návrhu neexistuje minimálně v jednom testovacím kritériu, které odpovídá požadavku nebo scénáři, zvažte, jestli je tato součást návrhu potřeba. Nezapomeňte si také připravit následující věci:

-   **Účty:** Testovací účty licencované pro EMS a Office 365, aby bylo možné testovat všechny scénáře použití.

-   **Zařízení:** Testovací zařízení, která je možné vymazat nebo resetovat do výchozího továrního nastavení.

-   **Integrované komponenty:** Všechny integrované komponenty (Certificate Connector, Intune Service to Service Connector pro hostovaný Exchange a konektor Intune pro místní Exchange) by měly být nainstalované a nakonfigurované, pokud jsou potřeba.

V případě nečekaných komplikací možná bude potřeba změnit návrh. Všechny změny návrhu musí být plně dokumentované, včetně důvodu každé změny. Následující příklad ilustruje, o jaký druh změn může jít:

<blockquote>Zjistili jste, že nesplňujete požadavky služby zápisu síťových zařízení (NDES). Dále jste zjistili, že ke konfiguraci profilů VPN a Wi-Fi můžete použít kořenovou CA, která vyhovuje stejným požadavkům bez implementace NDES.</blockquote>

Při testování a ověřování se mohou vyskytnout problémy, které vyžadují technickou pomoc nebo odborné řešení potíží. Pokud hledáte pomoc, doporučujeme požádat o podporu prostřednictvím kanálů podpory Microsoftu.

-   [Informace o tom, jak získat podporu pro Intune](get-support.md)

-   [Kontakt na odbornou telefonickou podporu Microsoft Intune](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)

## <a name="functional-validation-testing"></a>Ověřovací testování funkčnosti

Ověřování funkčnosti spočívá v testování každé součásti a konfigurace, abyste zjistili, jestli fungují správně. Příklad testování a ověřování je v následující tabulce.

![9. část – tabulka 1](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a>Ověřovací testování případů použití

Ověřovací testování případů použití se provádí, aby se ověřilo, zda jsou scénáře použití úplné a funkční. Existují dva typy scénářů použití: správce IT a koncový uživatel.

### <a name="it-admin"></a>Správce IT

Ověřovací testování správce IT se provádí, aby se ověřilo správné fungování akcí při správě zařízení nebo uživatelů. Následující příklad obsahuje scénář koncového ověřování, které provádí správce IT.

![9. část – tabulka 2](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a>koncový uživatel

Ověřovací testování koncového uživatele se provádí, aby se ověřilo, jestli pracovní prostředí koncového uživatele funguje očekávaným způsobem a je správně prezentované při veškeré komunikaci uživatele. Je důležité k ověření, jestli má uživatel k dispozici funkce, které potřebuje. Pokud se vám ověření nepodaří, může se snížit míra přijetí a zvýšit objem volání na helpdesk.

![9. část – tabulka 3](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a>Další kroky

Jakmile jste otestovali a ověřili funkce a scénáře použití Intune, jste připraveni zahájit [ostrý provoz Intune](planning-guide-rollout-plan.md).

Další šablony a informace k plánování najdete v části s informacemi o [dalších prostředcích](planning-guide-resources.md).
