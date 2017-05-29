---
title: "Jak funguje typický cyklus migrace Intune | Dokumentace Microsoftu"
description: "Tento článek vysvětluje, jak funguje cyklus migrace Intune, a uvádí příklady aplikace cyklů migrace zákazníky."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7130d09d7340aba94f3f9ac72743a281e0aa45ca
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="phase-2-typical-migration-cycle"></a>Fáze 2: Typický cyklus migrace

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Je běžné, že organizace zahájí migraci do Intune malou pilotní skupinou uživatelů z IT oddělení. Dále je vhodné, aby organizace zohlednila faktory, jako je připravenost uživatelů na změnu, počet uživatelů, komplexnost prostředků a lokalit, požadavky a obchodní rizika. To vše vám pomůže vytvořit optimální časový plán migrace.

Tady je příklad naplánování cílových skupin:

  | **Cílové skupiny migrace** | **Časové období 1** | **Časové období 2** | **Časové období 3** | **Časové období 4** | **...**
|:---:|:---:|:---:|:---:|:---:|:---:|
| Omezená pilotní skupina IT uživatelů (50 uživatelů) | Oznámení plánu | Pokyny k registraci | Stanovení termínu | Vynucení podmíněného přístupu |  |                                                        
| Rozšíření pilotní IT skupiny (200 uživatelů) |  | Oznámení plánu | Pokyny k registraci | Stanovení termínu | Vynucení podmíněného přístupu | 
| Migrace fáze 1 – technicky zkušenější uživatelé (2000 uživatelů) |  |  | Oznámení plánu | Pokyny k registraci | Stanovení termínu | 
| Migrace fáze 2 – východ USA |  |  |  | Oznámení plánu | Pokyny k registraci | 
| Všechny oblasti |  |  |  |  | Oznámení plánu | 

## <a name="customer-migration-case-study"></a>Případová studie migrace zákazníků

### <a name="adatum-corporation"></a>Adatum Corporation

- Podívejte se, [jak společnost Adatum Corporation absolvovala proces migrace od jiného poskytovatele MDM k Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).

## <a name="monitoring-migration"></a>Monitorování migrace

Microsoft Intune nabízí několik způsobů monitorování migrace:

1.  Zobrazení skupin uživatelů Intune

2.  Sada předdefinovaných sestav

3.  Výstrahy v konzole

Je vhodné sledovat, kolik uživatelů si po každé fázi zaregistrovalo zařízení, abyste mohli:

-   Zhodnotit účinnost vašeho plánu komunikace.

-   Zhodnotit dopad vynucení podmíněného přístupu.

Informace o [způsobech monitorování migrace do Intune](/intune-classic/deploy-use/understand-microsoft-intune-operations-by-using-reports)

## <a name="post-migration"></a>Po migraci

Po migraci do Intune je potřeba ukončit spolupráci s předchozím poskytovatelem MDM nebo se odhlásit od jeho služby. Dále je nutné podle pokynů poskytovatele MDM odebrat nepotřebné požadavky na infrastrukturu.

