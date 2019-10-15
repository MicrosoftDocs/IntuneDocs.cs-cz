---
title: Ukládání a zpracování dat v Intune
titleSuffix: Microsoft Intune
description: Zjistěte, jak jsou osobní údaje uložené a zpracovávané v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: edb07842-6a16-482e-8c1d-541a29e169a8
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9c9a8bd5888ab0977d1ca553d059c1e96cccda75
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306883"
---
# <a name="data-storage-and-processing-in-intune"></a>Ukládání a zpracování dat v Intune

Jakmile Intune [shromáždí data](privacy-data-collect.md), úložiště a zpracování těchto dat pokračuje podle níže uvedených pokynů.

## <a name="storing-personal-data"></a>Ukládání osobních údajů

Všechna shromážděná data bez telemetrie se zpracovávají prostřednictvím služby Intune a ukládají se v jednom nebo několika následujících umístěních úložiště: 

- SQLAzure 
- Spolehlivé kolekce (Service Fabric)  
- Úložiště Azure 

Telemetrie (protokoly služeb, protokoly výkonu, chyby atd.), které jsou klíčem k monitorování a poskytování stabilní služby se odesílají do úložišť dat telemetrie Microsoftu.

### <a name="storage-locations"></a>Umístění úložiště

Microsoft nabízí a provozuje služby Intune v mnoha oblastech po celém světě. Intune respektuje volby umístění úložiště provedené správcem zákaznických dat.

Další informace najdete v tématu [kde se nacházejí vaše data?](https://www.microsoft.com/trust-center/privacy/data-location)

### <a name="personal-data-retention"></a>Uchovávání osobních údajů

Obecně platí, že Intune uchovává osobní údaje až po dobu 30 dnů od odebrání uživatele ze správy Intune.

Data telemetrie shromážděná jako součást využití Intune se uchovávají po dobu maximálně 30 dnů.

Protokoly auditu se uchovávají až po dobu jednoho roku.

## <a name="processing-personal-data"></a>Zpracování osobních údajů

Intune zpracovává osobní údaje s certifikovanými systémy ISO. Další informace najdete na [portálu vztahu důvěryhodnosti služby](https://www.microsoft.com/en-us/TrustCenter/stp).

### <a name="profiling-and-marketing"></a>Profilace a marketing

Microsoft Intune nepoužívá žádné osobní údaje shromážděné jako součást poskytování služby pro profilaci nebo marketingové účely. 

### <a name="restrict-processing-of-personal-data"></a>Omezení zpracování osobních údajů

Chcete-li omezit zpracování osobních údajů uživatele, můžete účet uživatele odstranit pomocí:
1. Export elektronické kopie osobních údajů uživatele, včetně
    - accounts
    - data služby
    - přidružené protokoly
2. Odstraňuje se účet uživatele a přidružená data z Intune.

## <a name="next-steps"></a>Další kroky

Přečtěte si další informace o tom, jak Intune [zabezpečuje a sdílí](privacy-data-secure-share.md) osobní údaje. 
