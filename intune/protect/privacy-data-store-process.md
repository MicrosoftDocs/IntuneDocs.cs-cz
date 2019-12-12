---
title: Ukládání a zpracovávání údajů v Intune
titleSuffix: Microsoft Intune
description: Přečtěte si informace o ukládání a zpracovávání osobních údajů v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: edb07842-6a16-482e-8c1d-541a29e169a8
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 07a9232203c7d93eb1b9e81b962d2369e77b7421
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/05/2019
ms.locfileid: "72509047"
---
# <a name="data-storage-and-processing-in-intune"></a>Ukládání a zpracovávání údajů v Intune

Jakmile Intune [shromáždí údaje](privacy-data-collect.md), následuje jejich uložení a zpracování popsané níže.

## <a name="storing-personal-data"></a>Ukládání osobních údajů

Veškeré shromážděné údaje, které nepatří mezi telemetrická data, se zpracovávají prostřednictvím služby Intune a ukládají nejméně v jednom z následujících umístění: 

- SQLAzure 
- Spolehlivé kolekce (Service Fabric)  
- Azure Storage 

Telemetrická data (protokoly služby, protokoly výkonu, chyby atd.) nezbytná pro monitorování a poskytování stabilní služby se odesílají do úložišť telemetrických dat Microsoftu.

### <a name="storage-locations"></a>Umístění úložišť

Microsoft nabízí a provozuje služby Intune v mnoha oblastech po celém světe. Intune respektuje volbu umístění úložiště pro zákaznická data provedenou správcem.

Další informace najdete v tématu [kde se nacházejí vaše data?](https://www.microsoft.com/trust-center/privacy/data-location)

### <a name="personal-data-retention"></a>Uchovávání osobních údajů

Obecně platí, že Intune uchovává osobní údaje až po dobu 30 dnů od odebrání uživatele ze správy Intune.

Data telemetrie shromážděná jako součást využití Intune se uchovávají po dobu maximálně 30 dnů.

Protokoly auditů se uchovávají až jeden rok.

## <a name="processing-personal-data"></a>Zpracovávání osobních údajů

Intune zpracovává osobní údaje pomocí systémů s certifikací ISO. Další informace najdete na portálu [Service Trust Portal](https://www.microsoft.com/en-us/TrustCenter/stp).

### <a name="profiling-and-marketing"></a>Profilace a marketing

Žádné osobní údaje shromážděné v rámci poskytování služeb nejsou službou Microsoft Intune využívány k profilování ani marketingovým účelům. 

### <a name="restrict-processing-of-personal-data"></a>Omezení zpracování osobních údajů

Pokud chcete omezit zpracovávání osobních údajů uživatele, můžete jeho uživatelský účet odstranit takto:
1. Export elektronické kopie osobních údajů uživatele, jejíž součástí jsou také:
    - Účty
    - Data služby
    - Přidružené protokoly
2. Odstranění uživatelského účtu a přidružených dat z Intune.

## <a name="next-steps"></a>Další kroky

Přečtěte si další informace o tom, jak služba Intune [zabezpečuje a sdílí](privacy-data-secure-share.md) osobní údaje. 
