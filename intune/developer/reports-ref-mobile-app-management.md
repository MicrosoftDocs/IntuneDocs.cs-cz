---
title: Správa mobilních aplikací (MAM)
titleSuffix: Microsoft Intune
description: Referenční téma pro kategorii správy mobilní aplikace v kolekcích entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 084F11AD-F7BA-45A4-8424-45E6E4564930
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f06d2b4b61d522dced12e5d08cd1e854aefd9de8
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71939951"
---
# <a name="reference-for-mobile-app-management-mam-entities"></a>Referenční informace o entitách správy mobilních aplikací (MAM)

Kategorie **Správa mobilních aplikací** obsahuje entity pro mobilní aplikace, jako například:

- Můžou
- Instance
- Stav vrácení se změnami
- Stav
- Stav zásad
- Stav registrace
- Typy platforem

## <a name="mamapplications"></a>mamApplications

Entita **mamApplication** obsahuje seznam obchodních aplikací (LOB), které jsou spravované prostřednictvím správy mobilních aplikací (MAM) bez registrace ve vašem podniku.

| Vlastnost | Popis | Příklad |
|---------|------------|--------|
| mamApplicationKey |Jedinečný identifikátor aplikace MAM | 432 |
| mamApplicationName |Název aplikace MAM |Příklad názvu aplikace MAM |
| mamApplicationId |ID aplikace MAM | 123 |
| IsDeleted |Určuje, jestli se tento záznam aplikace MAM aktualizoval. <br>True – aplikace MAM má v této tabulce nový záznam s aktualizovanými poli. <br>False – poslední záznam pro tuto aplikaci MAM |True nebo false |
| StartDateInclusiveUTC |Datum a čas ve standardu UTC, kdy se tato aplikace MAM v datovém skladu vytvořila |11/23/2016 12:00:00 DOP. |
| DeletedDateUTC |Datum a čas ve standardu UTC, kdy došlo ke změně hodnoty IsDeleted na hodnotu true |11/23/2016 12:00:00 DOP. |
| RowLastModifiedDateTimeUTC |Datum a čas ve standardu UTC, kdy se tato aplikace MAM v datovém skladu naposledy změnila |11/23/2016 12:00:00 DOP. |


## <a name="mamapplicationinstances"></a>mamApplicationInstances

Entita **mamApplicationInstance** obsahuje seznam spravovaných aplikací pro správu mobilních aplikací (MAM) jako jednotné instance na uživatele a zařízení. Všichni uživatelé a zařízení v seznamu v entitě jsou chránění, jako v aplikaci mají přiřazenou alespoň jednu MAM zásadu.


|          Vlastnost          |                                                                                                  Popis                                                                                                  |               Příklad                |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
|   Vlastnosti applicationinstancekey   |                                                               Jedinečný identifikátor instance aplikace MAM v datovém skladu – náhradní klíč                                                                |                 123                  |
|           userId           |                                                                              ID uživatele, který má tuto aplikaci MAM nainstalovanou.                                                                              | b66bc706-FFFF-7437-0340-032819502773 |
|   ApplicationInstanceId    |                                              Jedinečný identifikátor instance aplikace MAM – podobně jako vlastnosti applicationinstancekey, ale identifikátor je přirozený klíč.                                              | b66bc706-FFFF-7437-0340-032819502773 |
| mamApplicationId | ID aplikace mam, pro kterou se vytvořila tato instance aplikace mam   | 11/23/2016 12:00:00 DOP.   |
|     applicationVersion     |                                                                                     Verze aplikace této aplikace MAM                                                                                      |                  odst                   |
|        CreatedDate         |                                                                 Datum, kdy se vytvořil tento záznam instance aplikace MAM Hodnota může být null.                                                                 |        11/23/2016 12:00:00 DOP.        |
|          platforma          |                                                                          Platforma zařízení, na které je nainstalovaná Tato aplikace MAM                                                                           |                  odst                   |
|      PlatformVersion       |                                                                      Verze platformy zařízení, na které je nainstalována tato aplikace MAM                                                                       |                 2,2                  |
|         SdkVersion         |                                                                            Verze sady SDK MAM, pomocí které byla tato aplikace MAM zabalena                                                                            |                 3,2                  |
| mamDeviceId | ID zařízení, ke kterému je přidružená instance aplikace MAM   | 11/23/2016 12:00:00 DOP.   |
| mamDeviceType | Typ zařízení, ke kterému je přidružená instance aplikace MAM   | 11/23/2016 12:00:00 DOP.   |
| mamDeviceName | Název zařízení, ke kterému je přidružená instance aplikace MAM   | 11/23/2016 12:00:00 DOP.   |
|         IsDeleted          | Určuje, jestli se tento záznam instance aplikace MAM aktualizoval. <br>True – tato instance aplikace MAM má v této tabulce nový záznam s aktualizovanými poli. <br>False – poslední záznam pro tuto instanci aplikace MAM |              True nebo false              |
|   StartDateInclusiveUtc    |                                                              Datum a čas ve standardu UTC, kdy se tato instance aplikace MAM v datovém skladu vytvořila                                                               |        11/23/2016 12:00:00 DOP.        |
|       DeletedDateUtc       |                                                                             Datum a čas ve standardu UTC, kdy došlo ke změně hodnoty IsDeleted na hodnotu true                                                                              |        11/23/2016 12:00:00 DOP.        |
| RowLastModifiedDateTimeUtc |                                                           Datum a čas ve standardu UTC, kdy se tato instance aplikace MAM v datovém skladu naposledy změnila                                                            |        11/23/2016 12:00:00 DOP.        |


