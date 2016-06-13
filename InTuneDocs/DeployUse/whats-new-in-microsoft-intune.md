---
# required metadata

experiment_id: lindavr-abtest-20160527
experimental: true
title: Co je nového | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Co je nového v Microsoft Intune


## Květen 2016


S výjimkou integrace TeamVieweru jsou všechny tyto funkce podporované také pro hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší stránce [Co je nového pro hybridní nasazení](https://technet.microsoft.com/en-us/library/mt718155.aspx).

### Dokumentace

Vítejte ve verzi Preview pro [docs.microsoft.com](https://docs.microsoft.com/en-us/intune)!
Toto je zcela nová platforma s moderním obsahem, navržená tak, aby bylo snazší pro vás, naše zákazníky, pochopit a používat službu Intune.
Informace o všech nových funkcích najdete v tématu [Představení docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/).

### Stav služby Intune
Informace o stavu služby pro Intune se přesouvají do centrálního umístění společně s ostatními službami Microsoftu. Tyto informace nyní najdete na [portálu pro správu Office 365](https://portal.office.com/Admin/Default.aspx) v části věnované **stavu služby**.
Další informace najdete v [tomto příspěvku blogu](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).


### Správa aplikací

- **MAM SDK: Podpora konfigurace délky PINu.** Bude možné zadat délku PINu pro aplikace MAM podobně, jako je tomu u PINu zařízení. Bude tak nutné, aby koncoví uživatelé dodrželi nová omezení, která nastavíte. Zobrazí se jim mírně upravená obrazovka pro zadání PINu, ve které je teď delší pole pro jeho zadání. Podrobnosti najdete v tématu [Nastavení zásad MAM pro Android](/intune/deploy-use/android-mam-policy-settings) a [Nastavení zásad MAM pro iOS](/intune/deploy-use/ios-mam-policy-settings).

- **Skype pro firmy pro iOS a Android.** Nyní můžete cílit na Skype pro firmy se [správou mobilních aplikací (MAM) bez zásad registrace](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Jakmile se uživatelé přihlásí, aplikují se zásady MAM.

- **Pro správu pomocí zásad MAM jsou teď dostupné nové aplikace.** Na zařízeních, která nejsou zaregistrovaná v Intune, je teď možné přidružit k zásadám MAM aplikace Microsoft Word, Excel a PowerPoint pro Android. Úplný seznam podporovaných aplikací najdete v galerii mobilních aplikací Microsoft Intune na stránce [aplikací pro Microsoft Intune od partnerů](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).

### Správa zařízení

- **Relace vzdálené pomoci pro počítače s Windows.** Integrace TeamVieweru pro počítače s Windows spravované klientským softwarem Intune vám umožní navázání relací vzdálené pomoci s počítači s Windows z důvodu podpory oddělení helpdesku. Mezi podporované počítače patří počítače s Windows 7, 8, 8.1 a Windows 10.
Podrobnosti najdete v tématu [Běžné úlohy správy počítačů s Windows pomocí počítačového klienta Microsoft Intune](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#respond-to-a-remote-assistance-request).

### Aktualizace Portálu společnosti

#### Aplikace Portál společnosti pro Android

- **Informační zprávy pro koncové uživatele:** Koncoví uživatelé nyní uvidí informační zprávy aplikace Portál společnosti pro Android, když registrují svoje zařízení nebo je odebírají z portálu společnosti.

- **Změny účtů správců registrace zařízení v aplikaci Portál společnosti pro Android.** Za účelem zvýšení výkonu a možností škálování už Intune v aplikaci Portál společnosti pro Android v podokně Moje zařízení nezobrazuje všechna zařízení správce registrace zařízení (DEM). Zobrazí se pouze místní zařízení, na kterém aplikace běží, a to pouze v případě, že je zaregistrováno prostřednictvím aplikace Portál společnosti. Uživatel Správce registrace zařízení může na místním zařízení provádět různé akce, ale vzdálenou správu jiných zaregistrovaných zařízení je možné provádět pouze z konzoly správce Intune.
-
#### Web portálu společnosti

**Web Portál společnosti: Informační zpráva s identifikací zařízení bude koncovým uživatelům poskytovat další informace.** Koncoví uživatelé mohou nyní snadněji identifikovat zařízení, které vybrali při používání webu Portál společnosti. Pokud je vybrané nesprávné zařízení, budou moct vybrat správné zařízení klepnutím na odkaz **Klepněte sem** v informační zprávě domovské stránky.


## Co připravujeme

- **Přechod k uživatelskému rozhraní centra zpráv**. V rámci migrace Intune do [portálu pro správu Office 365](https://portal.office.com/) začneme pro oznamování nových funkcí a pro další oznámení využívat výhod Centra zpráv. Také můžete nainstalováním mobilní doprovodné aplikace Správce Office 365 dostávat oznámení na mobilní telefon a snadno všechny zprávy přeposílat uživatelům nebo na alias distribučního seznamu.
Centrum zpráv začneme používat od květnové verze. Oznámíme vám tímto způsobem, že byly dokončeny aktualizace, a přidáme také informace o nových a vylepšených funkcích Intune. Na Centrum zpráv se můžete podívat již dnes, a to tak, že se přihlásíte na [portál pro správu Office 365](https://portal.office.com/) a v levém navigačním podokně zvolíte CENTRUM ZPRÁV.

- **Změny účtů Správců registrace zařízení**. Za účelem zvýšení výkonu a možností škálování už Intune v aplikaci Portál společnosti v iOS v podokně **Moje zařízení** nezobrazuje **všechna** zařízení správce registrace zařízení (DEM). Zobrazí se pouze místní zařízení, na kterém aplikace běží, a to pouze v případě, že je zaregistrováno prostřednictvím aplikace Portál společnosti. Uživatel Správce registrace zařízení může na místním zařízení provádět různé akce, ale vzdálenou správu jiných zaregistrovaných zařízení je možné provádět pouze z konzoly správce Intune. Kromě toho se v Intune místo účtů DEM začne používat buď program Apple DEP (Device Enrollment Program), nebo nástroj Apple Configurator. Obě tyto metody registrace již podporují registrace bez zásahu uživatele pro sdílená zařízení s iOS. Účty Správce registrace zařízení používejte pouze v případě, že registrace sdílených zařízení bez zásahu uživatele není dostupná.

### Plán cloudu
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



## Předchozí verze Intune
Informace o tom, co bylo vydáno v rámci Intune během posledních šest měsíců, najdete v článku [Předchozí verze Intune](previous-intune-releases.md).



### Související témata
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)


<!--HONumber=Jun16_HO1-->


