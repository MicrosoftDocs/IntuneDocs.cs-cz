---
title: Referenční informace pro entity aplikací
titlesuffix: Microsoft Intune
description: Téma referenčních informací ke kategorii Aplikace pro kolekce entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/06/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9d8284d84f089a27cc7d8f1becb3e538209359d9
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57399986"
---
# <a name="reference-for-application-entities"></a>Referenční informace o entitách aplikací

Kategorie **Aplikace** obsahuje entity pro mobilní zařízení, které sledují informace, například:

  -  Verze aplikace
  -  Zdroj instalace aplikace
  -  Typ vývojářů, kteří aplikaci vytvořili
  -  Typy spravovaného softwaru pro aplikaci, například **sidecar** nebo **desktop**
  -  Stav VPP (Volume Purchase Program) pro aplikaci

## <a name="apprevision"></a>AppRevision

Entita **AppRevision** obsahuje seznam všech verzí aplikací.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| AppKey |Jedinečný identifikátor aplikace |123 |
| ApplicationId |Jedinečný identifikátor aplikace – podobá se AppKey, ale tento klíč je přirozený. |b66bc706-ffff-7437-0340-032819502773 |
| Revize |Verze, kterou uvedl správce během nahrávání binárního souboru |2 |
| Název |Název aplikace |Excel |
| Vydavatel |Vydavatel aplikace |Microsoft |
| UploadState |Stav nahrávání aplikace |1 |
| AppTypeKey |Odkaz na entitu AppType, která je popsaná v následujícím oddílu | |
| VppProgramTypeKey |Odkaz na entitu VppProgramType, která je popsaná níže | |
| CreationTime |Čas vytvoření této revize |23.11.2016 12:00:00 |
| ModifiedTime |Čas poslední změny nějakého prvku, který s touto revizí souvisí |23.11.2016 12:00:00 |
| Velikost |Velikost binárního souboru | |
| StartDateInclusiveUTC |Datum a čas ve standardu UTC, kdy se tato revize aplikace v datovém skladu vytvořila |23.11.2016 12:00:00 |
| EndDateExclusiveUTC |Datum a čas ve standardu UTC, od kdy je tato revize aplikace zastaralá |23.11.2016 12:00:00 |
| IsCurrent |Určuje, jestli tato verze aplikace v datovém skladu je nebo není aktuální |True nebo False |
| RowLastModifiedDateTimeUTC |Datum a čas ve standardu UTC, kdy se tato verze aplikace v datovém skladu naposledy změnila |23.11.2016 12:00:00 |

## <a name="apptypes"></a>AppTypes

Entita **AppTypes** obsahuje seznam zdrojů instalace aplikace.

| Vlastnost  | Popis |
|---------|------------|
| AppTypeID |ID pro daný typ |
| AppTypeKey |Náhradní klíč pro daný klíč |
| AppTypeName |Typ aplikace |

### <a name="example"></a>Příklad

| AppTypeID  | Název | Popis |
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


## <a name="vppprogramtypes"></a>VppProgramTypes

Entita **VppProgramTypes** obsahuje seznam možných typů programu VPP pro aplikaci.

| Vlastnost  | Popis |
|---------|------------|
| VppProgramTypeID | ID pro daný typ |
| VppProgramTypeKey | Náhradní klíč pro daný klíč |
| VppProgramTypeName | Typ programu VPP |

### <a name="example"></a>Příklad

| VppProgramID  | Název | Popis |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft | Program VPP společnosti Microsoft |
| 00000000-0000-0000-0000-000000000000 | Ještě není k dispozici | Výchozí hodnota, žádný program VPP |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple | Program VPP společnosti Apple |



## <a name="applicationinventory"></a>ApplicationInventory

Entita **ApplicationInventory** zobrazuje seznam aplikací, které se na zařízení nacházejí v době shromažďování inventáře.

| Vlastnost  | Popis |
|---------|------------|
| DeviceKey | Jedná se o odkaz na tabulku zařízení obsahující ID zařízení v Intune. |
| DateKey | Odkaz na tabulku kalendářních dat udávající den inventáře |
| ApplicationName | Název aplikace |
| ApplicationVersion | Verze aplikace |
| BundleSize | Velikost aplikace v bajtech |

## <a name="mobileappinstallstate"></a>MobileAppInstallState

Entita **MobileAppInstallState** představuje stav instalace mobilní aplikace po jejím přiřazení do skupiny obsahující zařízení, uživatele, nebo obě tyto možnosti.

| Vlastnost | Popis |
|---|---|
| AppInstallStateKey | Jedinečné ID stavu instalace aplikace pro váš účet |
| AppInstallState | Hodnota výčtu stavu instalace aplikace |
| AppInstallStateName | Název stavu instalace aplikace |

## <a name="mobileappdeviceuserinstallstatus"></a>MobileAppDeviceUserInstallStatus

**MobileAppDeviceUserInstallStatus** představuje stav instalace mobilní aplikace pro dané zařízení a uživatele.


|      Vlastnost      |                                                         Popis                                                         |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------|
|      DateKey       |                                  Klíč data záznamu stavu instalace aplikace                                  |
|       AppKey       |                             Klíč mobilní aplikace, který se používá k identifikaci instance AppRevision                              |
|     DeviceKey      |                              Klíč cílového zařízení, který se používá k identifikaci instance Device                               |
|      UserKey       |                                Klíč cílového uživatele, který se používá k identifikaci instance User                                 |
| AppInstallStateKey |                     Klíč stavu instalace aplikace, který se používá k identifikaci instance MobileAppInstallState                     |
|     Kód chyby      | Kód chyby, který vrací instalační program aplikace, mobilní platforma nebo služba, které se instalace aplikace týká |

