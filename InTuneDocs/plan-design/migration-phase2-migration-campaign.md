---
title: "Zahájení kampaně migrace do Intune | Dokumentace Microsoftu"
description: "Tento článek uvádí postup zahájení kampaně migrace."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 506b0360fb7b1f28c4c9ad3265e24c0ffa0b065d
ms.lasthandoff: 03/27/2017


---

# <a name="phase-2-migration-campaign"></a>Fáze 2: Kampaň migrace

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Organizace by si měla zvolit přístup k migraci, který bude nejvíc vyhovovat jejím potřebám, a přizpůsobit taktiku implementace vlastním požadavkům. Zbývající část tohoto průvodce vás seznámí s nástroji, které budete potřebovat k úspěšnému zaregistrování zařízení vašich uživatelů do Intune.

## <a name="keys-to-a-successful-migration"></a>Klíč k úspěšné migraci

Hlavní poučení o migraci od jiných poskytovatelů MDM do Intune:

-   Klíčem ke spokojenosti koncových uživatelů a minimalizaci výpadků je komunikace.

-   Poskytněte uživatelům konkrétní pokyny k migraci.

-   Před registrací do Intune musí být zrušena registrace všech spravovaných zařízení u vašeho stávajícího poskytovatele MDM.

-   Poskytněte koncovým uživatelům pokyny od vašeho stávajícího poskytovatele MDM ke zrušení registrace zařízení.

-   Proveďte migraci v několika fázích. Začněte s malou, zkušební skupinou uživatelů a postupně přidávejte další skupiny uživatelů, dokud nedosáhnete nasazení v plném rozsahu.

-   Monitorujte vytíženost technické podpory a úspěšnost registrace v jednotlivých cyklech. Ponechte si časovou rezervu, abyste mohli vyhodnotit kritéria úspěšnosti migrace každé skupiny, než přejdete k migraci další skupiny. Při pilotním nasazení byste měli zhodnotit následující:

    -   Míra úspěchu a selhání registrací je v rámci očekávání.

    -   Produktivita uživatelů:

        -   Firemní prostředky, například sítě VPN a Wi-Fi, e-mail a certifikáty, jsou funkční.

        -   Uživatelé mají přístup ke zřízeným aplikacím.

    -   Zabezpečení dat:

        -   Generování sestav dodržování předpisů

        -   Vynucení ochrany mobilních aplikací

-   Pokud jste spokojení s první fází migrace, zopakujte cyklus migrace (popsaný níže jako Typický cyklus migrace) pro další fázi.

-   Opakujte cykly migrace, dokud nebudou všichni uživatelé migrovaní do Intune.

-   Zajistěte, aby byl tým technické podpory během kampaně migrace připraven pomoct koncovým uživatelům. Spusťte dobrovolnou migraci, abyste byli schopni odhadnout zátěž telefonních linek technické podpory.

-   Nestanovujte konečný termín registrace, dokud nebude tým technické podpory schopný vyřídit dotazy zbývajících uživatelů.

> [!IMPORTANT] 
> Vyhněte se tomu, abyste konfigurovali použití ovládacích prvků přístupu k prostředkům, jako je Exchange nebo SharePoint Online, současně pro Intune i vaše stávající řešení MDM. Kromě toho by měla být zařízení registrována vždy jen v jednom řešení.

## <a name="next-steps"></a>Další kroky

[Fáze 2: Plán komunikace](https://docs.microsoft.com/intune/plan-design/migration-phase2-communication-plan)

