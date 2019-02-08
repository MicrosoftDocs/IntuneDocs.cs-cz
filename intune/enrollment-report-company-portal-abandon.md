---
title: Opuštění registrace na Portálu společnosti v Intune
titlesuffix: Microsoft Intune
description: Přečtěte si informace o sestavě opuštění registrace na Portálu společnosti.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 85a03718185de939612f5431a993f9f34c3048ba
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55840650"
---
# <a name="company-portal-abandonment-report"></a>Sestava opuštění registrace na Portálu společnosti

Tato sestava informuje, na jakém místě uživatelé opouštějí proces registrace na Portálu společnosti.

Když chcete tuto sestavu zobrazit, zvolte **Intune** > **Registrace zařízení** > **Opuštění Portálu společnosti**.

Na základě těchto informací o opuštění registrace můžete vaše dokumenty týkající se onboardingu aktualizovat tak, aby uživatelům pomáhaly registraci dokončit. Pokud například končí mnoho uživatelů u podmínek použití, můžete tuto oblast prozkoumat a upravit, aby byla pro uživatele intuitivnější.

## <a name="what-is-abandonment"></a>Co je opuštění registrace?

K opuštění registrace dojde, když uživatel provede některou z následujících akcí:

-   Explicitně zvolí akci, která zastaví registraci.
-   Zavře Portál společnosti v průběhu registrace.
-   Stráví více než 30 minut mezi částmi registrace.

Pokud uživatel několikrát zastaví registraci a znovu ji spustí, považuje se to za několik pokusů o registraci a několik opuštění registrace. Pokud uživatel čeká 30 minut na různých obrazovkách registrace, považuje se to za několik opuštění registrace.

## <a name="what-does-the-report-show"></a>Co tato sestava zobrazuje?

Sestavy registrace obsahují data pro zařízení s iOSem a Androidem.

Sestavy zobrazují data za poslední dva týdny, ale můžete nastavit filtr sestavy tak, aby zobrazovala libovolné období do 30 dnů v minulosti.

Pomocí **filtru** můžete zvolit rozsah kalendářních dat, operační systém a část registrace.

### <a name="number-and-percentage-tiles"></a>Dlaždice pro počet a procentuální hodnotu

V horní části sestavy se zobrazuje počet opuštění registrace a procentuální hodnota vzhledem k celkovému počtu registrací.

-   Registrace iniciovaná: Počet registrací se pokusili.
-   Opuštěné registrace: Počet pokusů o registrací nemělo za následek plně zaregistrované a vyhovující zařízení.
-   Zřeknutí rychlost: Procento pokusy o registraci, které byly opuštěny (opuštěných registrace / iniciované registrací).

### <a name="line-graph"></a>Spojnicový graf

Spojnicový graf zobrazuje denní počet opuštění v každé ze čtyř základních částí registrace:

-   Kontrolní seznam instalace
-   Obrazovky platformy
-   Podmínky použití
-   Dodržování předpisů / aktivace

### <a name="user-abandonment-actions"></a>Akce uživatelů, po kterých došlo k opuštění registrace

Následující tabulky zobrazují seznam akcí uživatelů, které způsobily opuštění registrace. Příklady obrazovek registrace můžete vidět ve videích s registrací zařízení s [iOSem](https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment) a [Androidem](https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment). 


#### <a name="setup-checklist-section"></a>Část Kontrolní seznam instalace

| Název opuštění registrace | Obrazovka nebo tok | Platforma | Akce |
| ---- |---- |---- |---- |
| EnrollmentWrapUp | Výzva k otevření stránky v Portálu společnosti | iOS/Android | **Zrušit** |
| EnrollmentWrapUp | Obrazovka registrace zařízení až do dokončení **načítání firemních prostředků** | iOS/Android | Trvalo > 30 minut |
| DeviceCategory | Výběr kategorie zařízení (pokud ji správce nakonfiguroval) až do kliknutí na **Hotovo** | iOS/Android | Trvalo > 30 minut |
| PreEnrollmentWizard | Obrazovka nastavení přístupu, pokud byla registrace zahájena, ale vrátila se k nastavení přístupu | iOS/Android| **Postpone** |
| PreEnrollmentWizard | Obrazovka nastavení přístupu až do kliknutí na **Další** na obrazovce **Co dál** | iOS/Android | Trvalo > 30 minut |

#### <a name="platform-screens-section"></a>Část Obrazovky platformy

| Název opuštění registrace | Obrazovka nebo tok | Platforma | Akce |
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

| Název opuštění registrace | Obrazovka nebo tok | Platforma | Akce |
| ---- |---- |---- |---- |
| TermsofUse | Podmínky použití (pokud je správce nakonfiguroval) | iOS/Android | **Odmítnout vše** |
| TermsofUse | Podmínky použití až do výběru možnosti **Přijmout vše** | iOS/Android | Trvalo > 30 minut |

#### <a name="complianceactivation-section"></a>Část Dodržování předpisů / aktivace

| Název opuštění registrace | Obrazovka nebo tok | Platforma | Akce |
| ---- |---- |---- |---- |
| Dodržování předpisů | Dodržování předpisů zařízením (pokud je správce nakonfiguroval) se v nastavení přístupu po registraci zobrazuje jinak než zeleně.| iOS/Android | **Postpone** |
| Dodržování předpisů | Dodržování předpisů zařízením se zobrazuje jinak než zeleně až do aktualizace, po které se zobrazuje zeleně. | iOS/Android | Trvalo > 30 minut |
| Aktivace | Aktivace registrace (pokud ji správce nakonfiguroval) se v nastavení přístupu zobrazuje jinak než zeleně. | iOS/Android | **Postpone** |
| Dodržování předpisů | Aktivace zařízení se zobrazuje jinak než zeleně až do aktualizace, po které se zobrazuje zeleně. | iOS/Android | Trvalo > 30 minut |

## <a name="next-steps"></a>Další postup

Po kontrole vašich četností opuštění můžete prozkoumat [možnosti registrace](enrollment-options.md), abyste zjistili, jestli lze provést nějaké změny, které proces registrace vylepší.
