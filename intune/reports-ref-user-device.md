---
title: Přidružení zařízení uživatelů – Datový sklad Intune
titleSuffix: Microsoft Intune
description: UserDeviceAssociation entitě přidružení zařízení uživatelů ve vaší organizaci.
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/14/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 466066faf03cbdf560697a04310eac844d4f1b87
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798256"
---
# <a name="reference-for-user-device-association-entity"></a>Referenční informace o entitě Přidružení zařízení uživatelů

Entita **UserDeviceAssociation** obsahuje přidružení zařízení uživatelů ve vaší organizaci.

## <a name="userdeviceassociation"></a>UserDeviceAssociation


|        Name        |                                           Popis                                            |        Příklad         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      UserKey       |              Jedinečný identifikátor uživatele v datovém skladu (náhradní klíč)               |          123           |
|     DeviceKey      |                      Jedinečný identifikátor zařízení v datovém skladu                      |          123           |
| CreatedDateTimeUTC |           Datum a čas, kdy bylo přidružení zařízení uživatele vytvořeno. Používá formát UTC.           | 23.11.2016 12:00:00 |
|     IsDeleted      | Udává, že uživatel registraci zařízení zrušil a že přidružení už není aktuální. |       True nebo False       |
|  EndedDateTimeUTC  |              Datum a čas ve standardu UTC, kdy došlo ke změně vlastnosti IsDeleted na hodnotu <strong>True</strong>               | 23.06.2017 12:00:00 |

## <a name="next-steps"></a>Další postup

- Další informace o [datový sklad Intune](reports-nav-create-intune-reports.md).
