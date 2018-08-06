---
title: Omezení zařízení s Windows Holographic for Business v Microsoft Intune – Azure | Microsoft Docs
description: Seznamte se s nastaveními a konfigurací omezení zařízení s Windows Holographic for Business v Microsoft Intune, včetně zrušení registrace, zeměpisné polohy, hesel, instalace aplikací z obchodu App Store, souborů cookie a automaticky otevíraných oken v Edgi, programu Windows Defender, vyhledávání, cloudu a úložiště, možností připojení přes Bluetooth, systémového času a dat o používání v Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9d7f54ce0e288025a4a7f0f45bf5b10de5323021
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321630"
---
# <a name="device-restriction-settings-for-windows-holographic-for-business-in-intune"></a>Nastavení omezení zařízení s Windows Holographic for Business v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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

## <a name="kiosk---obsolete"></a>Veřejný terminál (zastaralé)

Tato nastavení jsou jen pro čtení a nedají se změnit. Pokud chcete nakonfigurovat režim veřejného terminálu, podívejte se na článek o [nastavení veřejného terminálu](kiosk-settings.md#windows-holographic-for-business).

Ve veřejných terminálech obvykle běží konkrétní aplikace. Uživatelé nemají v zařízení přístup k žádným prvkům ani funkcím mimo aplikaci veřejného terminálu.

- **Beznabídkový režim** – Určuje typ režimu veřejného terminálu podporovaného zásadami. Vaše možnosti jsou:

  - **Nenakonfigurováno** (výchozí) – Zásady nepovolují režim veřejného terminálu. 
  - **Veřejný terminál s jednou aplikací** – Profil povoluje v zařízení spouštět pouze jednu aplikaci. Jakmile se uživatel přihlásí, spustí se daná aplikace. Tento režim zároveň brání uživateli v otevírání nových aplikací nebo změně spuštěné aplikace.
  - **Veřejný terminál s více aplikacemi** – Profil povoluje v zařízení spouštět více aplikací. Uživatel má k dispozici pouze aplikace, které přidáte. Veřejný terminál s více aplikacemi, neboli zařízení s pevně stanoveným účelem, umožňuje poskytovat přehledné prostředí jednotlivým uživatelům, protože jim povoluje přístup pouze k aplikacím, které potřebují. Nezobrazuje aplikace, které nepotřebují. 
  
    Když přidáváte aplikace pro prostředí veřejného terminálu s více aplikacemi, potřebujete také soubor rozložení nabídky Start. [Soubor rozložení nabídky Start](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-file-for-intune) obsahuje ukázkový soubor XML, který můžete použít v Intune. 

#### <a name="single-app-kiosks"></a>Veřejné terminály s jednou aplikací
Zadejte následující nastavení:

- **Uživatelský účet** – Zadejte místní uživatelský účet (v zařízení) nebo přihlášení k účtu Azure AD přidružené k aplikaci veřejného terminálu. U účtů připojených k doménám Azure AD zadejte účet ve tvaru `domain\username@tenant.org`. 

    U terminálů určených veřejnosti s povoleným automatickým přihlašováním je vhodné použít typ uživatele s nejnižšími oprávněními (například místní standardní uživatelský účet). Ke konfiguraci účtu Azure Active Directory (AD) pro beznabídkový režim veřejného terminálu použijte formát `AzureAD\user@contoso.com`.

- **ID modelu uživatele aplikace (AUMID) dané aplikace** – Zadejte AUMID aplikace veřejného terminálu. Další informace najdete v tématu [Jak najít ID modelu uživatele aplikace (AUMID) nainstalované aplikace](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

## <a name="reporting-and-telemetry"></a>Vytváření sestav a telemetrie

- **Sdílet data o využití** – Umožňuje vybrat úroveň odesílaných diagnostických dat.
