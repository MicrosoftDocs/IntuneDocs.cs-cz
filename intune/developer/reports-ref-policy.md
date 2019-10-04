---
title: Referenční informace pro entity zásad
titleSuffix: Microsoft Intune
description: Referenční téma pro kategorii zásad pro kolekce entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: a812234588081443c2ee8ea8d42b161c22ad4232
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940339"
---
# <a name="reference-for-policy-entities"></a>Referenční informace pro entity zásad

Kategorie **zásady** obsahuje entity pro mobilní zařízení, které sledují informace, jako například:

- Inventář profilů konfigurace zařízení, konfiguračních profilů aplikací a zásad dodržování předpisů  
- Počet zařízení v úspěšném, nevyřízeném, neúspěšném nebo chybovém stavu za den  
- Počet uživatelů v úspěšném, nevyřízeném, neúspěšném nebo chybovém stavu za den  
- Kumulativní počet zařízení v úspěšném, nevyřízeném, neúspěšném nebo chybovém stavu  

## <a name="policies"></a>Zásady

Entita **zásady** uvádí profily konfigurace zařízení, konfigurační profily aplikací a zásady dodržování předpisů. Zásady se správou mobilních zařízení (MDM) můžete přiřadit ke skupině v podniku.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| PolicyKey |Jedinečný klíč, který bude představovat zásady v datovém skladu. |123 |
| PolicyId |Jedinečný identifikátor zásad v datovém skladu. |b66bc706-FFFF-7437-0340-032819502773 |
| PolicyName |Název zásady |"Směrný plán Windows 10" |
| PolicyVersion |Verze zásad Když se zásada upraví nebo změní, vytvoří se novější verze. |1, 2, 3 |
| IsDeleted |Určuje, jestli se záznam zásad aktualizoval.  <br>True – zásada má nový záznam s aktualizovanými poli. <br>False – poslední záznam pro zásadu. |True nebo false |
| StartDateInclusiveUTC |Datum a čas ve standardu UTC, kdy se tyto zásady v datovém skladu vytvořily |11/23/2016 12:00:00 DOP. |
| DeletedDateUTC |Datum a čas ve standardu UTC, kdy došlo ke změně hodnoty IsDeleted na hodnotu true |11/23/2016 12:00:00 DOP. |
| RowLastModifiedDateTimeUTC |Datum a čas ve standardu UTC, kdy se tyto zásady v datovém skladu naposledy změnily |11/23/2016 12:00:00 DOP. |

## <a name="policytypes"></a>policyTypes

Entita **policyType** obsahuje seznam typů profilů konfigurace zařízení, konfiguračních profilů aplikací a zásad dodržování předpisů. Zásady se správou mobilních zařízení (MDM) můžete přiřadit ke skupině v podniku.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| PolicyTypeId |Jedinečný identifikátor zásad ve zdrojovém systému. |123 |
| PolicyTypeKey |Jedinečný identifikátor zásad v datovém skladu. |první |
| PolicyTypeName |Název typu zásad |Zásady dodržování předpisů ve Windows 10 |

## <a name="device-configuration"></a>Konfigurace zařízení

Entita **deviceConfigurationProfileDeviceActivity** uvádí počet **zařízení** v úspěšném, nevyřízeném, neúspěšném nebo chybovém stavu za den. Číslo odráží profily konfigurace zařízení přiřazené k entitě. Pokud je například **zařízení** v úspěšném stavu pro všechny přiřazené zásady, zvýší se v tomto dni čítač úspěšného dokončení. Pokud má zařízení přiřazené dva profily, jeden v úspěšném stavu a druhý v chybovém stavu, entita zvýší čítač úspěšných a umístí zařízení do chybového stavu. Entita uvádí počet zařízení, ve kterých se v daném dni během posledních 30 dnů zobrazuje stav.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| DateKey |Klíč data, kdy se vrácení se změnami konfiguračního profilu zařízení v datovém skladu zaznamenalo |20160703 |
| Uložené |Počet jedinečných zařízení v nevyřízeném stavu. |123 |
| Úspěchu |Počet jedinečných zařízení v úspěšném stavu |12,5 |
| error |Počet jedinečných zařízení v chybovém stavu. |10pruhový |
| failed |Počet jedinečných zařízení v neúspěšném stavu |odst |

