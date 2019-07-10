---
title: Referenční informace pro entity zásad
titleSuffix: Microsoft Intune
description: Téma referenčních informací ke kategorii Zásady pro kolekce entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4f66cc3a10711b137e081fab98445d73108748a9
ms.sourcegitcommit: 63b55e81122e5c15893302b109ae137c30855b55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/10/2019
ms.locfileid: "67713157"
---
# <a name="reference-for-policy-entities"></a>Referenční informace pro entity zásad

Kategorie **Zásady** obsahuje entity pro mobilní zařízení, které sledují informace, například:

  - Inventář konfiguračních profilů zařízení, konfiguračních profilů aplikací a zásad dodržování předpisů  
  - Počet zařízení v úspěšném, čekajícím, neúspěšném nebo chybovém stavu za den  
  - Počet uživatelů v úspěšném, čekajícím, neúspěšném nebo chybovém stavu za den  
  - Kumulativní počet zařízení v úspěšném, čekajícím, neúspěšném nebo chybovém stavu  

## <a name="policy"></a>zásady

Entita **Policy** obsahuje seznam konfiguračních profilů zařízení, konfiguračních profilů aplikací a zásady dodržování předpisů. Zásady se správou mobilních zařízení (MDM) můžete přiřadit skupině ve vašem podniku.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| PolicyKey |Jedinečný klíč reprezentující zásady v datovém skladu |123 |
| PolicyId |Jedinečný identifikátor zásad v datovém skladu |b66bc706-ffff-7437-0340-032819502773 |
| PolicyName |Název zásad |„Směrný plán Windows 10“ |
| PolicyVersion |Verze zásad Když dojde k úpravě nebo změně zásad, vytvoří se novější verze. |1, 2, 3 |
| IsDeleted |Určuje, jestli je záznam zásad aktualizovaný.  <br>True – zásada má nový záznam s aktualizovanými poli. <br>False – jedná se o nejnovější záznam pro zásady. |True nebo False |
| StartDateInclusiveUTC |Datum a čas ve standardu UTC, kdy se tyto zásady v datovém skladu vytvořily |23.11.2016 12:00:00 |
| DeletedDateUTC |Datum a čas ve standardu UTC, kdy došlo ke změně vlastnosti IsDeleted na hodnotu True |23.11.2016 12:00:00 |
| RowLastModifiedDateTimeUTC |Datum a čas ve standardu UTC, kdy se tyto zásady v datovém skladu naposledy změnily |23.11.2016 12:00:00 |

## <a name="policytype"></a>PolicyType

Entita **PolicyType** obsahuje seznam typů konfiguračních profilů zařízení, konfiguračních profilů aplikací a zásady dodržování předpisů. Zásady se správou mobilních zařízení (MDM) můžete přiřadit skupině ve vašem podniku.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| PolicyTypeId |Jedinečný identifikátor zásad ve zdrojovém systému |123 |
| PolicyTypeKey |Jedinečný identifikátor zásad v datovém skladu |1 |
| PolicyTypeName |Název typu zásad |Zásady dodržování předpisů Windows 10 |

## <a name="deviceconfiguration"></a>DeviceConfiguration

**DeviceConfigurationProfileDeviceActivity** entita uvádí počet **zařízení** v úspěšném, čekajícím, neúspěšném nebo chybovém stavu za den. Číslo odráží konfigurační profily Zařízení přiřazené entitě. Například pokud **zařízení** je v úspěšném stavu pro všechny své přiřazené zásady, se zvýší Čítač úspěšných zařízení o jedno pro daný den. Pokud má zařízení přiřazené dva profily, jeden je v úspěšném stavu a druhý v chybovém stavu, entita zvýší čítač úspěšných zařízení o jedno a umístí zařízení do chybového stavu. Entita uvádí, kolik zařízení je v jakém stavu v daném dni za posledních 30 dní.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| DateKey |Klíč data, kdy se přihlášení konfiguračního profilu zařízení v datovém skladu zaznamenalo |20160703 |
| Čekající na vyřízení |Počet jedinečných zařízení v čekajícím stavu |123 |
| Úspěšné |Počet jedinečných zařízení v úspěšném stavu |12 |
| Chyba |Počet jedinečných zařízení v chybovém stavu |10 |
| Neúspěch |Počet jedinečných zařízení v neúspěšném stavu |2 |

