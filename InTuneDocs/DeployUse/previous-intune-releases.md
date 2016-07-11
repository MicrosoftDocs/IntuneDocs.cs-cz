---
title: "Předchozí verze | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 06/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.reviewer: mamoriss
ms.suite: ems
ms.sourcegitcommit: 3080d23f464e96315ed9e5fd59774ba9f1b2dd86
ms.openlocfilehash: 65d582958d77150091880cce72e079b87308209f


---

# Předchozí verze Intune
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

## Prosinec 2015
### Změny a aktualizace Portálu společnosti Microsoft
V této verzi došlo k následujícím změnám Portálu společnosti.

**Aplikace Portál společnosti pro Android**

K zajištění souladu s novými požadavky Googlu se provedly následující změny. Na zařízeních se systémem Android 6.0 a vyšším se uživatelům zobrazují dvě nové zprávy:
* Povolit pro Portál společnosti telefonování a správu telefonních hovorů?
* Povolit pro Portál společnosti přístup k fotkám, médiím a souborům ve vašem zařízení?

Podrobnosti o těchto dvou zprávách najdete v následujících tabulkách.



Text zprávy  |Povolit pro Portál společnosti telefonování a správu telefonních hovorů?  
---------|---------
Význam zprávy     |  Povoluje odeslat IMEI a telefonní číslo zařízení uživatele službě Intune a zobrazit tyto informace v konzole pro správu na stránce Hardware.   </br></br>**POZNÁMKA: Aplikace Portál společnosti nikdy netelefonuje ani nespravuje telefonní hovory!** Text zprávy je pod kontrolu Googlu a nejde ho změnit. </br></br>Pokud chcete zobrazit stránku **Hardware**, použijte možnosti **Skupiny** > **Všechna mobilní zařízení** > **Zařízení**. Vyberte zařízení uživatele a pak použijte možnosti **Zobrazit vlastnosti** > **Hardware**.    
Kde a kdy se zpráva zobrazí  | Zpráva se zobrazí, když se uživatel poprvé přihlásí k aplikaci Portál společnosti a začne registrovat svoje zařízení.|         
Co se stane, když uživatel povolí přístup  |  IMEI a telefonní číslo zařízení se zobrazí v konzole pro správu na stránce Hardware. |         
Co se stane, když uživatel přístup odepře     | Může i dál používat aplikaci Portál společnosti a registrovat zařízení, ale IMEI a telefonní číslo jeho zařízení se na stránce Hardware v konzole pro správu nezobrazí.       </br></br> Při druhém přihlášení k aplikaci Portál společnosti po odepření přístupu se ve zprávě zobrazí zaškrtávací políčko **Příště se už neptat**, takže uživatel může určit, že se tato zpráva už nebude zobrazovat.</br></br>Pokud uživatel povolí přístup, ale později ho odepře, tato zpráva se zobrazí při přihlášení k aplikaci Portál společnosti, které následuje po registraci zařízení.</br></br>Pokud se uživatelé rozhodnou povolit přístup později, mohou přejít na **Nastavení** > **Aplikace** > **Portál společnosti** > **Oprávnění** > **Telefon** a toto oprávnění zapnout.
Další informace     |  Pro vaše uživatele: [Přihlášení do aplikace Portál společnosti](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>Pro profesionály v oblasti IT: Informace v této tabulce jsou uvedené taky v části [Jak uživatelům pomoct pochopit zprávy aplikace Portál společnosti](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   

Text zprávy  |Povolit pro Portál společnosti přístup k fotkám, médiím a souborům ve vašem zařízení?  
---------|---------
Význam zprávy     |  Povoluje, aby zařízení zapsalo datové protokoly na kartu SD zařízení, která umožňuje přesunutí protokolů pomocí kabelu USB.   </br></br>**POZNÁMKA: Aplikace Portál společnosti nikdy nemá přístup k fotografiím, médiím a souborům uživatele.** Text zprávy je pod kontrolu Googlu a nejde ho změnit.     
Kde a kdy se zpráva zobrazí  | Zpráva se zobrazí, když uživatel klepnutím na **Odeslat data** odešle datové protokoly příslušnému správci IT.|         
Co se stane, když uživatel povolí přístup  |  Protokoly se zkopírují na kartu SD. |         
Co se stane, když uživatel přístup odepře     | Může i dál posílat datové protokoly, ale tyto protokoly se nezkopírují na kartu SD zařízení.       </br></br> Při druhém přihlášení k aplikaci Portál společnosti po odepření přístupu se ve zprávě zobrazí zaškrtávací políčko **Příště se už neptat**, takže uživatel může určit, že se tato zpráva už nebude zobrazovat.</br></br>Pokud uživatel povolí přístup, ale později ho odepře, tato zpráva se zobrazí při příštím pokusu o odeslání protokolu.</br></br>Pokud se uživatelé rozhodnou povolit přístup později, mohou přejít na **Nastavení** > **Aplikace** > **Portál společnosti** > **Oprávnění** > **Úložiště** a toto oprávnění zapnout.
Další informace     |  Pro vaše uživatele: [Odeslání protokolů s diagnostickými daty e-mailem vašemu správci IT](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>Pro profesionály v oblasti IT: Informace v této tabulce jsou uvedené taky v části [Jak uživatelům pomoct pochopit zprávy aplikace Portál společnosti](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   


**Aplikace Portál společnosti pro iOS**
* Uživatelé teď můžou k odesílání diagnostických protokolů správci IT používat Microsoft Outlook nebo další poštovní aplikace. Dřív šlo použít jenom nativní aplikaci.
* Vylepšila se podpora programu DEP (Device Enrollment Program)  společnosti Apple a registrovaných podnikových zařízení. Podrobnosti najdete v tématu [Při pokusu o registraci se zobrazí výzva k identifikaci vašeho zařízení](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device).
* V seznamu registrovaných zařízení uživatele se teď vedle zařízení, které uživatel právě používá, zobrazí zelené zaškrtnutí. Před přidáním tohoto zaškrtnutí uživatelé nemohli s jistotou určit, které registrované zařízení používají.

**Aplikace Portál společnosti pro Windows**

Microsoft automaticky shromažďuje anonymní informace o výkonu a využití portálu společnosti za účelem zlepšení svých produktů a služeb. Koncoví uživatelé můžou na svém zařízení shromažďování dat vypnout v nastavení dat o využití, ale správci nemají nad shromažďováním dat žádnou kontrolu a nemůžou toto nastavení koncového uživatele nijak změnit.



## Listopad 2015
### Správa aplikací
Intune podporuje zásady správy mobilních aplikací (MAM), které můžou pomoct zabránit v úniku firemních dat do uživatelských aplikací nebo služeb. Dřív se tyto zásady vynucovaly jenom v mobilních aplikacích spuštěných na zařízeních, která byla zároveň zaregistrovaná do správy mobilních zařízení (MDM) ve službě Intune.

V rámci aktualizace v tomto měsíci ale Intune rozšiřuje svoje funkce MAM na nové třídy zařízení. Vedle zařízení zaregistrovaných ve službě Intune teď můžete vynucovat zásady MAM i na těchto zařízeních:
* Zařízení nespravovaná žádným řešením správy mobilních zařízení (MDM)
* Zařízení nezaregistrovaná v žádném systému správy zařízení, většinou vlastní zařízení uživatelů

Další informace o těchto nových funkcích MAM najdete v těchto příspěvcích na blogu:
* [Zvýšení produktivity spravovaných mobilních zařízení](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [Nové možnosti sady Enterprise Mobility](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Kromě toho existují také další zajímavosti a funkce o funkcích MAM ve službě Intune:
* Podniková data jsou v aplikacích určených pro Intune, včetně aplikací Office Mobile, aplikací jiných výrobců, které používají sadu Intune SDK, a obchodních aplikací začleněných do služby Intune, izolovaná od uživatelských dat.
* Podniková data se dají sdílet (**vyjmout/kopírovat/vložit**) v různých podnikových aplikacích a zároveň je možné zabránit jejich sdílení v osobních aplikacích. Další informace najdete v článku [Jak zásady MAM chrání data aplikací](https://technet.microsoft.com/library/mt627825.aspx). Ukázkový scénář [Použití aplikace Microsoft Word k pracovním a osobním úkolům](https://technet.microsoft.com/library/mt627827.aspx) vysvětluje, jak se dá zabránit sdílení podnikových dat v osobních aplikacích.
* Používají se zásady prevence ztráty klíčových dat, jako je kód PIN pro jednotlivé aplikace, ovládací prvky funkce Uložit jako a spravované sdílení dat mezi aplikacemi. Seznam všech zásad najdete v tématu [Vytvoření a nasazení zásad správy mobilních aplikací pomocí Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Těmito novými funkcemi jsou vybavené aplikace Word, Excel, PowerPoint, Outlook, OneNote a OneDrive pro firmy, takže se dají spravovat s registrací zařízení nebo bez ní. Standardní aplikace Office v obchodě Apple Store nebo Google Store mají nativně vestavěné funkce ochrany proti ztrátě dat a nevyžadují zabalení aplikace ani zkušební načtení před prodejem.
* O zahájení práce si můžete přečíst v tématu [Začínáme se zásadami správy mobilních aplikací na portálu Azure](https://technet.microsoft.com/library/mt627830.aspx). Pokud chcete zjistit, jak nakonfigurovat a nasadit zásady správy mobilních aplikací, přečtěte si téma [Vytvoření a nasazení zásad správy mobilních aplikací pomocí Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Pokud se koncoví uživatelé přihlásí do aplikace pomocí firemních přihlašovacích údajů, funkce ochrany proti ztrátě dat se nastaví automaticky. Téma [Činnost koncových uživatelů pro aplikace přidružené k zásadám správy mobilních aplikací Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx) obsahuje ukázkové scénáře přístupu k OneDrivu na zařízeních se systémy iOS a Android.
* Funguje na zařízeních se systémy iOS a Android.

Do seznamu [aplikací Microsoftu, které podporují zásady správy mobilních aplikací v Microsoft Intune](https://technet.microsoft.com/library/dn708489.aspx), přibyly nejnovější aplikace.

### Správa zařízení
 **Správa zařízení s Mac OS X** Intune teď umožňuje registraci a správu zařízení s Mac OS X. Se zařízeními s Mac OS X můžete provádět tyto úlohy:
* Registrovat zařízení pro správu pomocí Intune. Další informace najdete v tématu [Nastavení správy pro iOS a Mac pomocí Microsoft Intune](https://technet.microsoft.com/library/dn408185.aspx).
* Ovládat nastavení zařízení pomocí zásad obecné konfigurace. Informace najdete v tématu [Nastavení zásad konfigurace pro Mac OS X v Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx).
* Nasadit vytvořené nastavení systému Mac OS X pomocí nástroje Apple Configurator. Informace najdete v tématu [Nastavení vlastních zásad pro Mac OS X v Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx).
* Sestavit inventář hardwaru a softwaru ze zařízení s Mac OS X. Informace najdete v tématu [Seznámení se zařízeními s inventářem v Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx).
* Spustit nové sestavy, které zobrazují podrobnosti o spravovaných zařízeních se systémem Mac OS X. Informace najdete v tématu [Pochopení operací Microsoft Intune pomocí sestav](https://technet.microsoft.com/library/dn646977.aspx).

**Nové nastavení prohlížeče Edge pro zařízení s Windows 10** Do zásad obecné konfigurace systému Windows 10 přibyla nová nastavení, která umožňují spravovat nastavení a funkce prohlížeče Microsoft Edge. Informace najdete v tématu [Nastavení zásad konfigurace Windows 10 v Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx).

**E-mailové profily** Přibyla nová zásada e-mailových profilů pro stolní počítače s Windows 10 a mobilní zařízení s Windows 10. Informace najdete v tématu [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](https://technet.microsoft.com/library/dn646984.aspx).

**Nová nastavení zásad dodržování předpisů** Do seznamu zásad dodržování předpisů přibyla tato nová nastavení zabezpečení a systémových zásad:
* Pokud chcete mít jistotu, že zařízení se systémem Windows 8.1 nebo novějším, která přistupují k vašim podnikovým prostředkům, mají nainstalované nejnovější aktualizace, použijte nastavení **Vyžadovat automatické aktualizace**. Můžete také určit typ aktualizací, které se mají instalovat automaticky – buď se budou instalovat všechny aktualizace označené jako důležité, nebo všechny aktualizace označené jako důležité nebo doporučené. Úplný seznam nastavení zásad dodržování předpisů najdete v tématu [Správa zásad dodržování předpisů zařízeními pro Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx).
* Nové nastavení **Po návratu zařízení ze stavu nečinnosti vyžadovat heslo** v kombinaci s existujícím nastavením **Počet minut nečinnosti před vyžádáním hesla** umožňuje vytvořit nastavení dodržování předpisů, které vyžaduje, aby koncový uživatel zadal heslo, pokud chce použít zařízení, které bylo nějakou dobu nečinné.

**Nové možnost zásad podmíněného přístupu** Nové i existující zásady podmíněného přístupu můžete použít na **všechny uživatele**. Všichni uživatelé s licencí pro Intune a Office 365 budou muset svoje zařízení zaregistrovat, a pokud Intune platformu zařízení nepodporuje, zablokuje se přístup ke klientským aplikacím pomocí [přihlášení založeného na ověření ve službě Active Directory (moderní ověřování)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/).

Můžete také určit, že se mají zásady podmíněného přístupu uplatňovat na **všechny platformy**.  Každá klientská aplikace používající [přihlášení založené na ověření ve službě Active Directory (moderní ověřování)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) podléhá zásadám podmíněného přístupu, a Intune momentálně nepodporuje danou platformu, dojde k jejímu zablokování.

### Změny a aktualizace Portálu společnosti Microsoft
V této verzi se provedly následující změny aplikací portálu společnosti:

* **Android**: V aplikaci Portál společnosti pro Android přibyla úvodní obrazovka, která pomáhá uživatelům pochopit účel aplikace Portál společnosti. Tato obrazovka má snížit počet stažení aplikace ze strany uživatelů, jejichž společnosti nemají předplatné Intune.

* **iOS**: Intune teď podporuje nasazení zařízení s Mac OS X pomocí [webu Portál společnosti](https://portal.manage.microsoft.com). Pokyny najdete v tématu [Registrace zařízení se systémem Mac OS X v Intune](https://technet.microsoft.com/library/mt598622.aspx).

* **Web Portál společnosti**: Uživatelé, kteří si zaregistrovali zařízení v Intune, teď ke změně hesla můžou použít možnost **Resetovat heslo** na webu Portál společnosti. Dřív mohli hesla uživatelů resetovat jenom správci IT. Možnost Resetovat heslo se nepodporuje v zařízeních s Windows 8.1 a Windows RT a zobrazuje se jenom, když jsou zařízení zaregistrovaná pomocí správy mobilních zařízení (MDM) nebo MDM s Exchange ActiveSync. Pokyny pro uživatele najdete v části [Obnovení hesla](https://technet.microsoft.com/library/mt590895.aspx).

### Změny licencí pro globální správce
V říjnu jsme oznámili, že globální správci (také označovaní jako správci klienta) by mohli dál vykonávat běžné úkony správy bez samostatné licence služby Intune nebo sady EMS (Enterprise Mobility Suite). Pokud ale chtějí globální správci službu používat, například zaregistrovat si svoje vlastní nebo firemní zařízení nebo používat portál společnosti Intune, budou potřebovat licenci služby Intune nebo sady EMS jako ostatní uživatelé. Níže najdete pár dalších podrobností.
* Portál společnosti Intune je místo, kde můžou koncoví uživatelé provádět tyto kroky:
    * Registrovat svoje zařízení
    * Zobrazit stav svého zařízení
    * Stáhnout si software, který globální správce nasadil v organizaci
    * Získat odkazy pro kontaktování oddělení IT, které zveřejnil globální správce.

    [Získejte informace o portálu společnosti](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) a [o tom, jak portál společnosti přizpůsobit](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal).
* Osoba, která se zaregistruje k nákupu předplatného Intune nebo EMS jménem organizace, se automaticky stává prvním globálním správcem daného klienta. Na podzim služba Intune začala těmto prvním globálním správcům v rámci přechodu na [portál služeb Office 365](http://portal.office.com/) a vyřazení [portálu účtů Intune](http://account.manage.microsoft.com/) přidělovat licenci služby Intune nebo sady EMS. Každý další přidaný globální správce může pokračovat v každodenní správě bez samostatné licence služby Intune nebo sady EMS. Pokud by se začal chovat jako koncový uživatel a zaregistroval svoje vlastní (nebo firemní) zařízení nebo stáhl software z portálu společnosti, znamenalo by to, že už potřebuje licenci jako každý jiný uživatel.
* Tato změna se bude zavádět postupně a spustí se v lednu 2016.
* Pro partnery Microsoftu platí, že tato změna by neměla mít vliv na jejich schopnost spravovat službu pro potřeby jejich zákazníků. V případě úloh koncového uživatele bude uživatel potřebovat licenci služby Intune nebo sady EMS, aby mohl zaregistrovat zařízení a získat přístup k softwaru z portálu společnosti nebo ho stáhnout.

Pokud máte k této změně nějaké dotazy, obraťte se na tým podpory služby Intune:
* [Kanály podpory služby Microsoft Intune](https://technet.microsoft.com/library/jj839713.aspx)
* [Podpora komunity](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

Pokud chcete odeslat obecnou zpětnou vazbu ke službě Microsoft Intune, včetně vyplnění žádosti o změnu návrhu nebo oznámení chyb, navštivte stránku [Intune User Voice](https://microsoftintune.uservoice.com/).


### Co je nového v dokumentaci k Intune -- listopad 2015
**Nový obsah**
* [Nastavení zásad konfigurace systému Mac OS X v Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx): Určuje způsob ovládání nastavení a funkcí zařízení se systémem Mac OS X.
* [Nastavení vlastních zásad konfigurace systému Mac OS X v Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx): Určuje, jak nasadit nastavení zařízení se systémem Mac OS X, které jste vytvořili pomocí nástroje Apple Configurator.
* [Konfigurace zásad aplikací pro prevenci ztráty dat v Microsoft Intune](https://technet.microsoft.com/library/mt627825.aspx): Obsahuje informace o scénářích podporovaných zásadami správy mobilních aplikací a o tom, jak tyto zásady chrání data.
* [Začínáme se zásadami správy mobilní aplikace na portálu Azure](https://technet.microsoft.com/library/mt627830.aspx): Všechno, co potřebujete, abyste mohli začít používat portál Azure Preview pro zásady správy mobilních aplikací.
* [Vytvoření a nasazení zásad správy mobilních aplikací v Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx): Obsahuje podrobný návod, jak vytvořit zásady správy mobilních aplikací na portálu Azure Preview.
* [Monitorování zásad správy mobilních aplikací v Microsoft Intune](https://technet.microsoft.com/library/mt627824.aspx): Informace o tom, jak monitorovat zásady správy mobilních aplikací pomocí portálu Azure Preview.
* [Zásady správy mobilních aplikací v Microsoft Intune a funkce Open In systému iOS](https://technet.microsoft.com/library/mt627821.aspx): Informace o tom, jak zásady správy mobilních aplikací spolupracují s funkcí Open In systému iOS.
* [Činnost koncových uživatelů pro aplikace přidružené k zásadám správy mobilních aplikací Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx): Popisuje způsob práce koncového uživatele při použití aplikaci přidružených k určité zásadě správy mobilních aplikací.
* [Vymazání dat ze spravovaných firemních aplikací pomocí Microsoft Intune](https://technet.microsoft.com/library/mt627826.aspx): Popisuje, jak odebrat data z podnikových aplikací.

**Aktualizovaný obsah**
* [Nastavení zásad konfigurace Windows 10 v Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx): Přibylo nové nastavení prohlížeče Edge.
* [Nastavení správy pro iOS a Mac v Microsoft Intune](http://technet.microsoft.com/library/dn408185.aspx): Přibyly informace o registraci zařízení se systémem Mac OS X.
* [Pochopení vašeho zařízení s inventářem v Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx): Přibyly informace o inventáři shromážděném ze zařízení se systémem Mac OS X. Také došlo k aktualizaci tématu, takže teď obsahuje nejnovější informace o všech platformách zařízení.
* [Pochopení operací Microsoft Intune pomocí sestav](https://technet.microsoft.com/library/dn646977.aspx): Přibyly informace o dvou nových sestavách, které slouží k zobrazení informací o spravovaných zařízeních se systémem Mac OS X.
* [Správa zásad dodržování předpisů zařízeními pro Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx): Přibyly informace o nových zásadách dodržování předpisů, které se týkají vyžadování automatických aktualizací a vyžadování hesla při návratu zařízení ze stavu nečinnosti.
* [Správa přístupu k e-mailu v Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx): Přibyly informace o schopnosti uplatňovat zásady podmíněného přístupu na všechny platformy a uživatele.
* [Správa přístupu ke službě SharePoint Online v Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx): Přibyly informace o schopnosti uplatňovat zásady podmíněného přístupu na všechny platformy a uživatele.

## Říjen 2015

### Aktualizace podmíněného přístupu pro místní Exchange
**Teď můžete vyhovujícím zařízením zaregistrovaným v Intune povolit přístup k e-mailu protokolu Exchange Active Sync, pokud je globální pravidlo Exchange nastavené na blokování nebo karanténu** Až do této chvíle platilo, že pokud jste chtěli na zaregistrovaných a vyhovujících zařízeních povolit přístup k e-mailu, bylo potřeba nastavit výchozí globální pravidlo Exchange na **Povolit**.

Po této aktualizaci služby už toto nastavení není k podmíněnému přístupu nezbytné. Pokud vaše prostředí Exchange vyžaduje, abyste výchozí globální pravidlo nastavili na **Blokovat / Umístit do karantény**, stačí na stránce zásad podmíněného přístupu do místního prostředí Exchange zaškrtnout políčko **Přepsat výchozí pravidlo**. Další informace o pravidlech a výsledných oznámeních pro koncové uživatele najdete v tématu [Správa přístupu k e-mailu v Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx).

**Nové prostředí karantény přístupné jedním kliknutím** Zjednodušili jsme využití e-mailu o umístění do karantény, takže teď umožňuje registraci jedním kliknutím. Pomocí této aktualizace služby můžou koncoví uživatelé dokončit proces registrace v aplikaci Portál společnosti kliknutím na odkaz v e-mailu o umístění do karantény.
### Aktualizace správy mobilních zařízení a aplikací
**Android** Všechny funkce pro správu služby Intune teď podporují systém Android 6.0 (Marshmallow), jak se píše v tomto příspěvku na blogu: [Microsoft Intune nabízí podporu systému Android Marshmallow od nultého dne](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx).

**iOS** Už nemůžete vytvářet nová nasazení aplikací do zařízení iOS se starší verzí operačního systému než iOS 7.1. Všechna stávající nasazení aplikací do zařízení se starší verzí operačního systému než iOS 7.1 budou dál fungovat a bude je spravovat Intune.

**Windows 10** Intune teď podporuje nasazení univerzálních aplikací pro Windows 10 pomocí instalačního softwaru typu **balíček aplikací systému Windows**. Podrobnosti a požadavky najdete v tématu [Začínáme s nasazováním aplikací v Microsoft Intune](http://technet.microsoft.com/en-US/library/dn646955.aspx).


### Změny a aktualizace aplikací portálů společnosti Microsoft
V aplikacích Portál společnosti byly v této verzi provedeny následující změny: **iOS** Do aplikace Portál společnosti byla přidána nová tlačítka, která uživatelům usnadňují odesílání diagnostických protokolů správcům IT:

|Název tlačítka|Místo zobrazení|
|------------|---------------|
|Zpráva|Zprávy s chybovou výstrahou|
|Odeslat diagnostickou sestavu|Obrazovka O aplikaci v aplikaci Portál společnosti|


>[!div class="step-by-step"]

>[&larr; **Co je nového v Intune**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Jun16_HO3-->


