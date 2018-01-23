---
title: "Zásady | Dokumentace Microsoftu"
description: "Téma referenčních informací ke kategorii Zásady pro kolekce entit v rozhraní API datového skladu Intune"
keywords: "Datový sklad Intune"
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D5ADB9D8-D46A-43BD-AB0F-D6927508E3F4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1425d172e5305f02405a4b05c19ab43c79a7353b
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2018
---
# <a name="reference-for-policy-entities"></a>Referenční informace pro entity zásad

Kategorie **Zásady** obsahuje entity pro mobilní zařízení, které sledují informace, například:

  -  Inventář konfiguračních profilů zařízení, konfiguračních profilů aplikací a zásad dodržování předpisů  
  -  Počet zařízení v úspěšném, čekajícím, neúspěšném nebo chybovém stavu za den  
  -  Počet uživatelů v úspěšném, čekajícím, neúspěšném nebo chybovém stavu za den  
  -  Kumulativní počet zařízení v úspěšném, čekajícím, neúspěšném nebo chybovém stavu  

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

Entita **DeviceConfigurationProfileDeviceActivity** obsahuje počet zařízení v úspěšném, čekajícím, neúspěšném nebo chybovém stavu za den. Číslo odráží konfigurační profily Zařízení přiřazené entitě. Pokud se například zařízení nachází v úspěšném stavu pro všechny své přiřazené zásady, zvýší čítač úspěšných zařízení pro daný den o jedno. Pokud má zařízení přiřazené dva profily, jeden je v úspěšném stavu a druhý v chybovém stavu, entita zvýší čítač úspěšných zařízení o jedno a umístí zařízení do chybového stavu. Entita uvádí, kolik zařízení je v jakém stavu v daném dni za posledních 30 dní.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| DateKey |Klíč data, kdy se přihlášení konfiguračního profilu zařízení v datovém skladu zaznamenalo |20160703 |
| Čeká |Počet jedinečných zařízení v čekajícím stavu |123 |
| Úspěšné |Počet jedinečných zařízení v úspěšném stavu |12 |
| Chyba |Počet jedinečných zařízení v chybovém stavu |10 |
| Neúspěch |Počet jedinečných zařízení v neúspěšném stavu |2 |

## <a name="userconfiguration"></a>UserConfiguration

Entita **UserConfigurationProfileDeviceActivity** obsahuje počet uživatelů v úspěšném, čekajícím, neúspěšném nebo chybovém stavu za den. Číslo odráží konfigurační profily Zařízení přiřazené entitě. Pokud se například uživatel nachází v úspěšném stavu pro všechny své přiřazené zásady, posune čítač úspěšných uživatelů pro daný den o jedna nahoru. Pokud má uživatel přiřazené dva profily, jeden je v úspěšném stavu a druhý je v chybovém stavu, počítáme uživatele v chybovém stavu.  Entita **UserConfigurationProfileDeviceActivity** uvádí, kolik uživatelů je v jakém stavu v daném dni za posledních 30 dní.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| DateKey |Klíč data, kdy se přihlášení konfiguračního profilu zařízení v datovém skladu zaznamenalo |20160703 |
| Čeká |Počet jedinečných uživatelů v čekajícím stavu |123 |
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
| Čeká |Počet jedinečných zařízení v čekajícím stavu |123 |
| Úspěšné |Počet jedinečných zařízení v úspěšném stavu |12 |
| Chyba |Počet jedinečných zařízení v chybovém stavu |10 |
| Neúspěch – |Počet jedinečných zařízení v neúspěšném stavu |2 |