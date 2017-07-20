---
title: "Jak funguje typický cyklus migrace Intune"
description: "Tento článek vysvětluje, jak funguje cyklus migrace Intune, a uvádí příklady aplikace cyklů migrace."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 34e748e16449a99bad4c1f3e96c22dda6d8f3018
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2017
---
# <a name="typical-migration-cycle"></a>Typický cyklus migrace

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

Podívejte se, [jak společnost Adatum Corporation absolvovala proces migrace od jiného poskytovatele MDM k Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).

## <a name="monitoring-migration"></a>Monitorování migrace

Intune nabízí několik způsobů monitorování migrace:

* Zobrazení skupin uživatelů Intune

* Sada předdefinovaných sestav

* Výstrahy v konzole

Sledujte, kolik uživatelů si po každé fázi zaregistrovalo zařízení, abyste mohli:

-   Zhodnotit účinnost vašeho plánu komunikace.

-   Zhodnotit dopad vynucení podmíněného přístupu.


## <a name="post-migration"></a>Po migraci

Po migraci do Intune ukončete spolupráci s předchozím poskytovatelem služby pro správu mobilních zařízení (MDM) a zrušte odběr této služby. Dále je nutné podle pokynů poskytovatele MDM odebrat veškerou požadovanou infrastrukturu, která už není potřeba.
