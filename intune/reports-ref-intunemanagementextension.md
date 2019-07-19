---
title: Entita IntuneManagementExtension
titleSuffix: Microsoft Intune
description: Téma referenčních informací ke kategorii Entita IntuneManagementExtension pro kolekce entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/08/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 70802626c79f11748e81c39afdd8bc8c5d0622b3
ms.sourcegitcommit: c3ac858bbadb63d248ed54069e48160d703bbaf2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/18/2019
ms.locfileid: "68313776"
---
# <a name="reference-for-intune-management-extensions"></a>Referenční informace o rozšířeních pro správu Intune

Kategorie **intuneManagementExtensions** obsahuje entity pro mobilní zařízení, které sledují informace, jako například:

- Verze IntuneManagementExtension
- Stav instalace IntuneManagementExtension

## <a name="intunemanagementextensionversions"></a>intuneManagementExtensionVersions

Entita **intuneManagementExtensionVersion** obsahuje všechny verze, které používá intuneManagementExtensions.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| ExtensionVersionKey |Jedinečný identifikátor verze intuneManagementExtensions | 1 |
| ExtensionVersion |Číslo verze tvořené 4 číslicemi |1.0.2.0 |

## <a name="intunemanagementextensionhealthstates"></a>intuneManagementExtensionHealthStates

**IntuneManagementExtensionHealthState** obsahuje seznam všech možných stavů intuneManagementExtensions.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| ExtensionStateKey |Jedinečný identifikátor stavu | 2 |
| ExtensionState |Stav IntuneManagementExtension | V pořádku |

## <a name="intunemanagementextensions"></a>intuneManagementExtensions

**IntuneManagementExtension** uvádí stav IntuneManagementExtensions na každém zařízení s Windows 10 za den.
Uchovávají se data za posledních 60 dní. 


|      Vlastnost       |                         Popis                         | Příklad |
|---------------------|-------------------------------------------------------------|---------|
|       dateKey       |               Jedinečný identifikátor data                |   123   |
|      TenantKey      |              Jedinečný identifikátor tenanta               |   456   |
|      DeviceKey      |              Jedinečný identifikátor zařízení               |   789   |
| ExtensionVersionKey | Jedinečný identifikátor verze intuneManagementExtension |    1    |
|  ExtensionStateKey  |             Jedinečný identifikátor stavu              |    2    |

