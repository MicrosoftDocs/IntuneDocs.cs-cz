---
title: "Odeslání protokolů správci IT pro zařízení s Windows 10 | Dokumentace Microsoftu"
description: "Registrace zařízení s Windows 10 1511 v Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 038747fb-5b52-47c4-a2b6-f9218da4cfe1
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: be9976f03bf749222ca372040d4d936e6a8fd26b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="send-logs-to-your-it-admin-from-the-settings-app-for-windows-10"></a>Odeslání protokolů správci IT z aplikace Nastavení pro Windows 10

Pokud dojde k chybě při použití zařízení s Windows 10 spravovaného vaší společností, můžete správci IT poslat e-mailem informace o této chybě a pomoct mu tak při řešení daných potíží. Tyto informace se ukládají na zařízení ve speciálním dokumentu s názvem _diagnostický protokol_.

1.  Otevřete aplikaci **Nastavení** Windows – přejděte na **nabídku Start** a vyberte tlačítko **Nastavení**. Můžete také pomocí panelu hledání vyhledat „nastavení“.
2.  Vyberte **Účty** > **Přístup do práce nebo do školy**.
3.  Vyberte možnost Exportovat soubory protokolů správy.

  ![Obrazovka Přístup do práce nebo do školy s možností exportu pod nadpisem Související nastavení](./media/w10-export-logs.png)

4. Protokoly se uloží do složky **C:\Users\Public\Public Documents\MDMDiagnostics**. Vytvoří se dva soubory: Jeden je samotný protokol a druhý je speciální dokument, který umožňuje správci prohlížet protokoly v různých aplikacích, jako je Microsoft Excel. Oba soubory připojte k e-mailu a e-mail odešlete správci. Pokud se nejedná jenom o jednorázovou akci, jednoduše vyberte soubory ze dne, kdy jste protokoly vytvořili. 

Možná bude také potřeba odeslat [protokoly z aplikace Portál společnosti](send-logs-to-your-it-admin-cp-windows.md) a poskytnout tak další pomoc správci IT při řešení potíží, které se můžou vyskytnout. 

Potřebujete ještě další pomoc? Obraťte se na správce IT. Kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).
