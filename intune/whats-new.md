---
title: Novinky v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Zjistěte, jaké novinky přináší portál Intune Azure.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: dfc8d782f2d7acee0e935790378d5bedd89a1ac0
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2019
ms.locfileid: "67403567"
---
# <a name="whats-new-in-microsoft-intune"></a>Co je nového v Microsoft Intune

Zjistěte, jaké novinky každý týden přináší Microsoft Intune. Můžete také vyhledat [důležitá oznámení](#notices), [minulých verzích](whats-new-archive.md)a informace o [jak vydání aktualizací služby Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728). 

> [!Note]
> Každý [měsíčních aktualizacích](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) celý proces může trvat až tři dny zavedení a bude v následujícím pořadí:
> - 1\. den: Asie a Tichomoří (APAC)
> - Dne 2: Evropa, Střední východ, Afrika (EMEA)
> - Den 3: Severní Amerika
> 
> Některé funkce můžou vycházet v průběhu několika týdnů a nemusí být k dispozici všem zákazníkům hned první týden.
>
> Zkontrolujte [vývoj stránce](in-development.md) seznam chystaných funkcí ve vydané verzi.

**Informační kanál RSS**: Nechte se informovat Tato stránka se aktualizuje zkopírováním a vložením do informačního kanálu čtečky na následující adrese URL: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->  

<!-- ########################## -->

## <a name="week-of-june-17-2019"></a>Týden od června 17. května 2019   

### <a name="app-management"></a>Správa aplikací

#### <a name="new-features-in-microsoft-intune-app"></a>Nové funkce v aplikaci Microsoft Intune
Přidali jsme nové funkce do aplikace pro Microsoft Intune (preview) pro Android. Teď můžou uživatelé na plně spravovaná zařízení s Androidem:  

* Umožňuje zobrazit a spravovat zařízení, která jste zaregistrovali prostřednictvím aplikace portál společnosti Intune nebo Microsoft Intune.    
* Požádejte o podporu jejich organizace.    
* Posílat připomínky do Microsoftu.    
* Zobrazit podmínky a ujednání, pokud ve své organizaci nastavení.  

## <a name="week-of-june-10-2019"></a>Týden od 10. června 2019 

### <a name="app-management"></a>Správa aplikací  

#### <a name="new-sample-apps-showing-intune-sdk-integration-available-on-github----2653471---"></a>Nové vzorové aplikace zobrazuje dostupné integraci sady Intune SDK na Githubu <!-- 2653471 -->
Složce msintuneappsdk účet GitHub bylo přidáno nové ukázkové aplikace pro iOS (Swift), Android, Xamarin.iOS, Xamarin.Android a Xamarin Forms. Tyto aplikace jsou určené doplnění stávající dokumentaci a ukázky toho, jak integrovat do mobilních aplikací Intune APP SDK. Pokud jste vývojář aplikací, které potřebuje další doprovodné materiály sady Intune SDK, přečtěte si téma následující propojené ukázky:
- [Chatr](https://github.com/msintuneappsdk/Chatr-Sample-Intune-iOS-App) – nativní iOS (Swift) rychlých zpráv aplikace, která se používá Azure Active Directory Authentication Library (ADAL) k zprostředkovanému ověřování.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App) -aplikaci seznamu úkolů nativní Android, která využívá ADAL ke zprostředkovanému ověřování.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps) -aplikaci seznamu úkolů A Xamarin.Android, která využívá ADAL ke zprostředkovanému ověřování, toto úložiště taky má aplikace Xamarin.Forms.
- [Ukázkové aplikace Xamarin.iOS](https://github.com/msintuneappsdk/sample-intune-xamarin-ios) – ukázkové aplikace Xamarin.iOS nejzákladnější.

## <a name="week-of-may-27-2019"></a>Týden od 27. května 2019 

### <a name="app-management"></a>Správa aplikací

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices----4223162---"></a>Vytváření sestav pro potenciálně škodlivých aplikací na zařízeních s Androidem <!-- 4223162 -->
Intune teď poskytuje další informace sestav o potenciálně škodlivých aplikací na zařízeních s Androidem. 

## <a name="week-of-may-20-2019"></a>Týden od 20. května 2019 

### <a name="app-management"></a>Správa aplikací

#### <a name="windows-company-portal-app----3316993---"></a>Aplikace Portál společnosti pro Windows <!-- 3316993 -->
Aplikaci portál společnosti pro Windows budou mít novou stránku s popiskem **zařízení**. **Zařízení** stránce se zobrazí koncovým uživatelům všech zaregistrovaných zařízeních. Uživatelům se zobrazí tuto změnu na portálu společnosti, pokud používají verzi 10.3.4291.0 a novější. Informace o konfiguraci portálu společnosti, naleznete v tématu [konfigurace aplikace portál společnosti Microsoft Intune](company-portal-app.md).

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>AutoPilot zařízení OrderID název atributu změněn na značka skupiny <!-- 4659453 -->

Aby byl intuitivnější, **OrderID** název atributu na zařízení Autopilot se změnil na **značka skupiny**. Při použití sdílených svazků clusteru pro nahrání informací o zařízení Autopilot, je nutné použít značka skupiny jako záhlaví sloupců, nikoli OrderID.  

## <a name="week-of-may-13-2019"></a>Týden od 13. května 2019 

### <a name="app-management"></a>Správa aplikací

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359-idready-wnready--"></a>Aktualizovat zásady Intune metodu ověřování a instalace aplikace portál společnosti  <!-- 1927359 idready wnready-->
Na zařízení už zaregistrované prostřednictvím pomocníka prostřednictvím jednoho z metody registrace podnikového zařízení společnosti Apple Intune nebude podporovat aplikace portál společnosti nainstalovaný ručně koncovými uživateli z app storu. Tato změna platí pouze v Apple Pomocníka s nastavením ověřování během registrace. Tato změna ovlivní také pouze zařízení s Iosem zaregistrovaná prostřednictvím:  
* Apple configurator

* Obchodní ředitel společnosti Apple

* Apple School Manager

* Program registrace zařízení Apple (DEP)

Pokud je uživatelé nainstalovat aplikaci portál společnosti z App storu a potom se pokuste registraci těchto zařízení jeho prostřednictvím, dojde k chybě. Tato zařízení bude očekávat, jenom když ho se převede, automaticky, pomocí Intune během registrace pomocí portálu společnosti. Profily registrace v Intune na portálu Azure portal bude aktualizován, takže můžete určit, jak ověřovat zařízení a pokud se zobrazí v aplikaci portál společnosti. Pokud chcete, aby uživatelé zařízení DEP budou používat aplikaci portál společnosti, musíte zadat předvolby v registrační profil. 

Kromě toho **identifikaci vašeho zařízení** obrazovky v aplikaci portál společnosti pro iOS se odebírá. Proto správci, kteří mají povolení podmíněného přístupu a nasazovat firemní aplikace musí aktualizovat registrační profil DEP. Tento požadavek platí, pouze pokud registrace DEP se ověřuje pomocí Pomocníka pro nastavení. V takovém případě musíte nahrajete aplikaci portál společnosti na zařízení. Chcete-li to provést, zvolte **Intune** > **registrace zařízení** > **registrace Apple** > **programu registrace tokeny** > zvolte token > **profily** > zvolte profil > **vlastnosti** > nastavit **nainstalovat portál společnosti** k **Ano**.

Chcete-li nainstalovat aplikaci portál společnosti na zařízení už zaregistrované s programem DEP, budete muset přejít do Intune > klientských aplikací a poslat ho jako spravovaná aplikace pomocí zásad Konfigurace aplikací. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy----3568384---"></a>Nakonfigurujte, jak koncoví uživatelé aktualizace-obchodní (LOB) aplikace pomocí zásad ochrany aplikací <!-- 3568384 -->
Teď můžete nakonfigurovat, kde můžou koncoví uživatelé získávají aktualizovanou verzi aplikace – obchodní (LOB). Koncovým uživatelům se zobrazí tuto funkci **minimální verze aplikace** dialogového okna podmíněného spuštění, který vás vyzve k koncovým uživatelům aktualizovat na minimální verzi aplikace LOB. Je nutné zadat, že tyto podrobné informace o aktualizaci jako součást zásady ochrany aplikací LOB (aplikace). Tato funkce je k dispozici v Iosu a Androidu. V systémech iOS, tato funkce vyžaduje aplikaci, aby se integrovat (nebo zabalená nástrojem pro zabalení) pomocí sady Intune SDK pro iOS verze. 10.0.7 nebo vyšší. V systému Android se tuto funkci by vyžadovaly nejnovější aplikaci portál společnosti. Pokud chcete nakonfigurovat, jak koncový uživatel aktualizace obchodní aplikace, musí aplikace zásady Konfigurace spravovaných aplikací do něj odesílají s klíčem, `com.microsoft.intune.myappstore`. Odeslané hodnotě bude definovat, které úložiště koncový uživatel stáhne aplikaci. Pokud je aplikace nasazena prostřednictvím aplikace portál společnosti, musí být hodnota `CompanyPortal`. Pro jiné úložiště zadejte úplnou adresu URL.

#### <a name="intune-management-extension-powershell-scripts-----3734186-idready---"></a>Skripty Powershellu rozšíření správy Intune  <!-- 3734186 idready -->
Můžete konfigurovat skripty prostředí PowerShell, spusťte s oprávněními správce uživatele na zařízení. Další informace najdete v tématu [skripty prostředí PowerShell použít na zařízeních s Windows 10 v Intune](intune-management-extension.md) a [správy aplikací Win32](apps-win32-app-management.md).

#### <a name="android-enterprise-app-management----4459905---"></a>Správa aplikací androidu Enterprise <!-- 4459905 -->
Aby bylo snazší pro správce IT ke konfiguraci a použití správy Androidu Enterprise, Intune automaticky přidá čtyři běžné Androidu Enterprise související s aplikací do konzoly pro správu Intune. Čtyři aplikace Android Enterprise jsou následující:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**  – používá se pro scénáře s Androidem Enterprise, plně spravovaná.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)**  – pomáhá vám přihlášení k účtům používáte dvojúrovňového ověřování.
- **[Portál společnosti Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)**  – používá se pro zásady ochrany aplikací (aplikace) a Android Enterprise pracovní profil scénáře.
- [Spravované domovskou obrazovku](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) – používá se pro scénáře vyhrazeného/veřejný terminál s Androidem Enterprise.

Dříve by správci IT musí ručně vyhledejte a schvalte tyto aplikace [spravovaný obchod Google Play storu](https://play.google.com/store/apps) jako součást instalace. Tato změna odebere tyto dříve Ruční postup snadnější a rychlejší pro zákazníky, kteří pro použití správy Androidu.

Správci uvidí tyto čtyři aplikace automaticky přidá do seznamu svých aplikací pro Intune v době, že nejprve připojit svého tenanta Intune do spravovaného obchodu Google Play. Další informace najdete v tématu [připojte si účet Intune ke svému účtu spravovaný obchod Google Play](connect-intune-android-enterprise.md). U klientů, který je již připojen svého tenanta nebo který už používáte Android Enterprise nic, co správce potřeba. Tyto čtyři aplikace se automaticky zobrazí během 7 dnů od konce května 2019 služby zavedení.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune-----1533038---"></a>Aktualizovaný soubor PFX Certificate Connector pro Microsoft Intune  <!-- 1533038 -->
Vydali jsme aktualizaci [konektor certifikátu PFX pro Microsoft Intune](certficates-pfx-configure.md#whats-new-for-connectors) , který řeší problém kde nadále znovu zpracována, stávající certifikáty PFX, což způsobí, že konektoru zastaví zpracování nových žádostí.

####  <a name="intune-security-tasks-for-defender-atp-in-public-preview--------3208597---"></a>Zabezpečení úloh Intune pro ochrany ATP v programu Defender (ve verzi public preview)     <!-- 3208597 -->
Ve verzi public preview, můžete Intune použít ke správě [úloh zabezpečení pro Microsoft Defender Advanced Threat Protection (ATP)](atp-manage-vulnerabilities.md). Tato integrace s ochrany ATP v programu a přidá a přístup na základě rizik zjistit, prioritu a náprava ohrožení zabezpečení koncového bodu a chybné konfigurace, při současném snížení času mezi zjišťování tak, aby omezení rizik.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---idstaged--"></a>Vyhledat čipů TPM v zásadách dodržování předpisů zařízení Windows 10 <!-- 3617671   idstaged-->
Mnoho Windows 10 a novější zařízení má čipovými sadami Trusted Platform Module (TPM). Tato aktualizace zahrnuje nové nastavení dodržování předpisů, která kontroluje verze čipu TPM v zařízení. 

[Windows 10 a novější nastavení zásad dodržování předpisů](compliance-policy-create-windows.md#device-security) popisuje toto nastavení.

Platí pro: Windows 10 a novější

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices----4097904-----"></a>Koncovým uživatelům zabránit ve změně jejich osobní HotSpot a zakázat protokolování zařízení s Iosem server Siri <!-- 4097904   -->  
Vytvořit profil omezení zařízení na zařízení s Iosem (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **iOS** pro platformu > **omezení zařízení** pro typ profilu). Tato aktualizace zahrnuje nové nastavení, které můžete nakonfigurovat:

- **Integrované aplikace**: Protokolování na straně serveru pro příkazy Siri
- **Bezdrátové**: Úprava uživatele osobní Hotspot (jenom pod dohledem)

Chcete-li zobrazit tato nastavení, přejděte na [nastavení Integrovaná aplikace pro iOS](device-restrictions-ios.md#built-in-apps) a [bezdrátové nastavení pro iOS](device-restrictions-ios.md#wireless).

Platí pro: iOS 12.2 a novější

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices----4097905-----"></a>Nová Učebna aplikace nastavení omezení zařízení pro zařízení s macOS <!-- 4097905   --> 
Zařízení můžete vytvořit konfigurační profily pro zařízení s macOS (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **macOS** pro platformu > **omezení zařízení** pro typ profilu). Tato aktualizace obsahovat nové nastavení aplikace classroom, možnost blokovat snímky obrazovky a možnost zakázat knihovnu fotografií na Icloudu.

Pokud chcete zobrazit aktuální nastavení, přejděte na [nastavení zařízení s macOS k povolení nebo zakázání funkcí pomocí Intune](device-restrictions-macos.md).

Platí pro: macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>Přejmenování heslo pro přístup k obchodu s aplikacemi nastavení iOS<!-- 4557891  -->
**Heslo pro přístup k obchodu s aplikacemi** nastavení bylo přejmenováno na **vyžadují iTunes Store heslo u všech nákupů** (**konfigurace zařízení**  >  **Profily** > **vytvořit profil** > **iOS** pro platformu > **omezení zařízení** pro Typ profilu > **App storu, Doc, zobrazení a hraní her**).

Pokud chcete zobrazit dostupná nastavení, přejděte na [App Store, zobrazování dokumentů, nastavení iOS herní](device-restrictions-ios.md#app-store-doc-viewing-gaming).

Platí pro: iOS

####  <a name="microsoft-defender-advanced-threat-protection--baseline--preview------3754134---"></a>Microsoft Defender Advanced Threat Protection směrným plánem (Preview)  <!--  3754134 -->
Přidali jsme základní řešení zabezpečení ve verzi Preview pro [Microsoft Defender Advanced Threat Protection](security-baseline-settings-defender-atp.md) nastavení. Tyto standardní hodnoty je k dispozici, pokud vaše prostředí splňuje předpoklady pro použití [Microsoft Defender Advanced Threat Protection](advanced-threat-protection.md#prerequisites).

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available----3605348---"></a>Windows registrace stavové stránce (ESP) je teď obecně dostupná <!-- 3605348 -->
Stránka stavu registrace se teď z verze preview. Další informace najdete v tématu [nastavení na stránce Stav registrace](windows-enrollment-status.md).


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation-----4593669---"></a>Intune uživatelské rozhraní pro sadu vs11 – vytvoření profilu registrace Autopilot  <!-- 4593669 -->
Aktualizovali jsme uživatelské rozhraní pro vytváření registrační profil Autopilot se zarovnají se styly Azure uživatelského rozhraní. Další informace najdete v tématu [vytvořit registrační profil Autopilot](https://docs.microsoft.com/intune/enrollment-autopilot#create-an-autopilot-deployment-profile). V budoucnu, aktualizují se další scénáře Intune pro tento nový styl uživatelského rozhraní.

#### <a name="enable-autopilot-reset-for-all-windows-devices----4225665---"></a>Povolit resetování Autopilot pro všechna zařízení s Windows <!-- 4225665 -->
Obnovení nastavení AutoPilot nyní pracuje pro všechna zařízení Windows, včetně těch, které není nakonfigurován pro použití stránka stavu registrace. Pokud stránku Stav registrace nebyl nakonfigurován pro zařízení během počáteční registrace zařízení, zařízení přejdete přímo na ploše po přihlášení. Může trvat až 8 hodin synchronizovat, a zobrazí předpisy v Intune. Další informace najdete v tématu [resetovat zařízení pomocí vzdáleného Windows Autopilot resetování](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote).

#### <a name="exact-imei-format-not-required-when-searching-all-devices---30407680---"></a>Přesném formátu IMEI, který není nutné při vyhledávání všech zařízení <!--30407680 -->
Nebudete muset při hledání obsahují mezery v čísla IMEI **všechna zařízení**.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Odstraňuje se zařízení na portálu Apple se projeví na portálu Intune <!--2489996 -->
Pokud zařízení se odstraní z Apple Device Enrollment Program nebo Apple obchodní ředitel portálů, zařízení automaticky se odstraní ze služby Intune při příští synchronizaci.

### <a name="the-enrollment-status-page-now-tracks-win32-apps----2714451---"></a>Stránka stavu registrace se teď sleduje aplikací Win32 <!-- 2714451 -->
Platí jenom pro zařízení s Windows 10 verze 1903 a výše. Další informace najdete v tématu [nastavení na stránce Stav registrace](windows-enrollment-status.md).

### <a name="device-management"></a>Správa zařízení

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Resetovat a vymazání zařízení hromadně pomocí rozhraní Graph API <!-- 3295288 -->
Teď můžete obnovit a vymazání zařízení až 100 hromadně pomocí rozhraní Graph API.


### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="the-encryption-report-is-out-of-public-preview------4587546--------"></a>Sestava šifrování je z verze Public Preview   <!-- 4587546      -->
[Sestavy pro šifrování nástroje BitLocker a zařízení](encryption-monitor.md) je teď obecně dostupná a už nebude součástí verze public preview. 

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices----4050557---"></a>Podpis aplikace Outlook a biometrické nastavení pro iOS a zařízení s Androidem <!-- 4050557 -->
Teď můžete zadat, jestli je povolené výchozí podpis v Outlooku pro iOS a androidem. Kromě toho můžete povolit uživatelům změnit nastavení biometrické v Outlooku pro iOS.

## <a name="week-of-may-6-2019"></a>Týden od 6. května 2019 

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices----4500808---"></a>Řízení přístupu (NAC) podporu pro F5 přístup pro zařízení s Iosem sítě <!-- 4500808 -->

F5 vydali aktualizaci BIG-IP 13, které umožňuje funkci NAC F5 přístup v systému iOS v Intune. Chcete používat tuto funkci:

- Aktualizovat BIG-IP 13.1.1.5 aktualizovat. 14 BIG-IP se nepodporuje.
- Integrace BIG-IP pro NAC s Intune. Kroky v [přehled: Konfigurací funkce APM pro stav zařízení kontroluje se koncový bod správy systémy](https://techdocs.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html).
- Zkontrolujte, **povolit síť přístup ovládacího prvku (NAC)** nastavení v profilu sítě VPN v Intune.

Pokud chcete zobrazit nastavení dostupnosti, přejděte na [nastavení konfigurace sítě VPN na zařízeních s Iosem](vpn-settings-ios.md).

Platí pro: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune----doc-vso-1521237----"></a>Aktualizovaný soubor PFX Certificate Connector pro Microsoft Intune <!-- doc-vso 1521237  -->  
Vydali jsme aktualizaci [konektor certifikátu PFX pro Microsoft Intune](certficates-pfx-configure.md#whats-new-for-connectors) interval dotazování od 5 sekund, který klesne na 30 sekund.

## <a name="week-of-april-22-2019"></a>Týden od 22. dubna 2019

### <a name="use-compliance-manager-to-create-assessments-for-microsoft-intune---4404750---"></a>Správce dodržování předpisů můžete vytvořit posouzení pro Microsoft Intune<!-- 4404750 -->

[Správce dodržování předpisů](https://servicetrust.microsoft.com/ComplianceManager) (otevře jiný web společnosti Microsoft) je nástroj pro vyhodnocení rizik založené na pracovních postupech v Microsoft Service Trust Portal. Umožňuje sledovat, přiřaďte a ověřte aktivit vaší organizace dodržování legislativních předpisů týkající se ke službám Microsoftu. Můžete vytvořit vlastní hodnocení dodržování předpisů Office 365, Azure, Dynamics, odborné služby a Intune. Intune má dvě posouzení k dispozici – FFIEC a nařízení GDPR.

Správce dodržování předpisů pomáhá soustředit vaše úsilí rozdělením ovládací prvky – spravováno společností Microsoft a ovládací prvky spravované vaší organizací. Můžete dokončení vyhodnocení a pak je exportovat a vytisknout posouzení, která.

[Federální finanční instituce zkoumání Rady (FFIEC)](https://www.microsoft.com/trustcenter/compliance/FFIEC) (otevře jiný web společnosti Microsoft) je sada standardů pro online bankovnictví vydané FFIEC dodržování předpisů. Je zatím nejžádanějších posouzení pro finanční instituce, které používají Intune. Interpretuje, jak Intune pomáhá plnit FFIEC příkazu o kyberbezpečnosti pokyny související s veřejnou cloudovými úlohami. FFIEC hodnocení služby Intune je druhý FFIEC vyhodnocování ve Správci dodržování předpisů.

V následujícím příkladu můžete zobrazit rozpis FFIEC ovládacích prvků. Microsoft věnuje 64 ovládací prvky. Zodpovídáte za zbývající 12 ovládací prvky.

![Naleznete v tématu ukázka posouzení Intune FFIEC, včetně akce zákazníků a akce Microsoft](./media/intune-ffiec-assessment-status.png)

[Obecné nařízení (GDPR)](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-overview) (otevře jiný web společnosti Microsoft) je Evropské unie (EU) zákon, který pomáhá chránit práva jednotlivce a jejich data. GDPR se zatím nejžádanějších hodnocení pomáhají dodržovat nařízení o ochraně osobních údajů. 

V následujícím příkladu se vám zobrazit rozpis pro ovládací prvky podle nařízení GDPR. Microsoft věnuje 49 ovládací prvky. Zodpovídáte za zbývající 66 ovládací prvky.

![Viz ukázka posouzení Intune gdpr, včetně akce zákazníků a akce Microsoft](./media/intune-assessment-status.png)

## <a name="week-of-april-15-2019"></a>Týden od 15. dubna 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="openssl-encryption-for-android-app-protection-policies----3747362---"></a>Šifrování OpenSSL pro zásady ochrany aplikací pro Android <!-- 3747362 -->
Zásady ochrany aplikací (aplikace) Intune na zařízeních s Androidem teď využívá knihovnu šifrování OpenSSL, který je podle standardu FIPS 140-2 kompatibilní. Další informace najdete v tématu [šifrování](app-protection-policy-settings-android.md#encryption) část [nastavení zásad ochrany aplikací pro Android v Microsoft Intune](app-protection-policy-settings-android.md).

#### <a name="enable-win32-app-dependencies----2617348----"></a>Povolí závislosti aplikace systému Win32 <!-- 2617348  -->
Jako správce můžete vyžadovat, aby ostatní aplikace se instalují jako závislosti před instalací aplikace Win32. Konkrétně zařízení musíte nainstalovat závislé aplikace, před instalací aplikace Win32. V Intune, vyberte **klientské aplikace** > **aplikace** > **přidat** zobrazíte **přidat aplikaci** okno. Vyberte **aplikace Windows (Win32)** jako **typ aplikace**. Po přidání aplikace můžete vybrat **závislosti** přidat závislé aplikace, které musí být nainstalovaný před instalací aplikace Win32. Další informace najdete v tématu [samostatnou službu Intune – Správa aplikací Win32](apps-win32-app-management.md). 

#### <a name="app-version-installation-information-for-microsoft-store-for-business-apps----3537391-----"></a>Informace o instalaci verze aplikace pro Microsoft Store pro obchodní aplikace <!-- 3537391   -->
Sestavy instalací aplikace zahrnují informace o verzi aplikace pro Microsoft Store pro obchodní aplikace. V Intune, vyberte **klientské aplikace** > **aplikace**. Vyberte **Microsoft Store pro firmy** a pak vyberte **stav instalace zařízení** pod **monitorování** oddílu.

#### <a name="additions-to-win32-apps-requirement-rules----3676883-----"></a>Tvorba pravidla požadavků aplikace Win32 <!-- 3676883   -->
Můžete vytvořit požadavek na skripty prostředí PowerShell, hodnoty registru a informace o systému souborů na základě pravidel. V Intune, vyberte **klientské aplikace** > **aplikace** > **přidat**. Potom vyberte **aplikace Windows (Win32)** jako **typ aplikace** v **přidat aplikaci** okno.  Vyberte **požadavky** > **přidat** ke konfiguraci pravidla dalších požadavků. Vyberte buď **typ souboru**, **registru**, nebo **skript** jako **typ požadavku**. Další informace najdete v tématu [správy aplikací Win32](apps-win32-app-management.md).

 #### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227----"></a>Konfigurace aplikace Win32 pro instalaci na zaregistrovaná v Intune zařízení připojená k Azure AD <!-- 3695227  -->
Aplikace Win32 pro instalaci na zaregistrovaná v Intune můžete přiřadit zařízení připojená k Azure AD. Další informace o aplikacích Win32 v Intune najdete v tématu [správy aplikací Win32](apps-win32-app-management.md).

#### <a name="device-overview-shows-primary-user---794259----"></a>Přehled zařízení zobrazuje primární uživatel <!--794259  -->
Primární uživatel taky jako uživatele pro spřažení zařízení uživatele (UDA) se zobrazí stránka s přehledem zařízení. Pokud chcete zjistit primární uživatele pro zařízení, zvolte **Intune** > **zařízení** > **všechna zařízení** > zvolte zařízení. Primární uživatel se zobrazí v horní části **přehled** stránky.

#### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925----"></a>Vytváření sestav pro zařízení s Androidem Enterprise pracovním profilem dalších aplikace spravovaný obchod Google Play <!-- 4105925  -->
Pro spravovaný obchod Google Play aplikace nasazené na zařízení s Androidem Enterprise pracovním profilem můžete zobrazit číslo verze konkrétní aplikace nainstalované v zařízení. To platí pro pouze požadované aplikace.  

#### <a name="ios-third-party-keyboards----4111843-----"></a>iOS klávesnice třetích stran <!-- 4111843   -->
Podpora Intune app protection zásad (aplikace) pro **třetích stran klávesnice** nastavení pro iOS se už nepodporuje z důvodu o změnu pro platformu iOS. Nebude moct nakonfigurovat toto nastavení v konzole správce Intune a neuplatní se na klientovi v sadě Intune App SDK.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083----"></a>Nastavení přihlášení a řídit možnosti restartování na zařízeních s macOS <!-- 1210083  -->
Na zařízeních s macOS, můžete vytvořit profil konfigurace zařízení (**konfigurace zařízení** > **profily** > **vytvořit profil** > Zvolte **macOS** pro platformu > **funkcí na zařízeních** pro typ profilu). Tato aktualizace zahrnuje nové okno Nastavení přihlášení, například zobrazení vlastní hlavičky, zvolte, jak uživatelé přihlásit, zobrazit nebo skrýt nastavení napájení a další.

Chcete-li zobrazit tato nastavení, přejděte na [nastavení funkcí zařízení s macOS](macos-device-features-settings.md).

#### <a name="configure-wifi-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode---3041940----"></a>Konfigurace Wi-Fi na Androidu Enterprise, vlastník zařízení vyhrazená zařízení spuštěné v režimu veřejného terminálu s více aplikacemi <!--3041940  -->
Můžete povolit nastavení na Androidu Enterprise, vlastník zařízení při spuštění jako vyhrazená zařízení v celoobrazovkovém režimu s více aplikacemi. V této aktualizaci, povolíte uživatelům ke konfiguraci a připojení k sítím Wi-Fi (**Intune** > **konfigurace zařízení** > **profily**  >  **Vytvořit profil** > **Androidu Enterprise** pro platformu > **jen vlastník zařízení, omezení zařízení** pro typy profilů >  **Vyhrazená zařízení** > **celoobrazovkový režim**: **Multi-App** > **konfigurace Wi-Fi**). 

Pokud chcete zobrazit všechna nastavení můžete nakonfigurovat, přejděte na [nastavení zařízení s Androidem Enterprise a povolení nebo zakázání funkce](device-restrictions-android-for-work.md).

Platí pro: Zařízení s androidem Enterprise vyhrazené spuštěn v režimu veřejného terminálu s více aplikacemi


#### <a name="configure-bluetooth-and-pairing-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode----3041941----"></a>Konfigurovat Bluetooth a párování na Androidu Enterprise, vlastník zařízení vyhrazená zařízení spuštěné v režimu veřejného terminálu s více aplikacemi <!-- 3041941  -->
Můžete povolit nastavení na Androidu Enterprise, vlastník zařízení při spuštění jako vyhrazená zařízení v celoobrazovkovém režimu s více aplikacemi. V této aktualizaci můžete povolit koncovým uživatelům povolit Bluetooth a spárujte zařízení přes Bluetooth (**Intune** > **konfigurace zařízení** > **profily**  >  **Vytvořit profil** > **Androidu Enterprise** pro platformu > **jen vlastník zařízení, omezení zařízení** profilu Typ > **vyhrazená zařízení** > **celoobrazovkový režim**: **Multi-App** > **Bluetooth konfigurace**). 

Pokud chcete zobrazit všechna nastavení můžete nakonfigurovat, přejděte na [nastavení zařízení s Androidem Enterprise a povolení nebo zakázání funkce](device-restrictions-android-for-work.md).

Platí pro: Zařízení s androidem Enterprise vyhrazené spuštěn v režimu veřejného terminálu s více aplikacemi

#### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883----"></a>Vytváření a používání OEMConfig profilů konfigurace zařízení v Intune <!-- 3305883  -->
V této aktualizaci Intune podporuje konfiguraci zařízení s Androidem Enterprise s OEMConfig. Konkrétně můžete vytvořit profil konfigurace zařízení a použít nastavení podnikových zařízení s Androidem pomocí OEMConfig (**konfigurace zařízení** > **profily**  >  **Vytvořit profil** > **Androidu enterprise** pro platformu).

Podpora pro výrobce OEM, je aktuálně na základě za OEM. Pokud chcete, aby aplikace OEMConfig není k dispozici v seznamu aplikací OEMConfig, obraťte se na `IntuneOEMConfig@microsoft.com`.

Další informace o této funkci, přejděte na [použití a správa zařízení s Androidem Enterprise v OEMConfig v Microsoft Intune](android-oem-configuration-overview.md).

Platí pro: Android enterprise

#### <a name="windows-update-notifications-----3316758-3316782----"></a>Oznámení o aktualizaci Windows  <!-- 3316758, 3316782  -->
Přidali jsme dvě *nastavení činnosti koncového uživatele* ke službě Windows Update vyzvánět konfigurace, které můžete spravovat z konzoly Intune. Teď můžete:
- Blokovat nebo povolit uživatelům [vyhledávání aktualizací Windows](windows-update-settings.md#block-user-from-scanning-for-windows-updates).
- Správa [úrovně upozornění na aktualizace Windows](windows-update-settings.md#windows-update-notification-level) , že uživatelé uvidí.

#### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254----"></a>Nová nastavení omezení zařízení s Androidem Enterprise, vlastník zařízení <!-- 3574254  -->
Na zařízeních s Androidem Enterprise, můžete vytvořit profil omezení zařízení, povolení nebo zakázání funkce, nastavit pravidla pro hesla a další (**konfigurace zařízení** > **profily**  >  **Vytvořit profil** > zvolte **Androidu Enterprise** pro platformu > **jen vlastník zařízení > omezení zařízení** pro typ profilu). 

Tato aktualizace zahrnuje nové nastavení hesla, umožňuje plný přístup k aplikacím v Google Play Store plně spravovaných zařízeních a další věci. Pokud chcete zobrazit aktuální seznam nastavení, přejděte na [nastavení zařízení s Androidem Enterprise a povolení nebo zakázání funkce](device-restrictions-android-for-work.md). 

Platí pro: Plně spravovaná zařízení s androidem Enterprise

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Vyhledat čipů TPM v zásadách dodržování předpisů zařízení Windows 10 <!-- 3617671 -->

Tato funkce je zpožděno a plánujeme přidat později uvolní.

#### <a name="updated-ui-changes-for-microsoft-edge-browser-on-windows-10-and-later-devices----3775833-----"></a>Aktualizované změny uživatelského rozhraní pro prohlížeče Microsoft Edge ve Windows 10 a novější zařízení <!-- 3775833   -->
Když vytvoříte profil konfigurace zařízení, můžete povolit nebo omezit funkce Microsoft Edge ve Windows 10 a novější zařízení (**konfigurace zařízení** > **profily**  >  **Vytvořit profil** > **Windows 10 a novější** pro platformu > **omezení zařízení** pro typy profilů >  **Prohlížeč Microsoft Edge**). V této aktualizaci nastavení Microsoft Edge jsou více popisné a srozumitelnější. 

Pokud chcete zobrazit tyto funkce, přejděte na [nastavení omezení zařízení s prohlížečem Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser).

Platí pro: Windows 10 a novější

#### <a name="expanded-support-for-android-enterprise-fully-managed-devices--preview-------3903241-3903244-3903246-----"></a>Rozšířenou podporu pro zařízení s Androidem Enterprise, plně spravovaná (Preview)  <!--   3903241, 3903244, 3903246   -->
Stále ve verzi public preview, jsme rozšířili naši podporu zařízení s Androidem Enterprise, plně spravovaná ([poprvé oznámena v lednu. 2019](whats-new.md#week-of-january-14-2019) zahrnout následující: 

- Na plně spravované a vyhrazená zařízení, můžete vytvořit [zásady dodržování předpisů](compliance-policy-create-android-for-work.md) pravidla pro hesla a požadavky na operační systém (**dodržování předpisů zařízením**  >   **Zásady** > **vytvořit zásadu** > **Androidu Enterprise** pro platformu > **vlastník zařízení** pro Typ profilu). 

  Vyhrazená zařízení můžou zařízení zobrazit jako **nevyhovující předpisům**. Podmíněný přístup není k dispozici na vyhrazené zařízení. Ujistěte se, že dokončení libovolné úlohy nebo akce pro získání vyhrazená zařízení kompatibilní s přiřazené zásady.

- [Podmíněný přístup](conditional-access.md) – podmíněný přístup, zásady, které platí pro Android platí také pro Android Enterprise plně spravovaná zařízení. Uživatelé můžou registrovat nyní plně spravovaná zařízení v Azure Active Directory pomocí **aplikace pro Microsoft Intune**. Pak naleznete v tématu a vyřešte všechny problémy dodržování předpisů pro přístup k prostředkům organizace.

- Nový koncový uživatel aplikace (Microsoft Intune app) – je nová koncový uživatel aplikace pro Android je plně spravovaná zařízení, která volá **Microsoft Intune**. Tato nová aplikace je odlehčené a moderní a poskytuje podobné funkce jako aplikace portál společnosti, ale pro plně spravovaná zařízení. Další informace najdete v tématu [aplikace pro Microsoft Intune na webu Google Play](https://play.google.com/store/apps/details?id=com.microsoft.intune).

Nastavení Androidu plně spravovaná zařízení, přejděte na **registrace zařízení** > **registrace zařízení s Androidem** > **uživatele vlastněné společností, plně spravovaná zařízení**. Podpora pro zůstává plně spravovaná zařízení s Androidem ve verzi preview a některé funkce Intune nemusí být plně funkční.  

Další informace o této verzi preview, najdete v našem blogu [Microsoft Intune – náhled 2 pro zařízení s Androidem Enterprise plně spravovaná](https://aka.ms/preview2_AE_fullymanaged).


### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470--wnstaged--"></a>Konfigurace profilu některé obrazovky přeskočte Průvodci nastavením <!-- 2276470  wnstaged-->
Když vytvoříte profil registrace s macOS, můžete nakonfigurovat na některý z následujících obrazovky přeskočit, když uživatel prochází Pomocníka pro instalaci:
- Vzhled
- Tón zobrazení
- iCloudStorage, je-li vytvořit nový profil nebo upravte profil, vybrané přeskočit obrazovky nutnost synchronizovat s Apple MDM server.  Uživatelé můžou vydat ruční synchronizaci zařízení tak, aby se žádné zpoždění v ujímají změny profilu.
Další informace najdete v tématu [automaticky zaregistrovat zařízení s macOS pomocí programu registrace zařízení nebo Apple School Manageru](device-enrollment-program-enroll-macos.md).

#### <a name="bulk-device-naming-when-enrolling-corporate-ios-devices--3566569----"></a>Hromadné zařízení pojmenování při registraci zařízení s Iosem podnikové<!--3566569  -->
Při použití jedné z metod registrace podnikového společnosti Apple (DEP/ABM/ASM), můžete nastavit formát názvu zařízení automaticky název příchozí zařízením s Iosem. Můžete určit formát, který obsahuje typ zařízení a sériové číslo ve vaší šabloně. Chcete-li to provést, zvolte **Intune** > **registrace zařízení** > **registrace Apple** > **programu registrace tokeny** > **vyberte token** >**vytvořit profil** > **formát pojmenování zařízení**. Můžete upravit stávající profily, ale jenom nově synchronizovaných zařízení bude mít název použít.

#### <a name="updated-default-timeout-message-on-enrollment-status-page----3959331---"></a>Aktualizované výchozí časový limit zprávy na stránka stavu registrace <!-- 3959331 -->
Aktualizovali jsme výchozí časový limit zprávy, které uživatelé uvidí, když se stránka stavu registrace (ESP) překročí hodnotu časového limitu, který je specifikovaný v profilu ESP. Nové výchozí zprávu je, co uživatelé uvidí a pomáhá jim pochopit, provedení další akcí s jejich ESP nasazení.  

### <a name="device-management"></a>Správa zařízení

#### <a name="retire-noncompliant-devices-----1827291-----"></a>Vyřazení zařízení nedodržující předpisy  <!-- 1827291   -->
Tato funkce byla odložena a je plánovaná pro budoucí verzi.


### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="intune-data-warehouse-v10-changes-reflecting-back-to-beta----4403765---"></a>Intune Data Warehouse V1.0 změny odráží zpět na verzi beta <!-- 4403765 -->
Verze 1.0 bylo poprvé dostupné ve. 1808, se liší v některých ohledech významné z beta verze rozhraní API. Tyto změny se projeví v 1903 zpět do beta verzi rozhraní API. Pokud máte důležitá sestavy, které používají beta verzi rozhraní API, důrazně doporučujeme přepínání tyto sestavy V1.0, aby se zabránilo rozbíjející změny. Další informace najdete v tématu [protokol změn pro rozhraní API datového skladu Intune](reports-changelog.md#1903-part-2).

#### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Monitorovat stav standardních hodnot zabezpečení (public preview) <!-- 3082047 --> 
Přidali jsme [zobrazení podle kategorií](security-baselines-monitor.md#per-category-view) monitorování standardních hodnot zabezpečení. (Základní nastavení zabezpečení zůstávají ve verzi preview). Podle kategorie zobrazení jednotlivých kategorií ze standardních hodnot společně s procento zařízení, které spadají do skupiny pro každý stav pro danou kategorii. Nyní můžete vidět, kolik zařízení jednotlivých kategorií se neshodují, jsou nesprávně nakonfigurované nebo se nedají použít.

### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="scope-tags-for-apple-vpp-tokens---2371886----"></a>Značky oboru pro tokeny programu Apple VPP <!--2371886  -->
Nyní můžete přidat značky oboru na tokeny programu Apple VPP. Přístup k tokenu Apple VPP s konkrétní značkou budou mít jenom uživatelé, kterým je přiřazená stejnou značku oboru. Aplikace VPP a e-knih pro zakoupit pomocí tohoto tokenu zdědí její klíčová slova oboru. Další informace o značky oboru, naleznete v tématu [značky pomocí RBAC a oboru](scope-tags.md).







## <a name="week-of-april-1-2019"></a>Týden od 1. dubna 2019

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="updated-certificate-connectors-----icm-113304612---"></a>Aktualizovaný certifikát konektory  <!-- ICM 113304612 -->
Vydali jsme aktualizace pro obě [Intune Certificate Connector a konektor certifikátu PFX pro Microsoft Intune](certficates-pfx-configure.md#whats-new-for-connectors). Nové vydání opravy několik známých problémů.  

### <a name="app-management"></a>Správa aplikací

#### <a name="user-experience-update-for-the-company-portal-app-for-ios----2536024---"></a>Aktualizace uživatelského prostředí aplikace portál společnosti pro iOS <!-- 2536024 -->
Domovská stránka aplikace portál společnosti pro zařízení s iOS jsme přepracovali. Díky této změně se na domovské stránce lépe postupujte podle vzorů uživatelského rozhraní pro iOS a také poskytují vylepšili jsme zjistitelnost aplikací a e-knihy.

#### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Změny registrace pomocí portálu společnosti pro uživatele zařízení s Iosem 12 <!--3448635 -->  
Portál společnosti pro iOS registrace obrazovky a kroky byla aktualizována, aby bylo v souladu s MDM změny registrace v Apple iOS 12.2. Aktualizovaný pracovní postup vyzve uživatele k:  

* Povolit Safari otevřít na webu portál společnosti a stáhnout profil pro správu před návratem do aplikace portál společnosti.  
* Otevřete aplikaci nastavení na instalaci profilu správy na svém zařízení.
* Vraťte se do aplikace portál společnosti, aby prošel registrací.  

Postup aktualizované registrace a obrazovky, naleznete v tématu [zaregistrovat zařízení s Iosem v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).  

## <a name="week-of-march-25-2019"></a>Týden od 25. března 2019

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

### <a name="support-for-the-power-bi-compliance-app-from-the-data-warehouse-blade-in-microsoft-intune----4260871---"></a>Podpora pro dodržování předpisů službou Power BI aplikace v okně datového skladu v Microsoft Intune <!-- 4260871 -->
Dříve **soubor stáhněte si Power BI** odkaz v **datový sklad Intune** okno Stáhnout sestavu datového skladu Intune (soubor .pbix). Tato sestava se nahradil údajem aplikace dodržování předpisů službou Power BI. Dodržování předpisů službou Power BI aplikace nebude vyžadovat zvláštní načítání a nastavování. Bude otevírat přímo v Power BI online portálu a zobrazení dat speciálně pro vašeho tenanta Intune na základě vašich přihlašovacích údajů. V Intune, vyberte **nastavení datového skladu Intune** odkaz na pravé straně okna Intune. Potom klikněte na **získat aplikace Power BI**. Další informace najdete v tématu [připojení k datovému skladu pomocí Power BI](reports-proc-get-a-link-powerbi.md).

## <a name="week-of-march-18-2019"></a>Týden od 18. března 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="deploy-microsoft-visio-and-microsoft-project----3725386----"></a>Nasazení aplikace Microsoft Visio a Microsoft Project <!-- 3725386  -->
Teď můžete nasadit aplikaci Microsoft Visio Pro Office 365 a Microsoft Project Online Desktop Client jako aplikace nezávislých na zařízení s Windows 10 pomocí Microsoft Intune, pokud vlastníte příslušné licence pro tyto aplikace. V Intune, vyberte **klientské aplikace** > **aplikace** > **přidat** zobrazíte **přidat aplikaci** okno. Na **přidat aplikaci** okně vyberte **Windows 10** jako **typ aplikace**. Vyberte **konfiguraci sady aplikací** vybrat aplikace k instalaci. Další informace o aplikacích Office 365 pro zařízení s Windows 10 najdete v tématu [aplikace přiřadit Office 365 na zařízení s Windows 10 pomocí Microsoft Intune](apps-add-office365.md).

#### <a name="microsoft-visio-pro-for-office-365-product-name-change----3593653----"></a>Aplikace Microsoft Visio Pro for Office 365 Změna názvu produktu <!-- 3593653  -->
**Aplikace Microsoft Visio Pro for Office 365** se teď označuje jako **Microsoft Visio Online Plan 2**.  Další informace o aplikaci Microsoft Visio, naleznete v tématu [Visio Online Plan 2](https://products.office.com/visio/visio-online-plan-2). Další informace o aplikacích Office 365 pro zařízení s Windows 10 najdete v tématu [aplikace přiřadit Office 365 na zařízení s Windows 10 pomocí Microsoft Intune](apps-add-office365.md).

#### <a name="intune-app-protection-policy-app-character-limit-setting----3291302----"></a>Intune app protection (aplikace) znak limit zásad nastavení <!-- 3291302  -->
Správci Intune můžou určit výjimku pro aplikaci Intune **omezit vyjmutí, kopírování a vkládání v ostatních aplikacích** nastavení zásad.  Jako správce můžete zadat počet znaků, které mohou být vyjmutých nebo zkopírovaných z spravovanou aplikaci. Toto nastavení vám umožní sdílení zadaný počet znaků do žádné aplikace, bez ohledu na to, "omezit vyjmutí, kopírování a vkládání v ostatních aplikacích" nastavení. Upozorňujeme, že verze aplikace portál společnosti Intune pro Android vyžaduje verzi 5.0.4364.0 nebo novější. Další informace najdete v tématu [ochranu dat s Iosem](app-protection-policy-settings-ios.md#data-protection), [ochrany dat pro Android](app-protection-policy-settings-android.md#data-protection), a [kontrola protokolů ochrany aplikace klient](app-protection-policy-settings-log.md#app-protection-policy-settings).

#### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477-----"></a>Nástroj pro nasazení Office (ODT) XML pro nasazení Office ProPlus <!-- 3192477   -->
Budou moci poskytnout nástroj pro nasazení Office (ODT) XML při vytváření instance Office Pro Plus v konzole správce Intune. To vám umožní větší přizpůsobitelnost, pokud existující možnosti uživatelského rozhraní Intune nevyhovují vašim potřebám. Další informace najdete v tématu [aplikace přiřadit Office 365 na zařízení s Windows 10 pomocí Microsoft Intune](https://docs.microsoft.com/intune/apps-add-office365) a [možnosti konfigurace pro nástroj pro nasazení Office](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool).

#### <a name="app-icons-will-now-be-displayed-with-an-automatically-generated-background----1429026----"></a>Ikony aplikací se teď budou zobrazovat s automaticky generovaným pozadím <!-- 1429026  -->
V aplikaci portál společnosti Windows ikony aplikace nyní zobrazí s automaticky generovaným pozadím na základě dominantní barvy ikony (Pokud se dá zjistit). V případě potřeby toto pozadí nahradí šedé ohraničení, která byla dříve vidět na dlaždicích aplikací. Uživatelům se zobrazí tato změna později než 10.3.3451.0 verze portálu společnosti.

#### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523-----"></a>Instalovat dostupné aplikace pomocí aplikace portál společnosti po Windows hromadný zápis <!-- 2751523   -->
Zařízení Windows, která zaregistrovaná v Intune pomocí [Windows hromadnou registraci](windows-bulk-enroll.md) (zřizovacích balíčků) budete moct používat aplikaci portál společnosti instalovat aplikace k dispozici. Další informace o aplikaci portál společnosti, naleznete v tématu [ručně přidat portál společnosti pro Windows 10](store-apps-company-portal-app.md) a [konfigurace aplikace portál společnosti Microsoft Intune](company-portal-app.md).

#### <a name="the-microsoft-teams-app-can-be-selected-as-part-of-the-office-app-suite----3828932----"></a>Aplikace Microsoft Teams lze vybrat jako součást aplikace sady Office <!-- 3828932  -->
Aplikace Microsoft Teams můžete zahrnuty nebo vyloučeny jako součást instalace sady aplikací Office Pro Plus. Tato funkce funguje pro Office Pro Plus číslo 16.0.11328.20116+ sestavení. Uživatel musí odhlásit a pak se přihlaste k zařízení pro dokončení instalace. V Intune, vyberte **klientské aplikace** > **aplikace** > **přidat**. Vyberte jednu z **sada Office 365** typy aplikací a pak vyberte **konfiguraci sady aplikací**.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="automatically-start-an-app-when-running-multiple-apps-in-kiosk-mode-on-windows-10-and-later-devices----2351390---"></a>Automatické spuštění aplikace při spuštění více aplikací na Windows 10 a novější zařízení v celoobrazovkovém režimu. <!-- 2351390 -->

V systému Windows 10 a novější zařízení můžete zařízení v beznabídkovém režimu spouštět a spustit velký počet aplikací. V této aktualizaci se **automatickým spouštěním** nastavení (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **Windows 10 a novější** pro platformu > **veřejného terminálu** pro typy profilů > **veřejný terminál s více aplikacemi**). Pomocí tohoto nastavení můžete automaticky spustit aplikaci, když uživatel přihlásí k zařízení.

Pokud chcete zobrazit seznam a popis všech nastavení beznabídkového režimu, najdete v článku [Windows 10 a novější zařízení nastavení pro spuštění jako veřejný terminál v Intune](kiosk-settings-windows.md).

Platí pro: Windows 10 a novější

#### <a name="operational-logs-also-show-details-on-non-compliant-devices----4063755----"></a>Operační protokoly také zobrazit podrobnosti o zařízení nedodržující předpisy <!-- 4063755  -->
Když směrování Intune přihlásí k funkcím Azure monitor, můžete také směrovat provozní protokoly. V této aktualizaci provozních protokolech také poskytují informace o zařízení nedodržující předpisy. 

Další informace o této funkci najdete v tématu [protokolu odesílání dat do úložiště, služba event hubs nebo log analytics v Intune](review-logs-using-azure-monitor.md).

#### <a name="route-logs-to-azure-monitor-in-more-intune-workloads----3804627---"></a>Směrování protokolů do Azure monitoru v další úlohy Intune <!-- 3804627 -->
V Intune, můžete směrovat do centra událostí, úložiště, audit a provozní protokoly a protokolovat analytics ve službě Azure Monitor (**Intune** > **monitorování** > **diagnostiky nastavení**). Tato aktualizace může směrovat tyto protokoly ve více úloh Intune, včetně dodržování předpisů, konfigurace, klientské aplikace a další. 

Další informace o směrování protokolů do Azure monitoru, naleznete v tématu [odeslat data protokolů do služby storage, služby event hubs nebo protokolování analytics](review-logs-using-azure-monitor.md).

#### <a name="create-and-use-mobility-extensions-on-android-zebra-devices-in-intune----3305880-----"></a>Vytváření a používání rozšíření nastavení mobilních zařízení na zařízeních s Androidem Zebra v Intune <!-- 3305880   -->
V této aktualizaci Intune podporuje konfiguraci zařízení s Androidem Zebra. Konkrétně můžete vytvořit profil konfigurace zařízení a použít nastavení na zařízení s Androidem Zebra pomocí profilů rozšíření Mobility (MX) generovaných StageNow (**konfigurace zařízení**  >   **Profily** > **vytvořit profil** > **Android** pro platformu > **MX profil (jenom Zebra)** profilu Typ).

Další informace o této funkci najdete v tématu [použití a správa zařízení Zebra pomocí rozšíření nastavení mobilních zařízení v Intune](android-zebra-mx-overview.md).

Platí pro: Android

### <a name="device-management"></a>Správa zařízení

#### <a name="encryption-report-for-windows-10-devices-in-public-preview---2351538---"></a>Sestava šifrování pro zařízení s Windows 10 (ve verzi public preview)<!-- 2351538 -->  
Pomocí nové [šifrování sestavu (Preview)](encryption-monitor.md) k zobrazení podrobností o stav šifrování zařízení s Windows 10. Dostupné podrobnosti zahrnují verze čipu TPM zařízení, šifrování připravenost a stav, chybách a další.  

#### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-in-public-preview----2351547-----"></a>Přístupové klíče pro obnovení Bitlockeru z portálu Intune (ve verzi public preview) <!-- 2351547   -->  
Teď můžete pomocí Intune, aby [podrobnosti](encryption-monitor.md) o ID klíče Bitlockeru a klíče pro obnovení Bitlockeru, ze služby Azure Active Directory.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Podpora Microsoft Edge pro scénáře Intune na zařízení iOS a Androidem <!-- 3411007 -->
Microsoft Edge bude podporovat všechny stejné scénáře správy jako Intune Managed Browser a uveďte vylepšení prostředí pro koncové uživatele. Microsoft Edge podnikových funkcí, které jsou povolené prostřednictvím zásad v Intune zahrnují dual-Identity, integraci zásady ochrany aplikací, integrace proxy aplikace Azure a spravovaný Oblíbené položky a zkratky domovské stránky. Další informace najdete v tématu [podpory Microsoft Edge](app-configuration-managed-browser.md#microsoft-edge-support).

#### <a name="exchange-onlineintune-connector-deprecate-support-for-eas-only-devices---3105122----"></a>Konektor systému Exchange Online a Intune přestat poskytovat podporu pro pouze zařízení v EAS <!--3105122  -->
Konzola Intune už podporuje zobrazení a správy EA jen pro zařízení připojená na Exchange Online s Intune Connectoru. Místo toho máte následující možnosti:
- Registrace zařízení do správy mobilních zařízení (MDM)
- Použití zásad ochrany aplikací Intune ke správě svých zařízení
- Použití ovládacích prvků systému Exchange, jak je uvedeno v [klientů a mobilní zařízení v Exchangi Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online)

### <a name="search-the-all-devices-page-for-an-exact-device-by-using-name---4254930---"></a>Vyhledejte všechny stránky zařízení pro zařízení s přesnou pomocí [název] <!--4254930 -->
Teď můžete hledat názvu přesné zařízení. Přejděte na **Intune** > **zařízení** > **všechna zařízení** > do vyhledávacího pole před a za název zařízení {} k vyhledání přesná shoda. Například **{Device12345}** .

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202----"></a>Podpora pro další konektory na stránce Stav Tenanta. <!-- 3617202  -->
[Tenanta stavové stránce](tenant-status.md) teď zobrazuje informace o dalších konektorů, včetně stavu *rozšířené ochrany před internetovými útoky programu Windows Defender* (ATP) a dalším konektorům Mobile Threat Defense.

### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917----"></a>Udělení Intune přístup pro čtení jenom k několik rolí Azure Active Directory <!-- 3637917  -->
Následující role Azure AD je udělen přístup jen pro čtení Intune. Oprávnění udělená role Azure AD mají přednost před oprávněním s Intune řízení přístupu na základě role (RBAC).

Číst pouze přístup k datům auditování Intune:

- Správce dodržování předpisů
- Správce dat dodržování předpisů

Přístup jen ke čtení ke všem datům Intune:

- Správce zabezpečení
- Operátor zabezpečení
- Čtenář zabezpečení

Další informace najdete v tématu [řízení přístupu na základě rolí](role-based-access-control.md).

#### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430-----"></a>Značky oboru pro zřizovací profily aplikací pro iOS <!--2934430   -->
Značka oboru můžete přidat do zřizovacího profilu aplikace iOS tak, aby pouze uživatelé s rolemi také přiřadit značky oboru mít přístup k zřizovací profil aplikace iOS. Další informace najdete v tématu [značky pomocí RBAC a oboru](scope-tags.md).

#### <a name="scope-tags-for-app-configuration-policies---2371891-----"></a>Značky oboru pro zásady Konfigurace aplikací <!--2371891   -->
Značka oboru můžete přidat do zásad Konfigurace aplikace tak, aby pouze uživatelé s rolí také přiřadit značky oboru přístupu pro zásady Konfigurace aplikací. Zásady Konfigurace aplikací můžete pouze cílené na nebo přidružené aplikace přiřazené stejné značka oboru. Další informace najdete v tématu [značky pomocí RBAC a oboru](scope-tags.md).

### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Podpora Microsoft Edge pro scénáře Intune na zařízení iOS a Androidem <!-- 3411007 -->
Microsoft Edge bude podporovat všechny stejné scénáře správy jako Intune Managed Browser a uveďte vylepšení prostředí pro koncové uživatele. Microsoft Edge podnikových funkcí, které jsou povolené prostřednictvím zásad v Intune zahrnují dual-Identity, integraci zásady ochrany aplikací, integrace proxy aplikace Azure a spravovaný Oblíbené položky a zkratky domovské stránky. Další informace najdete v tématu [podpory Microsoft Edge](app-configuration-managed-browser.md#microsoft-edge-support).

## <a name="week-of-february-25-2019"></a>Týden od 25. února 2019

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="intune-powershell-module----951068----"></a>Modul Intune PowerShell <!-- 951068  -->
Modul Intune PowerShell, který poskytuje podporu pro rozhraní Intune API prostřednictvím Microsoft Graphu, je teď dostupná v [Microsoft PowerShell Gallery](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10).

- [Podrobnosti o použití tohoto modulu](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/README.md)
- [Příklady scénářů s použitím tohoto modulu](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/Samples/README.md)

#### <a name="improved-support-for-delivery-optimization----3183757----"></a>Vylepšená podpora pro optimalizaci doručení  <!--3183757  -->
Pro konfiguraci optimalizace doručení jsme rozšířili podporu v Intune. Teď můžete nakonfigurovat rozšířený seznam [nastavení optimalizace doručení](delivery-optimization-settings.md) a vyvíjet aplikace cílené na vaše zařízení přímo z konzoly Intune.


## <a name="week-of-february-18-2019"></a>Týden od 18. února 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355-----"></a>Intune bude využívat služby Google Play API chránit na zařízení s Androidem <!-- 2577355   -->
Někteří správci IT potýkají s na šířku BYOD, kde koncoví uživatelé uvíznout kořenová nebo jailbreaking svůj mobilní telefon. Toto chování, když někdy není nesprávně míněný, výsledkem jednorázové přihlášení řada zásad Intune, které jsou nastaveny, aby bylo možné chránit data vaší organizace na zařízeních koncových uživatelů. Proto Intune poskytuje detekce rootů a jailbreaků pro zařízení zaregistrovaná a zruší. V této vydané verzi bude Intune využívat nyní Google Play ochrana rozhraní API pro přidání do naší stávající zjišťování kontroly kořenové pro neregistrovaná zařízení. Zatímco Google nesdílí rozsahu zjišťování kontroly kořenové, ke kterým dochází, Očekáváme, že tato rozhraní API pro detekci uživatelé, kteří mají jejich zařízení z jakéhokoli důvodu z vlastního nastavení zařízení, abyste mohli získat novější aktualizace operačního systému na starší zařízení s rootem. Tito uživatelé mohou pak blokovat přístup k podnikovým datům, nebo jejich podnikové účty se můžou vymazat z jejich povolené zásadou. Pro další hodnoty, správce IT budou mít několik sestav aktualizací v rámci okna Intune App Protection – "Uživatelé označení příznakem" sestava bude obsahovat, kteří uživatelé jsou zjištěny přes Google Play Protect kontrola SafetyNet API "Potenciálně škodlivé aplikace" sestavy se Zobrazit aplikace, které jsou zjištěny prostřednictvím ověření aplikace rozhraní API společnosti Google skenování. Tato funkce je dostupná v systému Android.

#### <a name="win32-app-information-available-in-troubleshooting-blade----2617342-----"></a>Informace pro aplikace Win32 k dispozici v okně řešení potíží <!-- 2617342   -->
Lze shromažďovat soubory protokolů selhání instalace aplikace Win32 z aplikace Intune **Poradce při potížích s** okno. Další informace o řešení potíží s instalací aplikace najdete v tématu [řešit problémy při instalaci aplikace](troubleshoot-app-install.md) a [Win32 řešení problémů s aplikací](apps-win32-app-management.md#troubleshoot-win32-app-issues).

#### <a name="app-status-details-for-ios-apps----3761235-----"></a>Podrobnosti o stavu aplikace pro aplikace pro iOS <!-- 3761235   -->
Existují nové aplikace instalace chybové zprávy související s tímto:
- Selhání aplikace VPP při instalaci na sdílený iPad
- Chyba při app storu je zakázaná.
- Nepodařilo se najít licence VPP pro aplikaci
- Selhání instalace aplikace pro systém s poskytovatele řešení MDM.
- Nepodařilo se nainstalovat aplikace, když je zařízení v režimu ztráty nebo celoobrazovkový režim
- Nepodařilo se nainstalovat aplikaci, když uživatel není přihlášen k App Store

V Intune, vyberte **klientské aplikace** > **aplikace** > "Název aplikace" > **stav instalace zařízení**. Bude k dispozici v nové chybové zprávy **podrobnosti o stavu** sloupce.

#### <a name="new-app-categories-screen-in-the-company-portal-app-for-windows-10---3834780----"></a>Nová obrazovka kategorie aplikací v aplikaci portál společnosti pro Windows 10<!-- 3834780  -->
Volá se nová obrazovka **kategorie aplikací** byla přidána ke zlepšení prostředí procházení a výběr aplikací v aplikaci portál společnosti pro Windows 10. Uživatelé nyní uvidí svoje aplikace, seřazený podle kategorií, jako **doporučené**, **vzdělávání**, a **produktivitu**. Tato změna se zobrazí v aplikaci portál společnosti verze 10.3.3451.0 a novější. Chcete-li zobrazit novou obrazovku, naleznete v tématu [co je nového v Uživatelském rozhraní aplikace](https://docs.microsoft.com/intune/whats-new-app-ui). Další informace o aplikacích v aplikaci portál společnosti, naleznete v tématu [nainstalovat a sdílejte aplikace na zařízení](/intune-user-help/install-apps-cpapp-windows).  

#### <a name="power-bi-compliance-app----1455231-doc-work-item---"></a>Dodržování předpisů aplikace Power BI <!-- 1455231 doc-work-item -->
Přístup k datovému skladu Intune pomocí Power BI Online [dodržování předpisů v Intune (datový sklad)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) aplikace. V této aplikaci Power BI můžete nyní přístup k a sdílet předem vytvořených sestav bez nastavení a aniž byste museli opustit ve webovém prohlížeči. Další informace najdete v tématu [protokol změn – dodržování předpisů službou Power BI aplikace](reports-changelog.md#power-bi-compliance-app).


### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675-----"></a>Skripty prostředí PowerShell můžete spustit na hostiteli 64-bit na 64bitových zařízeních <!-- 1862675   -->
Při přidání skriptu prostředí PowerShell do konfiguračního profilu zařízení se skript spustí vždy v 32bitové i v 64bitových operačních systémech. S touto aktualizací správce můžete spustit skript v hostitelském prostředí PowerShell 64-bit na 64bitových zařízeních (**konfigurace zařízení** > **skripty prostředí PowerShell**  >   **Přidat** > **konfigurovat** > **spuštění skriptu v 64bitovém hostitele prostředí PowerShell**).

Další podrobnosti o použití prostředí PowerShell najdete v tématu [Powershellové skripty do Intune](intune-management-extension.md).

Platí pro: Windows 10 a novější

#### <a name="macos-users-are-prompted-to-update-their-password----1873216---"></a>macOS uživatelům se výzva k aktualizaci hesla <!-- 1873216 -->
Vynucování Intune **ChangeAtNextAuth** nastavení na zařízení s macOS. Toto nastavení má vliv na koncové uživatele a zařízení, která mají zásady dodržování předpisů pro hesla nebo profily omezení zařízení s heslem. Koncovým uživatelům se výzva jednou aktualizovat své heslo. Tuto výzvu dojde pokaždé, když se uživatel poprvé spustí úlohu, která vyžaduje ověření, jako je například přihlášení k zařízení. Uživatelé mohou také vyzváni k aktualizovat své heslo, když teď zrovna nic nedělá, která vyžaduje oprávnění správce, například požadavek na přístup do řetězce klíčů. 

Jakákoli změna zásady nové nebo stávající heslo správce vyzve koncovým uživatelům aktualizovat své heslo.

Platí pro:  
macOS

#### <a name="assign-scep-certificates-to-a-userless-macos-device-----2340521----"></a>Přiřadit zařízení bez uživatelů macOS certifikáty SCEP  <!-- 2340521  -->
Můžete přiřadit certifikát protokolu SCEP (Simple Enrollment) certifikáty pomocí atributů zařízení pro zařízení s macOS, včetně zařízení bez přidružení uživatele a přiřadit profil certifikátu Wi-Fi nebo profily sítě VPN. Tím se rozšiřují podporu jsme již [přiřadit zařízení bez přidružení uživatele s certifikáty SCEP](certificates-scep-configure.md#create-a-scep-certificate-profile) , na kterých běží Windows, iOS a Android.  Tato aktualizace přidává možnost vybrat si certifikát typu *zařízení* při konfiguraci profilu certifikátu SCEP systému MacOS.

Platí pro: 
- macOS

#### <a name="intune-conditional-access-ui-update------2432313-----"></a>Aktualizace podmíněného uživatelského přístupu k Intune   <!-- 2432313   -->
Vylepšili jsme do uživatelského rozhraní pro podmíněný přístup v konzole Intune. Mezi ně patří:
-  Nahradí Intune *podmíněného přístupu* okna okno ze služby Azure Active Directory. To zajistí, že budete mít přístup k široké spektrum nastavení a konfigurace pro [podmíněného přístupu](conditional-access.md) (které zůstává technologie Azure AD), z konzoly v Intune. 
- Jsme jste přejmenovali *přístup k místnímu* okna *přístup k Exchangi*a přemístění *konektoru služby Exchange* instalační program pro toto okno byl přejmenován.  Tato změna konsoliduje, kde jste [konfigurovat a monitorovat podrobnosti související s Exchange online a místně](exchange-connector-install.md).  

#### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135-----"></a>Prohlížeč beznabídkového režimu a prohlížeče Microsoft Edge aplikace můžou běžet na zařízeních s Windows 10 v celoobrazovkovém režimu. <!-- 2935135   -->
Zařízení s Windows 10 můžete použít v beznabídkovém režimu spouštět jedna aplikace nebo velký počet aplikací. Tato aktualizace zahrnuje několik změn pomocí aplikace prohlížeče v režimu veřejného terminálu, včetně:

- Přidat do prohlížeče Microsoft Edge nebo prohlížeči Kiosk spuštěné jako aplikace na zařízení beznabídkového režimu (**konfigurace zařízení** > **profily** > **nový profil**  >  **Windows 10 a novější** pro platformu > **veřejného terminálu** pro typ profilu).
- Nové funkce a nastavení jsou k dispozici pro povolení nebo zakázání (**konfigurace zařízení** > **profily** > **nový profil**  >  **Windows 10 a novější** pro platformu > **omezení zařízení** pro typ profilu), včetně:

  - Prohlížeč Microsoft Edge:
  - Režim veřejného terminálu použijte Microsoft Edge
  - Aktualizujte prohlížeč po nečinnosti

 - Oblíbené položky a hledání:
  - Povolit změny v hledání modulu

Seznam nastavení najdete v tématu:

- [Windows 10 a novější zařízení nastavení pro spuštění jako jako veřejný terminál](kiosk-settings-windows.md)
- [Omezení zařízení prohlížeče Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser)
- [Oblíbené položky a omezení hledání zařízení](device-restrictions-windows-10.md##favorites-and-search)

Platí pro: Windows 10 a novější

#### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774-----"></a>Nová nastavení omezení zařízení pro zařízení s Iosem a macOS <!-- 3448774   -->
Můžete omezit některá nastavení a funkcí na zařízeních s iOS a macOS (**konfigurace zařízení** > **profily** > **nový profil**  >  **iOS** nebo **macOS** pro platformu > **omezení zařízení** pro typ profilu). Tato aktualizace přidává další funkce a nastaveních, pomocí kterých můžete řídit, včetně nastavení času obrazovky, změna karty eSIM a mobilní plány a další nastavení na zařízeních s Iosem. Také přičemž dojde ke zpoždění uživatele viditelnost aktualizace softwaru a blokování ukládání obsahu do mezipaměti na zařízeních s macOS. 

Pokud chcete zobrazit, funkcích a nastaveních, pomocí kterých můžete omezit, naleznete v tématu:

- [nastavení omezení zařízení s Iosem](device-restrictions-ios.md)
- [nastavení omezení zařízení s macOS](device-restrictions-macos.md)

Platí pro:

- iOS
- macOS

#### <a name="kiosk-devices-are-now-called-dedicated-devices-on-android-enterprise-devices----3598402-----"></a>Zařízení v "celoobrazovkovém režimu" se teď nazývají "Vyhrazená zařízení" v zařízeních s Androidem Enterprise <!-- 3598402   -->
Aby bylo v souladu s Androidem terminologií **veřejného terminálu** se změní na **vyhrazená zařízení** pro zařízení s Androidem enterprise (**konfigurace zařízení**  >  **Profily** > **vytvořit profil** > ** pro platformu Android enterprise > **pouze vlastník zařízení** > **zařízení Omezení** > **vyhrazená zařízení**).

Pokud chcete zobrazit dostupná nastavení, přejděte na [nastavení zařízení a povolení nebo zakázání funkce](device-restrictions-android-for-work.md#dedicated-device-settings).

Platí pro:  
Android Enterprise

#### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850-3803313-----"></a>Safari a odložením uživatele aktualizace softwaru iOS viditelnost, které nastavení se přesouvají v Uživatelském rozhraní Intune <!-- 3640850, 3803313   -->
Pro zařízení s Iosem můžete nastavit Safari, nastavení a konfigurace aktualizací softwaru. V této aktualizaci se tato nastavení přesouvají do různých částí uživatelského rozhraní Intune:

- Nastavení prohlížeče Safari přesunuta z **Safari** (**konfigurace zařízení** > **profily** > **nový profil**  >  **iOS** pro platformu > **omezení zařízení** pro typy profilů) k  **[integrované aplikace](device-restrictions-ios.md#built-in-apps)** .
- **Zpoždění viditelnost aktualizace softwaru uživatele pro zařízení s Iosem pod dohledem** nastavení (**aktualizace softwaru** > **aktualizovat zásady pro iOS**) přechází na  **Omezení zařízení** >  **[Obecné](device-restrictions-ios.md#general)** .  Podrobnosti o vlivu na existující zásady najdete v tématu [aktualizace softwaru iOS](software-updates-ios.md#configure-the-policy). 

Seznam nastavení najdete v tématu:

- [omezení zařízení s Iosem](device-restrictions-ios.md) 
- [aktualizace softwaru v Iosu](software-updates-ios.md)

Tato funkce platí pro: 

- iOS

#### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164-----"></a>Povolení omezení v nastavení zařízení bylo přejmenováno na čas obrazovky na zařízeních s Iosem <!-- 3699164   -->
Můžete nakonfigurovat **povolení omezení v nastavení zařízení** na hlídaných zařízeních s Iosem (**konfigurace zařízení** > **profily**  >  **Nový profil** > **iOS** pro platformu > **omezení zařízení** pro typy profilů > **Obecné**). V této aktualizaci se toto nastavení bylo přejmenováno na **čas obrazovky (jenom pod dohledem)** . 

Chování je stejné. Konkrétně: 

- iOS 11.4.1 a dříve: **Blok** zabrání koncovým uživatelům vlastní omezení v nastavení zařízení. 
- iOS 12,0 a novější: **Blok** koncovým uživatelům zabrání v nastavení své vlastní **obrazovky čas** v nastavení zařízení, včetně omezení obsahu a ochrana osobních údajů. Zařízení upgradovat operační systém na iOS 12.0 už nezobrazí na kartě omezení v nastavení zařízení. Tato nastavení jsou v **obrazovky čas**. 

Seznam nastavení najdete v tématu [omezení zařízení s Iosem](device-restrictions-ios.md#general).

Platí pro: 
- iOS


### <a name="device-management"></a>Správa zařízení

#### <a name="rename-an-enrolled-windows-device----1911112----"></a>Přejmenovat zaregistrovaná zařízení s Windows <!-- 1911112  -->
Nyní můžete přejmenovat zaregistrovaná zařízení s Windows 10 (RS4 nebo novější). Chcete-li provést, zvolte **Intune** > **zařízení** > **všechna zařízení** > zvolte zařízení > **přejmenování zařízení**. Tato funkce v současné době nepodporuje přejmenování zařízení hybridní Windows Azure AD.

#### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Umožňuje automaticky přiřazovat značky oboru na prostředky vytvořené v rámci správce v tomto oboru <!-- 3173823  -->
Když správce vytvoří prostředek, všechny značky oboru přiřazeno správce automaticky přiřadí tyto nové prostředky.

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202----"></a>Sestava selhání registrace přesune do okna pro registraci zařízení <!-- 3560202  -->
**Nepovedlo registrace** sestava byla přesunuta do **monitorování** část **registrace zařízení** okno. Přidali jsme dva nové sloupce (způsob registrace a verze operačního systému).

#### <a name="company-portal-abandonment-report-renamed-to-incomplete-user-enrollments---3815076-eemiss---"></a>Firemní portál zřeknutí sestavy přejmenován na nekompletní uživatele registrací <!--3815076 eemiss -->
**Portál společnosti zřeknutí** sestava byla přejmenována na **registrací neúplné uživatele**.


<!-- ########################## -->
## <a name="week-of-february-4-2019"></a>Týden od 4. února 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="intune-macos-company-portal-dark-mode----3300524----"></a>MacOS tmavě režimu portál společnosti Intune <!-- 3300524  -->
Portál společnosti pro macOS Intune teď podporuje tmavě režim pro macOS. Když zapnete režim tmavé na zařízení s macOS 10.14 +, portál společnosti upraví jeho vzhled barvy, které odpovídají tohoto režimu.

<!-- ########################## -->
## <a name="week-of-january-21-2019"></a>Týden od 21. ledna 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Informační zprávy pro aplikace Win32 <!-- 3136566   -->
Můžete potlačit oznámení informační zprávy zobrazující koncový uživatel za přiřazení aplikace. V Intune, vyberte **klientské aplikace** > **aplikace** > vyberte aplikaci > **přiřazení** > **zahrnout skupiny**. 

#### <a name="intune-app-protection-policies-ui-update----3251427----"></a>Aktualizace uživatelského rozhraní zásad ochrany aplikací Intune <!-- 3251427  -->
Popisky pro nastavení a tlačítka pro Intune app protection srozumitelnější každý jsme změnili. Některé změny patří:  
- Ovládací prvky se změnil z **Ano** / **žádné** ovládacích prvků do primárně **bloku** / **povolit** a **zakázat** / **povolit** ovládacích prvků. Popisky jsou také aktualizovány.  
- Nastavení přeformátovali, takže nastavení s popiskem jsou vedle sebe v ovládacím prvku, poskytují lepší navigace.   

Výchozí nastavení a několik položek nastavení zůstávají stejné, ale tato změna umožňuje uživatelům pochopit, navigace a využívat další nastavení snadno a použít zásady ochrany aplikací vybrané. Informace najdete v tématu [nastavení iOS](app-protection-policy-settings-ios.md) a [nastavení Androidu](app-protection-policy-settings-android.md).

### <a name="additional-settings-for-outlook----3301182----"></a>Další nastavení pro aplikaci Outlook <!-- 3301182  -->
Teď můžete nakonfigurovat následující dodatečná nastavení pro aplikaci Outlook pro iOS a Android pomocí Intune:

- Povolte jenom pracovní nebo školní účty, který se má použít v aplikaci Outlook v Iosu a Androidu
- Nasazení moderní ověřování Office 365 a hybridním moderním ověřováním místních účtů
- Použití `SAMAccountName` pro pole uživatelské jméno v e-mailový profil, pokud je vybrána základní ověřování
- Povolit kontakty, které chcete uložit
- Konfigurace externího příjemce upozornění než odešlete
- Konfigurace **zaměřuje doručené pošty**
- Vyžadovat biometrické údaje pro přístup k aplikaci Outlook pro iOS
- Blokovat externí obrázky

> [!NOTE]
> Pokud používáte zásady ochrany aplikací Intune pro správu přístupu pro podnikové identity, měli byste zvážit, ne povolení **vyžadují biometrika**. Další informace najdete v tématu **vyžadovat pro přístup podnikové přihlašovací údaje** pro [nastavení přístupu pro iOS](app-protection-policy-settings-ios.md#access-requirements) a [nastavení přístupu pro Android](app-protection-policy-settings-android.md#access-requirements).

Další informace najdete v tématu [nastavení konfigurace aplikace Microsoft Outlook](app-configuration-policies-outlook.md).

#### <a name="delete-android-enterprise-apps----1352553---"></a>Odstranění aplikací Androidu Enterprise <!-- 1352553 -->
Spravované aplikace Google Play můžete odstranit ze služby Microsoft Intune. Pokud chcete odstranit spravovanou aplikaci služby Google Play, otevřete Microsoft Intune v Azure portal a vyberte **klientské aplikace** > **aplikace**. Ze seznamu aplikací vyberte symbol tří teček (...) napravo od spravované aplikace Google Play a potom vyberte **odstranit** ze zobrazeného seznamu. Když odstraníte spravované aplikace Google Play ze seznamu aplikací, je automaticky neschválených spravované aplikace Google Play.

#### <a name="managed-google-play-app-type----1352580---"></a>Typ aplikace Google Play spravované <!-- 1352580 -->
**Spravované Google Play** typ aplikace vám umožní konkrétně přidat [spravované aplikace Google Play](https://play.google.com/work/search?q=microsoft&c=apps) do Intune. Jako správce Intune teď můžete procházet, Hledat, schválit, synchronizaci a přiřazení aplikací v Intune schválené spravovaného obchodu Google Play.  Už nemusíte procházet spravovanou konzolu Google Play samostatně a donutit k už máte.  V Intune, vyberte **klientské aplikace** > **aplikace** > **přidat**. V **typ aplikace** seznamu vyberte **spravovaný obchod Google Play** jako typ aplikace.

### <a name="default-android-pin-keyboard----3802457---"></a>Výchozí Android PIN klávesnice <!-- 3802457 -->
Pro koncové uživatele, kteří na svých zařízeních s Androidem se PIN kód typu "Číselná" nastavili App Protection zásad (PIN aplikace Intune) zobrazí se nyní výchozí Android klávesnice místo pevné Android klávesnice uživatelského rozhraní, která dříve byla navržena. Tato změna byla provedena, aby byla konzistentní při použití výchozí klávesnice v Androidu a iOS, pro oba typy kódu PIN, "Číselná" nebo "Heslo". Další informace o nastavení přístup koncového uživatele na Androidu, jako je například PIN kód aplikace, najdete v části [požadavky na přístup Android](app-protection-policy-settings-android.md#access-requirements).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="use-microsoft-recommended-settings-with-security-baselines-public-preview----2055484-----"></a>Nastavení Microsoft doporučuje používat směrné plány zabezpečení (Public Preview) <!-- 2055484   -->

Intune se integruje s dalšími službami, které se zaměřují na zabezpečení, včetně Ochrany ATP v programu Windows Defender a Ochrany ATP v Office 365. Zákazníci požadují ve službách Microsoft 365 společnou strategii a soudržnější sadu ucelených bezpečnostních pracovních postupů. Naším cílem je srovnat strategie tak, abychom mohli vytvářet řešení přemosťující operace zabezpečení a běžné úlohy správy. V Intune se snažíme tohoto cíle dosáhnout prostřednictvím publikování sady Standardních hodnot zabezpečení doporučených Microsoftem (**Intune** > **Standardní hodnoty zabezpečení**).  Správce můžete vytvořit zásady zabezpečení přímo z těchto standardních hodnot a pak je nasadit na svoje uživatele. Můžete také přizpůsobit doporučení osvědčených postupů pro potřeby vaší organizace. Intune zajišťuje, že zařízení zůstávají v souladu s těmito standardními hodnotami, a upozorní správce, pokud uživatelé nebo zařízení tyto hodnoty nedodržují.

Tato funkce je ve verzi public preview, takže všechny profily vytvořené nyní nebude přesunout do standardních hodnot zabezpečení šablony, které jsou všeobecně dostupná (GA). Plánujete by neměly používat tyto šablony ve verzi preview v produkčním prostředí.

Další informace o standardních hodnot zabezpečení najdete v tématu [vytvoření standardních hodnot zabezpečení Windows 10 v Intune](security-baselines-monitor.md).

Tato funkce platí pro: Windows 10 a novější

#### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379-----"></a>Non-správci mohou povolit nástroj BitLocker na zařízeních s Windows 10 připojená k Azure AD<!-- 2147379   -->
Když povolíte nastavení nástroje BitLocker na zařízeních s Windows 10 (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **Windows 10 a novější** pro platformu > **Endpoint protection** pro typy profilů > **šifrování Windows**), přidejte nastavení Bitlockeru. 

Tato aktualizace zahrnuje nové nastavení nástroje BitLocker umožňuje standardní uživatelé (bez oprávnění správce), aby šifrování povolil. 

Chcete-li nastavení zobrazit, přejděte na [nastavení služby Endpoint protection pro Windows 10](endpoint-protection-windows-10.md#windows-encryption).

#### <a name="check-for-configuration-manager-compliance----2192052--eepublished----"></a>Zkontrolovat dodržování předpisů v Configuration Manageru <!-- 2192052  eepublished  -->
Tato aktualizace zahrnuje novým nastavením dodržování předpisů System Center Configuration Manager (**dodržování předpisů zařízením** > **zásady** > **vytvořit zásadu**  >  **Windows 10 a novější** > **dodržování předpisů v Configuration Manageru**). Configuration Manager bude posílat signály funkci dodržování předpisů v Intune. Pomocí tohoto nastavení můžete vyžadovat všechny signály nástroje Configuration Manager k vrácení "kompatibilní".

Můžete například vyžadovat, aby v zařízeních byly nainstalované všechny aktualizace softwaru. V Configuration Manageru má tento požadavek stav Nainstalováno. Pokud jsou všechny programy na zařízení v neznámém stavu, je zařízení nedodržují předpisy v Intune.

[Dodržování předpisů v Configuration Manageru](compliance-policy-create-windows.md#configuration-manager-compliance) popisuje toto nastavení.

Platí pro: Windows 10 a novější

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324-----"></a>Přizpůsobení tapeta na zařízeních s Iosem pod dohledem pomocí konfiguračního profilu zařízení <!-- 2809324   -->
Když vytvoříte profil konfigurace zařízení pro zařízení s Iosem, můžete přizpůsobit některé funkce (**konfigurace zařízení** > **profily** > **Create profil** > **iOS** pro platformu > **funkcí na zařízeních** pro typ profilu). Tato aktualizace zahrnuje nové **tapeta** nastavení, které umožňují správcům použít image ve formátu PNG, JPG nebo JPEG na domovské obrazovce nebo zamykací obrazovce. Tato nastavení tapeta platí jenom pro zařízení pod dohledem. 

Seznam nastavení najdete v tématu [nastavení funkcí zařízení s Iosem](ios-device-features-settings.md).

#### <a name="windows-10-kiosk-is-generally-available----3594661----"></a>Veřejný terminál Windows 10 je obecně dostupná <!-- 3594661  -->
V této aktualizaci funkce veřejného terminálu na Windows 10 a novější zařízení je všeobecně dostupná (GA). Pokud chcete zobrazit všechna nastavení, můžete přidávat a konfigurovat, najdete v článku [nastavení beznabídkového režimu pro Windows 10 (a novější)](kiosk-settings.md).

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396-----"></a>Sdílení kontaktů přes Bluetooth se už v omezení zařízení > vlastník zařízení pro Android Enterprise <!-- 3598396   -->
Když vytvoříte profil omezení zařízení pro zařízení s Androidem Enterprise, je **sdílení kontaktů přes Bluetooth** nastavení. V této aktualizaci **sdílení kontaktů přes Bluetooth** odebrat nastavení (**konfigurace zařízení** > **profily**  >   **Vytvoření profilu** > **Androidu Enterprise** pro platformu > **omezení zařízení > vlastník zařízení** pro typy profilů > **obecné** ). 

**Sdílení kontaktů přes Bluetooth** nastavení není podporováno pro vlastníka zařízení s Androidem Enterprise management. Takže při odebrání tohoto nastavení neovlivní žádné zařízení ani tenantů, i když toto nastavení je povolena a konfigurována ve vašem prostředí.

Pokud chcete zobrazit aktuální seznam nastavení, přejděte na [nastavení zařízení s Androidem Enterprise a povolení nebo zakázání funkce](device-restrictions-android-for-work.md).

Platí pro: Vlastník zařízení s androidem Enterprise

### <a name="device-management"></a>Správa zařízení

#### <a name="selective-wipe-support-for-wip-without-enrollment-devices----1434452---"></a>Podpora selektivní vymazání pro WIP bez registrace zařízení <!-- 1434452 -->
Windows Information Protection bez registrace (NV-jsme) umožňuje zákazníkům, aby chránili firemní data na zařízeních s Windows 10 bez nutnosti úplné registraci MDM. Jakmile jsou dokumenty chránit pomocí WIP-zásad jsme chráněných dat selektivně vymažou microsoftem nebo správcem Intune. Výběr uživatelů a zařízení, a odešlete žádost o vymazání, všechna data, která byla chráněných pomocí WIP-zásad jsme už nepůjdou použít. V Intune na portálu Azure Portal vyberte **Mobilní aplikace** > **Selektivní vymazání aplikace**.

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="new-operational-logs-and-ability-to-send-logs-to-azure-monitor-services----3762211----"></a>Novou provozní protokoly a možnost odesílat protokoly do služby Azure Monitor <!-- 3762211  -->
Intune poskytuje protokolování integrované auditu, která sleduje události, jakmile jsou provedeny změny. Tato aktualizace zahrnuje nové funkce protokolování, včetně: 
- Operační protokoly (preview), které ukazují na uživatele a zařízení, která zaregistrovaná, včetně úspěšných a neúspěšných pokusů o podrobnosti.
- Protokoly auditu a provozní protokoly je možné odeslat k monitorování Azure, včetně účtů úložiště, služba event hubs a protokolu analytics. Tyto služby umožňují ukládat, použijte analýzy, jako jsou Splunk a QRadar a zobrazit vizualizaci dat protokolování.

[Odeslat data protokolů do služby storage, služby event hubs, nebo se přihlaste analytics Intune](review-logs-using-azure-monitor.md) poskytuje další informace o této funkci.

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509----"></a>Přeskočit další obrazovky Pomocníka s nastavením nastavení na zařízení s Iosem <!-- 2687509  -->
Kromě obrazovky, které se aktuálně můžete přeskočit můžete nastavit zařízení DEP, přejděte na následující obrazovce v nastavením když se uživatel zaregistruje zařízení s Iosem: Zobrazení tón, ochrany osobních údajů, Android migrace, tlačítko Domů, iMessage & FaceTime, připojení, sledování migrace, vzhled, čas obrazovky, aktualizace softwaru, SIM instalace.
Zvolte, které obrazovky přeskočte, přejděte na **registrace zařízení** > **registrace Apple** > **tokeny programu registrace** > zvolte token > **Profily** > zvolte profil > **vlastnosti** > **Pomocníka pro nastavení přizpůsobení** > zvolte **skrýt**  pro všechny obrazovky, které chcete nechat Přeskočit > **OK**.
Je-li vytvořit nový profil nebo upravte profil, přeskočte vybrané obrazovky nutnost synchronizovat s Apple MDM server. Uživatelé můžou vydat ruční synchronizaci zařízení tak, aby se žádné zpoždění v ujímají změny profilu.

#### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Aplikace pro Android Enterprise-jsme nasazení aplikace <!-- 1171203 -->
Pro zařízení s Androidem v neregistrovaných ochrany zásady bez registrace aplikace (APP-jsme) scénář nasazení, můžete teď použít spravované Google Play pro nasazení aplikací pro store a obchodních aplikací pro uživatele. Konkrétně můžete poskytnout koncovým uživatelům aplikace katalogu a instalace prostředí, které už vyžaduje, aby koncoví uživatelé zmírnit stav zabezpečení svých zařízeních tím, že instalace z neznámých zdrojů. Kromě toho tento scénář nasazení bude poskytovat Vylepšené uživatelské prostředí.

<!-- ########################## -->
## <a name="week-of-january-14-2019"></a>Týden od 14. května 2019

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Ve verzi Preview podpory pro vlastněných společností, plně spravovaná zařízení s Androidem <!-- 1574342  -->
Intune teď podporuje zařízení s Androidem, firemním vlastnictví plně spravovaná "vlastník zařízení" scénář, ve kterém zařízení úzce spravuje IT a jste spojeni jednotlivým uživatelům. To umožňuje správcům spravovat celé zařízení, vynucovat ochranu před rozsahem rozšířené ovládací prvky zásad, není k dispozici pro pracovní profily a instalaci aplikací ze spravovaného obchodu Google Play pouze omezení pro uživatele. Další informace najdete v tématu [Intune nastavit registraci androidu plně spravovaná zařízení](android-fully-managed-enroll.md) a [zaregistrujete své zařízení vyhrazená nebo plně spravovaná zařízení](android-dedicated-devices-fully-managed-enroll.md).  Mějte prosím na paměti, že tato funkce je ve verzi preview. Některé funkce Intune, jako jsou certifikáty, dodržování předpisů a podmíněného přístupu nejsou aktuálně k dispozici pro Android je plně spravovaná zařízení uživatelů.

<!-- ########################## -->
## <a name="week-of-january-7-2019"></a>Týden od 7. ledna 2019

### <a name="app-management"></a>Správa aplikací

#### <a name="intune-app-pin----2298397---"></a>PIN aplikace Intune <!-- 2298397 -->
Jako správce IT vám teď můžete nakonfigurovat počet dní, po které koncový uživatel počkat, až pro aplikaci Intune, které se musí změnit PIN kód. Toto nové nastavení představuje *PIN reset Service, za kolik dní* a je k dispozici na webu Azure Portal tak, že vyberete **Intune** > **klientské aplikace**  >   **Zásady ochrany aplikací** > **vytvořit zásadu** > **nastavení** > **požadavkynapřístup**. K dispozici pro [iOS](app-protection-policy-settings-ios.md) a [Android](app-protection-policy-settings-android.md) zařízení, tato funkce podporuje kladné celé číslo.


#### <a name="intune-device-reporting-fields----2748738---"></a>Zařízení v Intune polí pro vytváření sestav <!-- 2748738 -->
Intune poskytuje další zařízení polí, včetně ID registrace aplikace, s Androidem výrobce, model a verzi opravy zabezpečení, jakož i modelu iOS, který pro vytváření sestav. V Intune najdete tato pole jsou dostupné tak, že vyberete **klientské aplikace** > **stav ochrany aplikace** a zvolíte **sestava ochrany aplikací: iOS, Android**. Kromě toho tyto parametry můžete nakonfigurovat **povolit** seznamu pro výrobce zařízení (Android), **povolit** seznam pro model zařízení (Android a iOS) a minimální opravu zabezpečení Androidu nastavení verze. 


### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Šablony pro správu jsou ve verzi public preview a přesunout do své vlastní konfigurační profil <!-- 3322847 -->

Šablony pro správu v Intune (**konfigurace zařízení** > **šablony pro správu**) jsou aktuálně ve verzi public preview. Od této aktualizace:

- Šablony pro správu zahrnují přibližně 300 nastavení, které jde spravovat v Intune. Dříve tato nastavení existuje pouze v editoru zásad skupiny.
- Šablony pro správu jsou k dispozici ve verzi public preview.
- Šablony pro správu se přesouvají z **konfigurace zařízení** > **šablony pro správu** k **konfigurace zařízení**  >   **Profily** > **vytvořit profil** > v **platformy**, zvolte **Windows 10 a novější** > v **profilu typ**, zvolte **šablony pro správu**.
- Vytváření sestav je povoleno

Další informace o této funkci, přejděte na [Windows 10 šablon ke konfiguraci nastavení zásad skupiny](administrative-templates-windows.md).

Platí pro: Windows 10 a novější

#### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user-----1333642---"></a>Použít S/MIME k šifrování a podepisování více zařízení pro uživatele  <!-- 1333642 -->
Tato aktualizace zahrnuje šifrování S/MIME e-mailů pomocí nového profilu importovaného certifikátu (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > vyberte platformu > typ profilu **Importovaný certifikát PKCS**). V Intune můžete importovat certifikáty ve formátu PFX. Intune pak může doručit stejné certifikáty do více zařízení zaregistrovaných jedním uživatelem. To také zahrnuje:
- Nativní e-mailový profil v iOS podporuje povolení šifrování S/MIME pomocí importovaných certifikátů ve formátu PFX.
- Nativní poštovní aplikace na zařízeních se systémem Windows Phone 10 automaticky použije certifikát S/MIME.
- Privátní certifikáty je možné doručit na různé platformy. Některé e-mailové aplikace ale S/MIME nepodporují.
- Na jiných platformách může být nutné ručně nakonfigurovat e-mailovou aplikaci a povolit S/MIME.  
- E-mailové aplikace, které podporují šifrování S/MIME, můžou zpracovávat načítání certifikátů pro šifrování S/MIME e-mailů způsobem, který MDM nepodporuje (například ho načítají z úložiště certifikátů svého vydavatele).
Další informace o této funkci najdete v tématu [přehled S/MIME k podepisování a šifrování e-mailu](certificates-s-mime-encryption-sign.md).
Podporované platformy: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Nové možnosti, které automaticky připojit a zachovat pravidla při použití nastavení DNS na Windows 10 a novější zařízení <!-- 1333665, 2999078 -->
V systému Windows 10 a novější zařízení můžete vytvořit konfigurační profil sítě VPN, který obsahuje seznam serverů DNS přeložit domén, třeba contoso.com. Tato aktualizace zahrnuje nové nastavení pro překlad adres (**konfigurace zařízení** > **profily** > **vytvořit profil** > zvolit  **Windows 10 a novější** pro platformu > zvolit **VPN** pro typy profilů > **nastavení DNS** >**přidat**): 
- **Automaticky se připojovat**: Když **povoleno**, zařízení se automaticky připojí k síti VPN, když zařízení kontaktuje domény můžete zadat, třeba contoso.com.
- **Trvalé**: Ve výchozím nastavení všechna pravidla tabulky (IP adres NRPT) název zásady překladu IP adres jsou aktivní, tak dlouho, dokud se zařízení připojí pomocí tohoto profilu sítě VPN. Pokud je toto nastavení **povoleno** u pravidla tabulky NRPT, zůstane aktivní na zařízení, pravidla, dokonce i při odpojení sítě VPN. Pravidlo zůstane, dokud se odebere profil sítě VPN nebo dokud je ručně odebrat pravidlo, které lze provést pomocí Powershellu.
[Nastavení sítě VPN ve Windows 10](vpn-settings-windows-10.md) popisuje nastavení. 

#### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Detekce důvěryhodných sítí pomocí profilů sítě VPN na zařízeních s Windows 10 <!-- 1500165 -->
Při použití detekce důvěryhodných sítí, můžete zabránit profily sítě VPN automaticky vytvoří připojení k síti VPN, pokud je uživatel v důvěryhodné síti. S touto aktualizací můžete přidat přípony DNS pro povolení detekce důvěryhodných sítí na zařízeních s Windows 10 a novější (**konfigurace zařízení** > **profily**  >  **Vytvořit profil** > **Windows 10 a novější** pro platformu > **VPN** pro typ profilu).
[Nastavení sítě VPN ve Windows 10](vpn-settings-windows-10.md) uvádí aktuální nastavení sítě VPN.

#### <a name="manage-windows-holographic-for-business-devices-used-by-multiple-users----1907917-1063203---"></a>Správa Windows Holographic for Business zařízení používá více uživatelů <!-- 1907917, 1063203 -->
V současné době můžete nakonfigurovat nastavení sdílené počítače na Windows 10 a Windows Holographic for Business zařízení pomocí vlastního nastavení OMA-URI. S touto aktualizací se přidá nový profil konfigurace sdíleného zařízení (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **Windows 10 a novější** > **sdílený více uživateli zařízení**).
Další informace o této funkci, přejděte na [nastavení Intune můžete spravovat sdílená zařízení](shared-user-device-settings.md).
Platí pro: Windows 10 a novější, Windows Holographic for Business

#### <a name="new-windows-10-update-settings---2626030--2512994----"></a>Nové nastavení aktualizace Windows 10 <!--2626030  2512994  -->
Pro vaše [aktualizační kanály Windows 10](windows-update-for-business-configure.md), můžete nakonfigurovat:
- **Chování automatické aktualizace** -pomocí nové možnosti *obnovit výchozí* obnovit původní nastavení automatických aktualizací na počítač s Windows 10 na počítače, které běží *aktualizace z října 2018*
- **Brání uživateli ve pozastavení aktualizací Windows** – konfigurace aktualizace nastavení, která umožňuje blokovat nebo povolit uživatelům k pozastavení instalace aktualizace z nového softwaru *nastavení* jejich počítačů. 

#### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>e-mailové profily iOS můžete použít S/MIME podepisování a šifrování <!-- 2662949 -->
Můžete vytvořit e-mailový profil, který obsahuje jiné nastavení. Tato aktualizace zahrnuje nastavení S/MIME, které lze použít pro podepisování a šifrování komunikace e-mailu na zařízeních s Iosem (**konfigurace zařízení** > **profily**  >  **Vytvořit profil** > zvolit **iOS** pro platformu > **e-mailu** pro typ profilu).
[Konfigurace nastavení e-mailu iOS](email-settings-ios.md) uvádí nastavení.

#### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Edice Windows 10 Pro podporu některých nastavení Bitlockeru<!-- 2727036 -->
Můžete vytvořit konfigurační profil, který nastaví nastavení služby endpoint protection na zařízeních s Windows 10, včetně nástroje BitLocker. Tato aktualizace přidává podporu pro Windows 10 Professional edition pro některá nastavení nástroje BitLocker. Pokud chcete zobrazit nastavení ochrany, přejděte na [nastavení služby Endpoint protection pro Windows 10](endpoint-protection-windows-10.md#windows-encryption).

#### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal---2809362---"></a>Konfigurace sdíleného zařízení bylo přejmenováno na zpráva na zamčené obrazovce pro zařízení s Iosem na webu Azure Portal<!-- 2809362 -->
Při vytváření konfiguračního profilu pro zařízení s Iosem, můžete přidat **konfigurace sdíleného zařízení** nastavení na zamykací obrazovce zobrazit určitý text. Tato aktualizace zahrnuje následující změny: 
- **Konfigurace sdíleného zařízení** nastavení na portálu Azure portal je přejmenován na "Zpráva na zamčené obrazovce (jenom pod dohledem)" (**konfigurace zařízení** > **profily**  >  **Vytvořit profil** > zvolit **iOS** pro platformu > zvolit **funkcí na zařízeních** pro typy profilů > **zámku Obrazovky zprávy**).
- Když přidáte zámek obrazovky zprávy, můžete vložit sériové číslo, název zařízení nebo jiné hodnoty konkrétní zařízení jako proměnná v **informace z inventárního štítku** a **zamykací obrazovka Poznámka pod čarou**. Například můžete zadat `Device name: {{devicename}}` nebo `Serial number is {{serialnumber}}` pomocí složených závorek. [tokeny pro iOS](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) uvádí dostupné tokeny, které lze použít.
[Nastavení pro zobrazení zpráv na zamykací obrazovce](shared-device-settings-ios.md) uvádí nastavení.

#### <a name="new-app-store-doc-viewing-gaming-device-restriction-settings-added-to-ios-devices----2827760--"></a>Nové aplikace App Store, zobrazování dokumentů, nastavení omezení pro herní zařízení přidat do zařízení s Iosem <!-- 2827760-->
V **konfigurace zařízení** > **profily** > **vytvořit profil** > **iOS** pro Platforma > **omezení zařízení** pro typy profilů > **App Store, zobrazování dokumentů, hraní her**, jsou přidána následující nastavení: Povolit spravovaným aplikacím zápis kontaktů nespravované kontakty účtům povolit nespravované aplikace o čtení z účtů spravovaných kontakty zobrazovat tato nastavení, přejděte na [omezení zařízení s Iosem](device-restrictions-ios.md#app-store-doc-viewing-gaming).

#### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Nové oznámení, Rady a keyguard nastavení vlastníka zařízení s Androidem Enterprise <!-- 3201839 3201843 -->
Tato aktualizace zahrnuje několik nových funkcí na zařízeních s Androidem Enterprise, při spuštění jako vlastník zařízení. K používání těchto funkcí, přejděte na **konfigurace zařízení** > **profily** > **vytvořit profil** > v **platformy**, zvolte **Androidu Enterprise** > v **typ profilu**, zvolte **jen vlastník zařízení** > **zařízení Omezení**.

Mezi nové funkce patří: 

- Zakážete oznámení systému ze zobrazení, včetně příchozí volání, systém upozornění, chyby systému a další.
- Navrhuje přeskočit počáteční kurzy a pomocných parametrů pro aplikace, které jsou otevřené poprvé.
- Zakázat rozšířené keyguard, odemkněte nastavení, jako je fotoaparát, oznámení, otisk prstu a další.


Chcete-li nastavení zobrazit, přejděte na [nastavení omezení pro zařízení s Androidem Enterprise](device-restrictions-android-for-work.md).

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Vlastník zařízení s androidem enterprise, můžete použít připojení Always On VPN <!-- 3202194 -->
V této aktualizaci použijete k připojení vždy zapnutá síť VPN na zařízeních s Androidem enterprise zařízení vlastníka. Neustále aktivní připojení VPN zůstávají ve spojení nebo se ihned znovu připojí, jakmile uživatel odemkne zařízení, zařízení se restartuje nebo se změní bezdrátová síť. Připojení také můžete přepnout do „zamčeného“ režimu, který blokuje veškerý síťový provoz, dokud není připojení VPN zase aktivní.
Můžete povolit vždy zapnutá síť VPN v **konfigurace zařízení** > **profily** > **vytvořit profil**  >   **Android enterprise** pro platformu > **omezení zařízení** jen vlastník zařízení > **připojení** nastavení. Chcete-li nastavení zobrazit, přejděte na [nastavení omezení pro zařízení s Androidem Enterprise](device-restrictions-android-for-work.md).

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Nové nastavení pro procesy ve Správci úloh na zařízení s Windows 10 <!-- 3285177 --> 
Tato aktualizace zahrnuje nové nastavení k ukončení procesů pomocí Správce úloh na zařízení s Windows 10. Pomocí konfiguračního profilu zařízení (**konfigurace zařízení** > **profily** > **vytvořit profil** > v **platformy** , zvolte **Windows 10** > v **typ profilu**, zvolte **omezení zařízení** > **Obecné** nastavení), budete chtít povolit nebo zakázat toto nastavení.
Chcete-li zobrazit tato nastavení, přejděte na [nastavení omezení zařízení s Windows 10](device-restrictions-windows-10.md).
Platí pro: Windows 10 a novější


### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564---"></a>Podrobnější zasílání zpráv selhání omezení registrace <!-- 3111564 -->
Podrobné chybové zprávy jsou k dispozici, pokud nejsou splněné omezení registrace. Chcete-li zobrazit tyto zprávy, přejděte na **Intune** > **Poradce při potížích** > a zkontrolovat chyby registrace tabulku. Další informace najdete v tématu [seznam chyb registrace](help-desk-operators.md#enrollment-failure-reference).

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="tenant-status-dashboard-----1124854---"></a>Řídicí panel stavu klienta  <!-- 1124854 -->
Nové [Tenanta stavové stránce](tenant-status.md) poskytuje jediné místo, kde můžete zobrazit stav a související informace pro vašeho tenanta.  Řídicí panel je rozdělen na čtyři oblasti:
- **Tenant podrobnosti** – zobrazí informace, jako jsou název Tenanta a umístění, vaše autorita MDM celkový počet zaregistrovaných zařízení ve vašem tenantovi, a licence se počítá. Tato část také obsahuje seznam aktuální verze služby pro vašeho tenanta.
- **Stav konektoru** – zobrazí informace o dostupných konektorů, které jste nakonfigurovali a můžete také zařadit ty, které jste ještě nepovolili.  
   Na základě aktuálního stavu každého konektoru, jsou označeny jako v pořádku, upozornění nebo není v pořádku. Vyberte konektor, Procházet na podrobnosti a zobrazit podrobnosti nebo Další informace o jeho konfiguraci.
-  **Stav služby Intune** – pro vašeho tenanta se zobrazí podrobnosti o aktivní incidenty nebo výpadky. Tyto informace v této části se načítají přímo v Centru zpráv Office.
-  **Intune zpráv** – pro vašeho tenanta se zobrazí aktivní zprávy. Zprávy zahrnují věci, jako je oznámení, když váš tenant obdrží nejnovější funkce Intune.  Tyto informace v této části se načítají přímo v Centru zpráv Office.

#### <a name="new-help-and-support-experience-in-company-portal-for-windows-10----1488939--"></a>Nové Nápověda a podpora prostředí v aplikaci portál společnosti pro Windows 10 <!-- 1488939-->
Nová stránka nápovědy portál společnosti a podpora pomáhá uživatelům řešení potíží a požádat o pomoc pro problémy s aplikací a přístup. Na nové stránce mohou e-mailu chyby a podrobnosti diagnostických protokolů a najít podrobnosti o technickou podporu organizace. Také najdete v části Nejčastější dotazy s odkazy na relevantní dokumentaci k Intune. 

#### <a name="new-help-and-support-experience-for-intune------3307080---"></a>Prostředí nové nápovědy a podpory pro Intune   <!-- #3307080 -->
Zavádíme nové prostředí nápovědy a podpory pro všechny tenanty prostřednictvím během několika dalších dnů. Toto nové prostředí je k dispozici pro Intune a je přístupný při používání okna Intune v [webu Azure portal](https://portal.azure.com/).
Nové prostředí vám umožňuje popsat problém vlastními slovy a získat přehled možností řešení potíží a postupy z webu, jak problém opravit. Tato řešení jsou k dispozici prostřednictvím počítač založený na pravidlech umožňujících učení algoritmu řízené uživatelem. Kromě pokyny týkající se problému můžete použít nový pracovní postup vytvoření případu k otevření případu podpory podle e-mail nebo telefon. Toto nové prostředí nahradí předchozí prostředí nápovědy a podpory statickou sadu předem vybranými možnostmi, které jsou založeny na oblasti konzoly jsou otevřít nápovědu a podporu. Další informace najdete v tématu [jak získat podporu pro Microsoft Intune](get-support.md).

### <a name="role-based-access-control"></a>Řízení přístupu na základě role

#### <a name="scope-tags-for-apps----1081941---"></a>Značky oboru pro aplikace <!-- 1081941 -->
Můžete vytvořit značky oboru k omezení přístupu pro role a aplikace. Značka oboru můžete přidat do aplikace tak, aby přístup k aplikaci mají pouze lidé s rolemi také přiřadit značky oboru. Aplikace přidaní do Intune ze spravovaného obchodu Google Play nebo aplikací koupených pomocí Apple Volume Purchase Program (VPP) v současné době nelze přiřadit značky oboru (budoucí podpora je naplánovaná). Další informace najdete v tématu [pomocí značky oboru filtru zásad](scope-tags.md).

<!-- ########################## -->
## <a name="week-of-december-10-2018"></a>Týden od 10. prosince 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="updates-for-application-transport-security----748318---"></a>Aktualizace pro Application Transport Security <!-- 748318 -->

Microsoft Intune podporuje zabezpečení TLS (Transport Layer) 1.2 + poskytnout ve své třídě nejlepší šifrování, ujistěte se, že je ve výchozím nastavení bezpečnější, Intune a aby bylo v souladu s jinými službami Microsoftu, jako je například Microsoft Office 365. Aby bylo možné tento požadavek splnit, portály společnosti pro iOS a macOS bude vynucovat společnosti Apple aktualizované aplikace přenosu zabezpečení () požadavky na ATS, které také vyžadují protokol TLS 1.2 +. ATS se používá k vynucení vyššího zabezpečení veškeré komunikace aplikací přes protokol HTTPS. Tato změna ovlivní zákazníky Intune pomocí aplikace portál společnosti pro iOS a macOS. Další informace najdete v tématu [blogu podpory Intune](https://aka.ms/compportalats).

#### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>Intune App SDK bude podporovat 256bitových šifrovacích klíčů <!-- 1832174 -->
Intune App SDK pro Android teď používá 256bitových šifrovacích klíčů, když je povoleno šifrování pomocí zásad ochrany aplikací. Sady SDK bude dále poskytovat podpora 128bitových klíčů z důvodu kompatibility s obsahem a aplikace, které používají starší verze sady SDK.

### <a name="microsoft-auto-update-version-450-required-for-macos-devices----3503442---"></a>Microsoft automaticky aktualizovanou verzi 4.5.0 požadované pro zařízení s macOS <!-- 3503442 -->
Chcete-li pokračovat, příjem aktualizací pro aplikaci portál společnosti a další aplikace Office, musí zařízení s macOS spravovaná pomocí Intune upgradovat na Microsoft automatickou aktualizaci 4.5.0. Uživatelé můžou mít už tuto verzi pro jejich aplikace Office.

### <a name="intune-requires-macos-1012-or-later----2827778---"></a>Intune vyžaduje macOS 10.12 nebo novější <!-- 2827778 -->
Intune teď vyžaduje macOS verze 10.12 nebo novější. Zařízení s macOS předchozí verze pomocí nelze použít aplikaci portál společnosti k registraci do Intune. Na podporu a nové funkce, musí uživatelé upgradovat svoje zařízení s macOS 10.12 nebo novější a upgradovat na nejnovější verzi aplikace portál společnosti.

<!-- ########################## -->
## <a name="week-of-november-26-2018"></a>Týden od 26. listopadu 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Odinstalování aplikací na zařízeních vlastněných společností s Iosem pod dohledem <!-- 1281677 -->

Můžete odebrat všechny aplikace na zařízeních vlastněných společností s Iosem pod dohledem. Libovolnou aplikaci můžete odebrat, když cílem přiřazení typu **Odinstalovat** budou skupiny uživatelů nebo zařízení. U zařízení s iOSem, která jsou osobní nebo nejsou pod dohledem, budete nadále moci odebrat jen aplikace, které byly nainstalované pomocí Intune.

#### <a name="downloading-intune-win32-app-content----2617320---"></a>Stahuje se obsah aplikace Intune Win32 <!-- 2617320 -->
Windows 10 RS3 a vyšší než klienti budou stahovat obsah aplikace Intune Win32 pomocí optimalizace doručení komponenty na straně klienta Windows 10. Optimalizace doručení poskytuje Peer-to-Peer funkce, které je ve výchozím nastavení zapnutá. Optimalizace doručení v současné době je možné nakonfigurovat prostřednictvím zásad skupiny. Další informace najdete v tématu [optimalizace doručení pro Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization). 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Koncový uživatel zařízení a aplikací kontextové nabídky <!-- 2771453 -->
Koncoví uživatelé teď můžou používat místní nabídka na zařízení a aplikací pro aktivaci běžné akce, jako je přejmenování zařízení nebo kontroluje se dodržování předpisů.

#### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Nastavení vlastní pozadí v aplikaci spravované domovskou obrazovku  <!-- 3041945 -->
Přidáváme nastavení, které umožňuje přizpůsobit vzhled pozadí spravované domovskou obrazovku aplikace na Androidu Enterprise, s více aplikacemi, zařízení pro beznabídkový režim.  Pokud chcete nakonfigurovat **vlastní adresu URL pozadí**, na webu Azure Portal přejděte na Intune > Konfigurace zařízení. Vyberte aktuální profil konfigurace zařízení nebo vytvořte nový a upravte nastavení beznabídkového režimu.
Nastavení beznabídkového režimu, najdete v sekci [omezení zařízení s Androidem Enterprise](device-restrictions-android-for-work.md).

#### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Přiřazení zásad ochrany aplikací, uložit a použít <!-- 3104570 -->
Teď máte lepší kontrolu nad vaší [přiřazených zásad ochrany aplikací](app-protection-policies.md#deploy-a-policy-to-users). Když vyberete *přiřazení* nastavit nebo upravit přiřazení zásady, je nutné **Uložit** konfigurace předtím, než změna se vztahuje. Použití **zahodit** zrušte všechny změny provedete bez uložení jakýchkoliv změn k zahrnutí nebo vyloučení seznamy.  Vyžadování uložit nebo zahodit jsou přiřazeny pouze uživatele, které chcete zásady ochrany aplikací.

#### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Nové nastavení prohlížeče Microsoft Edge pro Windows 10 a novější <!-- 3174639 -->
Tato aktualizace zahrnuje nové nastavení, které pomáhá řídit a spravovat prohlížeč Microsoft Edge na zařízení. Seznam nastavení najdete v tématu [omezení zařízení pro Windows 10 (a novější)](device-restrictions-windows-10.md#microsoft-edge-browser).

#### <a name="new-apps-support-with-app-protection-policies----3330037---"></a>Podpora nových aplikací se zásadami ochrany aplikací <!-- 3330037 -->
Teď můžete spravovat tyto aplikace s [zásady ochrany aplikací Intune](app-protection-policies.md):
- Stream (iOS)
- Úkol (Android, iOS)
- PowerApps (Android, iOS)
- Tok (Android, iOS)

Použití zásad ochrany aplikací pro ochranu firemních dat a ovládací prvek přenos dat u těchto aplikací, jako ostatní zásady spravované aplikace Intune. Poznámka: Pokud tok není viditelné v konzole, přidáte tok, když vytvoříte nebo upravíte a zásady ochrany aplikací. Chcete-li tak učinit, použijte **+ další aplikace** možnost a potom zadejte *ID aplikace* pro tok do vstupního pole. Pro Android pomocí *com.microsoft.flow*, a pro iOS použijte *com.microsoft.procsimo*.


### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="ios-and-macos-version-numbers-and-build-numbers-are-shown----1892471---"></a>zařízení s iOS a macOS čísla verzí a sestavení jsou uvedeny. <!-- 1892471 -->
V oblasti **Dodržování předpisů zařízením** > **Dodržování předpisů zařízením** se zobrazují verze operačního systému iOS a macOS, která lze použít v zásadách dodržování předpisů. Tato aktualizace obsahuje číslo sestavení, které je možné nakonfigurovat pro obě platformy.
Při vydání aktualizací zabezpečení společnost Apple obvykle ponechává stávající číslo verze, ale aktualizuje číslo buildu. Pomocí čísla buildu v zásadách dodržování předpisů můžete snadno zkontrolovat, jestli je nainstalovaná aktualizace řešící ohrožení zabezpečení.
Chcete-li tuto funkci používat, naleznete v tématu [iOS](compliance-policy-create-ios.md#device-health) a [macOS](compliance-policy-create-mac-os.md#device-properties) zásady dodržování předpisů.

#### <a name="update-rings-are-being-replaced-with-delivery-optimization-settings-for-windows-10-and-later----2753807---"></a>Nastavení optimalizace doručení pro Windows 10 a novější se nahrazují aktualizační okruhy <!-- 2753807 -->
Optimalizace doručení je nový profil konfigurace pro Windows 10 a novější. Tato funkce poskytuje přináší optimalizaci prostředí pro doručení aktualizací softwaru do zařízení ve vaší organizaci. Tato aktualizace umožňuje poskytovat nastavení nové i stávající aktualizačních kanálů pomocí konfiguračního profilu.
Konfiguraci optimalizace doručení konfiguračního profilu najdete v tématu [nastavení aktualizace Windows 10 (nebo novější)](delivery-optimization-windows.md).

#### <a name="new-device-restriction-settings-added-to-ios-and-macos-devices----2827760---"></a>Nová nastavení omezení zařízení přidat do zařízení s Iosem a macOS <!-- 2827760 -->
Tato aktualizace zahrnuje nové nastavení pro zařízení s Iosem a macOS, které jsou vydány s Iosem 12:

**nastavení iOS**: 
- Obecné: Odebrání bloku aplikace (jenom pod dohledem)
- Obecné: Blok USB omezený režim (jenom pod dohledem)
- Obecné: Vynutit automatické datum a čas (jenom pod dohledem)
- Heslo: Heslo blokovat automatické vyplňování (jenom pod dohledem)
- Heslo: Blokovat požadavky blízkosti hesla (jenom pod dohledem)
- Heslo: Blokovat sdílení hesla (jenom pod dohledem)

**nastavení macOS**: 
- Heslo: Blokovat automatické vyplňování hesel
- Heslo: Blokovat požadavky blízkosti heslo
- Heslo: Blokovat sdílení hesla

Další informace o těchto nastaveních najdete v tématu [iOS](device-restrictions-ios.md) a [macOS](device-restrictions-macos.md) nastavení omezení zařízení.

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Vyberte aplikace, které byly sledovány pro stránka stavu registrace<!-- 2531007 -->
Můžete vybrat aplikace, které jsou sledovány v stránka stavu registrace. Dokud se tyto aplikace jsou nainstalované, nemůže používat zařízení. Další informace najdete v tématu [nastavení na stránce Stav registrace](windows-enrollment-status.md).

#### <a name="search-for-autopilot-device-by-serial-number---2595788---"></a>Hledat podle sériového čísla zařízení Autopilot <!--2595788 -->
Zařízení Autopilot můžete teď hledat podle sériového čísla. Chcete-li to provést, zvolte **registrace zařízení** > **registrace Windows** > **zařízení** > zadejte sériové číslo do **hledat podle sériové číslo** pole > stiskněte klávesu Enter.

#### <a name="track-installation-of-office-proplus---2620217---"></a>Sledování instalace Office ProPlus <!--2620217 -->
Uživatelé mohou sledovat průběh instalace [Office ProPlus](apps-add-office365.md) pomocí [stránka stavu registrace](windows-enrollment-status.md). Další informace najdete v tématu [nastavení na stránce Stav registrace](windows-enrollment-status.md).

#### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Spuštěné s nízkou licence výstrah, u nichž vyprší platnost tokenu VPP nebo portál společnosti <!-- 2237572 -->
Pokud používáte Volume Purchase Program (VPP) k předběžnému přidělení portálu společnosti během registrace DEP, vás Intune upozorní VPP token blížící se vypršení platnosti a pokud není k dispozici dostatek licencí pro aplikaci portál společnosti.

### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133---"></a>Program registrace zařízení s macOS se podporují pro účty Apple School Manageru <!--3006133 -->
Intune teď podporuje pomocí programu registrace zařízení na zařízeních s macOS pro účty Apple School Manageru.  Další informace najdete v tématu [Automatická registrace zařízení s macOS pomocí Apple School Manager nebo programu registrace zařízení](device-enrollment-program-enroll-macos.md).

### <a name="new-intune-device-subscription-sku---3312071--"></a>Nové předplatné Intune zařízení SKU <!--3312071-->
Abychom v podnicích pomohli snížit náklady na správu zařízení, nabízíme teď novou skladovou položku pro předplatné na základě zařízení. Tato skladová položka je licencovaná měsíčně podle počtu zařízení. Ceny se liší podle licenčního programu. Je k dispozici přímo prostřednictvím centra pro správu služeb Microsoft 365 a [smlouvy Enterprise](https://www.microsoft.com/licensing/licensing-programs/enterprise?activetab=enterprise-tab:primaryr2) (EA), [Products Microsoftu a smlouva o poskytování služeb](https://www.microsoft.com/licensing/mpsa/default) (MPSA), [Microsoft Open Smlouvy o](https://partner.microsoft.com/licensing/licensing-agreements), a [Cloud Solution Provider](https://www.microsoftpartnercommunity.com/t5/Partnership-101/What-is-the-Cloud-Solution-Provider-CSP-program/td-p/2453) (CSP).

### <a name="device-management"></a>Správa zařízení

#### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Dočasně pozastavíte celoobrazovkového režimu na zařízeních s Androidem provádět změny <!-- 3041935 -->
Při používání zařízení s Androidem v beznabídkovém režimu s více aplikacemi může správce IT potřebovat udělat v zařízení změny. Tato aktualizace zahrnuje nové nastavení veřejný terminál s více aplikacemi, které správcům IT umožňuje dočasně pozastavit beznabídkovým režimem pomocí kódu PIN a získat přístup k celé zařízení.
Nastavení beznabídkového režimu, najdete v sekci [omezení zařízení s Androidem Enterprise](device-restrictions-android-for-work.md).

#### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Povolit virtuální tlačítko Domů na zařízení s Androidem Enterprise v celoobrazovkovém režimu  <!-- 3042021 -->
Nové nastavení umožní uživatelům klepnutím na softwarové tlačítko přepínat mezi aplikací Managed Home Screen a jinými přiřazenými aplikacemi na zařízení v beznabídkovém režimu s více aplikacemi. Toto nastavení je zvláště užitečné v situacích, kdy beznabídková aplikace uživatele nereaguje správně na tlačítko Zpět. Toto nastavení budete moci nakonfigurovat pro zařízení s Androidem ve vlastnictví firmy pro použití s jednou aplikací. Pokud chcete nakonfigurovat **Virtuální tlačítko Domů**, na webu Azure Portal přejděte na Intune > Konfigurace zařízení. Vyberte aktuální profil konfigurace zařízení nebo vytvořte nový a upravte nastavení beznabídkového režimu.
Nastavení beznabídkového režimu, najdete v sekci [omezení zařízení s Androidem Enterprise](device-restrictions-android-for-work.md).

<!-- ########################## -->
## <a name="week-of-november-12-2018"></a>Týden od 12. listopadu 2018

### <a name="network-access-control-nac-support-for-citrix-sso-for-ios----3259404---"></a>Sítě – podpora řízení přístupu (NAC) pro Citrix jednotného přihlašování pro iOS <!-- 3259404 -->

Citrix vydali aktualizaci Citrix Gateway, která ovládací prvek přístupu k síti (NAC) pro Citrix jednotného přihlašování pro iOS v Intune. Můžete vyjádřit výslovný souhlas s zahrnují ID zařízení v rámci profilu sítě VPN v Intune a potom nasdílejte tento profil k zařízením s Iosem. Je potřeba nainstalovat nejnovější aktualizaci pro Citrix bráně pro použití této funkce.

[Konfigurace nastavení sítě VPN na zařízeních s Iosem](vpn-settings-ios.md#base-vpn-settings) poskytuje další informace o používání NAC, včetně některých dalších požadavků. 

<!-- ########################## -->
## <a name="week-of-november-5-2018"></a>Týden od 5. listopadu 2018

### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>Podpora pro iOS 12 OAuth v e-mailové profily pro iOS <!--2155106 -->

E-mailové profily Intune pro iOS podporují OAuth (Open Authorization) v iOS 12. Pokud chcete tuto funkci zobrazit, vytvořte nový profil (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **iOS** jako platforma > **E-mail** jako typ profilu), nebo aktualizujte existující e-mailový profil iOS. Pokud OAuth povolíte v profilu, který už je nasazený uživatelům, jsou uživatelé vyzváni k opětovnému ověření a stažení svých e-mailů.

[E-mailové profily pro iOS](email-settings-ios.md) obsahují více informací o použití OAuth.

### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview----1048100--"></a>Podpora AutoPilot pro hybridní služby Azure Active Directory zařízení připojené k doméně (Preview) <!-- 1048100-->
Zařízení připojená k hybridní službě Azure Active Directory si teď můžete nastavit pomocí Autopilotu. Zařízení musí být připojená do vaší podnikové sítě, aby mohla použít hybridní funkci Autopilotu. Další informace najdete v článku o [nasazení zařízení připojených k hybridní službě Azure AD pomocí Intune a Windows Autopilotu](windows-autopilot-hybrid.md).
Tato funkce se bude zavádět pro uživatelskou základnu v průběhu několika dalších dnů. Následující postup bude možné provést až po jejím zavedení pro váš účet.

<!-- ########################## -->
## <a name="week-of-october-29-2018"></a>Týden od 29. října 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="require-non-biometric-pin-after-a-specified-timeout----1506985---"></a>Vyžadovat kód PIN – biometrické po zadaný časový limit <!-- 1506985 -->
Po uplynutí časového limitu určeného správcem Intune požaduje nebiometrický kód PIN. Služba tak lépe zabezpečí aplikace s podporou Správy mobilních aplikací (MAM), protože omezí použití biometrické identifikace pro přístup k firemním datům. Toto nastavení má vliv na uživatele, kteří pro přístup k aplikacím s podporou APP/MAM používají Touch ID (iOS), Face ID (iOS), Biometriku Androidu nebo jiné budoucí způsoby biometrického ověřování. S tímto nastavením mají správci Intune přesnější kontrolu nad přístupem uživatelů, takže mohou vyloučit případy, kdy zařízení s více otisky prstů nebo jinými biometrickými metodami přístupu může odhalit firemní data nesprávnému uživateli. Na portálu Azure Portal otevřete **Microsoft Intune**. Vyberte **Klientské aplikace** > **Zásady ochrany aplikací** > **Přidat zásadu** > **Nastavení**. Najděte část **Přístup** s konkrétními nastaveními. Informace o nastavení přístupu najdete v [nastavení iOSu](app-protection-policy-settings-ios.md#access-requirements) a [nastavení Androidu](app-protection-policy-settings-android.md#access-requirements).

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Nastavení přenosu dat v aplikaci Intune v iOS MDM zaregistrovaná zařízení <!-- 2244713 -->
Ovládání nastavení Intune APP pro přenos dat na zařízeních s iOSem zaregistrovaných v MDM můžete oddělit od zadání identity registrovaného uživatele, která se označuje také jako hlavní název uživatele (UPN). Správci, kteří nepoužívají aplikaci IntuneMAMUPN, nezaznamenají změnu chování. Pokud je tato funkce k dispozici, musí správci, kteří k řízení chování při přenosech dat na registrovaných zařízeních používají Intune MAMUPN, zkontrolovat nové nastavení a podle potřeby aktualizovat nastavení APP.

#### <a name="windows-10-win32-apps----2617325---"></a>Aplikace Win32 pro Windows 10 <!-- 2617325 -->
Aplikace Win32 můžete nakonfigurovat tak, aby se instalovaly v kontextu uživatele pro jednotlivé uživatele, nebo pro všechny uživatele zařízení.

#### <a name="windows-win32-apps-and-powershell-scripts----2617330---"></a>Aplikace Windows Win32 a skripty prostředí PowerShell <!-- 2617330 -->
Koncoví uživatelé už nemusí být kvůli instalaci aplikací Win32 nebo spouštění powershellových skriptů přihlášení k zařízení. 

#### <a name="troubleshooting-client-app-installation----1363711---"></a>Řešení problémů při instalaci klienta aplikace <!-- 1363711 -->
Potíže s instalací klientských aplikací můžete řešit tak, že se podíváte do sloupce s názvem **Instalace aplikace** v okně **Řešení potíží**. Okno **Řešení potíží** zobrazíte tak, že na portálu Intune vyberete **Řešení potíží** v části **Nápověda a podpora**.

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="network-access-control-support-on-ios-vpn-clients----1333693---"></a>Síť podporu řízení přístupu na klientech VPN iOS <!-- 1333693 -->
V této aktualizaci zavádíme nové nastavení, kterým můžete při vytváření konfiguračního profilu VPN pro Cisco AnyConnect, F5 Access a Citrix SSO pro iOS povolit řízení přístupu k síti (NAC). Toto nastavení umožní zahrnutí ID NAC zařízení do profilu VPN. V současné době neexistují žádní klienti VPN ani partnerská řešení NAC podporující toto nové ID NAC, ale jakmile se tak stane, budeme vás informovat prostřednictvím [blogového příspěvku o podpoře](ttps://aka.ms/iOS12_and_vpn).

Abyste mohli používat NAC, budete muset:
1. vyjádřením výslovného souhlasu povolit službě Intune zahrnout ID zařízení do profilů VPN,
2. aktualizovat software nebo firmware poskytovatele NAC pomocí pokynů, které získáte přímo od svého poskytovatele NAC.

Informace o tomto nastavení v profilu VPN v iOSu najdete v článku, který se zabývá [přidáním nastavení VPN v zařízeních s iOSem v Microsoft Intune](vpn-settings-ios.md). Další informace o řízení přístupu k síti najdete v článku [Integrace řešení pro řízení přístupu k síti (NAC) do Intune](network-access-control-integrate.md). 

Platí pro: iOS

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile----1818139---"></a>Odebrání e-mailový profil ze zařízení, i v případě, že existuje pouze jedna e-mailový profil <!-- 1818139 -->
Dříve nebylo možné ze zařízení odebrat e-mailový profil, *pokud* jich tam nebylo více. S touto aktualizací se toto chování změní. Teď můžete e-mailový profil odebrat, i když na zařízení není žádný další. Podrobnosti najdete v tématu [Přidání e-mailového nastavení na zařízení pomocí Intune](email-settings-configure.md).

#### <a name="powershell-scripts-and-aad----2309469---"></a>Skripty prostředí PowerShell a AAD <!-- 2309469 -->
Cílem powershellových skriptů v Intune mohou být skupiny zabezpečení zařízení služby AAD.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Nový "vyžadovaný typ hesla" výchozí nastavení pro Android, Android enterprise<!-- 2649963 -->
Když vytvoříte nové zásady dodržování předpisů (**Intune** > **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu** > **Android** nebo **Android Enterprise** pro Platforma > Zabezpečení systému), výchozí hodnota pro **Požadovaný typ hesla** se změní:

Od: Výchozí ze zařízení na: Aspoň číselné

Platí pro: Android, Android Enterprise

Pokud se chcete podívat na tato nastavení, přejděte do [Androidu](compliance-policy-create-android.md) nebo [Androidu Enterprise](compliance-policy-create-android-for-work.md).

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Použít předsdílený klíč v profilu Wi-Fi pro Windows 10 <!-- 2662938 -->
S touto aktualizací můžete k ověření konfiguračního profilu sítě Wi-Fi pro Windows 10 použít předsdílený klíč (PSK) s protokolem zabezpečení WPA/WPA2-osobní. U zařízení s Windows 10 a aktualizací ze října 2018 můžete také zadat konfiguraci nákladů pro síť s měřením dat.

Pokud chcete použít předsdílený klíč, musíte v současnosti importovat profil Wi-Fi nebo vytvořit vlastní profil. Seznam aktuálních nastavení je v [nastavení sítě Wi-Fi pro Windows 10](wi-fi-settings-windows.md). 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices----3218390---"></a>Ze zařízení odebrat certifikáty PKCS a SCEP <!-- 3218390 -->
V některých scénářích zůstávaly certifikáty PKCS a SCEP na zařízeních i po odebrání zásad ze skupiny, odstranění nasazené konfigurace nebo nastavení pro dodržování předpisů nebo aktualizaci existujícího profilu SCEP nebo PKCS správcem. Tato aktualizace toto chování mění. Budou existovat určité scénáře, kdy se certifikáty PKCS a SCEP ze zařízení odeberou, a jiné scénáře, kdy tyto certifikáty zůstanou na zařízení. Tyto scénáře najdete v tématu [Odebrání certifikátů SCEP a PKCS v Microsoft Intune](remove-certificates.md).

#### <a name="use-gatekeeper-on-macos-devices-for-compliance----2504381---"></a>Použít Gatekeeper na dodržování předpisů u zařízení s macOS <!-- 2504381 -->
Tato aktualizace zahrnuje Gatekeeper pro macOS, který umožňuje u zařízení vyhodnotit dodržování předpisů. Pokud chcete nastavit vlastnost Gatekeeper, přejděte na článek [Přidání zásad dodržování předpisů pro zařízení s macOS v Intune](compliance-policy-create-mac-os.md).


### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="enrollment-abandonment-report----1382924---"></a>Registrace zřeknutí sestavy <!-- 1382924 -->
Nová sestava, která poskytuje podrobné informace o opuštěných registracích, je k dispozici v části **Registrace zařízení** > **Monitorování**. Další informace najdete v článku, který se věnuje [sestavě opuštění Portálu společnosti](enrollment-report-company-portal-abandon.md).

#### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Nové podmínky použití funkce Azure Active Directory <!-- 2870393 -->
Azure Active Directory má funkci podmínek použití, kterou můžete využít místo stávajících podmínek a ujednání služby Intune. Funkce podmínek použití služby Azure AD poskytuje větší flexibilitu ohledně toho, které podmínky a kdy se mají zobrazovat, lepší podporu lokalizace, větší kontrolu nad tím, jak se podmínky vykreslují, a vylepšené generování sestav. Funkce podmínek použití služby Azure AD vyžaduje Azure Active Directory Premium P1, která je také součástí sady Enterprise Mobility + Security E3. Další informace najdete v článku [Správa firemních podmínek a ujednání pro přístup uživatelů](terms-and-conditions-create.md).

#### <a name="android-device-owner-mode-support---3188762--"></a>Podpora režimu androidu vlastník zařízení <!--3188762-->
U registrace mobilního zařízení Samsung Knox teď Intune podporuje registraci zařízení do režimu správy Vlastník zařízení Android. Uživatelé připojení prostřednictvím Wi-Fi nebo mobilních sítí mohou svá zařízení při prvním zapnutí registrovat několika klepnutími. Další informace najdete v článku věnovaném [automatické registraci zařízení s Androidem pomocí technologie Knox Mobile Enrollment od Samsungu](android-samsung-knox-mobile-enroll.md).

### <a name="device-management"></a>Správa zařízení
#### <a name="new-settings-for-software-updates------1907869---"></a>Nová nastavení pro aktualizace softwaru   <!-- 1907869 -->  
- Teď můžete nakonfigurovat některá oznámení výstrah koncovým uživatelům o restartování, které jsou nutné k dokončení instalace nejnovějších aktualizací softwaru.   
- Teď můžete nakonfigurovat restartování výzvu s upozorněním pro restartování, ke kterým dochází mimo pracovní dobu, která podporuje scénáře BYOD.

#### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Zařízení zaregistrovaná ve službě Windows Autopilot correlator ID skupiny <!-- 2075110 -->
Intune teď podporuje seskupování zařízení s Windows podle ID korelátoru, pokud jsou zaregistrovaná pomocí [Autopilotu pro existující zařízení](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) v nástroji Configuration Manager. ID korelátoru je parametr konfiguračního souboru Autopilotu. Intune automaticky nastaví [atribut enrollmentProfileName zařízení služby Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices) tak, aby odpovídal nastavení OfflineAutopilotprofile-<correlator ID>. Umožní se tím, aby se pro offline registrace Autopilotu vytvořily libovolné dynamické skupiny Azure AD na základě ID korelátoru prostřednictvím atributu enrollmentprofileName. Další informace najdete v tématu [Windows Autopilot pro existující zařízení](enrollment-autopilot.md#windows-autopilot-for-existing-devices).

#### <a name="intune-app-protection-policies----2984657---"></a>Zásady ochrany aplikací Intune <!-- 2984657 -->
Zásady ochrany aplikací Intune umožňují pro aplikace chráněné přes Intune (například Microsoft Outlook a Microsoft Word) nakonfigurovat různá nastavení ochrany dat. Změnili jsme vzhled těchto nastavení jak pro [iOS](app-protection-policy-settings-ios.md), tak i pro [Android](app-protection-policy-settings-android.md), abychom usnadnili vyhledání jednotlivých nastavení. Existují tři kategorie nastavení zásad:
- **Přemístění dat** – tato skupina obsahuje kontrolní mechanismy ochrany před únikem informací, například omezení operací Vyjmout, Kopírovat, Vložit a Uložit jako. Tato nastavení určují, jak uživatelé pracují s daty v aplikacích.
- **Požadavky na přístup** – tato skupina obsahuje možnosti kódu PIN pro jednotlivé aplikace, které určují, jak koncový uživatel získá přístup k aplikacím v pracovním kontextu.  
- **Podmíněné spouštění** – tato skupina obsahuje nastavení, jako je minimální verze operačního systému, detekce zařízení s jailbreakem a rootem a období odkladu pro offline režim.  
  
Funkčnost těchto nastavení se nemění, ale bude snazší je vyhledat při vytváření zásad.

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps----1727158---"></a>Intune bude podporovat balíček maximální velikosti 8 GB pro obchodní aplikace <!-- 1727158 -->
Služba Intune zvýšila maximální velikost balíčku u obchodních aplikací na 8 GB. Další informace najdete v článku [Přidání aplikací do Microsoft Intune](apps-add.md).

#### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Přidat vlastní značky obrázku pro aplikaci portál společnosti <!-- 1916266 -->
Správce služby Microsoft Intune může nahrát obrázek vlastní značky, který se v aplikaci Portál společnosti pro iOS zobrazí jako pozadí stránky s profilem uživatele. Další informace o konfiguraci aplikace Portál společnosti najdete v tématu [Konfigurace aplikace Portál společnosti služby Microsoft Intune](company-portal-app.md).

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>Intune bude udržovat Office lokalizovaný jazyk při aktualizaci Office na počítačích koncových uživatelů <!-- 2971030 -->
Když Intune nainstaluje Office na počítače koncových uživatelů, získají koncoví uživatelé automaticky stejné jazykové sady, které měli s předchozími instalacemi Office .MSI. Další informace najdete v článku [Přiřazení aplikací Office 365 k zařízením s Windows 10 pomocí Microsoft Intune](apps-add-office365.md).

### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal----3076965---"></a>Nové prostředí podpory Intune na portálu správy Microsoft 365 zařízení <!-- 3076965 -->
Na [portálu Správa zařízení Microsoft 365]( http://devicemanagement.microsoft.com) zavádíme nové prostředí pro nápovědu a podporu Intune. Nové prostředí vám umožňuje popsat problém vlastními slovy a získat přehled možností řešení potíží a postupy z webu, jak problém opravit. Tato řešení jsou nabízena prostřednictvím algoritmů strojového učení založeného na pravidlech, které se řídí dotazy uživatelů.  

Kromě pokynů ke konkrétnímu problému můžete také využít nového pracovního postupu vytváření případů a otevřít případ podpory e-mailem nebo telefonicky.  

U zákazníků v této vlně nasazení toto nové prostředí nahradí aktuální prostředí pro nápovědu a podporu, které obsahuje statickou skupinu předem vybraných možností. Ty jsou založené na oblasti konzoly, ve které se nacházíte při otevření nápovědy a podpory.  

*Toto nové prostředí pro nápovědu a správu zavádíme pro některé, ale ne všechny tenanty, a najdete ho na portálu Správa zařízení. Účastníci nasazení tohoto nového prostředí jsou náhodně vybráni z dostupných tenantů Intune. Nové tenanty budeme přidávat postupně tak, jak budeme nasazení rozšiřovat.*  

Další informace najdete v tématu [Nápověda a podpora prostředí](get-support.md#help-and-support-experience) v tom, jak získat podporu pro Microsoft Intune.  

### <a name="powershell-module-for-intune--preview-available----951068---"></a>Modul PowerShell pro službu Intune – k dispozici ve verzi Preview <!-- 951068 -->
Nový modul prostředí PowerShell, který poskytuje podporu pro rozhraní Intune API prostřednictvím Microsoft Graphu, je teď dostupný ve verzi Preview na [GitHubu]( https://aka.ms/intunepowershell). Podrobnosti o tom, jak tento modul používat, najdete v souboru README v uvedeném umístění. 


<!-- ########################## -->
## <a name="week-of-october-15-2018"></a>Týden od 15. října 2018

### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device-----2637704----"></a>Výzvy k zadání PINU při změně otisky prstů nebo ID pro rozpoznávání tváře na zařízení s iOS  <!-- 2637704  -->
Uživatelům se teď po provedení biometrických změn na zařízení s iOSem zobrazuje výzva k zadání kódu PIN. Týká se to i změn zaregistrovaných otisků prstů nebo Face ID. Načasování výzvy závisí na konfiguraci časového limitu *Překontrolovat požadavky na přístup za (minuty)* .  Pokud není kód PIN nastavený, zobrazí se uživateli výzva k jeho nastavení. 
 
Tato funkce je dostupná jen pro iOS a vyžaduje zapojení aplikací, které integrují sadu Intune APP SDK pro iOS verze 9.0.1 nebo novější. Integrace této sady SDK je nezbytná kvůli vynucení tohoto chování u cílových aplikací. K této integraci dochází průběžně a závisí na týmech konkrétních aplikací. Mezi zapojené aplikace patří například WXP, Outlook, Managed Browser a Yammer.


<!-- ########################## -->
## <a name="week-of-october-1-2018"></a>Týden od 1. října 2018

### <a name="app-management"></a>Správa aplikací

#### <a name="access-to-key-profile-properties-using-the-company-portal-app----772203---"></a>Přístup k vlastnostem profil klíče pomocí aplikace portál společnosti <!-- 772203 -->
Koncoví uživatelé teď mají přístup ke klíčovým vlastnostem účtu a akcím, jako je například resetování hesla, z aplikace Portál společnosti. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>3\. stran klávesnice může být blokováno jiným nastavení aplikace v Iosu <!-- 1248481 -->
Na zařízeních s iOSem můžou správci Intune zablokovat použití klávesnic jiných výrobců pro přístup k datům organizace z aplikací chráněných zásadami. Když budou nastavené Zásady ochrany aplikací (APP) k blokování klávesnic jiných výrobců, uživatelům zařízení se při první interakci s firemními daty pomocí klávesnice jiného výrobce zobrazí zpráva. Všechny jiné možnosti než nativní klávesnice budou zablokované a uživatelům zařízení se nezobrazí. Uživatelům se dialog se zprávou zobrazí jenom jednou. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices----1248496---"></a>Přístup k účtu uživatele z aplikací v Intune na spravovaných zařízeních s Androidem a iOS <!-- 1248496 -->
Jako správce Microsoft Intune můžete řídit, které uživatelské účty se přidají do aplikací Microsoft Office na spravovaných zařízeních. Můžete omezit přístup jenom na povolené uživatelské účty organizace a zablokovat osobní účty na zaregistrovaných zařízeních. 

#### <a name="outlook-ios-and-android-app-configuration-policy---1828527---"></a>IOS aplikace Outlook a zásady Konfigurace aplikací pro Android <!--1828527 -->
Teď můžete vytvořit zásadu konfigurace aplikace Outlook pro iOS a Android pro místní uživatele, kteří využívají základní ověřování pomocí protokolu ActiveSync. Další nastavení konfigurace se přidají po jejich povolení pro Outlook pro iOS a Android.

#### <a name="office-365-pro-plus-language-packs----1833450---"></a>Jazykové sady Office 365 Pro Plus <!-- 1833450 -->
Jako správce Intune budete moct nasadit další jazyky pro aplikace Office 365 Pro Plus spravované prostřednictvím Intune. Seznam dostupných jazyků zahrnuje **Typ** jazykové sady (Základní, Částečná a Kontrola pravopisu). Na portálu Azure Portal vyberte **Microsoft Intune** > **Klientské aplikace** > **Aplikace** > **Přidat**. V okně **Přidat aplikaci** v seznamu **Typ aplikace** vyberte v části **Sada Office 365** možnost **Windows 10**. V okně **Nastavení sady aplikací** vyberte **Jazyky**.

####  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Přípony souborů z podnikové (LOB) aplikace Windows <!-- 1884873 -->
Přípony souborů pro Windows obchodní aplikace teď bude zahrnovat *MSI*, *.appx*, *.appxbundle*, *.msix*, a *. msixbundle*. Aplikaci můžete v Microsoft Intune přidat výběrem možností **Klientské aplikace** > **Aplikace** > **Přidat**. Zobrazí se podokno **Přidat aplikaci**, které vám umožní vybrat **Typ aplikace**. Pro obchodní aplikace pro Windows vyberte jako typ aplikace **Obchodní aplikace**, vyberte **Soubor balíčku aplikace** a pak zadejte instalační soubor s příslušnou příponou.

#### <a name="windows-10-app-deployment-using-intune----2309001---"></a>Nasazení aplikace systému Windows 10 pomocí Intune <!-- 2309001 -->
S využitím stávající podpory obchodních aplikací a Microsoft Storu pro obchodní aplikace mohou správci prostřednictvím Intune nasadit většinu svých firemních aplikací koncovým uživatelům, kteří používají zařízení s Windows 10. Správci mohou přidávat, instalovat a odinstalovávat aplikace pro uživatele Windows 10 v různých formátech, jako jsou MSI, Setup.exe nebo MSP. Před stažením a instalací Intune vyhodnotí pravidla požadavků a prostřednictvím centra akcí Windows 10 upozorní koncové uživatele na stav nebo požadavky na restartování. Tato funkce účinně uvolňuje ruce organizacím, které chtějí přesunout tuto úlohu do Intune a do cloudu. Tato funkce je v tuto chvíli ve veřejné verzi Preview. Očekáváme, že během několik dalších měsíců přidáme k této funkci důležité nové schopnosti. 

#### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Nastavení zásad ochrany (aplikace) aplikace pro web data <!-- 2662995 -->
Nastavení zásad ochrany aplikací (APP) pro webový obsah na zařízeních s Androidem a iOS bude aktualizované, aby lépe pracovalo s webovými odkazy http a https a také s přenosy dat prostřednictvím univerzálních odkazů iOS a odkazů aplikací pro Android. 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Koncový uživatel zařízení a aplikací kontextové nabídky <!-- 2771453 -->
Koncoví uživatelé teď můžou pomocí místní nabídky zařízení a aplikací aktivovat běžné akce, jako jsou například přejmenování zařízení nebo kontrola dodržování předpisů. 

#### <a name="windows-company-portal-keyboard-shortcuts----2771518---"></a>Klávesové zkratky v Portálu společnosti pro Windows <!-- 2771518 -->
Koncoví uživatelé teď budou moct aktivovat akce aplikací a zařízení v aplikaci Portál společnosti pro Windows pomocí klávesových zkratek (akcelerátorů).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>Vytvoření přípony DNS v konfigurační profily sítě VPN na zařízeních s Windows 10<!-- 1333668 -->
Při vytváření profilu konfigurace zařízení v síti VPN (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Windows 10 a novější** Platforma > **VPN** pro typ profilu), zadáváte nastavení DNS. S touto aktualizací můžete také zadat v Intune více **přípon DNS**. Pokud použijete přípony DNS, můžete k vyhledání síťového prostředku použít jeho krátký název místo plně kvalifikovaného názvu domény (FQDN). V této aktualizaci můžete v Intune změnit pořadí přípon DNS.
Seznam aktuálních nastavení DNS je v [nastavení sítě VPN ve Windows 10](vpn-settings-windows-10.md#dns-settings).
Platí pro: Zařízení s Windows 10

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Podpora pro vždy zapnutá síť VPN pro pracovní profily Androidu enterprise <!-- 1333705 -->
V této aktualizaci můžete využít neustále aktivní připojení VPN na zařízeních s Androidem Enterprise, která používají spravované pracovní profily. Neustále aktivní připojení VPN zůstávají ve spojení nebo se ihned znovu připojí, jakmile uživatel odemkne zařízení, zařízení se restartuje nebo se změní bezdrátová síť. Připojení také můžete přepnout do „zamčeného“ režimu, který blokuje veškerý síťový provoz, dokud není připojení VPN zase aktivní.
Neustále aktivní připojení VPN můžete povolit v nastavení **Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Android Enterprise** pro platformu > **Omezení zařízení** > **Možnosti připojení**.

#### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>Vydává certifikáty SCEP zařízení bez uživatele <!-- 1744554 -->
Certifikáty se v současnosti vydávají jenom uživatelům. S touto aktualizací můžete certifikáty SCEP vydat i zařízením, včetně zařízení bez uživatelů, jako jsou terminály (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Windows 10 a novější** pro platformu > **Certifikát SCEP** pro profil). Další aktualizace zahrnují:
- Vlastnost **Subjekt** v profilu SCEP je nyní vlastní textové pole, které může obsahovat nové proměnné. 
- Vlastnost **Alternativní název subjektu (SAN)** v profilu SCEP má nyní formát tabulky a může obsahovat nové proměnné. Správce může do tabulky přidat atribut a vyplnit hodnotu vlastního textového pole. Alternativní název subjektu (SAN) podporuje následující atributy: 
  - DNS
  - E-mailová adresa
  - HLAVNÍ NÁZEV UŽIVATELE

  Tyto nové proměnné můžete přidat jako statický text do textového pole s vlastní hodnotou. Například atribut DNS můžete přidat jako `DNS = {{AzureADDeviceId}}.domain.com`.

  > [!NOTE]
  > Ve statickém textu alternativního názvu subjektu (SAN) nejdou použít složené závorky, středníky ani svislé čáry (|). Do složených závorek můžete uzavřít jenom jednu z nových proměnných certifikátu zařízení, aby mohla být přijata jako `Subject` nebo `Subject alternative name`. 

Nové proměnné certifikátu zařízení:  

```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
>  - `{{FullyQualifiedDomainName}}` funguje jenom pro Windows a zařízení připojená k doméně. 
>  -  Když do subjektu nebo alternativního názvu subjektu (SAN) pro certifikát zařízení zadáváte vlastnosti zařízení, jako je IMEI, sériové číslo a plně kvalifikovaný název domény, uvědomte si, že osoba, která má k zařízení přístup, může tyto vlastnosti zfalšovat. 

V části [Vytvoření profilu certifikátu SCEP](certificates-scep-configure.md#create-a-scep-certificate-profile) je seznam aktuálních proměnných při vytvoření konfiguračního profilu SCEP. 

Platí pro: Windows 10 a novější a iOS, které jsou podporovány pro Wi-Fi

#### <a name="remotely-lock-uncompliant-devices----2064495---"></a>Vzdálené uzamčení uncompliant zařízení <!-- 2064495 -->
Pokud zařízení nevyhovuje, můžete vytvořit akci, která vychází ze zásady dodržování předpisů a která zařízení vzdáleně zamkne. V Intune vyberte **Dodržování předpisů zařízením**, vytvořte novou nebo vyberte některou ze stávajících zásad > **Vlastnosti**. Vyberte **Akce při nedodržení předpisů** > **Přidat** a zvolte, že chcete zařízení vzdáleně zamknout.
Podporované platformy: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- Windows Phone 8.1 nebo novější 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224---"></a>Windows 10 a novější vylepšení profil beznabídkového režimu na webu Azure Portal <!-- 2748224 -->
Tato aktualizace zahrnuje následující vylepšení konfiguračního profilu zařízení s beznabídkovým režimem s Windows 10 (**Konfigurace zařízení** > **Profily** > **Vytvořit profil** > **Windows 10 a novější** pro platformu > **Beznabídkový režim (Preview)** pro typ profilu): 
- V současnosti můžete na stejném zařízení vytvářet více profilů beznabídkového režimu. Po této aktualizaci bude Intune u každého zařízení podporovat jenom jeden profil. Pokud přesto potřebujete více profilů beznabídkového režimu, můžete použít vlastní identifikátor URI.
- V profilu **Beznabídkový režim s více aplikacemi** můžete vybrat velikost dlaždice aplikace a určit pořadí **rozložení nabídky Start** v mřížce aplikace. Pokud chcete provádět vlastní úpravy většího rozsahu, pokračujte k odeslání souboru XML.
- Nastavení aplikace Kiosk Browser se přesouvají do nastavení **Veřejný terminál**. V současnosti má nastavení **Kiosk Web Browser** na webu Azure Portal vlastní kategorii.
Platí pro: Windows 10 a novější




### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Použití Autopilotu profilu pro zaregistrovaná zařízení Windows 10 ještě není zaregistrované pro Autopilot <!-- 1558983 -->
Profily Autopilotu můžete použít u zaregistrovaných zařízení s Windows 10, která nejsou zaregistrovaná do Autopilotu. V profilu Autopilotu zvolte možnost **Převést všechna cílová zařízení na AutoPilot**, abyste mohli k automatické registraci zařízení bez Autopilotu použít službu nasazení Autopilotu. Vyřízení registrace trvá 48 hodin. Jakmile bude registrace zařízení zrušena a zařízení bude resetováno, Autopilot zajistí registraci.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564---"></a>Vytvořit a přiřadit profily více stránka stavu registrace na skupiny Azure AD <!-- 2526564 -->
Nově můžete [vytvořit a přiřadit](windows-enrollment-status.md) více profilů stránky o stavu registrace skupinám Azure ADD.

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune---2748613--"></a>Migrace z programu registrace zařízení Apple Business Manager v Intune <!--2748613-->
V Intune funguje Apple Business Manager (ABM), takže je možné upgradovat účet z Programu registrace zařízení (DEP) na ABM. Proces v Intune je stejný. Pokud chcete účet Apple upgradovat z DEP na ABM, přejděte na [ https://support.apple.com/HT208817]( https://support.apple.com/HT208817).

### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page---2748656--"></a>Upozornění a registrace stav karty na stránce s přehledem registrace zařízení <!--2748656-->
Na stránce s přehledem registrace zařízení se teď zobrazují upozornění a chyby registrace na samostatných kartách.

### <a name="device-management"></a>Správa zařízení

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices----2451462----"></a>Omezí aplikace a zablokovat přístup k prostředkům společnosti na zařízeních s Androidem <!-- 2451462  -->  
V části **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu** > **Android** > **Zabezpečení systému** v oddílu *Zabezpečení zařízení* existuje nové nastavení s názvem **Omezené aplikace**. Nastavení **Omezené aplikace** pomocí zásad dodržování předpisů blokuje přístup k firemním prostředkům, pokud jsou v zařízení nainstalované některé aplikace. Zařízení se považuje za neodpovídající předpisům, dokud se z něj aplikace s omezeným přístupem neodeberou.
Platí pro: 
- Android

<!-- ########################### -->
## <a name="notices"></a>Sdělení

[!INCLUDE [Intune notices](./includes/intune-notices.md)]
