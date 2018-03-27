---
title: Nastavení Microsoft Intune pro omezení zařízení s Windows Holographic for Business
titleSuffix: ''
description: Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s Windows Holographic for Business.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 694b81434a95f48abc98f5012460523420df58cc
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="microsoft-intune-windows-holographic-for-business-device-restriction-settings"></a>Nastavení omezení pro zařízení s Windows Holographic for Business v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Následující nastavení omezení zařízení se podporují na zařízeních s Windows Holographic for Business, jako je například Microsoft Hololens.

## <a name="general"></a>Obecné

- **Ruční zrušení zápisu** – Umožňuje uživateli ze zařízení ručně odstranit pracovní účet.
- **Cortana** – Povolí nebo zakáže hlasovou asistentku Cortanu.
- **Zeměpisná poloha** – Určuje, jestli zařízení může používat informace služeb určování polohy.



## <a name="password"></a>Heslo
-   **Heslo** – Vyžaduje, aby koncový uživatel zadal heslo pro přístup k zařízení.
    -   **Vyžadovat heslo při návratu zařízení ze stavu nečinnosti** – Určuje, že uživatel musí zadat heslo k odemknutí zařízení.



## <a name="app-store"></a>App Store

-   **Automaticky aktualizovat aplikace ze Storu** – Povolí automatickou aktualizaci aplikací nainstalovaných z Microsoft Storu.
-   **Instalace důvěryhodné aplikace** – Povolí, aby se aplikace podepsané důvěryhodným certifikátem instalovaly bokem.
-   **Odemčení pro vývojáře** – Povolí nastavení pro vývojáře Windows, například možnost povolit koncovým uživatelům provádět změny aplikací nainstalovaných bokem.

## <a name="edge-browser"></a>Prohlížeč Microsoft Edge

-   **Prohlížeč Microsoft Edge** – Povolí používání webového prohlížeče Edge na zařízení.
-   **Soubory cookie** – Umožní prohlížeči ukládat internetové soubory cookie do zařízení.
-   **Automaticky otevíraná okna** – Blokuje automaticky otevíraná okna v prohlížeči (platí jenom pro Windows 10 Desktop).
-   **Návrhy hledání** – Umožní, aby vám vyhledávací web při psaní hledaného textu navrhoval weby.
-   **Správce hesel** – Povolí nebo zakáže funkci Správce hesel v Edgi.
- **Odesílat hlavičky Do Not Track** – Nakonfiguruje prohlížeč Microsoft Edge tak, aby se webům, které uživatelé navštíví, posílaly hlavičky DNT (Do Not Track).

## <a name="windows-defender-smart-screen"></a>Filtr SmartScreen v programu Windows Defender

- **SmartScreen pro Microsoft Edge** – Povolí filtr SmartScreen v prohlížeči Edge pro přístup k webu a stahování souborů.

## <a name="search"></a>Hledat
- **Poloha při hledání** – Určuje, jestli hledání může používat informace


## <a name="cloud-and-storage"></a>Cloud a úložiště
-   **Účet Microsoft** – Umožní uživateli přidružit k zařízení účet Microsoft.

## <a name="cellular-and-connectivity"></a>Mobilní síť a připojení

-   **Bluetooth** – Určuje, jestli uživatel může povolit a konfigurovat Bluetooth na zařízení.
-   **Zjistitelnost zařízení Bluetooth** – Umožní, aby bylo toto zařízení zjistitelné jinými zařízeními podporujícími Bluetooth.
-   **Reklama přes Bluetooth** – Umožní zařízení přijímat přes Bluetooth inzerci.

## <a name="control-panel-and-settings"></a>Ovládací panely a nastavení

- **Změny systémového času** – Zabrání koncovému uživateli ve změně data a času zařízení.

## <a name="reporting-and-telemetry"></a>Vytváření sestav a telemetrie

- **Sdílet data o využití** – Umožňuje vybrat úroveň odesílaných diagnostických dat.