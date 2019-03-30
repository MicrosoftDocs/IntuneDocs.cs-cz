---
title: Při vývoji – Microsoft Intune
titlesuffix: ''
description: Microsoft Intune nabízí ve vývoji
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3e068e2c9834290b705e8e7bc2f895636415f9ba
ms.sourcegitcommit: 69aaf89140f82f344404e75a69dc59d8a1585b10
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675438"
---
# <a name="in-development-for-microsoft-intune---april-2019"></a>Při vývoji pro Microsoft Intune – duben 2019

Pomáhat při vaší připravenosti a plánování, tato stránka seznamy uživatelské rozhraní Intune aktualizuje a funkce, které jsou ve vývoji, ale ještě není. Navíc platí:

- Pokud předpokládáme, že budete muset udělat před změnu, budeme publikovat praktického příspěvek Centru zpráv Office.
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
 
## <a name="intune-in-the-azure-portal"></a>Intune na portálu Azure Portal

<!-- 1904 start-->

### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083---"></a>Nastavení přihlášení a řídit možnosti restartování na zařízeních s macOS <!-- 1210083 -->
Na zařízeních s macOS, můžete vytvořit profil konfigurace zařízení (**konfigurace zařízení** > **profily** > **vytvořit profil** > Zvolte **macOS** pro platformu > **funkcí na zařízeních** pro typ profilu). Nové okno Nastavení přihlášení bude obsahovat položky jako zobrazující vlastní hlavičky, zvolte, jak uživatelé přihlásit, zobrazit nebo skrýt nastavení napájení a další.

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení funkcí zařízení s macOS](macos-device-features-settings.md).

Platí pro: macOS

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Pokročilé nastavení firewallu v programu Windows Defender <!-- 1311949 -->
Brzy budete moct používat Intune ke správě vlastních pravidel brány firewall na klientech pro program Windows Defender. Pravidla můžete zadat příchozí a odchozí chování aplikací, síťové adresy a porty. 

### <a name="require-app-protection-conditional-access----1634317---"></a>Vyžadují podmíněný přístup ochrany aplikací  <!--1634317 -->
Budete moct použít *zásady ochrany aplikací vyžadují*, tím se potvrdí zásad se použije pro uživatele aplikace před dokončením přihlášení uživatelům zabránit v přístupu k datům můžete chránit pomocí podmíněného přístupu. Při zabezpečování zásad může zpomalit první prostředí použijte, pomáhá chránit před problémy se sítí, správu chyb v konfiguraci nebo úmyslné úsilí o čáru přes rozpočet zásady ochrany aplikací. 

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----16726660---"></a>Nasazení služby online licenci pro obchodní aplikace pro Microsoft Store <!-- 16726660 -->
Budete moct přiřadit vyžaduje online licencovaných Microsoft Store pro obchodní aplikace v kontextu zařízení. Nasazení Microsoft Store pro firmy díky tomu umožní aplikaci nainstalují pro všechny uživatele v zařízení. Tento krok platí jenom na Windows 10 RS4 + desktopových zařízeních. Možnost instalace v kontextu zařízení je k dispozici na stránce pro přiřazení klientské aplikace pro MSFB Online licencované aplikace.

### <a name="include-and-exclude-mixture-of-user-groups-and-device-groups-when-assigning-policies-and-profiles----1807547---"></a>Zahrnout a vyloučit skupiny uživatelů a skupin zařízení při přiřazování zásady a profily <!-- 1807547 -->
Při přiřazování zásady dodržování předpisů nebo konfigurace profilů, můžete je přiřadit ke skupinám zabezpečení s uživateli nebo zařízení. V současné době můžete zahrnout a vyloučit pouze skupiny uživatelů, *nebo* zahrnout a vyloučit pouze skupiny zařízení. Nelze zahrnout a vyloučit směs skupin, jako například zahrnovat skupiny uživatelů *a* vyloučit skupiny zařízení.

Budete mít zahrnout nebo vyloučit skupiny uživatelů i skupiny zařízení. Můžete zahrnout skupiny uživatelů a vyloučit skupiny zařízení. Například můžete přiřadit nebo nasadit profil konfigurace zařízení na skupinu uživatelů, ale vyloučit osobní zařízení.

