---
title: "Uživatel – datový sklad Intune | Dokumentace Microsoftu"
description: "Referenční téma pro kategorii Uživatel v kolekcích entit v rozhraní API datového skladu Intune"
keywords: "Datový sklad Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6f321a3a9ac09c004639a3db15df280fbdb5be3c
ms.sourcegitcommit: d26930f45ba9e6292a49bcb08defb5b3f14b704b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="reference-for-current-user-entity"></a>Referenční informace o entitě aktuálního uživatele

Kategorie **Aktuální uživatel** obsahuje vlastnosti uživatele a agenta v datovém modelu. Kolekce entit **Aktuální uživatel** se omezuje na aktuálně aktivní uživatele. Entita obsahuje všechny uživatele Azure Active Directory, kteří mají aktuálně přiřazenou licenci. Licence může být licence Intune, hybridní licence nebo licence Microsoft Office 365. Pokud se odebere uživatel, nebude možné ho po dobu shromažďování dat reprezentovat. Kolekci, která obsahuje historii změn ve stavu uživatele, najdete v tématu [Referenční informace pro entitu uživatele](reports-ref-user.md).


## <a name="user"></a>Uživatel

Entita **User** obsahuje seznam všech uživatelů Azure Active Directory (Azure AD) s přiřazenými licencemi ve vaší společnosti.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| UserKey |Jedinečný identifikátor uživatele v datovém skladu – náhradní klíč |123 |
| UserId |Jedinečný identifikátor uživatele – podobá se vlastnosti UserKey, jedná se ale o přirozený klíč. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |E-mailová adresa uživatele |John@constoso.com |
| UPN | Hlavní název uživatele (UPN) uživatele | John@constoso.com |
| DisplayName |Zobrazované jméno uživatele |Honza |
| IntuneLicensed |Určuje, jestli tento uživatel má licenci na službu Intune. |True nebo False |
| StartDateInclusiveUTC |Datum a čas ve standardu UTC, kdy se tento uživatel v datovém skladu vytvořil |23.11.2016 12:00:00 |
| RowLastModifiedDateTimeUTC |Datum a čas ve standardu UTC, kdy se tento uživatel v datovém skladu naposledy změnil |23.11.2016 12:00:00 |

## <a name="next-steps"></a>Další kroky
 - Kolekci entit **Uživatelé** můžete použít k rozšíření dat uživatelů o uživatele, kteří aktuálně nejsou aktivní. Další informace najdete v tématu [Referenční informace pro entitu uživatele](reports-ref-user.md). 
 - Další informace o tom, jak datový sklad sleduje dobu života uživatele v Intune, získáte v článku věnovaném [reprezentaci doby života uživatele v datovém skladu Intune](reports-ref-user-timeline.md).