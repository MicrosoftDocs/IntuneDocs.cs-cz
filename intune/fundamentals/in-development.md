---
title: Při vývoji – Microsoft Intune
titleSuffix: ''
description: Microsoft Intune funkce vývoje
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3720b0b9a67f0c3462993feef4162ef35f7f3f92
ms.sourcegitcommit: d1b36501186e867355843ddd67c795ade800b76a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2019
ms.locfileid: "73182922"
---
# <a name="in-development-for-microsoft-intune---november-2019"></a>Ve vývoji Microsoft Intune – listopad 2019

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

### <a name="smime-support-for-microsoft-outlook-mobile----2669398----"></a>Podpora S/MIME pro Microsoft Outlook Mobile <!-- 2669398  -->
Intune bude podporovat doručení podpisových a šifrovacích certifikátů S/MIME, které se dají používat s Outlook Mobile v iOS a Androidem. Související informace najdete v tématu [Nastavení e-mailu pro zařízení s iOS](~/configuration/email-settings-ios.md) a [Nastavení e-mailu pro zařízení s Androidem](~/configuration/email-settings-android.md)

### <a name="custom-settings-support-for-macos-applications----4736278----"></a>Podpora vlastních nastavení pro aplikace macOS <!-- 4736278  -->
Intune bude podporovat vlastní nastavení, což vám umožní přidat konkrétní klíče a hodnoty do existujícího souboru seznamu vlastností předvoleb (. plist) a nakonfigurovat tak aplikace macOS a zařízení. Ne všechny aplikace podporují spravované předvolby a v některých případech je možné spravovat jenom specifická nastavení. Nastavení se nasazují jenom přes kanál zařízení. Měli byste nahrávat jenom soubory seznamu vlastností nebo soubory. XML, které cílí na nastavení kanálu zařízení.

### <a name="assignment-type-value-in-windows-company-portal----5459950----"></a>Hodnota typu přiřazení ve Windows Portál společnosti <!-- 5459950  -->
Zobrazí se stránka **nainstalované aplikace** v aplikaci pro Windows portál společnosti se aktualizuje. Sloupec **Typ přiřazení** stránky **nainstalovaných aplikací** byl aktualizován tak, aby byl označen jako "vyžadován vaší organizací". Možné hodnoty jsou **Ano** nebo **ne** k určení požadovaných a dostupných aplikací. Tato změna se provádí v reakci na určitou nejasnost koncového uživatele. Další informace o portálu společnosti pro Windows najdete v tématu [Jak konfigurovat aplikaci Microsoft Intune portál společnosti](~/apps/company-portal-app.md).

### <a name="run-win32-apps-on-windows-10-s-mode-devices----3747604----"></a>Spouštění aplikací Win32 v zařízeních S Windows 10 S v režimu <!-- 3747604  --> 
Aplikace Win32 budete moct instalovat a spouštět na zařízeních spravovaných v režimu Windows 10 S. Pomocí nástrojů PowerShellu pro řízení aplikací v programu Windows Defender (WDAC) vytvořte jednu nebo více doplňkových zásad pro režim S. Pro podepsání doplňkových zásad použijte registrační portál pro ochranu zařízení. Pak tyto zásady nahrajte a distribuujte prostřednictvím Intune. 

V Intune tuto možnost najdete tak, že vyberete **klientské aplikace**  > **doplňkové zásady Windows 10 S**. 

### <a name="set-app-availability-based-on-a-date-and-time----3510685----"></a>Nastavení dostupnosti aplikace na základě data a času <!-- 3510685  -->
Jako správce budete moct nakonfigurovat čas zahájení a termín pro požadovanou aplikaci. V počátečním čase rozšíření pro správu Intune stáhne obsah aplikace a uloží je do mezipaměti. Aplikace se nainstaluje v čase konečného termínu. V případě dostupných aplikací se čas spuštění určí při zobrazení aplikace v Portál společnosti. 

Nastavení dostupnosti aplikace na základě data a času:

