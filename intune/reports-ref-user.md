---
title: Uživatel – Datový sklad Intune
titlesuffix: Microsoft Intune
description: Referenční téma pro kategorii Uživatel v kolekcích entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/14/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9a8fa64b0458321ef9b0db39edc354a24099f03d
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57388729"
---
# <a name="reference-for-user-entity"></a>Referenční informace pro entitu uživatele

Kategorie **Uživatel** obsahuje entitu **Uživatel**, která definuje vlastnosti uživatele datového modelu.

## <a name="user"></a>Uživatel

Entita **User** obsahuje seznam všech uživatelů Azure Active Directory (Azure AD) s přiřazenými licencemi ve vaší společnosti.

Kolekce entit **Uživatel** obsahuje uživatelská data. Tyto záznamy zahrnují stavy uživatelů za dobu shromažďování dat i v případě odebrání uživatele. Uživatel například může být přidaný do Intune a potom v průběhu posledního měsíce dojde k jeho odebrání. Přestože tento uživatel není v době vytvoření sestavy přítomen, existují data o uživateli a stavu z předchozího měsíce. Můžete vytvořit sestavu, která ukazuje trvání historické přítomnosti uživatele ve vašich datech.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| UserKey |Jedinečný identifikátor uživatele v datovém skladu – náhradní klíč |123 |
| UserId |Jedinečný identifikátor uživatele – podobá se vlastnosti UserKey, jedná se ale o přirozený klíč. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |E-mailová adresa uživatele |John@constoso.com |
| HLAVNÍ NÁZEV UŽIVATELE | Hlavní název uživatele (UPN) uživatele | John@constoso.com |
| displayName |Zobrazované jméno uživatele |Honza |
| IntuneLicensed |Určuje, jestli tento uživatel má licenci na službu Intune. |True nebo False |
| IsDeleted | Určuje, zda všem uživatelským licencím vypršela platnost a zda byl proto uživatel odebrán z Intune. Pro jeden záznam se tento příznak nemění. Místo toho se vytvoří nový záznam pro nový stav uživatele. |True nebo False |
| StartDateInclusiveUTC |Pokud IsDeleted = FALSE, použije se DateTime ve standardu UTC, kdy byla uživateli přiřazena licence a začal existovat v Intune. Pokud IsDeleted = TRUE, použije se DateTime ve standardu UTC, kdy uživateli vypršela platnost licencí a byl odebrán z Intune. |23.11.2016 12:00:00 |
| EndDateExclusiveUTC |Pokud IsDeleted = FALSE, použije se DateTime ve standardu UTC, kdy uživateli vypršela platnost licence a byl odebrán z Intune. Platnost licence vypršela během předchozího dne. Pokud IsDeleted = TRUE, použije se DateTime ve standardu UTC, kdy uživatel znovu získal novou licenci a byl znovu vytvořen v Intune.  |23.11.2016 12:00:00 |
| IsCurrent |Určuje, zda tento záznam představuje nejnovější stav uživatele. Může existovat více záznamů pro jednoho uživatele, ale pouze jeden z nich představuje aktuální stav.  |True nebo False |
| RowLastModifiedDateTimeUTC |Datum a čas ve standardu UTC, kdy se tento záznam v datovém skladu naposledy změnil  |23.11.2016 12:00:00 |

## <a name="next-steps"></a>Další postup
 - Kolekci entit **Aktuální uživatel** můžete použít k omezení dat uživatelů na uživatele, kteří jsou aktuálně aktivní. Další informace najdete v tématu [Referenční informace pro entitu aktuálního uživatele](reports-ref-current-user.md).
 - Další informace o tom, jak datový sklad sleduje dobu života uživatele v Intune, získáte v článku [Znázornění životnosti uživatele v datovém skladu Microsoft Intune](reports-ref-user-timeline.md).
