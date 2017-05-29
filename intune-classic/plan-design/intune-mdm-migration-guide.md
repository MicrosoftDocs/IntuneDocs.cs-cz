---
title: "Průvodce migrací správy mobilních zařízení Intune (MDM) | Dokumentace Microsoftu"
description: "Účelem tohoto průvodce je seznámit zákazníky s různými aspekty migrace od jiného poskytovatele MDM k Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: cce6d997c1aad73819b8cfcf31a1505f0ce75923
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="intune-migration-guide"></a>Příručka k migraci do Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

![Příručka k migraci do Intune MDM – schéma](../media/MDM-migration-guide-art.PNG)

Úspěšná migrace do Intune začíná vypracováním promyšleného plánu, který zohledňuje aktuální prostředí MDM, obchodní cíle a technické požadavky. Kromě toho je potřeba vybrat klíčové účastníky, kteří vám pomůžou plán migrace zrealizovat.

Účelem tohoto průvodce je seznámit vás s různými aspekty migrace od jiného poskytovatele MDM k Intune.

## <a name="whats-included-in-this-guide"></a>Obsah příručky

Tato příručka obsahuje dvě fáze zahrnující úkoly, strategie a taktické pokyny, které vám pomůžou projít celým procesem migrace do Intune MDM.

-   [Fáze 1: Příprava služby Intune na správu mobilních zařízení] (/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

    -   [Vyhodnocení požadavků na migraci MDM](/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements)

    -   [Základní nastavení](/intune-classic/plan-design/migration-phase1-basic-setup)

    -   [Konfigurace zásad pro správu zařízení a aplikací](/intune-classic/plan-design/migration-phase1-configure-device-and-app-management-policies)

    -   [Konfigurace zásad ochrany aplikací] (/intune-classic/plan-design/migration-phase1-configure-app-protection-policies)

    -   [Speciální aspekty migrace](/intune-classic/plan-design/migration-phase1-special-migration-considerations)

-   [Fáze 2: Kampaň migrace](/intune-classic/plan-design/migration-phase2-migration-campaign)

    -   [Plán komunikace](/intune-classic/plan-design/migration-phase2-communication-plan)

    -   [Podpora přijetí koncovými uživateli pomocí podmíněného přístupu](/intune-classic/plan-design/migration-phase2-drive-end-user-adoption-with-conditional-access)
    
    -   [Typický cyklus migrace](/intune-classic/plan-design/migration-phase2-typical-migration-cycle)
        -   [Monitorování migrace](/intune-classic/plan-design/migration-phase2-typical-migration-cycle#monitoring-migration)
        -   [Po dokončení migrace](/intune-classic/plan-design/migration-phase2-typical-migration-cycle#post-migration)

## <a name="assumptions"></a>Předpoklady

-   Službu Intune jste už vyhodnotili v prostředí testování konceptu a rozhodli jste se použít ji jako řešení MDM ve vaší organizaci.

-   Intune a její funkce už znáte. 

> [!NOTE]
> Pokud chcete Intune poznat více do hloubky ještě před zahájením migrace, podívejte se do [Příručky pro testování Intune](/intune-classic/understand-explore/sign-up-for-30-day-trial-microsoft-intune).

## <a name="before-you-begin"></a>Před zahájením

Je důležité uvědomit si, že nové nasazení Intune se může lišit od předchozího nasazení MDM. Na rozdíl od tradičních služeb MDM používá Intune řízení přístupu na základě identity, takže řízení přístupu k firemním datům z mobilních zařízení nacházejících se mimo síť organizace nevyžaduje síťová proxy zařízení. Společnost Microsoft nabízí řešení pro zabezpečení dat přímo v cloudu prostřednictvím úzce integrovaných cloudových služeb, které se souhrnně označují jako Enterprise Client + Security.

-   Projděte si [běžné způsoby použití Intune](/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements).

## <a name="next-steps"></a>Další kroky

[Fáze 1: Příprava Intune na správu mobilních zařízení] (/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

