---
title: Určení cílových skupin a časových rámců nasazení
titlesuffix: Microsoft Intune
description: Tento článek vám pomůže rozhodnout, jakým skupinám budete nasazovat Microsoft Intune, a stanovit časové rámce tohoto nasazení.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3a63f78f-a7e7-4f44-9288-16b28d5d58ca
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4eb30a070fd12538750888b92e940480afb677ea
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55846260"
---
# <a name="develop-a-rollout-plan"></a>Vývoj plánu nasazení

V plánu nasazení identifikujete organizační skupiny, kterým chcete Intune zavést, časový rámec nasazení u každé skupiny a použité přístupy při registraci.

## <a name="targeted-groups-and-timeframes"></a>Cílové skupiny a časové rámce

Nejprve si prohlédněte skupiny, kterým chcete zavést Intune a které jste zjistili ve [scénářích použití](planning-guide-scenarios.md).

V dalším kroku určete pro každou cílovou skupinu časový rámec. Tento úkol obvykle vyžaduje diskuzi implementačního týmu Intune s cílovými skupinami. Z této diskuze vyplyne nejvhodnější časový rámec zavedení pro každou skupinu. Diskutované body:
* Ochota skupiny ke změně
* Počet uživatelů a zařízení
* Typy platforem zařízení
* Požadavky
* Zeměpisná poloha
* Obchodní riziko

## <a name="rollout-phases"></a>Fáze uvedení
Organizace se většinou rozhodnou, že zahájí zavedení Intune úvodním pilotním projektem určeným pro malou skupinu uživatelů v oddělení IT. Pilotní projekt se dá rozšířit na širší skupinu uživatelů IT a mohou se ho účastnit i další organizační skupiny.

### <a name="pilot"></a>Pilotní nasazení
V první fázi by řešení mělo být nasazeno u pilotních uživatelů. Těm je potřeba vysvětlit, že jsou první, kteří nové řešení používají. Proto musí být ochotni poskytnout zpětnou vazbu, která pomůže zlepšit konfiguraci, dokumentaci, oznámení a usnadní cestu všem dalším uživatelům v pozdějších fázích implementace. Nedoporučuje se, aby to byli členové vedení ani důležití uživatelé.

Pilotní projekt je vhodnou příležitostí k otestování [problémů](planning-guide-deployment-goals.md) a zpřesnění dříve shromážděných [požadavků](planning-guide-requirements.md).

Nezapomeňte zahrnout plán [komunikace](planning-guide-communication-plan.md), [podpory](planning-guide-support-plan.md), [testování a ověřování](planning-guide-test-validation.md), abyste případné problémy dokázali vyřešit, dokud je dopad na uživatele ještě malý.

### <a name="production-rollout"></a>Nasazení v ostrém provozu
Po úspěšném pilotním projektu jste připraveni spustit nasazení v plném provozu, kdy se zapojí i zbývající organizační skupiny. Tady je několik příkladů různých zaváděcích skupin a fází:

-   **Oddělení** <br/>Fáze nasazení se může účastnit každé oddělení. Zaměříte se vždy jen na jedno oddělení. Při tomto typu nasazení je větší pravděpodobnost, že uživatelé budou v každém oddělení používat mobilní zařízení stejným způsobem a budou přistupovat ke stejným aplikacím. Uživatelé také budou mít stejné typy zásad.

