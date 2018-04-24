---
title: Předchozí verze
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 02/13/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: NOINDEX,NOFOLLOW
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 57b2ab83f356eac27f668908a9a14b4f9310da19
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="previous-intune-releases"></a>Předchozí verze Intune

Tato stránka představuje seznam oznámení uvedených na stránce s [novinkami v Microsoft Intune](whats-new-in-microsoft-intune.md).

[!INCLUDE [wit_nextref](../includes/whats-new-last-six-months.md)]

## <a name="july-2016"></a>Červenec 2016

### <a name="app-management"></a>Správa aplikací

__Vylepšení prostředí aktualizace zřizovacího profilu aplikace__ – Mobilní obchodní aplikace pro Apple iOS jsou vytvořeny tak, že obsahují zřizovací profil a kód podepsaný certifikátem. Když se taková aplikace spustí na zařízení s iOSem, iOS potvrdí její integritu a vynutí zásady jejím definované zřizovacím profilem.

Podpisový certifikát společnosti, který se používá k podepisování aplikací, má obvykle platnost 3 roky. Platnost zřizovacího profilu ale vyprší už po jednom roce. Prostřednictvím této aktualizace Intune poskytuje nástroje pro proaktivní nasazení nových zásad zřizovacích profilů do zařízení, ve kterých se aplikace blíží vypršení data platnosti, ale certifikát je stále platný. Další informace najdete v tématu věnovaném [použití mobilních zásad zřizovacích profilů pro iOS k zajištění aktuálnosti obchodních aplikací](/intune-classic/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

__Je dostupná sada Xamarin SDK pro aplikace Intune__ – Komponenta Intune App SDK Xamarin umožňuje v mobilních aplikacích pro iOS a Android vytvořených pomocí Xamarinu povolit funkce správy mobilních aplikací Intune. Tuto komponentu najdete v [Xamarin Storu](https://components.xamarin.com/view/Microsoft.Intune.MAM) nebo na [stránce Microsoft Intune Githubu](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### <a name="device-management"></a>Správa zařízení
__Zvýšené limity pro registraci zařízení__ – Služba Intune zvýšila maximální limit pro registraci zařízení z 5 na 15 zařízení na každého uživatele.
<!---TFS 1289896 --->

__Integrace TeamVieweru pro počítače s Windows a klientským softwarem Intune__
[TeamViewer](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>Aktualizace Portálu společnosti

__Web Portál společnosti__
- **Vylepšené prostředí při registraci zařízení s Windows**<br/>
Na webu Portál společnosti byly upřesněny kroky registrace pro Windows 8.1, Windows 10 Desktop a Windows 10 Mobile při použití podmíněného přístupu. Uživatelům se nyní zobrazí samostatné kroky Registrace zařízení a Workplace Join. Snáz tak zjistí stav svého zařízení a dokončí celý proces v případě, že dojde k chybě Workplace Join (WPJ). Očekává se, že tyto samostatné kroky také zjednoduší proces řešení potíží pro správce IT. Když se dříve uživatelé pokusili zaregistrovat a všechny kroky registrace se provedly úspěšně s výjimkou WPJ, zaregistrované zařízení se nezobrazilo v seznamu zařízení a uživatele to mátlo.

__Androidemem__
- **Aplikace Portál společnosti pro Android**<br/>
Když se koncovému uživateli Androidu zobrazí zpráva, která uvádí, že v zařízení chybí požadovaný certifikát, může kliknutím na tlačítko Jak to vyřešit zobrazit [kroky](/intune-classic/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), podle kterých může správce IT problém s certifikátem vyřešit.

- **Omezení instalací aplikací pro instalaci bokem (mimo Store) jenom na registrovaná zařízení**<br/>
Zařízení s Androidem už nemohou instalovat aplikace prostřednictvím webu Portál společnosti, pokud nejsou v Intune zaregistrovaná pomocí aplikace Portál společnosti Intune pro Android.
<!---TFS 1299082--->

__iOS__
- **Změny účtů Správců registrace zařízení v aplikaci Portál společnosti pro iOS**<br/>
Za účelem zvýšení výkonu a možností škálování už Intune v aplikaci Portál společnosti pro iOS v podokně **Moje zařízení** nezobrazuje všechna zařízení Správce registrace zařízení. Zobrazí se pouze místní zařízení, na kterém aplikace běží, a to pouze v případě, že je zaregistrováno prostřednictvím aplikace Portál společnosti.

Uživatel Správce registrace zařízení může na místním zařízení provádět různé akce, ale vzdálenou správu jiných zaregistrovaných zařízení je možné provádět pouze z konzoly správce Intune. Kromě toho se v Intune místo účtů DEM začne používat buď program Apple DEP (Device Enrollment Program), nebo nástroj Apple Configurator. Obě tyto metody registrace již podporují registrace bez zásahu uživatele pro sdílená zařízení s iOSem.

Účty Správce registrace zařízení používejte pouze v případě, že registrace sdílených zařízení bez zásahu uživatele není dostupná. Další informace najdete v části [Registrace firemních zařízení pomocí správce registrace zařízení v Microsoft Intune](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Změna názvů pro funkce Windows
- [Microsoft Passport pro Windows](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) se nyní označuje jako **Windows Hello pro firmy**.
- [Ochrana podnikových dat](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) se nyní označuje jako **Windows Information Protection**.


## <a name="june-2016"></a>Červen 2016
### <a name="intune-service-health"></a>Stav služby Intune
Informace o stavu služby pro Intune se přesouvají do centrálního umístění společně s ostatními službami Microsoftu. Tyto informace nyní najdete na portálu pro správu Office 365 v části věnované stavu služby. Další informace najdete v [tomto příspěvku blogu](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Správa aplikací
- **Vylepšení prostředí pro konfiguraci datových zásad systému Windows 10 Enterprise** Vylepšili jsme možnosti konfigurace zásad ochrany podnikových dat systému Windows 10 souvisejících s vytvářením pravidel aplikací, určováním definice mezí sítě a dalších nastavení pro ochranu podnikových dat. Další informace najdete v tématu [Vytvoření zásady ochrany podnikových dat pomocí Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


### <a name="device-management"></a>Správa zařízení
- **Nastavení zásad programu Windows Defender pro ochranu proti potenciálně nežádoucím aplikacím** Do obecné konfigurace zásady pro Windows 10 Desktop a Mobile bylo přidáno nové nastavení programu Windows Defender nazvané **Detekce potenciálně nežádoucích aplikací**. Pomocí tohoto nastavení můžete ochránit zaregistrované stolní počítače s Windows před spuštěním softwaru, který Windows Defender klasifikuje jako potenciálně nežádoucí. Můžete nastavit ochranu před spuštěním těchto aplikací nebo pomocí režimu auditu upozornit, když se potenciálně nežádoucí aplikace nainstaluje. Další informace najdete v tématu [Nastavení zásad pro Windows 10 v Microsoft Intune](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

### <a name="conditional-access"></a>podmíněný přístup
- **Zásady řízení přístupu k síti Cisco ISE pro Intune**  Zákazníci, kteří používají Cisco Identity Service Engine (ISE) 2.1 a také Microsoft Intune, mohou v modulu ISE nastavit zásady řízení přístupu k síti.

    Když se použijí tyto zásady, zařízení, která se připojují k síti pomocí WiFi nebo VPN, musí splňovat následující podmínky, jinak jim nebude povolen přístup:

    * Musí být spravovaná pomocí Intune.
    * Musí splňovat veškeré nasazené zásady dodržování předpisů Intune.

  Koncovým uživatelům nevyhovujících zařízení se zobrazí výzva k registraci. Pokud chtějí získat přístup, musí všechny problémy s dodržováním předpisů vyřešit.
- **Podmíněný přístup pro prohlížeč** Můžete nastavit zásady podmíněného přístupu pro [Exchange Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune), na základě kterých k nim bude možné získat přístup jenom z podporovaných webových prohlížečů ve spravovaných a vyhovujících zařízeních s iOSem a Androidem. Koncoví uživatelé, kteří se pokusí přihlásit k aplikaci Outlook Web Access (OWA) a webům služby SharePoint pomocí zařízení s iOSem a Androidem, budou vyzváni, aby před přihlášením svoje zařízení zaregistrovali v Intune a opravili všechny problémy, kvůli kterým zařízení nesplňuje pravidla zásad dodržování předpisů.
  <!---TFS 1175844--->

- **Dynamics CRM Online podporuje podmíněný přístup** Můžete pro [Dynamics CRM Online](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune) nastavit zásady podmíněného přístupu, aby k němu měla přístup pouze spravovaná a vyhovující zařízení s iOSem a s Androidem. Koncovým uživatelům, kteří se pokusí přihlásit k mobilní aplikaci Dynamics CRM v iOSu a Androidu, se zobrazí výzva, aby si před přihlášením zařízení zaregistrovali v Intune a aby vyřešili všechny problémy, kvůli kterým zařízení není v souladu s pravidly zásad dodržování předpisů v organizaci.
  <!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Aktualizace Portálu společnosti Intune

__Aplikace Portál společnosti pro Android__

- Když správci IT použijí nové zásady „Požadovat, aby zařízení nepovolovala instalaci aplikací z neznámých zdrojů (Android 4.0 +)“, koncovým uživatelům se zařízeními s Androidem 4.0 nebo novějším zařízení se zobrazí zpráva Musí se zakázat instalace z neznámých zdrojů. Uživatelé budou muset přejít do části **Nastavení** > **Zabezpečení** a vypnout nastavení **Neznámé zdroje**. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat další [informace](/intune-user-help/you-are-asked-to-turn-off-unknown-sources-android) o zprávě a důvodu, proč se po nich vyžaduje vypnutí příslušného nastavení.

- Když správci IT použijí nové zásady „Požadovat, aby zařízení měla povoleno vyhledávání bezpečnostních hrozeb v aplikacích (Android 4.0+)“, koncovým uživatelům se zařízeními s Androidem 4.0 nebo novějším se zobrazí zpráva Vyhledat v zařízení bezpečnostní hrozby. Uživatelé budou muset přejít do části **Nastavení** > **Google** > **Zabezpečení** a zapnout nastavení **Vyhledat v zařízení bezpečnostní hrozby**. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat další [informace](/intune-user-help/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o zprávě a důvodu, proč se po nich vyžaduje zapnutí příslušného nastavení.

- Když správci IT použijí nové zásady „Požadovat, aby bylo zakázané ladění USB (Android 4.2+)“, koncovým uživatelům se zařízeními s Androidem 4.2 nebo novějším se zobrazí zpráva Musí se zakázat ladění USB. Uživatelé budou muset přejít do části **Nastavení** > **Možnosti pro vývojáře** a vypnout nastavení **Ladění USB**. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat další [informace](/intune-user-help/you-are-asked-to-turn-off-usb-debugging-android) o zprávě a důvodu, proč se po nich vyžaduje vypnutí příslušného nastavení.

- Když správci IT použijí nové zásady „Minimální úroveň oprav zabezpečení Androidu (Android 6.0 +)“, koncovým uživatelům se zařízeními s Androidem 6.0 nebo novějším se zobrazí zpráva Toto zařízení nesplňuje minimální úroveň oprav zabezpečení Androidu. Uživatelé budou muset nainstalovat požadovanou opravu zabezpečení. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat [informace](/intune-user-help/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o postupu při instalaci požadované opravy zabezpečení a zjistit, které opravy zabezpečení mají aktuálně nainstalovány.

__Aplikace Portál společnosti pro iOS__

- Když budou koncoví uživatelé instalovat podnikové aplikace, bude se jim nyní zobrazovat vylepšené prostředí instalace aplikace. Pokud instalace aplikace trvá příliš dlouho, uživatelé si můžou zařízení synchronizovat ručně, aby se vynutilo pokračování procesu synchronizace. Pokud si chcete projít pokyny pro koncové uživatele, najdete je v tématu [Ruční synchronizace zařízení s iOSem](/intune-user-help/sync-your-device-manually-ios).

- Aplikace Portál společnosti Microsoft Intune pro iOS je aktualizovaná tak, aby podporovala iOS verze 8.0 a novější. Aktualizace znamená, že můžou koncoví uživatelé nainstalovat aplikaci Portál společnosti a zaregistrovat nová zařízení v Intune, jenom když se na zařízení používá iOS verze 8.0 nebo novější. Uživatelé, kteří už mají zaregistrovaná zařízení používaná v nepodporované verzi iOS, můžou nadále používat aplikaci Portál společnosti nainstalovanou na svých zařízeních.

## <a name="may-2016"></a>Květen 2016
Všechny tyto funkce jsou také podporovány pro hybridní nasazení (nástroj Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší stránce věnované [novinkám pro hybridní nasazení](https://technet.microsoft.com/library/mt718155.aspx).

### <a name="documentation"></a>Dokumentace
Vítejte ve verzi Preview pro [docs.microsoft.com](https://docs.microsoft.com/intune).
Toto je zcela nová platforma s moderním obsahem, navržená tak, aby bylo snazší pro vás, naše zákazníky, pochopit a používat službu Intune.
Informace o všech nových funkcích najdete v tématu [Představení docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/).

### <a name="intune-service-health"></a>Stav služby Intune
Informace o stavu služby pro Intune se přesouvají do centrálního umístění společně s ostatními službami Microsoftu. Tyto informace nyní najdete na [portálu pro správu Office 365](https://portal.office.com/Admin/Default.aspx) v části věnované **stavu služby**.
Další informace najdete v [tomto příspěvku blogu](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Správa aplikací
- **MAM SDK: Podpora konfigurace délky PIN kódu** Bude možné zadat délku PIN kódu pro aplikace MAM podobně, jako je tomu u PIN kódu zařízení. Bude tak nutné, aby koncoví uživatelé dodrželi nová omezení, která nastavíte. Zobrazí se jim mírně upravená obrazovka pro zadání PIN kódu, ve které je teď delší pole pro jeho zadání. Podrobnosti najdete v tématu [Nastavení zásad MAM pro Android](/intune-classic/deploy-use/ios-mam-policy-settings).

- **Skype pro firmy pro iOS a Android** Nyní můžete cílit na Skype pro firmy se [správou mobilních aplikací (MAM) bez zásad registrace](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Jakmile se uživatelé přihlásí, aplikují se zásady MAM.

- **Pro správu pomocí zásad MAM jsou teď dostupné nové aplikace** Na zařízeních, která nejsou zaregistrovaná v Intune, je teď možné přidružit k zásadám MAM aplikace Microsoft Word, Excel a PowerPoint pro Android. Úplný seznam podporovaných aplikací najdete v galerii mobilních aplikací Microsoft Intune na stránce [aplikací pro Microsoft Intune od partnerů](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx).


### <a name="company-portal-updates"></a>Aktualizace Portálu společnosti

#### <a name="android-company-portal-app"></a>Aplikace Portál společnosti pro Android
- **Informační zprávy pro koncové uživatele:** Koncoví uživatelé nyní uvidí informační zprávy aplikace Portál společnosti pro Android, když registrují svoje zařízení nebo je odebírají z Portálu společnosti.

- **Změny účtů správců registrace zařízení v aplikaci Portál společnosti pro Android** Za účelem zvýšení výkonu a možností škálování už Intune v aplikaci Portál společnosti pro Android v podokně Moje zařízení nezobrazuje všechna zařízení správce registrace zařízení (DEM). Zobrazí se pouze místní zařízení, na kterém aplikace běží, a to pouze v případě, že je zaregistrováno prostřednictvím aplikace Portál společnosti. Uživatel Správce registrace zařízení může na místním zařízení provádět různé akce, ale vzdálenou správu jiných zaregistrovaných zařízení je možné provádět pouze z konzoly správce Intune.

#### <a name="company-portal-website"></a>Web Portál společnosti
- **Web Portál společnosti: Informační zpráva s identifikací zařízení bude koncovým uživatelům poskytovat další informace** Koncoví uživatelé mohou nyní snadněji identifikovat zařízení, které vybrali při používání webu Portál společnosti. Pokud je vybrané nesprávné zařízení, budou moct vybrat správné zařízení klepnutím na odkaz **Klepněte sem** v informační zprávě domovské stránky.

### <a name="service-deprecation"></a>Zastaralá služba
- **Aplikace Intune Viewer** V souvislosti s vydáním nové aplikace Sdílení RMS odebíráme od srpna 2016 následující aplikace Intune Viewer:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer pro Android z Google Play

  Místo použití aplikací Intune Viewer vám doporučujeme používat novou aplikaci Rights Management (sdílení RMS) pro Android, která pro bezpečné prohlížení firemních souborů na zařízeních s Androidem umožňuje nasadit jednu aplikaci (namísto tří samostatných aplikací). Přečtěte si víc o aplikaci Sdílení RMS (s odkazem na dokumentaci).

- **Odebrání možnosti cílení pravidel oznámení na vlastní skupiny**
Pravidla oznámení Intune definují, komu se budou z Intune odesílat e-mailové výstrahy. V současnosti můžete nakonfigurovat pravidla oznámení pro odesílání e-mailů všem uživatelům zařízení nebo skupině zařízení služby Intune, kterou jste vytvořili. Přibližně od 1. června 2016 se už cílení na uživatelsky vytvořené skupiny nebude podporovat.

    Pokud byste v současnosti chtěli pravidlo oznámení cílit na skupinu, kterou jste vytvořili pomocí konzoly správce Microsoft Intune, použijete tyto kroky:

    V pracovním prostoru **Správa** klikněte na **Pravidla oznámení** > **Vytvořit nové pravidlo**.

    V kroku 2 Průvodce vytvořením pravidla oznámení vyberte skupiny zařízení, na které bude pravidlo cílit. Tento krok (Vybrat skupiny zařízení) z konzoly Intune odebíráme.

    Předběžná časová osa pro tuto změnu je následující:
    - V červnu 2016 se novým tenantům v Průvodci vytvořením pravidla oznámení nezobrazí krok 2. Stávající tenanty to neovlivní.
    - Zhruba v srpnu 2016 se některým tenantům v tomto průvodci nezobrazí možnost Vybrat skupiny zařízení.
    - Přibližně od října 2016 očekáváme, že se možnost Vybrat skupiny zařízení v tomto průvodci nezobrazí žádným tenantům.


- **Změny v podpoře pro aplikaci Portál společnosti pro iOS**. V nadcházejících měsících bude dostupná aktualizace aplikace Portál společnosti Microsoft Intune pro iOS, která bude podporovat jenom zařízení se systémem iOS 8.0 nebo novějším. Uživatelé si nebudou moci zaregistrovat nová zařízení se systémem starším než iOS 8.0. Zaregistrovaná zařízení se systémem starším než iOS 8.0 se budou spravovat i nadále a po omezenou dobu budou moci pokračovat v používání aplikace Portálu společnosti. Pro přístup k nejnovější verzi aplikace Portál společnosti ale zařízení musí používat iOS 8.0 nebo novější. Doporučujeme vám, abyste upozornili uživatele, že k plnému využití nových funkcí služby Intune musí aktualizovat na iOS 8.0 nebo novější.  


## <a name="april-2016"></a>Duben 2016
Všechny tyto funkce jsou také podporovány pro zákazníky, kteří v současné době využívají hybridní řešení (nástroj Configuration Manager integrovaný s Intune).

### <a name="app-management"></a>Správa aplikací
- **MAM – dodržování předpisů uživateli.**
  Nyní můžete zobrazit [stav](/intune-classic/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) zásad správy aplikací pro všechny uživatele ve vašem tenantovi Azure Active Directory (AAD). Patří mezi ně:
  - Zařízení
  - Aplikace na zařízení

    Stavové hodnoty:

    **Zaregistrováno:** Označuje, že byly zásady nasazeny uživateli, v pracovním kontextu byla použita aplikace a úspěšně byly přijaty zásady.

    **Není zaregistrováno:** Označuje, že byly zásady nasazeny uživateli, ale aplikace od té doby nebyla použita v pracovním kontextu.


- **Kontrolní mechanismy správy mobilních aplikací (MAM) pro zabránění synchronizace kontaktů Outlooku (Android)**
  Nové nastavení je k dispozici pro [správu mobilních aplikací](/intune-classic/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune). Kontakty, které už jsou uložené v nativním adresáři, budou odebrány. Toto nové nastavení je ve výchozím nastavení podporováno v aplikaci Outlook na zařízeních s Androidem.

### <a name="device-management"></a>Správa zařízení
- **Identifikace telefonního čísla pro zařízení vlastněná společností** Telefony, které jsou klasifikovány jako Podnikové, jsou nyní označeny úplným telefonním číslem, když například spustíte sestavu inventáře mobilních zařízení. Telefonní čísla osobních zařízení zaměstnanců (BYOD) jsou nadále maskována hvězdičkami (****). Zobrazují se pouze poslední 4 číslice.


### <a name="company-portal-updates"></a>Aktualizace Portálu společnosti
**Aplikace Portál společnosti pro Android** Uživatelé, kteří si nezaregistrovali svoje zařízení v Intune a kteří nemají nainstalovaný správný certifikát, se nebudou moct přihlásit k aplikaci Portál společnosti pro Android a zobrazí se jim zpráva Nemůžete se přihlásit, protože vašemu zařízení chybí požadovaný certifikát. Součástí zprávy je i odkaz Jak to vyřešit, na který můžou uživatelé klepnout a zobrazit si tak pokyny k instalaci certifikátu. Informace o tom, jaké kroky musí koncoví uživatelé při řešení tohoto problému provést, najdete v tématu [Zařízení nemá požadovaný certifikát](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**Aplikace Portál společnosti pro iOS** Byla přidána podpora pro akci aktualizace obsahu tažením na domovské obrazovce, která zahrnuje uvedené aplikace, uvedená zařízení a kontaktní údaje oddělení IT. Akce aktualizace obsahu potažením nekontroluje informace dodržování předpisů nebo zásad, což lze provést výběrem dlaždice pro aktuální zařízení a klepnutím na tlačítko **Synchronizovat**.

**Aplikace Portál společnosti pro Windows 10 Mobile a Windows Phone 8.1** Když budou koncoví uživatelé instalovat obchodní aplikace, budou se jim nyní zobrazovat vylepšené možnosti instalace aplikace. Pokud instalace aplikace trvá příliš dlouho, uživatelé si můžou zařízení synchronizovat ručně, aby se vynutilo pokračování procesu synchronizace. Pokud si chcete projít pokyny pro koncové uživatele, najdete je v tématu [Ruční synchronizace zařízení pro urychlení instalace aplikací](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Web Portál společnosti** Když budou uživatelé zařízení s Windows 10 Mobile a Windows Phone 8.1 instalovat obchodní aplikace, zobrazí se jim nyní následující nové stavy, díky kterým získají více podrobností o stavu instalace:

* **Čeká se na synchronizaci zařízení** – Uživatel klepl na Nainstalovat a zařízení se teď snaží synchronizovat s infrastrukturou služby Intune. Před instalací je nutné provést synchronizaci. Zpráva Čeká se na synchronizaci zařízení je také odkaz, na který můžou klepnout a zobrazit si tak [pokyny](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) k tomu, jak ručně synchronizovat zařízení s Intune, pokud proces synchronizace trvá dlouho nebo se zastavil.
* **Stahování** – Zpracovává se žádost uživatele o stažení a zařízení stahuje a instaluje aplikaci.

Než byly přidány tyto stavy, uživatelé ztráceli přehled o tom, co se děje, pokud instalace aplikace trvalo dlouhou dobu. Viděli totiž pouze stav Probíhá instalace, který se mohl na obrazovce zobrazovat i několik hodin. To, že se přidaly nové stavy, znamená, že uživatelé namísto volání podpory mohou nyní klepnout na odkaz Čeká se na synchronizaci zařízení a podle pokynů vynutit pokračování procesu synchronizace.

> [!div class="step-by-step"]
> 
> [&larr; **Co je nového v Intune**](whats-new-in-microsoft-intune.md)    
