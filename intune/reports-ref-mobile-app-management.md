---
title: Správa mobilních aplikací (MAM)
titlesuffix: Microsoft Intune
description: Téma referenčních informací ke kategorii Správa mobilních aplikací pro kolekce entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/05/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 084F11AD-F7BA-45A4-8424-45E6E4564930
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7ea3e2c87055e4f111c8f12c47c468dff2c4e587
ms.sourcegitcommit: 9a4c5b6c2ce511edaeace25426a23f180cb71e15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/07/2019
ms.locfileid: "57565685"
---
# <a name="reference-for-mobile-app-management-mam-entities"></a>Referenční informace o entitách správy mobilních aplikací (MAM)

Kategorie **Správa mobilních aplikací** obsahuje entity pro mobilní aplikace, například:

  -  Aplikace
  -  instancí
  -  Stav přihlášení
  -  Stav
  -  Stav zásad
  -  Stav zápisu
  -  Typy platformy

## <a name="mamapplication"></a>MamApplication

Entita **MamApplication** obsahuje seznam obchodních aplikací, které jsou spravované přes správu mobilních aplikací (MAM) bez registrace ve vašem podniku.

| Vlastnost | Popis | Příklad |
|---------|------------|--------|
| ApplicationKey |Jedinečný identifikátor aplikace MAM v datovém skladu |123 |
| ApplicationName |Název aplikace MAM |Word |
| ApplicationId |ID aplikace pro danou aplikaci MAM |b66bc706-ffff-7437-0340-032819502773 |
| IsDeleted |Určuje, jestli je tento záznam aplikace MAM aktualizovaný. <br>True – aplikace MAM má v této tabulce nový záznam s aktualizovanými poli. <br>False – jedná se o nejnovější záznam pro tuto aplikaci MAM. |True nebo False |
| StartDateInclusiveUTC |Datum a čas ve standardu UTC, kdy se tato aplikace MAM v datovém skladu vytvořila |23.11.2016 12:00:00 |
| DeletedDateUTC |Datum a čas ve standardu UTC, kdy došlo ke změně vlastnosti IsDeleted na hodnotu True |23.11.2016 12:00:00 |
| RowLastModifiedDateTimeUTC |Datum a čas ve standardu UTC, kdy se tato aplikace MAM v datovém skladu naposledy změnila |23.11.2016 12:00:00 |

## <a name="mamapplicationinstance"></a>MamApplicationInstance

Entita **MamApplicationInstance** obsahuje seznam aplikací spravovaných přes správu mobilních aplikací (MAM) jako jedinečné instance pro uživatele a zařízení. Všichni uživatelé a zařízení, kteří jsou v této entitě uvedení, jsou chránění, protože mají přiřazenou aspoň jednu zásadu MAM.


|          Vlastnost          |                                                                                                  Popis                                                                                                  |               Příklad                |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
|   ApplicationInstanceKey   |                                                               Jedinečný identifikátor instance aplikace MAM v datovém skladu – náhradní klíč                                                                |                 123                  |
|           UserId           |                                                                              ID uživatele, který má tuto aplikaci MAM nainstalovanou                                                                              | b66bc706-ffff-7437-0340-032819502773 |
|   ApplicationInstanceId    |                                              Jedinečný identifikátor instance aplikace MAM – podobá se vlastnosti ApplicationInstanceKey, ale tento identifikátor představuje přirozený klíč.                                              | b66bc706-ffff-7437-0340-032819502773 |
|       ApplicationId        |                                                                                        ID aplikace pro danou aplikaci MAM                                                                                         |  com.microsoft.groupies-daily.<IOS>  |
|     ApplicationVersion     |                                                                                     Verze aplikace pro danou aplikaci MAM                                                                                      |                  2                   |
|        CreatedDate         |                                                                 Datum vytvoření daného záznamu instance aplikace MAM Hodnota může být null.                                                                 |        23.11.2016 12:00:00        |
|          Platforma          |                                                                          Platforma zařízení, na kterém je daná aplikace MAM nainstalovaná                                                                           |                  2                   |
|      PlatformVersion       |                                                                      Verze platformy zařízení, na kterém je daná aplikace MAM nainstalovaná                                                                       |                 2.2                  |
|         SdkVersion         |                                                                            Verze sady SDK MAM, pomocí které byla daná aplikace MAM zabalena                                                                            |                 3.2                  |
|          DeviceId          |                                                                          ID zařízení, na kterém je daná aplikace MAM nainstalovaná                                                                          | b66bc706-ffff-7437-0340-032819502773 |
|         Název zařízení         |                                                                         Název zařízení, na kterém je daná aplikace MAM nainstalovaná                                                                         |              MojeZařízení              |
|         IsDeleted          | Určuje, jestli je tento záznam instance aplikace MAM aktualizovaný. <br>True – tato instance aplikace MAM má v této tabulce nový záznam s aktualizovanými poli. <br>False – jedná se o nejnovější záznam pro tuto instanci aplikace MAM. |              True nebo False              |
|   StartDateInclusiveUtc    |                                                              Datum a čas ve standardu UTC, kdy se tato instance aplikace MAM v datovém skladu vytvořila                                                               |        23.11.2016 12:00:00        |
|       DeletedDateUtc       |                                                                             Datum a čas ve standardu UTC, kdy došlo ke změně vlastnosti IsDeleted na hodnotu True                                                                              |        23.11.2016 12:00:00        |
| RowLastModifiedDateTimeUtc |                                                           Datum a čas ve standardu UTC, kdy se tato instance aplikace MAM v datovém skladu naposledy změnila                                                            |        23.11.2016 12:00:00        |

