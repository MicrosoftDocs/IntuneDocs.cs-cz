## <a name="november-2016"></a>Listopad 2016

### <a name="new-capabilities"></a>Nové funkce

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

__Nový Portál společnosti Microsoft Intune pro zařízení s Windows 10:__ Společnost Microsoft vydala novou [aplikaci Portál společnosti Microsoft Intune pro zařízení s Windows 10](https://www.microsoft.com/store/apps/9wzdncrfj3pz). Tato aplikace, která využívá nový univerzální formát Windows 10, poskytne uživatelům aktualizované prostředí, které je identické napříč všemi zařízeními s Windows 10, ať už jsou to počítače, nebo mobilní zařízení, a nabídne přitom stejné funkce, které v současnosti využívají.

Tato nová aplikace také uživatelům umožní využít v zařízeních s Windows 10 další funkce platformy, jako je jednotné přihlašování (SSO) a ověřování na základě certifikátů. Tato aplikace bude dostupná jako upgrade stávající aplikace Portál společnosti Windows 8.1 a Portál společnosti Windows Phone 8.1 a instaluje se z Windows Storu. Další podrobnosti najdete na adrese [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __Aktuální informace o Intune a Android for Work__

> I když aplikace Android for Work můžete nasazovat s akcí __Požadované__, pokud byly vaše skupiny Intune migrovány do nového prostředí Azure AD, můžete aplikace nasazovat jenom jako __Dostupné__.

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

<!--Existing Intune customers can use this feature in production once their tenant has been migrated. Existing customers are welcome to create a trial Intune account to plan for and test this feature until their tenant has been migrated. Any questions on grouping and targeting timelines, please contact our [migration team](mailto:intunegrps@microsoft.com).-->

[Přečtěte si prohlášení Microsoftu o podpoře Intune pro Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Následující témata pro Intune jsou nová nebo aktualizovaná o informace týkající se Androidu for Work:

Pro IT specialisty:
- [Nastavení Androidu for Work](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
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

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

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

Koncoví uživatelé zařízení nesplňujících požadavky budou vyzvání k registraci. Dále si budou muset před získáním přístupu nainstalovat na zařízení s Androidem aplikaci Lookout for Work, aktivovat ji a opravit hrozby nahlášené aplikací Lookout for Work. Další informace najdete v článku [Omezení přístupu na základě rizika zařízení, sítě a aplikace](https://docs.microsoft.com/en-us/intune/deploy-use/restrict-access-based-on-device-network-app-risk).


### <a name="company-portal-updates"></a>Aktualizace Portálu společnosti

__Android__

<p style="margin-left: 40px">**Přidání oznámení do aplikace Portál společnosti pro Android**<br/>
<p style="margin-left: 40px">Na domovskou stránku aplikace Portál společnosti pro Android byla přidaná nová ikona oznámení. Klepnutí na tuto ikonu otevře stránku Oznámení, kde se koncovým uživatelům zobrazí všechny položky, které v aplikaci Portál společnosti vyžadují pozornost (například že nějaké zařízení nedodržuje předpisy, zpráva o aktualizaci registrací nebo aktivaci registrací). Aplikace Portál společnosti pro iOS už tato oznámení má. Po zavedení stránky Oznámení se už při každém spuštění nebo obnovení aplikace Portál společnosti pro Android nezobrazí stránka Nastavení firemního přístupu, pokud je zařízení už zaregistrované. Pokud vytvoříte vlastní návod pro koncové uživatele, nezapomeňte tuto změnu do dokumentace promítnout. Aktualizované snímky obrazovky najdete [tady](https://aka.ms/androidcpupdate).  

__iOS__
<p style="margin-left: 40px">**Změny v podpoře pro aplikaci Portál společnosti pro iOS**<br/>
<p style="margin-left: 40px">Od všech uživatelů aplikace Portál společnosti pro iOS se nyní vyžaduje, aby používali její nejnovější verzi. Noví uživatelé si mohou stáhnout jenom nejnovější verzi a aktuální uživatelé si musí aplikaci aktualizovat. Nejnovější verze vyžaduje iOS 8.0 nebo novější, takže zařízení se starší verzí iOS nemohou Portál společnosti používat ani nebudou moct zařízení zaregistrovat, dokud si v něm neaktualizují operační systém na iOS 8.0 nebo novější a následně neaktualizují i aplikaci Portál společnosti na nejnovější verzi. Zaregistrovaná zařízení se systémem iOS starším 8.0 se budou spravovat i nadále a budou se zobrazovat v konzole správce Intune.
<!---TFS 1283165--->

<p style="margin-left: 40px">**Vylepšení způsobu, kterým koncoví uživatelé iOS získávají svoje aplikace**<br/>
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
Do knihovny jsme přidali nové téma [Glosář](https://docs.microsoft.com/intune/understand-explore/intune-glossary), abychom vám pomohli správně chápat některé termíny používané ve službě Intune.

## <a name="august-2016"></a>Srpen 2016
### <a name="app-management"></a>Správa aplikací
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

__Skryté a zobrazené aplikace pro iOS 9.3__ U zařízení se systémem iOS 9.3 nebo novějším můžete využít seznam skrytých a zobrazených aplikací v obecných zásadách konfigurace iOSu k těmto akcím:
- Určení seznamu aplikací, které budou uživatelům skryté. Uživatelé nebudou moci tyto aplikace zobrazit ani spustit.
- Určení seznamu aplikací, které uživatelé mohou zobrazit a spustit. Žádné jiné aplikace nebude možné zobrazit ani spustit.

Mezi aplikace, které můžete zadat, patří aplikace, které jste nasadili, a integrované aplikace pro iOS, jako jsou Zprávy a Poznámky. Podrobnosti najdete v tématu [Nastavení zásad pro iOS v Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune).
<!---TFS 1279009 checked--->
__Zásady povolených a blokovaných aplikací pro zařízení se systémem Samsung KNOX__ – Teď můžete pro zařízení se systémem Samsung KNOX nakonfigurovat vlastní zásady, které umožňují vytvořit:
- Seznam aplikací, u kterých je v příslušném zařízení blokované spuštění. Aplikace, které jsou definované v seznamu blokovaných aplikací, nejde na zařízení aktivovat, ani když jsou nainstalované.
- Seznam aplikací, které si uživatelé příslušného zařízení mohou nainstalovat z obchodu Google Play. Z tohoto obchodu nejde nainstalovat žádné další aplikace.

Tato nastavení mohou využívat jenom zařízení se systémem Samsung KNOX.
Podrobnosti viz [Použití vlastních zásad povolených a blokovaných aplikací pro zařízení se systémem Samsung KNOX](https://docs.microsoft.com/en-us/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps).
<!---TFS 1311629 checked --->

__Nové aplikace kompatibilní se zásadami správy mobilních aplikací (MAM)__ – Aplikace Yammer pro [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) a [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) je teď kompatibilní se [zásadami správy mobilních aplikací (MAM) služby Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) bez ohledu na to, jestli zařízení je nebo není zaregistrované.

Kompletní seznam aplikací kompatibilních s MAM najdete na webu [aplikací pro Microsoft Intune od partnerů](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

__Aplikace Intune Viewer__ – S vydáním nové verze aplikace RMS pro sdílení jsme od srpna 2016 odebrali následující aplikace Intune Viewer:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer pro Android z Google Play

Místo použití aplikací Intune Viewer vám doporučujeme používat novou aplikaci [Rights Management (sdílení RMS) pro Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), která pro bezpečné prohlížení firemních souborů na zařízeních s Androidem umožňuje nasadit jednu aplikaci (namísto tří samostatných aplikací). Až se aplikace Intune Viewer už nebude podporovat, bude odebrána z Google Storu a nebude už dostupná pro budoucí použití.

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
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Změny v podpoře pro aplikaci Portál společnosti pro iOS**<br/>
Od září se začne vyžadovat, aby všichni uživatelé aplikace Portál společnosti Microsoft Intune pro iOS používali její nejnovější verzi. Noví uživatelé si budou moct stáhnout jenom nejnovější verzi a aktuální uživatelé si budou muset aplikaci aktualizovat. Nejnovější verze vyžaduje iOS 8.0 nebo novější, takže zařízení se starší verzí iOS nebudou moct Portál společnosti používat ani nebudou moct zařízení zaregistrovat, dokud si v něm neaktualizují operační systém na iOS 8.0 nebo novější a následně neaktualizují i aplikaci Portál společnosti na nejnovější verzi. Zaregistrovaná zařízení se systémem iOS starším 8.0 se budou spravovat i nadále a budou se zobrazovat v konzole správce Intune.  

- **Minimální verze iOS pro Managed Browser byla aktualizovaná na 8.0**<br/>
V srpnu Intune vydá aktualizovanou aplikaci Microsoft Intune Managed Browser pro iOS, která bude podporovat jenom zařízení se systémem iOS 8.0 nebo novějším. Přestože v zařízeních s iOSem 7.1 bude i dál možné využívat stávající aplikaci Managed Browser, doporučte prosím svým uživatelům, aby aktualizovali na iOSem 8.0 nebo novější a mohli plně využít výhody nových funkcí Managed Browseru.  
<!---TFS 1313253--->

- **Aplikace Portál společnosti pro Windows 8 a Windows Phone 8 se od září 2016 přestanou používat** <br/>
Od září 2016 přestane Microsoft Intune podporovat aplikace Portál společnosti Microsoft Intune pro platformy Windows Phone 8 a Windows 8. Pokud budete chtít do zařízení s těmito systémy dál distribuovat aplikace, aktualizujte si zařízení na Windows 8.1 a Windows Phone 8.1 a začněte používat odpovídající aplikaci Portál společnosti pro Windows 8.1 a Windows Phone 8.1.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->

## <a name="july-2016"></a>Červenec 2016
### <a name="app-management"></a>Správa aplikací

__Vylepšení prostředí aktualizace zřizovacího profilu aplikace__ – Mobilní obchodní aplikace pro Apple iOS jsou vytvořeny tak, že obsahují zřizovací profil a kód podepsaný certifikátem. Když se taková aplikace spustí na zařízení s iOSem, iOS potvrdí její integritu a vynutí zásady jejím definované zřizovacím profilem.

Podpisový certifikát společnosti, který se používá k podepisování aplikací, má obvykle platnost 3 roky. Platnost zřizovacího profilu ale vyprší už po jednom roce. Prostřednictvím této aktualizace Intune poskytuje nástroje pro proaktivní nasazení nových zásad zřizovacích profilů do zařízení, ve kterých se aplikace blíží vypršení data platnosti, ale certifikát je stále platný. Další informace najdete v tématu věnovaném [použití mobilních zásad zřizovacích profilů pro iOS k zajištění aktuálnosti obchodních aplikací](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

__Je dostupná sada Xamarin SDK pro aplikace Intune__ – Komponenta Intune App SDK Xamarin umožňuje v mobilních aplikacích pro iOS a Android vytvořených pomocí Xamarinu povolit funkce správy mobilních aplikací Intune. Tuto komponentu najdete v [Xamarin Storu](https://components.xamarin.com/view/Microsoft.Intune.MAM) nebo na [stránce Microsoft Intune Githubu](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### <a name="device-management"></a>Správa zařízení
__Zvýšené limity pro registraci zařízení__ – Služba Intune zvýšila maximální limit pro registraci zařízení z 5 na 15 zařízení na každého uživatele.
<!---TFS 1289896 --->

__Integrace TeamVieweru pro počítače s Windows a klientským softwarem Intune__
 – Integrovaný [TeamViewer](https://www.teamviewer.com) v počítačích s Windows a klientským softwarem Intune umožňuje v rámci podpory navazovat relace vzdálené pomoci s počítači se systémem Windows. Tuto podporu poskytují oddělení helpdesku koncovým uživatelům. To zahrnuje systém Windows 7, 8, 8.1 a Windows 10. Podrobnosti najdete v tématu [Běžné úlohy správy počítačů s Windows pomocí počítačového klienta Microsoft Intune](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>Aktualizace Portálu společnosti

__Web Portál společnosti__
- **Vylepšené prostředí při registraci zařízení s Windows**<br/>
Na webu Portál společnosti byly upřesněny kroky registrace pro Windows 8.1, Windows 10 Desktop a Windows 10 Mobile při použití podmíněného přístupu. Uživatelům se nyní zobrazí samostatné kroky Registrace zařízení a Workplace Join. Snáz tak zjistí stav svého zařízení a dokončí celý proces v případě, že dojde k chybě Workplace Join (WPJ). Očekává se, že tyto samostatné kroky také zjednoduší proces řešení potíží pro správce IT. Když se dříve uživatelé pokusili zaregistrovat a všechny kroky registrace se provedly úspěšně s výjimkou WPJ, zaregistrované zařízení se nezobrazilo v seznamu zařízení a uživatele to mátlo.

__Androidemem__
- **Aplikace Portál společnosti pro Android**<br/>
Když se koncovému uživateli Androidu zobrazí zpráva, která uvádí, že v zařízení chybí certifikát, může kliknutím na tlačítko Jak to vyřešit zobrazit [kroky](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) pro instalaci chybějícího certifikátu. Pokud uživatel dokončí tyto kroky, ale zobrazí se mu další chybová zpráva typu chybějící certifikát, měl by kontaktovat správce IT a poskytnout mu tento [odkaz](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), který obsahuje kroky, jejichž prostřednictvím správce může potíže s certifikátem vyřešit.

- **Omezení instalací aplikací pro instalaci bokem (mimo Store) jenom na registrovaná zařízení**<br/>
Zařízení s Androidem už nemohou instalovat aplikace prostřednictvím webu Portál společnosti, pokud nejsou v Intune zaregistrovaná pomocí aplikace Portál společnosti Intune pro Android.
<!---TFS 1299082--->

__iOS__
- **Změny účtů Správců registrace zařízení v aplikaci Portál společnosti pro iOS**<br/>
Za účelem zvýšení výkonu a možností škálování už Intune v aplikaci Portál společnosti pro iOS v podokně **Moje zařízení** nezobrazuje všechna zařízení Správce registrace zařízení. Zobrazí se pouze místní zařízení, na kterém aplikace běží, a to pouze v případě, že je zaregistrováno prostřednictvím aplikace Portál společnosti.

Uživatel Správce registrace zařízení může na místním zařízení provádět různé akce, ale vzdálenou správu jiných zaregistrovaných zařízení je možné provádět pouze z konzoly správce Intune. Kromě toho se v Intune místo účtů DEM začne používat buď program Apple DEP (Device Enrollment Program), nebo nástroj Apple Configurator. Obě tyto metody registrace již podporují registrace bez zásahu uživatele pro sdílená zařízení s iOSem.

Účty Správce registrace zařízení používejte pouze v případě, že registrace sdílených zařízení bez zásahu uživatele není dostupná. Další informace najdete v části [Registrace firemních zařízení pomocí správce registrace zařízení v Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Změna názvů pro funkce Windows
- [Microsoft Passport pro Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) se nyní označuje jako **Windows Hello pro firmy**.
- [Ochrana podnikových dat](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) se nyní označuje jako **Windows Information Protection**.

## <a name="june-2016"></a>Červen 2016
### <a name="intune-service-health"></a>Stav služby Intune
Informace o stavu služby pro Intune se přesouvají do centrálního umístění společně s ostatními službami Microsoftu. Tyto informace nyní najdete na portálu pro správu Office 365 v části věnované stavu služby. Další informace najdete v [tomto příspěvku blogu](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Správa aplikací
- **Vylepšení prostředí pro konfiguraci datových zásad systému Windows 10 Enterprise** Vylepšili jsme možnosti konfigurace zásad ochrany podnikových dat systému Windows 10 souvisejících s vytvářením pravidel aplikací, určováním definice mezí sítě a dalších nastavení pro ochranu podnikových dat. Další informace najdete v tématu [Vytvoření zásady ochrany podnikových dat pomocí Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


### <a name="device-management"></a>Správa zařízení
- **Nastavení zásad programu Windows Defender pro ochranu proti potenciálně nežádoucím aplikacím** Do obecné konfigurace zásady pro Windows 10 Desktop a Mobile bylo přidáno nové nastavení programu Windows Defender nazvané **Detekce potenciálně nežádoucích aplikací**. Pomocí tohoto nastavení můžete ochránit zaregistrované stolní počítače s Windows před spuštěním softwaru, který Windows Defender klasifikuje jako potenciálně nežádoucí. Můžete nastavit ochranu před spuštěním těchto aplikací nebo pomocí režimu auditu upozornit, když se potenciálně nežádoucí aplikace nainstaluje. Další informace najdete v tématu [Nastavení zásad pro Windows 10 v Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

### <a name="conditional-access"></a>podmíněný přístup
- **Zásady řízení přístupu k síti Cisco ISE pro Intune**  Zákazníci, kteří používají Cisco Identity Service Engine (ISE) 2.1 a také Microsoft Intune, mohou v modulu ISE nastavit zásady řízení přístupu k síti.

    Když se použijí tyto zásady, zařízení, která se připojují k síti pomocí WiFi nebo VPN, musí splňovat následující podmínky, jinak jim nebude povolen přístup:

    * Musí být spravovaná pomocí Intune.
    * Musí splňovat veškeré nasazené zásady dodržování předpisů Intune.

 Koncovým uživatelům nevyhovujících zařízení se zobrazí výzva k registraci. Pokud chtějí získat přístup, musí všechny problémy s dodržováním předpisů vyřešit.
- **Podmíněný přístup pro prohlížeč** Můžete nastavit zásady podmíněného přístupu pro [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) a [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune), na základě kterých k nim bude možné získat přístup pouze z podporovaných webových prohlížečů ve spravovaných a vyhovujících zařízeních. Koncoví uživatelé, kteří se pokusí přihlásit k aplikaci Outlook Web Access (OWA) a webům služby SharePoint pomocí zařízení s iOSem a Androidem, budou vyzváni, aby před přihlášením svoje zařízení zaregistrovali v Intune a opravili všechny problémy, kvůli kterým zařízení nesplňuje pravidla zásad dodržování předpisů.
<!---TFS 1175844--->

- **Dynamics CRM Online podporuje podmíněný přístup** Můžete pro [Dynamics CRM Online](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune) nastavit zásady podmíněného přístupu, aby k němu měla přístup pouze spravovaná a vyhovující zařízení s iOSem a s Androidem. Koncovým uživatelům, kteří se pokusí přihlásit k mobilní aplikaci Dynamics CRM na iOS a Androidu, se zobrazí výzva, aby si před přihlášením zařízení zaregistrovali v Intune a aby vyřešili všechny problémy, kvůli kterým zařízení není v souladu s pravidly zásad dodržování předpisů v organizaci.
<!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Aktualizace Portálu společnosti Intune

__Aplikace Portál společnosti pro Android__

- Když správci IT použijí nové zásady „Požadovat, aby zařízení nepovolovala instalaci aplikací z neznámých zdrojů (Android 4.0 +)“, koncovým uživatelům se zařízeními s Androidem 4.0 nebo novějším zařízení se zobrazí zpráva Musí se zakázat instalace z neznámých zdrojů. Uživatelé budou muset přejít do části **Nastavení** > **Zabezpečení** a vypnout nastavení **Neznámé zdroje**. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat další [informace](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) o zprávě a důvodu, proč se po nich vyžaduje vypnutí příslušného nastavení.

- Když správci IT použijí nové zásady „Požadovat, aby zařízení měla povoleno vyhledávání bezpečnostních hrozeb v aplikacích (Android 4.0+)“, koncovým uživatelům se zařízeními s Androidem 4.0 nebo novějším se zobrazí zpráva Vyhledat v zařízení bezpečnostní hrozby. Uživatelé budou muset přejít do části **Nastavení** > **Google** > **Zabezpečení** a zapnout nastavení **Vyhledat v zařízení bezpečnostní hrozby**. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat další [informace](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o zprávě a důvodu, proč se po nich vyžaduje zapnutí příslušného nastavení.

- Když správci IT použijí nové zásady „Požadovat, aby bylo zakázané ladění USB (Android 4.2+)“, koncovým uživatelům se zařízeními s Androidem 4.2 nebo novějším se zobrazí zpráva Musí se zakázat ladění USB. Uživatelé budou muset přejít do části **Nastavení** > **Možnosti pro vývojáře** a vypnout nastavení **Ladění USB**. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat další [informace](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) o zprávě a důvodu, proč se po nich vyžaduje vypnutí příslušného nastavení.

- Když správci IT použijí nové zásady „Minimální úroveň oprav zabezpečení Androidu (Android 6.0 +)“, koncovým uživatelům se zařízeními s Androidem 6.0 nebo novějším se zobrazí zpráva Toto zařízení nesplňuje minimální úroveň oprav zabezpečení Androidu. Uživatelé budou muset nainstalovat požadovanou opravu zabezpečení. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat [informace](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o postupu při instalaci požadované opravy zabezpečení a zjistit, které opravy zabezpečení mají aktuálně nainstalovány.

__Aplikace Portál společnosti pro iOS__

- Když budou koncoví uživatelé instalovat podnikové aplikace, bude se jim nyní zobrazovat vylepšené prostředí instalace aplikace. Pokud instalace aplikace trvá příliš dlouho, uživatelé si můžou zařízení synchronizovat ručně, aby se vynutilo pokračování procesu synchronizace. Pokud si chcete projít pokyny pro koncové uživatele, najdete je v tématu [Ruční synchronizace zařízení s iOSem](/Intune/EndUser/sync-your-device-manually-ios).

- Aplikace Portál společnosti Microsoft Intune pro iOS je aktualizovaná tak, aby podporovala iOS verze 8.0 a novější. Aktualizace znamená, že můžou koncoví uživatelé nainstalovat aplikaci Portál společnosti a zaregistrovat nová zařízení v Intune, jenom když se na zařízení používá iOS verze 8.0 nebo novější. Uživatelé, kteří už mají zaregistrovaná zařízení používaná v nepodporované verzi iOS, můžou nadále používat aplikaci Portál společnosti nainstalovanou na svých zařízeních.


<!--HONumber=Dec16_HO1-->


