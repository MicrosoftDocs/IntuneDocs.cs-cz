---
title: "Určení cílových skupin a časových rámců při zavádění Intune | Dokumentace Microsoftu"
description: "Tento článek vám pomůže určit cílové skupiny a časové rámce při cloudové implementaci Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a63f78f-a7e7-4f44-9288-16b28d5d58ca
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2a970badf5ac18a05115a72dc267ee455ba4628d
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="develop-an-intune-rollout-plan"></a>Příprava plánu zavedení Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

V této části určíte organizační skupiny, kterým budete Intune zavádět, časový rámec zavedení každé skupiny a použité přístupy k registraci.

## <a name="determine-intune-rollout-targeted-groups-and-timeframes"></a>Určení cílových skupin a časových rámců při zavádění Intune

Napřed je důležité určit skupiny, kterým budete Intune zavádět. Cílové skupiny jsme probírali v předchozí části tohoto průvodce o identifikaci scénářů použití Intune.

Teď je potřeba určit časový rámec zavedení Intune pro každou skupinu. Obvykle o tom členové implementačního týmu Intune diskutují s cílovými skupinami. Z této diskuse vyplyne nejvhodnější časový rámec zavedení pro každou skupinu.

Při zjišťování časového rámce zavedení může implementační tým Intune jednat o takových věcech, jako je například ochota skupiny ke změně, počet uživatelů a zařízení, typy platforem zařízení, požadavky, zeměpisná poloha a obchodní riziko.

Organizace se většinou rozhodnou, že zahájí zavedení Intune úvodním pilotním projektem určeným pro malou skupinu uživatelů v oddělení IT. Potom pilotní projekt rozšíří na širší skupinu pracovníků IT a zapojí další organizační skupiny. Po úspěšném pilotním nasazení jsou organizace připravené zahájit ostrý provoz i ve zbývajících organizačních skupinách. Tady jsou některé příklady jednotlivých skupin a fází spuštění:

-   **Pilotní nasazení:** První fáze zavedení řešení u pilotních uživatelů. Pilotní uživatelé musí chápat, že jsou prvními uživateli nového řešení, a proto by měli být ochotni poskytnout zpětnou vazbu, která pomůže zlepšit konfiguraci, dokumentaci, oznámení a usnadní cestu všem dalším uživatelům v pozdějších zaváděcích fázích. Nedoporučuje se, aby to byli členové vedení ani důležití uživatelé.

-   **Oddělení:** Zaváděcí fáze se může účastnit každé oddělení. V tomto scénáři se zaměříme na celé oddělení najednou. U tohoto typu zavádění se v každé fázi pravděpodobně bude používat mobilní zařízení stejným způsobem a bude se přistupovat ke stejným aplikacím. Uživatelé budou mít s největší pravděpodobností stejné typy zásad.

-   **Zeměpisná oblast:** U tohoto typu se řešení nasadí u všech uživatelů v určité zeměpisné oblasti. Může to být stejný kontinent, země, oblast nebo stejná firemní budova. Tento typ postupného nasazení umožňuje se zaměřit na uživatele v určitém místě. Takový přístup je [opatrnější](#user-assisted-enrollment), protože počet míst, kde se současně nasazuje Intune, je menší. Na jednom místě budou pravděpodobně různá oddělení nebo různé způsoby použití, a proto mohou být současně nasazovány různé způsoby použití.

-   **Platforma:** Tento typ nasazení spočívá v současném nasazení podobných platforem. Příkladem mohou být všechna zařízení s iOSem v prvním měsíci, po kterých budou následovat zařízení s Androidem a po nich zařízení s Windows. Tento typ postupného nasazení usnadňuje podporu helpdesku. Podpora helpdesku totiž nasazuje vždy jenom jednu platformu.

V následujícím příkladu je plán zavedení Intune, který obsahuje cílové skupiny a časové rámce:

| **Zaváděcí fáze** | **Červenec** | **Srpen** | **Září** | **Říjen** |
|:---:|:---:|:---:|:---:|:---:|
| Omezené pilotní nasazení | IT (50 uživatelů) |  |  |  |                                                         
| Rozšířené pilotní nasazení | IT (200 uživatelů), vedení IT (10 uživatelů) |  |  |  |                                                         
| 1. fáze nasazení v ostrém provozu |  | Prodej a marketing (2000 uživatelů) |  |  |
| 2. fáze nasazení v ostrém provozu |  |  | Maloobchod (1000 uživatelů) |  |
| 3. fáze nasazení v ostrém provozu |  |  |  | Personalistika (50 uživatelů), finance (40 uživatelů), vedení (30 uživatelů) |

## <a name="determine-the-intune-enrollment-approach"></a>Vymezení přístupu k registraci v Intune

Když jste určili cílové skupiny a časové rámce zavedení Intune, zvolte pro každou skupinu nejvhodnější přístup k registraci do této služby. Existují různé přístupy k registraci, které mohou organizace při zavádění Intune použít. K nejčastějším přístupům k registraci patří samoobslužná služba pro uživatele, registrace s asistencí pro uživatele a technický veletrh IT.

### <a name="user-self-service"></a>Samoobslužná služba pro uživatele

U tohoto přístupu zodpovídá za registraci svého zařízení uživatel. Ten se obvykle řídí pokyny, které dostane od týmu IT v organizaci. Tento přístup se nejčastěji používá v organizacích, protože nabízí větší škálovatelnost než registrace s asistencí uživatele.

### <a name="user-assisted-enrollment"></a>Registrace s asistencí pro uživatele

Tento přístup se považuje za šetrnější. Člen týmu IT pomáhá uživateli při registraci, a to buď osobně, nebo přes Skype. Tento přístup se často používá u vedoucích pracovníků a jiných skupin, které mohou při registraci potřebovat větší pomoc.

### <a name="it-tech-fair"></a>Technický veletrh IT

Další možností, jak registrovat uživatele do Intune, je uspořádat technický veletrh IT. Na tuto událost připraví skupina IT registrační stánek Intune, kde mohou uživatelé získat informace o registraci Intune, mohou se ptát a získat pomoc s registrací. Tento způsob může být výhodný pro skupinu IT i pro uživatele, hlavně v počátečních fázích zavádění Intune.

Tady je příklad plánu zavedení Intune s cílovými skupinami, časovými rámci a přístupy k registraci:

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
| Šetrný způsob |  |  |  | Vedení |

## <a name="next-section"></a>Další část

V další části najdete pokyny k [přípravě komunikačního plánu pro zavedení Intune](section-5-develop-a-rollout-communication-plan.md).