## <a name="mamcheckin"></a>MamCheckin

Entita **MamCheckin** představuje data shromážděná v době, kdy se instance aplikace MAM přihlásila ke službě Intune. 

> [!Note]  
> Pokud se instance aplikace přihlásí několikrát denně, uloží se to v datovém skladu jako jediné přihlášení.

| Vlastnost | Popis | Příklad |
|---------|------------|--------|
| DateKey |Klíč data, kdy se přihlášení aplikace MAM v datovém skladu zaznamenalo | 20160703 |
| ApplicationInstanceKey |Klíč instance aplikace, který je k tomuto přihlášení aplikace MAM přidružený | 123 |
| UserKey |Klíč uživatele, který je k tomuto přihlášení aplikace MAM přidružený | 4323 |
| ApplicationKey |Klíč aplikace MAM, která se přihlásila |234 |
| DeviceHealthKey |Klíč pro stav, který je k tomuto přihlášení aplikace MAM přidružený | 321 |
| PlatformKey |Představuje platformu zařízení, které je k tomuto přihlášení aplikace MAM přidružené |123 |
| EffectiveAppliedPolicyKey |Představuje platné použité zásady, které jsou k tomuto přihlášení aplikace MAM přidružené. Platné použité zásady jsou výsledkem sloučení všech zásad, které jsou pro konkrétní aplikaci a uživatele relevantní. | 322 |
| LastCheckInDate |Datum a čas posledního přihlášení dané aplikace MAM Hodnota může být null. |23.11.2016 12:00:00 |

## <a name="mamdevicehealth"></a>MamDeviceHealth

Entita **MamDeviceHealth** představuje zařízení, na kterých jsou nasazené zásady správy mobilních aplikací (MAM), i když jsou tato zařízení s jailbreakem.

| Vlastnost | Popis | Příklad |
|---------|------------|--------|
| DeviceHealthKey |Jedinečný identifikátor zařízení a jeho přidruženého stavu v datovém skladu – náhradní klíč |123 |
| DeviceHealth |Jedinečný identifikátor zařízení a jeho přidruženého stavu – podobá se vlastnosti DeviceHealthKey, ale tento identifikátor představuje přirozený klíč. |b66bc706-ffff-7777-0340-032819502773 |
| DeviceHealthName |Představuje stav zařízení. <br>Není k dispozici – žádné informace o tomto zařízení nejsou dostupné. <br>V pořádku – nejedná se o zařízení s jailbreakem. <br>Není v pořádku – jedná se o zařízení s jailbreakem. |Není k dispozici, V pořádku, Není v pořádku |
| RowLastModifiedDateTimeUtc |Datum a čas ve standardu UTC, kdy se tento konkrétní stav zařízení MAM v datovém skladu naposledy změnil |23.11.2016 12:00:00 |

## <a name="mameffectivepolicy"></a>MamEffectivePolicy

Entita **MamEffectivePolicy** obsahuje seznam všech platných použitých zásad správy mobilních aplikací (MAM) ve vaší organizaci. Platné použité zásady jsou výsledkem sloučení všech zásad, které jsou pro konkrétní aplikaci a uživatele relevantní.

| Vlastnost | Popis | Příklad |
|---------|------------|--------|
| EffectivePolicyKey |Jedinečný identifikátor platných zásad MAM v datovém skladu |2 |
| RealPolicyKey |Jedinečný identifikátor zásad MAM, které vytvořil pracovník oddělení IT |1 |
| RowCreatedDateTimeUtc |Datum a čas ve standardu UTC, kdy se tyto platné zásady MAM v datovém skladu vytvořily |23.11.2016 12:00:00 |

## <a name="mamglobalapplication"></a>MamGlobalApplication

Entita **MamGlobalApplication** obsahuje seznam aplikací pro Store, které jsou spravované přes správu mobilních aplikací (MAM) bez registrace ve vašem podniku.


|          Vlastnost          |                                               Popis                                               |           Příklad            |
|----------------------------|---------------------------------------------------------------------------------------------------------|------------------------------|
|       ApplicationKey       |          Jedinečný identifikátor aplikace pro Store v datovém skladu, který se označuje jako náhradní klíč          |             123              |
|       ApplicationId        | Jedinečný identifikátor aplikace pro Store. Tento identifikátor se podobá vlastnosti ApplicationKey, ale představuje přirozený klíč.  | com.microsoft.skydrive.<ios> |
|      ApplicationName       |                                      Název globální aplikace MAM                                       |           SkyDrive           |
| RowLastModifiedDateTimeUtc | Datum a čas ve standardu UTC, kdy se tato konkrétní globální aplikace MAM v datovém skladu naposledy změnila |    23.11.2016 12:00:00    |

## <a name="mamplatform"></a>MamPlatform

Entita **MamPlatform** obsahuje seznam názvů a typů platforem, na kterých byla aplikace MAM nainstalována.


|          Vlastnost          |                                    Popis                                    |                         Příklad                         |
|----------------------------|-----------------------------------------------------------------------------------|---------------------------------------------------------|
|        PlatformKey         |     Jedinečný identifikátor platformy v datovém skladu – náhradní klíč      |                           123                           |
|          Platforma          | Jedinečný identifikátor platformy – podobá se vlastnosti PlatformKey, jedná se ale o přirozený klíč. |                           123                           |
|        PlatformName        |                                   Název platformy                                   | Není k dispozici <br>Žádné <br>Windows <br>iOS <br>Android. |
| RowLastModifiedDateTimeUtc | Datum a čas ve standardu UTC, kdy se tato platforma v datovém skladu naposledy změnila  |                 23.11.2016 12:00:00                  |