[Přiřazení profilů konfigurace zařízení](device-profile-assign.md) obsahuje další informace o přiřazování profilů na skupiny uživatelů a skupin zařízení.

Platí pro: Všechny platformy

### <a name="retire-noncompliant-devices----1827291---"></a>Vyřazení zařízení nedodržující předpisy <!-- 1827291 -->
Chceme přidat novou akci vyřadit z provozu zařízení nesplňujícím požadavky dodržování předpisů. Po vyřazení zařízení nesplňujícím požadavky, odeberete z něj všechna podniková data a také odebere zařízení ze spravované pomocí Intune. Tato akce spustí, když je dosaženo použije se konfigurovaná hodnota ve dnech. Minimální hodnota je 30 dní. 

### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>Konfigurace nastavení pro rozšíření jádra na zařízeních s macOS <!-- 2043024 -->
Na zařízeních s macOS, můžete vytvořit profil konfigurace zařízení (**konfigurace zařízení** > **profily** > **vytvořit profil** > Zvolte **macOS** pro platformu). Nová skupina nastavení vám umožní nakonfigurovat a používat rozšíření jádra na vašich zařízeních.

Platí pro: macOS 10.13.2 a novější

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Konfigurace profilu některé obrazovky přeskočte Průvodci nastavením <!-- 2276470 -->
Při vytváření budete moct profil registrace zařízení s macOS nakonfigurovat tak, aby při procházení Průvodce nastavením přeskočil některé z následujících obrazovek:
- Migrace zařízení s Androidem
- Tón zobrazení
- Ochrana osobních údajů
- iCloudStorage, je-li vytvořit nový profil nebo upravte profil, vybrané přeskočit obrazovky nutnost synchronizovat s Apple MDM server. Uživatelé můžou vydat ruční synchronizaci zařízení tak, aby se žádné zpoždění v ujímají změny profilu.
Další informace najdete v tématu [automaticky zaregistrovat zařízení s macOS pomocí programu registrace zařízení nebo Apple School Manageru](device-enrollment-program-enroll-macos.md).

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Uživatelé zařízení můžete zobrazit všechny spravované aplikace, které jste nainstalovaná nebo se pokusila o instalaci <!-- 2352913 -->
Portál společnosti pro Windows se zobrazí seznam všech spravovaných aplikací&ndash; povinné a k dispozici&ndash; které se instalují na zařízení uživatele. Uživatelé budou moct k pokusu o zobrazení a probíhající instalace aplikací a jejich aktuální stavy. Pokud vaše organizace nemá vytvořit obdobné aplikace vyžaduje nebo jsou dostupné, uživatelům se zobrazí se zpráva s vysvětlením, že nebyly nainstalovány žádné aplikace společnosti. Uživatelé budou také moct seřadíte nebo vyfiltrujete podle stavu instalace aplikace.

### <a name="scope-tags-for-apple-vpp-tokens---2371886---"></a>Značky oboru pro tokeny programu Apple VPP <!--2371886 -->
Budete moct přidat značky oboru tokeny VPP společnosti Apple. Přístup k tokenu Apple VPP s konkrétní značkou budou mít jenom uživatelé, kterým je přiřazená stejnou značku oboru. Aplikace VPP a e-knih pro zakoupit pomocí tohoto tokenu zdědí její klíčová slova oboru. Další informace o značky oboru, naleznete v tématu [značky pomocí RBAC a oboru](scope-tags.md).

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Použijte "pravidla použitelnosti" při vytváření profilů konfigurace zařízení s Windows 10 <!-- 2549910 -->
Vytváření profilů konfigurace zařízení s Windows 10 (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **Windows 10** pro platformu). Budete moct vytvořit **pravidla použitelnosti** tak profil, který se vztahuje pouze na konkrétní edici nebo konkrétní verzi. Například vytvořit profil, který umožňuje některá nastavení nástroje BitLocker. Po přidání profilu použijte použije pravidlo použitelnosti, tak profil, který platí jenom pro zařízení s Windows 10 Enterprise.

Platí pro: 
- Windows 10 a novější

