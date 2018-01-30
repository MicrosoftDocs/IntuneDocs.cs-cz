---
title: "Novinky v Microsoft Intune za předchozí měsíce"
titlesuffix: Azure portal
description: "Zkontrolujte starší oznámení ze stránky novinek Intune"
keywords: 
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d6513b570851473651fbfa38dbb4dc1b6c91036
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Novinky v Microsoft Intune – předchozí měsíce

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="september-2017"></a>Září 2017

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Informování koncových uživatelů o tom, jaké informace o zařízení si můžou zobrazit v iOSu <!--739894-->

Na obrazovku Podrobnosti o zařízení v aplikaci Portál společnosti pro iOS jsme přidali **Typ vlastnictví**. Uživatelům to umožní zjistit další informace o ochraně osobních údajů přímo z této stránky z dokumentace Intune pro koncové uživatele. Tyto informace najdou také na obrazovce s informacemi o produktu.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Možnost pro koncové uživatele získat přístup k aplikaci Portál společnosti pro Android bez registrace <!---1169910--->

Koncoví uživatelé brzy nebudou muset svá zařízení registrovat, aby získali přístup k aplikaci Portál společnosti pro Android. Koncovým uživatelům v organizacích, které používají zásady ochrany aplikací, už nebudou při otevření aplikace Portál společnosti chodit výzvy k registraci jejich zařízení. Koncoví uživatelé budou také moct bez registrace zařízení z Portálu společnosti instalovat aplikace. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Srozumitelnější text v aplikaci Portál společnosti pro Android <!---1396349--->  

