---
title: "Speciální aspekty migrace | Dokumentace Microsoftu"
description: "Cílem tohoto článku je seznámit zákazníky s určitými aspekty migrace, na které je potřeba pamatovat před zahájením kampaně migrace."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 634e84312fa1a93eb85bf70e1593ca11359b72ff
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-special-migration-considerations"></a>Fáze 1: Speciální aspekty migrace

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

V závislosti na prostředí vašeho stávajícího poskytovatele MDM se vás můžou týkat některé speciální aspekty migrace.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Obnovení továrního nastavení pro Program registrace zařízení Apple (DEP)

Program registrace zařízení Apple (DEP) nastaví konfiguraci zařízení, kterou koncový uživatel nebude moct odebrat. Pokud chcete zachovat pokročilé funkce správy DEP, je potřeba vrátit zařízení do výchozího stavu prostřednictvím obnovení továrního nastavení a pak ho registrovat do Intune.

Pokud chcete dál spravovat zařízení v Intune prostřednictvím programu DEP:

1.  Nasazení [DEP do Intune](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)

2.  Přejděte do svého účtu Apple DEP a [změňte přiřazení sériových čísel zařízení DEP](https://help.apple.com/deployment/business/#/tesf9562af26) ze stávajícího poskytovatele MDM na Intune.

3.  [Synchronizace](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) účtu DEP s Intune

4.  [Vytvořte a přiřaďte](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) příslušné profily registrace DEP k sériovým číslům v Intune.

5.  Obnovte tovární nastavení zařízení (buď vzdáleně prostřednictvím stávajícího poskytovatele MDM, nebo ručně na každém zařízení zvlášť).

6.  Distribuujte zařízení koncovým uživatelům.

## <a name="next-steps"></a>Další kroky 

[Fáze 2: Kampaň migrace](https://docs.microsoft.com/intune/plan-design/migration-phase2-migration-campaign)