## <a name="mamcheckins"></a>mamCheckins

Entita **mamCheckin** představuje data shromážděná při vrácení instance aplikace správy mobilních aplikací (MAM) ve službě Intune. 

> [!Note]  
> Když se instance aplikace několikrát denně kontroluje, datový sklad je uloží do jediného vrácení se změnami.

| Vlastnost | Popis | Příklad |
|---------|------------|--------|
| DateKey |Klíč data, kdy se vrácení se změnami aplikace MAM v datovém skladu zaznamenalo | 20160703 |
| Vlastnosti applicationinstancekey |Klíč instance aplikace přidružené k tomuto vrácení se změnami aplikace MAM | 123 |
| Vlastnosti UserKey |Klíč uživatele, který je přidružený k tomuto vrácení se změnami aplikace MAM | 4323 |
| mamApplicationKey |Aplikační klíč aplikace přidružený k vrácení aplikace MAM se změnami | 432 |
| Vlastnosti devicehealthkey |Klíč přidružený přidruženého k tomuto vrácení se změnami aplikace MAM | 321 |
| Vlastnosti platformkey |Představuje platformu zařízení přidruženou k tomuto vrácení se změnami aplikace MAM. |123 |
| EffectiveAppliedPolicyKey |Představuje efektivní použité zásady přidružené k aplikaci MAM, která se vrátila se změnami. Efektivní použitá zásada je výsledkem sloučení všech zásad, které jsou relevantní pro konkrétní aplikaci a uživatele. | 322 |
| pastCheckInDate |Datum a čas, kdy se tato aplikace MAM naposledy vrátila Hodnota může být null. |11/23/2016 12:00:00 DOP. |


## <a name="mamdevicehealth"></a>MamDeviceHealth

Entita **mamDeviceHealth** představuje zařízení, která mají nasazené zásady správy mobilních aplikací (MAM), i když mají jailbreak.

| Vlastnost | Popis | Příklad |
|---------|------------|--------|
| Vlastnosti devicehealthkey |Jedinečný identifikátor zařízení a jeho přidruženého stavu v datovém skladu – náhradní klíč |123 |
| Přidružený |Jedinečný identifikátor zařízení a jeho přidruženého stavu, podobně jako vlastnosti devicehealthkey, ale identifikátor je přirozený klíč. |b66bc706-FFFF-7777-0340-032819502773 |
| DeviceHealthName |Představuje stav zařízení. <br>Nedostupné – na tomto zařízení nejsou žádné informace. <br>V pořádku – zařízení není jailbreak. <br>Není v pořádku – zařízení má jailbreak. |Není dostupný stav není v pořádku |
| RowLastModifiedDateTimeUtc |Datum a čas ve standardu UTC, kdy se tato specifická Stav zařízení MAM v datovém skladu naposledy změnila |11/23/2016 12:00:00 DOP. |

## <a name="mameffectivepolicies"></a>mamEffectivePolicies

Entita **mamEffectivePolicy** obsahuje seznam všech efektivních zásad správy mobilních aplikací (MAM) používaných ve vaší organizaci. Efektivní použitá zásada je výsledkem sloučení všech zásad, které jsou relevantní pro konkrétní aplikaci a uživatele.

| Vlastnost | Popis | Příklad |
|---------|------------|--------|
| EffectivePolicyKey |Jedinečný identifikátor platných zásad MAM v datovém skladu. |odst |
| RealPolicyKey |Jedinečný identifikátor zásad MAM, které vytvořil IT specialista |první |
| RowCreatedDateTimeUtc |Datum a čas ve standardu UTC, kdy se v datovém skladu vytvořila tato zásada účinnosti MAM |11/23/2016 12:00:00 DOP. |

## <a name="mamplatforms"></a>mamPlatforms

Entita **mamPlatform** obsahuje seznam názvů a typů platforem, na kterých se nainstalovala aplikace pro správu mobilních aplikací (MAM).


|          Vlastnost          |                                    Popis                                    |                         Příklad                         |
|----------------------------|-----------------------------------------------------------------------------------|---------------------------------------------------------|
|        Vlastnosti platformkey         |     Jedinečný identifikátor platformy v datovém skladu – náhradní klíč      |                           123                           |
|          platforma          | Jedinečný identifikátor platformy podobný vlastnosti platformkey, ale je přirozený klíč. |                           123                           |
|        PlatformName        |                                   Název platformy                                   | Není k dispozici <br>Žádné <br>Windows <br>iOS <br>Svém. |
| RowLastModifiedDateTimeUtc | Datum a čas ve standardu UTC, kdy se tato platforma v datovém skladu naposledy změnila  |                 11/23/2016 12:00:00 DOP.                  |

