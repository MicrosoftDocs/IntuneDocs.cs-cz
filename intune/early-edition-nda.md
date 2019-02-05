---
title: Časná edice – Microsoft Intune
titlesuffix: ''
description: Časná edice Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: d50925d9f5422e1bfea01869233c63d6a2889109
ms.sourcegitcommit: 12f8b7f0bca1baa2c1f68dd6af4f16a4814daa11
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/05/2019
ms.locfileid: "55737498"
---
# <a name="the-early-edition-for-microsoft-intune---january-2019"></a>Časná edice Microsoft Intune – leden 2019

> [!Note]
> Smlouvu NDA pro oznámení: Následující změny v Intune jsou ve vývoji. Tyto informace jsou sdíleny ve velmi omezeném rozsahu a platí pro ně dohoda o mlčenlivosti (NDA). Nepublikujte žádné z těchto informací na sociálních sítích nebo veřejných webech, jako jsou Twitter, UserVoice, Reddit apod. 

**Časná edice** poskytuje seznam funkcí, sdílený na základě dohody o mlčenlivosti (NDA), které se chystají v nadcházejících vydáních služby Microsoft Intune. Tyto informace jsou poskytovány v omezené míře a můžou podléhat změnám. Tyto informace netweetujte, nepublikujte na webu UserVoice ani jinak nesdílejte mimo vaši společnost. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a můžou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moct zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se na příslušný kontakt pro skupinu produktů společnosti Microsoft.

Tato stránka se pravidelně aktualizuje. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune na portálu Azure Portal
<!-- 1902 start-->

### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675----"></a>Skripty prostředí PowerShell můžete spustit na hostiteli 64-bit na 64bitových zařízeních <!-- 1862675  -->
Při přidání skriptu prostředí PowerShell do konfiguračního profilu zařízení se skript spustí vždy v 32bitové i v 64bitových operačních systémech. S touto aktualizací správce můžete spustit skript v hostitelském prostředí PowerShell 64-bit na 64bitových zařízeních (**konfigurace zařízení** > **skripty prostředí PowerShell**  >   **Přidat** > **konfigurovat** > **spuštění skriptu v 64bitovém hostitele prostředí PowerShell**).
Další podrobnosti o použití prostředí PowerShell najdete v tématu [Powershellové skripty do Intune](intune-management-extension.md).
Platí pro: Windows 10 a novější

### <a name="rename-an-enrolled-windows-device----1911112----"></a>Přejmenovat zaregistrovaná zařízení s Windows <!-- 1911112  -->
Budete moct přejmenovat zaregistrovaná zařízení s Windows 10 (RS4 nebo novější). Chcete-li provést, zvolte **Intune** > **zařízení** > **všechna zařízení** > zvolte zařízení > **přejmenování zařízení**.

