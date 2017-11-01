---
title: "Co je nového v Microsoft Intune"
titlesuffix: Azure portal
description: "Zjistěte, jaké novinky přináší portál Intune Azure."
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b669268073e4484738e93fd2909b905242732664
ms.sourcegitcommit: b8d3f8da6d8c2bd5d6140d538193a02d5875aefb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
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

## <a name="week-of-october-23-2017"></a>Týden od 23. října 2017

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Podpora ověřování na základě certifikátu v Portálu společnosti pro iOS <!--1029830-->
Přidali jsme podporu ověřování pomocí certifikátů v aplikaci Portál společnosti pro iOS. Uživatelé s ověřováním pomocí certifikátů zadají svoje uživatelské jméno a pak klepnou na odkaz „Přihlásit se pomocí certifikátu“. V aplikacích Portál společnosti pro Android a Windows je už ověřování pomocí certifikátů podporované. Další informace najdete na stránce o [přihlášení do aplikace Portál společnosti](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

## <a name="week-of-october-16-2017"></a>Týden od 16. října 2017

### <a name="device-enrollment"></a>Registrace zařízení
#### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Podpora programu Windows AutoPilot Deployment v Microsoft Intune  <!-- 747617  -->
Teď můžete Microsoft Intune používat s programem Windows AutoPilot Deployment, abyste uživatelům umožnili zřizovat firemní zařízení bez zapojení IT pracovníků. Můžete přizpůsobit software spouštěný při prvním zapnutí a nasměrovat uživatele k tomu, aby své zařízení připojili k Azure AD a zaregistrovali v Intune. Microsoft Intune a Windows AutoPilot společně eliminují potřebu nasazovat, udržovat a spravovat image operačního systému. Podrobnosti najdete v článku [Registrace zařízení s Windows pomocí programu Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).

#### <a name="quick-start-for-device-enrollment-----1425655---"></a>Rychlé zahájení pro registraci zařízení  <!-- 1425655 --> 
V **Registraci zařízení** je teď dostupné rychlé zahájení, které poskytuje referenční tabulku pro správu platforem a konfiguraci procesu registrace. Stručný popis jednotlivých položek a odkazy na dokumentaci s podrobnými pokyny poskytují užitečnou dokumentaci, která zjednodušuje zahájení práce.

#### <a name="device-categorization----1427491---"></a>Kategorizace zařízení <!-- 1427491 -->
Graf platforem zaregistrovaných zařízení v okně **Zařízení > Přehled** uspořádá zařízení podle platforem, včetně Androidu, iOSu, macOS, Windows a Windows Mobile.  Zařízení s jinými operačními systémy jsou seskupená do kategorie „Ostatní“.  Ta zahrnuje zařízení od výrobců Blackberry, NOKIA a dalších.  

Pokud chcete zjistit, která zařízení jsou ve vašem tenantovi ovlivněna, zvolte **Spravovat > Všechna zařízení** a pak pomocí **Filtrovat** omezte pole **OS**.

### <a name="device-management"></a>Správa zařízení
#### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium – nový partner ochrany před mobilními hrozbami   <!-- 954681 -->  
Přístup mobilních zařízení k podnikovým prostředkům můžete regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Zimperium. Je to řešení ochrany před mobilními hrozbami, které se integruje s Microsoft Intune.

##### <a name="how-integration-with-intune-works"></a>Jak integrace s Intune funguje
Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých služba Zimperium běží. Zásady podmíněného přístupu EMS založené na posouzení rizika službou Zimperium můžete nakonfigurovat prostřednictvím zásad dodržování předpisů zařízení služby Intune, kterými můžete na základě odhalených hrozeb u zařízení, které nedodržují předpisy, povolit nebo zablokovat přístup k firemním prostředkům.

#### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Nová nastavení pro profil omezení zařízení s Windows 10  <!--- 978575, 1308849, -->  
Do profilu omezení zařízení s Windows 10 v kategorii filtru SmartScreen v programu Windows Defender přidáváme nová nastavení.

Podrobnosti o profilu omezení zařízení s Windows 10 najdete v tématu [Nastavení omezení pro zařízení Windows 10 a novější]( device-restrictions-windows-10.md).

#### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Vzdálená podpora zařízení s Windows a Windows Mobile   <!-- 1070473 -->  
Intune vám teď pomocí samostatně zakoupeného softwaru [TeamViewer](https://www.teamviewer.com) umožňuje poskytovat vzdálenou pomoc uživatelům, kteří používají zařízení s Windows a Windows Mobile.

#### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Kontrola zařízení pomocí programu Windows Defender <!-- 1280988  1280990   -->
Na spravovaných zařízeních s Windows 10 teď můžete pomocí Antivirové ochrany v programu Windows Defender provádět **rychlou kontrolu**, **úplnou kontrolu** a **aktualizaci signatur**. V okně s přehledem zařízení zvolte akci, která se má na zařízení spustit. Před odesláním příkazu do zařízení budete vyzváni k potvrzení. 

**Rychlá kontrola:** Při rychlé kontrole se kontrolují místa, kde se registruje spuštění malwaru, jako jsou klíče registru a známé spouštěcí složky Windows. Rychlá kontrola trvá průměrně pět minut. V kombinaci s nastavením **trvalé ochrany v reálném čase**, která soubory kontroluje při otevření, zavření a vždy, když uživatel přejde do nějaké složky, poskytuje rychlá kontrola ochranu před malwarem, který se může nacházet v systému nebo jádru. Uživatelé uvidí na svých zařízeních výsledky kontroly potom, co se dokončí. 

**Úplná kontrola:** Úplnou kontrolu využijete u zařízení napadených malwarem, kdy umožňuje zjistit, jestli v zařízení nezůstaly nějaké neaktivní komponenty, které vyžadují důkladnější vyčištění. Slouží také ke spuštění kontrol na vyžádání. Úplná kontrola může trvat hodinu. Uživatelé uvidí na svých zařízeních výsledky kontroly potom, co se dokončí. 

**Aktualizace signatur:** Tímto příkazem se u Antivirové ochrany v programu Windows Defender aktualizují definice a signatury malwaru. Tím se zajistí účinnost Antivirové ochrany v programu Windows Defender při zjišťování malwaru. Tato funkce je určená jen pro zařízení s Windows 10 a očekává, že je zařízení připojené k internetu. 

#### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>Bylo odebráno tlačítko Povolit/Zakázat ze stránky certifikační autority Intune na portálu Intune Azure Portal  <!-- 1400455 -->
 Odstraňujeme nadbytečný krok při nastavení Certificate Connectoru v Intune. V současné době stáhnete Certificate Connector a pak ho povolíte v konzole Intune. Pokud ale konektor v konzole Intune zakážete, dál vydává certifikáty.

##### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Od října už se tlačítko Povolit/Zakázat na stránce certifikační autority na portálu Azure Portal zobrazovat nebude. Funkce konektoru zůstává stejná. Do zařízení zaregistrovaných v Intune se budou certifikáty dál nasazovat. Certificate Connector můžete dál stáhnout a nainstalovat. Pokud chcete zastavit vydávání certifikátů, Certificate Connector teď místo zakázání odinstalujete.

##### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Pokud máte Certificate Connector aktuálně zakázaný, měli byste ho odinstalovat.



### <a name="device-configuration"></a>Konfigurace zařízení
#### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Nová nastavení pro profil omezení zařízení s Windows 10 Team   <!--- 1308838 -->
V této verzi jsme přidali spoustu nových nastavení do profilu omezení zařízení s Windows 10 Team, která vám pomůžou ovládat zařízení Surface Hub.

Další informace o tomto profilu najdete v článku [Nastavení omezení zařízení s Windows 10 Team](device-restrictions-windows-10-teams.md).

#### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Uživatelům zařízení s Androidem lze zabránit ve změně data a času <!-- 1333292 -->
Pomocí [vlastních zásad zařízení s Androidem](custom-settings-android.md) můžete uživatelům zabránit, aby na zařízení změnili datum a čas.

Uděláte to tak, že nakonfigurujete vlastní zásadu pro Android s identifikátorem URI nastavení ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange. Nastavte tuto zásadu na **TRUE** a pak ji přiřaďte požadovaným skupinám.

#### <a name="bitlocker-device-configuration----1397398---"></a>Konfigurace zařízení s BitLockerem <!-- 1397398 -->
Možnost **Šifrování Windows > Základní nastavení** obsahuje nové nastavení **Upozornění na jiné šifrování disku**, které vám umožní zakázat [výzvu s upozorněním](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) na jiné šifrování disku, které se na zařízení uživatele může používat.  Tato výzva s upozorněním vyžaduje svolení koncového uživatele před nastavením BitLockeru na zařízení a blokuje jeho nastavení, dokud není potvrzené koncovým uživatelem.  Toto nové nastavení zakazuje upozornění koncového uživatele.


### <a name="app-management"></a>Správa aplikací
#### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Aplikace Volume Purchase Program for Business se teď budou synchronizovat s vaším tenantem Intune <!-- 800882 -->  
Vývojáři třetích stran můžou soukromě distribuovat aplikace autorizovaným členům programu Volume Purchase Program (VPP) for Business, kteří jsou uvedeni ve službě iTunes Connect. Tito členové programu VPP for Business se mohou přihlásit do zvláštního App Storu pro tento program a aplikace si zakoupit.

Od této verze se teď začnou aplikace VPP for Business zakoupené koncovým uživatelem synchronizovat s jeho tenanty Intune.

#### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Výběr regionálního Apple App Storu pro synchronizaci aplikací VPP <!-- 1332311 -->  
Při nahrávání tokenu VPP (Volume Purchase Program) můžete nakonfigurovat regionální VPP Store. Intune synchronizuje aplikace VPP pro všechna národní prostředí z určeného regionálního VPP Storu.

> [!NOTE]  
> V současnosti synchronizuje Intune jen aplikace VPP z regionálního VPP Storu, které se shodují s národním prostředím Intune, ve kterém byl tenant Intune vytvořen.




### <a name="intune-apps"></a>Aplikace Intune
#### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Blokování kopírování a vkládání mezi pracovním a osobním profilem pro Android for Work <!-- 1098994 -->
V této verzi můžete pracovní profil pro Android for Work nakonfigurovat tak, aby bylo zablokované kopírování a vkládání mezi pracovními a osobními aplikacemi. Toto nové nastavení najdete v profilu **Omezení zařízení** pro platformu **Android for Work** v **Nastavení pracovního profilu**.

#### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Vytvoření aplikací pro iOS omezených na určité regionální Apple App Story <!-- 1281692 -->
Během vytváření spravované aplikace pro Apple App Store budete moci určit národní prostředí země.

> [!Note]  
> V současnosti můžete vytvářet jen spravované aplikace pro Apple App Store, které se nacházejí v americkém App Storu.

####  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Aktualizace aplikací VPP pro iOS licencovaných pro uživatele a zařízení <!-- 1305564 -->  
Token VPP pro iOS budete moci nakonfigurovat tak, aby se prostřednictvím služby Intune aktualizovaly všechny aplikace zakoupené pro tento token. Intune zjistí aktualizace aplikací VPP v App Storu a automaticky je nabídne zařízení, jakmile se zařízení ohlásí.

Pokyny k nastavení tokenu VPP a povolení automatických aktualizací najdete v článku [Správa aplikací pro systém iOS nakoupených prostřednictvím programu hromadného nákupu pomocí Microsoft Intune] (/intune/vpp-apps-ios).



### <a name="monitor-and-troubleshoot"></a>Monitorování a odstraňování potíží
#### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Do datového modelu datového skladu Intune byla přidána kolekce entit přidružení uživatelů a zařízení <!-- 1187917 -->
Pomocí informací o přidružení uživatelů a zařízení, které přidružují kolekce entit uživatelů a zařízení, teď můžete vytvářet sestavy a vizualizace dat. Tento datový model lze zpřístupnit přes soubor Power BI (PBIX) načtený ze stránky Datový sklad v Intune, přes koncový bod OData nebo vývojem vlastního klienta.

#### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Kontrola dodržování zásad pro aktualizační okruhy Windows 10 <!-- 1067886 -->
Přes Aktualizace softwaru > Stav nasazení podle kruhu aktualizace budete moct zkontrolovat sestavu zásad pro aktualizační kanály Windows 10. Tato sestava zásad obsahuje stav nasazení pro nakonfigurované aktualizační okruhy. 

#### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nová sestava obsahující seznam zařízení se staršími verzemi iOSu   <!-- 1352223 -->
Sestava **zařízení se zastaralým iOSem** je k dispozici z pracovního prostoru **Aktualizace softwaru**. V sestavě můžete zobrazit seznam zařízení s iOSem pod dohledem, na která byla zacílena zásada aktualizace iOSu a pro která jsou k dispozici aktualizace. Pro každé zařízení můžete zobrazit stav, proč nebylo automaticky aktualizováno. 

#### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Zobrazení přiřazených zásad ochrany aplikací kvůli řešení problémů <!--  1475003 -->
V této nadcházející verzi bude do rozevíracího seznamu **Přiřazení**, který je dostupný v okně pro řešení potíží, přidána možnost **Zásady ochrany aplikací**. Výběrem zásad ochrany aplikací teď můžete zobrazit zásady ochrany aplikací přiřazené vybraným uživatelům.



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

Aplikace Portál společnosti se pokusí zaregistrovat pouze podporovaná zařízení Samsung Knox. Aby předešla chybám aktivace KNOX, které brání v registraci MDM, pokusí se aplikace zaregistrovat pouze ta zařízení, která jsou uvedená v [seznamu zařízení publikovaném společnosti Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Některá čísla modelů zařízení Samsung mohou podporovat KNOX, některá nemusí. Než si zařízení koupíte a nasadíte, ověřte si u prodejce, zda je vaše zařízení kompatibilní se systémem Knox. Úplný seznam ověřených zařízení najdete v [nastavení zásad pro Android a Samsung KNOX Standard](/intune/supported-devices-browsers.md#intune-supported-devices).

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920----"></a>Konec podpory pro Android verze 4.3 a nižší <!---1171126, 1326920 --->
Spravované aplikace a aplikace Portál společnosti pro Android budou pro přístup k firemním prostředkům vyžadovat operační systém Android 4.4 nebo novější. Od prosince budou všechna zaregistrovaná zařízení vyřazena, čímž dojde ke ztrátě přístupu k firemním prostředkům. Pokud používáte zásady ochrany aplikací bez správy mobilních zařízení MDM, aplikace nebudou získávat aktualizace a kvalita jejich činnosti bude časem upadat.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Informování koncových uživatelů o tom, které informace o zařízení si můžou zobrazit na zaregistrovaném zařízení <!--1165314-->
Na obrazovku Podrobnosti o zařízení ve všech aplikacích Portál společnosti přidáváme **Typ vlastnictví**. Uživatelům to umožní zjistit další informace o ochraně osobních údajů přímo z článku [Jaké informace moje společnost uvidí?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune). Tuto funkci budeme v blízké budoucnosti postupně zavádět ve všech aplikacích Portál společnosti. Pro iOS jsme implementaci této funkce oznámili v [září](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).


## <a name="week-of-september-25-2017"></a>Týden od 25. září 2017

### <a name="device-enrollment"></a>Registrace zařízení

#### <a name="intune-supports-ios-11---1428975--"></a>Intune podporuje iOS 11 <!--1428975-->
Intune podporuje iOS 11. Tuto podporu jsme již dříve oznámili na [blogu podpory Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

#### <a name="end-of-support-for-ios-80----1164477---"></a>Konec podpory pro systém iOS 8.0 <!---1164477--->
Spravované aplikace a aplikace Portál společnosti pro iOS budou pro přístup k firemním prostředkům vyžadovat operační systém iOS 9.0 nebo novější. Zařízení, která nebudou do tohoto září aktualizována, již nebudou mít k těmto aplikacím nebo k Portálu společnosti přístup. 

### <a name="intune-apps"></a>Aplikace Intune

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Do aplikace Portál společnosti pro Windows 10 byla přidána akce aktualizace <!--1132468-->
Aplikace Portál společnosti pro Windows 10 umožňuje uživatelům aktualizovat data v aplikaci, a to buď potažením prstem, nebo stisknutím klávesy F5 na počítačích.



## <a name="notices"></a>Sdělení

### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>Nová cesta pro spravovaná zařízení v Graph API <!-- 1586728 -->
Měníme cestu používanou pro přístup ke spravovaným zařízením v beta verzi rozhraní Graph API. 

| | |
|--|--|
| Aktuální cesta |  https://graph.microsoft.com/beta/managedDevices |
| Nová cesta | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Celý říjen budou fungovat obě cesty. Po říjnovém vydání verze služby bude fungovat jenom cesta nová.  Pokud používáte rozhraní Graph API pro přístup ke spravovaným zařízením, aktualizujte a ověřte své skripty a aplikace s novou cestou. Další změny najdete v měsíčním [protokolu změn Graph API](https://developer.microsoft.com/graph/docs/concepts/changelog).


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Přímý přístup ke scénářům registrace Apple <!--951869-->
U účtů Intune vytvořených po lednu 2017 umožňuje Intune přímý přístup ke scénářům registrace Apple pomocí úlohy Registrovat zařízení na portálu Azure Portal. Náhled na registraci Apple byl předtím přístupný jen přes odkazy na klasickém portálu Intune. Zpřístupnění těchto funkcí v Azure vyžaduje u účtů Intune vytvořených před lednem 2017 jednorázovou migraci. Plán této migrace zatím nebyl oznámen, podrobnosti ale budou zpřístupněny co nejdříve. Pokud váš existující účet nemá k portálu Azure Portal přístup, k otestování tohoto nového prostředí důrazně doporučujeme vytvořit zkušební účet.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Nahrazení rolí správy na portálu Azure Portal
Existující role pro správu mobilních aplikací (MAM) (Přispěvatel, Vlastník a Jen pro čtení) používané v klasickém portálu Intune (Silverlight) byly na portálu Azure Portal pro Intune nahrazeny celou řadou nových možností řízení přístupu na základě role (RBAC). Jakmile migrujete na portál Azure Portal, bude potřeba, abyste svým správcům přiřadili tyto nové role správy. Další informace o RBAC a nových rolích najdete v článku [Řízení přístupu na základě role pro Microsoft Intune](/intune/role-based-access-control).



## <a name="whats-coming"></a>Co připravujeme

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

## <a name="see-also"></a>Viz taky
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co je nového v uživatelském rozhraní Portálu společnosti](whats-new-app-ui.md)
* [Novinky v předchozích měsících](whats-new-archive.md)
