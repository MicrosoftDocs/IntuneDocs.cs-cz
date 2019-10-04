---
title: Referenční informace o entitách aplikace
titleSuffix: Microsoft Intune
description: Téma reference pro kategorii aplikací pro kolekce entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1e737f1cce594b5dd40b2f43048ba37578f5d7c9
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940437"
---
# <a name="reference-for-application-entities"></a>Referenční informace o entitách aplikace

Kategorie **aplikace** obsahuje entity pro mobilní zařízení, které sledují informace, jako například:

- Verze aplikace
- Zdroj instalace aplikace
- Typ vývojářů, kteří aplikaci vytvořili
- Spravované typy softwaru pro aplikaci, například **postranní vozík** nebo **plocha**
- Stav programu Volume purchase program (VPP) aplikace

## <a name="apprevisions"></a>appRevisions

Entita **appRevision** obsahuje seznam všech verzí aplikací.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| AppKey |Jedinečný identifikátor aplikace |123 |
| ApplicationId |Jedinečný identifikátor aplikace podobný AppKey, ale tento klíč je přirozený. |b66bc706-FFFF-7437-0340-032819502773 |
| Revize |Verze uvedená správcem během nahrávání binárního souboru. |odst |
| Hlava |Název aplikace |Excel |
| Microsoft |Vydavatel aplikace |Microsoft |
| UploadState |Odeslat stav aplikace |první |
| AppTypeKey |Odkaz na typ aplikace popsaný v následující části. | |
| VppProgramTypeKey |Odkaz na entitu vppprogramtype popsaný níže. | |
| CreationTime |Čas, kdy byla tato revize vytvořena. |11/23/2016 12:00:00 DOP. |
| ModifiedTime |Čas posledního pokusu o změnu jakékoli souvislosti s touto revizí. |11/23/2016 12:00:00 DOP. |
| velikost |Velikost binárního souboru. | |
| StartDateInclusiveUTC |Datum a čas ve standardu UTC, kdy se tato revize aplikace v datovém skladu vytvořila |11/23/2016 12:00:00 DOP. |
| EndDateExclusiveUTC |Datum a čas ve standardu UTC, kdy se tato revize aplikace stala zastaralou |11/23/2016 12:00:00 DOP. |
| Aktuální |Určuje, jestli je tato verze aplikace v datovém skladu aktuální nebo ne. |True nebo false |
| RowLastModifiedDateTimeUTC |Datum a čas ve standardu UTC, kdy se tato verze aplikace v datovém skladu naposledy změnila |11/23/2016 12:00:00 DOP. |

## <a name="apptypes"></a>AppTypes

Entita **Typ aplikace** obsahuje zdroj instalace aplikace.

| Vlastnost  | Popis |
|---------|------------|
| AppTypeID |ID pro typ |
| AppTypeKey |Náhradní klíč pro klíč |
| AppTypeName |Typ aplikace |

### <a name="example"></a>Příklad

| AppTypeID  | Name | Popis |
|---------|------------|--------|
| 0,8 |Aplikace pro Android Store | Aplikace pro Android Store |
| první |Obchodní aplikace pro Android | Obchodní aplikace pro Android. |
| odst |Spravovaná aplikace pro Android Store (MAM) | Aplikace z obchodu pro Android s povolenou správou |
| 3 |aplikace pro iOS Store | Aplikace pro iOS Store |
| 4 |aplikace LOB pro iOS | Obchodní aplikace pro iOS. |
| 5 |Spravovaná aplikace z obchodu pro iOS (MAM?) | Aplikace Z obchodu, která je povolená pro správu. |
| 6 |Sada O365 pro plus | Sada Office 365 pro plus pro Windows 10. |
| čl |Webová aplikace | Webová aplikace |
| 8 |Aplikace Windows Phone 8,1 Store | Aplikace pro Windows Phone 8,1 Store. |
| 9 |Aplikace pro Windows Store | Aplikace pro Windows Store |
| 10pruhový |Aplikace LOB pro Windows | Obchodní aplikace Windows AppX. |
| odst |Windows Mobile MSI | Obchodní aplikace MSI. |
| 12,5 |Aplikace Windows Phone LOB | Obchodní aplikace pro Windows Phone. |


## <a name="vppprogramtypes"></a>VppProgramTypes

Entita **entitu vppprogramtype** uvádí možné typy programů VPP pro aplikaci.

| Vlastnost  | Popis |
|---------|------------|
| VppProgramTypeID | ID pro typ |
| VppProgramTypeKey | Náhradní klíč pro klíč |
| VppProgramTypeName | Typ programu VPP |

### <a name="example"></a>Příklad

| VppProgramID  | Name | Popis |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft | Program VPP společnosti Microsoft. |
| 00000000-0000-0000-0000-000000000000 | Ještě není k dispozici | Výchozí hodnota, žádný VPP |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple | Program VPP společnosti Apple. |



## <a name="applicationinventories"></a>applicationInventories

Entita **entita applicationinventory zobrazuje** obsahuje seznam aplikací, které se v zařízení našly v okamžiku shromažďování inventáře.

| Vlastnost  | Popis |
|---------|------------|
| DeviceKey | Toto je odkaz na tabulku zařízení obsahující ID zařízení v Intune. |
| DateKey | Odkaz na tabulku kalendářních dat udávající den inventáře |
| ApplicationName | Název aplikace |
| applicationVersion | Verze aplikace |
| BundleSize | Velikost aplikace v bajtech |

## <a name="mobileappinstallstates"></a>mobileAppInstallStates

Entita **entita mobileappinstallstate** představuje stav instalace mobilní aplikace poté, co byla přiřazena ke skupině obsahující zařízení, uživatele nebo obojímu.

| Vlastnost | Popis |
|---|---|
| AppInstallStateKey | Jedinečné ID stavu instalace aplikace pro váš účet. |
| AppInstallState | Hodnota výčtu stavu instalace aplikace |
| AppInstallStateName | Název stavu instalace aplikace |



