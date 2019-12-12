---
title: Při vývoji – Microsoft Intune
titleSuffix: ''
description: Microsoft Intune funkce vývoje
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04b284a62076122cec70b6b455151a0377470521
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/05/2019
ms.locfileid: "74540736"
---
# <a name="in-development-for-microsoft-intune---december-2019"></a>Ve vývoji pro Microsoft Intune – prosince 2019

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

### <a name="ios-user-licensed-vpp-apps---5619268-idready---"></a>aplikace VPP licencované uživateli iOS<!-- 5619268 idready -->
U zařízení se systémem iOS pro registraci uživatelů se už koncoví uživatelé nebudou mít k dispozici aplikace VPP licencované pro zařízení, které jsou nasazené jako dostupné. Koncoví uživatelé ale budou dál zobrazovat všechny aplikace VPP licencované uživateli v rámci Portál společnosti. Další informace o aplikacích VPP najdete v tématu [Správa aplikací pro iOS a MacOS zakoupených prostřednictvím Apple Volume purchase program s Microsoft Intune](~/apps/vpp-apps-ios.md).

### <a name="retrieve-personal-recovery-key-from-mem-encrypted-macos-devices---4851745-idready---"></a>Načtení osobního obnovovacího klíče ze zařízení s macOS šifrovaným zařízením MEM<!-- 4851745 idready -->
Koncoví uživatelé budou moci načíst svůj osobní obnovovací klíč (klíč trezoru) pomocí aplikace Portál společnosti pro iOS. Zařízení, které má osobní obnovovací klíč, musí být zaregistrované v Intune a zašifrované pomocí trezoru služby prostřednictvím Intune. Pomocí aplikace Portál společnosti pro iOS může koncový uživatel otevřít webové zobrazení Safari a načíst svůj osobní obnovovací klíč. V Intune vyberte **zařízení** > *šifrovaných a zaregistrovaných zařízení MacOS* > **získat obnovovací klíč**. Další informace o trezoru úložišť najdete v tématu [šifrování trezoru MacOS](~/protect/encrypt-devices.md#filevault-encryption-for-macos).

### <a name="microsoft-app-icons-update--4677605--"></a>Aktualizace ikon aplikace Microsoft<!--4677605-->
Ikony používané pro aplikace Microsoftu v podokně cílení aplikace pro zásady ochrany aplikací a zásady konfigurace aplikací se aktualizují.

### <a name="smime-support-for-microsoft-outlook-mobile---2669398----"></a>Podpora S/MIME pro Microsoft Outlook Mobile<!-- 2669398  -->
Intune bude podporovat doručení podpisových a šifrovacích certifikátů S/MIME, které se dají používat s Outlook Mobile v iOS a Androidem. Související informace najdete v tématu [Nastavení e-mailu pro zařízení s iOS](~/configuration/email-settings-ios.md) a [Nastavení e-mailu pro zařízení s Androidem](~/configuration/email-settings-android.md)

### <a name="custom-settings-support-for-macos-applications---4736278----"></a>Podpora vlastních nastavení pro aplikace macOS<!-- 4736278  -->
Intune bude podporovat vlastní nastavení, což vám umožní přidat konkrétní klíče a hodnoty do existujícího souboru seznamu vlastností předvoleb (. plist) a nakonfigurovat tak aplikace macOS a zařízení. Ne všechny aplikace podporují spravované předvolby a v některých případech je možné spravovat jenom specifická nastavení. Nastavení se nasazují jenom přes kanál zařízení. Měli byste nahrávat jenom soubory seznamu vlastností nebo soubory. XML, které cílí na nastavení kanálu zařízení.

### <a name="display-notifications-for-the-company-portal-app-on-windows---1808082----"></a>Zobrazit oznámení pro aplikaci Portál společnosti ve Windows<!-- 1808082  -->
Aplikaci Portál společnosti na zařízeních s Windows aktualizujeme tak, aby zobrazovala informační oznámení uživatelům, a to i v případě, že je aplikace uzavřená. Tato aktualizace bude zobrazovat oznámení pro dostupné aplikace pouze v případě, že je stav instalace dokončen nebo se nezdařil. Aplikace Portál společnosti nebude zobrazovat oznámení pro požadované aplikace.

### <a name="display-installation-status-messages-for-the-company-portal-app---2514416----"></a>Zobrazit stavové zprávy instalace pro aplikaci Portál společnosti<!-- 2514416  -->
Aplikace Portál společnosti zobrazí koncovým uživatelům další zprávy o stavu instalace aplikace. Následující podmínky se vztahují na nové funkce závislosti Win32:
- Aplikaci se nepovedlo nainstalovat. Nevyhověly závislosti definované správcem.

### <a name="configure-app-notification-content-for-organization-accounts---2576686---"></a>Konfigurace obsahu oznámení aplikace pro účty organizace<!-- 2576686 -->
APLIKACE Intune na zařízeních s Androidem a iOS vám umožní řídit obsah oznámení aplikací pro účty organizace. Tato funkce bude vyžadovat podporu aplikací a nemusí být k dispozici pro všechny aplikace s podporou aplikací. Další informace o aplikaci najdete v tématu [co jsou zásady ochrany aplikací?](../apps/app-protection-policy.md)

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfigurace zařízení

### <a name="block-users-from-configuring-certificate-credentials-in-the-managed-keystore-on-android-enterprise-device-owner-devices---3311998-idready---"></a>Zablokovat uživatelům nastavení přihlašovacích údajů certifikátu ve spravovaném úložišti klíčů na zařízeních s Androidem Enterprise Device Owner<!-- 3311998 idready -->
Na zařízeních pro vlastní zařízení s Androidem Enterprise se bude zablokovat nové nastavení pro blokování uživatelů při konfiguraci svých přihlašovacích údajů k certifikátu ve spravovaném úložišti klíčů (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** pro **vlastníka zařízení > jenom > omezení zařízení** pro typ profilu > **Uživatelé a účty**).

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-android-for-work.md).