1. V Intune vyberte **klientské aplikace** > **aplikace**. 
1. Vyberte aplikaci ze seznamu nebo přidejte novou kliknutím na tlačítko **Přidat**. 
1. V okně aplikace vyberte **přiřazení** > **Přidat skupinu**. 
1. Nastavte **Typ přiřazení** na **požadováno** a pak vyberte **zahrnuté skupiny**. 
1. Nastavte nastavit **tuto aplikaci jako povinnou pro všechny uživatele** na **Ano**. 
1. Vyberte **Upravit** a upravte možnosti **prostředí pro koncové uživatele** . 
1. V okně **činnost koncového uživatele** nastavte **čas dostupný pro software** podle potřeby. 

Další informace najdete v článku [Přidání aplikací do Microsoft Intune](../apps/apps-add.md).

### <a name="require-win32-apps-to-restart----3136567----"></a>Vyžadovat restartování aplikací Win32 <!-- 3136567  -->
Po úspěšné instalaci budete moct vyžadovat, aby se aplikace Win32 restartovala. Můžete zvolit dobu (dobu odkladu) před restartováním.

### <a name="display-notifications-for-the-company-portal-app-on-windows----1808082----"></a>Zobrazit oznámení pro aplikaci Portál společnosti ve Windows <!-- 1808082  -->
Aplikaci Portál společnosti na zařízeních s Windows aktualizujeme tak, aby zobrazovala informační oznámení uživatelům, a to i v případě, že je aplikace uzavřená. Tato aktualizace bude zobrazovat oznámení pro dostupné aplikace pouze v případě, že je stav instalace dokončen nebo se nezdařil. Aplikace Portál společnosti nebude zobrazovat oznámení pro požadované aplikace.

### <a name="display-installation-status-messages-for-the-company-portal-app----2514416----"></a>Zobrazit stavové zprávy instalace pro aplikaci Portál společnosti <!-- 2514416  -->
Aplikace Portál společnosti zobrazí koncovým uživatelům další zprávy o stavu instalace aplikace. Následující podmínky se vztahují na nové funkce závislosti Win32:
- Aplikaci se nepovedlo nainstalovat. Nevyhověly závislosti definované správcem.
- Aplikace byla úspěšně nainstalována, ale vyžaduje restart.
- Aplikace se právě instaluje, ale vyžaduje restart, aby bylo možné pokračovat.

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Konfigurace obsahu oznámení aplikace pro účty organizace <!-- 2576686 -->
APLIKACE Intune na zařízeních s Androidem a iOS vám umožní řídit obsah oznámení aplikací pro účty organizace. Tato funkce bude vyžadovat podporu aplikací a nemusí být k dispozici pro všechny aplikace s podporou aplikací. Další informace o aplikaci najdete v tématu [co jsou zásady ochrany aplikací?](../apps/app-protection-policy.md)


<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfigurace zařízení

### <a name="use-pkcs-certificates-with-wi-fi-profiles-on-windows-10-and-later-devices----3246388----"></a>Použití certifikátů PKCS s profily sítě Wi-Fi na zařízeních s Windows 10 a novějším <!-- 3246388  -->
V současné době můžete ověřit profily Wi-Fi pro Windows pomocí certifikátů SCEP (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Windows 10 a novější** pro platformu > **Wi-Fi** pro Typ profilu > **Enterprise** > **typ protokolu EAP**). Certifikáty PKCS budete moct používat se profily Wi-Fi pro Windows. Tato funkce umožňuje uživatelům ověřovat profily sítě Wi-Fi pomocí nových nebo existujících profilů certifikátů PKCS ve vašem tenantovi. 

Další informace o profilech sítě Wi-Fi najdete v tématu [Přidání nastavení Wi-Fi pro zařízení s Windows 10 a novějším v Intune](../configuration/wi-fi-settings-windows.md).

Platí pro:
- Windows 10 a novější

