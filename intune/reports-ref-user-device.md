---
title: Přidružení zařízení uživatelů – Datový sklad Intune
titlesuffix: Microsoft Intune
description: Seznam změn v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bd06c4d42de0c4f64ec0c0cfa61d8aa44af7ab95
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="user-device-association"></a>Přidružení zařízení uživatelů

Entita **UserDeviceAssociation** obsahuje přidružení zařízení uživatelů ve vaší organizaci.


|        Název        |                                           Popis                                            |        Příklad         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      UserKey       |              Jedinečný identifikátor uživatele v datovém skladu (náhradní klíč)               |          123           |
|     DeviceKey      |                      Jedinečný identifikátor zařízení v datovém skladu                      |          123           |
| CreatedDateTimeUTC |           Datum a čas, kdy bylo přidružení zařízení uživatele vytvořeno. Používá formát UTC.           | 23.11.2016 12:00:00 |
|     IsDeleted      | Udává, že uživatel registraci zařízení zrušil a že přidružení už není aktuální. |       True nebo False       |
|  EndedDateTimeUTC  |              Datum a čas ve standardu UTC, kdy došlo ke změně vlastnosti IsDeleted na hodnotu <strong>True</strong>               | 23.06.2017 12:00:00 |

