---
title: Zvláštní stránky migrace
titlesuffix: Microsoft Intune
description: Tento článek obsahuje informace o zvláštních aspektech migrace, které je nutné vzít v úvahu, než zahájíte kampaň migrace do Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 23619048faca4cdf9d64b15b0db7c09cb958a082
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2018
ms.locfileid: "43314036"
---
# <a name="special-migration-considerations"></a>Zvláštní stránky migrace

V závislosti na prostředí vašeho stávajícího poskytovatele MDM se vás můžou týkat některé speciální aspekty migrace.

## <a name="wipe-for-apples-device-enrollment-program-dep"></a>Vymazání pro Program registrace zařízení (DEP) společnosti Apple

Program registrace zařízení Apple (DEP) nastaví konfiguraci zařízení, kterou koncový uživatel nebude moct odebrat. Pokud chcete zachovat pokročilé funkce správy DEP, je potřeba vrátit zařízení do výchozího stavu prostřednictvím vymazání a pak ho zaregistrovat do Intune.

Pokud chcete ke správě zařízení v Intune dále používat program DEP, [nastavte registraci zařízení s iOSem pomocí programu DEP](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Další kroky

[Fáze 2: Kampaň migrace](migration-guide-campaign.md)