**DeviceConfigurationProfileUserActivity** entita uvádí počet **uživatelé** v úspěšném, čekajícím, neúspěšném nebo chybovém stavu za den. Číslo odráží konfigurační profily Zařízení přiřazené entitě. Například pokud **uživatele** je v úspěšném stavu pro všechny své přiřazené zásady, přesune se Čítač úspěšných jednou za tento den. Pokud má uživatel přiřazené dva profily, jeden je v úspěšném stavu a druhý je v chybovém stavu, započítá se uživatel v chybovém stavu.  Entita **DeviceConfigurationProfileUserActivity** uvádí, kolik uživatelů je v jakém stavu v daném dni za posledních 30 dní.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| DateKey |Klíč data, kdy se přihlášení konfiguračního profilu zařízení v datovém skladu zaznamenalo |20160703 |
| Čekající na vyřízení |Počet jedinečných uživatelů v čekajícím stavu |123 |
| Úspěšné |Počet jedinečných uživatelů v úspěšném stavu |12 |
| Chyba |Počet jedinečných uživatelů v chybovém stavu |10 |
| Neúspěch |Počet jedinečných uživatelů v neúspěšném stavu |2 |

## <a name="policytypeactivity"></a>PolicyTypeActivity

Entita **PolicyTypeActivity** obsahuje kumulativní počet zařízení v úspěšném, čekajícím, neúspěšném nebo chybovém stavu. Zobrazí tyto stavy s ohledem na konfigurační profil zařízení, konfigurační profil aplikace nebo zásady dodržování předpisů na den.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| DateKey |Klíč data, kdy se přihlášení konfiguračního profilu zařízení v datovém skladu zaznamenalo |20160703 |
| PolicyKey |Klíč zásad, který jde připojit k zásadám a získat tak název zásad |Směrný plán Windows 10 |
| PolicyTypeKey |Typ klíče zásad, který jde připojit k typu zásad a získat tak název typu zásad |Zásady dodržování předpisů Windows 10 |
| Čekající na vyřízení |Počet jedinečných zařízení v čekajícím stavu |123 |
| Úspěšné |Počet jedinečných zařízení v úspěšném stavu |12 |
| Chyba |Počet jedinečných zařízení v chybovém stavu |10 |
| Neúspěch |Počet jedinečných zařízení v neúspěšném stavu |2 |

## <a name="compliance-policy"></a>Zásady dodržování předpisů

Referenční dokumentace rozhraní Compliance Policy API obsahuje entity, které poskytují stavové informace týkající se zásad dodržování předpisů přiřazených k zařízením.

### <a name="compliancepolicystatusdeviceactivities"></a>CompliancePolicyStatusDeviceActivities

Následující tabulka shrnuje stav přiřazení zásad dodržování předpisů k zařízením. Uvádí počet zařízení nacházejících se v jednotlivých stavech shody.


|Vlastnost     |Popis  |Příklad  |
|---------|---------|---------|
|DateKey  |Klíč data, kdy se vytvořil souhrn pro zásady dodržování předpisů|20161204 |
|Neznámé  |Počet zařízení, která jsou offline nebo kterým se nepodařilo komunikovat s Intune nebo Azure AD z jiných důvodů |5|
|NotApplicable      |Počet zařízení, ve kterých nejsou použitelné zásady dodržování předpisů, na které zacílil správce|201 |
|Odpovídající      |Počet zařízení, ve kterých se úspěšně použily jedny nebo více zásad dodržování předpisů, na které zacílil správce |4083 |
|InGracePeriod      |Počet zařízení, která nevyhovují předpisům, ale jsou v období odkladu definovaném správcem |57|
|NonCompliant      |Počet zařízení, u kterých se nepodařilo použít jedny nebo více zásad dodržování předpisů, na které zacílil správce nebo u kterých uživatel nedodržel zásady, na které zacílil správce|43 |
|Chyba      |Počet zařízení, kterým se nepodařilo komunikovat s Intune nebo Azure AD a která vrátila chybovou zprávu |3|

### <a name="compliancepolicystatusdeviceperpolicyactivities"></a>CompliancePolicyStatusDevicePerPolicyActivities 

Následující tabulka shrnuje stav přiřazení zásad dodržování předpisů k zařízením pro jednotlivé zásady a pro jednotlivé typy zásad. Uvádí počet zařízení nacházejících se v jednotlivých stavech shody pro všechny přiřazené zásady dodržování předpisů.



