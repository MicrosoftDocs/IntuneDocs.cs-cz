---
title: "Přidružení zařízení uživatelů| Dokumentace Microsoftu"
description: "Referenční téma pro kategorii Přidružení zařízení uživatelů v kolekci entit v rozhraní API datového skladu Intune"
keywords: "Datový sklad Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: BCDBABCB-A7B1-42F2-BDD1-D055E33F2239
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 490e29f87c65875a385472e6abe9400363383f9b
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/20/2017
---
# <a name="reference-for-user-device-association-entity"></a>Referenční informace o entitě Přidružení zařízení uživatelů

Kategorie **Přidružení zařízení uživatelů** obsahuje entitu **Přidružení zařízení uživatelů** používanou k definování přidružení zařízení v organizaci.

**Přidružení zařízení uživatelů**

Entita **Přidružení zařízení uživatelů** představuje definovaná přidružení zařízení v organizaci.

| Název               | Popis                                                                                      | Příklad                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Jedinečný identifikátor uživatele v datovém skladu – náhradní klíč                             | 123                    |
| DeviceKey          | Jedinečný identifikátor zařízení v datovém skladu                                           | 123                    |
| CreatedDateTimeUTC | Datum a čas ve standardu UTC, kdy bylo přidružení zařízení uživatele vytvořeno                               | 23.11.2016 12:00:00 |
| IsDeleted          | Udává, že uživatel registraci zařízení zrušil a že přidružení už není aktuální. | True (Pravda)                   |
| EndedDateTimeUTC   | Datum a čas ve standardu UTC, kdy došlo ke změně vlastnosti IsDeleted na hodnotu **True**                                         | 23.06.2017 12:00:00 |