---
title: "Zvláštní stránky migrace"
description: "Tento článek obsahuje speciální informace o tom, co je nutné vzít v úvahu v oblasti migrace, než zahájíte kampaň migrace."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 7ff1180275fddc7f0d6ef957c4680d7c34ad471e
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2017
---
# <a name="special-migration-considerations"></a>Zvláštní stránky migrace

V závislosti na prostředí vašeho stávajícího poskytovatele MDM se vás můžou týkat některé speciální aspekty migrace.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Obnovení továrního nastavení pro Program registrace zařízení Apple (DEP)

Program registrace zařízení Apple (DEP) nastaví konfiguraci zařízení, kterou koncový uživatel nebude moct odebrat. Pokud chcete zachovat pokročilé funkce správy DEP, je potřeba vrátit zařízení do výchozího stavu prostřednictvím obnovení továrního nastavení a pak ho zaregistrovat do Intune.

Pokud chcete ke správě zařízení v Intune dále používat program DEP, [nastavte registraci zařízení s iOSem pomocí programu DEP](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Další kroky

[Fáze 2: Kampaň migrace](migration-guide-campaign.md)
