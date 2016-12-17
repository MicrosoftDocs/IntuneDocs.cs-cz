---
title: "Předchozí verze | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4dab832da4490c3df045d2c627b231028c92b25
ms.openlocfilehash: 3de5e57589a24600301e54a3b60eecb5321ff838


---

# <a name="previous-intune-releases"></a>Předchozí verze Intune

Tato stránka představuje seznam oznámení uvedených na stránce s [novinkami v Microsoft Intune](whats-new-in-microsoft-intune.md).

[!INCLUDE[wit_nextref](../includes/whats-new-last-six-months.md)]

## <a name="may-2016"></a>Květen 2016
Všechny tyto funkce jsou také podporovány pro hybridní nasazení (nástroj Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší stránce věnované [novinkám pro hybridní nasazení](https://technet.microsoft.com/en-us/library/mt718155.aspx).

### <a name="documentation"></a>Dokumentace
Vítejte ve verzi Preview pro [docs.microsoft.com](https://docs.microsoft.com/en-us/intune).
Toto je zcela nová platforma s moderním obsahem, navržená tak, aby bylo snazší pro vás, naše zákazníky, pochopit a používat službu Intune.
Informace o všech nových funkcích najdete v tématu [Představení docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/).

### <a name="intune-service-health"></a>Stav služby Intune
Informace o stavu služby pro Intune se přesouvají do centrálního umístění společně s ostatními službami Microsoftu. Tyto informace nyní najdete na [portálu pro správu Office 365](https://portal.office.com/Admin/Default.aspx) v části věnované **stavu služby**.
Další informace najdete v [tomto příspěvku blogu](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Správa aplikací
- **MAM SDK: Podpora konfigurace délky PIN kódu** Bude možné zadat délku PIN kódu pro aplikace MAM podobně, jako je tomu u PIN kódu zařízení. Bude tak nutné, aby koncoví uživatelé dodrželi nová omezení, která nastavíte. Zobrazí se jim mírně upravená obrazovka pro zadání PIN kódu, ve které je teď delší pole pro jeho zadání. Podrobnosti najdete v tématu [Nastavení zásad MAM pro Android](/intune/deploy-use/android-mam-policy-settings) a [Nastavení zásad MAM pro iOS](/intune/deploy-use/ios-mam-policy-settings).

- **Skype pro firmy pro iOS a Android** Nyní můžete cílit na Skype pro firmy se [správou mobilních aplikací (MAM) bez zásad registrace](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Jakmile se uživatelé přihlásí, aplikují se zásady MAM.

- **Pro správu pomocí zásad MAM jsou teď dostupné nové aplikace** Na zařízeních, která nejsou zaregistrovaná v Intune, je teď možné přidružit k zásadám MAM aplikace Microsoft Word, Excel a PowerPoint pro Android. Úplný seznam podporovaných aplikací najdete v galerii mobilních aplikací Microsoft Intune na stránce [aplikací pro Microsoft Intune od partnerů](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


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
Nyní můžete zobrazit [stav](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) zásad správy aplikací pro všechny uživatele ve vašem tenantovi Azure Active Directory (AAD). Patří mezi ně:
   - Zařízení
   - Aplikace na zařízení

   Stavové hodnoty:

   **Zaregistrováno:** Označuje, že byly zásady nasazeny uživateli, v pracovním kontextu byla použita aplikace a úspěšně byly přijaty zásady.

    **Není zaregistrováno:** Označuje, že byly zásady nasazeny uživateli, ale aplikace od té doby nebyla použita v pracovním kontextu.


- **Kontrolní mechanismy správy mobilních aplikací (MAM) pro zabránění synchronizace kontaktů Outlooku (Android)**
Je k dispozici nové nastavení pro [správu mobilních aplikací](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) bez registrace zařízení. Toto nastavení vám umožňuje zabránit aplikaci v synchronizaci kontaktů s nativním adresářem na zařízeních s Androidem. Pokud je toto nastavení povoleno, cílové aplikace již nebudou nadále moci ukládat kontakty do nativního adresáře. Pokud je toto nastavení zakázáno, cílové aplikace nebudou moci ukládat kontakty do nativního adresáře. Když se rozhodnete [vymazat zařízení nebo aplikaci](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune), budou odebrány všechny kontakty, které byly uloženy do nativního adresáře. Toto nové nastavení je ve výchozím nastavení podporováno v aplikaci Outlook na zařízeních s Androidem.

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

>[!div class="step-by-step"]

>[&larr; **Co je nového v Intune**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Dec16_HO1-->


