---
title: Při vývoji – Microsoft Intune
titleSuffix: ''
description: Microsoft Intune nabízí ve vývoji
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f7dd6f62cb53dd0cc373fb3f2ffa7d9434b135cd
ms.sourcegitcommit: 116ef72b9da4d114782d4b8dd9f57556c9b01511
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2019
ms.locfileid: "67494246"
---
# <a name="in-development-for-microsoft-intune---july-2019"></a>Při vývoji pro Microsoft Intune – červenec 2019

Pomáhat při vaší připravenosti a plánování, tato stránka seznamy uživatelské rozhraní Intune aktualizuje a funkce, které jsou ve vývoji, ale ještě není. Navíc platí:

- Pokud předpokládáme, že budete muset udělat před změnu, budeme publikovat doplňkové příspěvek Centru zpráv Office.
- Když funkce se spustí v produkčním prostředí, buď ve verzi preview nebo obecně k dispozici, popis funkce se přesune mimo tuto stránku a na [stránce s novinkami](whats-new.md).
- Na této stránce a [stránce s novinkami](whats-new.md) jsou pravidelně aktualizovány. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.
- Odkazovat [M365 plán](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) pro strategické dodávky a časovými osami.

> [!Note]
> Tyto položky odrážejí aktuální očekávání společnosti Microsoft o možnostech Intune v budoucí verzi. Data a jednotlivé funkce mohou změnit. Ne všechny položky ve vývoji mají popis funkce na této stránce.

**Informační kanál RSS**: Nechte se informovat Tato stránka se aktualizuje zkopírováním a vložením do informačního kanálu čtečky na následující adrese URL: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
#### App management
#### Device configuration
#### Device enrollment
#### Device management
#### Intune apps
#### Monitor and troubleshoot
#### Role-based access control
#### Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Správa aplikací