### <a name="enable-win32-app-dependencies----2617348---"></a>Povolí závislosti aplikace systému Win32 <!-- 2617348 -->
Veřejná verze preview – jako správce, budete moct vyžadují, aby ostatní aplikace se instalují jako závislosti před instalací aplikace Win32. Konkrétně zařízení musíte nainstalovat závislé aplikace, před instalací aplikace Win32. Tato funkce bude k dispozici až poté, co byla upgradována na verzi 1904 (větší než 1.18.120.0), což může trvat 1 nebo 2 další týdny poté, co jsme upgradovat službu na 1904 agenta pro správu Intune. V Intune, vyberte **klientské aplikace** > **aplikace** > **přidat** zobrazíte **přidat aplikaci** okno. Vyberte **aplikace Windows (Win32)** jako **typ aplikace**. Další informace najdete v tématu [samostatnou službu Intune – Správa aplikací Win32](apps-win32-app-management.md).

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-connect-to-wi-fi-networks-on-android-enterprise-dedicated-devices-running-multi-app-kiosk-mode---3041940---"></a>Nová nastavení omezení zařízení pro Android Enterprise, vlastník zařízení: umožnit uživatelům s připojením k sítím Wi-Fi na zařízeních s Androidem Enterprise vyhrazené s beznabídkový režim s více aplikacemi <!--3041940 -->
Správci budou moct přepnout nové nastavení, která umožňuje uživatelům nakonfigurovat Bluetooth na svých zařízeních s Androidem Enterprise vyhrazený systémem beznabídkový režim s více aplikacemi. Chcete-li zobrazit toto nastavení v konzole Intune, zvolte **Intune** > **konfigurace zařízení** > **profily**  >  **Vytvořit profil** > zvolte **Androidu Enterprise** pro platformu > **jen vlastník zařízení, omezení zařízení** pro typy profilů > **nastavení**   >  **Vyhrazená zařízení** > vyberte **s více aplikacemi** z **celoobrazovkový režim** nastavení rozevírací seznam. Volá se, možnost **konfigurace Wi-Fi** bude k dispozici. 

Platí pro: Zařízení s androidem Enterprise vyhrazený systémem beznabídkový režim s více aplikacemi. 

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-configure-bluetooth-and-pairing-on-android-enterprise-dedicated-devices---3041941---"></a>Nová nastavení omezení zařízení pro Android Enterprise, vlastník zařízení: umožnit uživatelům konfigurovat Bluetooth a párování na zařízeních s Androidem Enterprise vyhrazené <!--3041941 -->
Správci budou moct přepnout nové nastavení, která umožňuje uživatelům nakonfigurovat Bluetooth na svých zařízeních s Androidem Enterprise vyhrazený systémem beznabídkový režim s více aplikacemi. Chcete-li zobrazit toto nastavení v konzole Intune, zvolte **Intune** > **konfigurace zařízení** > **profily**  >  **Vytvořit profil** > zvolte **Androidu Enterprise** pro platformu > **jen vlastník zařízení, omezení zařízení** pro typy profilů > **nastavení**   >  **Vyhrazená zařízení** > vyberte **s více aplikacemi** z **celoobrazovkový režim** nastavení rozevírací seznam. Volá se, možnost **Bluetooth konfigurace** bude k dispozici. 

Platí pro: Zařízení s androidem Enterprise vyhrazený systémem beznabídkový režim s více aplikacemi. 

### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Monitorovat stav standardních hodnot zabezpečení (public preview) <!-- 3082047 --> 
Při monitorování *stav zařízení* pro směrné plány zabezpečení, zobrazení uspořádá stav podle kategorie standardních hodnot, jako je třeba *nad zámkem*, *BitLocker*a  *Prohlížeč*. Všechny kategorie dostupné standardní hodnoty bude reprezentovat. Pro každou kategorii uvidíte, kolik zařízení se neshodují s konkrétní základní kategorie, jsou nesprávně nakonfigurované nebo se nedají použít.

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Zabezpečení úloh Intune pro ochrany ATP v programu Defender (ve verzi public preview) <!-- 3208597 -->
Už jako verze public preview, Intune brzo přidávat úkoly zabezpečení pro nově oznámené Microsoft Defender Threat & Správa ohrožení zabezpečení.  Tato integrace správce operací zabezpečení v systému Windows Defender ATP (WDATP) efektivněji komunikaci doporučené nápravy nově vznikající hrozby pro správce Intune. Přidání zabezpečení úloh přidá a přístup na základě rizik zjistit, prioritu a náprava ohrožení zabezpečení koncového bodu a chyby v konfiguraci.

