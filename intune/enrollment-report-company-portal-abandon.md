---
title: Sestava neúplné uživatele registrace v Intune
titleSuffix: Microsoft Intune
description: Informace o registraci neúplné uživatele.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 2/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 78d55ef2baf0608d22af53bf0803634700e01eb3
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61505858"
---
# <a name="incomplete-user-enrollments-report"></a>Sestava registrace neúplné uživatele

Tato sestava informuje, kde na portálu společnosti nejsou uživatelé proces registrace dokončí proces registrace.

Chcete-li zobrazit sestavy, zvolte **Intune** > **registrace zařízení** > **registrací neúplné uživatele**.

Na základě těchto informací můžete aktualizovat vaše dokumenty připojování k poskytování pomoci uživatelům bylo možné registraci dokončit. Pokud například končí mnoho uživatelů u podmínek použití, můžete tuto oblast prozkoumat a upravit, aby byla pro uživatele intuitivnější.

## <a name="what-is-an-incomplete-enrollment"></a>Co je neúplný registrace?

Neúplný zápis je, když uživatel provede některou z následujících akcí:

-   Explicitně zvolí akci, která zastaví registraci.
-   Zavře Portál společnosti v průběhu registrace.
-   Stráví více než 30 minut mezi částmi registrace.

Pokud uživatel zvolí registraci zastavit a znovu spustit několikrát, zobrazí jako více neúplné registrace i více pokusů. Pokud uživatel počká 30 minut mezi obrazovkami různých registrace, bude považován za více neúplné registrace.

## <a name="what-does-the-report-show"></a>Co tato sestava zobrazuje?

Sestavy obsahují data pro iOS a androidem.

Sestavy zobrazují data za poslední dva týdny, ale můžete nastavit filtr sestavy tak, aby zobrazovala libovolné období do 30 dnů v minulosti.

Pomocí **filtru** můžete zvolit rozsah kalendářních dat, operační systém a část registrace.

### <a name="number-and-percentage-tiles"></a>Dlaždice pro počet a procentuální hodnotu

V horní části stránky sestavy zobrazí se počet a procento neúplné registrací ve vztahu k všechny registrace.

-   Registrace iniciovaná: Počet registrací se pokusili.
-   Neúplné registrace: Počet pokusů o registrací nemělo za následek plně zaregistrované a vyhovující zařízení.
-   Neúplné rychlost: Procento pokusy o registraci, které byly opuštěny (opuštěných registrace / iniciované registrací).

### <a name="line-graph"></a>Spojnicový graf

Spojnicový graf zobrazuje denní neúplné registrace pro každý oddíl čtyři základní registrace:

-   Kontrolní seznam instalace
-   Obrazovky platformy
-   Podmínky použití
-   Dodržování předpisů / aktivace

### <a name="user-abandonment-actions"></a>Akce uživatelů, po kterých došlo k opuštění registrace

Seznam akcí uživatele, které jsou způsobilé jako dotazování neúplný zápis v následujících tabulkách. Příklady obrazovek registrace můžete vidět ve videích s registrací zařízení s [iOSem](https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment) a [Androidem](https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment). 


#### <a name="setup-checklist-section"></a>Část Kontrolní seznam instalace

| Název akce | Obrazovka nebo tok | Platforma | Akce |
| ---- |---- |---- |---- |
| EnrollmentWrapUp | Výzva k otevření stránky v Portálu společnosti | iOS/Android | **Zrušit** |
| EnrollmentWrapUp | Obrazovka registrace zařízení až do dokončení **načítání firemních prostředků** | iOS/Android | Trvalo > 30 minut |
| DeviceCategory | Výběr kategorie zařízení (pokud ji správce nakonfiguroval) až do kliknutí na **Hotovo** | iOS/Android | Trvalo > 30 minut |
| PreEnrollmentWizard | Obrazovka nastavení přístupu, pokud byla registrace zahájena, ale vrátila se k nastavení přístupu | iOS/Android| **Postpone** |
| PreEnrollmentWizard | Obrazovka nastavení přístupu až do kliknutí na **Další** na obrazovce **Co dál** | iOS/Android | Trvalo > 30 minut |

#### <a name="platform-screens-section"></a>Část Obrazovky platformy

| Název akce | Obrazovka nebo tok | Platforma | Akce |
| ---- |---- |---- |---- |
| iOSProfileLaunch | Výzva k zobrazení konfiguračního profilu | iOS | **Ignorovat** |
| iOSProfileLaunch | Obrazovka instalace profilu | iOS | **Zrušit** |
| iOSProfileLaunch | Výzva k určení důvěryhodnosti zdroje profilu pro registraci zařízení | iOS | **Zrušit** |
| iOSProfileLaunch | Obrazovka instalace profilu až do dokončení instalace profilu | iOS | Trvalo > 30 minut |
| AndroidPermissions | Obrazovka aktivace správce zařízení | Android | **Zrušit** |
| AndroidPermissions | Od výzvy ke schválení uskutečňování telefonních hovorů a jejich správy až do **aktivace** správce zařízení | Android | Trvalo > 30 minut |
| KnoxActivation | Aktivace agenta KLMS (pouze Samsung) | Android| **Zrušit** |
| KnoxActivation | Aktivace agenta KLMS až do výběru možnosti **Potvrdit** | Android | Trvalo > 30 minut|

#### <a name="terms-of-use-section"></a>Část Podmínky použití

| Název akce | Obrazovka nebo tok | Platforma | Akce |
| ---- |---- |---- |---- |
| TermsofUse | Podmínky použití (pokud je správce nakonfiguroval) | iOS/Android | **Odmítnout vše** |
| TermsofUse | Podmínky použití až do výběru možnosti **Přijmout vše** | iOS/Android | Trvalo > 30 minut |

#### <a name="complianceactivation-section"></a>Část Dodržování předpisů / aktivace

| Název akce | Obrazovka nebo tok | Platforma | Akce |
| ---- |---- |---- |---- |
| Dodržování předpisů | Dodržování předpisů zařízením (pokud je správce nakonfiguroval) se v nastavení přístupu po registraci zobrazuje jinak než zeleně.| iOS/Android | **Postpone** |
| Dodržování předpisů | Dodržování předpisů zařízením se zobrazuje jinak než zeleně až do aktualizace, po které se zobrazuje zeleně. | iOS/Android | Trvalo > 30 minut |
| Aktivace | Aktivace registrace (pokud ji správce nakonfiguroval) se v nastavení přístupu zobrazuje jinak než zeleně. | iOS/Android | **Postpone** |
| Dodržování předpisů | Aktivace zařízení se zobrazuje jinak než zeleně až do aktualizace, po které se zobrazuje zeleně. | iOS/Android | Trvalo > 30 minut |

## <a name="next-steps"></a>Další postup

Po kontrole na neúplný zápis sazby, můžete zkontrolovat [možnosti registrace](enrollment-options.md) zobrazíte, pokud jste provedli změny ke zlepšení registrace.
