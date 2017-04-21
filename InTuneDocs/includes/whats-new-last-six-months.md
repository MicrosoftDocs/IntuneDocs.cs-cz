## <a name="march-2017"></a>Březen 2017

### <a name="new-capabilities"></a>Nové funkce

#### <a name="support-for-skycure"></a>Podpora aplikace Skycure

Přístup mobilních zařízení k podnikovým prostředkům teď můžete řídit pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Skycure. Je to řešení ochrany před mobilními hrozbami integrované v Microsoft Intune. Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých běží služba Skycure. Patří do ní:

- Fyzická ochrana
- Síťová ochrana
- Ochrana aplikací
- Ochrana chyb zabezpečení

Na základě posouzení rizik aplikací Skycure, které se povoluje přes zásady dodržování předpisů v Intune, můžete nakonfigurovat zásady podmíněného přístupu EMS. Tyto zásady můžete použít k povolení nebo blokování přístupu zařízení nesplňujících požadavky k podnikovým prostředkům na základě zjištěných hrozeb. Další informace najdete v článku [Konektor Skycure Mobile Threat Defense](/intune/deploy-use/skycure-mobile-threat-defense-connector).

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nové uživatelské prostředí aplikace Portál společnosti pro Android <!--621622-->

Kvůli modernějšímu vzhledu a chování a lepšímu uživatelskému prostředí bude aktualizováno uživatelské rozhraní aplikace Portál společnosti pro Android. K významným aktualizacím patří:

- Barvy: IT oddělení může v záhlaví karet aplikace Portál společnosti definovat firemní barvy.
- Aplikace: Na kartě **Aplikace** jsou aktualizovaná tlačítka **Vybrané aplikace** a **Všechny aplikace**.
- Hledání: Na kartě **Aplikace** má tlačítko **Hledat** podobu plovoucího tlačítka akce.
- Navigace mezi aplikacemi: Zobrazení **Všechny aplikace** obsahuje karty **Doporučené**, **Vše** a **Kategorie**, které zjednodušují navigaci.
- Podpora: Karty **Moje zařízení** a **Kontaktovat IT** jsou aktualizované tak, aby byly zřetelnější.

Další podrobnosti o těchto změnách najdete v článku [Aktualizace uživatelského rozhraní pro aplikace Intune pro koncové uživatele](/intune/whats-new/whats-new-in-intune-app-ui).

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Nespravovaná zařízení mají přístup k přiřazeným aplikacím <!--664691-->

Jako součást změn v návrhu na webu Portál společnosti budou moci uživatelé iOSu a Androidu na svoje nespravovaná zařízení instalovat aplikace, které mají přiřazené jako dostupné bez registrace. S použitím přihlašovacích údajů pro Intune se budou moct uživatelé přihlásit na web Portál společnosti a zobrazit seznam aplikací, které mají přiřazené. Balíčky aplikací, které jsou dostupné bez registrace, jsou k dispozici ke stažení prostřednictvím webu Portál společnosti. Aplikace, které vyžadují registraci, aby je bylo možné nainstalovat, nejsou touto změnou ovlivněny, protože když budou chtít tyto aplikace uživatelé nainstalovat, zobrazí se jim výzva k registraci.

#### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Podepisovací skript pro Portál společnosti pro Windows 10 <!--941642-->