Další informace o zabezpečení úloh v Intune, najdete v blogovém příspěvku o [rozšíření Microsoft Defender ATP Správa ohrožení zabezpečení a používání Intune zabezpečení úloh](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883---"></a>Vytváření a používání OEMConfig profilů konfigurace zařízení v Intune <!-- 3305883 -->
Intune bude podporovat konfiguraci zařízení s Androidem Enterprise s OEMConfig. Konkrétně můžete vytvořit profil konfigurace zařízení a použít nastavení podnikových zařízení s Androidem pomocí OEMConfig (**konfigurace zařízení** > **profily**  >  **Vytvořit profil** > **Androidu enterprise** pro platformu).

Podpora pro výrobce OEM, je aktuálně na základě za OEM. Pokud chcete, aby aplikace OEMConfig není k dispozici v seznamu aplikací OEMConfig, obraťte se na `IntuneOEMConfig@microsoft.com`.

Platí pro: 
- Android enterprise

### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254---"></a>Nová nastavení omezení zařízení s Androidem Enterprise, vlastník zařízení <!-- 3574254 -->
Na zařízeních s Androidem Enterprise, můžete vytvořit profil omezení zařízení, povolení nebo zakázání funkce, nastavit pravidla pro hesla a další (**konfigurace zařízení** > **profily**  >  **Vytvořit profil** > zvolte **Androidu Enterprise** pro platformu > **jen vlastník zařízení > omezení zařízení** pro typ profilu). 

Nová nastavení, včetně nastavení hesla, umožňuje úplný přístup k aplikacím v Google Play Store pro plně spravovaná zařízení, a další budou k dispozici. 

Pokud chcete zobrazit aktuální seznam nastavení, přejděte na [nastavení zařízení s Androidem Enterprise a povolení nebo zakázání funkce](device-restrictions-android-for-work.md). 

Platí pro: Plně spravovaná zařízení s androidem Enterprise

### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Vyhledat čipů TPM v zásadách dodržování předpisů zařízení Windows 10 <!-- 3617671 -->
Mnoho Windows 10 a novější zařízení má čipovými sadami Trusted Platform Module (TPM). Nové nastavení dodržování předpisů bude zkontrolujte, jestli je čip TPM na zařízení.

[Windows 10 a novější nastavení zásad dodržování předpisů](compliance-policy-create-windows.md#windows-10-and-later-policy-settings) vypíše aktuální nastavení.

Platí pro: 
- Windows 10 a novější

### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227---"></a>Konfigurace aplikace Win32 pro instalaci na zaregistrovaná v Intune zařízení připojená k Azure AD <!-- 3695227 -->
Budete moct zařízení připojená k přiřazení aplikace Win32 k instalaci v Intune zaregistrovaná Azure AD. Další informace o aplikacích Win32 v Intune najdete v tématu [správy aplikací Win32](apps-win32-app-management.md).

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>Rozšířené ochrany před internetovými útoky programu Windows Defender směrného plánu <!-- 3754134 -->
Chceme přidat nový směrný plán můžete nakonfigurovat nastavení rozšířené ochrany před internetovými útoky programu Windows Defender.

### <a name="device-overview-shows-primary-user---794259---"></a>Přehled zařízení zobrazuje primární uživatel <!--794259 -->
Primární uživatel taky jako uživatele pro spřažení zařízení uživatele (UDA) se zobrazí stránka s přehledem zařízení. Pokud chcete zjistit primární uživatele pro zařízení, zvolte **Intune** > **zařízení** > **všechna zařízení** > zvolte zařízení. Primární uživatel se zobrazí v horní části **přehled** stránky.

### <a name="expanded-support-for-android-enterprise-fully-managed-devices----3903241-3903244-3903246---"></a>Rozšířenou podporu pro zařízení s Androidem Enterprise, plně spravovaná <!-- 3903241, 3903244, 3903246 -->
My budeme rozšíření podpory zařízení s Androidem Enterprise, plně spravovaná ([poprvé oznámena v lednu. 2019](whats-new.md#week-of-january-14-2019) zahrnout následující:
- Dodržování předpisů
- podmíněný přístup
- Nový koncový uživatel aplikace

Nastavení Androidu plně spravovaná zařízení, přejděte na **registrace zařízení** > **registrace zařízení s Androidem** > **uživatele vlastněné společností, plně spravovaná zařízení**. Podpora pro zůstává plně spravovaná zařízení s Androidem ve verzi preview a některé funkce Intune nemusí být plně funkční. 

### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925---"></a>Vytváření sestav pro zařízení s Androidem Enterprise pracovním profilem dalších aplikace spravovaný obchod Google Play <!-- 4105925 -->
Pro spravovaný obchod Google Play aplikace nasazené na zařízení s Androidem Enterprise pracovním profilem bude možné zobrazit číslo verze konkrétní aplikace nainstalované v zařízení. To platí pro pouze požadované aplikace. Povolí se stejné funkce pro aplikace k dispozici v budoucí verzi.

### <a name="ios-third-party-keyboards----4111843---"></a>iOS klávesnice třetích stran <!-- 4111843 -->
Podpora pro zásady ochrany aplikací Intune (aplikace) **třetích stran klávesnice** nastavení skončí kvůli o změnu pro platformu iOS. Nebude moct nakonfigurovat toto nastavení v konzole správce Intune a neuplatní se na klientovi v sadě Intune App SDK.

<!-- 1903 start-->

### <a name="block-users-from-scanning-for-windows-updates----3316758---"></a>Zablokovat uživatelům hledání aktualizací Windows <!-- 3316758 -->
Přidáváme nové nastavení Windows update kanál, který vám pomůže se zablokuje uživatelům možnost skenování pro aktualizace Windows. Toto nastavení nebude k dispozici v rámci portálu, ale dá se s použitím rozhraní Intune Graph API.

### <a name="windows-update-notifications----3316782---"></a>Oznámení o aktualizaci Windows <!-- 3316782 -->
Konfigurace aktualizačního kanálu Windows Update Doplňujeme podporu, takže budete moci konfigurovat oznámení o aktualizacích Windows, které se uživatelům zobrazí. Toto nastavení nebude k dispozici v rámci portálu, ale dá se s použitím rozhraní Intune Graph API.

### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Změny registrace pomocí portálu společnosti pro uživatele zařízení s Iosem 12 <!--3448635 --> 
Portál společnosti pro iOS se aktualizuje obrazovky registrace aplikace a postupy, které bylo v souladu s MDM změny registrace v Apple iOS 12.2. Aktualizovaný pracovní postup bude nyní vyzvat uživatele, aby:

- Povolit Safari otevřít na webu portál společnosti (přes Safari) a stáhněte profil správy před návratem do aplikace portál společnosti.
- Otevřete aplikaci nastavení na instalaci profilu správy na svém zařízení.
- Vraťte se do aplikace portál společnosti, aby prošel registrací.

Další informace o tom, jak můžete připravit pro tyto změny najdete v tématu [technické komunitě Microsoftu příspěvek](https://aka.ms/CP_changes_iOS12). Do té doby pro podporu nové registrace iOS v aplikaci portál společnosti, jsme aktualizovali kroky v [zaregistrovat zařízení s Iosem v Intune](https://docs.microsoft.com/en-us/intune/ios-enroll). Po vydání iOS verze 12.2 Apple, budou tyto změny dokumentu za provozu. 

### <a name="easier-access-to-diagnostic-settings----3804627---"></a>Jednodušší přístup k nastavení diagnostiky <!-- 3804627 -->
Přidáváme novou možnost, jak **protokoly auditu** okno v každé úloze protokolu auditu v konzole Intune, který vám umožní otevřít přímo *nastavení diagnostiky* stránky.

## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).


