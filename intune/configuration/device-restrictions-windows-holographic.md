---
title: Nastavení zařízení pro Windows holografické firmy – Microsoft Intune – Azure | Microsoft Docs
description: Seznamte se v Microsoft Intune s konfigurací nastavení pro omezení zařízení s Windows Holographic for Business, včetně zrušení registrace, geografické polohy, hesel, instalace aplikací z obchodu s aplikacemi, souborů cookie a automaticky otevíraných oken v Microsoft Edgi, programu Windows Defender, vyhledávání, cloudu a úložiště, připojení přes Bluetooth, systémového času a dat o používání v Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 10efed6bf1f6017881618ac692a190e26b8df638
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730710"
---
# <a name="windows-holographic-for-business-device-settings-to-allow-or-restrict-features-using-intune"></a>Nastavení zařízení ve Windows-holografické pro firmy, které umožňuje povolit nebo zakázat funkce využívající Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Tento článek obsahuje seznam a popis různých nastavení, která můžete řídit na zařízeních s Windows holografickým pro firmy, jako je například Microsoft HoloLens. Jako součást řešení správy mobilních zařízení (MDM) pomocí těchto nastavení můžete povolit nebo zakázat funkce, zabezpečení a další funkce.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil konfigurace zařízení](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Obecné

- **Ruční zrušení registrace**: umožňuje uživateli ze zařízení ručně odstranit pracovní účet.
- **Cortana**: povolení nebo zákaz hlasového asistenta Cortana
- **Zeměpisná poloha**: Určuje, jestli zařízení může používat informace o poloze služby.

## <a name="password"></a>Heslo

- **Heslo**: vyžaduje, aby koncový uživatel zadal heslo pro přístup k zařízení.
- **Vyžadovat heslo při návratu zařízení ze stavu nečinnosti**: Určuje, že uživatel musí zadat heslo k odemknutí zařízení.

## <a name="app-store"></a>App Store

- **Automaticky aktualizovat aplikace ze Storu**: povolí automatickou aktualizaci aplikací nainstalovaných z Microsoft Store.
- **Instalace důvěryhodné aplikace**: povoluje zkušebně načtené aplikací podepsaných důvěryhodným certifikátem.
- **Odemčení pro vývojáře**: umožňuje povolit nastavení vývojářů pro Windows, jako je například umožnění úprav aplikací zkušebně načtené koncovým uživatelem.

## <a name="microsoft-edge-browser"></a>Prohlížeč Microsoft Edge

- **Soubory cookie**: umožňuje prohlížeči ukládat do zařízení internetové soubory cookie.
- **Automaticky otevíraná**okna: blokuje automaticky otevíraná okna v prohlížeči (platí jenom pro Windows 10 Desktop).
- **Návrhy hledání**: umožňuje vyhledávacímu webu navrhovat weby při psaní vyhledávacích frází.
- **Správce hesel**: povolí nebo zakáže funkci Microsoft Edge Password Manager.
- **Odeslat hlavičky do Not Track**: nakonfiguruje prohlížeč Microsoft Edge tak, aby odesílal záhlaví do nesledovaných webů, které uživatelé navštěvují.

## <a name="windows-defender-smart-screen"></a>Filtr SmartScreen v programu Windows Defender

- **Filtr SmartScreen pro Microsoft Edge**: Povolí filtr SmartScreen v Microsoft Edge pro přístup k webu a stahování souborů.

## <a name="search"></a>Hledat

- **Poloha při hledání** – Určuje, jestli hledání může používat informace

## <a name="cloud-and-storage"></a>Cloud a úložiště

- **Účet Microsoft**: umožňuje uživateli přidružit k zařízení účet Microsoft.

## <a name="cellular-and-connectivity"></a>Mobilní síť a připojení

- **Bluetooth**: Určuje, jestli uživatel může na zařízení povolit a nakonfigurovat Bluetooth.
- **Zjistitelnost Bluetooth**: umožňuje zařízení zjistit jiná zařízení s podporou Bluetooth.
- **Inzerce Bluetooth**: umožňuje zařízení přijímat reklamy přes Bluetooth.

## <a name="control-panel-and-settings"></a>Ovládací panely a nastavení

- **Změna systémového času**: zabrání koncovému uživateli ve změně data a času zařízení.

## <a name="kiosk---obsolete"></a>Veřejný terminál (zastaralé)

Tato nastavení jsou jen pro čtení a nedají se změnit. Pokud chcete nakonfigurovat režim veřejného terminálu, podívejte se na článek o [nastavení veřejného terminálu](kiosk-settings-holographic.md).

Ve veřejných terminálech obvykle běží konkrétní aplikace. Uživatelé nemají v zařízení přístup k žádným prvkům ani funkcím mimo aplikaci veřejného terminálu.

- **Celoobrazovkový režim**: Určuje typ beznabídkového režimu, který zásady podporuje. Vaše možnosti jsou:

  - **Není konfigurováno** (výchozí): Zásady nepovolují režim veřejného terminálu. 
  - Veřejný **terminál s jednou aplikací**: Profil umožňuje, aby zařízení spouštělo jenom jednu aplikaci. Jakmile se uživatel přihlásí, spustí se daná aplikace. Tento režim zároveň brání uživateli v otevírání nových aplikací nebo změně spuštěné aplikace.
  - Veřejný **terminál s více aplikacemi**: Profil umožňuje, aby zařízení spouštělo víc aplikací. Uživatel má k dispozici pouze aplikace, které přidáte. Veřejný terminál s více aplikacemi, neboli zařízení s pevně stanoveným účelem, umožňuje poskytovat přehledné prostředí jednotlivým uživatelům, protože jim povoluje přístup pouze k aplikacím, které potřebují. Nezobrazuje aplikace, které nepotřebují. 
  
    Když přidáváte aplikace pro prostředí veřejného terminálu s více aplikacemi, potřebujete také soubor rozložení nabídky Start. [Soubor rozložení nabídky Start](/hololens/hololens-kiosk#start-layout-file-for-mdm-intune-and-others) obsahuje ukázkový soubor XML, který můžete použít v Intune. 

### <a name="single-app-kiosks"></a>Veřejné terminály s jednou aplikací

Zadejte následující nastavení:

- **Uživatelský účet**: Zadejte místní uživatelský účet (zařízení) nebo přihlašovací údaje k účtu Azure AD přidružené k aplikaci veřejného terminálu. U účtů připojených k doménám Azure AD zadejte účet ve tvaru `domain\username@tenant.org`. 

    U terminálů určených veřejnosti s povoleným automatickým přihlašováním je vhodné použít typ uživatele s nejnižšími oprávněními (například místní standardní uživatelský účet). Ke konfiguraci účtu Azure Active Directory (AD) pro beznabídkový režim veřejného terminálu použijte formát `AzureAD\user@contoso.com`.

- **ID modelu uživatele aplikace (AUMID)** aplikace: zadejte AUMID aplikace veřejného terminálu. Další informace najdete v tématu [Jak najít ID modelu uživatele aplikace (AUMID) nainstalované aplikace](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

## <a name="reporting-and-telemetry"></a>Vytváření sestav a telemetrie

- **Sdílet data o využití**: vyberte úroveň odeslání diagnostických dat.

## <a name="next-steps"></a>Další kroky

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
