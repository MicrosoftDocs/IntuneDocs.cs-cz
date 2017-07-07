---
title: "Zvláštní stránky migrace"
description: "Cílem tohoto článku je seznámit zákazníky s určitými aspekty migrace, na které je potřeba pamatovat před zahájením kampaně migrace."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bc39ffd3a4f11a4c2b32f75dc5befcd8ce42f43e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="special-migration-considerations"></a>Zvláštní stránky migrace

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

V závislosti na prostředí vašeho stávajícího poskytovatele MDM se vás můžou týkat některé speciální aspekty migrace.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Obnovení továrního nastavení pro Program registrace zařízení Apple (DEP)

Program registrace zařízení Apple (DEP) nastaví konfiguraci zařízení, kterou koncový uživatel nebude moct odebrat. Pokud chcete zachovat pokročilé funkce správy DEP, je potřeba vrátit zařízení do výchozího stavu prostřednictvím obnovení továrního nastavení a pak ho registrovat do Intune.

Pokud chcete ke správě zařízení v Intune dále používat program DEP, [nastavte registraci zařízení s iOSem pomocí programu DEP](/intune/device-enrollment-program-enroll-ios).


## <a name="next-steps"></a>Další kroky 

[Fáze 2: Kampaň migrace](migration-guide-campaign.md)