### <a name="new-exchangeactivesync-settings-when-creating-an-email-device-configuration-profile-on-ios-devices----4892824----"></a>Nové nastavení ExchangeActiveSync při vytváření profilu konfigurace e-mailového zařízení na zařízeních s iOS <!-- 4892824  --> 
V zařízeních se systémem iOS/iPadOS můžete nakonfigurovat připojení e-mailu v profilu konfigurace zařízení (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS/iPadOS** pro **> pro** platformy. pro typ profilu). 

K dispozici jsou nová nastavení ExchangeActiveSync, včetně:
- Vyberte služby, které se mají synchronizovat (nebo blokovat synchronizaci), jako je e-mail, kalendář a kontakty.
- Povolí (nebo zablokuje) uživatelům změnu nastavení synchronizace pro tyto služby na svých zařízeních. 

Pokud chcete zobrazit aktuální nastavení, přejděte na [Nastavení e-mailového profilu pro zařízení s iOS v Intune](../configuration/email-settings-ios.md).

Platí pro:
- iOS 13,0 a novější
- iPadOS 13,0 a novější

### <a name="prevent-users-from-adding-personal-google-accounts-to-android-enterprise-device-owner-and-dedicated-devices----5353228----"></a>Zabránit uživatelům v přidávání osobních účtů Google na vlastníka zařízení s Androidem Enterprise a vyhrazená zařízení <!-- 5353228  -->
Uživatelům budete moct zabránit v vytváření osobních účtů Google na základě vlastníka zařízení s Androidem Enterprise a vyhrazených zařízení (**Konfigurace zařízení** > **profily** > **vytvořit profil** > **Android Enterprise.** pro > **jenom pro vlastníka zařízení > omezení zařízení** pro typ profilu > **nastavení uživatelé a účty**).

Pokud chcete zobrazit aktuální nastavení, která můžete nakonfigurovat, přejděte na [nastavení zařízení s Androidem Enterprise a povolte nebo omezte funkce pomocí Intune](../configuration/device-restrictions-android-for-work.md).

Platí pro:
- Vlastník zařízení se systémem Android Enterprise
- Zařízení se systémem Android Enterprise vyhrazená

### <a name="server-side-logging-for-siri-commands-setting-is-removed-in-ios-device-restrictions-profile----5468501----"></a>Nastavení příkazů protokolování na straně serveru pro příkazy Siri se v profilu omezení zařízení s iOS odeberou. <!-- 5468501  -->
Na zařízeních s iOS můžete vytvořit profily omezení zařízení, které nakonfigurují protokolování na straně serveru pro příkazy Siri (**Konfigurace zařízení** > **profily** > **Vytvoření profilu** > **iOS/iPadOS** pro platformu. > **Omezení zařízení** pro typ profilu > **integrovaných aplikací**). Bude odebráno nastavení **protokolování na straně serveru pro příkazy Siri** .

Toto nastavení se odebere z konzoly pro správu Intune. Toto nastavení nemá na zařízení žádný vliv, i když existující zásady s nakonfigurovaným nastavením budou pokračovat v zobrazování tohoto nastavení. Pokud chcete odebrat nastavení z existujících zásad, přečtěte si zásady, udělejte dílčí úpravu, uložte ji a zásady se aktualizují.

Nastavení, která můžete konfigurovat, najdete v tématu [nastavení zařízení s iOS a iPadOS, které umožňuje povolit nebo zakázat funkce využívající Intune](../configuration/device-restrictions-ios.md).

Platí pro:
- iOS


<!-- ***********************************************-->
<!--## Device enrollment-->

<!-- ***********************************************-->
## <a name="device-management"></a>Správa zařízení

### <a name="edit-device-name-value-for-autopilot-devices---2640074----"></a>Upravit hodnotu názvu zařízení pro zařízení s autopilotem<!-- 2640074  -->
Budete moct upravit hodnotu název zařízení pro zařízení autopilotu připojená k Azure AD. Provedete to tak, že přejdete na **Intune** > **registrace zařízení** > **registraci systému windows** > **Windows autopilot** > **zařízení** > vyberte zařízení > změnit hodnotu **názvu zařízení** v pravém podokně. > **Uložit**.


