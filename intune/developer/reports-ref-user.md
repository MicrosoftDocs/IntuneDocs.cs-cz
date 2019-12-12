---
title: Uživatel – Datový sklad Intune
titleSuffix: Microsoft Intune
description: Referenční téma pro kategorii Uživatel v kolekcích entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 996e28f9dceff88637c93e667597e3364215b965
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/05/2019
ms.locfileid: "72505630"
---
# <a name="reference-for-user-entity"></a>Referenční informace pro entitu uživatele

Kategorie **Uživatelé** obsahuje entitu **uživatele** , která definuje vlastnosti uživatele v datovém modelu.

## <a name="users"></a>uživatelé

Entita **user** obsahuje seznam všech uživatelů Azure Active Directory (Azure AD) s přiřazenými licencemi ve vaší společnosti.

Kolekce entit **user** obsahuje uživatelská data. Tyto záznamy zahrnují stavy uživatelů za dobu shromažďování dat i v případě odebrání uživatele. Uživatel například může být přidaný do Intune a potom v průběhu posledního měsíce dojde k jeho odebrání. Přestože tento uživatel není v době vytvoření sestavy přítomný, data o něm a jeho stavu existují z předchozího měsíce. Můžete vytvořit sestavu, která ukazuje trvání historické přítomnosti uživatele ve vašich datech.

|          Vlastnost          |                                                                                                           Description                                                                                                          |                Příklad               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| userKey                    | Jedinečný identifikátor uživatele v datovém skladu – náhradní klíč                                                                                                                                                         | 123                                  |
| userId                     | Jedinečný identifikátor uživatele – podobá se vlastnosti UserKey, jedná se ale o přirozený klíč.                                                                                                                                                    | b66bc706-ffff-7437-0340-032819502773 |
| userEmail                  | E-mailová adresa uživatele                                                                                                                                                                                                     | John@constoso.com                    |
| userPrincipalName                        | Hlavní název uživatele (UPN) uživatele                                                                                                                                                                                               | John@constoso.com                    |
| displayName                | Zobrazované jméno uživatele                                                                                                                                                                                                      | Honza                                 |
| intuneLicensed             | Určuje, jestli tento uživatel má licenci na službu Intune.                                                                                                                                                                              | True nebo False                           |
| IsDeleted                  | Určuje, zda všem uživatelským licencím vypršela platnost a zda byl proto uživatel odebrán z Intune. Pro jeden záznam se tento příznak nemění. Místo toho se vytvoří nový záznam pro nový stav uživatele. | True nebo False                           |
| RowLastModifiedDateTimeUTC | Datum a čas ve standardu UTC, kdy se tento záznam v datovém skladu naposledy změnil                                                                                                                                                 | 23. 11. 2016 0:00                      |


## <a name="next-steps"></a>Další kroky
- Kolekci entit **Aktuální uživatel** můžete použít k omezení dat uživatelů na uživatele, kteří jsou aktuálně aktivní. Další informace najdete v tématu [Referenční informace pro entitu aktuálního uživatele](../reports-ref-current-user.md).
- Další informace o tom, jak datový sklad sleduje dobu života uživatele v Intune, získáte v článku [Znázornění životnosti uživatele v datovém skladu Microsoft Intune](reports-ref-user-timeline.md).