Entita **entita deviceconfigurationprofileuseractivity** uvádí počet **uživatelů** v úspěšném, nevyřízeném, neúspěšném nebo chybovém stavu za den. Číslo odráží profily konfigurace zařízení přiřazené k entitě. Například pokud je **uživatel** v úspěšném stavu pro všechny přiřazené zásady, posune čítač úspěšného počítadla o jeden den. Pokud má uživatel přiřazené dva profily, jeden v úspěšném stavu a druhý je v chybovém stavu, započítá se uživatel v chybovém stavu.  Entita **entita deviceconfigurationprofileuseractivity** uvádí, kolik uživatelů se v daném dni během posledních 30 dnů zobrazuje.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| DateKey |Klíč data, kdy se vrácení se změnami konfiguračního profilu zařízení v datovém skladu zaznamenalo |20160703 |
| Uložené |Počet jedinečných uživatelů ve stavu čeká na vyřízení. |123 |
| Úspěchu |Počet jedinečných uživatelů v úspěšném stavu |12,5 |
| error |Počet jedinečných uživatelů v chybovém stavu. |10pruhový |
| failed |Počet jedinečných uživatelů v neúspěšném stavu |odst |

## <a name="policytypeactivities"></a>policyTypeActivities

Entita **policyTypeActivity** obsahuje kumulativní počet zařízení v úspěšném, nevyřízeném, neúspěšném nebo chybovém stavu. Uvádí tyto stavy s ohledem na konfigurační profil zařízení, konfigurační profil aplikace nebo zásady dodržování předpisů za den.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| DateKey |dateKey, když se v datovém skladu zaznamenalo vrácení se změnami konfiguračního profilu zařízení. |20160703 |
| PolicyKey |policyKey se dá připojit k zásadám a získat tak zásadu. |Směrný plán Windows 10 |
| PolicyTypeKey |Typ klíče zásad se dá spojit s typem zásad a získat tak název typu zásad. |Zásady dodržování předpisů v Windows10 |
| Uložené |Počet jedinečných zařízení v nevyřízeném stavu. |123 |
| Úspěchu |Počet jedinečných zařízení v úspěšném stavu |12,5 |
| error |Počet jedinečných zařízení v chybovém stavu. |10pruhový |
| failed |Počet jedinečných zařízení v neúspěšném stavu |odst |

## <a name="compliance-policy"></a>Zásady dodržování předpisů

Reference k rozhraní API zásad dodržování předpisů obsahují entity, které poskytují informace o stavu pro zásady dodržování předpisů přiřazené zařízením.

### <a name="compliancepolicystatusdeviceactivities"></a>CompliancePolicyStatusDeviceActivities

Následující tabulka shrnuje stav přiřazení zásad dodržování předpisů na zařízení. Zobrazuje počet zařízení nalezených v jednotlivých stavech dodržování předpisů.


|Vlastnost     |Popis  |Příklad  |
|---------|---------|---------|
|DateKey  |Klíč data, kdy se vytvořil souhrn pro zásady dodržování předpisů.|20161204 |
|Neznámý  |Počet zařízení, která jsou offline nebo se nezdařila komunikace s Intune nebo Azure AD z jiných důvodů. |5|
|NotApplicable      |Počet zařízení, ve kterých nejsou použitelné zásady dodržování předpisů zařízením, které cílí na správce.|201 |
|Kompatibilní      |Počet zařízení, která úspěšně použili jednu nebo více zásad dodržování předpisů zařízením, které cílí správce. |4083 |
|V období odkladu      |Počet zařízení, která nedodržují předpisy, ale jsou v období odkladu definovaném správcem. |57|
|Nekompatibilních      |Počet zařízení, u kterých se nepodařilo použít jednu nebo více zásad dodržování předpisů zařízením, které cílí na správce nebo kde uživatel nevyhověl zásadám, které cílí na správce.|43 |
|error      |Počet zařízení, která nedokázala komunikovat se službou Intune nebo Azure AD, a vrátila chybovou zprávu. |3|

### <a name="compliancepolicystatusdeviceperpolicyactivities"></a>CompliancePolicyStatusDevicePerPolicyActivities 

Následující tabulka shrnuje stav přiřazení zásad dodržování předpisů pro zařízení na základě zásad a pro jednotlivé typy zásad. Zobrazuje počet zařízení nalezených v jednotlivých stavech dodržování předpisů pro každou přiřazenou zásadu dodržování předpisů.



