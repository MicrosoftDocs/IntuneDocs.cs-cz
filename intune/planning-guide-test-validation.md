---
title: Testování a ověřování Intune
titleSuffix: Microsoft Intune
description: Postup testování a ověřování čistě cloudového řešení Intune ve vašem prostředí
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 3/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: ba257ad6ebd7c8dbb2ca6ef805c896a4584ed41f
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59900175"
---
# <a name="intune-testing-and-validation"></a>Testování a ověřování Intune

Při testování implementace Microsoft Intune zvažte ověřování funkčnosti a ověřování případů použití. Ověřování funkčnosti spočívá v testování každé součásti a konfigurace, abyste zjistili, jestli fungují správně. Ověřování případů použití zahrnuje testování k ověření toho, že scénáře zahrnující řadu úkolů fungují podle očekávání. 

Doporučujeme do testovací fáze zapojit pracovníky IT, kteří mají na starosti podporu a helpdesk, aby vytvořili podpůrnou dokumentaci a zvykli si na podporou produktu. Pokud fungování součásti nebo scénáře neodpovídá případu použití, popište potřebné změny a uveďte důvod provedené změny.

## <a name="before-you-begin"></a>Před zahájením

Doporučujeme vytvořit následující dokumentaci:

-   **Testovací kritéria:** Identifikujte srovnávací testy pro měření.

-   **Součásti návrhu:** Musí existovat alespoň v jednom testovacím kritériu.

Pokud součást návrhu neexistuje minimálně v jednom testovacím kritériu, které odpovídá požadavku nebo scénáři, zvažte, jestli je tato součást návrhu potřeba. Nezapomeňte si také připravit následující věci:

-   **Účty:** Testovací účty licencované pro EMS a Office 365 a testovat všechny scénáře použití.

-   **Zařízení:** Testovací zařízení, které je možné vymazat nebo resetovat do továrního nastavení.

-   **Integrační komponenty:** Všechny integrované komponenty (certificate konektory a místní konektor Intune Exchange) by měl nainstalovaný a nakonfigurovaný v případě potřeby.

V případě nečekaných komplikací možná bude potřeba změnit návrh. Všechny změny návrhu musí být plně dokumentované, včetně důvodu každé změny. Následující příklad ilustruje, o jaký druh změn může jít:

<blockquote>Zjistili jste, že nesplňujete požadavky služby zápisu síťových zařízení (NDES). Dále jste zjistili, že ke konfiguraci profilů VPN a Wi-Fi můžete použít kořenovou CA, která vyhovuje stejným požadavkům bez implementace NDES.</blockquote>

Při testování a ověřování se mohou vyskytnout problémy, které vyžadují technickou pomoc nebo odborné řešení potíží. Pokud hledáte pomoc, doporučujeme požádat o podporu prostřednictvím kanálů podpory Microsoftu.

-   [Informace o tom, jak získat podporu pro Intune](get-support.md)

-   [Kontakt na odbornou telefonickou podporu Microsoft Intune](get-support.md)

## <a name="functional-validation-testing"></a>Ověřovací testování funkčnosti

Ověřování funkčnosti spočívá v testování každé součásti a konfigurace, abyste zjistili, jestli fungují správně. Příklad testování a ověřování je v následující tabulce.

![9. část – tabulka 1](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a>Ověřovací testování případů použití

Ověřovací testování případů použití se provádí, aby se ověřilo, zda jsou scénáře použití úplné a funkční. Existují dva typy scénářů použití: Správce IT a koncový uživatel.

### <a name="it-admin"></a>Správce IT

Ověřovací testování správce IT se provádí, aby se ověřilo správné fungování akcí při správě zařízení nebo uživatelů. Následující příklad obsahuje scénář koncového ověřování, které provádí správce IT.

![9. část – tabulka 2](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a>koncový uživatel

Ověřovací testování koncového uživatele se provádí, aby se ověřilo, jestli pracovní prostředí koncového uživatele funguje očekávaným způsobem a je správně prezentované při veškeré komunikaci uživatele. Je důležité k ověření, jestli má uživatel k dispozici funkce, které potřebuje. Pokud se vám ověření nepodaří, může se snížit míra přijetí a zvýšit objem volání na helpdesk.

![9. část – tabulka 3](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a>Další postup

Jakmile jste otestovali a ověřili funkce a scénáře použití Intune, jste připraveni zahájit [ostrý provoz Intune](planning-guide-rollout-plan.md).

Další šablony a informace k plánování najdete v části s informacemi o [dalších prostředcích](planning-guide-resources.md).