### <a name="edit-the-group-tag-value-for-autopilot-devices---4816775---"></a>Úprava hodnoty značky skupiny pro zařízení autopilotu<!-- 4816775 -->
Budete moct upravit hodnotu **značky skupiny** pro zařízení autopilotu:

1. Vyberte **Intune** > **registrace zařízení** >  registrace**Windows** > **zařízení**s Windows**autopilot** > .
1. Vyberte zařízení.
1. V pravém podokně změňte hodnotu **značky skupiny** .
1. Vyberte **Uložit**.

### <a name="target-macos-user-groups-to-require-jamf-management----4061739---"></a>Cílové skupiny uživatelů macOS, které vyžadují správu Jamf <!-- 4061739 -->
Budete moct cílit na konkrétní skupiny uživatelů, aby se zařízení macOS mohla spravovat pomocí Jamf. Tento cíl vám umožní použít integraci Jamf dodržování předpisů pro podmnožinu zařízení macOS, zatímco ostatní zařízení se budou dál spravovat přes Intune. Cílení taky vám umožní postupně migrovat zařízení uživatelů z jednoho systému správy mobilních zařízení (MDM) do druhého.

<!-- ***********************************************-->
## <a name="intune-apps"></a>Aplikace Intune

### <a name="improved-macos-enrollment-experience-in-company-portal----5074349----"></a>Vylepšené možnosti registrace macOS v Portál společnosti <!-- 5074349  -->
Portál společnosti pro registraci v macOS bude mít jednodušší proces registrace, který bude lépe zarovnávat Portál společnosti možnosti registrace zařízení s iOS. Uživatelům zařízení se zobrazí:  

* Elegantní uživatelské rozhraní.  
* Vylepšený kontrolní seznam pro registraci.  
* Informace o tom, jak zaregistrovat svá zařízení.  
* Vylepšené možnosti řešení potíží.  

### <a name="improved-checklist-design-in-company-portal-app-for-android---5550857----"></a>Vylepšený návrh kontrolního seznamu v aplikaci Portál společnosti App pro Android<!-- 5550857  -->
Kontrolní seznam nastavení v aplikaci Portál společnosti pro Android se bude aktualizovat s odlehčeným návrhem a novými ikonami. Změny se zarovnají s posledními aktualizacemi provedenými v aplikaci Portál společnosti pro iOS.

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>Monitorování a řešení potíží

### <a name="updated-support-experience-------5012398------"></a>Aktualizované prostředí podpory   <!--  5012398    -->
V rámci pokračujících vylepšení aktualizujeme prostředí podpory v konzole pro Intune.  Vyřešíme vyhledávání v konzole a zpětnou vazbu k běžným problémům a my Zjednodušme pracovní postup, abychom kontaktovali podporu.     

<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Řízení přístupu na základě role

### <a name="duplicate-custom-or-built-in-roles----1081938---"></a>Duplicitní vlastní nebo předdefinované role <!-- 1081938 -->
Budete moct zkopírovat předdefinované a vlastní role. Provedete to tak, že přejdete na > **role** **Intune** > **všechny role** > zvolit roli v seznamu > **Duplikovat**. Ujistěte se, že jste zadali nový název, který je jedinečný.

<!-- ***********************************************-->

## <a name="security"></a>Zabezpečení

### <a name="bitlocker-key-rotation--------2564951--------"></a>Střídání klíčů BitLockeru     <!-- 2564951      -->
K otočení klíčů pro obnovení BitLockeru pro spravovaná zařízení s Windows verze 1909 nebo novější budete moct použít Intune. 

<!-- ***********************************************-->
## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Související témata
Podrobnosti o posledním vývoji najdete v tématu [co je nového v Microsoft Intune](whats-new.md).
