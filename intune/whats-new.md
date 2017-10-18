---
title: "Co je nového v Microsoft Intune"
titlesuffix: Azure portal
description: "Zjistěte, jaké novinky přináší portál Intune Azure."
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1bc322567505506f63e2eb002fd330fc151bc70d
ms.sourcegitcommit: 6004fe51e3cee6fb34514ed0d56e20587ecafeb4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/17/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Co je nového v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zjistěte, jaké novinky každý týden přináší Microsoft Intune. Můžete také získat informace o [nadcházejících změnách](#whats-coming), [důležitá oznámení](#notices) o službě a informace o [minulých verzích](whats-new-archive.md).

> [!Note]
> Mnohé z těchto funkcí budou nakonec podporované pro hybridní nasazení pomocí Configuration Manageru. Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   

## <a name="week-of-october-2-2017"></a>Týden od 2. října 2017

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Vylepšení pracovního postupu instalace zařízení na Portálu společnosti <!--1490692-->
Vylepšili jsme pracovní postup instalace zařízení v aplikaci Portál společnosti pro Android. Jazyk je uživatelsky přívětivější a přizpůsobenější potřebám vaší společnosti. Tam, kde to bylo možné, jsme také zkombinovali obrazovky. Tato vylepšení najdete na stránce s [novinkami v uživatelském rozhraní aplikace](whats-new-app-ui.md#week-of-october-2-2017).

#### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Vylepšené pokyny týkající se žádosti o přístup ke kontaktům na zařízeních s Androidem <!--1484985-->

Aplikace Portál společnosti často po koncových uživatelích vyžaduje, aby přijali oprávnění Kontaktů. Pokud koncový uživatel tento přístup zamítne, zobrazí se mu nyní oznámení v aplikaci, které ho upozorní, aby aplikaci udělil podmíněný přístup. 

#### <a name="secure-startup-remediation-for-android---1490712--"></a>Odstranění problému spojeného se zabezpečeným spuštěním pro Android <!--1490712-->

Koncoví uživatelé, kteří používají zařízení s Androidem, budou moct v aplikaci Portál společnosti klepnout na důvod nedodržení předpisů. Pokud to bude možné, přejdou tímto klepnutím přímo do správného umístění v aplikaci Nastavení, aby mohli problém vyřešit. 

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Další nabízená oznámení pro koncové uživatele v aplikaci Portál společnosti pro Android Oreo <!--1475932-->

Koncovým uživatelům se zobrazí další oznámení, která je upozorní, že aplikace Portál společnosti pro Android Oreo provádí úlohy na pozadí, třeba načítání zásad ze služby Intune. Pro koncové uživatele tak bude transparentnější, kdy Portál společnosti na jejich zařízení provádí úlohy správy. Jde o součást celkové [optimalizace uživatelského rozhraní Portálu společnosti](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) pro aplikaci Portál společnosti pro Android Oreo. 

Provedli jsme další optimalizace nových prvků uživatelského rozhraní, které jsou v Androidu Oreo povoleny.  Koncovým uživatelům se zobrazí další oznámení, která je upozorní, že Portál společnosti provádí úlohy na pozadí, třeba načítání zásad ze služby Intune.  Pro koncové uživatele tak bude transparentnější, kdy Portál společnosti na jejich zařízení provádí úlohy správy.

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nové chování aplikace Portál společnosti pro Android s pracovními profily <!---1485783--->

Při registraci zařízení s Androidem for Work s pracovním profilem se o správu úloh na tomto zařízení stará aplikace Portál společnosti v pracovním profilu. 

Pokud v osobním profilu nepoužíváte nějakou aplikaci s podporou MAM, neslouží už aplikace Portál společnosti k žádnému účelu. Kvůli příjemnější práci v pracovním profilu Intune po úspěšné registraci pracovního profilu automaticky skryje osobní aplikaci Portál společnosti.

Aplikaci Portál společnosti pro Android můžete v osobním profilu kdykoli povolit tak, že přejdete na [Portál společnosti v Obchodě Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) a klepnete na **Povolit**.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Portál společnosti pro Windows 8.1 a Windows Phone 8.1 přechází do udržovacího režimu <!--1428681-->

Počínaje říjnem 2017 přejdou aplikace Portál společnosti pro Windows 8.1 a Windows Phone 8.1 do udržovacího režimu. To znamená, že tyto aplikace a existující scénáře (například registrace a dodržování předpisů) budou pro tyto platformy nadále podporovány. Tyto aplikace budu pořád dostupné ke stažení přes existující vydávací kanály, jako je Microsoft Store. 

Jakmile tyto aplikace budou v udržovacím režimu, budou dostávat jen důležité aktualizace zabezpečení. Pro tyto aplikace se už nebudou vydávat další aktualizace ani funkce. Kvůli novým funkcím doporučujeme zařízení aktualizovat na Windows 10 nebo Windows 10 Mobile. 

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="block-unsupported-samsung-knox-device-enrollment------1490695----"></a>Blokování registrace nepodporovaných zařízení Samsung KNOX <!--- 1490695 --->

Aplikace Portál společnosti se pokusí zaregistrovat pouze podporovaná zařízení Samsung Knox. Aby předešla chybám aktivace KNOX, které brání v registraci MDM, pokusí se aplikace zaregistrovat pouze ta zařízení, která jsou uvedená v [seznamu zařízení publikovaném společnosti Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Některá čísla modelů zařízení Samsung mohou podporovat KNOX, některá nemusí. Než si zařízení koupíte a nasadíte, ověřte si u prodejce, zda je vaše zařízení kompatibilní se systémem Knox. Úplný seznam ověřených zařízení najdete v [nastavení zásad pro Android a Samsung KNOX Standard](/intune-classic/android-policy-settings-in-microsoft-intune.md#supported-samsung-knox-standard-devices).

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920----"></a>Konec podpory pro Android verze 4.3 a nižší <!---1171126, 1326920 --->
Spravované aplikace a aplikace Portál společnosti pro Android budou pro přístup k firemním prostředkům vyžadovat operační systém Android 4.4 nebo novější. Od prosince budou všechna zaregistrovaná zařízení vyřazena, čímž dojde ke ztrátě přístupu k firemním prostředkům. Pokud používáte zásady ochrany aplikací bez správy mobilních zařízení MDM, aplikace nebudou získávat aktualizace a kvalita jejich činnosti bude časem upadat.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Informování koncových uživatelů o tom, které informace o zařízení si můžou zobrazit na zaregistrovaném zařízení <!--1165314-->
Na obrazovku Podrobnosti o zařízení ve všech aplikacích Portál společnosti přidáváme **Typ vlastnictví**. Uživatelům to umožní zjistit další informace o ochraně osobních údajů přímo z článku [Jaké informace moje společnost uvidí?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune). Tuto funkci budeme v blízké budoucnosti postupně zavádět ve všech aplikacích Portál společnosti. Pro iOS jsme implementaci této funkce oznámili v [září](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017). 


## <a name="week-of-september-25-2017"></a>Týden od 25. září 2017

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="intune-supports-ios-11---1428975--"></a>Intune podporuje iOS 11 <!--1428975-->
Intune podporuje iOS 11. Tuto podporu jsme již dříve oznámili na [blogu podpory Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

### <a name="end-of-support-for-ios-80----1164477---"></a>Konec podpory pro systém iOS 8.0 <!---1164477--->
Spravované aplikace a aplikace Portál společnosti pro iOS budou pro přístup k firemním prostředkům vyžadovat operační systém iOS 9.0 nebo novější. Zařízení, která nebudou do tohoto září aktualizována, již nebudou mít k těmto aplikacím nebo k Portálu společnosti přístup. 

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Do aplikace Portál společnosti pro Windows 10 byla přidána akce aktualizace <!--1132468-->

Aplikace Portál společnosti pro Windows 10 umožňuje uživatelům aktualizovat data v aplikaci, a to buď potažením prstem, nebo stisknutím klávesy F5 na počítačích.

## <a name="week-of-september-11-2017"></a>Týden od 11. září 2017

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Informování koncových uživatelů o tom, jaké informace o zařízení si můžou zobrazit v iOSu <!--739894-->

Na obrazovku Podrobnosti o zařízení v aplikaci Portál společnosti pro iOS jsme přidali **Typ vlastnictví**. Uživatelům to umožní zjistit další informace o ochraně osobních údajů přímo z této stránky z dokumentace Intune pro koncové uživatele. Tyto informace najdou také na obrazovce s informacemi o produktu.

#### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Možnost pro koncové uživatele získat přístup k aplikaci Portál společnosti pro Android bez registrace <!---1169910--->

Koncoví uživatelé brzy nebudou muset svá zařízení registrovat, aby získali přístup k aplikaci Portál společnosti pro Android. Koncovým uživatelům v organizacích, které používají zásady ochrany aplikací, už nebudou při otevření aplikace Portál společnosti chodit výzvy k registraci jejich zařízení. Koncoví uživatelé budou také moct bez registrace zařízení z Portálu společnosti instalovat aplikace. 


#### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Srozumitelnější text v aplikaci Portál společnosti pro Android <!---1396349--->  

Proces registrace aplikace Portál společnosti pro Android byl zjednodušen novým textem, který koncovým uživatelům umožňuje jednodušší registraci. Pokud máte vlastní dokumentaci k registraci, měli byste ji aktualizovat, aby odrážela nové obrazovky. Ukázkové obrázky najdete na naší stránce [aktualizací uživatelského rozhraní aplikací Intune pro koncové uživatele](whats-new-app-ui.md#week-of-september-11-2017).

#### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Do zásad povolení Windows Information Protection byla přidána aplikace Portál společnosti pro Windows 10 <!-- 677129 -->

Aplikace Portál společnosti pro Windows 10 byla aktualizována o podporu WIP (Windows Information Protection). Tuto aplikaci lze přidat do zásad povolení WIP. Díky této změně se už tato aplikace nemusí přidávat do seznamu **výjimek**.


## <a name="week-of-august-21-2017"></a>Týden od 21. srpna 2017

### <a name="device-enrollment"></a>Registrace zařízení
#### <a name="improvements-to-device-overview----1404453---"></a>Vylepšení přehledu zařízení <!-- 1404453 -->  
Ve vylepšeném přehledu zařízení se teď zobrazují registrovaná zařízení, jsou ale vyloučena zařízení spravovaná přes Exchange Active Sync. Zařízení Exchange ActiveSync nemají stejné možnosti správy jako registrovaná zařízení. Pokud chcete v Intune na Azure Portalu zjistit počet registrovaných zařízení a počet registrovaných zařízení podle platformy, přejděte na **Zařízení** > **Přehled**.

### <a name="device-management"></a>Správa zařízení
#### <a name="improvements-to-device-inventory-collected-by-intune"></a>Vylepšení inventáře zařízení shromažďovaného službou Intune
<!-- 961134, 1104426, 1281327, 1333543 -->
V této verzi jsme udělali následující vylepšení inventarizačních informací shromažďovaných zařízeními, která spravujete:
 
-   Pro zařízení s Androidem teď můžete do inventáře zařízení přidat sloupec, ve kterém se zobrazuje nejnovější úroveň opravy jednotlivých zařízení. Tento údaj zobrazíte, když do seznamu zařízení přidáte sloupec **Úroveň opravy zabezpečení**.
-   Zobrazení zařízení teď můžete filtrovat podle data registrace zařízení. Můžete například zobrazit jen zařízení, která byla zaregistrována po zadaném datu.
-   Vylepšili jsme filtr, který se používá u údaje **Datum posledního ohlášení**.
-   V seznamu zařízení si teď u zařízení ve vlastnictví firmy můžete zobrazit telefonní číslo.
Pomocí podokna filtru můžete navíc vyhledat zařízení podle telefonního čísla.
 
Další podrobnosti o inventáři zařízení najdete v článku [Jak zobrazit inventář zařízení spravovaných přes Intune](device-inventory.md).

#### <a name="conditional-access-support-for-macos-devices"></a>Podpora podmíněného přístupu pro zařízení s macOS 
<!-- 720172 -->
Teď můžete nastavit zásady podmíněného přístupu, které po zařízeních Mac vyžadují registraci v Intune a soulad se zásadami dodržování předpisů pro zařízení. Uživatelé si mohou například stáhnout aplikaci Portál společnosti Intune pro macOS a zaregistrovat svá zařízení Mac ve službě Intune. Intune prostřednictvím požadavků, jako je kód PIN, šifrování, verze operačního systému a integrita systému, vyhodnotí, zda zařízení Mac předpisy dodržuje nebo ne.

- Přečtěte si další informace o [podpoře podmíněného přístupu pro zařízení s macOS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

#### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>Aplikace Portál společnosti pro macOS ve verzi Public Preview <!---1484796--->
Aplikace Portál společnosti pro macOS je teď k dispozici jako součást verze Public Preview pro podmíněný přístup v Enterprise Mobility + Security. Tato verze podporuje macOS 10.11 a novější. Získáte ji na [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


#### <a name="new-device-restriction-settings-for-windows-10"></a>Nová nastavení omezení pro zařízení s Windows 10    
<!--1063965, 1308850  -->
V této verzi jsme přidali nová nastavení pro [profil omezení zařízení s Windows 10](/intune/device-restrictions-windows-10) v následujících kategoriích:

-   Filtr SmartScreen v programu Windows Defender
-   App Store

#### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Aktualizace profilu zařízení ochrany koncových bodů Windows 10 o nastavení BitLockeru
<!--1459533 -->    
V této verzi jsme následujícím způsobem vylepšili nastavení BitLockeru v profilu zařízení ochrany koncových bodů Windows 10:
 
Když jste dříve v **Nastavení BitLockeru pro jednotky s operačním systémem** vybrali u nastavení **BitLocker s nekompatibilním čipem TPM** možnost **Blokovat**, ve skutečnosti se BitLocker povolil. Teď je to opravené a při výběru této možnosti se BitLocker zablokuje.
V **Nastavení BitLockeru pro jednotky s operačním systémem** teď můžete pomocí nastavení **Agent obnovení dat založený na certifikátech** explicitně zablokovat agenta obnovení dat založeného na certifikátech. Standardně je ale tento agent povolený.
V **Nastavení BitLockeru pro jednotky s operačním systémem** teď můžete pomocí nastavení **Agent obnovení dat** explicitně zablokovat agenta obnovení dat.
Další informace najdete v tématu o [nastavení služby Endpoint Protection pro Windows 10 a novější](endpoint-protection-windows-10.md).


### <a name="app-management"></a>Správa aplikací
#### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nové prostředí po přihlášení pro uživatele Portálu společnosti pro Android a uživatele zásad ochrany aplikací <!-- 621669 -->
Koncoví uživatelé teď můžou pomocí aplikace Portál společnosti pro Android procházet aplikace, spravovat zařízení a zobrazit kontakt na IT oddělení, aniž by své zařízení s Androidem zaregistrovali. Pokud už koncový uživatel používá aplikaci chráněnou zásadami Intune App Protection a spustí Portál společnosti pro Android, už se mu navíc nezobrazí výzva k registraci zařízení.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nové nastavení v aplikaci Portál společnosti pro Android k přepnutí optimalizace baterie <!--1405990-->
Stránka **Nastavení** v aplikaci Portál společnosti pro Android obsahuje nové nastavení, které uživatelům umožní snadno vypnout optimalizaci baterie pro aplikace Portál společnosti a Microsoft Authenticator. Název aplikace uvedený v nastavení se liší v závislosti na tom, která aplikace spravuje pracovní účet. Doporučujeme, aby uživatelé optimalizaci baterie vypnuli kvůli lepšímu výkonu pracovních aplikací, které synchronizují e-maily a data. 

#### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>Podpora více identit ve OneNotu pro iOS      <!-- 1234281 -->
Koncoví uživatelé teď můžou v Microsoft OneNotu pro iOS používat různé účty (pracovní a osobní). Na firemní data v pracovních poznámkových blocích lze uplatnit zásady ochrany aplikací, aniž to ovlivní osobní poznámkové bloky. Pomocí zásad můžete například uživateli povolit hledání informací v pracovních poznámkových blocích, ale zabránit v kopírování a vkládání firemních dat z pracovních do osobních poznámkových bloků.
 
- Přečtěte si další informace o aplikacích, které podporují [ochranu aplikací a více identit](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) s Intune.

#### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Povolení a blokování aplikací na zařízeních se Samsung KNOX Standard pomocí nových nastavení
<!-- 1305423 822899-->  
V této verzi přidáváme nová [nastavení omezení zařízení](device-restrictions-android.md), která vám umožní zadat následující seznamy aplikací:
 
- Aplikace, které mají uživatelé dovoleno instalovat.
- Aplikace, které mají uživatelé zakázáno spouštět.
- Aplikace, které jsou před uživatelem zařízení skryté.
 
Aplikaci můžete zadat pomocí adresy URL, názvu balíčku nebo ze seznamu spravovaných aplikací.

#### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Odkaz na nové uživatelské rozhraní zásad podmíněného přístupu na základě aplikací Azure AD z Intune
<!-- 1016201 -->
Správci IT teď můžou nastavit podmíněné zásady na základě aplikací prostřednictvím nového uživatelského rozhraní zásad podmíněného přístupu v úloze Azure AD. Podmíněný přístup na základě aplikací, který je v části Intune App Protection na portálu Azure Portal, prozatím zůstane a bude se vynucovat souběžně. Užitečný odkaz na nové uživatelské rozhraní zásad podmíněného přístup obsahuje také úloha Intune.

- Přečtěte si další informace o [podmíněném přístupu na základě aplikací v Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).


## <a name="notices"></a>Sdělení

### <a name="ip-addresses-for-intune-updated----1175274---"></a>IP adresy pro Intune aktualizovány <!-- 1175274 -->
K dispozici je [aktualizovaný seznam názvů DNS a IP adres](/intune/network-bandwidth-use) pro nastavení proxy serveru brány firewall.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Používání Azure Active Directory pro podmíněný přístup <!-- 967947 -->
Podmíněný přístup je dostupný v sekci Azure Active Directory na Azure Portalu a poskytuje výkonnější a flexibilnější rozhraní pro nastavení zásad cloudových aplikací, jako jsou Office 365 Exchange Online a SharePoint Online.  Místo konzoly Intune použijte ke konfiguraci nastavení zásad okno **Podmíněný přístup v Azure Active Directory**. Existující zásady v konzole Intune se musí na Azure Portalu znovu vytvořit. Další informace najdete v článku [Vytvoření zásad podmíněného přístupu Azure AD](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Přímý přístup ke scénářům registrace Apple <!--951869-->
U účtů Intune vytvořených po lednu 2017 umožňuje Intune přímý přístup ke scénářům registrace Apple pomocí úlohy Registrovat zařízení na portálu Azure Portal. Náhled na registraci Apple byl předtím přístupný jen přes odkazy na klasickém portálu Intune. Zpřístupnění těchto funkcí v Azure vyžaduje u účtů Intune vytvořených před lednem 2017 jednorázovou migraci. Plán této migrace zatím nebyl oznámen, podrobnosti ale budou zpřístupněny co nejdříve. Pokud váš existující účet nemá k portálu Azure Portal přístup, k otestování tohoto nového prostředí důrazně doporučujeme vytvořit zkušební účet.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Nahrazení rolí správy na portálu Azure Portal
Existující role pro správu mobilních aplikací (MAM) (Přispěvatel, Vlastník a Jen pro čtení) používané v klasickém portálu Intune (Silverlight) byly na portálu Azure Portal pro Intune nahrazeny celou řadou nových možností řízení přístupu na základě role (RBAC). Jakmile migrujete na portál Azure Portal, bude potřeba, abyste svým správcům přiřadili tyto nové role správy. Další informace o RBAC a nových rolích najdete v článku [Řízení přístupu na základě role pro Microsoft Intune](/intune/role-based-access-control).



## <a name="whats-coming"></a>Co připravujeme

#### <a name="ios-11-mail-app-will-support-oauth----1196951---"></a>Aplikace Mail v iOSu 11 bude podporovat OAuth <!---1196951--->
Podmíněný přístup s Intune podporuje zabezpečenější ověřování na zařízeních s iOSem pomocí OAuth. Pro podporu této funkce teď bude v aplikaci Portál společnosti pro iOS odlišný tok, který umožní ověřování s větším zabezpečením. Když se koncoví uživatelé pokusí v aplikaci Mail přihlásit k novému účtu Exchange, zobrazí se jim výzva ve webovém zobrazení. Při registraci v Intune se uživatelům zobrazí výzva, aby nativní aplikaci Mail povolili přístup k certifikátu. Většině koncových uživatelů se už nebudou zobrazovat žádné další e-maily v karanténě. Existující poštovní účty budou i nadále používat základní ověřovací protokol, a proto se uživatelům těchto účtů budou stále doručovat e-maily v karanténě. Prostředí pro přihlášení koncových uživatelů se podobá prostředí v mobilních aplikacích Office.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>Aktualizace uživatelského rozhraní webu Portál společnosti <!--1313244 part 2-->
__Aktualizace vybraných aplikací__  
Přidali jsme na web vyhrazenou stránku, kde můžou uživatelé procházet aplikace, které jste speciálně vybrali, a upravili jsme uživatelské rozhraní sekce Vybrané na domovské stránce. Tyto změny si můžete prohlédnout na stránce s [novinkami v uživatelském rozhraní aplikace](whats-new-app-ui.md).

### <a name="platform-support-reminder-windows-phone-81-mainstream-support-ended-july-11-2017"></a>Připomenutí podpory platformy: hlavní fáze technické podpory pro Windows Phone 8.1 skončila 11. července 2017
<!-- 1327781 -->
11. července 2017 skončila hlavní fáze technické podpory pro Windows Phone 8.1. Podporu počítačů s Windows 8.1 to neovlivní.

Na žádné zařízení s Windows Phone 8.1, které je spravováno službou Intune, to nebude mít okamžitý vliv. Zaregistrovaná zařízení budou nadále fungovat a všechny zásady, konfigurace a aplikace také. Všimněte si, že pro aplikaci Portál společnosti pro Windows Phone 8.1 ani pro platformu Windows Phone 8.1 v rámci služby Intune neexistují žádná cílená vylepšení.

Doporučujeme vám, abyste při nejbližší příležitosti způsobilá zařízení s Windows Phone 8.1 upgradovali na Windows 10 Mobile. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Změny v podpoře pro aplikaci Portál společnosti Intune pro iOS  <!-- 1164474  -->
Již brzy bude dostupná nová verze aplikace Portál společnosti Microsoft Intune pro iOS, která bude podporovat pouze zařízení se systémem iOS 9.0 nebo novějším. Verze podporující iOS 8 bude ještě na krátkou dobu k dispozici. Pokud používáte také aplikace iOS s podporou MAM, podporujeme iOS 9.0 a novější, takže budete muset zajistit, aby vaši koncoví uživatelé aktualizovali na nejnovější verzi operačního systému. 

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Přestože nemáme konkrétní datum, dáváme vám to vědět předem, abyste měli čas si to naplánovat. Zajistěte, aby vaši uživatelé měli iOS 9.0 nebo novější, a jakmile vyjde nová verze aplikace Portál společnosti, požádejte koncové uživatele, aby tuto aplikaci aktualizovali.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Upozorněte své uživatele, že aby mohli naplno využívat nových funkcí služby Intune, musí si iOS aktualizovat na verzi 9.0 nebo novější.  Vyzvěte uživatele, aby si nainstalovali novou verzi aplikace Portál společnosti a mohli využívat nově nabízených funkcí.

Pokud chcete vidět všechna aktuální zařízení s operačními systémy staršími než iOS 9, přejděte na Azure Portalu do služby Intune, zobrazte si Zařízení > Všechna zařízení a vyfiltrujte si je podle verze iOSu.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple bude vyžadovat aktualizace ATS (Application Transport Security) <!--748318-->
Apple oznámil, že začne vynucovat specifické požadavky na ATS (Application Transport Security). ATS se používá k vynucení vyššího zabezpečení veškeré komunikace aplikací přes protokol HTTPS. Tato změna ovlivní zákazníky Intune, kteří používají aplikace Portál společnosti pro iOS.

Prostřednictvím programu Apple TestFlight, který vynucuje nové požadavky na ATS, jsme zpřístupnili verzi aplikace Portál společnosti pro iOS. Pokud si ji chcete vyzkoušet a otestovat, jestli ATS dodržujete, napište nám na adresu <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> zprávu s vaším jménem a příjmením, e-mailovou adresou a názvem společnosti. Další podrobnosti najdete v [blogu podpory služby Intune](https://aka.ms/compportalats).

### <a name="see-also"></a>Viz taky
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co je nového v uživatelském rozhraní Portálu společnosti](whats-new-app-ui.md)
* [Novinky v předchozích měsících](whats-new-archive.md)
