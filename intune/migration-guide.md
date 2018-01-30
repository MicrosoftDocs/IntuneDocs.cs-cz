---
title: "Průvodce migrací správy mobilních zařízení do Intune"
description: "Tato příručka vás seznámí s různými detaily migrace od jiného poskytovatele MDM do Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 888624530fe77f22ea9391b688fa9f9b92f0ac75
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="intune-migration-guide"></a>Příručka k migraci do Intune

![Příručka k migraci do Intune MDM – schéma](./media/MDM-migration-guide-art.PNG)

Úspěšná migrace do Intune začíná vypracováním promyšleného plánu, který bere v úvahu nejen vaše aktuální prostředí pro správu mobilních zařízení (MDM), ale i obchodní cíle a technické požadavky. Kromě toho je potřeba vybrat klíčové účastníky, kteří vám pomůžou plán migrace zrealizovat.

Tato příručka vás seznámí s různými detaily migrace od jiného poskytovatele MDM do Intune.

## <a name="whats-included-in-this-guide"></a>Obsah příručky

Tato příručka rozděluje migraci na dvě fáze zahrnující úkoly, strategie a taktické pokyny, které vám pomůžou projít celým procesem migrace do Intune MDM.

-   [Fáze 1: Příprava Intune na správu mobilních zařízení](migration-guide-prepare.md)

    -   [Vyhodnocení požadavků na migraci MDM](migration-guide-prepare.md#assess-mdm-requirements)

    -   [Základní nastavení](migration-guide-setup.md)

    -   [Konfigurace zásad pro správu zařízení a aplikací](migration-guide-configure-policies.md)

    -   [Konfigurace zásad pro ochranu aplikací](migration-guide-app-protection-policies.md)

    -   [Speciální aspekty migrace](migration-guide-considerations.md)

-   [Fáze 2: Kampaň migrace](migration-guide-campaign.md)

    -   [Plán komunikace](migration-guide-communication-plan.md)

    -   [Podpora přijetí koncovými uživateli pomocí podmíněného přístupu](migration-guide-drive-adoption.md)

    -   [Typický cyklus migrace](migration-guide-cycle.md)
        -   [Monitorování migrace](migration-guide-cycle.md#monitoring-migration)
        -   [Po dokončení migrace](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>Předpoklady

-   Službu Intune jste už vyhodnotili v prostředí testování konceptu a rozhodli jste se použít ji jako řešení MDM ve vaší organizaci.

-   Intune a její funkce už znáte.

## <a name="before-you-begin"></a>Před zahájením

Je důležité uvědomit si, že nové nasazení Intune se může lišit od předchozího nasazení MDM. Na rozdíl od tradičních služeb MDM používá Intune řízení přístupu na základě identity, takže řízení přístupu k firemním datům z mobilních zařízení nacházejících se mimo síť organizace nevyžaduje síťová proxy zařízení. Microsoft nabízí řešení pro zabezpečení dat přímo v cloudu prostřednictvím úzce integrovaných cloudových služeb, které se souhrnně označují jako Enterprise Client + Security.

-   Projděte si [běžné způsoby použití Intune](common-scenarios.md).

## <a name="next-steps"></a>Další kroky

[Fáze 1: Příprava Intune na správu mobilních zařízení](migration-guide-prepare.md)