Pokud potřebujete stáhnout aplikaci Portál společnosti pro Windows 10 a nainstalovat ji bokem, můžete použít skript, který zjednoduší a zefektivní proces podepisování aplikací ve vaší organizaci.   Informace o tom, jak tento skript stáhnout, a pokyny k jeho použití najdete v článku [Microsoft Intune Signing Script for Windows 10 Company Portal](https://aka.ms/win10cpscript) (Podepisovací skript Microsoft Intune pro Portál společnosti pro Windows 10) na webu TechNet. Další podrobnosti o tomto oznámení najdete v článku [Updating your Windows 10 Company Portal app](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) (Aktualizace aplikace Portál společnosti pro Windows 10) na blogu týmu podpory Intune.


### <a name="notices"></a>Sdělení

#### <a name="support-for-ios-103"></a>Podpora pro iOS 10.3

Uživatelé iOSu mají k dispozici verzi iOS 10.3 od 27. března 2017. Všechny stávající scénáře Intune MDM a MAM jsou kompatibilní s nejnovější verzí OS od společnosti Apple. Předpokládáme, že všechny existující funkce Intune aktuálně dostupné pro správu zařízení s iOSem budou v zařízeních a aplikacích uživatelů nadále fungovat, i když si iOS upgradují na iOS 10.3.

V současnosti nejsou známy žádné problémy. Pokud se vyskytne problém s iOSem 10.3, kontaktujte prosím [tým podpory Intune](/intune/troubleshoot/contact-assisted-phone-support-for-microsoft-intune).

#### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Vylepšená podpora pro uživatele Androidu v Číně <!--720444-->

Vzhledem k absenci obchodu Google Play v Číně musí zařízení s Androidem získávat aplikace z čínských obchodů. Portál společnosti bude tuto situaci podporovat tím, že uživatele Androidu v Číně přesměruje na stažení aplikací Portál společnosti a Outlook z místních obchodů s aplikacemi. Tato změna vylepší uživatelské prostředí při povolených zásadách podmíněného přístupu, a to jak při správě mobilních zařízení, tak při správě mobilních aplikací. Aplikace Portál společnosti a Outlook pro Android jsou dostupné v následujících čínských obchodech s aplikacemi:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

#### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>Osvědčený postup: Ujistěte se, že aplikace Portál společnosti jsou aktuální. <!--879465-->

V prosinci 2016 jsme vydali aktualizaci umožňující vynucení pro vícefaktorové ověřování (MFA) u skupiny uživatelů, když zaregistrují zařízení s iOSem, Androidem, Windows 8.1+ nebo Windows Phone 8.1+. Tato funkce nefunguje bez některých základních verzí aplikace Portál společnosti pro Android (v5.0.3419.0+) a iOS (v2.1.17+).

Microsoft průběžně zdokonaluje Intune přidáváním nových funkcí do konzoly i do aplikací Portál společnosti na všech podporovaných platformách. Microsoft proto vydává opravy jenom pro problémy, které se vyskytly v aktuální verzi aplikace Portál společnosti. Aby se vám tedy s aplikacemi pracovalo co nejlépe, doporučujeme používat nejnovější verze aplikací Portál společnosti.

>[!Tip]
> Požádejte uživatele, aby si na svých zařízeních nastavili automatické aktualizace aplikací z příslušného obchodu s aplikacemi. Pokud jste ve sdílené síťové složce zpřístupnili aplikaci Portál společnosti pro Android, můžete její nejnovější verzi stáhnout z webu [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=49140).

#### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>Aplikace Microsoft Teams jsou teď povolené pro správu mobilních aplikací (MAM) v iOSu a Androidu

Společnost Microsoft oznámila obecnou dostupnost aplikací Microsoft Teams. Aktualizované aplikace Microsoft Teams pro iOS a Android teď můžou využívat možnosti správy mobilních aplikací (MAM) v Intune. Vaše týmy tedy můžou spolupracovat na různých zařízeních a zároveň je zajištěná ochrana konverzací a firemních dat. Další podrobnosti najdete v [oznámení o Microsoft Teams](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) na blogu Enterprise Mobility and Security.


## <a name="february-2017"></a>Únor 2017

### <a name="new-capabilities"></a>Nové funkce

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizace webu Portál společnosti <!--753980-->
Web Portál společnosti bude podporovat aplikace zaměřené na uživatele, kteří nemají spravovaná zařízení. Tento web bude podobně jako ostatní produkty a služby Microsoftu používat nové kontrastní barevné schéma, dynamické ilustrace a „hamburgerovou“ nabídku ![Obrázek hamburgerové nabídky webu Portál společnosti, která je teď přidaná v levém horním rohu webu Portál společnosti](/intune/whats-new/media/CP_hamburger_menu.png), která bude obsahovat kontaktní údaje helpdesku a informace o existujících spravovaných zařízeních. Cílová stránka bude mít nové uspořádání, které zdůrazní aplikace dostupné uživatelům – s karusely pro Vybrané a Nedávno aktualizované aplikace. Obrázky před a po najdete na [stránce s aktualizacemi uživatelského rozhraní](/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="notices"></a>Sdělení

#### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Migrace skupin nevyžadují pro zařízení s iOSem žádné aktualizace skupin ani zásad <!--898837-->
Pro každou skupinu zařízení s Intune předem přiřazenou profilem registrace podnikového zařízení se během migrace do skupin zařízení Azure Active Directory vytvoří odpovídající dynamická skupina zařízení v adresáři AAD založená na názvu profilu registrace podnikového zařízení. Zajistí se tak, že se budou zařízení během registrace automaticky seskupovat a přijmou stejné zásady a aplikace jako původní skupina Intune.

Jakmile tenant zahájí proces migrace pro seskupování a zacílení, vytvoří Intune automaticky dynamickou skupinu AAD tak, aby odpovídala skupině Intune, na kterou je zacílený profil registrace podnikového zařízení. Pokud správce Intune odstraní cílovou skupinu Intune, neodstraní se odpovídající dynamická skupina AAD. Smažou se členové skupiny a dynamický dotaz, ale skupina samotná zůstane, dokud ji správce IT neodebere přes portál AAD.

Podobně, pokud správce IT změní to, která skupina Intune je cílem profilu registrace podnikového zařízení, vytvoří Intune novou dynamickou skupinu odrážející nové přiřazení profilu, ale neodebere se dynamická skupina vytvořená pro staré přiřazení.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Změna výchozího nastavení: Správa desktopových zařízení s Windows přes nastavení Windows <!--663050-->
Výchozí chování registrace stolních počítačů s Windows 10 se mění. Nové registrace se budou provádět obvyklým tokem registrace agenta MDM, nikoli přes agenta pro počítače. Web Portál společnosti bude uživatelům stolních počítačů s Windows 10 poskytovat pokyny k registraci, které je provedou procesem přidání stolních počítačů s Windows 10 jako mobilní zařízení. Tato změna nebude mít vliv na už zaregistrované počítače, a [pokud chcete](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune), může stolní počítače s Windows 10 vaše organizace pořád spravovat přes agenta pro počítače.

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Vylepšení podpory správy mobilních aplikací pro selektivní vymazávání <!--581242-->
Koncoví uživatelé získají podrobnější pokyny o tom, jak získat zpět přístup k pracovním nebo školním datům v případě, že se data automaticky odebrala kvůli zásadám Doba v offline režimu před vymazáním dat.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Otevírání odkazů Portálu společnosti pro iOS v aplikaci <!--665954-->
Odkazy v aplikaci Portálu společnosti pro iOS, včetně těch, které vedou na dokumentaci a aplikace, se budou otevírat přímo v aplikaci Portál společnosti pomocí integrovaného zobrazení Safari. Tato aktualizace se bude dodávat odděleně od aktualizace služby v lednu.

#### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Nová adresa serveru MDM pro zařízení s Windows <!--893007-->
Uživatelům Windows a Windows Phone se při pokusu o registraci zařízení zobrazí chyba, pokud zadají jako adresu serveru MDM __manage.microsoft.com__ (když se zobrazí výzva). Adresa serveru MDM se mění z __manage.microsoft.com__ na __enrollment.manage.microsoft.com__. Upozorněte uživatele, že mají jako adresu serveru MDM použít __enrollment.manage.microsoft.com__, když se jim zobrazí výzva při registraci zařízení s Windows nebo zařízení Windows Phone. Nastavení CNAME nevyžaduje žádné změny. Další informace o této změně najdete na webu [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nové uživatelské prostředí aplikace Portál společnosti pro Android <!--621622-->
Od března bude aplikace Portál společnosti pro Android odpovídat [specifikacím Material Design](https://material.io/guidelines/material-design/introduction.html) a získá tak modernější vzhled a chování. Toto vylepšené uživatelské prostředí zahrnuje:

* __Barvy__: Záhlaví karet můžou mít barvy podle vaší vlastní palety barev.
* __Rozhraní__: Byla aktualizována tlačítka Vybrané aplikace a Všechny aplikace na kartě Aplikace. Tlačítko Hledat je nyní plovoucí tlačítko akce.
* __Navigace__: V části Všechny aplikace se teď zobrazují karty Doporučené, Vše a Kategorie, které zjednodušují navigaci.
* __Služba__: Zlepšila se čitelnost karet Moje zařízení a Kontaktovat IT.

Obrázky před a po najdete na [stránce s aktualizacemi uživatelského rozhraní](/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Přidružení více nástrojů pro správu k Windows Storu pro firmy <!--926135-->
Pokud k nasazování aplikací pro Windows Store pro firmy používáte více než jeden nástroj pro správu, mohli jste k Windows Storu pro firmy dříve přidružit jenom jeden z nich. Teď už můžete ke Storu přidružit více nástrojů pro správu, například Intune a Configuration Manager. Podrobnosti najdete v článku [Správa aplikací koupených ve Windows Storu pro firmy v Microsoft Intune](/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Co je nového ve veřejné verzi Preview prostředí pro správu Intune v Azure<!--736542-->

Na začátku kalendářního roku 2017 provedeme migraci celého našeho prostředí pro správu do Azure, což umožní výkonnou a integrovanou správu základních pracovních postupů EMS na moderní platformě pro služby, která je rozšiřitelná pomocí rozhraní Graph API.

Noví zkušební tenanti se začnou objevovat ve veřejné verzi Preview nového prostředí pro správu na webu Azure Portal tento měsíc. Funkce a parita se stávající konzolou Intune se ve verzi Preview budou zavádět postupně.

Prostředí pro správu na webu Azure Portal bude využívat nové funkce seskupování a cílení, které už byly oznámeny. Při migraci vašeho stávajícího tenanta do nového prostředí seskupování se provede také vaše migrace do verze Preview nového prostředí pro správu vašeho tenanta. Pokud si chcete otestovat nebo prohlédnout některé nové funkce ještě před migrací vašeho tenanta, zaregistrujte si nový zkušební účet Intune nebo se podívejte na [novou dokumentaci](/intune-azure/introduction/whats-new).

Novinky ve verzi Intune v Azure najdete [zde](/intune-azure/introduction/whats-new).

## <a name="january-2017"></a>Leden 2017

### <a name="new-capabilities"></a>Nové funkce

#### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Sestavy v konzole pro MAM bez registrace <!--677961-->
Pro registrovaná i nezaregistrovaná zařízení se přidaly nové sestavy pro ochranu aplikací. Další informace o tom, jak [monitorovat zásady správy mobilních aplikací pomocí Intune, najdete tady](/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

#### <a name="android-711-support---694397--"></a>Podpora pro Android 7.1.1 <!--694397-->
Intune teď plně podporuje a spravuje Android 7.1.1.

#### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>Řešení problému, kdy zařízení s iOSem nejsou aktivní nebo s nimi nemůže konzola správce komunikovat <!--unknown-->
Když zařízení uživatele ztratí kontakt s Intune, můžete uživateli poskytnout nový postup řešení potíží a pomoct mu tak znovu získat přístup k prostředkům společnosti. Viz [Zařízení nejsou aktivní nebo s nimi nemůže konzola správce komunikovat](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

### <a name="notices"></a>Sdělení

#### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Změna výchozího nastavení: Správa desktopových zařízení s Windows přes nastavení Windows <!--663050-->
Výchozí chování registrace stolních počítačů s Windows 10 se mění. Nové registrace se budou provádět obvyklým tokem registrace agenta MDM, nikoli přes agenta pro počítače.

Web Portál společnosti bude uživatelům stolních počítačů s Windows 10 poskytovat pokyny k registraci, které je provedou procesem přidání stolních počítačů s Windows 10 jako mobilní zařízení. Tato změna nebude mít vliv na už zaregistrované počítače, a [pokud chcete](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune), může stolní počítače s Windows 10 vaše organizace pořád spravovat přes agenta pro počítače.

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Vylepšení podpory správy mobilních aplikací pro selektivní vymazávání <!--581242-->
Koncoví uživatelé získají podrobnější pokyny o tom, jak získat zpět přístup k pracovním nebo školním datům v případě, že se data automaticky odebrala kvůli zásadám Doba v offline režimu před vymazáním dat.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Otevírání odkazů Portálu společnosti pro iOS v aplikaci <!--665954-->
Odkazy v aplikaci Portálu společnosti pro iOS, včetně těch, které vedou na dokumentaci a aplikace, se budou otevírat přímo v aplikaci Portál společnosti pomocí integrovaného zobrazení Safari. Tato aktualizace se bude dodávat odděleně od aktualizace služby v lednu.

#### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizace webu Portál společnosti <!--753980-->
Od února bude web Portál společnosti podporovat aplikace zaměřené na uživatele, kteří nemají spravovaná zařízení. Tento web bude podobně jako ostatní produkty a služby Microsoftu používat nové kontrastní barevné schéma a „hamburgerovou“ nabídku ![Hamburgerová nabídka webu Portál společnosti](/intune/whats-new/media/CP_hamburger_menu.png), která bude obsahovat kontaktní údaje helpdesku a informace o existujících spravovaných zařízeních. Cílová stránka bude mít nové uspořádání, které zdůrazní aplikace dostupné uživatelům – s karusely pro Vybrané a Nedávno aktualizované aplikace. Obrázky staré a nové verze najdete na stránce [Co je nového v uživatelském rozhraní aplikací Intune](/intune/whats-new/whats-new-in-intune-app-ui).

#### <a name="new-documentation-for-app-protection-policies---583398--"></a>Nová dokumentace zásad ochrany aplikací <!--583398-->
Aktualizovali jsme naši dokumentaci pro správce a vývojáře aplikací, kteří chtějí ve svých aplikacích pro iOS a Android zapnout zásady ochrany aplikací (známé jako zásady MAM) pomocí nástroje Intune App Wrapping Tool nebo sady Intune App SDK.

Aktualizovaly se tyto články:

* [Rozhodování o způsobu přípravy aplikací na jejich správu v Microsoft Intune](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Příprava aplikací pro iOS na správu mobilních aplikací přes nástroj Intune App Wrapping](/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Začínáme s Microsoft Intune App SDK](/intune/develop/intune-app-sdk-get-started)
* [Intune App SDK pro iOS – Příručka pro vývojáře](/intune/develop/intune-app-sdk-ios)

Následující články jsou v knihovně dokumentů nové:

* [Modul plug-in Cordova sady Intune App SDK](/intune/develop/intune-app-sdk-cordova)
* [Komponenta Xamarin sady Intune App SDK](/intune/develop/intune-app-sdk-xamarin)

#### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Indikátor průběhu při spuštění Portálu společnosti v iOSu <!--665978-->
Portál společnosti pro iOS zavádí na obrazovce spuštění indikátor průběhu, který uživateli poskytuje informace o probíhajících procesech načítání. Indikátor průběhu bude postupně nahrazovat ikonu zaneprázdnění. To znamená, že někteří uživatelé uvidí nový indikátor průběhu, zatímco jiným se bude dále zobrazovat ikona zaneprázdnění.

## <a name="december-2016"></a>Prosinec 2016

### <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Veřejná verze Preview nového prostředí pro správu Intune v Azure <!--736542-->
Na začátku kalendářního roku 2017 provedeme migraci celého našeho prostředí pro správu do Azure, což umožní výkonnou a integrovanou správu základních pracovních postupů EMS na moderní platformě pro služby, která je rozšiřitelná pomocí rozhraní Graph API. Před všeobecnou dostupností tohoto portálu pro všechny tenanty Intune s radostí oznamujeme, že později tento měsíc začneme vybraným tenantům zavádět verzi Preview tohoto nového prostředí pro správce.

Prostředí pro správu na webu Azure Portal bude využívat nové funkce seskupování a cílení, které už byly oznámeny. Při migraci vašeho stávajícího tenanta do nového prostředí seskupování se provede také vaše migrace do verze Preview nového prostředí pro správu vašeho tenanta. Zatím můžete zjistit další informace o tom, co pro Microsoft Intune na portálu Azure Portal chystáme, v naší [nové dokumentaci](/intune-azure/introduction/what-is-microsoft-intune).

__Integrace se službami Telecom Expense Management na webu Azure Portal ve veřejné verzi Preview__ <!--747605--> Ve verzi Preview teď začínáme na webu Azure Portal zavádět integraci se službami TEM (Telecom Expense Management) třetích stran. Pomocí Intune můžete uplatňovat limity na využívání domácích a roamingových dat. Tyto integrace začínáme zavádět s řešením [Saaswedo](http://www.saaswedo.com). Jestli chcete povolit tuto funkci ve zkušební verzi tenanta, [kontaktujte prosím podporu Microsoftu](/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="new-capabilities"></a>Nové funkce

__Vícefaktorové ověřování na všech platformách__ <!--747590--> Teď můžete vynutit vícefaktorové ověřování (MFA) u vybrané skupiny uživatelů při registraci jejich zařízení se systémem iOS, Android, Windows 8.1+ nebo Windows Phone 8.1+ tak, že na portálu pro správu Azure nakonfigurujete MFA v aplikaci pro registraci Microsoft Intune v Azure Active Directory.

__Možnost omezení registrace mobilního zařízení__ <!--747596--> Intune přidává nová omezení registrace řídící to, které platformy mobilních zařízení se mohou zaregistrovat. Intune odděluje platformy mobilních zařízení, jako je iOS, macOS, Android, Windows a Windows Mobile.
* Omezení registrace mobilních zařízení neomezuje registraci klienta pro počítače.
* Pouze pro iOS existuje další možnost blokování registrace osobně vlastněných zařízení.

Pokud správce IT neoznačí nová zařízení jako vlastněná podnikem, Intune všechna nová zařízení označí jako osobní. Podrobnosti najdete v [tomto článku](/intune/deploy-use/manage-corporate-owned-devices).

### <a name="notices"></a>Sdělení

__Vícefaktorové ověřování při registraci se přesouvá na Azure Portal__ <!--VSO 750545--> Dříve by správci při nastavování vícefaktorového ověřování pro registrace Intune přešli do konzoly Intune nebo do konzoly Configuration Manageru (verze dřívější než z října 2016). S touto aktualizovanou funkcí se teď budete pomocí přihlašovacích údajů Intune přihlašovat na [Microsoft Azure Portal](https://manage.windowsazure.com) a nakonfigurujete nastavení MFA pomocí služby Azure AD. Další informace o tom najdete [tady](https://aka.ms/mfa_ad).

__Aplikace Portál společnosti pro Android je teď dostupná v Číně__ <!--VSO 658093--> Publikujeme aplikaci Portál společnosti pro Android pro stahování v Číně. Vzhledem k absenci obchodu Google Play v Číně musí zařízení s Androidem získávat aplikace z čínských marketplace aplikací. Aplikace Portál společnosti pro Android bude dostupná ke stažení v těchto obchodech:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

Ke komunikaci se službou Microsoft Intune používá aplikace Portál společnosti pro Android služby Google Play. Vzhledem k tomu, že služby Google Play ještě nejsou v Číně dostupné, může provádění kterékoli z následujících úloh trvat až 8 hodin. 

|Konzola správce Intune| Aplikace Portál společnosti Intune pro Android |Web Portál společnosti Intune|   
|---|---|---|
|Úplné vymazání| Odebrání vzdáleného zařízení| Odebrání zařízení (místní a vzdálené)|
|selektivní vymazání| Resetování zařízení| Resetování zařízení|
|Nasazení nových nebo aktualizovaných aplikací| Instalace dostupných obchodních aplikací| Resetování hesla zařízení|
|Vzdálené uzamčení|||
|Resetování hesla|||

### <a name="deprecations"></a>Vyřazení

__Firefox už nebude podporovat Silverlight__ <!--VSO TBA--> Mozilla ve verzi 52 [prohlížeče Firefox](https://www.mozilla.org/firefox) přestává podporovat Silverlight s účinností od března 2017. V důsledku toho se už pomocí Firefoxu ve verzi vyšší než 51 nebudete moct přihlásit ke stávající konzole Intune. Doporučujeme pro přístup ke konzole pro správce používat Internet Explorer 10 nebo 11 nebo [verzi Firefoxu starší než 52](https://ftp.mozilla.org/pub/firefox/releases/). Přechod Intune na Azure Portal umožní podporu celé řady [moderních prohlížečů](/azure/azure-preview-portal-supported-browsers-devices) bez závislosti na Silverlightu.

__Odebrání zásad poštovní schránky mobilních zařízení Exchange Online__ <!--770687--> Od prosince už správci nebudou moct zobrazit nebo nakonfigurovat zásady poštovní schránky mobilních zařízení Exchange Online (EAS) v konzole Intune. Tato změna se bude pro všechny tenanty Intune zavádět v průběhu prosince a ledna. Všechny stávající zásady zůstanou tak, jak jsou nakonfigurované. Ke konfiguraci nových zásad použijte prostředí Exchange Management Shell. Další informace o tom najdete [tady](https://technet.microsoft.com/library/bb123783%28v=exchg.150%29.aspx).

__Aplikace Intune AV Player, Image Viewer a PDF Viewer se už v Androidu dále nepodporují__ <!--747553--> Od poloviny prosince 2016 už uživatelé nebudou moct dál používat aplikace Intune AV Player, Image Viewer a PDF Viewer. Tyto aplikace nahrazuje aplikace Azure Information Protection. Další informace o aplikaci Azure Information Protection najdete [tady](/information-protection/rms-client/mobile-app-faq).

## <a name="november-2016"></a>Listopad 2016

### <a name="new-capabilities"></a>Nové funkce

__Nový Portál společnosti Microsoft Intune pro zařízení s Windows 10__ Společnost Microsoft vydala novou [aplikaci Portál společnosti Microsoft Intune pro zařízení s Windows 10](https://www.microsoft.com/store/apps/9wzdncrfj3pz). Tato aplikace, která využívá nový univerzální formát Windows 10, poskytne uživatelům aktualizované prostředí, které je identické napříč všemi zařízeními s Windows 10, ať už jsou to počítače, nebo mobilní zařízení, a nabídne přitom stejné funkce, které v současnosti využívají.

Tato nová aplikace také uživatelům umožní využít v zařízeních s Windows 10 další funkce platformy, jako je jednotné přihlašování (SSO) a ověřování na základě certifikátů. Tato aplikace bude dostupná jako upgrade stávající aplikace Portál společnosti Windows 8.1 a Portál společnosti Windows Phone 8.1 a instaluje se z Windows Storu. Další podrobnosti najdete na adrese [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

> [!IMPORTANT]
> __Aktualizace v Intune a Androidu for Work__
> Aplikace Android for Work můžete nasazovat s akcí __Požadované__, ale pokud byly vaše skupiny Intune migrovány do nového prostředí Azure AD, můžete aplikace nasazovat jenom jako __Dostupné__.

__Intune App SDK pro modul plug-in Cordova teď podporuje MAM bez registrace__ Vývojáři aplikací můžou teď pomocí modulu plug-in Cordova sady Intune App SDK povolit funkce MAM bez registrace zařízení ve svých aplikacích založených na Cordově pro Android a iOS. Modul plug-in Cordova sady Intune App SDK najdete [tady](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

__Komponenta Xamarin sady Intune App SDK teď podporuje MAM bez registrace__ Vývojáři aplikací teď můžou pomocí komponenty Xamarin sady Intune App SDK povolit funkce MAM bez registrace zařízení ve svých aplikacích založených na Xamarinu pro Android a iOS. Komponentu Xamarin sady Intune App SDK najdete [tady](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

### <a name="notices"></a>Sdělení

__Podpisový certifikát Symantec už k nahrání nevyžaduje podepsanou aplikaci Portál společnosti ve Windows Phonu 8__ Nahrání podpisového certifikátu Symantec už nevyžaduje podepsanou aplikaci Portál společnosti ve Windows Phonu 8. Certifikát jde nahrát nezávisle.

###<a name="deprecations"></a>Vyřazení

__Podpora Portálu společnosti ve Windows Phonu 8__ Podpora Portálu společnosti ve Windows Phonu 8 se přestane nabízet. Podpora pro platformy Windows Phone 8 a WinRT se přestala nabízet v říjnu 2016. Podpora pro Portál společnosti ve Windows Phonu 8 se také přestala nabízet v říjnu 2016.

## <a name="october-2016"></a>Říjen 2016

### <a name="conditional-access-for-mobile-application-management"></a>Podmíněný přístup pro správu mobilních aplikací
Budete moct omezit přístup k Exchangi Online, takže přístup bude možný jenom z aplikací, které podporují zásady správy mobilních aplikací Intune, jako je Outlook. [Tato nová funkce](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) vhodně doplňuje zásady správy mobilních aplikací (MAM) Intune, protože vám umožní blokovat přístup k integrovaným poštovním klientům nebo jiným aplikacím, u kterých nebyly nakonfigurovány zásady Intune MAM. Tím zajistíte, že uživatelé mají přístup k datům vaší organizace prostřednictvím aplikací, které mohou být chráněny pomocí služby Intune MAM. Se správou mobilních aplikací Intune můžete začít prostřednictvím webu Azure Portal. V okně Nastavení hledejte novou sekci Podmíněný přístup.

### <a name="conditional-access-for-windows-pcs"></a>Podmíněný přístup pro počítače s Windows
Nově můžete přes konzolu správce Intune vytvářet zásady podmíněného přístupu, které budou počítačům s Windows blokovat přístup k [Exchangi Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) a [SharePointu Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Taky můžete vytvářet zásady podmíněného přístupu, které budou blokovat přístup k desktopovým a univerzálním aplikacím Office.

### <a name="android-for-work-support"></a>Podpora programu Android for Work

> [!IMPORTANT]

> I když aplikace Android for Work můžete nasazovat s akcí __Požadované__, pokud byly vaše skupiny Intune migrovány do nového prostředí Azure AD, můžete aplikace nasazovat jenom jako __Dostupné__.

Intune je teď součástí programu Android for Work (AfW). Od tohoto měsíce začneme poskytovat podporu funkcí AfW, která bude pokračovat i v následujících měsících. Všimněte si, že dostupné nasazení aplikace AfW využívá nové prostředí pro seskupení a zacílení. Nově zřízené účty služby Intune mohou tuto funkci využívat, jakmile budou mít k dispozici AfW.

[Přečtěte si prohlášení Microsoftu o podpoře Intune pro Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Následující témata pro Intune jsou nová nebo aktualizovaná o informace týkající se Androidu for Work:

Pro IT specialisty:
- [Nastavení Androidu for Work](/intune/deploy-use/set-up-android-for-work)
- [Omezení přístupu k e-mailu v Exchangi Online a novému vyhrazeném prostředí Exchange Online s Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Omezení přístupu k e-mailu v místním systému Exchange a starším vyhrazeném prostředí Exchange Online v Microsoft Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Nastavení zásad dodržování předpisů pro Android for Work](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Jak nasadit aplikace do zařízení s Androidem for Work pomocí Intune](/intune/deploy-use/android-for-work-apps)
- [Konfigurace aplikací pro Android for Work pomocí zásad konfigurace mobilních aplikací](/intune/deploy-use/afw-app-configuration-policy)
- [Nastavení zásad pro Android for Work](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Pro koncové uživatele:
- [Co se stane při vytvoření pracovního profilu](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Vytvoření pracovního profilu a registrace zařízení v Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### <a name="lookout-integration-to-protect-ios-devices"></a>Integrace služby Lookout pro ochranu zařízení s iOSem
V říjnu společnost Microsoft integruje řešení ochrany před mobilními hrozbami ve službě Lookout s cílem chránit pomocí zjišťování malwaru, riskantních aplikací a dalších problémů mobilní zařízení s iOSem. Řešení Lookout vám pomůže určit úroveň ohrožení, která je konfigurovatelná. Ve službě Intune můžete vytvořit pravidlo zásad dodržování předpisů na základě vyhodnocování rizik aplikací Lookout. Pomocí zásad podmíněného přístupu můžete povolit nebo blokovat přístup k prostředkům společnosti na základě stavu dodržování předpisů pro zařízení.

Koncoví uživatelé zařízení s iOSem nesplňujících požadavky budou vyzvaní k registraci. Dále si budou muset před získáním přístupu k firemním datům nainstalovat na svoje zařízení aplikaci Lookout for Work, aktivovat ji a opravit hrozby nahlášené aplikací Lookout for Work. Přečtěte si téma [Konfigurace a nasazení aplikací Lookout for Work](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

### <a name="intune-app-wrapping-tool-for-android"></a>Nástroj Intune App Wrapping Tool for Android
Pomocí nástroje Intune App Wrapping Tool svým aplikacím umožníte používat zásady správy mobilních aplikací (MAM) služby Intune. Podpora zásad Intune MAM je nyní dostupná bez nutnosti registrace zařízení.

### <a name="manage-printing-from-apps-managed-using-mam-policies"></a>Správa tisku z aplikací spravovaných pomocí zásad MAM
Nově je možné zabránit tisku firemních dat z aplikací se zásadami MAM. Toto nastavení je dostupné na webu [Azure Portal](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) a podporují ho zařízení s [iOS](/Intune/deploy-use/ios-mam-policy-settings) i [Androidem](/Intune/deploy-use/android-mam-policy-settings).
<!--TFS 1014328-->

### <a name="support-for-fingerprints-on-android-devices"></a>Podpora otisků prstů na zařízení s Androidem
Zásady správy mobilních aplikací (MAM) pro Android umožňují uživatelům přihlašovat se do aplikace otiskem prstu místo zadáním kódu PIN. Přečtěte si [další informace o nastavení zásad správy mobilních aplikací pro Android](/Intune/deploy-use/android-mam-policy-settings).

### <a name="notices"></a>Sdělení

__Kompatibilita systému Android Samsung KNOX s Intune__ Některé modely telefonů Samsung Galaxy Ace nejde spravovat pomocí Intune jako zařízení se systémem Samsung KNOX. Pokud tato zařízení zaregistrujete v Intune, budou se spravovat jako standardní zařízení s Androidem.

Jde o tyto modely:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Vy a vaši koncoví uživatelé nemusíte nic dělat. Další informace najdete na webu [Samsung KNOX](https://www.samsungknox.com).

__Aplikace Portál společnosti pro Windows 8 je zastaralá, podpora pro platformy Windows Phone 8 a Windows RT se přestává používat__ Od října 2016 přestane Microsoft Intune poskytovat podporu pro Portál společnosti pro Windows 8. Microsoft Intune také přestat poskytovat podporu pro platformy Windows Phone 8 a Windows RT. V důsledku toho nebude možné registrovat ani aktualizovat žádná zařízení s Windows Phone 8 nebo Windows RT.

Zařízení s Windows Phone 8 a Windows 8, která jsou už zaregistrovaná, můžete nadále spravovat. Pokud budete chtít do zařízení s těmito systémy dál bez přerušení distribuovat aplikace, aktualizujte si zařízení Windows 8 a Windows Phone 8 na Windows 8.1 a Windows Phone 8.1 a začněte používat odpovídající aplikaci Portál společnosti pro Windows 8.1 a Windows Phone 8.1.

Od listopadu 2016 přestaneme poskytovat podporu pro Portál společnosti pro Windows Phone 8.
<!--TFS 1255391-->

### <a name="whats-coming"></a>Co připravujeme

__Nový Portál společnosti Microsoft Intune pro zařízení s Windows 10__ Microsoft vydává nový Portál společnosti Microsoft Intune pro zařízení s Windows 10. Tato aplikace, která využívá nový univerzální formát Windows 10, poskytne uživatelům aktualizované prostředí, které je identické napříč všemi zařízeními s Windows 10, ať už jsou to počítače, nebo mobilní zařízení, a nabídne přitom stejné funkce, které v současnosti využívají.

Tato nová aplikace také uživatelům umožní využít v zařízeních s Windows 10 další funkce platformy, jako je jednotné přihlašování (SSO) a ověřování na základě certifikátů. Tato aplikace bude dostupná jako upgrade stávající aplikace Portál společnosti Windows 8.1 a Portál společnosti Windows Phone 8.1 a instaluje se z Windows Storu. Další podrobnosti najdete na adrese [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

## <a name="september-2016"></a>Září 2016
### <a name="new-features-announcements-and-information"></a>Nové funkce, oznámení a informace
* [Podmíněný přístup pro Windows](#windows-conditional-access)
* [Podpora pro iOS 10](#ios-10-support)
* [Nástroj App Wrapping podporuje MAM bez registrace zařízení pro Android a iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Přechod od skupin Intune ke skupinám Azure Active Directory od září](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Integrace aplikace Lookout pro ochranu zařízení s Androidem](#lookout-integration-to-protect-android-devices)
* [Aktualizace aplikace Portál společnosti pro Android, iOS a Windows](#company-portal-updates)
* [Glosář služby Intune](#intune-glossary)
* [Co připravujeme](#whats-coming)

### <a name="windows-conditional-access"></a>Podmíněný přístup pro Windows
Nově můžete přes konzolu správce Intune vytvářet zásady podmíněného přístupu, které budou počítačům s Windows blokovat přístup ke službám Exchange Online a SharePoint Online. Taky můžete vytvářet zásady podmíněného přístupu, které budou blokovat přístup k desktopovým a univerzálním aplikacím Office.

### <a name="ios-10-support"></a>Podpora pro iOS 10
Stávající scénáře Intune MDM a MAM jsou kompatibilní se systémem iOS 10. Tipy naleznete na [blogu týmu podpory služby Intune](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

### <a name="app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios"></a>Nástroj App Wrapping podporuje MAM bez registrace zařízení pro Android a iOS
Nástroj Intune App Wrapping je nástroj příkazového řádku, který slouží k aktivaci Intune MAM v obchodních aplikacích (LOB) pro iOS a Android. Jedná se o nejjednodušší způsob, jak začlenit sadu Intune MAM SDK do vaší aplikace, aby vaše aplikace vynucoval zásady MAM nasazené prostřednictvím služby Intune. Zásady MAM vám umožňují:

1. Zašifrovat data aplikace.
2. Požadovat, aby informační pracovník při spuštění aplikace zadal PIN.
3. Povolit aplikaci přenášet data pouze do ostatních spravovaných aplikací.
4. Zabránit aplikaci zálohovat data do Androidu, iTunes a iCloudu.
5. Povolit vyjmutí, kopírování a vložení z a do pouze ostatních spravovaných aplikací.

Veřejná verze Preview aktualizovaného nástroje Intune App Wrapping nyní podporuje MAM bez registrace zařízení na interních obchodních aplikacích v systémech iOS a Android. To znamená, že koncoví uživatelé mohou používat obchodní aplikace s podporou MAM, aniž by museli svá zařízení registrovat ve službě Intune.

Tuto veřejnou verzi Preview si může kdokoli vyzkoušet a přečíst si užitečnou dokumentaci na GitHubu ve složce msintuneappsdk:

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Před instalací předběžné verze nástroje Microsoft Intune App Wrapper pro Android a iOS si musíte:

* Znovu projít licenční podmínky společnosti Microsoft pro předběžnou verzi nástroje Microsoft Intune App Wrapping pro Android a iOS
* Vytisknout a uchovat pro své záznamy kopii licenčních podmínek. Stažením a používáním předběžné verze nástroje Microsoft Intune App Wrapping pro Android s těmito licenčními podmínkami souhlasíte. Pokud je nepřijímáte, software nepoužívejte.
<!---TFS 1235607--->

### <a name="intune-groups-begin-transitioning-to-azure-active-directory-in-september"></a>Přechod od skupin Intune ke skupinám Azure Active Directory od září
Některé nové účty Intune budou namísto skupin uživatelů Intune používat skupiny zabezpečení služby Azure Active Directory. Budete vědět, že pracujete se skupinami zabezpečení, jelikož stránka se skupinami na portálu Intune bude obsahovat odkaz na portál pro správu Azure.

### <a name="lookout-integration-to-protect-android-devices"></a>Integrace aplikace Lookout pro ochranu zařízení s Androidem
Společnost Microsoft integruje řešení ochrany před mobilními hrozbami v aplikaci Lookout za účelem ochrany mobilních zařízení s Androidem pomocí zjišťování malwaru, riskantních aplikací a dalších problémů na zařízení. Řešení Lookout vám pomůže určit úroveň ohrožení, která je konfigurovatelná. Ve službě Intune můžete vytvořit pravidlo zásad dodržování předpisů na základě vyhodnocování rizik aplikací Lookout. Pomocí zásad podmíněného přístupu můžete povolit nebo blokovat přístup k prostředkům společnosti na základě stavu dodržování předpisů pro zařízení.

Koncoví uživatelé zařízení nesplňujících požadavky budou vyzvání k registraci. Dále si budou muset před získáním přístupu nainstalovat na zařízení s Androidem aplikaci Lookout for Work, aktivovat ji a opravit hrozby nahlášené aplikací Lookout for Work. Další informace najdete v článku [Omezení přístupu na základě rizika zařízení, sítě a aplikace](/intune/deploy-use/device-threat-protection).


### <a name="company-portal-updates"></a>Aktualizace Portálu společnosti

__Android__

<p style="margin-left: 40px">**Přidání oznámení do aplikace Portál společnosti pro Android**<br/>
<p style="margin-left: 40px">Na domovskou stránku aplikace Portál společnosti pro Android byla přidaná nová ikona oznámení. Klepnutí na tuto ikonu otevře stránku Oznámení, kde se koncovým uživatelům zobrazí všechny položky, které v aplikaci Portál společnosti vyžadují pozornost (například že nějaké zařízení nedodržuje předpisy, zpráva o aktualizaci registrací nebo aktivaci registrací). Aplikace Portál společnosti pro iOS už tato oznámení má. Po zavedení stránky Oznámení se už při každém spuštění nebo obnovení aplikace Portál společnosti pro Android nezobrazí stránka Nastavení firemního přístupu, pokud je zařízení už zaregistrované. Pokud vytvoříte vlastní návod pro koncové uživatele, nezapomeňte tuto změnu do dokumentace promítnout. Aktualizované snímky obrazovky najdete [tady](https://aka.ms/androidcpupdate).  

__iOS__
<p style="margin-left: 40px">**Změny v podpoře pro aplikaci Portál společnosti pro iOS**<br/>
<p style="margin-left: 40px">Od všech uživatelů aplikace Portál společnosti pro iOS se nyní vyžaduje, aby používali její nejnovější verzi. Noví uživatelé si mohou stáhnout jenom nejnovější verzi a aktuální uživatelé si musí aplikaci aktualizovat. Nejnovější verze vyžaduje iOS 8.0 nebo novější, takže zařízení se starší verzí iOS nemohou Portál společnosti používat ani nebudou moct zařízení zaregistrovat, dokud si v něm neaktualizují operační systém na iOS 8.0 nebo novější a následně neaktualizují i aplikaci Portál společnosti na nejnovější verzi. Zaregistrovaná zařízení se systémem iOS starším 8.0 se budou spravovat i nadále a budou se zobrazovat v konzole správce Intune.
<!---TFS 1283165--->

<p style="margin-left: 40px">**Vylepšení způsobu, kterým koncoví uživatelé iOSu získávají svoje aplikace**<br/>
<p style="margin-left: 40px">Pro dlaždice aplikací v aplikaci Portál společnosti pro iOS byly provedeny následující změny tak, aby uživatele u všech aplikací odkazovaly na různá zobrazení v jednom umístění – na webu Portál společnosti. Omezení společnosti Apple zakazují, aby se obchodní a spravované aplikace z App Storu zobrazovaly v aplikaci Portál společnosti. Uživatel tak k vyhledání všech svých aplikací musí použít několik zobrazení.

<p style="margin-left: 40px">Dlaždice **Firemní aplikace** dříve odkazovala na seznam všech aplikací na kartě VŠE na webu Portál společnosti a bude tak fungovat i dál. Název dlaždice byl změněn na **Všechny aplikace**.

<p style="margin-left: 40px">Dlaždice **Ostatní aplikace** dříve odkazovala na zobrazení v aplikaci Portál společnosti, ve kterém je uvedený seznam všech aplikací, které Apple aplikaci Portál společnosti povoluje zobrazit. Název dlaždice byl změněn na **Doporučené aplikace**. Po klepnutí na tuto dlaždici uživatelé přejdou na kartu DOPORUČENÉ na webu Portál společnosti.

<p style="margin-left: 40px">Dlaždice **Kategorie** dříve odkazovala na zobrazení v aplikaci Portál společnosti, ve kterém je uvedený seznam kategorií aplikací. Název této dlaždice nebyl změněn, ale nyní odkazuje na kartu KATEGORIE na webu Portál společnosti. Aktualizované snímky obrazovky najdete [tady](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
  <!---TFS 1317133--->

<p style="margin-left: 40px">**Výzva k instalaci aplikace Spravovaný prohlížeč pro iOS, pokud IT specialista nastavil tento požadavek pro aplikaci**<br/>
<p style="margin-left: 40px">Pokud jste nakonfigurovali webový klip tak, aby se otevíral jenom ve spravovaném prohlížeči, a spravovaný prohlížeč není v zařízení nainstalovaný, aplikace Portál společnosti vyzve uživatele, aby nejdřív nainstaloval spravovaný prohlížeč. Teprve potom bude možné nainstalovat příslušný webový klip.
  <!---TFS 1228570--->

__Windows__
<p style="margin-left: 40px">**Přidání tlačítka pro odeslání názoru do aplikace Portál společnosti pro Windows Phone 8.1**<br/>
<p style="margin-left: 40px">Portál společnosti pro Windows Phone 8.1 koncovým uživatelům umožňuje odeslat zpětnou vazbu o aplikaci. Slouží k tomu tlačítko „Odeslat názor“. Tlačítko najdete tak, že klepnete na třítečkovou nabídku v dolní pravé části obrazovky aplikace Portál společnosti a potom na **Odeslat názor**. Shromážděná anonymizovaná zpětná vazba pomůže Microsoftu zlepšit prostředí aplikace Portál společnosti.
<!---TFS 1317806--->

### <a name="intune-glossarybr"></a>Glosář služby Intune</br>
Do knihovny jsme přidali nové téma [Glosář](/intune/understand-explore/intune-glossary), abychom vám pomohli správně chápat některé termíny používané ve službě Intune.

## <a name="august-2016"></a>Srpen 2016
### <a name="app-management"></a>Správa aplikací

__Skryté a zobrazené aplikace pro iOS 9.3__ U zařízení se systémem iOS 9.3 nebo novějším můžete využít seznam skrytých a zobrazených aplikací v obecných zásadách konfigurace iOSu k těmto akcím:
- Určení seznamu aplikací, které budou uživatelům skryté. Uživatelé nebudou moci tyto aplikace zobrazit ani spustit.
- Určení seznamu aplikací, které uživatelé mohou zobrazit a spustit. Žádné jiné aplikace nebude možné zobrazit ani spustit.

Mezi aplikace, které můžete zadat, patří aplikace, které jste nasadili, a integrované aplikace pro iOS, jako jsou Zprávy a Poznámky. Podrobnosti najdete v tématu [Nastavení zásad pro iOS v Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune).
<!---TFS 1279009 checked--->
__Zásady povolených a blokovaných aplikací pro zařízení se systémem Samsung KNOX__ – Teď můžete pro zařízení se systémem Samsung KNOX nakonfigurovat vlastní zásady, které umožňují vytvořit:
- Seznam aplikací, u kterých je v příslušném zařízení blokované spuštění. Aplikace, které jsou definované v seznamu blokovaných aplikací, nejde na zařízení aktivovat, ani když jsou nainstalované.
- Seznam aplikací, které si uživatelé příslušného zařízení mohou nainstalovat z obchodu Google Play. Z tohoto obchodu nejde nainstalovat žádné další aplikace.

Tato nastavení mohou využívat jenom zařízení se systémem Samsung KNOX.
Podrobnosti viz [Použití vlastních zásad povolených a blokovaných aplikací pro zařízení se systémem Samsung KNOX](/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps).
<!---TFS 1311629 checked --->

__Nové aplikace kompatibilní se zásadami správy mobilních aplikací (MAM)__ – Aplikace Yammer pro [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) a [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) je teď kompatibilní se [zásadami správy mobilních aplikací (MAM) služby Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) bez ohledu na to, jestli zařízení je nebo není zaregistrované.

Kompletní seznam aplikací kompatibilních s MAM najdete na webu [aplikací pro Microsoft Intune od partnerů](https://www.microsoft.com/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336 checked--->

__Aplikace Intune Viewer__ – S vydáním nové verze aplikace RMS pro sdílení jsme od srpna 2016 odebrali následující aplikace Intune Viewer:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer pro Android z Google Play

Místo použití aplikací Intune Viewer vám doporučujeme používat novou aplikaci [Rights Management (sdílení RMS) pro Android](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), která pro bezpečné prohlížení firemních souborů na zařízeních s Androidem umožňuje nasadit jednu aplikaci (namísto tří samostatných aplikací). Až se aplikace Intune Viewer už nebude podporovat, bude odebrána z Google Storu a nebude už dostupná pro budoucí použití.

### <a name="device-management"></a>Správa zařízení
__Podpora pro Android 7.0__ – Pro připravovaný operační systém Android 7.0, který je určený pro mobilní zařízení, nabízí Intune podporu „dne 0“.
<!---TFS 1262053--->
### <a name="google-removal-of-remote-passcode-reset-capability-on-android-70-devices"></a>Odebrání funkce pro vzdálené resetování hesla v zařízeních se systémem Android 7.0
Google odebírá správcům IT a koncovým uživatelům možnost vzdáleně resetovat hesla na zařízeních se systémem Android 7.0. V předchozích verzích mohli správci vzdáleně resetovat heslo uživatele e koncoví uživatelé mohli k resetování svých hesel využívat web Portál společnosti.



### <a name="company-portal-updates"></a>Aktualizace Portálu společnosti
__Web Portál společnosti__
- **Odkaz pro zasílání názorů společnosti Microsoft z Portálu společnosti** <br/>
Portál společnosti umožňuje koncovým uživatelům klepnout na nový odkaz Zpětná vazba v dolní části stránky a poslat společnosti Microsoft názory na tuto stránku a zkušenosti s ní. Shromážděná anonymizovaná zpětná vazba pomůže Microsoftu zlepšit prostředí webu Portál společnosti.
<!--- TFS 1313657 checked--->

__iOS__
- **Minimální verze iOS pro Managed Browser byla aktualizovaná na 8.0**<br/>
Aplikaci Microsoft Intune Managed Browser pro iOS byla aktualizována a podporuje zařízení se systémem iOS 8.0 nebo novějším. Přestože v zařízeních s iOSem 7.1 můžou využívat stávající aplikaci Managed Browser, doporučte prosím svým uživatelům, aby aktualizovali na iOSem 8.0 nebo novější a mohli plně využít výhody nových funkcí Managed Browseru.  
<!---TFS 1313253 checked--->

### <a name="whats-coming"></a>Co připravujeme
__Přechod od skupin Intune ke skupinám Azure Active Directory od září 2016__ – Intune vytváří nové prostředí pro správu skupin, které používá skupiny zabezpečení Azure Active Directory (AAD) jako skupiny uživatelů a zařízení v Intune. Tyto skupiny se budou využívat pro veškerou správu skupin a nasazování zásad a profilů, **až zavedeme nový portál pro správu Intune s využitím Azure**.

Toto nové prostředí vás zbaví nutnosti mít mezi službami duplicitní skupiny, **umožní přístup k některým novým funkcím skupin Azure Active Directory Premium (AADP)** a zajistí možnosti rozšíření prostřednictvím PowerShellu a Graphu. Sjednotí se tak i prostředí správy skupin napříč správou podnikové mobility.

Pro zajištění přechodu ke skupinám zabezpečení dojde v **aktuální konzole pro správu** k určitým úpravám. **Tyto změny a také použití skupin zabezpečení AAD budou popsané v dokumentaci k Intune**.

Zákazníci, kteří s Intune začínají, se s **některými změnami skupin zabezpečení setkají dříve než aktuální tenanti**.

Kromě změn ve správě skupin se také **přestanou používat následující funkce**:
- Vyloučení členů nebo skupin při vytvoření nové skupiny
- Skupiny **Neseskupení uživatelé** a **Neseskupená zařízení**
- **Správa skupin** v roli Správce služby
- Vlastní výstrahy na základě skupin pro pravidla oznámení
- Přesun skupin v sestavách
<!--- TFS 1295329--->

__Přidání oznámení na Portál společnosti pro Android__ – V září vydáme aktualizaci Portálu společnosti pro Android, která na domovské stránce zavádí novou ikonu **Oznámení**. Klepnutí na tuto ikonu zpřístupní stránku **Oznámení**, kde se koncovým uživatelům zobrazí všechny položky, které v aplikaci Portál společnosti vyžadují pozornost, jako je třeba to, že zařízení nedodržuje předpisy, aktualizace nebo aktivace registrace. Pokud používáte také aplikaci Portál společnosti pro iOS, už jste se s těmito oznámeními setkali. Po zavedení stránky **Oznámení** se při každém spuštění nebo obnovení Portálu společnosti pro Android už nezobrazí stránka **Nastavení firemního přístupu**, pokud je zařízení už zaregistrované. Slyšeli jsme, že celá řada z vás vytvořila pokyny pro koncové uživatele a oceníte, pokud vás předem upozorníme, že vaše pokyny nebo snímky obrazovky mohou vyžadovat aktualizaci. Proveďte prosím aktualizaci dokumentace tak, aby tuto chystanou změnu odrážela. Aktualizované snímky obrazovky najdete tady: https://aka.ms/androidcpupdate.  

### <a name="service-deprecation"></a>Zastaralá služba

- **Změny v podpoře pro aplikaci Portál společnosti pro iOS**<br/>
Od září se začne vyžadovat, aby všichni uživatelé aplikace Portál společnosti Microsoft Intune pro iOS používali její nejnovější verzi. Noví uživatelé si budou moct stáhnout jenom nejnovější verzi a aktuální uživatelé si budou muset aplikaci aktualizovat. Nejnovější verze vyžaduje iOS 8.0 nebo novější, takže zařízení se starší verzí iOS nebudou moct Portál společnosti používat ani nebudou moct zařízení zaregistrovat, dokud si v něm neaktualizují operační systém na iOS 8.0 nebo novější a následně neaktualizují i aplikaci Portál společnosti na nejnovější verzi. Zaregistrovaná zařízení se systémem iOS starším 8.0 se budou spravovat i nadále a budou se zobrazovat v konzole správce Intune.  

- **Minimální verze iOS pro Managed Browser byla aktualizovaná na 8.0**<br/>
V srpnu Intune vydá aktualizovanou aplikaci Microsoft Intune Managed Browser pro iOS, která bude podporovat jenom zařízení se systémem iOS 8.0 nebo novějším. Přestože v zařízeních s iOSem 7.1 bude i dál možné využívat stávající aplikaci Managed Browser, doporučte prosím svým uživatelům, aby aktualizovali na iOSem 8.0 nebo novější a mohli plně využít výhody nových funkcí Managed Browseru.  
<!---TFS 1313253--->

- **Aplikace Portál společnosti pro Windows 8 a Windows Phone 8 se od září 2016 přestanou používat** <br/>
Od září 2016 přestane Microsoft Intune podporovat aplikace Portál společnosti Microsoft Intune pro platformy Windows Phone 8 a Windows 8. Pokud budete chtít do zařízení s těmito systémy dál distribuovat aplikace, aktualizujte si zařízení na Windows 8.1 a Windows Phone 8.1 a začněte používat odpovídající aplikaci Portál společnosti pro Windows 8.1 a Windows Phone 8.1.
<!---TFS 1255391--->