|Vlastnost  |Popis  |Příklad  |
|---------|---------|---------|
|DateKey  |Klíč data, kdy se vytvořil souhrn pro zásady dodržování předpisů|20161219|
|PolicyKey     |Klíč pro zásady dodržování předpisů, pro který se vytvořil souhrn |10178 |
|PolicyPlatformKey      |Klíč pro typ platformy zásad dodržování předpisů, pro který se vytvořil souhrn|5|
|Neznámé     |Počet zařízení, která jsou offline nebo kterým se nepodařilo komunikovat s Intune nebo Azure AD z jiných důvodů|13|
|NotApplicable     |Počet zařízení, ve kterých nejsou použitelné zásady dodržování předpisů, na které zacílil správce|3|
|Odpovídající      |Počet zařízení, ve kterých se úspěšně použily jedny nebo více zásad dodržování předpisů, na které zacílil správce |45|
|InGracePeriod      |Počet zařízení, která nevyhovují předpisům, ale jsou v období odkladu definovaném správcem |3|
|NonCompliant      |Počet zařízení, u kterých se nepodařilo použít jedny nebo více zásad dodržování předpisů, na které zacílil správce nebo u kterých uživatel nedodržel zásady, na které zacílil správce|7|
|Chyba      |Počet zařízení, kterým se nepodařilo komunikovat s Intune nebo Azure AD a která vrátila chybovou zprávu |3|

### <a name="policyplatformtypes"></a>PolicyPlatformTypes

Následující tabulka obsahuje typy platforem všech přiřazených zásad. Typy platforem zásad, které se k žádným zařízením nikdy nepřiřadily, se v této tabulce nenacházejí.


|Vlastnost  |Popis  |Příklad  |
|---------|---------|---------|
|PolicyPlatformTypeKey      |Jedinečný klíč pro typ platformy zásad |20170519 |
|PolicyPlatformTypeId      |Jedinečný identifikátor pro typ platformy zásad|1|
|PolicyPlatformTypeName      |Název typu platformy zásad|AndroidForWork |

### <a name="policydeviceactivity"></a>PolicyDeviceActivity

Následující tabulka uvádí počet zařízení v úspěšném, čekajícím, neúspěšném nebo chybovém stavu za den. Číslo odráží data pro jednotlivé profily typu zásad. Pokud se například zařízení nachází v úspěšném stavu pro všechny své přiřazené zásady, zvýší čítač úspěšných zařízení pro daný den o jedno. Pokud má zařízení přiřazené dva profily, jeden je v úspěšném stavu a druhý v chybovém stavu, entita zvýší čítač úspěšných zařízení o jedno a umístí zařízení do chybového stavu. Entita PolicyDeviceActivity uvádí, kolik zařízení je v jakém stavu v daném dni za posledních 30 dní.

|Vlastnost  |Popis  |Příklad  |
|---------|---------|---------|
|DateKey|Klíč data, kdy se přihlášení konfiguračního profilu zařízení v datovém skladu zaznamenalo|20160703|
|Čekající na vyřízení|Počet jedinečných zařízení v čekajícím stavu|123|
|Úspěšné|Počet jedinečných zařízení v úspěšném stavu|12|
PolicyKey|Klíč zásad, který jde připojit k zásadám a získat tak název zásad|Směrný plán Windows 10|
|Chyba|Počet jedinečných zařízení v chybovém stavu|10|
|Neúspěch|Počet jedinečných zařízení v neúspěšném stavu|2|

### <a name="policyuseractivity"></a>PolicyUserActivity 

Následující tabulka uvádí počet uživatelů v úspěšném, čekajícím, neúspěšném nebo chybovém stavu za den. Číslo odráží data pro jednotlivé profily typu zásad. Pokud se například uživatel nachází v úspěšném stavu pro všechny své přiřazené zásady, posune čítač úspěšných uživatelů pro daný den o jedna nahoru. Pokud má uživatel přiřazené dva profily, jeden je v úspěšném stavu a druhý je v chybovém stavu, započítá se uživatel v chybovém stavu. Entita PolicyUserActivity uvádí, kolik uživatelů je v jakém stavu v daném dni za posledních 30 dní.


| Vlastnost  |                                         Popis                                         |       Příklad       |
|-----------|---------------------------------------------------------------------------------------------|---------------------|
|  DateKey  | Klíč data, kdy se přihlášení konfiguračního profilu zařízení v datovém skladu zaznamenalo |      20160703       |
|  Čekající na vyřízení  |                         Počet jedinečných zařízení v čekajícím stavu                          |         123         |
| Úspěšné |                         Počet jedinečných zařízení v úspěšném stavu                          |         12          |
| PolicyKey |                Klíč zásad, který jde připojit k zásadám a získat tak název zásad                 | Směrný plán Windows 10 |
|   Chyba   |                          Počet jedinečných zařízení v chybovém stavu                           |         10          |

