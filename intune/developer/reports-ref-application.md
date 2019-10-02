---
title: Referenční informace o entitách aplikace
titleSuffix: Microsoft Intune
description: Téma referenčních informací ke kategorii Aplikace pro kolekce entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/09/2019
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
ms.openlocfilehash: a5436de6b972e5cbe8b2b17d42f0974cb38df47e
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730162"
---
# <a name="reference-for-application-entities"></a>Referenční informace o entitách aplikací

Kategorie **Aplikace** obsahuje entity pro mobilní zařízení, které sledují informace, například:

- Verze aplikace
- Zdroj instalace aplikace
- Typ vývojářů, kteří aplikaci vytvořili
- Typy spravovaného softwaru pro aplikaci, například **sidecar** nebo **desktop**
- Stav VPP (Volume Purchase Program) pro aplikaci

## <a name="apprevisions"></a>appRevisions

Entita **appRevision** obsahuje seznam všech verzí aplikací.

| Vlastnost  | Description | Příklad |
|---------|------------|--------|
| AppKey |Jedinečný identifikátor aplikace |123 |
| ApplicationId |Jedinečný identifikátor aplikace – podobá se AppKey, ale tento klíč je přirozený. |b66bc706-ffff-7437-0340-032819502773 |
| Revize |Verze, kterou uvedl správce během nahrávání binárního souboru |2 |
| title |Název aplikace |Excel |
| Microsoft |Vydavatel aplikace |Microsoft |
| UploadState |Stav nahrávání aplikace |1 |
| AppTypeKey |Odkaz na entitu AppType, která je popsaná v následujícím oddílu | |
| VppProgramTypeKey |Odkaz na entitu VppProgramType, která je popsaná níže | |
| CreationTime |Čas vytvoření této revize |23.11.2016 12:00:00 |
| ModifiedTime |Čas poslední změny nějakého prvku, který s touto revizí souvisí |23.11.2016 12:00:00 |
| Velikost |Velikost binárního souboru | |
| startDateInclusiveUTC |Datum a čas ve standardu UTC, kdy se tato revize aplikace v datovém skladu vytvořila |23.11.2016 12:00:00 |
| EndDateExclusiveUTC |Datum a čas ve standardu UTC, od kdy je tato revize aplikace zastaralá |23.11.2016 12:00:00 |
| Aktuální |Určuje, jestli tato verze aplikace v datovém skladu je nebo není aktuální |True nebo False |
| RowLastModifiedDateTimeUTC |Datum a čas ve standardu UTC, kdy se tato verze aplikace v datovém skladu naposledy změnila |23.11.2016 12:00:00 |

## <a name="apptypes"></a>appTypes

Entita **appType** obsahuje seznam zdrojů instalace aplikace.

| Vlastnost  | Description |
|---------|------------|
| AppTypeID |ID pro daný typ |
| AppTypeKey |Náhradní klíč pro daný klíč |
| AppTypeName |Typ aplikace |

### <a name="example"></a>Příklad

| AppTypeID  | Název | Description |
|---------|------------|--------|
| 0 |Aplikace z obchodu pro Android | Aplikace z obchodu pro Android |
| 1 |Obchodní aplikace pro Android | Obchodní aplikace pro Android |
| 2 |Spravovaná aplikace z obchodu pro Android (MAM) | Aplikace z obchodu pro Android s povolenou správou |
| 3 |Aplikace z obchodu pro iOS | Aplikace z obchodu pro iOS |
| 4 |Obchodní aplikace pro iOS | Obchodní aplikace pro iOS |
| 5 |Spravovaná aplikace obchodu pro iOS (MAM) | Aplikace z obchodu pro iOS s povolenou správou |
| 6 |Sada O365 Pro Plus | Sada Office 365 Pro Plus pro Windows 10 |
| 7 |Webová aplikace | Webová aplikace |
| 8 |Aplikace pro Windows Phone 8.1 Store | Aplikace pro Windows Phone 8.1 Store |
| 9 |Aplikace pro Windows Store | Aplikace pro Windows Store |
| 10 |Obchodní aplikace pro Windows | Obchodní aplikace Windows AppX |
| 11 |Windows Mobile MSI | Obchodní aplikace MSI |
| 12 |Obchodní aplikace pro Windows Phone | Obchodní aplikace pro Windows Phone |


## <a name="vppprogramtypes"></a>vppProgramTypes

Entita **vppProgramType** obsahuje seznam možných typů programu VPP pro aplikaci.

| Vlastnost  | Description |
|---------|------------|
| VppProgramTypeID | ID pro daný typ |
| VppProgramTypeKey | Náhradní klíč pro daný klíč |
| VppProgramTypeName | Typ programu VPP |

### <a name="example"></a>Příklad

| VppProgramID  | Název | Description |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft | Program VPP společnosti Microsoft |
| 00000000-0000-0000-0000-000000000000 | Ještě není k dispozici | Výchozí hodnota, žádný program VPP |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple | Program VPP společnosti Apple |



## <a name="applicationinventories"></a>applicationInventories

Entita **entita applicationinventory zobrazuje** obsahuje seznam aplikací, které se v zařízení našly v okamžiku shromažďování inventáře.

| Vlastnost  | Description |
|---------|------------|
| DeviceKey | Jedná se o odkaz na tabulku zařízení obsahující ID zařízení v Intune. |
| dateKey | Odkaz na tabulku kalendářních dat udávající den inventáře |
| ApplicationName | Název aplikace |
| applicationVersion | Verze aplikace |
| BundleSize | Velikost aplikace v bajtech |

## <a name="mobileappinstallstates"></a>mobileAppInstallStates

Entita **entita mobileappinstallstate** představuje stav instalace mobilní aplikace poté, co byla přiřazena ke skupině obsahující zařízení, uživatele nebo obojímu.

| Vlastnost | Description |
|---|---|
| AppInstallStateKey | Jedinečné ID stavu instalace aplikace pro váš účet |
| AppInstallState | Hodnota výčtu stavu instalace aplikace |
| AppInstallStateName | Název stavu instalace aplikace |



