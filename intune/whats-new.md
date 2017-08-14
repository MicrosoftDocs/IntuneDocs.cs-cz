---
title: "Co je nového v Microsoft Intune"
titleSuffix: Intune on Azure
description: "Zjistěte, jaké novinky přináší portál Intune Azure."
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 08/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f915c805b20e88c661ad52e280a31054bbebce02
ms.sourcegitcommit: 2ed8d1c39d4b3e3282111f1d758afb3a50f19f8f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Co je nového v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zjistěte, jaké novinky každý týden přináší Microsoft Intune. Můžete také získat informace o [nadcházejících změnách](#whats-coming), [důležitá oznámení](#notices) o službě a informace o [minulých verzích](whats-new-archive.md).

> [!Note]
> Mnohé z těchto funkcí budou nakonec podporované pro hybridní nasazení pomocí Configuration Manageru. Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Role-based access control
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Intune apps
-->   

## <a name="week-of-july-31-2017"></a>Týden od 31. července 2017

### <a name="device-enrollment"></a>Registrace zařízení  

#### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Omezení registrace zařízení s Androidem a iOSem podle verze operačního systému  <!--- 1333256,  1245463 --->
Intune nyní podporuje omezení registrace iOSu a Androidu podle čísla verze operačního systému. V části **Omezení typu zařízení** teď správce IT může nastavit konfiguraci platformy tak, aby se registrace omezovala na rozsah mezi minimální a maximální hodnotou verze operačního systému. Verze operačního systému Android je nutné zadávat ve formátu Hlavní.Podverze.Sestavení.Revize, kde Podverze, Sestavení a Revize jsou nepovinné hodnoty. Verze iOS je nutné zadávat ve formátu Hlavní.Podverze.Sestavení, kde Podverze a Sestavení jsou nepovinné hodnoty. Přečtěte si další informace o [omezení registrace zařízení](enrollment-restrictions-set.md).

>[!NOTE]
>Neomezuje registrace prostřednictvím registračních programů Apple nebo nástroje Apple Configurator.

#### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Omezení registrace zařízení v osobním vlastnictví se systémem Android, iOS a macOS  <!--- 1333272,  1333275, 1245709 --->
Intune může omezit registrace osobních zařízení vytvořením seznamu povolených kódů IMEI podnikových zařízení. Intune teď tuto funkci rozšířil na iOS, Android a macOS na základě sériových čísel zařízení. Nahráním sériových čísel do Intune můžete zařízení předem deklarovat jako majetek společnosti. Pomocí omezení registrace můžete blokovat zařízení v osobním vlastnictví (BYOD) a umožnit registraci pouze zařízením ve vlastnictví společnosti. Přečtěte si další informace o [omezení registrace zařízení](enrollment-restrictions-set.md).

Pokud chcete importovat sériová čísla, přejděte na **Registrace zařízení** > **Identifikátory podnikových zařízení**, klikněte na **Přidat** a potom nahrajte soubor CSV (žádné záhlaví a dva odstavce pro sériová čísla a podrobnosti jako čísla IMEI).  Pokud chcete omezit zařízení v osobním vlastnictví, přejděte na **Registrace zařízení** > **Omezení registrace**. V části **Omezení typů zařízení** vyberte **Výchozí** a potom vyberte **Konfigurace platformy**. Zařízení se systémem iOS, Android a macOS v osobním vlastnictví můžete **povolit** nebo **zakázat**. 


### <a name="device-management"></a>Správa zařízení   

#### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nová akce zařízení, která zařízení donutí provést synchronizaci s Intune <!-- 711369 -->
V této verzi jsme přidali novou akci zařízení, která vybrané zařízení donutí se okamžitě ohlásit ve službě Intune. Jakmile se zařízení ohlásí, začne okamžitě přijímat veškeré čekající akce nebo zásady, které mu byly přiřazeny.  Tato akce vám může pomoct okamžitě ověřit přiřazené zásady nebo s těmito zásadami vyřešit potíže, aniž byste čekali na další naplánované ohlášení.
Podrobnosti najdete v části [Synchronizace zařízení](device-sync.md).

#### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Donucení zařízení s iOSem, která jsou pod dohledem, aby automaticky instalovaly nejnovější dostupnou aktualizaci softwaru <!-- 777100 -->
V pracovním prostoru aktualizací softwaru jsou dostupné nové zásady, které donutí zařízení s iOSem, která jsou pod dohledem, automaticky instalovat nejnovější dostupnou aktualizaci softwaru. Podrobnosti najdete v článku [Konfigurace zásad aktualizací pro iOS](/intune/software-updates-ios).


#### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile – Nový partner ochrany před mobilními hrozbami  <!-- 954651, 1172027 -->
Přístup mobilních zařízení k podnikovým prostředkům můžete regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Check Point SandBlast Mobile. Jedná se o řešení ochrany před mobilními hrozbami integrované ve službě Microsoft Intune.

##### <a name="how-integration-with-intune-works"></a>Jak integrace se službou Intune funguje?
Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých služba Check Point SandBlast Mobile běží. Na základě posouzení rizik aplikací Check Point SandBlast Mobile, které umožňují zásady dodržování předpisů v Intune, můžete nakonfigurovat zásady podmíněného přístupu EMS. Přístup k podnikovým prostředkům ze zařízení nesplňujících požadavky můžete na základě zjištěných hrozeb povolit nebo zakázat.


### <a name="app-management"></a>Správa aplikací

#### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Nasazení aplikace jako dostupné v Microsoft Storu pro firmy <!-- 748101 -->
V této verzi teď správci můžou Microsoft Store pro firmy přiřadit jako dostupný. Pokud to udělají, koncoví uživatelé si můžou aplikaci nainstalovat z aplikace nebo webu Portál společnosti, aniž by byli přesměrováni do Microsoft Storu.


### <a name="intune-apps"></a>Aplikace Intune  

#### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Aktualizace uživatelského rozhraní webu Portál společnosti <!--1313244 part 1-->
Provedli jsme několik aktualizací uživatelského rozhraní [webu Portál společnosti](https://portal.manage.microsoft.com) k vylepšení prostředí pro koncové uživatele.

- __Vylepšení dlaždic aplikací__: Ikony aplikací se teď budou zobrazovat s automaticky generovaným pozadím na základě převládající barvy ikony (pokud se dá zjistit). Tam, kde se toto pozadí použije, nahradí šedé ohraničení, které bylo dříve vidět na dlaždicích aplikací.

    Web Portál společnosti bude v nadcházející verzi zobrazovat velké ikony, kdykoli to bude možné. Doporučujeme, aby správci IT publikovali aplikace pomocí ikon s vysokým rozlišením a minimální velikostí 120 x 120 pixelů. 

- __Změny v navigaci__: Položky navigačního panelu se přesunuly do „hamburgerové“ nabídky vlevo nahoře. Stránka Kategorie byla odebrána. Uživatelé teď můžou filtrovat obsah podle kategorií během procházení.

- __Aktualizace Vybraných aplikací__: Přidali jsme na web vyhrazenou stránku, kde můžou uživatelé procházet aplikace, které jste speciálně vybrali, a upravili jsme uživatelské rozhraní sekce Vybrané na domovské stránce.

#### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Podpora iBooks pro web Portál společnosti <!--1231841-->
Na web Portál společnosti jsme přidali speciálně určenou stránku, která uživatelům umožňuje procházet a stahovat knihy iBooks. 

### <a name="reporting"></a>Generování sestav

#### <a name="intune-data-warehouse-public-preview"></a>Datový sklad Intune (Public Preview)

Datový sklad Intune denně vzorkuje data, aby mohl poskytovat historický přehled vašeho tenanta. K datům můžete mít získat přístup pomocí souboru Power BI (soubor PBIX) a odkazu OData, který je kompatibilní s celou řadu analytických nástrojů, nebo prostřednictvím interakce s rozhraním REST API. Další informace najdete v tématu [Použití Datového skladu Intune](reports-nav-create-intune-reports.md).


## <a name="week-of-july-23rd-2017"></a>Týden od 23. července 2017

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Světlé a tmavé režimy dostupné pro aplikaci Portál společnosti pro Windows 10 <!---676547--->
Koncoví uživatelé budou mít možnost přizpůsobit barevný režim aplikace Portál společnosti pro Windows 10. Uživatel může změny provádět v sekci Nastavení aplikace Portál společnosti. Změna se zobrazí, jakmile uživatel aplikaci restartuje. Pro Windows 10 verze 1607 a novější se režim aplikace nastaví podle výchozího nastavení systému. Pro Windows 10 verze 1511 a starší se režim aplikace nastaví do světlého režimu.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Možnost pro koncové uživatele v aplikaci Portál společnosti pro Windows 10 označit svou skupinu zařízení <!---807046-->
Koncoví uživatelé teď můžou vybrat, do které skupiny jejich zařízení patří, když ho označí přímo v aplikaci Portál společnosti pro Windows 10.




## <a name="notices"></a>Sdělení

### <a name="ip-addresses-for-intune-updated----1175274---"></a>IP adresy pro Intune aktualizovány <!-- 1175274 -->
K dispozici je [aktualizovaný seznam názvů DNS a IP adres](/intune/network-bandwidth-use) pro nastavení proxy serveru brány firewall.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Používání Azure Active Directory pro podmíněný přístup <!-- 967947 -->
Podmíněný přístup je k dispozici v sekci Azure Active Directory konzoly Azure a poskytuje výkonnější a flexibilnější rozhraní pro nastavení zásad pro cloudové aplikace jako Office 365 Exchange Online a SharePoint Online.  Místo klasické konzoly Intune použijte ke konfiguraci nastavení zásad okno **Podmíněný přístup v Azure Active Directory**. Existující zásady v klasické konzole Intune se musí v konzole Azure znovu vytvořit. Další informace najdete v článku o [vytvoření zásad podmíněného přístupu Azure AD](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Přímý přístup ke scénářům registrace Apple <!--951869-->
U účtů Intune vytvořených po lednu 2017 umožňuje Intune přímý přístup ke scénářům registrace Apple pomocí úlohy Registrovat zařízení na portálu Azure Portal. Náhled na registraci Apple byl předtím přístupný přes odkazy na portálu klasické služby Intune. Zpřístupnění těchto funkcí v Azure vyžaduje u účtů Intune vytvořených před lednem 2017 jednorázovou migraci. Plán této migrace zatím nebyl oznámen, podrobnosti ale budou zpřístupněny co nejdříve. Pokud váš existující účet nemá k portálu Azure Portal přístup, k otestování tohoto nového prostředí důrazně doporučujeme vytvořit zkušební účet.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Nahrazení rolí správy na portálu Azure Portal
Existující role pro správu mobilních aplikací (MAM) (Přispěvatel, Vlastník a Jen pro čtení) používané v klasickém portálu Intune (Silverlight) byly na portálu Azure Portal pro Intune nahrazeny celou řadou nových možností řízení přístupu na základě role (RBAC). Jakmile migrujete na portál Azure Portal, bude potřeba, abyste svým správcům přiřadili tyto nové role správy. Další informace o RBAC a nových rolích najdete v článku [Řízení přístupu na základě role pro Microsoft Intune](/intune/role-based-access-control).



## <a name="whats-coming"></a>Co připravujeme

### <a name="end-of-support-for-ios-80----1164477---"></a>Konec podpory pro systém iOS 8.0 <!---1164477--->
Spravované aplikace a aplikace Portál společnosti pro iOS budou pro přístup k firemním prostředkům vyžadovat operační systém iOS 9.0 nebo novější. Zařízení, která nebudou do tohoto září aktualizována, již nebudou mít k těmto aplikacím nebo k Portálu společnosti přístup. 

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>Aktualizace uživatelského rozhraní webu Portál společnosti <!--1313244 part 2-->
__Aktualizace vybraných aplikací__  
Přidali jsme na web vyhrazenou stránku, kde můžou uživatelé procházet aplikace, které jste speciálně vybrali, a upravili jsme uživatelské rozhraní sekce Vybrané na domovské stránce. Tyto změny si můžete prohlédnout na stránce s [novinkami v uživatelském rozhraní aplikace](whats-new-app-ui.md).


### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Konec podpory pro Android verze 4.3 a nižší <!---1171127, 1326920 --->
Spravované aplikace a aplikace Portál společnosti pro Android budou pro přístup k firemním prostředkům vyžadovat operační systém Android 4.4 nebo novější. Zařízení, která nebudou do začátku října aktualizována, již nebudou mít k těmto aplikacím nebo k Portálu společnosti přístup. Od prosince budou všechna zaregistrovaná zařízení vyřazena, čímž dojde ke ztrátě přístupu k firemním prostředkům. Pokud používáte zásady ochrany aplikací bez správy mobilních zařízení MDM, aplikace nebudou získávat aktualizace a kvalita jejich činnosti bude časem upadat.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-ended-july-11-2017"></a>Připomenutí podpory platformy: hlavní fáze technické podpory pro Windows Phone 8.1 skončila 11. července 2017
<!-- 1327781 -->
11. července 2017 skončila hlavní fáze technické podpory pro Windows Phone 8.1. Podporu počítačů s Windows 8.1 to neovlivní.

Na žádné zařízení s Windows Phone 8.1, které je spravováno službou Intune, to nebude mít okamžitý vliv. Zaregistrovaná zařízení budou nadále fungovat a všechny zásady, konfigurace a aplikace také. Všimněte si, že pro aplikaci Portál společnosti pro Windows Phone 8.1 ani pro platformu Windows Phone 8.1 v rámci služby Intune neexistují žádná cílená vylepšení.

Doporučujeme vám, abyste při nejbližší příležitosti způsobilá zařízení s Windows Phone 8.1 upgradovali na Windows 10 Mobile. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Změny v podpoře pro aplikaci Portál společnosti Intune pro iOS  <!-- 1164474  -->
Již brzy bude dostupná nová verze aplikace Portál společnosti Microsoft Intune pro iOS, která bude podporovat pouze zařízení se systémem iOS 9.0 nebo novějším. Verze podporující iOS 8 bude ještě na krátkou dobu k dispozici. Upozorňujeme vás, že pokud také používáte iOS aplikace s podporou MAM, podporujeme je pouze u verze iOS 9.0 a novější. Proto zajistěte, aby vaši koncoví uživatelé provedli aktualizaci na nejnovější verzi operačního systému. 

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Přestože nemáme konkrétní datum, dáváme vám to vědět předem, abyste měli čas si to naplánovat. Zajistěte, aby vaši uživatelé měli iOS 9.0 nebo novější, a jakmile vyjde nová verze aplikace Portál společnosti, požádejte své koncové uživatele, aby tuto aplikaci aktualizovali.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Upozorněte své uživatele, že aby mohli naplno využívat nových funkcí služby Intune, musí si iOS aktualizovat na verzi 9.0 nebo novější.  Vyzvěte uživatele, aby si nainstalovali novou verzi aplikace Portál společnosti a mohli využívat nově nabízených funkcí.

Na portálu Azure Portal přejděte do služby Intune, zobrazte si Zařízení > Všechna zařízení a vyfiltrujte si je podle verze systému iOS, abyste viděli všechna zařízení s operačními systémy staršími než iOS 9.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Plánovaná změna: Intune mění způsob fungování portálu Intune Partner Portal<!-- 1050016 -->
Počínaje aktualizací služby v polovině května 2017 odstraníme stránku Intune Partner z manage.microsoft.com.  

Pokud jste partnerským správcem, nebude už moct stránku Intune Partner zobrazit a provádět z ní jménem vašich zákazníků kroky, ale místo toho se budete muset přihlásit k jednomu ze dvou dalších partnerských portálů Microsoftu.

K účtům zákazníků, které spravujete, se budete moct přihlásit z [Partnerského centra Microsoftu](https://partnercenter.microsoft.com/) a [Centra pro partnerskou správu Office 365](https://portal.office.com/). V budoucnu jako partneři prosím ke správě svých zákazníků používejte jeden z těchto webů.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple bude vyžadovat aktualizace ATS (Application Transport Security) <!--748318-->
Apple oznámil, že začne vynucovat specifické požadavky na ATS (Application Transport Security). ATS se používá k vynucení vyššího zabezpečení veškeré komunikace aplikací přes protokol HTTPS. Tato změna ovlivní zákazníky Intune, kteří používají aplikace Portál společnosti pro iOS.

Prostřednictvím programu Apple TestFlight, který vynucuje nové požadavky na ATS, jsme zpřístupnili verzi aplikace Portál společnosti pro iOS. Pokud si ji chcete vyzkoušet a otestovat, jestli ATS dodržujete, napište nám na adresu <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> zprávu s vaším jménem a příjmením, e-mailovou adresou a názvem společnosti. Další podrobnosti najdete v [blogu podpory služby Intune](https://aka.ms/compportalats).

### <a name="see-also"></a>Viz taky
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co je nového v uživatelském rozhraní Portálu společnosti](whats-new-app-ui.md)
* [Novinky v předchozích měsících](whats-new-archive.md)
