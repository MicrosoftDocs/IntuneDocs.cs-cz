---
title: Přidání ochrany koncových bodů s macOS v Microsoft Intune – Azure | Microsoft Docs
description: Na zařízeních s macOS můžete použít Gatekeeper k určení aplikací, které se smí instalovat, včetně aplikací z Mac App Storu. V Microsoft Intune také můžete určitým aplikacím povolit nebo nakonfigurovat průchod bránou firewall nebo můžete určité aplikace zablokovat, použít neviditelný režim utajení, případně blokovat určité typy příchozích připojení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6e73295752f5bd2743299899e13f9c7e137800d0
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57394213"
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>Nastavení ochrany koncových bodů macOS v Intune

V tomto článku se dozvíte, jak nastavit ochranu koncových bodů pro zařízení s macOS. Na těchto zařízeních je potřeba nastavit Gatekeeper a firewall. V Microsoft Intune můžete ke konfiguraci použít profil zařízení.

## <a name="gatekeeper"></a>Gatekeeper

- **Povolit aplikace stažené z těchto míst**: Omezuje aplikace podle toho, kde jsou stažené. Účelem je chránit zařízení před malwarem a povolit jenom aplikace z důvěryhodných zdrojů. Dostupné možnosti: 
  - **Mac App Store**
  - **Mac App Store a identifikovaní vývojáři**
  - **Kdekoliv**

- **Uživatel může přepsat Gatekeeper**: Zabrání uživatelům v gatekeeperu nastavení a zabraňuje uživatelům kliknutím na instalovat aplikaci pro ovládací prvek. Pokud tuto možnost povolíte, uživatelé mohou stisknout klávesu Control a kliknutím na libovolnou aplikaci ji nainstalovat.

## <a name="firewall"></a>Firewall

Firewall slouží ke kontrole připojení aplikace, nikoli připojení k portu. Když použijete nastavení pro danou aplikaci, získáte snadno výhody ochrany branou firewall. Nežádoucím aplikacím také znemožníte převzetí kontroly nad síťovými porty otevřenými pro oprávněné aplikace.

- **Použijte bránu firewall k ochraně zařízení před neoprávněným přístupem do sítě pomocí řízení připojení na základě jednotlivých aplikací.**
  - **Brána firewall**: Povolit bránu Firewall nakonfigurovat jak příchozí připojení jsou zpracovávány ve vašem prostředí.
  - **Příchozí připojení**: Blokovat všechna příchozí připojení s výjimkou připojení potřebných pro základní internetové služby, například DHCP, Bonjour a IPSec. Tato funkce také zablokuje všechny služby sdílení, jako je sdílení souborů nebo sdílení obrazovky. Pokud používáte služby sdílení, toto nastavení **nekonfigurujte**.

- **Povolení nebo blokování příchozích připojení pro konkrétní aplikace**
  - **Povolené aplikace**: Vyberte aplikace, které se explicitně povolí příjem příchozích připojení.
  - **Blokované aplikace**: Vyberte aplikace, které by měly blokovat příchozí připojení.
  - **Neviditelný režim**: Zabráníte počítači v odpovídání na zjišťovací požadavky, povolení neviditelného režimu. Oprávněným aplikacím bude zařízení dále odpovídat na příchozí žádosti. Neočekávané požadavky, jako je ICMP (ping), se ignorují.
