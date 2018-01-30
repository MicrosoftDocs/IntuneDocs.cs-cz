---
title: "Zvláštní stránky migrace"
description: "Tento článek obsahuje speciální informace o tom, co je nutné vzít v úvahu v oblasti migrace, než zahájíte kampaň migrace."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 86f3f7f2c8066e1b7b50dfc5931184c394d4f15b
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="special-migration-considerations"></a>Zvláštní stránky migrace

V závislosti na prostředí vašeho stávajícího poskytovatele MDM se vás můžou týkat některé speciální aspekty migrace.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Obnovení továrního nastavení pro Program registrace zařízení Apple (DEP)

Program registrace zařízení Apple (DEP) nastaví konfiguraci zařízení, kterou koncový uživatel nebude moct odebrat. Pokud chcete zachovat pokročilé funkce správy DEP, je potřeba vrátit zařízení do výchozího stavu prostřednictvím obnovení továrního nastavení a pak ho zaregistrovat do Intune.

Pokud chcete ke správě zařízení v Intune dále používat program DEP, [nastavte registraci zařízení s iOSem pomocí programu DEP](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Další kroky

[Fáze 2: Kampaň migrace](migration-guide-campaign.md)