-   **Zeměpisná oblast** <br/>Při tomto přístupu se řešení nasadí u všech uživatelů v určité zeměpisné oblasti. Může to být stejný kontinent, země, oblast nebo stejná firemní budova. Tento typ postupného nasazení umožňuje zaměřit se na uživatele, kteří jsou na určitém místě. Takový přístup je [šetrnější](#user-assisted-enrollment), protože počet míst, kde se Intune současně nasazuje, je menší. Na jednom místě budou pravděpodobně různá oddělení nebo různé způsoby použití, a proto mohou být současně nasazovány různé způsoby použití.

-   **Platforma** <br/>Tento typ nasazení spočívá v současném nasazení podobných platforem. Příkladem mohou být všechna zařízení s iOSem v prvním měsíci, po kterých budou následovat zařízení s Androidem a po nich zařízení s Windows. Tento typ postupného nasazení zjednodušuje podporu helpdesku, protože se podpora týká vždy jen jedné platformy.

V následujícím příkladu je plán zavedení Intune, který obsahuje cílové skupiny a časové rámce:

| **Zaváděcí fáze** | **Červenec** | **Srpen** | **Září** | **Říjen** |
|:---:|:---:|:---:|:---:|:---:|
| Omezené pilotní nasazení | IT (50 uživatelů) |  |  |  |                                                         
| Rozšířené pilotní nasazení | IT (200 uživatelů), vedení IT (10 uživatelů) |  |  |  |                                                         
| 1. fáze nasazení v ostrém provozu |  | Prodej a marketing (2000 uživatelů) |  |  |
| 2. fáze nasazení v ostrém provozu |  |  | Maloobchod (1000 uživatelů) |  |
| 3. fáze nasazení v ostrém provozu |  |  |  | Personalistika (50 uživatelů), finance (40 uživatelů), vedení (30 uživatelů) |

K zadání fází nasazení pro svou organizaci si můžete [stáhnout šablonu předchozí tabulky](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).
## <a name="match-rollout-groups-to-enrollment-approaches"></a>Sladění skupin a přístupů při nasazení

Když jste určili cílové skupiny a časové rámce nasazení Intune, zvolte pro každou skupinu nejvhodnější přístup k registraci do této služby. Můžete použít různé přístupy k registraci:
* Samoobslužná služba pro uživatele
* Registrace s asistencí pro uživatele
* Technický veletrh IT

### <a name="user-self-service"></a>Samoobslužná služba pro uživatele

V tomto případě za registraci zařízení odpovídá uživatel. Ten se obvykle řídí pokyny, které dostane od týmu IT v organizaci. Tento přístup se nejčastěji používá v organizacích, protože nabízí větší škálovatelnost než asistovaná registrace uživatele.

### <a name="user-assisted-enrollment"></a>Asistovaná registrace

Tento přístup se považuje za šetrnější. Uživateli s registrací pomáhá člen týmu IT. Pomoc může být osobní nebo přes Skype. Tento přístup se často používá u vedoucích pracovníků a jiných skupin, které vyžadují při registraci větší pomoc.

### <a name="it-tech-fair"></a>Technický veletrh IT

Další možností, jak registrovat uživatele do Intune, je uspořádat technický veletrh IT. Na tuto událost připraví skupina IT registrační stánek Intune, kde mohou uživatelé získat informace o registraci do Intune, mohou se ptát a získat pomoc s registrací. Tento způsob může být – zejména v počátečních fázích zavádění Intune – výhodný jak pro skupinu IT, tak pro uživatele.

Tady je aktualizovaný příklad plánu nasazení Intune, který zahrnuje různé přístupy k registraci:

| **Zaváděcí fáze** | **Červenec** | **Srpen** | **Září** | **Říjen** |
|:---:|:---:|:---:|:---:|:---:|
| Omezené pilotní nasazení |  |  |  |  |                                                         
| Samoobslužný provoz | IT |  |  |  |
| Rozšířené pilotní nasazení |  |  |  |  |                                                         
| Samoobslužný provoz | IT |  |  |  |
| Šetrný způsob | Vedení IT |  |  |  |
| 1. fáze nasazení v ostrém provozu |  | Prodej, marketing |  |  |
| Samoobslužný provoz |  | Prodej a marketing |  |  |
| 2. fáze nasazení v ostrém provozu |  |  | Maloobchod |  |
| Samoobslužný provoz |  |  |  |  |
| 3. fáze nasazení v ostrém provozu |  |  | Maloobchod |  |
| Samoobslužný provoz |  |  |  | Personalistika, finance |
| Šetrný způsob |  |  |  | Členové vedení |

## <a name="next-steps"></a>Další postup

V další části najdete pokyny k [přípravě komunikačního plánu pro zavedení Intune](planning-guide-communication-plan.md).
