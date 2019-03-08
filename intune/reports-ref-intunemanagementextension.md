---
title: Entita IntuneManagementExtension
titlesuffix: Microsoft Intune
description: Téma referenčních informací ke kategorii Entita IntuneManagementExtension pro kolekce entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: d1cd36cba007b465d2100000c484ab6ef5eed2dd
ms.sourcegitcommit: 9a4c5b6c2ce511edaeace25426a23f180cb71e15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/07/2019
ms.locfileid: "57565719"
---
# <a name="reference-for-intune-management-extension"></a>Referenční informace k rozšíření správy Intune

Kategorie **IntuneManagementExtension** obsahuje entity pro mobilní zařízení, které sledují informace, například:

  -  Verze IntuneManagementExtension
  -  Stav instalace IntuneManagementExtension

## <a name="intunemanagementextensionversion"></a>IntuneManagementExtensionVersion

Entita **IntuneManagementExtensionVersion** uvádí seznam všech verzí, které IntuneManagementExtension používá.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| ExtensionVersionKey |Jedinečný identifikátor verze IntuneManagementExtension | 1 |
| ExtensionVersion |Číslo verze tvořené 4 číslicemi |1.0.2.0 |

## <a name="intunemanagementextensionhealthstate"></a>IntuneManagementExtensionHealthState

**IntuneManagementExtensionHealthState** uvádí seznam všech možných stavů IntuneManagementExtension.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| ExtensionStateKey |Jedinečný identifikátor stavu | 2 |
| ExtensionState |Stav IntuneManagementExtension | V pořádku |

## <a name="intunemanagementextension"></a>IntuneManagementExtension

**IntuneManagementExtension** uvádí seznam stavů IntuneManagementExtension na jednotlivých zařízeních s Windows 10 za den.
Uchovávají se data za posledních 60 dní. 


|      Vlastnost       |                         Popis                         | Příklad |
|---------------------|-------------------------------------------------------------|---------|
|       DateKey       |               Jedinečný identifikátor data                |   123   |
|      TenantKey      |              Jedinečný identifikátor tenanta               |   456   |
|      DeviceKey      |              Jedinečný identifikátor zařízení               |   789   |
| ExtensionVersionKey | Jedinečný identifikátor verze IntuneManagementExtension |    1    |
|  ExtensionStateKey  |             Jedinečný identifikátor stavu              |    2    |

