---
title: Nastavení zařízení s Windows Holographic Business – Microsoft Intune – Azure | Dokumentace Microsoftu
description: Přečtěte si o a nakonfigurujte nastavení omezení zařízení v Microsoft Intune pro Windows holografické pro firmy, včetně zrušení registrace, geografického umístění, hesel, instalace aplikací z App Storu, souborů cookie a automaticky otevíraných oken v Microsoft Edge, Microsoft Defenderu, hledání, Cloud a úložiště, konektivita Bluetooth, systémový čas a data o využití v Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: df5fb0ba370bff4f5ec99852484dfb1fd2cc9f60
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206495"
---
# <a name="windows-holographic-for-business-device-settings-to-allow-or-restrict-features-using-intune"></a>Windows Holographic for Business zařízení nastavení k povolení nebo zakázání funkcí pomocí Intune



Tento článek uvádí a popisuje různá nastavení, které můžete řídit na Windows Holographic for Business zařízení, jako je například Microsoft Hololens. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete povolit nebo zakázat funkce, ovládací prvek zabezpečení a další.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Obecné

- **Ruční zrušení zápisu**: umožňuje uživateli ze zařízení ručně odstranit pracovní účet.
- **Cortana**: Povolí nebo zakáže hlasového asistenta Cortany.
- **Informace o zeměpisné poloze**: Určuje, jestli zařízení může používat informace služeb určování polohy.

## <a name="password"></a>Heslo

- **Heslo**: vyžaduje koncový uživatel zadal heslo pro přístup k zařízení.
- **Vyžadovat heslo při návratu zařízení ze stavu nečinnosti**: Určuje, že uživatel musí zadat heslo k odemknutí zařízení.

## <a name="app-store"></a>App Store

- **Automaticky aktualizovat aplikace ze storu**: umožňuje aplikací nainstalovaných z Microsoft Store automaticky aktualizovat.
- **Instalace důvěryhodné aplikace**: umožňuje aplikacím, které jsou podepsané důvěryhodným certifikátem instalovaly bokem.
- **Odemčení pro vývojáře**: Windows povolit nastavení pro vývojáře, například můžete umožnit zkušebně načtené aplikace má být upraven koncový uživatel.

## <a name="microsoft-edge-browser"></a>Prohlížeč Microsoft Edge

- **Soubory cookie**: umožní prohlížeči ukládat internetové soubory cookie do zařízení.
- **Automaticky otevíraná okna**: blokuje automaticky otevíraná okna v prohlížeči (platí jenom pro Windows 10 desktop).
- **Návrhy hledání**: umožňuje vyhledávací navrhoval weby vyhledávací web při psaní.
- **Správce hesel**: Povolí nebo zakáže funkci správce hesel Microsoft Edge.
- **Odesílat hlavičky not track**: nakonfiguruje prohlížeč Microsoft Edge odesílat hlavičky do not track na weby, které uživatelé navštíví.

## <a name="microsoft-defender-smart-screen"></a>Inteligentní obrazovka Microsoft Defenderu

- **Filtr SmartScreen pro Microsoft Edge**: Povolit SmartScreen Microsoft Edge pro přístup k webu a stahování souborů.

## <a name="search"></a>Hledat

- **Poloha při hledání** – Určuje, jestli hledání může používat informace

## <a name="cloud-and-storage"></a>Cloud a úložiště

- **Účet Microsoft**: umožňuje uživateli přidružit k zařízení účet Microsoft.

## <a name="cellular-and-connectivity"></a>Mobilní síť a připojení

- **Bluetooth**: Určuje, jestli uživatel může zapnout a konfigurovat Bluetooth na zařízení.
- **Zjistitelnost zařízení Bluetooth**: umožňuje zařízení být zjištěny jinými zařízeními podporujícími technologii Bluetooth.
- **Reklama přes Bluetooth**: umožňuje zařízení přijímat reklamu přes Bluetooth.

## <a name="control-panel-and-settings"></a>Ovládací panely a nastavení

- **Změny systémového času**: zabrání koncovému uživateli ve změně data a času.

## <a name="kiosk---obsolete"></a>Veřejný terminál (zastaralé)

Tato nastavení jsou jen pro čtení a nedají se změnit. Pokud chcete nakonfigurovat režim veřejného terminálu, podívejte se na článek o [nastavení veřejného terminálu](kiosk-settings-holographic.md).

Ve veřejných terminálech obvykle běží konkrétní aplikace. Uživatelé nemají v zařízení přístup k žádným prvkům ani funkcím mimo aplikaci veřejného terminálu.

- **Celoobrazovkový režim**: Určuje typ režimu veřejného terminálu podporovaného zásadami. Vaše možnosti jsou:

  - **Není konfigurováno** (výchozí): Zásady nepovolují režim veřejného terminálu. 
  - **Veřejný terminál aplikace s jedním**: profil povoluje v zařízení běžela jenom jedna aplikace. Jakmile se uživatel přihlásí, spustí se daná aplikace. Tento režim zároveň brání uživateli v otevírání nových aplikací nebo změně spuštěné aplikace.
  - **Veřejný terminál s více aplikacemi**: profil povoluje v zařízení spouštět více aplikací. Uživatel má k dispozici pouze aplikace, které přidáte. Veřejný terminál s více aplikacemi, neboli zařízení s pevně stanoveným účelem, umožňuje poskytovat přehledné prostředí jednotlivým uživatelům, protože jim povoluje přístup pouze k aplikacím, které potřebují. Nezobrazuje aplikace, které nepotřebují. 
  
    Když přidáváte aplikace pro prostředí veřejného terminálu s více aplikacemi, potřebujete také soubor rozložení nabídky Start. [Soubor rozložení nabídky Start](/hololens/hololens-kiosk#start-layout-file-for-mdm-intune-and-others) obsahuje ukázkový soubor XML, který můžete použít v Intune. 

### <a name="single-app-kiosks"></a>Veřejné terminály s jednou aplikací

Zadejte následující nastavení:

- **Uživatelský účet**: Zadejte místní (pro zařízení) uživatelský účet nebo účet Azure AD přihlášení přidružené k aplikaci veřejného terminálu. U účtů připojených k doménám Azure AD zadejte účet ve tvaru `domain\username@tenant.org`. 

    U terminálů určených veřejnosti s povoleným automatickým přihlašováním je vhodné použít typ uživatele s nejnižšími oprávněními (například místní standardní uživatelský účet). Ke konfiguraci účtu Azure Active Directory (AD) pro beznabídkový režim veřejného terminálu použijte formát `AzureAD\user@contoso.com`.

- **Modelu uživatele aplikace ID (AUMID) dané aplikace**: Zadejte AUMID aplikace veřejného terminálu. Další informace najdete v tématu [Jak najít ID modelu uživatele aplikace (AUMID) nainstalované aplikace](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

## <a name="reporting-and-telemetry"></a>Vytváření sestav a telemetrie

- **Sdílet data o využití**: vybrat úroveň odesílaných diagnostických dat.

## <a name="next-steps"></a>Další kroky

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
