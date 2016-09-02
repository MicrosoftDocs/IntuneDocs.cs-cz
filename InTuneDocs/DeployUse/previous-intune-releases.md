---
title: "Předchozí verze | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 57570fcf2f738b68a01bb1c5fc8962c7ef117920
ms.openlocfilehash: 43546721245f92309d86c496dbcde7900a598ed0


---

# Předchozí verze Intune
## Červenec 2016
### Správa aplikací
#### Vylepšení prostředí aktualizace zřizovacího profilu aplikace
Mobilní obchodní aplikace pro Apple iOS jsou vytvořeny tak, že obsahují zřizovací profil a kód podepsaný certifikátem. Když se taková aplikace spustí na zařízení s iOS, iOS potvrdí její integritu a vynutí zásady jejím definované zřizovacím profilem.

Podpisový certifikát společnosti, který se používá k podepisování aplikací, má obvykle platnost 3 roky. Platnost zřizovacího profilu ale vyprší už po jednom roce. Prostřednictvím této aktualizace Intune poskytuje nástroje pro proaktivní nasazení nových zásad zřizovacích profilů do zařízení, ve kterých se aplikace blíží vypršení data platnosti, ale certifikát je stále platný. Další informace najdete v tématu věnovaném [použití mobilních zásad zřizovacích profilů pro iOS k zajištění aktuálnosti obchodních aplikací](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->
#### Je dostupná sada Xamarin SDK pro aplikace Intune
Komponenta Intune App SDK Xamarin umožňuje v mobilních aplikacích pro iOS a Android vytvořených pomocí Xamarinu povolit funkce správy mobilních aplikací Intune. Tuto komponentu najdete v [Xamarin Storu](https://components.xamarin.com/view/Microsoft.Intune.MAM) nebo na [stránce Microsoft Intune Githubu](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### Správa zařízení
#### Zvýšené limity pro registraci zařízení
Služba Intune zvýšila maximální limit pro registraci zařízení z 5 na 15 zařízení na uživatele.
<!---TFS 1289896 --->

#### Integrace TeamVieweru pro počítače s Windows a klientským softwarem Intune
Integrace [TeamVieweru](https://www.teamviewer.com) pro počítače s Windows a klientským softwarem Intune vám umožní navázání relací vzdálené pomoci s počítači s Windows v rámci podpory, kterou oddělení helpdesku poskytují koncovým uživatelů. To zahrnuje systém Windows 7, 8, 8.1 a Windows 10. Podrobnosti najdete v tématu [Běžné úlohy správy počítačů s Windows pomocí počítačového klienta Microsoft Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).
<!---TFS 1284856--->

### Aktualizace Portálu společnosti
#### Web portálu společnosti
- **Vylepšené prostředí při registraci zařízení s Windows**<br/>
Na webu Portál společnosti byly upřesněny kroky registrace pro Windows 8.1, Windows 10 Desktop a Windows 10 Mobile při použití podmíněného přístupu. Uživatelům se nyní zobrazí samostatné kroky Registrace zařízení a Workplace Join. Snáz tak zjistí stav svého zařízení a dokončí celý proces v případě, že dojde k chybě Workplace Join (WPJ). Očekává se, že tyto samostatné kroky také zjednoduší proces řešení potíží pro správce IT. Když se dříve uživatelé pokusili zaregistrovat a všechny kroky registrace se provedly úspěšně s výjimkou WPJ, zaregistrované zařízení se nezobrazilo v seznamu zařízení a uživatele to mátlo.

#### Android
- **Aplikace Portál společnosti pro Android**<br/>
Když se koncovému uživateli Androidu zobrazí zpráva, která uvádí, že v zařízení chybí certifikát, může kliknutím na tlačítko Jak to vyřešit zobrazit [kroky](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) pro instalaci chybějícího certifikátu. Pokud uživatel dokončí tyto kroky, ale zobrazí se mu další chybová zpráva typu chybějící certifikát, měl by kontaktovat správce IT a poskytnout mu tento [odkaz](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), který obsahuje kroky, jejichž prostřednictvím správce může potíže s certifikátem vyřešit.

- **Omezení instalací zkušebně načtených aplikací jenom na registrovaná zařízení**<br/>
Zařízení s Androidem už nemohou instalovat aplikace prostřednictvím webu Portál společnosti, pokud nejsou v Intune zaregistrovaná pomocí aplikace Portál společnosti Intune pro Android.
<!---TFS 1299082--->

#### iOS
- **Změny účtů Správců registrace zařízení v aplikaci Portál společnosti pro iOS**<br/>
Za účelem zvýšení výkonu a možností škálování už Intune v aplikaci Portál společnosti pro iOS v podokně **Moje zařízení** nezobrazuje všechna zařízení Správce registrace zařízení. Zobrazí se pouze místní zařízení, na kterém aplikace běží, a to pouze v případě, že je zaregistrováno prostřednictvím aplikace Portál společnosti.

Uživatel Správce registrace zařízení může na místním zařízení provádět různé akce, ale vzdálenou správu jiných zaregistrovaných zařízení je možné provádět pouze z konzoly správce Intune. Kromě toho se v Intune místo účtů DEM začne používat buď program Apple DEP (Device Enrollment Program), nebo nástroj Apple Configurator. Obě tyto metody registrace již podporují registrace bez zásahu uživatele pro sdílená zařízení s iOS.

Účty Správce registrace zařízení používejte pouze v případě, že registrace sdílených zařízení bez zásahu uživatele není dostupná. Další informace najdete v části [Registrace firemních zařízení pomocí správce registrace zařízení v Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### Změna názvů pro funkce Windows
- [Microsoft Passport pro Windows](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) se nyní označuje jako **Windows Hello pro firmy**.
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
- **Podmíněný přístup pro prohlížeč.** Můžete nastavit zásady podmíněného přístupu pro [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md) a [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md), na základě kterých k nim bude možné získat přístup pouze z podporovaných webových prohlížečů ve spravovaných a vyhovujících zařízeních. Koncoví uživatelé, kteří se pokusí přihlásit k aplikaci Outlook Web Access (OWA) a webům služby SharePoint pomocí zařízení s iOS a Androidem, budou vyzváni, aby před přihlášením svoje zařízení zaregistrovali v Intune a opravili všechny problémy, kvůli kterým zařízení nesplňuje pravidla zásad dodržování předpisů.
<!---TFS 1175844--->

- **Dynamics CRM Online podporuje podmíněný přístup.** Můžete pro [Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md) nastavit zásady podmíněného přístupu, aby k němu měla přístup pouze spravovaná a vyhovující zařízení s iOS a s Androidem. Koncovým uživatelům, kteří se pokusí přihlásit k mobilní aplikaci Dynamics CRM na iOS a Androidu, se zobrazí výzva, aby si před přihlášením zařízení zaregistrovali v Intune a aby vyřešili všechny problémy, kvůli kterým zařízení není v souladu s pravidly zásad dodržování předpisů v organizaci.
<!---TFS1295358--->

##Aktualizace Portálu společnosti

#### Aplikace Portál společnosti pro Android

- Když správci IT použijí nové zásady „Požadovat, aby zařízení nepovolovala instalaci aplikací z neznámých zdrojů (Android 4.0 +)“, koncovým uživatelům se zařízeními s Androidem 4.0 nebo novějším zařízení se zobrazí zpráva Musí se zakázat instalace z neznámých zdrojů. Uživatelé budou muset přejít do části **Nastavení** > **Zabezpečení** a vypnout nastavení **Neznámé zdroje**. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat další [informace](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) o zprávě a důvodu, proč se po nich vyžaduje vypnutí příslušného nastavení.

- Když správci IT použijí nové zásady „Požadovat, aby zařízení měla povoleno vyhledávání bezpečnostních hrozeb v aplikacích (Android 4.0+)“, koncovým uživatelům se zařízeními s Androidem 4.0 nebo novějším se zobrazí zpráva Vyhledat v zařízení bezpečnostní hrozby. Uživatelé budou muset přejít do části **Nastavení** > **Google** > **Zabezpečení** a zapnout nastavení **Vyhledat v zařízení bezpečnostní hrozby**. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat další [informace](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o zprávě a důvodu, proč se po nich vyžaduje zapnutí příslušného nastavení.

- Když správci IT použijí nové zásady „Požadovat, aby bylo zakázané ladění USB (Android 4.2+)“, koncovým uživatelům se zařízeními s Androidem 4.2 nebo novějším se zobrazí zpráva Musí se zakázat ladění USB. Uživatelé budou muset přejít do části **Nastavení** > **Možnosti pro vývojáře** a vypnout nastavení **Ladění USB**. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat další [informace](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) o zprávě a důvodu, proč se po nich vyžaduje vypnutí příslušného nastavení.

- Když správci IT použijí nové zásady „Minimální úroveň oprav zabezpečení Androidu (Android 6.0 +)“, koncovým uživatelům se zařízeními s Androidem 6.0 nebo novějším se zobrazí zpráva Toto zařízení nesplňuje minimální úroveň oprav zabezpečení Androidu. Uživatelé budou muset nainstalovat požadovanou opravu zabezpečení. Prostřednictvím odkazu ve zprávě o shodě mohou uživatelé získat [informace](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o postupu při instalaci požadované opravy zabezpečení a zjistit, které opravy zabezpečení mají aktuálně nainstalovány.

#### Aplikace Portál společnosti pro iOS

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
- **MAM SDK: Podpora konfigurace délky PIN kódu.** Bude možné zadat délku PIN kódu pro aplikace MAM podobně, jako je tomu u PIN kódu zařízení. Bude tak nutné, aby koncoví uživatelé dodrželi nová omezení, která nastavíte. Zobrazí se jim mírně upravená obrazovka pro zadání PIN kódu, ve které je teď delší pole pro jeho zadání. Podrobnosti najdete v tématu [Nastavení zásad MAM pro Android](android-mam-policy-settings.md) a [Nastavení zásad MAM pro iOS](ios-mam-policy-settings.md).

- **Skype pro firmy pro iOS a Android.** Nyní můžete cílit na Skype pro firmy se [správou mobilních aplikací (MAM) bez zásad registrace](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md). Jakmile se uživatelé přihlásí, aplikují se zásady MAM.

- **Pro správu pomocí zásad MAM jsou teď dostupné nové aplikace.** Na zařízeních, která nejsou zaregistrovaná v Intune, je teď možné přidružit k zásadám MAM aplikace Microsoft Word, Excel a PowerPoint pro Android. Úplný seznam podporovaných aplikací najdete v galerii mobilních aplikací Microsoft Intune na stránce [aplikací pro Microsoft Intune od partnerů](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


### Aktualizace Portálu společnosti

#### Aplikace Portál společnosti pro Android
- **Informační zprávy pro koncové uživatele:** Koncoví uživatelé nyní uvidí informační zprávy aplikace Portál společnosti pro Android, když registrují svoje zařízení nebo je odebírají z Portálu společnosti.

- **Změny účtů správců registrace zařízení v aplikaci Portál společnosti pro Android.** Za účelem zvýšení výkonu a možností škálování už Intune v aplikaci Portál společnosti pro Android v podokně Moje zařízení nezobrazuje všechna zařízení správce registrace zařízení (DEM). Zobrazí se pouze místní zařízení, na kterém aplikace běží, a to pouze v případě, že je zaregistrováno prostřednictvím aplikace Portál společnosti. Uživatel Správce registrace zařízení může na místním zařízení provádět různé akce, ale vzdálenou správu jiných zaregistrovaných zařízení je možné provádět pouze z konzoly správce Intune.

#### Web portálu společnosti
- **Web Portál společnosti: Informační zpráva s identifikací zařízení bude koncovým uživatelům poskytovat další informace.** Koncoví uživatelé mohou nyní snadněji identifikovat zařízení, které vybrali při používání webu Portál společnosti. Pokud je vybrané nesprávné zařízení, budou moct vybrat správné zařízení klepnutím na odkaz **Klepněte sem** v informační zprávě domovské stránky.

## Co připravujeme
- **Přechod k uživatelskému rozhraní Centra zpráv**. V rámci migrace Intune do [portálu pro správu Office 365](https://portal.office.com/) začneme pro oznamování nových funkcí a pro další oznámení využívat výhod Centra zpráv. Také můžete nainstalováním mobilní doprovodné aplikace Správce Office 365 dostávat oznámení na mobilní telefon a snadno všechny zprávy přeposílat uživatelům nebo na alias distribučního seznamu.
Centrum zpráv začneme používat od květnové verze. Oznámíme vám tímto způsobem, že byly dokončeny aktualizace, a přidáme také informace o nových a vylepšených funkcích Intune. Na Centrum zpráv se můžete podívat již dnes, a to tak, že se přihlásíte na [portál pro správu Office 365](https://portal.office.com/) a v levém navigačním podokně zvolíte CENTRUM ZPRÁV.

- **Změny účtů Správců registrace zařízení**. Za účelem zvýšení výkonu a možností škálování už Intune v aplikaci Portál společnosti v iOS v podokně **Moje zařízení** nezobrazuje **všechna** zařízení správce registrace zařízení (DEM). Zobrazí se pouze místní zařízení, na kterém aplikace běží, a to pouze v případě, že je zaregistrováno prostřednictvím aplikace Portál společnosti. Uživatel Správce registrace zařízení může na místním zařízení provádět různé akce, ale vzdálenou správu jiných zaregistrovaných zařízení je možné provádět pouze z konzoly správce Intune. Kromě toho se v Intune místo účtů DEM začne používat buď program Apple DEP (Device Enrollment Program), nebo nástroj Apple Configurator. Obě tyto metody registrace již podporují registrace bez zásahu uživatele pro sdílená zařízení s iOS. Účty Správce registrace zařízení používejte pouze v případě, že registrace sdílených zařízení bez zásahu uživatele není dostupná.

### Průvodce cloudem
Udržujte si přehled o budoucích novinkách pro Intune díky [průvodci cloudovou platformou](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

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
Nyní můžete zobrazit [stav](monitor-mobile-app-management-policies-with-Microsoft-Intune.md) zásad správy aplikací pro všechny uživatele ve vašem tenantovi Azure Active Directory (AAD). Patří mezi ně:
   - Zařízení
   - Aplikace na zařízení

   Stavové hodnoty:

   **Zaregistrováno:** Označuje, že byly zásady nasazeny uživateli, v pracovním kontextu byla použita aplikace a úspěšně byly přijaty zásady.

    **Není zaregistrováno:** Označuje, že byly zásady nasazeny uživateli, ale aplikace od té doby nebyla použita v pracovním kontextu.


- **Kontrolní mechanismy správy mobilních aplikací (MAM) pro zabránění synchronizace kontaktů Outlooku (Android).**
Je k dispozici nové nastavení pro [správu mobilních aplikací](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) bez registrace zařízení. Toto nastavení vám umožňuje zabránit aplikaci v synchronizaci kontaktů s nativním adresářem na zařízeních s Androidem. Pokud je toto nastavení povoleno, cílové aplikace již nebudou nadále moci ukládat kontakty do nativního adresáře. Pokud je toto nastavení zakázáno, cílové aplikace nebudou moci ukládat kontakty do nativního adresáře. Když se rozhodnete [vymazat zařízení nebo aplikaci](wipe-managed-company-app-data-with-Microsoft-Intune.md), budou odebrány všechny kontakty, které byly uloženy do nativního adresáře. Toto nové nastavení je ve výchozím nastavení podporováno v aplikaci Outlook na zařízeních s Androidem.

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


## Březen 2016
### Co je nového od 29. března 2016
S výjimkou aktualizace obecných zásad konfigurace Windows 10 jsou všechny funkce uvolněné 29. března 2016 podporovány také pro zákazníky využívající hybridní řešení (nástroj Configuration Manager integrovaný s Intune). Brzy bude k dispozici podpora hybridních řešení pro aktualizaci obecných zásad konfigurace Windows 10. Upozorňujeme, že některé z těchto funkcí mohou vyžadovat nejnovější verzi nástroje Configuration Manager.

### Správa aplikací
- **Kontrolní mechanismy správy mobilních aplikací (MAM) pro zabránění synchronizace kontaktů Outlooku (iOS)** Je k dispozici nové nastavení pro správu mobilních aplikací bez registrace zařízení. Toto nastavení vám umožňuje zabránit aplikaci v synchronizaci kontaktů s nativním adresářem na zařízeních s iOS. Pokud je toto nastavení povoleno, aplikace již nebude nadále moci ukládat kontakty do nativního adresáře. Pokud je toto nastavení zakázáno, aplikace bude moci ukládat kontakty do nativního adresáře. Když se rozhodnete selektivně vymazat zařízení, budou odebrány všechny kontakty, které byly uloženy do nativního adresáře. Toto nové nastavení je podporováno v aplikaci Outlook na zařízeních s iOS. Další podrobnosti o tomto a dalších nastaveních najdete v tématu [Vytvoření a nasazení zásad MAM](https://technet.microsoft.com/en-us/library/dn292747.aspx).

### Řízení přístupu
- **Online Skype pro firmy podporuje podmíněný přístup.** Pro Online Skype pro firmy můžete nastavit zásady podmíněného přístupu, aby k němu měla přístup pouze spravovaná a kompatibilní zařízení s iOS a Androidem. Koncovým uživatelům, kteří se pokusí přihlásit k mobilní aplikaci Skype pro firmy na iOS a Androidu, se zobrazí výzva, aby si před přihlášením zařízení zaregistrovali v Intune a aby odstranili všechny problémy, kvůli kterým zařízení není v souladu s pravidly zásad dodržování předpisů v organizaci. Podrobnosti najdete v tématu [Správa přístupu k Online Skypu pro firmy](https://technet.microsoft.com/en-us/library/mt695297.aspx).

### Správa zařízení
- **Podpora služby Intune pro iOS 9.3.** V pondělí 21. března Apple oznámil dostupnost systému iOS 9.3. Intenzivně jsme pracovali na tom, abychom zajistili, že bude Microsoft Intune kompatibilní s nejnovější verzí mobilního operačního systému od společnosti Apple, a [s radostí oznamujeme, že Intune podporuje správu zařízení s iOS 9.3](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  Všechny existující funkce Intune aktuálně dostupné pro správu zařízení s iOS budou nadále bezproblémově fungovat, i když si uživatelé v zařízení upgradují operační systém na verzi iOS 9.3. Kromě toho je systém iOS 9.3 také podporován pro zákazníky, kteří v současné době využívají hybridní řešení (nástroj Configuration Manager integrovaný s Intune).

- **Obecné zásady konfigurace Windows 10 nyní obsahují nastavení pro správu Windows Defenderu na zaregistrovaných počítačích s Windows 10.** Podrobnosti najdete v tématu [Nastavení zásad konfigurace Windows 10 v Microsoft Intune](https://technet.microsoft.com/en-us/library/mt404697.aspx).


### Portál společnosti

- **Balíčky aplikace pro systém Windows dostupné přímo z webu Portál společnosti** Uživatelé počítačů se systémem Windows 8, Windows 8.1 a Windows RT nyní mohou instalovat balíčky aplikace pro systém Windows (s příponou .appx) přímo z webu Portál společnosti. Dříve jste museli do zařízení uživatelů nasadit (nebo si do nich uživatelé museli nainstalovat) aplikaci Portál společnosti, aby bylo možné instalovat aplikace.

- **Uživatelé mohou své zařízení vzdáleně uzamknout z webu Portál společnosti.** Na web Portál společnosti byla přidána možnost vzdáleného uzamčení, aby mohli uživatelé vzdáleně zamknout své zařízení z portálu, pokud ho ztratili nebo jim bylo odcizeno. Viz [pokyny pro koncové uživatele](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). V následující tabulce najdete informace o podpoře funkce vzdáleného uzamčení zařízení podle platforem pro samostatně využívanou službu Intune a využívání služby Intune s nástrojem Configuration Manager.

|Platforma | Podrobnosti o podpoře|
|---------|----------------|
|Android |Podporováno|
|iOS |Podporováno|
|Windows 10 Mobile |Podporováno pouze v případě, že je pro telefon nastaven přístupový kód|
|Windows 10 Desktop |Není podporované|
|Windows Phone 8.1 |Podporováno pouze v případě, že je pro telefon nastaven přístupový kód|
|Windows Phone 8.0 |Není podporované|
|PC (Windows 8.0 a starší) |Není podporované|
|PC (Windows 8.1) |Není podporované|

### Co je nového od 10. března 2016

### Správa aplikací

- **Využívání výhod správy „Open In“ systému iOS pro zařízení zaregistrovaná v řešení MDM třetí strany** Prostřednictvím dodavatele správy mobilních zařízení (MDM) třetí strany management (MDM) můžete využívat výhody správy „Open In“ v systému iOS. V rámci nastavení konfiguračního profilu můžete nastavit omezení a implementovat aplikaci podle tématu [Správa přenosu dat mezi aplikacemi pro iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

     Tento přístup má dvě hlavní výhody:

     1. Než uživatelé získají přístup k podnikovým datům z aplikace Cloud Services nebo jiné aplikace, musí se přihlásit pomocí svého pracovního účtu. Tím se zajistí uplatňování zásad správy mobilních aplikací (MAM) při přístupu k datům.

     2. Spravované e-mailové profily a další spravované aplikace nasazené prostřednictvím řešení MDM jiného výrobce umožňují sdílet soubory a data s aplikacemi, které používají zásady MAM služby Intune.

- **Správa aplikace Microsoft Outlook se zásadami MAM pro zařízení, která nejsou zaregistrovaná v Intune** Teď můžete spravovat aplikaci Microsoft Outlook na zařízeních, která nejsou zaregistrovaná v Intune, pomocí zásad správy mobilních aplikací Intune. Aktualizovaná aplikace Microsoft Outlook s podporou funkcí MAM je dostupná pro zařízení se systémem [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) i [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook). Zásadu MAM můžete vytvořit podle pokynů v tématu [Vytvoření a nasazení zásad správy mobilních aplikací](https://technet.microsoft.com/library/mt627829.aspx).  


- **Zásady konfigurace mobilní aplikace poskytují větší flexibilitu, chcete-li zadat podrobnosti uživatele pro aplikace v iOS** Můžete zadat uživatelská nastavení, která může při spuštění vyžadovat aplikace v iOS. Můžete třeba zadat síťový port nebo uživatelské jméno. Podrobnosti najdete v tématu [Konfigurace aplikací pro iOS pomocí zásad konfigurace mobilních aplikací v Microsoft Intune](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).


- **Nasazení aplikace Adobe Reader pro Microsoft Intune na zařízení s iOS spravovaná pomocí Intune ve vašem podniku** Teď můžete spravovat aplikaci Adobe Reader pro iOS na registrovaných zařízeních pomocí zásad správy mobilních aplikací Intune.

- **Zajištění otevírání nasazených webových klipů ve spravovaném prohlížeči** Můžete nasazovat cílové webové klipy, které se dají na zařízeních s iOS nebo Androidem otevřít jenom pomocí spravovaného prohlížeče. Můžete třeba nasadit odkazy na podnikové prostředky prostřednictvím Portálu společnosti, a když na ně uživatelé přejdou, příslušné stránky se otevřou přímo ve spravovaném prohlížeči, kde je chrání zásady MAM. Podrobnosti najdete v tématu [Nasazení aplikací](deploy-apps.md).


- **Hledání, správa a distribuce aplikací Windows Store pro firmy zařízení s Windows 10 z konzoly správce Intune** Intune nabízí podporu služby Windows Store pro firmy, která umožňuje hledat, spravovat a distribuovat aplikace pro spravovaná zařízení s Windows 10. Windows Store pro firmy umožňuje spravovat proces nasazení a monitorování těchto aplikací z konzoly pro správu služby Intune, kterou používáte i ke správě jiných aplikací. Windows Store pro firmy konkrétně spravuje obsah a licence „online licencovaných aplikací“. Podrobnosti najdete v tématu [Správa aplikací zakoupených ve Windows Store pro firmy](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).


### Správa zařízení
- **Distribuce certifikátů PFX pro zařízení s iOS** Správci Intune můžou vytvářet a nasazovat certifikáty PFX systému iOS pro ověřování Wi-Fi, e-mailu a VPN na zařízeních s iOS. Tato funkce je už dostupná pro zařízení se systémy Android a Windows 10. Podrobnosti najdete v tématu [Povolení přístupu k firemním prostředkům pomocí profilů certifikátů](secure-resource-access-with-certificate-profiles.md).


- **Použití aplikací a zásad v různých skupinách zařízení na základě výběru kategorie uživatelem** Správci Intune teď můžou určit vlastní kategorie zařízení, ze kterých si budou uživatelé vybírat při registraci. Správci třeba můžou chtít, aby jejich uživatelé zadali, jestli registrují zařízení typu „Pokladna“, „Nákladní vůz“ nebo „Sklad inventáře“. Na základě vybrané kategorie se zařízení stane členem skupiny zařízení služby Intune, pomocí které se dají na zaregistrované zařízení nasazovat různé aplikace a zásady. Podrobnosti najdete v tématu [Kategorizace zařízení pomocí mapování skupin zařízení](categorize-devices-with-device-group-mapping-in-microsoft-intune.md).

### Změny a aktualizace Portálu společnosti Microsoft
V této verzi došlo k následujícím změnám Portálu společnosti.

**Aplikace Portál společnosti pro Android**

* Když uživatelé spustí aplikaci spravovanou pomocí správy mobilních aplikací (MAM), zobrazí se jim zpráva, že danou aplikaci spravuje jejich společnost. Potom můžou uživatelé klepnout na odkaz „Další informace“ a zobrazit tak [další informace](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) o tom, co znamená výraz „spravovaná aplikace“. Taky můžou klepnout na „Příště už nezobrazovat“, aby se už zpráva při příštím spuštění aplikace nezobrazovala.
* Přibyly nové obrazovky, které uživatele provádí procesem registrace a obsahují další informace o tom, proč by měli uživatelé provést registraci a co správci IT vidí nebo nevidí na jejich zaregistrovaných zařízeních. Podrobnosti najdete v [pokynech k registraci](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
* Zprávy o chybách registrace se teď zobrazují v aplikaci Portál společnosti. Dřív se tyto zprávy zobrazovaly na webu Portál společnosti. Díky této změně se teď všechny chybové zprávy zobrazují na jenom jednom místě, ne na dvou.


**Aplikace Portál společnosti pro iOS**
* Když uživatelé spustí aplikaci spravovanou pomocí správy mobilních aplikací (MAM), zobrazí se jim zpráva, že danou aplikaci spravuje jejich společnost. Potom můžou uživatelé klepnout na odkaz „Další informace“ a zobrazit tak [další informace](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) o tom, co znamená výraz „spravovaná aplikace“. Taky můžou klepnout na „Příště už nezobrazovat“, aby se už zpráva při příštím spuštění aplikace nezobrazovala.
* Přibyly nové obrazovky, které uživatele provádí procesem registrace a obsahují další informace o tom, proč by měli uživatelé provést registraci a co správci IT vidí nebo nevidí na jejich zaregistrovaných zařízeních. Podrobnosti najdete v [pokynech k registraci](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).
* Zprávy o chybách registrace se teď zobrazují v aplikaci Portál společnosti. Dřív se tyto zprávy zobrazovaly na webu Portál společnosti. Díky této změně se teď všechny chybové zprávy zobrazují na jenom jednom místě, ne na dvou.




## Únor 2016
### Změny a aktualizace Portálu společnosti Microsoft

V této verzi došlo k následujícím změnám Portálu společnosti.

#### Aplikace Portál společnosti pro Android
- Přibyly nové obrazovky, které uživatele provádí procesem registrace a obsahují další informace o tom, proč by měli uživatelé provést registraci a co správci IT vidí nebo nevidí na jejich zaregistrovaných zařízeních. Podrobnosti najdete v [pokynech k registraci](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
- Zprávy o chybách registrace se teď zobrazují v aplikaci Portál společnosti. Dřív se tyto zprávy zobrazovaly na webu Portál společnosti. Díky této změně se teď všechny chybové zprávy zobrazují na jenom jednom místě, ne na dvou.

#### Aplikace Portál společnosti pro iOS
 - Přibyly nové obrazovky, které uživatele provádí procesem registrace a obsahují další informace o tom, proč by měli uživatelé provést registraci a co správci IT vidí nebo nevidí na jejich zaregistrovaných zařízeních. Podrobnosti najdete v [pokynech k registraci](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).

 - Zprávy o chybách registrace se teď zobrazují v aplikaci Portál společnosti. Dřív se tyto zprávy zobrazovaly na webu Portál společnosti. Díky této změně se teď všechny chybové zprávy zobrazují na jenom jednom místě, ne na dvou.


## Leden 2016

### Využijte funkce Windows 10
* **Podmíněný přístup prostřednictvím služby ověření stavu** Správci Intune teď můžou zobrazit ověření stavu zařízení s Windows 10 v konzole pro správu služby Intune. Ověření stavu zařízení umožňuje správcům zajistit, že klientské počítače mají důvěryhodné konfigurace systému BIOS, čipu TPM a spouštěcího softwaru. Ověření stavu zařízení podporují jenom klientská zařízení s Windows 10 s povoleným čipem TPM 2. Funkce ověření stavu zařízení zobrazí počet zařízení povolených pro každou z následujících možností:
    * Antimalware s raným spuštěním
    * BitLocker
    * Zabezpečené spouštění
    * Integrita kódu

    Další podrobnosti o nastavení ověření stavu zařízení, shromážděných datových bodech a sestavě ověření stavu najdete v tématu [Úvod do zásad dodržování předpisů zařízeními pro Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md). Článek [Podrobnosti o službě HAS](https://msdn.microsoft.com/en-us/library/dn934876.aspx) obsahuje podrobné vysvětlení této služby.

* **Windows 10 Passport for Work – správa zásad a certifikátů** Služba Intune umožňuje [integraci se službou Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md). Je to alternativní metoda pro přihlašování do Windows 10 pomocí účtu služby Active Directory nebo Azure Active Directory, která může nahradit hesla, čipové karty a virtuální čipové karty. Služba Passport umožňuje používat k přihlášení gesto uživatele místo hesla. Gesto uživatele může být jednoduchý PIN kód, biometrické ověřování jako třeba Windows Hello nebo externí zařízení, jako je třeba čtečka otisků prstů.

* **Síť VPN pro konkrétní aplikace** Můžete vybrat aplikace, které se můžou automaticky připojit k podnikové síti prostřednictvím sítě VPN. Seznam aplikací vytvoříte při nastavování profilu sítě VPN, jak popisuje téma Pomoc uživatelům s připojením k práci pomocí profilů sítě VPN v Microsoft Intune.

* **Podpora úplného vymazání ve Windows 10** Prostřednictvím konzoly pro správu Intune teď můžete vzdáleně zadat úplné vymazání stolních zařízení s Windows 10 zaregistrovaných v Intune. Funkce úplného vymazání ve Windows 10 slouží k obnovení továrního nastavení zařízení.


### Aktualizace programu Apple VPP (Volume Purchase Program)
Intune vám teď může pomoct se [správou aplikací zakoupených prostřednictvím programu Apple VPP (Volume Purchase Program) pro firmy](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md). Tato pomoc zahrnuje synchronizaci licenčních informací mezi společností Apple a službou Intune a sledování počtu nasazených kopií jednotlivých aplikací.

### Identifikace zařízení patřících společnosti pomocí kódů IMEI
Teď můžete [importovat identifikační kódy IMEI (International Mobile Equipment Identity)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) pro platformy mobilních zařízení vybavených kódy IMEI. Ty vám pomůžou identifikovat mobilní zařízení patřící společnosti. Po registraci do Intune jsou zařízení s importovanými kódy IMEI označená jako firemní. Tato informace se dá využít k uplatnění zásad, které se liší od zásad používaných na soukromých zařízeních.

### Se zásadami MAM služby Intune je teď kompatibilní větší množství aplikací
Se zásadami správy mobilních aplikací (MAM) ve službě Intune jsou teď kompatibilní další aplikace od partnerů Microsoftu (pro zařízení spravovaná pomocí Intune):
* Box for EMM (od výrobce Box Inc) – jenom pro iOS
* Adobe Reader (od výrobce Adobe) – jenom pro Android
* Foxit PDF Reader (od výrobce Foxit Corporation) – pro iOS a Android


### V lednu končí podpora IE9
Od února 2016 už Internet Explorer 9 nebude podporovaný jako oficiální prohlížeč pro přístup k webu portálu společnosti Microsoft Intune, portálu účtů Intune a konzole pro správu Intune. Budete muset migrovat na Internet Explorer 10 nebo novější verzi.


>[!div class="step-by-step"]

>[&larr; **Co je nového v Intune**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Aug16_HO3-->


