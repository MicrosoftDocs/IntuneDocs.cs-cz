---
title: Při vývoji – Microsoft Intune
titleSuffix: ''
description: Microsoft Intune funkce vývoje
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/03/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1b590e8564f14ce9958c5a1c126edf5dd6740cd1
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576398"
---
# <a name="in-development-for-microsoft-intune---february-2020"></a>Ve vývoji pro Microsoft Intune – únor 2020

Tato stránka vám umožní v rámci připravenosti a plánování vypsat aktualizace uživatelského rozhraní Intune a funkce, které jsou ve vývoji, ale ještě nejsou vydané. Kromě informací na této stránce: 

- Pokud předpokládáme, že před změnou budete muset provést nějakou akci, zveřejníme doplňkový příspěvek v centru zpráv Office.
- Pokud funkce vstoupí do produkčního prostředí, ať už je verze Preview, nebo je všeobecně dostupná, popis funkce se přesune z této stránky na [co je nového](whats-new.md).
- Tato stránka a stránka [co je nového](whats-new.md) se pravidelně aktualizují. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.
- Strategické dodávky a časová osa najdete v tématu [Microsoft 365 plán](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) .

> [!NOTE]
> Tato stránka odráží naše aktuální očekávání na možnosti Intune v budoucí verzi. Data a jednotlivé funkce se můžou změnit. Tato stránka nepopisuje všechny funkce vývoje.

**Informační kanál RSS**: Zjistěte, kdy se tato stránka aktualizuje zkopírováním a vložením následující adresy URL do čtečky informačních kanálů: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
## App management
## Device configuration
## Device enrollment
## Device management
## Intune apps
## Monitor and troubleshoot
## Role-based access control
## Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Správa aplikací

### <a name="display-notifications-for-the-company-portal-app-on-windows---1808082----"></a>Zobrazit oznámení pro aplikaci Portál společnosti ve Windows<!-- 1808082  -->
Aplikaci Portál společnosti na zařízeních s Windows aktualizujeme tak, aby zobrazovala informační oznámení uživatelům, a to i v případě, že je aplikace uzavřená. Tato aktualizace bude zobrazovat oznámení pro dostupné aplikace pouze v případě, že je stav instalace dokončen nebo se nezdařil. Aplikace Portál společnosti nebude zobrazovat oznámení pro požadované aplikace. 

### <a name="display-installation-status-messages-for-the-company-portal-app---2514416----"></a>Zobrazit stavové zprávy instalace pro aplikaci Portál společnosti<!-- 2514416  -->
Aplikace Portál společnosti zobrazí koncovým uživatelům další zprávy o stavu instalace aplikace. Následující podmínky se vztahují na nové funkce závislosti Win32:
- Aplikaci se nepovedlo nainstalovat. Nevyhověly závislosti definované správcem.

### <a name="retarget-web-clips-to-microsoft-edge-on-iosipados-devices---5455276---"></a>Změna cílení webových klipů na zařízení s iOS nebo iPadOS na Microsoft Edge<!-- 5455276 -->
Webové klipy, které fungují jako připnuté webové aplikace v zařízeních s iOS/iPadOS, budou muset být aktualizované. Nově nasazené webové klipy se otevřou v Microsoft Edge místo Intune Managed Browser, pokud je to potřeba pro otevření v chráněném prohlížeči. Aby bylo zajištěno, že budou otevřeny v Microsoft Edge místo Managed Browser, je třeba změnit cílení na stávající webové klipy.


<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfigurace zařízení

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>Profily konfigurace síťových zařízení s drátovou sítí pro zařízení macOS<!-- 3508686  -->
Bude k dispozici nový profil konfigurace zařízení macOS, který konfiguruje drátové sítě (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **MacOS** pro typ profilu > platformed **Network** pro typ profilu). Pomocí této funkce můžete vytvořit profily 802.1 x ke správě drátových sítí a tyto drátové sítě nasadit do zařízení macOS.

Platí pro:
- macOS

### <a name="vpn-profiles-with-ikev2-vpn-connections-can-use-always-on-with-iosipados-devices----1947932-idready---"></a>Profily sítě VPN s připojením IKEv2 VPN můžou používat Always On se zařízeními se systémem iOS/iPadOS. <!-- 1947932 idready -->
Na zařízeních se systémem iOS/iPadOS můžete vytvořit profil sítě VPN, který používá připojení IKEv2 (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS/iPadOS** pro pro typ profilu Platform > **VPN** ). V budoucí aktualizaci můžete nakonfigurovat Always On s IKEv2. Po nakonfigurování se profily IKEv2 VPN připojují automaticky a udržují se připojení (nebo rychlé opětovné připojení) k síti VPN. Zůstane připojený i při přesunu mezi sítěmi nebo po restartování zařízení.

