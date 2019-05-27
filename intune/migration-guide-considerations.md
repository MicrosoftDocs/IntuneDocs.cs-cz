---
title: Zvláštní stránky migrace
titleSuffix: Microsoft Intune
description: Tento článek obsahuje informace o zvláštních aspektech migrace, které je nutné vzít v úvahu, než zahájíte kampaň migrace do Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6f700a93c9640381e33b4b1d1fd442f9442acbe1
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66050526"
---
# <a name="special-migration-considerations"></a>Zvláštní stránky migrace

V závislosti na prostředí vašeho stávajícího poskytovatele MDM se vás můžou týkat některé speciální aspekty migrace.

## <a name="wipe-for-apples-device-enrollment-program-dep"></a>Vymazání pro Program registrace zařízení (DEP) společnosti Apple

Program registrace zařízení Apple (DEP) nastaví konfiguraci zařízení, kterou koncový uživatel nebude moct odebrat. Pokud chcete zachovat pokročilé funkce správy DEP, je potřeba vrátit zařízení do výchozího stavu prostřednictvím vymazání a pak ho zaregistrovat do Intune.

Pokud chcete ke správě zařízení v Intune dále používat program DEP, [nastavte registraci zařízení s iOSem pomocí programu DEP](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Další postup

[Fáze 2: Kampaň migrace](migration-guide-campaign.md)
