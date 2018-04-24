---
title: Přidání ochrany koncových bodů s macOS v Microsoft Intune – Azure | Microsoft Docs
description: Na zařízeních s macOS můžete použít Gatekeeper k určení aplikací, které se smí instalovat, včetně aplikací z Mac App Storu. V Microsoft Intune také můžete určitým aplikacím povolit nebo nakonfigurovat průchod bránou firewall nebo můžete určité aplikace zablokovat, použít neviditelný režim utajení, případně blokovat určité typy příchozích připojení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 49194d49658042802cbc1148276445008ee1b09f
ms.sourcegitcommit: c3ae3c3dc46b62d9191813d25a196874ba4927be
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/28/2018
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>Nastavení ochrany koncových bodů macOS v Intune

V tomto článku se dozvíte, jak nastavit ochranu koncových bodů pro zařízení s macOS. Na těchto zařízeních je potřeba nastavit Gatekeeper a firewall. V Microsoft Intune můžete ke konfiguraci použít profil zařízení.

## <a name="gatekeeper"></a>Gatekeeper

- **Povolit aplikace stažené z těchto míst**: Omezuje aplikace podle toho, odkud jsou stažené. Účelem je chránit zařízení před malwarem a povolit jenom aplikace z důvěryhodných zdrojů. Dostupné možnosti: 
  - **Mac App Store**
  - **Mac App Store a identifikovaní vývojáři**
  - **Kdekoliv**

- **Uživatel může přepsat Gatekeeper**: Zabraňuje uživatelům přepsat nastavení Gatekeeperu a instalovat aplikace kliknutím při současném stisknutí klávesy Control. Pokud tuto možnost povolíte, uživatelé mohou stisknout klávesu Control a kliknutím na libovolnou aplikaci ji nainstalovat.

## <a name="firewall"></a>Brána firewall

Firewall slouží ke kontrole připojení aplikace, nikoli připojení k portu. Když použijete nastavení pro danou aplikaci, získáte snadno výhody ochrany branou firewall. Nežádoucím aplikacím také znemožníte převzetí kontroly nad síťovými porty otevřenými pro oprávněné aplikace.

- **Použijte bránu firewall k ochraně zařízení před neoprávněným přístupem do sítě pomocí řízení připojení na základě jednotlivých aplikací.**
  - **Firewall**: Umožňuje bráně firewall konfigurovat způsob zpracování příchozích připojení ve vašem prostředí.
  - **Příchozí připojení**: Blokuje všechna příchozí připojení s výjimkou připojení potřebných pro základní internetové služby, jako je DHCP, Bonjour a IPSec. Tato funkce také zablokuje všechny služby sdílení, jako je sdílení souborů nebo sdílení obrazovky. Pokud používáte služby sdílení, toto nastavení **nekonfigurujte**.

- **Povolení nebo blokování příchozích připojení pro konkrétní aplikace**
  - **Povolené aplikace**: Vyberte aplikace, kterým výslovně povolíte přijímat příchozí připojení.
  - **Blokované aplikace**: Vyberte aplikace, kterým zablokujete příchozí připojení.
  - **Neviditelný režim**: Aktivací neviditelného režimu zakážete počítači odpovídat na zjišťovací požadavky. Oprávněným aplikacím bude zařízení dále odpovídat na příchozí žádosti. Neočekávané požadavky, jako je ICMP (ping), se ignorují.
