---
title: Uživatel – datový sklad Intune
titleSuffix: Microsoft Intune
description: Téma reference pro kategorii uživatelů pro kolekce entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 444ed3ad156e81a15eec0b86bb670eb63b5b04e7
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71939928"
---
# <a name="reference-for-user-entity"></a>Referenční informace pro entitu uživatele

Kategorie **Uživatelé** obsahuje entitu **uživatele** , která definuje vlastnosti uživatele v datovém modelu.

## <a name="users"></a>uživatelé

Entita **uživatele** obsahuje seznam všech uživatelů Azure Active Directory (Azure AD) s přiřazenými licencemi ve vašem podniku.

Kolekce entit **uživatele** obsahuje uživatelská data. Tyto záznamy zahrnují stavy uživatele během období shromažďování dat, a to i v případě, že uživatel byl odebrán. Uživatel může například přidat do Intune a pak ho v průběhu posledního měsíce odebrat. I když tento uživatel není v době, kdy je sestava přítomen, k dispozici uživateli a stav v datech předchozí měsíc. Můžete vytvořit sestavu, která by zobrazila dobu trvání historické přítomnosti uživatele ve vašich datech.

|          Vlastnost          |                                                                                                           Popis                                                                                                          |                Příklad               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| Vlastnosti UserKey                    | Jedinečný identifikátor uživatele v datovém skladu – náhradní klíč                                                                                                                                                         | 123                                  |
| userId                     | Jedinečný identifikátor uživatele, který se podobá vlastnosti UserKey, ale je přirozený klíč.                                                                                                                                                    | b66bc706-FFFF-7437-0340-032819502773 |
| UserEmail                  | E-mailová adresa uživatele                                                                                                                                                                                                     | John@constoso.com                    |
| userPrincipalName                        | Hlavní uživatelské jméno uživatele                                                                                                                                                                                               | John@constoso.com                    |
| displayName                | Zobrazované jméno uživatele                                                                                                                                                                                                      | John                                 |
| IntuneLicensed             | Určuje, jestli je tento uživatel licencovaný v Intune, nebo ne.                                                                                                                                                                              | True nebo false                           |
| IsDeleted                  | Určuje, jestli vypršela platnost všech licencí uživatele a jestli se uživatel z Intune odebral. U jednoho záznamu se tento příznak nemění. Místo toho se vytvoří nový záznam pro nový stav uživatele. | True nebo false                           |
| RowLastModifiedDateTimeUTC | Datum a čas ve standardu UTC, kdy se záznam v datovém skladu naposledy změnil                                                                                                                                                 | 11/23/2016 0:00                      |


## <a name="next-steps"></a>Další kroky
- Pomocí kolekce entit **aktuální uživatel** můžete omezit uživatelská data na uživatele, kteří jsou aktuálně aktivní. Další informace najdete v tématu [referenční informace o entitě aktuálního uživatele](../reports-ref-current-user.md).
- Další informace o tom, jak datový sklad sleduje dobu života uživatele v Intune, najdete v tématu [reprezentace životního cyklu uživatele v datovém skladu Intune](reports-ref-user-timeline.md).
