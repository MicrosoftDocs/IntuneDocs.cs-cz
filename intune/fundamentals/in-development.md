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
ms.openlocfilehash: 7113552e09a7c7fa145a452e56575bfaf5297c3e
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514556"
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

### <a name="macos-company-portal-user-experience-improvements---5568987---"></a>vylepšení uživatelského prostředí pro macOS Portál společnosti<!-- 5568987 -->
Vylepšujeme možnosti registrace zařízení macOS a aplikace Portál společnosti pro Mac. Můžete očekávat následující:
- Lepší prostředí Microsoft **AutoUpdate** během registrace, které zajistí, aby vaši uživatelé měli nejnovější verzi portál společnosti.
- Pokročilý krok kontroly dodržování předpisů během registrace.
- Podpora kopírovaných ID incidentů, takže uživatelé můžou rychleji posílat chyby ze svých zařízení do týmu firemní podpory.

Další informace o registraci a Portál společnosti aplikaci pro Mac najdete v tématu Registrace zařízení macOS pomocí aplikace Portál společnosti (https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp). 


### <a name="screen-removed-from-company-portal-android-work-profile-enrollment--6103987---"></a>Obrazovka, která se odebrala z Portál společnosti, registrace pracovních profilů Android<!--6103987 -->
Obrazovka **co dál?** se odebere z toku registrace pracovního profilu Androidu v portál společnosti, aby se zjednodušilo uživatelské prostředí. Pokud chcete zobrazit aktuální tok registrace pracovního profilu Androidu, přejděte k [registraci v pracovním profilu Android]( https://docs.microsoft.com/intune-user-help/enroll-device-android-work-profile) .

### <a name="microsoft-defender-advanced-threat-protection-atp-app-for-macos---5424518-idready---"></a>Aplikace Microsoft Defender Advanced Threat Protection (ATP) pro macOS<!-- 5424518 idready -->
Intune bude poskytovat snadný způsob, jak nasadit aplikaci Microsoft Defender Advanced Threat Protection (ATP) pro macOS do spravovaných zařízení Mac. Další informace najdete v tématu [Rozšířená ochrana před internetovými útoky v programu Microsoft Defender pro Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac). 

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

### <a name="serial-number-on-the-apple-mdm-push-certificate-page--5947765---"></a>Sériové číslo na stránce Apple MDM push Certificate<!--5947765 -->
Na stránce Apple MDM push Certificate se zobrazí sériové číslo. Sériové číslo je potřeba k opětovnému získání přístupu k certifikátu Apple MDM push Certificate, pokud dojde ke ztrátě přístupu k Apple ID, které vytvořilo certifikát. Pokud se chcete podívat na sériové číslo, přejděte na **zařízení** > **iOS** > **iOS registrace** > **Apple MDM push Certificate**.

### <a name="choose-which-iosipados-updates-to-push-to-enrolled-devices--5879689---"></a>Zvolit aktualizace pro iOS/iPadOS, které se mají vložit do zaregistrovaných zařízení<!--5879689 -->
Budete moct vybrat konkrétní aktualizaci pro iOS/iPadOS, která bude nabízet zařízení, která jsou zaregistrovaná pomocí nástroje Apple Business Manager nebo Apple School Manager. Taková zařízení musí mít zásady konfigurace zařízení nastavené tak, aby po dobu určitého počtu dnů zpozdily přehlednost aktualizace softwaru. Tuto funkci zobrazíte tak, že přejdete na **zařízení** MEM > > zásady pro **iOS > ** **Update pro iOS/iPadOS** > **vytvořit profil**.

### <a name="new-update-schedule-options-for-pushing-os-updates-to-enrolled-iosipados-devices--5879689--"></a>Nové možnosti plánu aktualizace pro doručování aktualizací operačního systému do zaregistrovaných zařízení se systémem iOS/iPadOS<!--5879689-->
Při plánování aktualizací operačního systému pro zařízení s iOS/iPadOS budete mít možnost z následujících možností. To platí pro zařízení, která používají typy registrace Apple Business Manageru nebo Apple School Manager.
- Aktualizovat při dalším vrácení se změnami
- Aktualizovat během naplánovaného času
- Aktualizace mimo plánovaný čas

Pro tyto dvě možnosti můžete vytvořit několik časových oken.

Nové možnosti zobrazíte tak, že přejdete na **zařízení** MEM **>**  > **zásady pro iOS > Update pro iOS/iPadOS** > **vytvořit profil**.


<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>Monitorování a řešení potíží

### <a name="improved-intune-reporting-experience---3791418-idready---"></a>Vylepšené prostředí pro vytváření sestav v Intune<!-- 3791418 idready -->
Intune teď nabízí vylepšené možnosti vytváření sestav, včetně nových typů sestav, lepších organizací sestav, pokročilejších zobrazení, vylepšených funkcí sestav a také konzistentních a včasných dat. Možnosti vytváření sestav budou přesunuty z verze Public Preview na GA (všeobecně dostupná). Kromě toho bude verze GA poskytovat podporu lokalizace, opravy chyb, vylepšení návrhu a agregovaná data o dodržování předpisů zařízeními na dlaždicích v [centru pro správu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

Nové typy sestav se zaměřují na následující:
- **Provozní** – poskytuje nové záznamy s negativním důrazem na stav. 
- **Organizace** – poskytuje širší souhrn celkového stavu.
- **Historická** – poskytuje vzory a trendy v časovém intervalu.
- **Specialista** – umožňuje používat nezpracovaná data k vytváření vlastních sestav.

První sada nových sestav se zaměřuje na dodržování předpisů zařízením. Další informace najdete v tématu [Microsoft Intune pro vytváření sestav](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Reporting-Framework-Coming-to-Intune/ba-p/1009553) a [sestavy Intune](~/fundamentals/reports.md)v rámci blogů.



<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Řízení přístupu na základě role

### <a name="intune-roles-user-interface-changes-coming--5801612-idready--"></a>Připravujeme změny uživatelských rozhraní rolí Intune<!--5801612 idready-->
Uživatelské rozhraní pro centrum pro správu [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) > **správu tenanta** > **role** se změní na uživatelsky přívětivější a intuitivní návrh. Toto prostředí nabízí stejné nastavení a podrobnosti, které teď použijete, ale nové prostředí využívá proces podobný průvodci.


<!-- ***********************************************-->
## <a name="security"></a>Zabezpečení

### <a name="derived-credentials-support-on-android-cobo-devices--4839592--"></a>Podpora odvozených přihlašovacích údajů na zařízeních s Androidem COBO<!--4839592-->
V zařízeních s plnou správou pro Android Enterprise budete moct používat odvozená pověření. Podpora bude zahrnovat načítání odvozených přihlašovacích údajů pro Entrust Datacard, Intercede a DISA purebred. U aplikací, které ji podporují, budete moct používat odvozená pověření pro ověřování aplikací, podepisování Wi-Fi, VPN nebo šifrování S/MIME.

### <a name="use-antivirus-policy-to-manage-settings-for-microsoft-defender-antivirus-and-the-windows-security-experience--6131401---"></a>Použití zásad antivirové ochrany pro správu nastavení antivirové ochrany v programu Microsoft Defender a prostředí zabezpečení systému Windows<!--6131401 -->
V uzlu *zabezpečení koncového bodu* budete moct nakonfigurovat nastavení pro **antivirovou ochranu**. Když konfigurujete zásady pro antivirovou ochranu, definujete nastavení pro zařízení s Windows 10 prostřednictvím dvou typů profilů:

- Antivirová ochrana v programu Microsoft Defender: umožňuje spravovat nastavení cloudové ochrany, vyloučení antivirové ochrany, nápravy, možnosti kontroly a další funkce.
- Prostředí zabezpečení systému Windows: umožňuje spravovat způsob, jakým uživatelé na svých zařízeních nastanou nastavení zabezpečení systému Windows. Budete moct nakonfigurovat, co můžou koncoví uživatelé zobrazit v centru zabezpečení v programu Microsoft Defender a v oznámeních, která obdrží. 

<!-- ***********************************************-->
## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Viz také
Podrobnosti o posledním vývoji najdete v tématu [co je nového v Microsoft Intune](whats-new.md).


