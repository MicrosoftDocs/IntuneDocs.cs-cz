---
title: Jak funguje typický cyklus migrace Intune
titlesuffix: Microsoft Intune
description: Tento článek vysvětluje, jak funguje cyklus migrace Microsoft Intune, a uvádí příklady aplikace cyklů migrace.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 238ea903353b75a69d1c2fe2a836f9e89992d2d7
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/16/2018
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
