---
title: "Předchozí verze | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1360a23647d6e66ba682548ad2b158bb9047265d
ms.openlocfilehash: ec1b118b2c7681f351d83f469b8c32e95f8fa71f


---

# Předchozí verze Intune

## Září 2016
### Nové funkce, oznámení a informace
* [Podmíněný přístup pro Windows](#windows-conditional-access)
* [Podpora pro iOS 10](#ios-10-support)
* [Nástroj App Wrapping podporuje MAM bez registrace zařízení pro Android a iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Přechod od skupin Intune ke skupinám Azure Active Directory od září](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Integrace aplikace Lookout pro ochranu zařízení s Androidem](#lookout-integration-to-protect-android-devices)
* [Aktualizace aplikace Portál společnosti pro Android, iOS a Windows](#company-portal-updates)
* [Glosář služby Intune](#intune-glossary)
* [Co připravujeme](#whats-coming)

### Podmíněný přístup pro Windows
Nově můžete přes konzolu správce Intune vytvářet zásady podmíněného přístupu, které budou počítačům s Windows blokovat přístup ke službám Exchange Online a SharePoint Online. Taky můžete vytvářet zásady podmíněného přístupu, které budou blokovat přístup k desktopovým a univerzálním aplikacím Office.

### Podpora pro iOS 10
Stávající scénáře Intune MDM a MAM jsou kompatibilní se systémem iOS 10. Tipy naleznete na [blogu týmu podpory služby Intune](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

### Nástroj App Wrapping podporuje MAM bez registrace zařízení pro Android a iOS
Nástroj Intune App Wrapping je nástroj příkazového řádku, který slouží k aktivaci Intune MAM v obchodních aplikacích (LOB) pro iOS a Android. Jedná se o nejjednodušší způsob, jak začlenit sadu Intune MAM SDK do vaší aplikace, aby vaše aplikace vynucoval zásady MAM nasazené prostřednictvím služby Intune. Zásady MAM vám umožňují:

1. Zašifrovat data aplikace.
2. Požadovat, aby informační pracovník při spuštění aplikace zadal PIN.
3. Povolit aplikaci přenášet data pouze do ostatních spravovaných aplikací.
4. Zabránit aplikaci zálohovat data do Androidu, iTunes a iCloudu.
5. Povolit vyjmutí, kopírování a vložení z a do pouze ostatních spravovaných aplikací.

Veřejná verze Preview aktualizovaného nástroje Intune App Wrapping nyní podporuje MAM bez registrace zařízení na interních obchodních aplikacích v systémech iOS a Android. To znamená, že koncoví uživatelé mohou používat obchodní aplikace s podporou MAM, aniž by museli svá zařízení registrovat ve službě Intune.

Tuto veřejnou verzi Preview si může kdokoli vyzkoušet a přečíst si užitečnou dokumentaci na GitHubu ve složce msintuneappsdk:

http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Před instalací předběžné verze nástroje Microsoft Intune App Wrapper pro Android a iOS si musíte:

* Znovu projít licenční podmínky společnosti Microsoft pro předběžnou verzi nástroje Microsoft Intune App Wrapping pro Android a iOS
* Vytisknout a uchovat pro své záznamy kopii licenčních podmínek. Stažením a používáním předběžné verze nástroje Microsoft Intune App Wrapping pro Android s těmito licenčními podmínkami souhlasíte. Pokud je nepřijímáte, software nepoužívejte.
<!---TFS 1235607--->

### Přechod od skupin Intune ke skupinám Azure Active Directory od září
Některé nové účty Intune budou namísto skupin uživatelů Intune používat skupiny zabezpečení služby Azure Active Directory. Budete vědět, že pracujete se skupinami zabezpečení, jelikož stránka se skupinami na portálu Intune bude obsahovat odkaz na portál pro správu Azure.

### Integrace aplikace Lookout pro ochranu zařízení s Androidem
Společnost Microsoft integruje řešení ochrany před mobilními hrozbami v aplikaci Lookout za účelem ochrany mobilních zařízení s Androidem pomocí zjišťování malwaru, riskantních aplikací a dalších problémů na zařízení. Řešení Lookout vám pomůže určit úroveň ohrožení, která je konfigurovatelná. Ve službě Intune můžete vytvořit pravidlo zásad dodržování předpisů na základě vyhodnocování rizik aplikací Lookout. Pomocí zásad podmíněného přístupu můžete povolit nebo blokovat přístup k prostředkům společnosti na základě stavu dodržování předpisů pro zařízení.

Koncoví uživatelé zařízení nesplňujících požadavky budou vyzvání k registraci. Dále si budou muset před získáním přístupu nainstalovat na zařízení s Androidem aplikaci Lookout for Work, aktivovat ji a opravit hrozby nahlášené aplikací Lookout for Work. Další informace najdete v článku [Omezení přístupu na základě rizika zařízení, sítě a aplikace](restrict-access-based-on-device-network-app-risk.md).


### Aktualizace aplikace Portál společnosti

### Android
**Přidání oznámení do aplikace Portál společnosti pro Android**<br/>
Na domovskou stránku aplikace Portál společnosti pro Android byla přidaná nová ikona oznámení. Klepnutí na tuto ikonu otevře stránku Oznámení, kde se koncovým uživatelům zobrazí všechny položky, které v aplikaci Portál společnosti vyžadují pozornost (například že nějaké zařízení nedodržuje předpisy, zpráva o aktualizaci registrací nebo aktivaci registrací). Aplikace Portál společnosti pro iOS už tato oznámení má. Po zavedení stránky Oznámení se už při každém spuštění nebo obnovení aplikace Portál společnosti pro Android nezobrazí stránka Nastavení firemního přístupu, pokud je zařízení už zaregistrované. Pokud vytvoříte vlastní návod pro koncové uživatele, nezapomeňte tuto změnu do dokumentace promítnout. Aktualizované snímky obrazovky najdete [tady](https://aka.ms/androidcpupdate).  
<!---TFS 1095560--->

**Poskytování zpětné vazby v aplikaci Portál společnosti pro Android**</br>
Do nabídky aplikace Portál společnosti pro Android byla přidána nová položka. Klepnutím na **Nápověda a vaše názory** zobrazíte tři akce:
* Akci **Pomoc** použijte, když chcete vašemu IT oddělení nahlásit problémy s aplikací Portál společnosti. Tato akce vytvoří e-mail pomocí e-mailového klienta a připojí k němu jako přílohu protokol aplikace Portál společnosti. **Pomoc** nahrazuje funkci **Odeslat data** na stránce **Nastavení**.
* Akci **Poskytnout zpětnou vazbu** použijte, když chcete dát zpětnou vazbu týmu služby Portál společnosti.
* Akci **Ohodnotit tuto aplikaci** použijte, když chcete aplikaci Portál společnosti přidat hodnocení nebo recenzi na Google Play.

### iOS
**Změny v podpoře pro aplikaci Portál společnosti pro iOS**<br/>
Od všech uživatelů aplikace Portál společnosti pro iOS se nyní vyžaduje, aby používali její nejnovější verzi. Noví uživatelé si mohou stáhnout jenom nejnovější verzi a aktuální uživatelé si musí aplikaci aktualizovat. Nejnovější verze vyžaduje iOS 8.0 nebo novější, takže zařízení se starší verzí iOS nemohou Portál společnosti používat ani nebudou moct zařízení zaregistrovat, dokud si v něm neaktualizují operační systém na iOS 8.0 nebo novější a následně neaktualizují i aplikaci Portál společnosti na nejnovější verzi. Zaregistrovaná zařízení se systémem iOS starším 8.0 se budou spravovat i nadále a budou se zobrazovat v konzole správce Intune.
<!---TFS 1283165--->

**Vylepšení toho, jak koncoví uživatelé iOS získají svoje aplikace**<br/>
Pro dlaždice aplikací v aplikaci Portál společnosti pro iOS byly provedeny následující změny tak, aby uživatele u všech aplikací odkazovaly na různá zobrazení v jednom umístění – na webu Portál společnosti. Omezení společnosti Apple zakazují, aby se obchodní a spravované aplikace z App Storu zobrazovaly v aplikaci Portál společnosti. Uživatel tak k vyhledání všech svých aplikací musí použít několik zobrazení.

- Dlaždice **Firemní aplikace** dříve odkazovala na seznam všech aplikací na kartě VŠE na webu Portál společnosti a bude tak fungovat i dál. Název dlaždice byl změněn na **Všechny aplikace**.
- Dlaždice **Ostatní aplikace** dříve odkazovala na zobrazení v aplikaci Portál společnosti, ve kterém je uvedený seznam všech aplikací, které Apple aplikaci Portál společnosti povoluje zobrazit. Název dlaždice byl změněn na **Doporučené aplikace**. Po klepnutí na tuto dlaždici uživatelé přejdou na kartu DOPORUČENÉ na webu Portál společnosti.
-  Dlaždice **Kategorie** dříve odkazovala na zobrazení v aplikaci Portál společnosti, ve kterém je uvedený seznam kategorií aplikací. Název této dlaždice nebyl změněn, ale nyní odkazuje na kartu KATEGORIE na webu Portál společnosti.
Aktualizované snímky obrazovky najdete [tady](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

**Výzva k instalaci aplikace Spravovaný prohlížeč pro iOS, pokud IT specialista tento požadavek pro aplikaci nastavil**<br/>
Pokud jste nakonfigurovali webový klip tak, aby se otevíral jenom ve spravovaném prohlížeči, a spravovaný prohlížeč není v zařízení nainstalovaný, aplikace Portál společnosti vyzve uživatele, aby nejdřív nainstaloval spravovaný prohlížeč. Teprve potom bude možné nainstalovat příslušný webový klip.
<!---TFS 1228570--->

### Windows
**Přidání tlačítka pro odeslání zpětné vazby do aplikace Portál společnosti pro Windows Phone 8.1**<br/>
Portál společnosti pro Windows Phone 8.1 koncovým uživatelům umožňuje odeslat zpětnou vazbu o aplikaci. Slouží k tomu tlačítko „Odeslat názor“. Tlačítko najdete tak, že klepnete na třítečkovou nabídku v dolní pravé části obrazovky aplikace Portál společnosti a potom na **Odeslat názor**. Shromážděná anonymizovaná zpětná vazba pomůže Microsoftu zlepšit prostředí aplikace Portál společnosti.
<!---TFS 1317806--->

### Glosář služby Intune</br>
Do knihovny jsme přidali nové téma [Glosář](https://docs.microsoft.com/intune/understand-explore/intune-glossary), abychom vám pomohli správně chápat některé termíny používané ve službě Intune.


## Srpen 2016
### Správa aplikací
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

__Skryté a zobrazené aplikace pro iOS 9.3__ – U kontrolovaných zařízení se systémem iOS 9.3 nebo novějším můžete využít seznam skrytých a zobrazených aplikací v obecných zásadách konfigurace iOS k těmto akcím:
- Určení seznamu aplikací, které budou uživatelům skryté. Uživatelé nebudou moci tyto aplikace zobrazit ani spustit.
- Určení seznamu aplikací, které uživatelé mohou zobrazit a spustit. Žádné jiné aplikace nebude možné zobrazit ani spustit.

Mezi aplikace, které můžete zadat, patří aplikace, které jste nasadili, a integrované aplikace pro iOS, jako jsou Zprávy a Poznámky. Podrobnosti najdete v tématu [Nastavení zásad pro iOS v Microsoft Intune]( /intune/deploy-use/ios-policy-settings-in-microsoft-intune).
<!---TFS 1279009 checked--->
__Zásady povolených a blokovaných aplikací pro zařízení se systémem Samsung KNOX__ – Teď můžete pro zařízení se systémem Samsung KNOX nakonfigurovat vlastní zásady, které umožňují vytvořit:
- Seznam aplikací, u kterých je v příslušném zařízení blokované spuštění. Aplikace, které jsou definované v seznamu blokovaných aplikací, nejde na zařízení aktivovat, ani když jsou nainstalované.
- Seznam aplikací, které si uživatelé příslušného zařízení mohou nainstalovat z obchodu Google Play. Z tohoto obchodu nejde nainstalovat žádné další aplikace.

Tato nastavení mohou využívat jenom zařízení se systémem Samsung KNOX.
Podrobnosti viz [Použití vlastních zásad povolených a blokovaných aplikací pro zařízení se systémem Samsung KNOX](/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps).
<!---TFS 1311629 checked --->
__Nové aplikace kompatibilní se zásadami správy mobilních aplikací (MAM)__ – Aplikace Yammer pro [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) a [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) je teď kompatibilní se [zásadami správy mobilních aplikací (MAM) služby Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) bez ohledu na to, jestli zařízení je nebo není zaregistrované.

Kompletní seznam aplikací kompatibilních s MAM najdete na webu [aplikací pro Microsoft Intune od partnerů](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336 checked--->

<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

__Aplikace Intune Viewer__ – S vydáním nové verze aplikace RMS pro sdílení jsme od srpna 2016 odebrali následující aplikace Intune Viewer:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer pro Android z Google Play

Místo použití aplikací Intune Viewer vám doporučujeme používat novou aplikaci [Rights Management (sdílení RMS) pro Android](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), která pro bezpečné prohlížení firemních souborů na zařízeních s Androidem umožňuje nasadit jednu aplikaci (namísto tří samostatných aplikací). Až se aplikace Intune Viewer už nebude podporovat, bude odebrána z Google Storu a nebude už dostupná pro budoucí použití.

### Správa zařízení
__Podpora pro Android 7.0__ – Pro připravovaný operační systém Android 7.0, který je určený pro mobilní zařízení, nabízí Intune podporu „dne 0“.
<!---TFS 1262053--->

__Odebrání funkce pro vzdálené resetování hesla v zařízeních se systémem Android 7.0__ – U zařízení se systémem Android 7.0 společnost Google odebrala správcům IT a koncovým uživatelům možnost vzdáleně resetovat heslo. V předchozích verzích mohli správci vzdáleně resetovat heslo uživatele e koncoví uživatelé mohli k resetování svých hesel využívat web Portál společnosti.

### Aktualizace Portálu společnosti
__Web portálu společnosti__
- **Odkaz pro zasílání názorů společnosti Microsoft na webu Portál společnosti** <br/>
Portál společnosti umožňuje koncovým uživatelům klepnout na nový odkaz Zpětná vazba v dolní části stránky a poslat společnosti Microsoft názory na tuto stránku a zkušenosti s ní. Shromážděná anonymizovaná zpětná vazba pomůže Microsoftu zlepšit prostředí webu Portál společnosti.
<!--- TFS 1313657 checked--->

__iOS__
- **Minimální verze iOS pro Managed Browser byla aktualizovaná na 8.0**<br/>
Aplikaci Microsoft Intune Managed Browser pro iOS byla aktualizována a podporuje zařízení se systémem iOS 8.0 nebo novějším. Přestože v zařízeních s iOS 7.1 můžou využívat stávající aplikaci Managed Browser, doporučte prosím svým uživatelům, aby aktualizovali na iOS 8.0 nebo novější a mohli plně využít výhody nových funkcí Managed Browseru.  
<!---TFS 1313253 checked--->

### Co připravujeme

__Podpora pro iOS 10__ – Intune bude plně podporovat iOS 10. Další informace zveřejníme po vydání iOS 10.

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

__Vylepšení způsobu, jakým koncoví uživatelé iOS získávají své aplikace__ – V září proběhnou následující změny, které se týkají dlaždic aplikací v aplikaci Portál společnosti pro iOS. Díky těmto změnám budou uživatelé u všech svých aplikací přesměrováni na různá zobrazení v jednom umístění, kterým je web Portál společnosti. Apple v současnosti zakazuje, aby se obchodní a spravované aplikace z App Storu zobrazovaly v aplikaci Portál společnosti. Uživatel tak k vyhledání všech svých aplikací musí použít několik zobrazení.

- Dlaždice **Firemní aplikace** v současnosti odkazuje na seznam všech aplikací na kartě VŠE na webu Portál společnosti a bude tak fungovat i dál. Název této dlaždice se změní na **Všechny aplikace**.
- Dlaždice **Ostatní aplikace** v současnosti odkazuje v aplikaci Portál společnosti na zobrazení, ve kterém je uvedený seznam všech aplikací, které Apple aplikaci Portál společnosti povoluje zobrazit. Název dlaždice se změní na **Doporučené aplikace**. Po klepnutí na tuto dlaždici uživatelé přejdou na kartu DOPORUČENÉ na webu Portál společnosti.
-  Dlaždice **Kategorie** v současnosti odkazuje v aplikaci Portál společnosti na zobrazení, ve kterém je uvedený seznam kategorií aplikací. Název této dlaždice se nezmění, ale bude teď na webu Portál společnosti odkazovat na kartu KATEGORIE. Aktualizované snímky obrazovky najdete [tady](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

### Průvodce cloudem
Udržujte si přehled o budoucích novinkách pro Intune díky [průvodci cloudovou platformou](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Zastaralá služba
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Změny v podpoře pro aplikaci Portál společnosti pro iOS**<br/>
Od září se začne vyžadovat, aby všichni uživatelé aplikace Portál společnosti Microsoft Intune pro iOS používali její nejnovější verzi. Noví uživatelé si budou moct stáhnout jenom nejnovější verzi a aktuální uživatelé si budou muset aplikaci aktualizovat. Nejnovější verze vyžaduje iOS 8.0 nebo novější, takže zařízení se starší verzí iOS nebudou moct Portál společnosti používat ani nebudou moct zařízení zaregistrovat, dokud si v něm neaktualizují operační systém na iOS 8.0 nebo novější a následně neaktualizují i aplikaci Portál společnosti na nejnovější verzi. Zaregistrovaná zařízení se systémem iOS starším 8.0 se budou spravovat i nadále a budou se zobrazovat v konzole správce Intune.  

- **Minimální verze iOS pro Managed Browser byla aktualizovaná na 8.0**<br/>
V srpnu Intune vydá aktualizovanou aplikaci Microsoft Intune Managed Browser pro iOS, která bude podporovat jenom zařízení se systémem iOS 8.0 nebo novějším. Přestože v zařízeních s iOS 7.1 bude i dál možné využívat stávající aplikaci Managed Browser, doporučte prosím svým uživatelům, aby aktualizovali na iOS 8.0 nebo novější a mohli plně využít výhody nových funkcí Managed Browseru.  
<!---TFS 1313253--->

- **Aplikace Portál společnosti pro Windows 8 a Windows Phone 8 se přestanou používat** <br/>
Od října 2016 přestane Microsoft Intune poskytovat podporu aplikacím Portál společnosti pro Windows 8 a Windows Phone 8. Microsoft Intune také přestat poskytovat podporu pro platformu Windows Phone 8. V důsledku toho nebude možné registrovat ani aktualizovat žádná zařízení Windows Phone 8. Zařízení Windows Phone 8 a Windows 8, která jsou již zaregistrována, můžete nadále spravovat. Pokud budete chtít do zařízení s těmito systémy dál bez přerušení distribuovat aplikace, aktualizujte si zařízení Windows 8 a Windows Phone 8 na Windows 8.1 a Windows Phone 8.1 a začněte používat odpovídající aplikaci Portál společnosti pro Windows 8.1 a Windows Phone 8.1.
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

## Červenec 2016
### Správa aplikací

__Vylepšení prostředí aktualizace zřizovacího profilu aplikace__ – Mobilní obchodní aplikace pro Apple iOS jsou vytvořeny tak, že obsahují zřizovací profil a kód podepsaný certifikátem. Když se taková aplikace spustí na zařízení s iOS, iOS potvrdí její integritu a vynutí zásady jejím definované zřizovacím profilem.

Podpisový certifikát společnosti, který se používá k podepisování aplikací, má obvykle platnost 3 roky. Platnost zřizovacího profilu ale vyprší už po jednom roce. Prostřednictvím této aktualizace Intune poskytuje nástroje pro proaktivní nasazení nových zásad zřizovacích profilů do zařízení, ve kterých se aplikace blíží vypršení data platnosti, ale certifikát je stále platný. Další informace najdete v tématu věnovaném [použití mobilních zásad zřizovacích profilů pro iOS k zajištění aktuálnosti obchodních aplikací](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

__Je dostupná sada Xamarin SDK pro aplikace Intune__ – Komponenta Intune App SDK Xamarin umožňuje v mobilních aplikacích pro iOS a Android vytvořených pomocí Xamarinu povolit funkce správy mobilních aplikací Intune. Tuto komponentu najdete v [Xamarin Storu](https://components.xamarin.com/view/Microsoft.Intune.MAM) nebo na [stránce Microsoft Intune Githubu](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### Správa zařízení
__Zvýšené limity pro registraci zařízení__ – Služba Intune zvýšila maximální limit pro registraci zařízení z 5 na 15 zařízení na každého uživatele.
<!---TFS 1289896 --->

__Integrace TeamVieweru pro počítače s Windows a klientským softwarem Intune__
 – Integrovaný [TeamViewer](https://www.teamviewer.com) v počítačích s Windows a klientským softwarem Intune umožňuje v rámci podpory navazovat relace vzdálené pomoci s počítači se systémem Windows. Tuto podporu poskytují oddělení helpdesku koncovým uživatelům. To zahrnuje systém Windows 7, 8, 8.1 a Windows 10. Podrobnosti najdete v tématu [Běžné úlohy správy počítačů s Windows pomocí počítačového klienta Microsoft Intune](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### Aktualizace Portálu společnosti

__Web portálu společnosti__
- **Vylepšené prostředí při registraci zařízení s Windows**<br/>
Na webu Portál společnosti byly upřesněny kroky registrace pro Windows 8.1, Windows 10 Desktop a Windows 10 Mobile při použití podmíněného přístupu. Uživatelům se nyní zobrazí samostatné kroky Registrace zařízení a Workplace Join. Snáz tak zjistí stav svého zařízení a dokončí celý proces v případě, že dojde k chybě Workplace Join (WPJ). Očekává se, že tyto samostatné kroky také zjednoduší proces řešení potíží pro správce IT. Když se dříve uživatelé pokusili zaregistrovat a všechny kroky registrace se provedly úspěšně s výjimkou WPJ, zaregistrované zařízení se nezobrazilo v seznamu zařízení a uživatele to mátlo.

__Android__
- **Aplikace Portál společnosti pro Android**<br/>
Když se koncovému uživateli Androidu zobrazí zpráva, která uvádí, že v zařízení chybí certifikát, může kliknutím na tlačítko Jak to vyřešit zobrazit [kroky](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) pro instalaci chybějícího certifikátu. Pokud uživatel dokončí tyto kroky, ale zobrazí se mu další chybová zpráva typu chybějící certifikát, měl by kontaktovat správce IT a poskytnout mu tento [odkaz](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), který obsahuje kroky, jejichž prostřednictvím správce může potíže s certifikátem vyřešit.

- **Omezení instalací zkušebně načtených aplikací jenom na registrovaná zařízení**<br/>
Zařízení s Androidem už nemohou instalovat aplikace prostřednictvím webu Portál společnosti, pokud nejsou v Intune zaregistrovaná pomocí aplikace Portál společnosti Intune pro Android.
<!---TFS 1299082--->

__iOS__
- **Změny účtů Správců registrace zařízení v aplikaci Portál společnosti pro iOS**<br/>
Za účelem zvýšení výkonu a možností škálování už Intune v aplikaci Portál společnosti pro iOS v podokně **Moje zařízení** nezobrazuje všechna zařízení Správce registrace zařízení. Zobrazí se pouze místní zařízení, na kterém aplikace běží, a to pouze v případě, že je zaregistrováno prostřednictvím aplikace Portál společnosti.

Uživatel Správce registrace zařízení může na místním zařízení provádět různé akce, ale vzdálenou správu jiných zaregistrovaných zařízení je možné provádět pouze z konzoly správce Intune. Kromě toho se v Intune místo účtů DEM začne používat buď program Apple DEP (Device Enrollment Program), nebo nástroj Apple Configurator. Obě tyto metody registrace již podporují registrace bez zásahu uživatele pro sdílená zařízení s iOS.

Účty Správce registrace zařízení používejte pouze v případě, že registrace sdílených zařízení bez zásahu uživatele není dostupná. Další informace najdete v části [Registrace firemních zařízení pomocí správce registrace zařízení v Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### Změna názvů pro funkce Windows
- [Microsoft Passport pro Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) se nyní označuje jako **Windows Hello pro firmy**.
- [Ochrana podnikových dat](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) se nyní označuje jako **Windows Information Protection**.

## Červen 2016
### Stav služby Intune
Informace o stavu služby pro Intune se přesouvají do centrálního umístění společně s ostatními službami Microsoftu. Tyto informace nyní najdete na portálu pro správu Office 365 v části věnované stavu služby. Další informace najdete v [tomto příspěvku blogu](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### Správa aplikací
- **Vylepšení prostředí pro konfiguraci datových zásad systému Windows 10 Enterprise.** Vylepšili jsme možnosti konfigurace zásad ochrany podnikových dat systému Windows 10 souvisejících s vytvářením pravidel aplikací, určováním definice mezí sítě a dalších nastavení pro ochranu podnikových dat. Další informace najdete v tématu [Vytvoření zásady ochrany podnikových dat pomocí Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


### Správa zařízení
- **Nastavení zásad programu Windows Defender pro ochranu proti potenciálně nežádoucím aplikacím.** Do obecné konfigurace zásady pro Windows 10 Desktop a Mobile bylo přidáno nové nastavení programu Windows Defender nazvané **Detekce potenciálně nežádoucích aplikací**. Pomocí tohoto nastavení můžete ochránit zaregistrované stolní počítače s Windows před spuštěním softwaru, který Windows Defender klasifikuje jako potenciálně nežádoucí. Můžete nastavit ochranu před spuštěním těchto aplikací nebo pomocí režimu auditu upozornit, když se potenciálně nežádoucí aplikace nainstaluje. Další informace najdete v tématu [Nastavení zásad pro Windows 10 v Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

### Podmíněný přístup
- **Zásady řízení přístupu k síti Cisco ISE pro Intune.**  Zákazníci, kteří používají Cisco Identity Service Engine (ISE) 2.1 a také Microsoft Intune, mohou v modulu ISE nastavit zásady řízení přístupu k síti.

    Když se použijí tyto zásady, zařízení, která se připojují k síti pomocí WiFi nebo VPN, musí splňovat následující podmínky, jinak jim nebude povolen přístup:

    * Musí být spravovaná pomocí Intune.
    * Musí splňovat veškeré nasazené zásady dodržování předpisů Intune.

 Koncovým uživatelům nevyhovujících zařízení se zobrazí výzva k registraci. Pokud chtějí získat přístup, musí všechny problémy s dodržováním předpisů vyřešit.
- **Podmíněný přístup pro prohlížeč.** Můžete nastavit zásady podmíněného přístupu pro [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) a [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune), na základě kterých k nim bude možné získat přístup pouze z podporovaných webových prohlížečů ve spravovaných a vyhovujících zařízeních. Koncoví uživatelé, kteří se pokusí přihlásit k aplikaci Outlook Web Access (OWA) a webům služby SharePoint pomocí zařízení s iOS a Androidem, budou vyzváni, aby před přihlášením svoje zařízení zaregistrovali v Intune a opravili všechny problémy, kvůli kterým zařízení nesplňuje pravidla zásad dodržování předpisů.
<!---TFS 1175844--->

- **Dynamics CRM Online podporuje podmíněný přístup.** Můžete pro [Dynamics CRM Online](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune) nastavit zásady podmíněného přístupu, aby k němu měla přístup pouze spravovaná a vyhovující zařízení s iOS a s Androidem. Koncovým uživatelům, kteří se pokusí přihlásit k mobilní aplikaci Dynamics CRM na iOS a Androidu, se zobrazí výzva, aby si před přihlášením zařízení zaregistrovali v Intune a aby vyřešili všechny problémy, kvůli kterým zařízení není v souladu s pravidly zásad dodržování předpisů v organizaci.
<!---TFS1295358--->

### Aktualizace Portálu společnosti Intune

__Aplikace Portál společnosti pro Android__

- Když správci IT použijí nové zásady „Požadovat, aby zařízení nepovolovala instalaci aplikací z neznámých zdrojů (Android 4.0 +)“, koncovým uživatelům se zařízeními s Androidem 4.0 nebo novějším zařízení se zobrazí zpráva Musí se zakázat instalace z neznámých zdrojů. Uživatelé budou muset přejít do části **Nastavení** > **Zabezpečení** a vypnout nastavení **Neznámé zdroje**. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat další [informace](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) o zprávě a důvodu, proč se po nich vyžaduje vypnutí příslušného nastavení.

- Když správci IT použijí nové zásady „Požadovat, aby zařízení měla povoleno vyhledávání bezpečnostních hrozeb v aplikacích (Android 4.0+)“, koncovým uživatelům se zařízeními s Androidem 4.0 nebo novějším se zobrazí zpráva Vyhledat v zařízení bezpečnostní hrozby. Uživatelé budou muset přejít do části **Nastavení** > **Google** > **Zabezpečení** a zapnout nastavení **Vyhledat v zařízení bezpečnostní hrozby**. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat další [informace](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o zprávě a důvodu, proč se po nich vyžaduje zapnutí příslušného nastavení.

- Když správci IT použijí nové zásady „Požadovat, aby bylo zakázané ladění USB (Android 4.2+)“, koncovým uživatelům se zařízeními s Androidem 4.2 nebo novějším se zobrazí zpráva Musí se zakázat ladění USB. Uživatelé budou muset přejít do části **Nastavení** > **Možnosti pro vývojáře** a vypnout nastavení **Ladění USB**. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat další [informace](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) o zprávě a důvodu, proč se po nich vyžaduje vypnutí příslušného nastavení.

- Když správci IT použijí nové zásady „Minimální úroveň oprav zabezpečení Androidu (Android 6.0 +)“, koncovým uživatelům se zařízeními s Androidem 6.0 nebo novějším se zobrazí zpráva Toto zařízení nesplňuje minimální úroveň oprav zabezpečení Androidu. Uživatelé budou muset nainstalovat požadovanou opravu zabezpečení. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat [informace](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o postupu při instalaci požadované opravy zabezpečení a zjistit, které opravy zabezpečení mají aktuálně nainstalovány.

__Aplikace Portál společnosti pro iOS__

- Když budou koncoví uživatelé instalovat podnikové aplikace, bude se jim nyní zobrazovat vylepšené prostředí instalace aplikace. Pokud instalace aplikace trvá příliš dlouho, uživatelé si můžou zařízení synchronizovat ručně, aby se vynutilo pokračování procesu synchronizace. Pokud si chcete projít pokyny pro koncové uživatele, najdete je v tématu [Ruční synchronizace zařízení s iOS](/Intune/EndUser/sync-your-device-manually-ios).

- Aplikace Portál společnosti Microsoft Intune pro iOS je aktualizovaná tak, aby podporovala iOS verze 8.0 a novější. Aktualizace znamená, že můžou koncoví uživatelé nainstalovat aplikaci Portál společnosti a zaregistrovat nová zařízení v Intune, jenom když se na zařízení používá iOS verze 8.0 nebo novější. Uživatelé, kteří už mají zaregistrovaná zařízení používaná v nepodporované verzi iOS, můžou nadále používat aplikaci Firemní portál nainstalovanou na jejich zařízeních.


## Květen 2016
Všechny tyto funkce jsou také podporovány pro hybridní nasazení (nástroj Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší stránce věnované [novinkám pro hybridní nasazení](https://technet.microsoft.com/en-us/library/mt718155.aspx).

### Dokumentace
Vítejte ve verzi Preview pro [docs.microsoft.com](https://docs.microsoft.com/en-us/intune).
Toto je zcela nová platforma s moderním obsahem, navržená tak, aby bylo snazší pro vás, naše zákazníky, pochopit a používat službu Intune.
Informace o všech nových funkcích najdete v tématu [Představení docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/).

### Stav služby Intune
Informace o stavu služby pro Intune se přesouvají do centrálního umístění společně s ostatními službami Microsoftu. Tyto informace nyní najdete na [portálu pro správu Office 365](https://portal.office.com/Admin/Default.aspx) v části věnované **stavu služby**.
Další informace najdete v [tomto příspěvku blogu](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).


### Správa aplikací
- **MAM SDK: Podpora konfigurace délky PIN kódu.** Bude možné zadat délku PIN kódu pro aplikace MAM podobně, jako je tomu u PIN kódu zařízení. Bude tak nutné, aby koncoví uživatelé dodrželi nová omezení, která nastavíte. Zobrazí se jim mírně upravená obrazovka pro zadání PIN kódu, ve které je teď delší pole pro jeho zadání. Podrobnosti najdete v tématu [Nastavení zásad MAM pro Android](/intune/deploy-use/android-mam-policy-settings) a [Nastavení zásad MAM pro iOS](/intune/deploy-use/ios-mam-policy-settings).

- **Skype pro firmy pro iOS a Android.** Nyní můžete cílit na Skype pro firmy se [správou mobilních aplikací (MAM) bez zásad registrace](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Jakmile se uživatelé přihlásí, aplikují se zásady MAM.

- **Pro správu pomocí zásad MAM jsou teď dostupné nové aplikace.** Na zařízeních, která nejsou zaregistrovaná v Intune, je teď možné přidružit k zásadám MAM aplikace Microsoft Word, Excel a PowerPoint pro Android. Úplný seznam podporovaných aplikací najdete v galerii mobilních aplikací Microsoft Intune na stránce [aplikací pro Microsoft Intune od partnerů](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


### Aktualizace Portálu společnosti

#### Aplikace Portál společnosti pro Android
- **Informační zprávy pro koncové uživatele:** Koncoví uživatelé nyní uvidí informační zprávy aplikace Portál společnosti pro Android, když registrují svoje zařízení nebo je odebírají z Portálu společnosti.

- **Změny účtů správců registrace zařízení v aplikaci Portál společnosti pro Android.** Za účelem zvýšení výkonu a možností škálování už Intune v aplikaci Portál společnosti pro Android v podokně Moje zařízení nezobrazuje všechna zařízení správce registrace zařízení (DEM). Zobrazí se pouze místní zařízení, na kterém aplikace běží, a to pouze v případě, že je zaregistrováno prostřednictvím aplikace Portál společnosti. Uživatel Správce registrace zařízení může na místním zařízení provádět různé akce, ale vzdálenou správu jiných zaregistrovaných zařízení je možné provádět pouze z konzoly správce Intune.

#### Web portálu společnosti
- **Web Portál společnosti: Informační zpráva s identifikací zařízení bude koncovým uživatelům poskytovat další informace.** Koncoví uživatelé mohou nyní snadněji identifikovat zařízení, které vybrali při používání webu Portál společnosti. Pokud je vybrané nesprávné zařízení, budou moct vybrat správné zařízení klepnutím na odkaz **Klepněte sem** v informační zprávě domovské stránky.

### Zastaralá služba
- **Aplikace Intune Viewer.** V souvislosti s vydáním nové aplikace Sdílení RMS odebíráme od srpna 2016 následující aplikace Intune Viewer:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer pro Android z Google Play

  Místo použití aplikací Intune Viewer vám doporučujeme používat novou aplikaci Rights Management (sdílení RMS) pro Android, která pro bezpečné prohlížení firemních souborů na zařízeních s Androidem umožňuje nasadit jednu aplikaci (namísto tří samostatných aplikací). Přečtěte si víc o aplikaci Sdílení RMS (s odkazem na dokumentaci).

- **Odebrání možnosti cílení pravidel oznámení na vlastní skupiny.**
Pravidla oznámení Intune definují, komu se budou z Intune odesílat e-mailové výstrahy. V současnosti můžete nakonfigurovat pravidla oznámení pro odesílání e-mailů všem uživatelům zařízení nebo skupině zařízení služby Intune, kterou jste vytvořili. Přibližně od 1. června 2016 se už cílení na uživatelsky vytvořené skupiny nebude podporovat.

    Pokud byste v současnosti chtěli pravidlo oznámení cílit na skupinu, kterou jste vytvořili pomocí konzoly správce Microsoft Intune, použijete tyto kroky:

    V pracovním prostoru **Správa** klikněte na **Pravidla oznámení** > **Vytvořit nové pravidlo**.

    V kroku 2 Průvodce vytvořením pravidla oznámení vyberte skupiny zařízení, na které bude pravidlo cílit. Tento krok (Vybrat skupiny zařízení) z konzoly Intune odebíráme.

    Předběžná časová osa pro tuto změnu je následující:
    - V červnu 2016 se novým tenantům v Průvodci vytvořením pravidla oznámení nezobrazí krok 2. Stávající tenanty to neovlivní.
    - Zhruba v srpnu 2016 se některým tenantům v tomto průvodci nezobrazí možnost Vybrat skupiny zařízení.
    - Přibližně od října 2016 očekáváme, že se možnost Vybrat skupiny zařízení v tomto průvodci nezobrazí žádným tenantům.


- **Změny v podpoře pro aplikaci Portál společnosti pro iOS**. V nadcházejících měsících bude dostupná aktualizace aplikace Portál společnosti Microsoft Intune pro iOS, která bude podporovat jenom zařízení se systémem iOS 8.0 nebo novějším. Uživatelé si nebudou moci zaregistrovat nová zařízení se systémem starším než iOS 8.0. Zaregistrovaná zařízení se systémem starším než iOS 8.0 se budou spravovat i nadále a po omezenou dobu budou moci pokračovat v používání aplikace Portálu společnosti. Pro přístup k nejnovější verzi aplikace Portál společnosti ale zařízení musí používat iOS 8.0 nebo novější. Doporučujeme vám, abyste upozornili uživatele, že k plnému využití nových funkcí služby Intune musí aktualizovat na iOS 8.0 nebo novější.  


## Duben 2016
Všechny tyto funkce jsou také podporovány pro zákazníky, kteří v současné době využívají hybridní řešení (nástroj Configuration Manager integrovaný s Intune).

### Správa aplikací
- **MAM – dodržování předpisů uživateli.**
Nyní můžete zobrazit [stav](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) zásad správy aplikací pro všechny uživatele ve vašem tenantovi Azure Active Directory (AAD). Patří mezi ně:
   - Zařízení
   - Aplikace na zařízení

   Stavové hodnoty:

   **Zaregistrováno:** Označuje, že byly zásady nasazeny uživateli, v pracovním kontextu byla použita aplikace a úspěšně byly přijaty zásady.

    **Není zaregistrováno:** Označuje, že byly zásady nasazeny uživateli, ale aplikace od té doby nebyla použita v pracovním kontextu.


- **Kontrolní mechanismy správy mobilních aplikací (MAM) pro zabránění synchronizace kontaktů Outlooku (Android).**
Je k dispozici nové nastavení pro [správu mobilních aplikací](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) bez registrace zařízení. Toto nastavení vám umožňuje zabránit aplikaci v synchronizaci kontaktů s nativním adresářem na zařízeních s Androidem. Pokud je toto nastavení povoleno, cílové aplikace již nebudou nadále moci ukládat kontakty do nativního adresáře. Pokud je toto nastavení zakázáno, cílové aplikace nebudou moci ukládat kontakty do nativního adresáře. Když se rozhodnete [vymazat zařízení nebo aplikaci](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune), budou odebrány všechny kontakty, které byly uloženy do nativního adresáře. Toto nové nastavení je ve výchozím nastavení podporováno v aplikaci Outlook na zařízeních s Androidem.

### Správa zařízení
- **Identifikace telefonního čísla pro zařízení vlastněná společností.** Telefony, které jsou klasifikovány jako Podnikové, jsou nyní označeny úplným telefonním číslem, když například spustíte sestavu inventáře mobilních zařízení. Telefonní čísla osobních zařízení zaměstnanců (BYOD) jsou nadále maskována hvězdičkami (****). Zobrazují se pouze poslední 4 číslice.


### Aktualizace Portálu společnosti
**Aplikace Portál společnosti pro Android** Uživatelé, kteří si nezaregistrovali svoje zařízení v Intune a kteří nemají nainstalovaný správný certifikát, se nebudou moct přihlásit k aplikaci Portál společnosti pro Android a zobrazí se jim zpráva Nemůžete se přihlásit, protože vašemu zařízení chybí požadovaný certifikát. Součástí zprávy je i odkaz Jak to vyřešit, na který můžou uživatelé klepnout a zobrazit si tak pokyny k instalaci certifikátu. Informace o tom, jaké kroky musí koncoví uživatelé při řešení tohoto problému provést, najdete v tématu [Zařízení nemá požadovaný certifikát](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**Aplikace Portál společnosti pro iOS** Byla přidána podpora pro akci aktualizace obsahu tažením na domovské obrazovce, která zahrnuje uvedené aplikace, uvedená zařízení a kontaktní údaje oddělení IT. Akce aktualizace obsahu potažením nekontroluje informace dodržování předpisů nebo zásad, což lze provést výběrem dlaždice pro aktuální zařízení a klepnutím na tlačítko **Synchronizovat**.

**Aplikace Portál společnosti pro Windows 10 Mobile a Windows Phone 8.1** Když budou koncoví uživatelé instalovat obchodní aplikace, budou se jim nyní zobrazovat vylepšené možnosti instalace aplikace. Pokud instalace aplikace trvá příliš dlouho, uživatelé si můžou zařízení synchronizovat ručně, aby se vynutilo pokračování procesu synchronizace. Pokud si chcete projít pokyny pro koncové uživatele, najdete je v tématu [Ruční synchronizace zařízení pro urychlení instalace aplikací](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Web portálu společnosti** Když budou uživatelé zařízení s Windows 10 Mobile a Windows Phone 8.1 instalovat obchodní aplikace, zobrazí se jim nyní následující nové stavy, díky kterým získají více podrobností o stavu instalace:

* **Čeká se na synchronizaci zařízení** – Uživatel klepl na Nainstalovat a zařízení se teď snaží synchronizovat s infrastrukturou služby Intune. Před instalací je nutné provést synchronizaci. Zpráva Čeká se na synchronizaci zařízení je také odkaz, na který můžou klepnout a zobrazit si tak [pokyny](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) k tomu, jak ručně synchronizovat zařízení s Intune, pokud proces synchronizace trvá dlouho nebo se zastavil.
* **Stahování** – Zpracovává se žádost uživatele o stažení a zařízení stahuje a instaluje aplikaci.

Než byly přidány tyto stavy, uživatelé ztráceli přehled o tom, co se děje, pokud instalace aplikace trvalo dlouhou dobu. Viděli totiž pouze stav Probíhá instalace, který se mohl na obrazovce zobrazovat i několik hodin. To, že se přidaly nové stavy, znamená, že uživatelé namísto volání podpory mohou nyní klepnout na odkaz Čeká se na synchronizaci zařízení a podle pokynů vynutit pokračování procesu synchronizace.

>[!div class="step-by-step"]

>[&larr; **Co je nového v Intune**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Oct16_HO3-->