### <a name="assign-scep-certificates-to-a-userless-macos-device-------2340521-----"></a>Přiřadit zařízení bez uživatelů macOS certifikáty SCEP    <!-- 2340521   -->
Budete moct přiřadit certifikát protokolu SCEP (Simple Enrollment) certifikáty do zařízení bez uživatelů macOS a certifikát přidružit k Wi-Fi nebo profily sítě VPN. Tím se rozšíří na stávající podporu jsme již [přiřadit certifikátů do zařízení bez uživatelů, na kterých běží Windows, iOS a Android](certificates-scep-configure.md#create-a-scep-certificate-profile).

### <a name="intune-conditional-access-ui-update------2432313----"></a>Aktualizace uživatelského rozhraní podmíněného přístupu Intune   <!-- 2432313  -->
Nyní vylepšení v uživatelském rozhraní podmíněného přístupu v konzole Intune. Mezi ně patří:
- Nahraďte Intune *podmíněného přístupu* okna okno ze služby Azure Active Directory. Tím se zajistí, že budete mít přístup k široké spektrum nastavení a konfigurací podmíněného přístupu, která zůstává technologie Azure AD.
- Přemístit *konektoru služby Exchange* instalační program na to, co je aktuálně *přístup k místnímu* okno. Můžeme také přejmenovat toto okno k *přístup k Exchangi*. Tato změna zkonsoliduje, kde můžete konfigurovat a monitorovat podrobnosti související s Exchange online a místně.

### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355----"></a>Intune bude využívat služby Google Play API chránit na zařízení s Androidem <!-- 2577355  -->
Někteří správci IT potýkají s na šířku BYOD, kde koncoví uživatelé uvíznout kořenová nebo jailbreaking svůj mobilní telefon. Toto chování, když někdy není nesprávně míněný, výsledkem jednorázové přihlášení řada zásad Intune, které jsou nastaveny, aby bylo možné chránit data vaší organizace na zařízeních koncových uživatelů. Proto Intune poskytuje detekce rootů a jailbreaků pro zařízení zaregistrovaná a zruší. V této vydané verzi bude Intune využívat nyní Google Play ochrana rozhraní API pro přidání do naší stávající zjišťování kontroly kořenové pro neregistrovaná zařízení. Zatímco Google nesdílí rozsahu zjišťování kontroly kořenové, ke kterým dochází, Očekáváme, že tato rozhraní API pro detekci uživatelé, kteří mají jejich zařízení z jakéhokoli důvodu z vlastního nastavení zařízení, abyste mohli získat novější aktualizace operačního systému na starší zařízení s rootem. Tito uživatelé mohou pak blokovat přístup k podnikovým datům, nebo jejich podnikové účty se můžou vymazat z jejich povolené zásadou. Pro další hodnoty, správce IT budou mít několik sestav aktualizací v rámci okna Intune App Protection – "Uživatelé označení příznakem" sestava bude obsahovat, kteří uživatelé jsou zjištěny přes Google Play Protect kontrola SafetyNet API "Potenciálně škodlivé aplikace" sestavy se Zobrazit aplikace, které jsou zjištěny prostřednictvím ověření aplikace rozhraní API společnosti Google skenování. Tato funkce je dostupná v systému Android. 

### <a name="win32-app-information-available-in-troubleshooting-blade----2617342------"></a>Informace pro aplikace Win32 k dispozici v okně řešení potíží <!-- 2617342    -->
Bude moct shromažďovat soubory protokolů selhání instalace aplikace Win32 z aplikace Intune **Poradce při potížích s** okno. Další informace o řešení potíží s instalací aplikace najdete v tématu [řešit problémy při instalaci aplikace](troubleshoot-app-install.md).

### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135----"></a>Prohlížeč beznabídkového režimu a prohlížeče Microsoft Edge aplikace můžou běžet na zařízeních s Windows 10 v celoobrazovkovém režimu. <!-- 2935135  -->
Zařízení s Windows 10 v beznabídkovém režimu můžete použít ke spuštění aplikace jeden nebo více aplikací. Tato aktualizace zahrnuje několik změn pomocí aplikace prohlížeče v režimu veřejného terminálu, včetně:

- Přidat do prohlížeče Microsoft Edge nebo prohlížeči Kiosk spuštěné jako aplikace na zařízení beznabídkového režimu (**konfigurace zařízení** > **profily** > **nový profil**  >  **Windows 10 a novější** pro platformu > **veřejného terminálu** pro typ profilu).
- Omezit Microsoft Edge, takže můžete (nebo nemůže) spustit v celoobrazovkovém režimu (**konfigurace zařízení** > **profily** > **nový profil**  >  **Windows 10 a novější** pro platformu > **omezení zařízení** pro typy profilů > **prohlížeče Microsoft Edge**). Když nelze spustit v celoobrazovkovém režimu, můžete koncovým uživatelům změnit nastavení Microsoft Edge.

Seznam nastavení najdete v tématu:

- [Windows 10 a novější zařízení nastavení pro spuštění jako jako veřejný terminál](kiosk-settings-windows.md)
- [Omezení zařízení prohlížeče Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser)

Platí pro: Windows 10 a novější

### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Umožňuje automaticky přiřazovat značky oboru na prostředky vytvořené v rámci správce v tomto oboru <!-- 3173823  -->
Když správce vytvoří prostředek, všechny značky oboru přiřazeno správce automaticky přiřadí tyto nové prostředky.

### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774---"></a>Nová nastavení omezení zařízení pro zařízení s Iosem a macOS <!-- 3448774 -->
Můžete omezit některá nastavení a funkcí na zařízeních s iOS a macOS (**konfigurace zařízení** > **profily** > **nový profil**  >  **iOS** nebo **macOS** pro platformu > **omezení zařízení** pro typ profilu). Tato aktualizace přidává další funkce a nastaveních, pomocí kterých můžete řídit, včetně nastavení čas obrazovky, změna nastavení karty eSIM a mobilní plány, přičemž dojde ke zpoždění uživatele viditelnost aktualizace softwaru, blokování ukládání obsahu do mezipaměti a další.
Pokud chcete zobrazit aktuální funkcích a nastaveních, pomocí kterých můžete omezit, naleznete v tématu:
- [nastavení omezení zařízení s Iosem](device-restrictions-ios.md)
- [nastavení omezení zařízení s macOS](device-restrictions-macos.md)

Platí pro:
- iOS
- macOS

### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202---"></a>Sestava selhání registrace přesune do okna pro registraci zařízení <!-- 3560202 -->
**Nepovedlo registrace** sestavy se přesunou na **monitorování** část **registrace zařízení** okno. Jsou také přidány dva nové sloupce (způsob registrace a verze operačního systému).

### <a name="change-kiosk-to-dedicated-devices----3598402----"></a>Změňte "Veřejného terminálu" na "Vyhrazená zařízení." <!-- 3598402  -->
Zarovnat Android terminologie **veřejného terminálu** se změní na **vyhrazená zařízení** v části profily konfigurace zařízení **Androidu enterprise**  >   **Vlastník zařízení** > **omezení zařízení**.

### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850--3803313----"></a>Safari a odložením uživatele aktualizace softwaru iOS viditelnost, které nastavení se přesouvají v Uživatelském rozhraní Intune <!-- 3640850, , 3803313  -->
Pro zařízení s Iosem můžete nastavit Safari, nastavení a konfigurace aktualizací softwaru. V této aktualizaci se tato nastavení přesouvají do různých částí uživatelského rozhraní Intune:

- Nastavení prohlížeče Safari se přesouvají z **Safari** (**konfigurace zařízení** > **profily** > **nový profil**  >  **iOS** pro platformu > **omezení zařízení** pro typy profilů) k **integrované aplikace**. 
- **Zpoždění viditelnost aktualizace softwaru uživatele pro zařízení s Iosem pod dohledem** nastavení (**aktualizace softwaru** > **aktualizovat zásady pro iOS**) přechází na  **Omezení zařízení** > **Obecné**.

Seznam nastavení najdete v tématu [omezení zařízení s Iosem](device-restrictions-ios.md) a [aktualizace softwaru iOS](software-updates-ios.md).

Platí pro: 
- iOS

### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164----"></a>Povolení omezení v nastavení zařízení bylo přejmenováno na čas obrazovky na zařízeních s Iosem <!-- 3699164  -->
Můžete nakonfigurovat **povolení omezení v nastavení zařízení** na hlídaných zařízeních s Iosem (**konfigurace zařízení** > **profily**  >  **Nový profil** > **iOS** pro platformu > **omezení zařízení** pro typy profilů > **Obecné**). V této aktualizaci se toto nastavení bylo přejmenováno na **čas obrazovky (jenom pod dohledem)**. Chování je stejné. Konkrétně: 

- iOS 11.4.1 a dříve: **Blok** zabrání koncovým uživatelům vlastní omezení v nastavení zařízení. 
- iOS 12,0 a novější: **Blok** koncovým uživatelům zabrání v nastavení své vlastní **obrazovky čas** v nastavení zařízení, včetně omezení obsahu a ochrana osobních údajů. Zařízení upgradovat operační systém na iOS 12.0 už nezobrazí na kartě omezení v nastavení zařízení. Tato nastavení jsou v **obrazovky čas**. 

Seznam nastavení najdete v tématu [omezení zařízení s Iosem](device-restrictions-ios.md).

Platí pro: 
- iOS

### <a name="app-status-details-for-ios-apps----3761235----"></a>Podrobnosti o stavu aplikace pro aplikace pro iOS <!-- 3761235  -->
Bude nové aplikace instalace chybové zprávy související s tímto:
- Selhání aplikace VPP při instalaci na sdílený iPad
- Chyba při app storu je zakázaná.
- Nepodařilo se najít licence VPP pro aplikaci
- Selhání instalace aplikace pro systém s poskytovatele řešení MDM.
- Nepodařilo se nainstalovat aplikace, když je zařízení v režimu ztráty nebo celoobrazovkový režim
- Nepodařilo se nainstalovat aplikaci, když uživatel není přihlášen k App Store

V Intune, vyberte **klientské aplikace** > **aplikace** > "Název aplikace" > **stav instalace zařízení**. Bude k dispozici v nové chybové zprávy **podrobnosti o stavu** sloupce.

<!-- 1901 start -->

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Nasazení služby online licenci pro obchodní aplikace pro Microsoft Store <!-- 1672660  -->
Budete moct přiřadit vyžaduje online licencovaných Microsoft Store pro obchodní aplikace v kontextu zařízení. Nasazení Microsoft Store pro firmy díky tomu umožní aplikaci nainstalují pro všechny uživatele v zařízení. Tento krok platí jenom na Windows 10 RS4 + desktopových zařízeních. Možnost instalace v kontextu zařízení je k dispozici na stránce pro přiřazení klientské aplikace pro MSFB Online licencované aplikace.

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Aplikace pro Android Enterprise-jsme nasazení aplikace <!-- 1171203 -->
Pro zařízení s Androidem v neregistrovaných ochrany zásady bez registrace aplikace (APP-jsme) scénář nasazení, které budete moct pomocí spravovaného obchodu Google Play můžete nasadit aplikace pro store a obchodní aplikace pro uživatele. Konkrétně může oddělení IT koncovým uživatelům poskytnout aplikaci katalogu a instalace prostředí, které už vyžaduje, aby koncoví uživatelé zmírnit stav zabezpečení svých zařízeních tím, že instalace z neznámých zdrojů. Kromě toho tento scénář nasazení bude poskytovat Vylepšené uživatelské prostředí.

### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Aktualizovat zásady Intune metodu ověřování a instalace aplikace portál společnosti  <!-- 1927359 -->
Na zařízení už zaregistrované prostřednictvím pomocníka prostřednictvím jednoho z metody registrace podnikového zařízení společnosti Apple Intune nebude podporovat aplikace portál společnosti nainstalovaný ručně koncovými uživateli z app storu. Tato změna platí pouze v Apple Pomocníka s nastavením ověřování během registrace. Tato změna ovlivní také pouze zařízení s Iosem zaregistrovaná prostřednictvím:  
* Apple configurator
* Obchodní ředitel společnosti Apple
* Apple School Manager
* Program registrace zařízení Apple (DEP)

Pokud je uživatelé nainstalovat aplikaci portál společnosti z App storu a potom se pokuste registraci těchto zařízení jeho prostřednictvím, dojde k chybě. Tato zařízení bude očekávat, jenom když ho se převede, automaticky, pomocí Intune během registrace použijí portál společnosti. Profily registrace v Intune na portálu Azure portal bude aktualizován, takže můžete určit, jak ověřovat zařízení a pokud se zobrazí v aplikaci portál společnosti. Pokud chcete, aby uživatelé zařízení DEP budou používat aplikaci portál společnosti, musíte zadat předvolby v registrační profil. Kromě toho **identifikaci vašeho zařízení** obrazovky v aplikaci portál společnosti bude brzo zastaralá.  
Chcete-li nainstalovat portál společnosti na již zaregistrované zařízení DEP, budete muset přejít do Intune > klientských aplikací a poslat ho jako spravovaná aplikace pomocí zásad Konfigurace aplikací. Podrobnosti o tom, jak provést tyto kroky budou uvedené v budoucích dokumentace.

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Šablony pro správu jsou ve verzi public preview a přesunout do své vlastní konfigurační profil <!-- 3322847 -->
Šablony pro správu v Intune (**konfigurace zařízení** > **šablony pro správu**) jsou aktuálně ve verzi private preview. Od této aktualizace: Šablony pro správu zahrnuje přibližně 300 nastavení, které jde spravovat v Intune. Dříve tato nastavení existuje pouze v editoru zásad skupiny.
Šablony pro správu jsou k dispozici ve verzi public preview pro správu šablon se přesouvají z **konfigurace zařízení** > **šablony pro správu** k **zařízení konfigurace** > **profily** >**vytvořit profil** > v **platformy**, zvolte  **Windows 10 a novější**v **typ profilu**, zvolte **šablony pro správu**.
Je povoleno oznamování platí pro: Windows 10 a novější

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>MacOS tmavě režimu portál společnosti Intune <!-- 3300524 -->
Portál společnosti pro macOS Intune teď podporuje tmavě režim pro macOS. Když zapnete režim tmavé na zařízení s macOS 10.14 +, portál společnosti upraví jeho vzhled barvy, které odpovídají tohoto režimu.

<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Nastavení zásady ochrany aplikací (APP) pro webová data <!-- 2662995 -->
Nastavení zásad ochrany aplikací (APP) pro webový obsah na zařízeních s Androidem a iOS bude aktualizované, aby lépe pracovalo s webovými odkazy http a https a také s přenosy dat prostřednictvím univerzálních odkazů iOS a odkazů aplikací pro Android.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token Apple VPP používá jiný produkt MDM <!-- 1488946 -->
Intune rozpozná situaci, kdy se token programu hromadných nákupů (VPP) společnosti Apple používá v Intune a zároveň v jiném produktu MDM, a zobrazí podrobnosti.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Vyřazená zařízení na řídicím panelu Dodržování předpisů zařízením <!-- 1981119 -->
V budoucí aktualizaci se z řídicího panelu Dodržování předpisů zařízením odeberou vyřazená zařízení. Změní se tím číselné údaje týkající se dodržování předpisů.

## <a name="notices"></a>Sdělení

V současné době nejsou aktivní žádná sdělení.

### <a name="see-also"></a>Viz také:
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).