---
title: Aktuální uživatel – Datový sklad Intune
titlesuffix: Microsoft Intune
description: Referenční téma pro kategorii aktuální uživatel pro kolekce entit v rozhraní API datového skladu Intune.
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b9fdd1891f8a0e893d61ac3a0b40dac5a01f602c
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55851334"
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
| HLAVNÍ NÁZEV UŽIVATELE | Hlavní název uživatele (UPN) uživatele | John@constoso.com |
| displayName |Zobrazované jméno uživatele |Honza |
| IntuneLicensed |Určuje, jestli tento uživatel má licenci na službu Intune. |True nebo False |
| StartDateInclusiveUTC |Datum a čas ve standardu UTC, kdy se tento uživatel v datovém skladu vytvořil |23.11.2016 12:00:00 |
| RowLastModifiedDateTimeUTC |Datum a čas ve standardu UTC, kdy se tento uživatel v datovém skladu naposledy změnil |23.11.2016 12:00:00 |

## <a name="next-steps"></a>Další postup
 - Kolekci entit **Uživatelé** můžete použít k rozšíření uživatelských dat o uživatele, kteří momentálně nejsou aktivní. Další informace najdete v tématu [Referenční informace pro entitu uživatele](reports-ref-user.md).
 - Další informace o tom, jak datový sklad sleduje dobu života uživatele v Intune, získáte v článku věnovaném [reprezentaci doby života uživatele v datovém skladu Intune](reports-ref-user-timeline.md).
