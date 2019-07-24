---
title: Při vývoji – Microsoft Intune
titleSuffix: ''
description: Microsoft Intune funkce vývoje
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f9b02deb529bd6a9bca882fecb3d55d9db513191
ms.sourcegitcommit: 614c4c36cfe544569db998e17e29feeaefbb7a2e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2019
ms.locfileid: "68427178"
---
# <a name="in-development-for-microsoft-intune---july-2019"></a>Ve vývoji Microsoft Intune – červenec 2019

Tato stránka vám pomůže s vaším připravenostm a plánováním vypisuje aktualizace uživatelského rozhraní Intune a funkce, které jsou ve vývoji, ale ještě nejsou vydané. Navíc platí:

- Pokud předpokládáme, že před změnou budete muset provést nějakou akci, zveřejníme doplňkový příspěvek centra zpráv Office.
- Pokud se funkce spustí v produkčním prostředí, buď jako verze Preview, nebo všeobecně dostupná, popis funkce se přesune mimo tuto stránku a na [stránku co je nového](whats-new.md).
- Tato stránka a [Stránka co je nového](whats-new.md) se pravidelně aktualizují. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.
- Strategické dodávky a časové osy najdete v tématu [Přehled M365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) .

> [!Note]
> Tyto položky odrážejí aktuální očekávání Microsoftu týkající se možností Intune, které přichází v budoucí verzi. Data a jednotlivé funkce se můžou změnit. Ne všechny položky ve vývoji obsahují popis funkce na této stránce.

**Informační kanál RSS**: Po aktualizaci této stránky se zobrazí oznámení zkopírováním a vložením následující adresy URL do čtečky informačních kanálů:`https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

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

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Konfigurace obsahu oznámení aplikace pro účty organizace <!-- 2576686 -->
Zásady ochrany aplikací Intune (aplikace) na zařízeních s Androidem a iOS vám umožní řídit obsah oznámení aplikací pro účty org. Tato funkce bude vyžadovat podporu aplikací a nemusí být k dispozici pro všechny aplikace s podporou aplikací. Další informace o aplikaci najdete v tématu [co jsou zásady ochrany aplikací?](app-protection-policy.md).

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Dostupná Google Play vytváření sestav aplikací pro pracovní profily Androidu <!-- 3041956  -->
V případě instalace dostupné aplikace na zařízeních s pracovním profilem Androidu můžete zobrazit stav instalace aplikace a také nainstalovanou verzi spravovaných aplikací Google Play. Další informace najdete v tématu [monitorování zásad ochrany aplikací](app-protection-policies-monitor.md), [Správa zařízení s pracovním profilem Androidu pomocí Intune](android-enterprise-overview.md) a [spravovaného Google Play typu aplikace](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfigurace zařízení

### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Podpora pro profily IKEv2 VPN pro iOS <!-- 1943438 -->
Pomocí protokolu IKEv2 budete moct vytvořit profily sítě VPN pro klienta iOS Native. IKEv2 je nový typ připojení v**profilech** >  **Konfigurace** > zařízení**vytvořit profil** > **iOS** pro Platform > **VPN** pro typ profilu > **Nastavení**.

Tyto profily sítě VPN konfigurují nativního klienta VPN. Žádné klientské aplikace VPN proto nejsou nainstalované ani vložené do spravovaných zařízení. Tato funkce vyžaduje, aby byla zařízení zaregistrovaná v Intune (registrace MDM).

Chcete-li zobrazit aktuální nastavení sítě VPN, která můžete konfigurovat, přejděte na téma [Konfigurace nastavení sítě VPN na zařízeních s iOS v Microsoft Intune](vpn-settings-ios.md).

Platí pro: iOS


<!-- ***********************************************-->
## <a name="device-management"></a>Správa zařízení

### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Nakonfigurujte automatický časový limit pro vyčištění zařízení na 30 dní. <!--4231059  -->
Po posledním přihlášení budete moct nastavit automatický časový limit pro vyčištění zařízení, který je kratší než 30 dní (místo aktuálního limitu 90 dní). Provedete to tak,  > že přejdete na**zařízení** > Intune**Nastavení** > **pravidla vyčistit zařízení**.

<!-- ***********************************************-->
## <a name="security"></a>Zabezpečení

### <a name="import-and-export-security-baselines------3408610------------"></a>Import a export standardních hodnot zabezpečení    <!--3408610          -->  
Přidáváme možnost exportovat a importovat standardní hodnoty zabezpečení, abyste mohli převzít vlastní nastavení s vámi a sdílet je mezi prostředími Intune.


<!-- ***********************************************-->
## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).