|Vlastnost  |Popis  |Příklad  |
|---------|---------|---------|
|DateKey  |Klíč data, kdy se vytvořil souhrn pro zásady dodržování předpisů.|20161219|
|PolicyKey     |Klíč pro zásady dodržování předpisů, pro které se vytvořil souhrn |10178 |
|PolicyPlatformKey      |Klíč pro typ platformy zásad dodržování předpisů, pro který se vytvořil souhrn.|5|
|Neznámý     |Počet zařízení, která jsou offline nebo se nezdařila komunikace s Intune nebo Azure AD z jiných důvodů.|13,5|
|NotApplicable     |Počet zařízení, ve kterých nejsou použitelné zásady dodržování předpisů zařízením, které cílí na správce.|3|
|Kompatibilní      |Počet zařízení, která úspěšně použili jednu nebo více zásad dodržování předpisů zařízením, které cílí správce. |45|
|V období odkladu      |Počet zařízení, která nedodržují předpisy, ale jsou v období odkladu definovaném správcem. |3|
|Nekompatibilních      |Počet zařízení, u kterých se nepodařilo použít jednu nebo více zásad dodržování předpisů zařízením, které cílí na správce nebo kde uživatel nevyhověl zásadám, které cílí na správce.|čl|
|error      |Počet zařízení, která nedokázala komunikovat se službou Intune nebo Azure AD, a vrátila chybovou zprávu. |3|

### <a name="policyplatformtypes"></a>PolicyPlatformTypes

Následující tabulka obsahuje typy platforem všech přiřazených zásad. V této tabulce nejsou k dispozici typy platforem zásad, které nikdy nebyly přiřazeny k žádným zařízením.


|Vlastnost  |Popis  |Příklad  |
|---------|---------|---------|
|PolicyPlatformTypeKey      |Jedinečný klíč pro typ platformy zásad |20170519 |
|PolicyPlatformTypeId      |Jedinečný identifikátor pro typ platformy zásad|první|
|PolicyPlatformTypeName      |Název pro typ platformy zásad|AndroidForWork |

### <a name="policydeviceactivities"></a>policyDeviceActivities

Následující tabulka uvádí počet zařízení v úspěšném, nevyřízeném, neúspěšném nebo chybovém stavu za den. Číslo odráží data na profily typů zásad. Pokud je například zařízení v úspěšném stavu pro všechny přiřazené zásady, zvýší se v tomto dni čítač úspěšného dokončení. Pokud má zařízení přiřazené dva profily, jeden v úspěšném stavu a druhý v chybovém stavu, entita zvýší čítač úspěšných a umístí zařízení do chybového stavu. V entitě policyDeviceActivity se uvádí počet zařízení, ve kterých se v daném dni během posledních 30 dnů zobrazuje stav.

|Vlastnost  |Popis  |Příklad  |
|---------|---------|---------|
|DateKey|Klíč data, kdy se vrácení se změnami konfiguračního profilu zařízení v datovém skladu zaznamenalo|20160703|
|Uložené|Počet jedinečných zařízení v nevyřízeném stavu.|123|
|Úspěchu|Počet jedinečných zařízení v úspěšném stavu|12,5|
|PolicyKey|policyKey se dá připojit k zásadám a získat tak zásadu.|Směrný plán Windows 10|
|error|Počet jedinečných zařízení v chybovém stavu.|10pruhový|
|failed|Počet jedinečných zařízení v neúspěšném stavu|odst|

### <a name="policyuseractivities"></a>policyUserActivities

V následující tabulce je uveden počet uživatelů v úspěšném, nevyřízeném, neúspěšném nebo chybovém stavu za den. Číslo odráží data na profily typů zásad. Například pokud je uživatel v úspěšném stavu pro všechny přiřazené zásady, posune čítač úspěšného počítadla o jeden den. Pokud má uživatel přiřazené dva profily, jeden v úspěšném stavu a druhý je v chybovém stavu, započítá se uživatel v chybovém stavu. Entita PolicyUserActivity uvádí, kolik uživatelů se v daném dni během posledních 30 dnů zobrazuje.


| Vlastnost  |                                         Popis                                         |       Příklad       |
|-----------|---------------------------------------------------------------------------------------------|---------------------|
|  DateKey  | Klíč data, kdy se vrácení se změnami konfiguračního profilu zařízení v datovém skladu zaznamenalo |      20160703       |
|  Uložené  |                         Počet jedinečných zařízení v nevyřízeném stavu.                          |         123         |
| Úspěchu |                         Počet jedinečných zařízení v úspěšném stavu                          |         12,5          |
| PolicyKey |                 policyKey se dá připojit k zásadám a získat tak zásadu.                 | Směrný plán Windows 10 |
|   error   |                          Počet jedinečných zařízení v chybovém stavu.                           |         10pruhový          |