V systému iOS/iPadOS je vždycky zapnutá síť VPN omezená na profily IKEv2.

Pokud chcete zobrazit aktuální nastavení IKEv2, která můžete konfigurovat, přejděte na téma [Přidání nastavení sítě VPN na zařízeních s iOS/iPadOS v Microsoft Intune](../configuration/vpn-settings-ios.md#ikev2-settings).

Platí pro:
- iOS

### <a name="improved-user-interface-experience-when-creating-configuration-profiles-on-iosipados-and-macos-devices---5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984-idready---"></a>Vylepšené prostředí uživatelského rozhraní při vytváření konfiguračních profilů na zařízeních s iOS/iPadOS a macOS<!-- 5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984 idready -->
Když vytváříte profil pro zařízení s iOS/iPadOS nebo macOS, bude se aktualizovat prostředí v centru pro správu správy koncových bodů. Tato změna má vliv na následující konfigurační profily zařízení (**zařízení** > **konfiguračních profilech** > **Vytvoření profilu** > **iOS** nebo **MacOS** pro platformu):

- Vlastní: iOS/iPadOS, macOS
- Funkce zařízení: iOS/iPadOS, macOS
- Omezení zařízení: iOS/iPadOS, macOS
- Ochrana koncového bodu: macOS
- Rozšíření: macOS
- Soubor předvoleb: macOS

### <a name="improved-user-interface-experience-when-creating-oemconfig-configuration-profiles-on-android-enterprise-devices---5568645-idready----"></a>Vylepšené uživatelské rozhraní při vytváření OEMConfig konfigurací profilů na zařízeních s Androidem Enterprise<!-- 5568645 idready  -->
Když vytváříte nebo upravujete profil OEMConfig pro zařízení s Androidem Enterprise, bude se aktualizovat prostředí v centru pro správu správy koncových bodů. Aktualizované prostředí vám poskytne přehled o nastaveních, která jste nakonfigurovali na první pohled. Tato změna má vliv na konfigurační profil zařízení OEMConfig (**zařízení** > **konfiguračních profilů** > **vytvořit profil** > **Android Enterprise** for Platform > **OEMConfig** pro typ profilu).

Tato funkce platí pro:
- Android Enterprise 


<!-- ***********************************************-->
<!--## Device enrollment-->


<!-- ***********************************************-->
## <a name="device-management"></a>Správa zařízení

### <a name="change-primary-user-for-windows-devices----3794742---"></a>Změna primárního uživatele pro zařízení s Windows <!-- 3794742 -->
Můžete změnit primárního uživatele pro zařízení s Windows Hybrid a připojená k Azure AD. Provedete to tak, že přejdete na **zařízení** > **Intune** > **všechna zařízení** > vyberte zařízení > **vlastnosti** > **primární uživatel**. 


<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- ***********************************************-->
<!--
## Monitoring and troubleshooting
-->

<!-- ***********************************************-->
<!--
## Role-based access control
-->


<!-- ***********************************************-->
## <a name="security"></a>Zabezpečení

### <a name="derived-credentials-support-on-android-cobo-devices--4839592--"></a>Podpora odvozených přihlašovacích údajů na zařízeních s Androidem COBO<!--4839592-->
V zařízeních s plnou správou pro Android Enterprise budete moct používat odvozená pověření. Podpora bude zahrnovat načítání odvozených přihlašovacích údajů pro Entrust Datacard, Intercede a DISA purebred. U aplikací, které ji podporují, budete moct používat odvozená pověření pro ověřování aplikací, podepisování Wi-Fi, VPN nebo šifrování S/MIME.

### <a name="use-antivirus-policy-to-manage-settings-for-microsoft-defender-antivirus-and-the-windows-security-experience--6131401---"></a>Použití zásad antivirové ochrany pro správu nastavení antivirové ochrany v programu Microsoft Defender a prostředí zabezpečení systému Windows<!--6131401 -->
V uzlu *zabezpečení koncového bodu* budete moct nakonfigurovat nastavení pro **antivirovou ochranu**. Když konfigurujete zásady pro antivirovou ochranu, definujete nastavení pro zařízení s Windows 10 prostřednictvím dvou typů profilů:

- Antivirová ochrana v programu Microsoft Defender: Spravujte nastavení ochrany cloudu, vyloučení antivirové ochrany, nápravy, možností kontroly a dalších.
- Prostředí zabezpečení systému Windows: Spravujte, jak uživatelé na svých zařízeních nastanou nastavení zabezpečení systému Windows. Budete moct nakonfigurovat, co můžou koncoví uživatelé zobrazit v centru zabezpečení v programu Microsoft Defender a v oznámeních, která obdrží. 

<!-- ***********************************************-->
## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Související témata
Podrobnosti o posledním vývoji najdete v tématu [co je nového v Microsoft Intune](whats-new.md).


