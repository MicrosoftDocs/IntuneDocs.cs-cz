---
title: "Přidružení zařízení uživatelů – Datový sklad Intune | Dokumentace Microsoftu"
description: "Seznam změn v rozhraní API datového skladu Intune"
keywords: "Datový sklad Intune"
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 095395be4c86780ad65ba1e24b856f6eef8d41ae
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2018
---
# <a name="user-device-association"></a>Přidružení zařízení uživatelů

Entita **UserDeviceAssociation** obsahuje přidružení zařízení uživatelů ve vaší organizaci.

| Název               | Popis                                                                                      | Příklad                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Jedinečný identifikátor uživatele v datovém skladu (náhradní klíč)                              | 123                    |
| DeviceKey          | Jedinečný identifikátor zařízení v datovém skladu                                            | 123                    |
| CreatedDateTimeUTC | Datum a čas, kdy bylo přidružení zařízení uživatele vytvořeno. Používá formát UTC.                                | 23.11.2016 12:00:00 |
| IsDeleted          | Udává, že uživatel registraci zařízení zrušil a že přidružení už není aktuální. | True nebo False             |
| EndedDateTimeUTC   | Datum a čas ve standardu UTC, kdy došlo ke změně vlastnosti IsDeleted na hodnotu **True**                                              | 23.06.2017 12:00:00 |
