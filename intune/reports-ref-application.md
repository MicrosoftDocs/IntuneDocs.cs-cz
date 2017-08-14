---
title: Aplikace | Dokumentace Microsoftu
description: "Téma referenčních informací ke kategorii Aplikace pro kolekce entit v rozhraní API datového skladu Intune"
keywords: "Datový sklad Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2e12792445b36ba6657cbe6b2f6c924f6d97fe3c
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/04/2017
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
| Size |Velikost binárního souboru | |
| StartDateInclusiveUTC |Datum a čas ve standardu UTC, kdy se tato revize aplikace v datovém skladu vytvořila |23.11.2016 12:00:00 |
| EndDateExclusiveUTC |Datum a čas ve standardu UTC, od kdy je tato revize aplikace zastaralá |23.11.2016 12:00:00 |
| IsCurrent |Určuje, jestli tato verze aplikace v datovém skladu je nebo není aktuální |True nebo False |
| RowLastModifiedDateTimeUTC |Datum a čas ve standardu UTC, kdy se tato verze aplikace v datovém skladu naposledy změnila |23.11.2016 12:00:00 |

## <a name="appinstallertypes"></a>AppInstallerTypes

Entita **AppInstallerTypes** obsahuje seznam zdrojů instalace aplikace.

| Vlastnost  | Popis |
|---------|------------|
| AppTypeID |ID pro daný typ |
| AppTypeKey |Náhradní klíč pro daný klíč |
| AppTypeName |Typ aplikace |

## <a name="example"></a>Příklad

| AppTypeID  | Název | Popis |
|---------|------------|--------|
| 0 |Aplikace z obchodu pro Android |Aplikace z obchodu pro Android |
| 1 |Obchodní aplikace pro Android |Obchodní aplikace pro Android |
| 2 |Spravovaná aplikace z obchodu pro Android (MAM) |Aplikace z obchodu pro Android s povolenou správou |
| 3 |Aplikace z obchodu pro iOS |Aplikace z obchodu pro iOS |
| 4 |Obchodní aplikace pro iOS |Obchodní aplikace pro iOS |
| 5 |Spravovaná aplikace obchodu pro iOS (MAM) |Aplikace z obchodu pro iOS s povolenou správou |
| 6 |Sada O365 Pro Plus |Sada Office 365 Pro Plus pro Windows 10 |
| 7 |Webová aplikace |Webová aplikace |
| 8 |Aplikace pro Windows Phone 8.1 Store |Aplikace pro Windows Phone 8.1 Store |
| 9 |Aplikace pro Windows Store |Aplikace pro Windows Store |
| 10 |Obchodní aplikace pro Windows |Obchodní aplikace Windows AppX |
| 11 |Windows Mobile MSI |Obchodní aplikace MSI |
| 12 |Obchodní aplikace pro Windows Phone |Obchodní aplikace pro Windows Phone |

## <a name="applicationtypes"></a>ApplicationTypes

Entita **ApplicationTypes** obsahuje seznam možných typů aplikace.

| Vlastnost  | Popis |
|---------|------------|
| ApplicationTypeID |ID pro daný typ |
| ApplicationTypeKey |Náhradní klíč pro daný klíč |
| ApplicationTypeName |Typ aplikace |

## <a name="example"></a>Příklad

| ApplicationTypeID  | Název | Popis |
|---------|------------|--------|
| 0 |InHouse |Interně vyvinutá aplikace |
| 1 |DeepLink |Odkaz na aplikaci v App Storu |
| 2 |WebLink |Odkaz na webovou aplikaci |

## <a name="managedsoftwaretypes"></a>ManagedSoftwareTypes

Entita **ManagedSoftwareTypes** obsahuje seznam možných typů spravovaného softwaru pro aplikaci.

| Vlastnost  | Popis |
|---------|------------|
| SoftwareTypeID |ID pro daný typ |
| SoftwareTypeKey |Náhradní klíč pro daný klíč |
| SoftwareTypeName |Typ softwaru |

## <a name="example"></a>Příklad

| SoftwareTypeID  | Název | Popis |
|---------|------------|--------|
| 0 |Desktop |Desktopová aplikace |
| 2 |Aktualizovat |Aktualizace okna |
| 5 |SideCarAgent | |
| 1 |Mobilní |Mobilní aplikace |
| 3 |WebLink |Webový odkaz |
| 4 |VppDeepLink |Odkaz na aplikaci v App Storu, která je součástí programu VPP (Volume Purchase Program) |

## <a name="vppprogramtypes"></a>VppProgramTypes

Entita **VppProgramTypes** obsahuje seznam možných typů programu VPP pro aplikaci.

| Vlastnost  | Popis |
|---------|------------|
| VppProgramTypeID |ID pro daný typ |
| VppProgramTypeKey |Náhradní klíč pro daný klíč |
| VppProgramTypeName |Typ programu VPP |

## <a name="example"></a>Příklad

| VppProgramID  | Název | Popis |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 |Microsoft |Program VPP společnosti Microsoft |
| 00000000-0000-0000-0000-000000000000 |Ještě není k dispozici |Výchozí hodnota, žádný program VPP |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B |Apple |Program VPP společnosti Apple |