Týká se
- Vlastník zařízení se systémem Android Enterprise, včetně vyhrazených a plně spravovaných zařízení

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686-idready---"></a>Profily konfigurace síťových zařízení s drátovou sítí pro zařízení macOS<!-- 3508686 idready -->
V zařízeních macOS bude budoucí aktualizace zahrnovat nový profil konfigurace zařízení, který konfiguruje drátové sítě (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **MacOS** pro typ profilu > **drátovou síť** platformy pro typ profilu). Pomocí této funkce můžete vytvořit profily 802.1 x ke správě drátových sítí a tyto drátové sítě nasadit do zařízení macOS.

Týká se
- macOS

### <a name="add-automatic-proxy-settings-to-wi-fi-profiles-for-android-enterprise-work-profiles---4490822-idready---"></a>Přidání automatických nastavení proxy do profilů sítě Wi-Fi pro pracovní profily Android Enterprise<!-- 4490822 idready -->
Na zařízeních se systémem Android Enterprise Work Profiles můžete vytvořit profily sítě Wi-Fi. Když vyberete typ sítě Wi-Fi, můžete také zadat typ protokolu EAP (Extensible Authentication Protocol), který se používá ve vaší síti Wi-Fi.

Když v budoucí aktualizaci zvolíte typ podniku, budete moct zadat automatické nastavení proxy serveru, včetně proxy server URL, jako je například `proxy.contoso.com`.

Pokud chcete zobrazit aktuální nastavení Wi-Fi, která můžete nakonfigurovat, přejděte na [Přidat nastavení Wi-Fi pro zařízení s Androidem Enterprise a Androidem v Microsoft Intune](../configuration/wi-fi-settings-android-enterprise.md).

Týká se
- Pracovní profil Android Enterprise

### <a name="enable-network-access-control-nac-with-cisco-anyconnect-vpn-on-ios-devices---4860111-idready---"></a>Povolení řízení přístupu k síti (NAC) pomocí Cisco AnyConnect VPN na zařízeních s iOS<!-- 4860111 idready -->
Na zařízeních se systémem iOS můžete vytvořit profil sítě VPN a použít jiné typy připojení, včetně Cisco AnyConnect (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro Platform > **VPN** pro typ profilu > **Cisco AnyConnect** pro typ připojení). 

V budoucí aktualizaci budete moci povolit řízení přístupu k síti (NAC) pomocí Cisco AnyConnect. Chcete-li použít tuto funkci:

1. V [příručce pro správce modulu Cisco identity Services](https://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)použijte postup v části **Konfigurace Microsoft Intune jako MDM Server** ke konfiguraci modulu Cisco identity Services Engine (ISE) v Azure.
2. V profilu konfigurace zařízení v Intune vyberte nastavení **povolit Access Control sítě (NAC)** .

Všechna dostupná nastavení sítě VPN zobrazíte tak, že přejdete na [Konfigurace nastavení sítě VPN na zařízeních s iOS](../configuration/vpn-settings-ios.md).

Týká se
- iOS

### <a name="updated-single-sign-on-experience-for-apps-and-websites-on-your-ios-ipados-and-macos-devices---4999578-idready---"></a>Aktualizované prostředí jednotného přihlašování pro aplikace a weby na zařízeních s iOS, iPadOS a macOS<!-- 4999578 idready -->
Intune přidává do zařízení s iOS, iPadOS a macOS další nastavení jednotného přihlašování. V současné době můžete v Intune nakonfigurovat rozšíření aplikace jednotného přihlašování pomocí přihlašovacích údajů a integrované rozšíření protokolu Kerberos společnosti Apple. V budoucí aktualizaci budete moct nakonfigurovat přesměrování rozšíření aplikace jednotného přihlašování napsané vaší organizací nebo vaším poskytovatelem identity. 

Tato nastavení slouží ke konfiguraci bezproblémového jednotného přihlašování pro aplikace a weby, které používají moderní metody ověřování, jako je OAuth a typu Saml2. 

Pokud chcete zobrazit nastavení rozšíření aplikace jednotného přihlašování, které můžete nakonfigurovat, přejděte na adresu [SSO v iOS](../configuration/ios-device-features-settings.md#single-sign-on-app-extension) a [SSO v MacOS](../configuration/macos-device-features-settings.md#single-sign-on-app-extension).

Týká se
- iOS/iPadOS
- macOS

### <a name="require-use-of-approved-keyboards-on-android--4761794-idready---"></a>Vyžadovat použití schválených klávesnic v Androidu<!--4761794 IDready -->
Budete moct zadat seznam schválených klávesnic pro použití ve spravovaných aplikacích pro Android. Ve spravované aplikaci se uživateli zobrazí výzva k přepnutí na jednu ze schválených klávesnic, které už jsou na svém zařízení nainstalované, nebo v případě potřeby budou přesměrovány na Obchod Google Play ke stažení a nastavení jedné ze schválených klávesnic. Uživatel bude moci upravovat textová pole ve spravované aplikaci, pokud je jejich aktivní klávesnicí jednou ze schválených klávesnic.

### <a name="use-pkcs-certificates-with-wi-fi-profiles-on-windows-10-and-later-devices---3246388----"></a>Použití certifikátů PKCS s profily sítě Wi-Fi na zařízeních s Windows 10 a novějším<!-- 3246388  -->
V současné době můžete ověřit profily Wi-Fi pro Windows pomocí certifikátů SCEP (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější** pro platform > **Wi-Fi** pro typ profilu > **typ protokolu EAP** **Enterprise** > . Certifikáty PKCS budete moct používat se profily Wi-Fi pro Windows. Tato funkce umožňuje uživatelům ověřovat profily sítě Wi-Fi pomocí nových nebo existujících profilů certifikátů PKCS ve vašem tenantovi. 

Další informace o profilech sítě Wi-Fi najdete v tématu [Přidání nastavení Wi-Fi pro zařízení s Windows 10 a novějším v Intune](../configuration/wi-fi-settings-windows.md).

Týká se
- Windows 10 a novější

### <a name="new-exchangeactivesync-settings-when-creating-an-email-device-configuration-profile-on-ios-devices---4892824----"></a>Nové nastavení ExchangeActiveSync při vytváření profilu konfigurace e-mailového zařízení na zařízeních s iOS<!-- 4892824  --> 
V zařízeních s iOS/iPadOS můžete nakonfigurovat připojení e-mailu v profilu konfigurace zařízení (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS/iPadOS** **pro > pro** daný typ profilu). 

K dispozici jsou nová nastavení ExchangeActiveSync, včetně:
- Vyberte služby, které se mají synchronizovat (nebo blokovat synchronizaci), jako je e-mail, kalendář a kontakty.
- Povolí (nebo zablokuje) uživatelům změnu nastavení synchronizace pro tyto služby na svých zařízeních. 

Pokud chcete zobrazit aktuální nastavení, přejděte na [Nastavení e-mailového profilu pro zařízení s iOS v Intune](../configuration/email-settings-ios.md).

Týká se
- iOS 13,0 a novější
- iPadOS 13,0 a novější

### <a name="prevent-users-from-adding-personal-google-accounts-to-android-enterprise-device-owner-and-dedicated-devices---5353228----"></a>Zabránit uživatelům v přidávání osobních účtů Google na vlastníka zařízení s Androidem Enterprise a vyhrazená zařízení<!-- 5353228  -->
Budete moct uživatelům zabránit v vytváření osobních účtů Google na základě vlastníka zařízení s Androidem Enterprise a vyhrazených zařízení (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise** pro > Platform **jenom pro vlastníka zařízení > omezení** pro typ profilu > **Nastavení uživatelů a účtů**).

Pokud chcete zobrazit aktuální nastavení, která můžete nakonfigurovat, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-android-for-work.md).

Týká se
- Vlastník zařízení se systémem Android Enterprise
- Zařízení se systémem Android Enterprise vyhrazená

### <a name="server-side-logging-for-siri-commands-setting-is-removed-in-ios-device-restrictions-profile---5468501----"></a>Nastavení příkazů protokolování na straně serveru pro příkazy Siri se v profilu omezení zařízení s iOS odeberou.<!-- 5468501  -->
Na zařízeních s iOS můžete vytvořit profily omezení zařízení, které nakonfigurují protokolování na straně serveru pro příkazy Siri (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS/iPadOS** pro > **omezení zařízení** pro typ profilu > **integrované aplikace**). Bude odebráno nastavení **protokolování na straně serveru pro příkazy Siri** .

Toto nastavení se odebere z konzoly pro správu Intune. Toto nastavení nemá na zařízení žádný vliv, i když existující zásady s nakonfigurovaným nastavením budou pokračovat v zobrazování tohoto nastavení. Pokud chcete odebrat nastavení z existujících zásad, přečtěte si zásady, udělejte dílčí úpravu, uložte ji a zásady se aktualizují.

Nastavení, která můžete konfigurovat, najdete v tématu [nastavení zařízení s iOS a iPadOS, které umožňuje povolit nebo zakázat funkce využívající Intune](../configuration/device-restrictions-ios.md).

Týká se
- iOS

<!-- ***********************************************-->
<!--## Device enrollment-->

<!-- ***********************************************-->
<!--## Device management-->


<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>Monitorování a řešení potíží

### <a name="centralized-audit-logs--5603185-5697164--"></a>Centralizované protokoly auditu<!--5603185, 5697164-->
Nové centralizované prostředí protokolu auditu bude shromažďovat protokoly auditu pro všechny kategorie na jednu stránku. You'l budou moct filtrovat protokoly a získat tak data, která hledáte. Protokoly auditu zobrazíte tak, že přejdete do části **Správa tenanta** > **protokoly auditu**. Další informace najdete v tématu [nadcházející změna v protokolech auditu v Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Upcoming-change-to-Audit-logs-in-Intune/ba-p/1015858).

<!-- ***********************************************-->
<!--## Role-based access control-->


<!-- ***********************************************-->

## <a name="security"></a>Zabezpečení

### <a name="use-pkcs-certificate-profiles-to-provision-devices-with-certificates---2317124-2317130-2317139-2340517-2340528-2340529-idready---"></a>Použití profilů certifikátů PKCS ke zřízení zařízení s certifikáty<!-- 2317124, 2317130, 2317139, 2340517, 2340528, 2340529 IDready -->
K vystavování certifikátů pro zařízení budete moct použít profil certifikátu PKCS a rozšířit o naši aktuální podporu pro uživatelské certifikáty. Certifikáty založené na zařízeních budou podporovat platformy Android, iOS a Windows a dají se použít pro profily Wi-Fi a VPN.

<!-- ***********************************************-->
## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Související témata
Podrobnosti o posledním vývoji najdete v tématu [co je nového v Microsoft Intune](whats-new.md).