Proces registrace aplikace Portál společnosti pro Android byl zjednodušen novým textem, který koncovým uživatelům umožňuje jednodušší registraci. Pokud máte vlastní dokumentaci k registraci, měli byste ji aktualizovat, aby odrážela nové obrazovky. Ukázkové obrázky najdete na naší stránce [aktualizací uživatelského rozhraní aplikací Intune pro koncové uživatele](whats-new-app-ui.md#week-of-september-11-2017).

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Do zásad povolení Windows Information Protection byla přidána aplikace Portál společnosti pro Windows 10 <!-- 677129 -->

Aplikace Portál společnosti pro Windows 10 byla aktualizována o podporu WIP (Windows Information Protection). Tuto aplikaci lze přidat do zásad povolení WIP. Díky této změně se už tato aplikace nemusí přidávat do seznamu **výjimek**.


## <a name="august-2017"></a>Srpen 2017

### <a name="improvements-to-device-overview----1404453---"></a>Vylepšení přehledu zařízení <!-- 1404453 -->  
Ve vylepšeném přehledu zařízení se teď zobrazují registrovaná zařízení, jsou ale vyloučena zařízení spravovaná přes Exchange Active Sync. Zařízení Exchange ActiveSync nemají stejné možnosti správy jako registrovaná zařízení. Pokud chcete v Intune na Azure Portalu zjistit počet registrovaných zařízení a počet registrovaných zařízení podle platformy, přejděte na **Zařízení** > **Přehled**.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Vylepšení inventáře zařízení shromažďovaného službou Intune
<!-- 961134, 1104426, 1281327, 1333543 -->
V této verzi jsme udělali následující vylepšení inventarizačních informací shromažďovaných zařízeními, která spravujete:
 
-   Pro zařízení s Androidem teď můžete do inventáře zařízení přidat sloupec, ve kterém se zobrazuje nejnovější úroveň opravy jednotlivých zařízení. Tento údaj zobrazíte, když do seznamu zařízení přidáte sloupec **Úroveň opravy zabezpečení**.
-   Zobrazení zařízení teď můžete filtrovat podle data registrace zařízení. Můžete například zobrazit jen zařízení, která byla zaregistrována po zadaném datu.
-   Vylepšili jsme filtr, který se používá u údaje **Datum posledního ohlášení**.
-   V seznamu zařízení si teď u zařízení ve vlastnictví firmy můžete zobrazit telefonní číslo.
Pomocí podokna filtru můžete navíc vyhledat zařízení podle telefonního čísla.
 
Další podrobnosti o inventáři zařízení najdete v článku [Jak zobrazit inventář zařízení spravovaných přes Intune](device-inventory.md).

### <a name="conditional-access-support-for-macos-devices"></a>Podpora podmíněného přístupu pro zařízení s macOS 
<!-- 720172 -->
Teď můžete nastavit zásady podmíněného přístupu, které po zařízeních Mac vyžadují registraci v Intune a soulad se zásadami dodržování předpisů pro zařízení. Uživatelé si mohou například stáhnout aplikaci Portál společnosti Intune pro macOS a zaregistrovat svá zařízení Mac ve službě Intune. Intune prostřednictvím požadavků, jako je kód PIN, šifrování, verze operačního systému a integrita systému, vyhodnotí, zda zařízení Mac předpisy dodržuje nebo ne.

- Přečtěte si další informace o [podpoře podmíněného přístupu pro zařízení s macOS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>Aplikace Portál společnosti pro macOS ve verzi Public Preview <!---1484796--->
Aplikace Portál společnosti pro macOS je teď k dispozici jako součást verze Public Preview pro podmíněný přístup v Enterprise Mobility + Security. Tato verze podporuje macOS 10.11 a novější. Získáte ji na [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


### <a name="new-device-restriction-settings-for-windows-10"></a>Nová nastavení omezení pro zařízení s Windows 10    
<!--1063965, 1308850  -->
V této verzi jsme přidali nová nastavení pro [profil omezení zařízení s Windows 10](/intune/device-restrictions-windows-10) v následujících kategoriích:

-   Filtr SmartScreen v programu Windows Defender
-   App Store

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Aktualizace profilu zařízení ochrany koncových bodů Windows 10 o nastavení BitLockeru
<!--1459533 -->    
V této verzi jsme následujícím způsobem vylepšili nastavení BitLockeru v profilu zařízení ochrany koncových bodů Windows 10:
 
Když jste dříve v **Nastavení BitLockeru pro jednotky s operačním systémem** vybrali u nastavení **BitLocker s nekompatibilním čipem TPM** možnost **Blokovat**, ve skutečnosti se BitLocker povolil. Teď je to opravené a při výběru této možnosti se BitLocker zablokuje.
V **Nastavení BitLockeru pro jednotky s operačním systémem** teď můžete pomocí nastavení **Agent obnovení dat založený na certifikátech** explicitně zablokovat agenta obnovení dat založeného na certifikátech. Standardně je ale tento agent povolený.
V **Nastavení BitLockeru pro jednotky s operačním systémem** teď můžete pomocí nastavení **Agent obnovení dat** explicitně zablokovat agenta obnovení dat.
Další informace najdete v tématu o [nastavení služby Endpoint Protection pro Windows 10 a novější](endpoint-protection-windows-10.md).


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nové prostředí po přihlášení pro uživatele Portálu společnosti pro Android a uživatele zásad ochrany aplikací <!-- 621669 -->
Koncoví uživatelé teď můžou pomocí aplikace Portál společnosti pro Android procházet aplikace, spravovat zařízení a zobrazit kontakt na IT oddělení, aniž by své zařízení s Androidem zaregistrovali. Pokud už koncový uživatel používá aplikaci chráněnou zásadami Intune App Protection a spustí Portál společnosti pro Android, už se mu navíc nezobrazí výzva k registraci zařízení.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nové nastavení v aplikaci Portál společnosti pro Android k přepnutí optimalizace baterie <!--1405990-->
Stránka **Nastavení** v aplikaci Portál společnosti pro Android obsahuje nové nastavení, které uživatelům umožní snadno vypnout optimalizaci baterie pro aplikace Portál společnosti a Microsoft Authenticator. Název aplikace uvedený v nastavení se liší v závislosti na tom, která aplikace spravuje pracovní účet. Doporučujeme, aby uživatelé optimalizaci baterie vypnuli kvůli lepšímu výkonu pracovních aplikací, které synchronizují e-maily a data. 

### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>Podpora více identit ve OneNotu pro iOS      <!-- 1234281 -->
Koncoví uživatelé teď můžou v Microsoft OneNotu pro iOS používat různé účty (pracovní a osobní). Na firemní data v pracovních poznámkových blocích lze uplatnit zásady ochrany aplikací, aniž to ovlivní osobní poznámkové bloky. Pomocí zásad můžete například uživateli povolit hledání informací v pracovních poznámkových blocích, ale zabránit v kopírování a vkládání firemních dat z pracovních do osobních poznámkových bloků.
 
- Přečtěte si další informace o aplikacích, které podporují [ochranu aplikací a více identit](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) s Intune.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Nová nastavení, která povolí nebo blokují aplikace na zařízeních se zabezpečením Samsung Knox Standard
<!-- 1305423 822899-->  
V této verzi přidáváme nová [nastavení omezení zařízení](device-restrictions-android.md), která vám umožní zadat následující seznamy aplikací:
 
- Aplikace, které mají uživatelé dovoleno instalovat.
- Aplikace, které mají uživatelé zakázáno spouštět.
- Aplikace, které jsou před uživatelem zařízení skryté.
 
Aplikaci můžete zadat pomocí adresy URL, názvu balíčku nebo ze seznamu spravovaných aplikací.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Odkaz na nové uživatelské rozhraní zásad podmíněného přístupu na základě aplikací Azure AD z Intune
<!-- 1016201 -->
Správci IT teď můžou nastavit podmíněné zásady na základě aplikací prostřednictvím nového uživatelského rozhraní zásad podmíněného přístupu v úloze Azure AD. Podmíněný přístup na základě aplikací, který je v části Intune App Protection na portálu Azure Portal, prozatím zůstane a bude se vynucovat souběžně. Užitečný odkaz na nové uživatelské rozhraní zásad podmíněného přístup obsahuje také úloha Intune.

- Přečtěte si další informace o [podmíněném přístupu na základě aplikací v Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).



## <a name="july-2017"></a>Červenec 2017

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Omezení registrace zařízení s Androidem a iOSem podle verze operačního systému  <!--- 1333256,  1245463 --->
Intune nyní podporuje omezení registrace iOSu a Androidu podle čísla verze operačního systému. V části **Omezení typu zařízení** teď správce IT může nastavit konfiguraci platformy tak, aby se registrace omezovala na rozsah mezi minimální a maximální hodnotou verze operačního systému. Verze operačního systému Android je nutné zadávat ve formátu Hlavní.Podverze.Sestavení.Revize, kde Podverze, Sestavení a Revize jsou nepovinné hodnoty. Verze iOS je nutné zadávat ve formátu Hlavní.Podverze.Sestavení, kde Podverze a Sestavení jsou nepovinné hodnoty. Přečtěte si další informace o [omezení registrace zařízení](enrollment-restrictions-set.md).

>[!NOTE]
>Neomezuje registrace prostřednictvím registračních programů Apple nebo nástroje Apple Configurator.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Omezení registrace zařízení v osobním vlastnictví se systémem Android, iOS a macOS  <!--- 1333272,  1333275, 1245709 --->
Intune může omezit registraci osobních zařízení tím, že kódy IMEI podnikových zařízení umístí do seznamu povolených. Intune teď tuto funkci rozšířil na iOS, Android a macOS na základě sériových čísel zařízení. Nahráním sériových čísel do Intune můžete zařízení předem deklarovat jako majetek společnosti. Pomocí omezení registrace můžete blokovat zařízení v osobním vlastnictví (BYOD) a umožnit registraci pouze zařízením ve vlastnictví společnosti. Přečtěte si další informace o [omezení registrace zařízení](enrollment-restrictions-set.md).

Pokud chcete importovat sériová čísla, přejděte na **Registrace zařízení** > **Identifikátory podnikových zařízení**, klikněte na **Přidat** a potom nahrajte soubor CSV (žádné záhlaví a dva odstavce pro sériová čísla a podrobnosti jako čísla IMEI).  Pokud chcete omezit zařízení v osobním vlastnictví, přejděte na **Registrace zařízení** > **Omezení registrace**. V části **Omezení typů zařízení** vyberte **Výchozí** a potom vyberte **Konfigurace platformy**. Zařízení se systémem iOS, Android a macOS v osobním vlastnictví můžete **povolit** nebo **zakázat**. 


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nová akce zařízení, která zařízení donutí provést synchronizaci s Intune <!-- 711369 -->
V této verzi jsme přidali novou akci zařízení, která vybrané zařízení donutí se okamžitě ohlásit ve službě Intune. Jakmile se zařízení ohlásí, začne okamžitě přijímat veškeré čekající akce nebo zásady, které mu byly přiřazeny.  Tato akce vám může pomoct okamžitě ověřit přiřazené zásady nebo s těmito zásadami vyřešit potíže, aniž byste čekali na další naplánované ohlášení.
Podrobnosti najdete v části [Synchronizace zařízení](device-sync.md).

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Donucení zařízení s iOSem, která jsou pod dohledem, aby automaticky instalovaly nejnovější dostupnou aktualizaci softwaru <!-- 777100 -->
V pracovním prostoru aktualizací softwaru jsou dostupné nové zásady, které donutí zařízení s iOSem, která jsou pod dohledem, automaticky instalovat nejnovější dostupnou aktualizaci softwaru. Podrobnosti najdete v článku [Konfigurace zásad aktualizací pro iOS](/intune/software-updates-ios).

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile – Nový partner ochrany před mobilními hrozbami  <!-- 954651, 1172027 -->
Přístup mobilních zařízení k podnikovým prostředkům můžete regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Check Point SandBlast Mobile. Jedná se o řešení ochrany před mobilními hrozbami integrované ve službě Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak integrace se službou Intune funguje?
Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých služba Check Point SandBlast Mobile běží. Na základě posouzení rizik aplikací Check Point SandBlast Mobile, které umožňují zásady dodržování předpisů v Intune, můžete nakonfigurovat zásady podmíněného přístupu EMS. Přístup k podnikovým prostředkům ze zařízení nesplňujících požadavky můžete na základě zjištěných hrozeb povolit nebo zakázat.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Nasazení aplikace jako dostupné v Microsoft Storu pro firmy <!-- 748101 -->
V této verzi teď správci můžou Microsoft Store pro firmy přiřadit jako dostupný. Pokud to udělají, koncoví uživatelé si můžou aplikaci nainstalovat z aplikace nebo webu Portál společnosti, aniž by byli přesměrováni do Microsoft Storu.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Aktualizace uživatelského rozhraní webu Portál společnosti <!--1313244 part 1-->
Provedli jsme několik aktualizací uživatelského rozhraní [webu Portál společnosti](https://portal.manage.microsoft.com) k vylepšení prostředí pro koncové uživatele.

- __Vylepšení dlaždic aplikací__: Ikony aplikací se teď budou zobrazovat s automaticky generovaným pozadím na základě převládající barvy ikony (pokud se dá zjistit). Tam, kde se toto pozadí použije, nahradí šedé ohraničení, které bylo dříve vidět na dlaždicích aplikací.

    Web Portál společnosti bude v nadcházející verzi zobrazovat velké ikony, kdykoli to bude možné. Doporučujeme, aby správci IT publikovali aplikace pomocí ikon s vysokým rozlišením a minimální velikostí 120 x 120 pixelů. 

- __Změny v navigaci__: Položky navigačního panelu se přesunuly do „hamburgerové“ nabídky vlevo nahoře. Stránka Kategorie byla odebrána. Uživatelé teď můžou filtrovat obsah podle kategorií během procházení.

- __Aktualizace Vybraných aplikací__: Přidali jsme na web vyhrazenou stránku, kde můžou uživatelé procházet aplikace, které jste speciálně vybrali, a upravili jsme uživatelské rozhraní sekce Vybrané na domovské stránce.

### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Podpora iBooks pro web Portál společnosti <!--1231841-->
Na web Portál společnosti jsme přidali speciálně určenou stránku, která uživatelům umožňuje procházet a stahovat knihy iBooks. 


### <a name="additional-help-desk-troubleshooting-details------applies-to-1263399-1326964-1341642----"></a>Další podrobnosti o řešení problémů pro helpdesk <!---  Applies to 1263399, 1326964, 1341642 --->
Intune má aktualizované zobrazení pro řešení problémů, které je doplněné k informacím poskytovaným správcům a pracovníkům helpdesku. Teď si můžete zobrazit tabulku **Přiřazení**, ve které jsou shrnuta všechna přiřazení uživatele na základě členství ve skupinách. Tento seznam obsahuje:
- Mobilní aplikace
- Zásady dodržování předpisů
- Konfigurační profily
 
Tabulka **Zařízení** teď navíc obsahuje sloupce **Typ připojení ke službě Azure AD** a **Vyhovuje Azure AD**. Další informace najdete v článku [Pomoc uživatelům s řešením problémů](help-desk-operators.md).



### <a name="intune-data-warehouse-public-preview"></a>Datový sklad Intune (Public Preview)
Datový sklad Intune denně vzorkuje data, aby mohl poskytovat historický přehled vašeho tenanta. K datům můžete mít získat přístup pomocí souboru Power BI (soubor PBIX) a odkazu OData, který je kompatibilní s celou řadu analytických nástrojů, nebo prostřednictvím interakce s rozhraním REST API. Další informace najdete v tématu [Použití Datového skladu Intune](reports-nav-create-intune-reports.md).


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Světlé a tmavé režimy dostupné pro aplikaci Portál společnosti pro Windows 10 <!---676547--->
Koncoví uživatelé budou mít možnost přizpůsobit barevný režim aplikace Portál společnosti pro Windows 10. Uživatel může změny provádět v sekci Nastavení aplikace Portál společnosti. Změna se zobrazí, jakmile uživatel aplikaci restartuje. Pro Windows 10 verze 1607 a novější se režim aplikace nastaví podle výchozího nastavení systému. Pro Windows 10 verze 1511 a starší se režim aplikace nastaví do světlého režimu.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Možnost pro koncové uživatele v aplikaci Portál společnosti pro Windows 10 označit svou skupinu zařízení <!---807046-->
Koncoví uživatelé teď můžou vybrat, do které skupiny jejich zařízení patří, když ho označí přímo v aplikaci Portál společnosti pro Windows 10.



## <a name="june-2017"></a>Červen 2017

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Přístup pro správu na základě nové role pro správce Intune   <!-- 1099990 -->  
Přidáváme novou roli správce podmíněného přístupu, která umožňuje zobrazit, vytvořit, upravit a odstranit zásady podmíněného přístupu Azure AD. Dříve měli toto oprávnění jenom globální správci a správci zabezpečení. Oprávnění této role se může udělit správcům Intune, kteří pak mají přístup k zásadám podmíněného přístupu.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Označení zařízení vlastněných podnikem pomocí sériového čísla <!-- 1215070 -->  
Intune nyní podporuje ukládání sériových čísel v systémech iOS, macOS a Android jako identifikátorů podnikových zařízení. Sériová čísla nemůžete používat k blokování registrace osobních zařízení, protože sériová čísla se při registraci neověřují. Blokování osobních zařízení podle sériového čísla bude dostupné v blízké budoucnosti.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>Nové vzdálené akce pro zařízení s iOSem <!-- 854689 -->
V této verzi jsme přidali dvě nové akce vzdáleného zařízení pro sdílené iPady, které spravují aplikaci Apple Classroom:

-   [Odhlásit aktuálního uživatele](device-logout-user.md) – odhlásí aktuálního uživatele na vybraném zařízení s iOSem.
-   [Odebrat uživatele](device-remove-user.md) – odstraní vybraného uživatele z místní mezipaměti zařízení s iOSem.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Podpora pro sdílené iPady s aplikací Classroom pro iOS<!-- 1044681 -->
V této verzi jsme rozšířili podporu správy aplikace Classroom pro iOS tak, aby zahrnovala studenty, kteří se přihlásí do sdílených iPadů pomocí svých spravovaných Apple ID.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Změny integrovaných aplikací Intune <!-- 1332306 -->
Dříve služba Intune obsahovala řadu integrovaných aplikací, které jste mohli rychle přiřadit. Na základě vaší zpětné vazby jsme tento seznam odebrali a integrované aplikace už neuvidíte.
Pokud jste už ale nějaké integrované aplikace přiřadili, budou se v seznamu aplikací dál zobrazovat. Tyto aplikace můžete dál přiřazovat podle potřeby.
V pozdější verzi plánujeme přidat jednodušší způsob výběru a přiřazování integrovaných aplikací z Azure Portalu.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Snadnější instalace aplikací Office 365 <!--- 1121362 --->
Nový typ aplikace **Office 365 ProPlus** vám usnadní přiřazování aplikací Office 365 ProPlus 2016 na vámi spravovaná zařízení, na kterých běží nejnovější verze Windows 10. Pokud vlastníte příslušné licence, můžete si také nainstalovat Microsoft Project a Microsoft Visio. Požadované aplikace jsou spojeny dohromady a v seznamu aplikací v konzole Intune se zobrazují jako jedna aplikace.
Další informace najdete v tématu [Jak přidat aplikace Office 365 pro Windows 10](apps-add-office365.md).


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>Podpora pro offline aplikace z Microsoft Storu pro firmy <!--- 777044 --->
Aplikace Offline zakoupené v Microsoft Storu pro firmy se teď budou synchronizovat na Azure Portal. Tyto aplikace můžete nasadit pro skupiny zařízení nebo skupiny uživatelů. Offline aplikace bude instalovat služba Intune, nikoli Store.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Aplikace Microsoft Teams je nyní součástí seznamu schválených aplikací pro zásady podmíněného přístupu na podle aplikací   <!-- 1257019 -->
Aplikace Microsoft Teams pro iOS a Android je nyní součástí schválených aplikací pro zásady podmíněného přístupu podle aplikací pro Exchange a SharePoint Online. Aplikaci lze nakonfigurovat prostřednictvím okna Intune App Protection na portálu Azure Portal pro všechny tenanty aktuálně používající podmíněný přístup podle aplikací.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Spravovaný prohlížeč (Managed Browser) a integrace proxy aplikace <!-- 1287310 -->
Spravovaný prohlížeč Intune Managed Browser je nyní možné integrovat do služby Azure AD Application Proxy, což umožní uživatelům získat přístup k interním webům, i když pracují vzdáleně. Uživatelé prohlížeče jako obvykle zadají adresu URL webu a Managed Browser požadavek prostřednictvím webové brány proxy aplikace přesměruje. Další informace najdete v tématu [Správa přístupu k internetu pomocí zásad spravovaného prohlížeče](app-configuration-managed-browser.md).

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Nová nastavení konfigurace aplikace pro Intune Managed Browser <!-- 682951 -->
V této verzi jsme pro aplikaci Intune Managed Browser pro iOS a Android přidali další konfigurace. Pomocí zásad konfigurace aplikace nyní můžete prohlížeči nakonfigurovat výchozí domovskou stránku a záložky.
Další informace najdete v tématu [Správa přístupu k internetu pomocí zásad spravovaného prohlížeče](app-configuration-managed-browser.md).

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Nastavení nástroje BitLocker pro Windows 10  <!-- 951707 -->
Nyní můžete nastavení nástroje BitLocker konfigurovat pro zařízení s Windows 10 pomocí nového profilu zařízení Intune. Například můžete vyžadovat, aby se zařízení šifrovala, a také nakonfigurovat další nastavení, která se použijí při zapnutí nástroje BitLocker.
Další informace najdete v tématu o [nastavení služby Endpoint Protection pro Windows 10 a novější](endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Nová nastavení pro profil omezení zařízení s Windows 10 <!--- 978527,  978550, 978569, 1050031, 1058611,  --->
V této verzi jsme přidali nová nastavení pro profil omezení zařízení s Windows 10 v následujících kategoriích:

-  Windows Defender
-  Mobilní síť a připojení
-  Prostředí zamknuté obrazovky
-  Ochrana osobních údajů
-  Hledat
-  Windows Spotlight
-  Prohlížeč Edge

Další informace o nastavení Windows 10 najdete v tématu [Nastavení omezení pro zařízení Windows 10 a novější](device-restrictions-windows-10.md).


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Aplikace Portál společnosti pro Android má teď novou činnost koncového uživatele pro zásady ochrany aplikací <!--1305217-->
Na základě zpětné vazby od zákazníků jsme aplikaci Portál společnosti pro Android upravili tak, aby zobrazovala tlačítko **Přístup k obsahu společnosti**. Naším záměrem je předejít zbytečné registraci koncových uživatelů, když pouze potřebují přístup k aplikacím s podporou zásad ochrany aplikací – funkce správy mobilních aplikací Intune. Tyto změny najdete na stránce s [novinkami v uživatelském rozhraní aplikace](whats-new-app-ui.md).

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nová akce nabídky ke snadnému odebrání Portálu společnosti <!--1164569-->
Na základě zpětné vazby od uživatelů jsme do aplikace Portál společnosti pro Android přidali novou akci nabídky k zahájení odebrání Portálu společnosti ze zařízení. Tato akce odebere zařízení ze správy Intune, aby uživatel mohl aplikaci ze zařízení odebrat. Tyto změny najdete na stránce [novinek v uživatelském rozhraní aplikace](whats-new-app-ui.md) a v [dokumentaci pro koncové uživatele Androidu](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Vylepšení synchronizace aplikace s Windows 10 Creators Update <!--676505-->
Aplikace Portál společnosti pro Windows 10 teď automaticky zahájí synchronizaci pro požadavky na instalaci zařízení s Windows 10 Creators Update (verze 1703). Omezí se tím potíže s pozastavením instalací aplikace ve stavu čekající synchronizace. Uživatelé navíc budou moct synchronizaci zahájit ručně uvnitř aplikace. Tyto změny najdete na stránce s [novinkami v uživatelském rozhraní aplikace](whats-new-app-ui.md).

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nové prostředí s asistencí pro portál společnosti s Windows 10 <!---1058938--->
Aplikace Portál společnosti pro Windows 10 bude obsahovat návod s pokyny Intune pro zařízení, která nejsou identifikovaná nebo zaregistrovaná. Nové prostředí obsahuje podrobné pokyny, které provedou uživatele registrací do Azure Active Directory (která je nutná pro funkce podmíněného přístupu), a zápis do MDM (který je nutný pro funkce správy zařízení). Prostředí s asistencí bude přístupné z domovské stránky portálu společnosti. Uživatelé můžou aplikaci dál používat, i když registraci a zápis neprovedou, ale budou mít k dispozici omezené funkce.

Tato aktualizace se zobrazí pouze na zařízení s Windows 10 Anniversary Update (build 1607) a novějšími verzemi. Tyto změny najdete na stránce s [novinkami v uživatelském rozhraní aplikace](whats-new-app-ui.md).


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Konzoly správců Microsoft Intune a podmíněného přístupu jsou obecně dostupné
Oznamujeme obecnou dostupnost nové služby Intune v konzole správce Azure Portalu a v konzole správce podmíněného přístupu. Prostřednictvím Intune na Azure Portalu teď můžete spravovat všechny funkce Intune MAM a MDM v jednom sjednoceném prostředí pro správce a využívat seskupování a cílení služby Azure AD. Podmíněný přístup v Azure přináší bohaté možnosti v rámci Azure AD a Intune společně v jedné sjednocené konzole. A z prostředí pro správu vám přechod na platformu Azure umožňuje používat moderní prohlížeče.

Intune se teď na Azure Portalu na adrese portal.azure.com zobrazuje bez popisku **Preview**.

Pokud jste v centru zpráv nedostali některou z řady zpráv požadující provedení nějaké akce, abychom mohli migrovat vaše skupiny, nemusíte jako stávající zákazníci nic dělat. Možná jste také v centru zpráv dostali oznámení, že migrace trvá déle z důvodu chyb na naší straně. Usilovně pokračujeme v práci na migraci všech ovlivněných zákazníků.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Vylepšení dlaždic aplikací v aplikaci Portál společnosti pro iOS
Aktualizovali jsme vzhled dlaždic aplikací na domovské stránce tak, aby odrážely barvu brandingu nastavenou v Portálu společnosti. Další informace najdete v [novinkách v uživatelském rozhraní aplikace](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Pro aplikaci Portál společnosti pro iOS je teď dostupný výběr účtu
Uživatelům zařízení s iOSem se při přihlašování do Portálu společnosti může zobrazit náš nový výběr účtu, pokud k přihlašování do jiných aplikací Microsoftu používají svůj pracovní nebo školní účet. Další informace najdete v [novinkách v uživatelském rozhraní aplikace](whats-new-app-ui.md).

## <a name="may-2017"></a>Květen 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Změna autority pro správu mobilních zařízení bez zrušení registrace spravovaných zařízení <!--1103950-->
Autoritu pro správu mobilních zařízení teď můžete změnit, aniž byste museli kontaktovat podporu Microsoftu a zrušit registraci a provést novou registraci stávajících spravovaných zařízení. V konzole Configuration Manageru můžete [změnit autoritu pro správu mobilních zařízení](/sccm/mdm/deploy-use/change-mdm-authority) z Nastavit na nástroj Configuration Manager (hybridní) na Microsoft Intune (samostatné) a naopak.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Vylepšené oznámení pro spouštěcí PIN kódy zabezpečení Samsung Knox <!--1087143-->
Pokud koncoví uživatelé na zařízeních se zabezpečením Samsung Knox potřebují nastavit spouštěcí PIN, aby vyhovoval požadavkům na šifrování, přenese je oznámení, které se zobrazí po klepnutí, přímo na místo v aplikaci Nastavení.  Dříve oznámení odkázalo koncové uživatele na obrazovku pro změnu hesla.

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Podpora Apple School Manageru (ASM) se sdíleným iPadem <!-- 748864, 770395-->

Pro první registraci zařízení s iOSem teď Intune místo programu Apple Device Enrollment Program podporuje použití Apple School Manageru (ASM). K použití aplikace Classroom pro sdílené iPady a k povolení synchronizace dat z ASM do Azure Active Directory prostřednictvím služby Synchronizace školních dat Microsoftu se vyžaduje zprovoznění ASM. Další informace najdete v tématu [Povolení registrace zařízení s iOSem pomocí Apple School Manageru](apple-school-manager-set-up-ios.md).

> [!NOTE]
> Konfigurace fungování sdílených iPadů s aplikací Classroom vyžaduje konfigurace iOS Education v Azure, které ještě nejsou k dispozici.  Tato funkce bude brzy přidána.

### <a name="device-management"></a>Správa zařízení

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>Poskytování vzdálené pomoci na zařízeních s Androidem pomocí TeamVieweru <!-- 675418 -->

Intune vám teď pomocí softwaru [TeamViewer](https://www.teamviewer.com), který se prodává zvlášť, umožňuje poskytovat vzdálenou pomoc uživatelům používajícím zařízení s Androidem. Další informace najdete v článku o [poskytování vzdálené pomoci pro zařízení s Androidem, která se spravují přes Intune](device-profile-android-teamviewer.md).

### <a name="app-management"></a>Správa aplikací

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>Nové podmínky zásad ochrany aplikace pro MAM <!-- 679864 -->

Teď můžete nastavit požadavek pro MAM bez uživatelů registrace, který vynucuje tyto zásady:

- Minimální verzi aplikací
- Minimální verzi operačního systému
- Minimální verzi Intune APP SDK cílové aplikace (pouze iOS)

Tato funkce je k dispozici pro Android i iOS. Intune podporuje vynucení minimální verze pro verze platformy OS, verze aplikací a Intune APP SDK. V iOSu můžou aplikace s integrovanou sadou SDK také nastavit vynucení minimální veze na úrovni SDK. Pokud nebudou splněny minimální požadavky prostřednictvím zásad ochrany aplikace na třech různých úrovních uvedených výše, uživatel nebude moct k cílové aplikaci přistupovat. Uživatel teď může odebrat svůj účet (pro aplikace s více identitami), zavřít aplikaci nebo aktualizovat verzi operačního systému nebo aplikace.

Můžete také nakonfigurovat další nastavení, abyste poskytovali neblokující oznámení, které bude doporučovat upgrade operačního systému nebo aplikace. Toto oznámení se dá zavřít a aplikace se dá používat jako obvykle.

Další informace najdete v [Nastavení zásad ochrany aplikací pro iOS](app-protection-policy-settings-ios.md) a [Nastavení zásad ochrany aplikací pro Android](app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Konfigurace aplikací pro Android for Work <!-- 621621 -->
Některé aplikace pro Android z obchodu podporují možnosti spravované konfigurace, které správci IT umožňují řídit, jak aplikace běží v pracovním profilu. S Intune teď můžete zobrazit konfigurace podporované aplikací a nakonfigurovat je z Azure Portalu pomocí návrháře konfigurace nebo editoru JSON. Další informace najdete v článku o [používání konfigurací aplikací pro Android for Work](app-configuration-policies-use-android.md).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Nová možnost konfigurace aplikací pro MAM bez registrace <!-- 677969 -->
Teď můžete vytvářet zásady konfigurace aplikací prostřednictvím MAM bez kanálu registrace. Tato funkce je ekvivalentní zásadám konfigurace aplikací dostupným v konfiguraci aplikací ve správě mobilních zařízení (MDM). Příklad konfigurace aplikací pomocí MAM bez registrace najdete v článku o [správě přístupu k internetu pomocí zásad Managed Browseru v Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Konfigurace seznamů povolených a blokovaných adres URL pro Managed Browser <!-- 682960 -->
Teď můžete nakonfigurovat seznam povolených a blokovaných domén a adres URL pro Intune Managed Browser pomocí nastavení konfigurace aplikací na portálu Azure Portal. Tato nastavení jde nakonfigurovat bez ohledu na to, jestli se používá na spravovaném nebo nespravovaném zařízení. Další informace najdete v článku o [správě přístupu k internetu pomocí zásad Managed Browseru v Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Zobrazení zásad ochrany aplikací v helpdesku <!-- 1069473 -->
Uživatelé IT Helpdesku teď můžou zkontrolovat stav licencí uživatelů a stav zásad ochrany aplikací přiřazených uživatelům v okně Řešení potíží. Podrobnosti najdete v tématu o [řešení potíží](./help-desk-operators.md).

### <a name="device-configuration"></a>Konfigurace zařízení

#### <a name="control-website-visits-on-ios-devices----723832---"></a>Řízení navštěvování webů na zařízeních s iOSem <!-- 723832 -->
Můžete teď řídit, které webové stránky můžou uživatelé zařízení s iOSem navštívit, a to pomocí jedné z těchto dvou metod:

- Přidejte povolené a blokované adresy URL pomocí integrovaného filtru webového obsahu od společnosti Apple.

- Povolte přístup z prohlížeče Safari jenom k určeným webovým stránkám. V Safari se vytvoří záložky pro weby, které určíte.

Další informace najdete v článku o [nastavení filtru webového obsahu pro zařízení s iOSem](web-content-filter-settings-ios.md).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Konfigurace oprávnění zařízení pro aplikace Android for Work <!-- 621614 -->
U aplikací nasazených do pracovních profilů zařízení Android for Work můžete teď nakonfigurovat stav oprávnění pro jednotlivé aplikace.  Aplikace pro Android, které vyžadují oprávnění zařízení, jako je například přístup k umístění nebo fotoaparátu zařízení, ve výchozím nastavení vyzvou uživatele, aby oprávnění přijali nebo odmítli.  Pokud například aplikace používá mikrofon zařízení, potom bude koncový uživatel vyzván, aby aplikaci udělil oprávnění používat mikrofon. Tato funkce umožňuje definovat oprávnění jménem koncového uživatele.  Můžete nakonfigurovat oprávnění k a) automatickému odmítnutí bez upozornění uživatele, b) automatickému schválení bez upozornění uživatele nebo c) vyzvání uživatele k přijmutí nebo odmítnutí. Další informace najdete v článku [Nastavení omezení pro zařízení s Androidem for Work v Microsoft Intune](device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Definice PIN kódu aplikace pro zařízení s Androidem for Work <!-- 728976, 1102534 -->
Zařízení s Androidem 7.0 a vyšším s pracovním profilem spravovaným jako zařízení s Androidem for Work umožňují správci definovat zásady hesla, které se vztahují jenom na aplikace v pracovním profilu.  Vaše možnosti jsou:

- Definovat jenom zásady hesla pro celé zařízení – jedná se o heslo, které musí uživatel používat k odemknutí celého zařízení.
- Definovat jenom zásady hesla pracovního profilu – uživatelé budou vyzváni k zadání hesla při každém otevření jakékoli aplikace v pracovním profilu.
- Definovat zásady hesla pro zařízení i pro pracovní profil – správce IT má možnost definovat zásady hesla zařízení a pracovního profilu o různé síle (třeba čtyřmístný PIN kód pro odemknutí zařízení a šestimístný PIN kód pro otevření libovolné pracovní aplikace).

Další informace najdete v článku [Nastavení omezení pro zařízení s Androidem for Work v Microsoft Intune](device-restrictions-android-for-work.md).

> [!NOTE]
> Tyto možnosti jsou k dispozici jenom u Androidu 7.0 a vyššího.  Ve výchozím nastavení může koncový uživatel použít dva samostatně definované PIN kódy, nebo se může rozhodnout zkombinovat tyto dva nadefinované PIN kódy do silnějšího z nich.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Nová nastavení pro zařízení s Windows 10 <!-- 978585 -->
Přidali jsme nová [nastavení omezení zařízení s Windows](device-restrictions-windows-10.md), která řídí funkce, jako jsou bezdrátové displeje, zjišťování zařízení, přepínání úloh a chybové zprávy SIM karet.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Aktualizace konfigurace certifikátu <!-- 918991 and 823198 -->
Při vytváření profilu certifikátu SCEP je pro **Formát názvu subjektu** dostupná možnost **Vlastní** pro zařízení s iOSem, Androidem a Windows. Před touto aktualizací bylo pole **Vlastní** k dispozici jenom pro zařízení s iOSem. Další informace najdete v tématu [Vytvoření profilu certifikátu SCEP] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile).

Při vytváření profilu certifikátu PKCS je pro **Alternativní název subjektu** dostupná možnost **Vlastní atribut Azure AD**. Když vyberete **Vlastní atribut Azure AD**, je dostupná možnost **Oddělení**. Další informace naleznete v tématu [Vytvoření profilu certifikátu PKCS](certficates-pfx-configure.md#create-a-device-configuration-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Konfigurace víc aplikací, které můžou být spuštěné, když je zařízení s Androidem v režimu veřejného terminálu (kiosku) <!-- 662059 -->
Když je zařízení s Androidem v režimu veřejného terminálu, mohli jste dřív konfigurovat jenom jednu aplikaci, která mohla být spuštěná. Teď můžete konfigurovat víc aplikací pomocí ID aplikace, adresy URL obchodu nebo výběrem aplikace pro Android, kterou už spravujete. Další informace najdete v tématu o [nastavení režimu veřejného terminálu (kiosku)](device-restrictions-android.md#kiosk).



## <a name="april-2017"></a>Duben 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Podpora správy aplikace Apple Classroom
Na iPadech teď můžete spravovat aplikaci Classroom pro iOS. Nainstalujte aplikaci Classroom na iPady učitelů se správnými údaji o předmětu a studentech, pak nakonfigurujte iPady studentů zaregistrované k předmětu, abyste je mohli pomocí této aplikace ovládat.
Podrobnosti najdete v článku [Konfigurace nastavení iOS Education](education-settings-configure-ios.md).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Podpora možností spravované konfigurace pro aplikace Android <!-- 621621 -->
Aplikace Android v obchodu Play podporující možnosti spravované konfigurace se teď dají konfigurovat pomocí Intune.  Tato funkce umožňuje IT pracovníkům zobrazit seznam hodnot konfigurace podporovaných aplikací a poskytuje prvotřídní uživatelské rozhraní s asistencí, které jim umožňuje tyto hodnoty konfigurovat.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nové zásady Androidu pro komplexní kódy PIN <!-- 722069 -->
V profilu zařízení s Androidem 5.0 a vyšším teď můžete nastavit požadovaný typ [hesla](device-restrictions-android.md#password) na Číselné komplexní.  Pomocí tohoto nastavení můžete uživatelům zařízení zabránit ve vytvoření PINu, který obsahuje opakující se nebo po sobě jdoucí čísla jako 1111 nebo 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Další podpora pro zařízení s Androidem for Work
- **Správa nastavení hesla a pracovního profilu** <!-- 612808 -->

  Tato nová zásada omezení pro zařízení s Androidem for Work vám teď umožní spravovat nastavení hesla a pracovního profilu na zařízeních s Androidem for Work, která spravujete.

- **Povolení sdílení dat mezi pracovními a osobními profily** <!-- 1045102 -->

Tento profil pro omezení zařízení s Androidem for Work teď obsahuje nové možnosti, které vám pomůžou nakonfigurovat sdílení dat mezi pracovním a osobním profilem.

- **Zakázaní kopírování a vkládání mezi pracovními a osobními profily** <!-- 1046094 -->

  Nový vlastní profil zařízení pro zařízení s Androidem for Work teď umožňuje zakázat akce Kopírovat a Vložit mezi pracovními a osobními aplikacemi.

Další informace najdete v tématu o [omezeních zařízení pro Android for Work](device-restrictions-android-for-work.md).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Přiřazení obchodních aplikací zařízením s iOSem a Androidem <!-- 1057568 -->
Uživatelům nebo zařízením teď můžete přiřadit obchodní aplikace pro [iOS](lob-apps-ios.md) (soubory .ipa) a [Android](lob-apps-android.md) (soubory .apk).


###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Nové zásady zařízení pro iOS <!-- 723774, 723815, 723826, 723830 -->
- **Aplikace na ploše** – určuje, které aplikace uživatelé uvidí na [ploše svého zařízení s iOSem](home-screen-settings-ios.md). Tato zásada změní rozložení plochy, ale nenasadí žádné aplikace.

- **Připojení k zařízením AirPrint** – určuje, ke kterým [zařízením AirPrint](air-print-settings-ios-macos.md) (síťovým tiskárnám) se můžou koncoví uživatelé zařízení s iOSem připojit.

- **Připojení k zařízením AirPlay** – určuje, ke kterým [zařízením AirPlay](airplay-settings-ios.md) (jako Apple TV) se můžou koncoví uživatelé zařízení s iOSem připojit.

- **Vlastní zpráva na zamčené obrazovce** – nakonfigurujte vlastní zprávu, která se zobrazí uživatelům na zamčené obrazovce jejich zařízení s iOSem místo výchozí zprávy. Další informace najdete v tématu [Aktivace režimu ztráty u zařízení s iOSem](device-lost-mode.md)

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Omezení nabízených oznámení pro aplikace pro iOS <!-- 723767 -->
V profilu omezení zařízení Intune teď můžete nakonfigurovat tato [nastavení oznámení](app-notification-settings-ios.md) pro zařízení s iOSem:

- Úplně zapnout nebo vypnout oznámení pro konkrétní aplikaci
- Zapnut nebo vypnout oznámení v centru oznámení pro konkrétní aplikaci
- Určit typ upozornění, a to buď **žádné**, **banner** nebo **modální upozornění**
- Určit, jestli jsou pro tuto aplikaci povolené odznaky
- Určit, jestli jsou povolené zvuky oznámení

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Konfigurace spouštění aplikací pro iOS autonomně v režimu jedné aplikace <!-- 737837 -->
Pomocí profilu zařízení Intune teď můžete nakonfigurovat, aby zařízení s iOSem spouštěla zadané aplikace v [autonomním režimu jedné aplikace](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only). Pokud je tento režim nakonfigurovaný a uživatel spustí aplikaci, v zařízení se zablokuje spuštění jakékoli další aplikace. Příkladem je nakonfigurování aplikace, která uživatelům umožňuje absolvovat na zařízení test. Když se akce aplikace dokončí nebo tuto zásadu odeberete, zařízení se vrátí do normálního stavu.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Konfigurace důvěryhodných domén pro e-mail a procházení webu v zařízeních s iOSem <!-- 723765 -->
V profilu omezení zařízení s iOSem teď můžete nakonfigurovat tato [nastavení domén](device-restrictions-ios.md#domains):

- **Zrušit označení e-mailových domén** – E-maily, které uživatel posílá nebo přijímá a které neodpovídají doménám zadaným tady, se označí jako nedůvěryhodné.

- **Spravované webové domény** – Dokumenty stažené z adres URL, které zadáte tady, se budou považovat za spravované (jenom Safari).  

- **Domény pro automatické vyplňování hesel v Safari**  – Uživatelé můžou ukládat hesla v Safari jenom z adres URL odpovídajících vzorům, které tady zadáte. Pokud toto nastavení chcete použít, musí být zařízení v režimu pod dohledem a nesmí být nakonfigurované pro více uživatelů. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>Aplikace VPP, dostupné v Portálu společnosti pro iOS <!-- 748782 -->
Multilicenční aplikace (VPP) pro iOS teď můžete koncovým uživatelům přiřadit jako **Dostupné** instalace. Koncoví uživatelé budou k instalaci aplikace potřebovat účet Apple Store.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Synchronizace elektronických knih z Apple VPP Storu <!-- 800878 -->
Pomocí Intune můžete [synchronizovat knihy](vpp-apps-ios.md), které jste zakoupili z Apple Storu v rámci multilicenčního programu, a přiřadit je uživatelům.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Správa více uživatelů pro zařízení se zabezpečením Samsung Knox Standard <!-- 971988 -->
U zařízení, která používají Samsung Knox Standard, je teď v Intune podporovaná [správa více uživatelů](android-enroll.md). To znamená, že koncoví uživatelé se můžou k zařízení přihlašovat a ze zařízení odhlašovat pomocí svých přihlašovacích údajů Azure Active Directory a zařízení je centrálně spravované bez ohledu na to, jestli se zrovna používá.  Když se koncoví uživatelé přihlásí, mají přístup k aplikacím a také se na ně vztahují všechny zásady. Po odhlášení uživatelů se všechna data aplikací vymažou.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Další nastavení omezení pro zařízení s Windows <!-- 818566 -->
Přidali jsme podporu dalších [nastavení omezení pro zařízení s Windows](device-restrictions-windows-10.md), jako je dodatečná podpora prohlížeče Edge, přizpůsobení zamykací obrazovky zařízení, přizpůsobení nabídky start, tapeta nastavená z vyhledávání ve Windows Spotlight a nastavení proxy serveru.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Podpora více uživatelů pro Windows 10 Creators Update <!-- 822547 -->
Přidali jsme podporu [správy více uživatelů](windows-enroll.md) pro zařízení s Windows 10 Creators Updatem připojená k doméně Azure Active Directory. To znamená, že když se k zařízení přihlásí různí standardní uživatelé pomocí svých přihlašovacích údajů Azure AD, dostanou všechny aplikace a zásady přiřazené k jejich uživatelskému jménu. Uživatelé v současnosti nemůžou používat Portál společnosti pro samoobslužné scénáře, například instalování aplikací.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Akce Začít znovu pro počítače s Windows 10 <!-- 1004830 -->
K dispozici je teď nová [akce zařízení Začít znovu](device-fresh-start.md) pro počítače s Windows 10.  Když tuto akci provedete, odeberou se všechny aplikace, které byly v počítači PC nainstalované, a počítač PC se automaticky aktualizuje na nejnovější verzi Windows. To se dá využít k odebrání aplikací předem nainstalovaných výrobcem, které se často dodávají s novým počítačem PC. Můžete nakonfigurovat, jestli se při provedení této akce mají zachovat uživatelská data.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Další možnosti upgradu na Windows 10 <!-- 903672 -->
Vytvořením [zásad upgradu edice teď můžete zařízení upgradovat](edition-upgrade-configure-windows-10.md) na následující další edice Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Hromadná registrace zařízení s Windows 10 <!-- 747607 -->
K Azure Active Directory a Intune můžete teď pomocí Windows Configuration Designeru (WCD) připojit velký počet zařízení s Windows 10 Creators Updatem. Pokud chcete pro svého tenanta Azure AD povolit [hromadnou registraci MDM](windows-bulk-enroll.md), vytvořte zřizovací balíček, který zařízení k tenantovi Azure AD připojí pomocí Windows Configuration Designeru, a použijte balíček na zařízení ve vlastnictví firmy, která chcete hromadně zaregistrovat a spravovat. Po použití balíčku se zařízení připojí k Azure AD, zaregistrují v Intune a jsou připravená na přihlašování vašich uživatelů z Azure AD.  Uživatelé Azure AD jsou na těchto zařízeních standardními uživateli a obdrží přiřazené zásady a požadované aplikace. Samoobslužné scénáře a scénáře s Portálem společnosti v současnosti nejsou podporované.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Nová nastavení MAM pro PIN a spravovaná umístění úložiště<!-- 581122, 736644 -->
K dispozici jsou teď dvě nová nastavení aplikací, která vám pomůžou se scénáři správy mobilních aplikací (MAM):

- **Zakázat PIN kód aplikace, když je PIN kód zařízení spravovaný** – zjistí, jestli se na zaregistrovaném zařízení nachází PIN zařízení, a pokud ano, obchází PIN aplikace aktivovaný zásadami ochrany aplikací. Toto nastavení umožní snížit počet případů, kdy se uživatelům při spuštění aplikace s povolenou správou mobilních zařízení na zaregistrovaném zařízení zobrazí výzva k zadání PINu. Tato funkce je k dispozici pro Android i iOS.

- **Vyberte, do kterých služeb úložiště se můžou ukládat firemní data** – umožňuje určit umístění úložiště, do kterých se můžou ukládat firemní data. Uživatelé můžou ukládat do zvolených služeb umístění úložiště, takže všechny ostatní služby umístění úložiště, které nejsou uvedené, budou zablokované.

  Seznam podporovaných služeb umístění úložiště:

  - OneDrive
  - Business SharePoint Online
  - Místní úložiště

### <a name="help-desk-troubleshooting-portal----907448---"></a>Portál helpdesku pro řešení potíží <!-- 907448 -->
Nový [portál pro řešení potíží](help-desk-operators.md) umožňuje operátorům helpdesku a správcům Intune zobrazit uživatele a jejich zařízení a provádět úlohy k vyřešení technických problémů Intune.

## <a name="march-2017"></a>Březen 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Podpora režimu ztráty pro iOS <!--431695-->
Pro zařízení s iOSem 9.3 nebo novějším je v Intune přidaná podpora pro **režim ztráty**. Teď máte možnost zařízení uzamknout, aby se nedalo používat, a na jeho zamykací obrazovce zobrazit zprávu a kontaktní telefonní číslo.

Koncový uživatel nebude moct zařízení odemknout, dokud správce režim ztráty nevypne. Když je režim ztráty zapnutý, můžete pomocí akce **Najít zařízení** zobrazit zeměpisnou polohu zařízení na mapě v konzole Intune.

Musí se jednat o zařízení s iOSem ve vlastnictví firmy, které je zaregistrované prostřednictvím programu DEP a je v režimu dohledu.

Další informace najdete v článku [Co je správa zařízení v Microsoft Intune](device-management.md).

### <a name="improvements-to-device-actions-report---677150--"></a>Vylepšení sestavy Akce zařízení <!--677150-->
Sestavu Akce zařízení jsme vylepšili z hlediska výkonu. Tuto sestavu teď navíc můžete filtrovat podle stavu. Filtrováním sestavy můžete například zobrazit jen akce zařízení, které byly dokončeny.

### <a name="custom-app-categories---748805--"></a>Vlastní kategorie aplikací <!--748805-->
Teď můžete vytvářet, upravovat a přiřazovat kategorie pro aplikace, které přidáte do Intune. V současné době se kategorie dají zadávat jenom v angličtině.
Přečtěte si téma [Jak přidat aplikaci do Intune](apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Přiřazování obchodních aplikací uživatelům s neregistrovanými zařízeními <!--748823-->
Obchodní aplikace a aplikace z obchodu teď můžete přiřazovat bez ohledu na to, jestli zařízení jsou, nebo nejsou zaregistrovaná do Intune. Pokud zařízení uživatele není zaregistrované v Intune, musí kvůli jeho instalaci přejít na web Portál společnosti, ne do aplikace Portál společnosti.

### <a name="new-compliance-reports---846671--"></a>Nové sestavy dodržování předpisů <!--846671-->
Teď máte k dispozici sestavy dodržování předpisů, ze kterých zjistíte, nakolik zařízení ve firmě dodržují předpisy, a které vám pomůžou rychle vyřešit problémy uživatelů související s dodržováním předpisů. Můžete zjistit:

- Celkový stav dodržování předpisů zařízeními
- Stav dodržování předpisů pro individuální nastavení
- Stav dodržování předpisů pro individuální zásadu

Tyto sestavy vám také umožňují přejít až k individuálnímu zařízení a zobrazit konkrétní nastavení a zásady, které se tohoto zařízení týkají.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Přímý přístup ke scénářům registrace Apple <!--951869-->
U účtů Intune vytvořených po lednu 2017 umožňuje Intune přímý přístup ke scénářům registrace Apple pomocí úlohy Registrovat zařízení na portálu Azure Portal. Náhled na registraci Apple byl předtím přístupný jen přes odkazy na Azure Portalu. Zpřístupnění těchto funkcí v Azure bude u účtů Intune vytvořených před lednem 2017 vyžadovat jednorázovou migraci. Plán této migrace zatím nebyl oznámen, podrobnosti ale budou zpřístupněny co nejdříve. Pokud váš existující účet nemá k tomuto náhledu přístup, k otestování tohoto nového prostředí důrazně doporučujeme vytvořit zkušební účet.


## <a name="february-2017"></a>Únor 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Možnost omezení registrace mobilních zařízení <!--747600, 795782-->
Intune přidává nová omezení registrace řídící to, které platformy mobilních zařízení se mohou zaregistrovat. Intune odděluje platformy mobilních zařízení, jako je iOS, macOS, Android, Windows a Windows Mobile.

* Omezení registrace mobilních zařízení neomezuje registraci klienta pro počítače.  
* Pouze pro iOS a Android existuje další možnost blokování registrace osobních zařízení.

Pokud správce IT neoznačí nová zařízení jako vlastněná podnikem, Intune všechna nová zařízení označí jako osobní. Podrobnosti najdete v [tomto článku](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Zobrazení všech akcí na spravovaných zařízeních <!--677150-->
V nové sestavě __Akce zařízení__ se zobrazí, kdo provedl vzdálené akce, jako je obnovení továrního nastavení zařízení, a dále stav dané akce. Viz [Co je správa zařízení?](device-management.md)

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Nespravovaná zařízení mají přístup k přiřazeným aplikacím <!--664691-->
Jako součást změn v návrhu na webu Portál společnosti budou moci uživatelé iOSu a Androidu na svoje nespravovaná zařízení instalovat aplikace, které mají přiřazené jako dostupné bez registrace. S použitím přihlašovacích údajů pro Intune se budou moct uživatelé přihlásit na web Portál společnosti a zobrazit seznam aplikací, které mají přiřazené. Balíčky aplikací, které jsou dostupné bez registrace, jsou k dispozici ke stažení prostřednictvím webu Portál společnosti. Aplikace, které vyžadují registraci, aby je bylo možné nainstalovat, nejsou touto změnou ovlivněny, protože když budou chtít tyto aplikace uživatelé nainstalovat, zobrazí se jim výzva k registraci.

### <a name="custom-app-categories---748805--"></a>Vlastní kategorie aplikací <!--748805-->
Teď můžete vytvářet, upravovat a přiřazovat kategorie pro aplikace, které přidáte do Intune. V současné době se kategorie dají zadávat jenom v angličtině.
Přečtěte si téma [Jak přidat aplikaci do Intune](apps-add.md).

### <a name="display-device-categories---814654--"></a>Zobrazení kategorií zařízení <!--814654-->
Kategorie zařízení teď můžete zobrazit jako sloupec v seznamu zařízení. Kategorii můžete upravit také v části vlastností v okně vlastností zařízení. Přečtěte si téma [Jak přidat aplikaci do Intune](apps-add.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Konfigurace nastavení služby Windows Update pro firmy <!--776716-->

Windows jako služba je nový způsob poskytování aktualizací pro Windows 10. Od verze Windows 10 budou všechny nové aktualizace funkcí a aktualizace pro zvýšení kvality zahrnovat obsah všech předchozích aktualizací. To znamená, že pokud si nainstalujete nejnovější aktualizaci, máte jistotu, že jsou vaše zařízení s Windows 10 zcela aktuální. Na rozdíl od předchozích verzí Windows je teď nutné nainstalovat celou aktualizaci (a ne jenom její část).

Pomocí služby Windows Update pro firmy můžete zjednodušit správu aktualizací, abyste nemuseli schvalovat jednotlivé aktualizace pro skupiny zařízení. Můžete nakonfigurovat strategii zavádění aktualizací, abyste měli pod kontrolou řízení rizik ve vašem prostředí, a služba Windows Update zajistí, aby se aktualizace nainstalovaly ve správný čas. Prostřednictvím Microsoft Intune můžete na zařízeních nakonfigurovat nastavení aktualizací a pozdržet instalaci aktualizací. V Intune nejsou uložené samotné aktualizace, ale jenom přiřazení zásad aktualizací. Zařízení získávají aktualizace přímo ze služby Windows Update. Pomocí Intune můžete nakonfigurovat a spravovat **aktualizační kanály Windows 10**. Aktualizační kanál obsahuje skupinu nastavení, která konfigurují, kdy a jak se budou aktualizace Windows 10 instalovat. Podrobnosti najdete v článku [Konfigurace nastavení služby Windows Update pro firmy](windows-update-for-business-configure.md).