### <a name="customized-notifications-for-users-and-groups-------16766574-----"></a>Přizpůsobená oznámení pro uživatele a skupiny    <!-- 16766574   -->
Brzy budete moct posílat vlastní ad-hoc nabízená oznámení z aplikace portál společnosti pro uživatele na zařízení iOS a Androidem, která spravujete přes Intune. Tato vlastní oznámení se váže na konkrétní funkce Intune a můžete použít k žádnému účelu, budete potřebovat, včetně Obecné oznámení, které chcete odeslat k některým nebo všem zaměstnancům.  

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Konfigurace obsahu oznámení aplikaci pro firemní účty <!-- 2576686 -->
Zásady ochrany aplikací (aplikace) Intune na zařízeních s Androidem a iOS vám umožní na obsah oznámení ovládacího prvku aplikace pro účty organizací. Tato funkce bude vyžadovat podporu aplikací a nemusí být dostupné pro všechny aplikace, povolení aplikace. Další informace o aplikaci, najdete v článku [co jsou zásady ochrany aplikací?](app-protection-policy.md).

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Dostupná aplikace Google Play pro vytváření sestav pro pracovní profily Androidu <!-- 3041956  -->
Instalací dostupných aplikací na zařízení s pracovním profilem můžete zobrazit stav instalace aplikace, jakož i nainstalovanou verzi spravované aplikace Google Play. Další informace najdete v tématu [jak monitorovat zásady ochrany aplikací](app-protection-policies-monitor.md), [spravovat pracovní profil androidu pomocí Intune](android-enterprise-overview.md) a [spravovaný obchod Google Play typ aplikace](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfigurace zařízení


### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Podpora IKEv2 VPN profily pro iOS <!-- 1943438 -->
Budete mít k vytvoření profilů sítě VPN pro iOS nativního klienta VPN pomocí protokolu IKEv2. IKEv2 je nový typ připojení v **konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS**  pro platformu > **VPN** pro typy profilů > **nastavení**.

Tyto profily sítě VPN nakonfigurovat nativního klienta VPN. Ano žádné aplikace klienta VPN jsou nainstalovány nebo nahrány do spravovaných zařízení. Tato funkce vyžaduje, aby zařízení zaregistrovaná v Intune (registrace MDM).

Pokud chcete zobrazit aktuální nastavení sítě VPN můžete nakonfigurovat, přejděte na [nastavení konfigurace sítě VPN na zařízeních s Iosem v Microsoft Intune](vpn-settings-ios.md).

Platí pro: iOS

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Použijte "pravidla použitelnosti" při vytváření profilů konfigurace zařízení s Windows 10 <!-- 2549910 -->
Vytváření profilů konfigurace zařízení s Windows 10 (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **Windows 10** pro platformu). Budete moct vytvořit **pravidla použitelnosti** tak profil, který se vztahuje pouze na konkrétní edici nebo konkrétní verzi. Například vytvořit profil, který umožňuje některá nastavení nástroje BitLocker. Po přidání profilu použijte použije pravidlo použitelnosti, tak profil, který platí jenom pro zařízení s Windows 10 Enterprise.

Platí pro: 
- Windows 10 a novější

### <a name="administrative-templates-for-group-policy---------3510695---"></a>Šablony pro správu zásad skupiny     <!--  3510695 -->
K vylepšení zabezpečení pro zařízení v cloudu, Připravujeme k vydání šablony pro správu, které vám umožní nakonfigurovat vyberte nastavení zásad skupiny pro počítače s Windows pomocí Intune.  Tyto šablony pomocí zásad poskytovatele konfiguračních služeb (CSP) můžete poskytnout až 2 500 dalších nastavení z Onedrivu, Office a Windows.

### <a name="manage-filevault-for-macos-------3858502--1210104-----"></a>Správa FileVault pro macOS   <!--  3858502 + 1210104   -->
Budete moct pomocí profilu konfigurace zařízení ochrany koncového bodu Intune ke správě šifrovacích klíčů FileVault pro zařízení s macOS. To zahrnuje podmíněné zobrazení a rotovat šifrovací klíče podnikových zařízení. Koncoví uživatelé budou moct načíst tyto klíče prostřednictvím webu portál společnosti.

### <a name="advanced-settings-for-windows-defender-firewall-------1311949-------"></a>Pokročilé nastavení firewallu v programu Windows Defender   <!--  1311949     -->
Jako verze public preview brzy budete moct používat Intune ke správě vlastních pravidel brány firewall na klientech pro program Windows Defender.  

### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise----3712769----"></a>Nové návrháře konfigurace při vytváření profil OEMConfig pro Android Enterprise <!-- 3712769  -->
V Intune, můžete vytvořit profil konfigurace zařízení, která používá aplikace OEMConfig (konfigurace zařízení > profily > vytvořit profil > pro platformu Android enterprise > OEMConfig pro typ profilu). Když toto provedete, otevře se JSON editor pomocí šablony a můžete změnit hodnoty. Tato aktualizace zahrnuje návrháře konfigurace pomocí vylepšené uživatelské prostředí, která obsahuje informace, které jsou součástí aplikace, jako jsou názvy, popisy a další. JSON editor je stále k dispozici a zobrazuje všechny změny že provedené v Návrháři konfigurace.

Pokud chcete zobrazit aktuální nastavení, přejděte na [použití a správa zařízení s Androidem Enterprise v OEMConfig](android-oem-configuration-overview.md).

Platí pro: Android Enterprise


<!-- ***********************************************-->
## <a name="device-management"></a>Správa zařízení

### <a name="improve-device-location---3855417---"></a>Vylepšení umístění zařízení<!-- 3855417 -->
Budete moct zvětšení přesné souřadnice zařízení pomocí **najít zařízení** akce. Další informace o vyhledání zařízení s Iosem ke ztrátě najdete v tématu [Vyhledání ztracených zařízení s Iosem](device-locate.md).

### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Konfigurovat automatické čištění časový limit na 30 dnů <!--4231059  -->
Budete moct nastavit časový limit čištění automatické zkrátit až na 30 dnů (místo aktuální limit 90 dnů) po posledním přihlášení. Uděláte to tak, přejděte na **Intune** > **zařízení** > **nastavení** > **zařízení vyčistit nahoru pravidla**.


<!-- ***********************************************-->
## <a name="security"></a>Zabezpečení

### <a name="import-and-export-security-baselines------3408610------------"></a>Import a export standardních hodnot zabezpečení    <!--3408610          -->  
Přidáváme funkci pro export a import standardních hodnot zabezpečení, můžete provést vlastní s vámi a jejich sdílení mezi prostředími Intune.



<!-- ***********************************************-->
## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).


