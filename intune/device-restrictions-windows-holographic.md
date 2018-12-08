---
title: Nastavení zařízení s Windows Holographic Business – Microsoft Intune – Azure | Dokumentace Microsoftu
description: Seznamte se v Microsoft Intune s konfigurací nastavení pro omezení zařízení s Windows Holographic for Business, včetně zrušení registrace, geografické polohy, hesel, instalace aplikací z obchodu s aplikacemi, souborů cookie a automaticky otevíraných oken v Microsoft Edgi, programu Windows Defender, vyhledávání, cloudu a úložiště, připojení přes Bluetooth, systémového času a dat o používání v Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: cdac4623c6c5c9e7258897e1536856e6b24492ea
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/07/2018
ms.locfileid: "53032006"
---
# <a name="windows-holographic-for-business-device-settings-to-allow-or-restrict-features-using-intune"></a>Windows Holographic for Business zařízení nastavení k povolení nebo zakázání funkcí pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek uvádí a popisuje různá nastavení, které můžete řídit na Windows Holographic for Business zařízení, jako je například Microsoft Hololens. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete povolit nebo zakázat funkce, ovládací prvek zabezpečení a další.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](device-restrictions-configure.md).

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

## <a name="windows-defender-smart-screen"></a>Filtr SmartScreen v programu Windows Defender

- **Filtr SmartScreen pro Microsoft Edge**: Povolit SmartScreen Microsoft Edge pro přístup k webu a stahování souborů.

## <a name="search"></a>Search

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

Tato nastavení jsou jen pro čtení a nedají se změnit. Pokud chcete nakonfigurovat režim veřejného terminálu, podívejte se na článek o [nastavení veřejného terminálu](kiosk-settings.md#windows-holographic-for-business).

Ve veřejných terminálech obvykle běží konkrétní aplikace. Uživatelé nemají v zařízení přístup k žádným prvkům ani funkcím mimo aplikaci veřejného terminálu.

- **Celoobrazovkový režim**: Určuje typ režimu veřejného terminálu podporovaného zásadami. Vaše možnosti jsou:

  - **Není konfigurováno** (výchozí): Zásady nepovolují režim veřejného terminálu. 
  - **Veřejný terminál aplikace s jedním**: profil povoluje v zařízení běžela jenom jedna aplikace. Jakmile se uživatel přihlásí, spustí se daná aplikace. Tento režim zároveň brání uživateli v otevírání nových aplikací nebo změně spuštěné aplikace.
  - **Veřejný terminál s více aplikacemi**: profil povoluje v zařízení spouštět více aplikací. Uživatel má k dispozici pouze aplikace, které přidáte. Veřejný terminál s více aplikacemi, neboli zařízení s pevně stanoveným účelem, umožňuje poskytovat přehledné prostředí jednotlivým uživatelům, protože jim povoluje přístup pouze k aplikacím, které potřebují. Nezobrazuje aplikace, které nepotřebují. 
  
    Když přidáváte aplikace pro prostředí veřejného terminálu s více aplikacemi, potřebujete také soubor rozložení nabídky Start. [Soubor rozložení nabídky Start](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-file-for-intune) obsahuje ukázkový soubor XML, který můžete použít v Intune. 

#### <a name="single-app-kiosks"></a>Veřejné terminály s jednou aplikací

Zadejte následující nastavení:

- **Uživatelský účet**: Zadejte místní (pro zařízení) uživatelský účet nebo účet Azure AD přihlášení přidružené k aplikaci veřejného terminálu. U účtů připojených k doménám Azure AD zadejte účet ve tvaru `domain\username@tenant.org`. 

    U terminálů určených veřejnosti s povoleným automatickým přihlašováním je vhodné použít typ uživatele s nejnižšími oprávněními (například místní standardní uživatelský účet). Ke konfiguraci účtu Azure Active Directory (AD) pro beznabídkový režim veřejného terminálu použijte formát `AzureAD\user@contoso.com`.

- **Modelu uživatele aplikace ID (AUMID) dané aplikace**: Zadejte AUMID aplikace veřejného terminálu. Další informace najdete v tématu [Jak najít ID modelu uživatele aplikace (AUMID) nainstalované aplikace](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

## <a name="reporting-and-telemetry"></a>Vytváření sestav a telemetrie

- **Sdílet data o využití**: vybrat úroveň odesílaných diagnostických dat.
