---
title: Aktuální uživatel – Datový sklad Intune
titlesuffix: Microsoft Intune
description: Referenční téma pro kategorii Uživatel v kolekcích entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: da149ea2870880a35352e9d37a91c5c39f7a7438
ms.sourcegitcommit: bea4a81d262607c6e9dd1e26f5cd1a2faf7d051b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/14/2018
ms.locfileid: "45602074"
---
# <a name="reference-for-current-user-entity"></a>Referenční informace o entitě aktuálního uživatele

Kategorie **Aktuální uživatel** obsahuje vlastnosti uživatele v datovém modelu. Kolekce entit **Aktuální uživatel** se omezuje na aktuálně aktivní uživatele. Entita obsahuje všechny uživatele Azure Active Directory, kteří mají aktuálně přiřazenou licenci. Licence může být licence Intune, hybridní licence nebo licence Microsoft Office 365. Odebraný uživatel v kolekci aktuálních uživatelů zastoupen nebude. Kolekci, která obsahuje historii změn ve stavu uživatele, najdete v tématu [Referenční informace pro entitu uživatele](reports-ref-user.md).


## <a name="current-user"></a>Aktuální uživatel

Entita **Aktuální uživatel** obsahuje seznam všech uživatelů Azure Active Directory (Azure AD), kteří mají v podniku přiřazené licence.

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
 - Kolekci entit **Uživatelé** můžete použít k rozšíření uživatelských dat o uživatele, kteří momentálně nejsou aktivní. Další informace najdete v tématu [Referenční informace pro entitu uživatele](reports-ref-user.md).
 - Další informace o tom, jak datový sklad sleduje dobu života uživatele v Intune, získáte v článku věnovaném [reprezentaci doby života uživatele v datovém skladu Intune](reports-ref-user-timeline.md).
