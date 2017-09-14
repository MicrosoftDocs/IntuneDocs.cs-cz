---
title: "Časná edice"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 09/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 31c3d3750aadbe8d302713f081f01f7c51d8ce96
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="the-early-edition-for-microsoft-intune---september-2017"></a>Časná edice Microsoft Intune – září 2017

**Časná edice** poskytuje seznam funkcí, které se chystají v nadcházejících vydáních služby Microsoft Intune. Tyto informace jsou poskytovány v omezené míře a můžou podléhat změnám. Nesdílejte tyto informace mimo společnost. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a můžou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moct zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se na příslušný kontakt pro skupinu produktů společnosti Microsoft.

Tato stránka se pravidelně aktualizuje. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.

> [!Note]
>Následující změny v Intune jsou ve vývoji. Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--

## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices

-->



## <a name="intune-in-the-azure-portal"></a>Intune na portálu Azure Portal


### <a name="google-play-protect-support-on-android----908720----"></a>Podpora Google Play Protect na Androidu <!-- 908720  -->  
S vydáním verze Android Oreo zavádí Google sadu bezpečnostních funkcí s názvem Google Play Protect, které uživatelům a organizacím umožňují provozovat zabezpečené aplikace a zabezpečené image Androidu. Intune bude funkce Google Play Protect podporovat, a to včetně vzdáleného ověření SafetyNet.  Správci můžou nastavit požadavky na zásady dodržování předpisů, které vyžadují, aby funkce Google Play Protect byla nakonfigurovaná a funkční. Nastavení **Ověření zařízení SafetyNet** vyžaduje, aby se zařízení připojilo ke službě Googlu, která ověří, že je zařízení v pořádku a není ohrožené. Správci můžou rovněž nastavením konfiguračního profilu pro Android for Work vyžádat, aby nainstalované aplikace byly ověřeny pomocí služeb Google Play.  Podmíněný přístup může uživatelům zablokovat přístup k firemním prostředkům, pokud zařízení nesplňuje požadavky na Google Play Protect. 

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Uživatelům zařízení s Androidem lze zabránit ve změně data a času <!-- 1333292 -->
Pomocí [vlastních zásad zařízení s Androidem](custom-settings-android.md) můžete uživatelům zabránit, aby na zařízení změnili datum a čas.
Uděláte to tak, že nakonfigurujete vlastní zásadu pro Android s identifikátorem URI nastavení ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange. Nastavte tuto zásadu na **TRUE** a pak ji přiřaďte požadovaným skupinám.

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Zobrazení přiřazených zásad ochrany aplikací kvůli řešení problémů <!--  1475003 -->
V této nadcházející verzi bude do rozevíracího seznamu **Přiřazení**, který je dostupný v okně pro řešení potíží, přidána možnost **Zásady ochrany aplikací**. Výběrem zásad ochrany aplikací teď můžete zobrazit zásady ochrany aplikací přiřazené vybraným uživatelům.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Vytvoření aplikací pro iOS omezených na určité regionální Apple App Story <!-- 1281692 -->
Během vytváření spravované aplikace pro Apple App Store budete moci určit národní prostředí země.

> [!NOTE]  
> V současnosti můžete vytvářet jen spravované aplikace pro Apple App Store, které se nacházejí v americkém App Storu.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Výběr regionálního Apple App Storu pro synchronizaci aplikací VPP <!-- 1332311 -->  
Při nahrávání tokenu VPP (Volume Purchase Program) můžete nakonfigurovat regionální VPP Store. Intune synchronizuje aplikace VPP pro všechna národní prostředí z určeného regionálního VPP Storu.

> [!NOTE]  
> V současnosti synchronizuje Intune jen aplikace VPP z regionálního VPP Storu, které se shodují s národním prostředím Intune, ve kterém byl tenant Intune vytvořen.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Aktualizace aplikací VPP pro iOS licencovaných pro uživatele a zařízení <!-- 1305564 -->  
Token VPP pro iOS budete moci nakonfigurovat tak, aby se prostřednictvím služby Intune aktualizovaly všechny aplikace zakoupené pro tento token. Intune zjistí aktualizace aplikací VPP v App Storu a automaticky je nabídne zařízení, jakmile se zařízení ohlásí.

### <a name="ios-11-support----1428975---"></a>Podpora iOS 11 <!-- 1428975 -->
Jakmile Apple vydá iOS 11, bude ho Intune podporovat.

### <a name="new-settings-for-windows-10-team-device-restriction-profile------1308838----"></a>Nová nastavení pro profil omezení zařízení s Windows 10 Team <!--- 1308838  -->
V této verzi přidáváme spoustu nových nastavení do profilu omezení zařízení s Windows 10 Team, která vám pomůžou ovládat zařízení Surface Hub.
Další informace o tomto profilu najdete v článku [Nastavení omezení zařízení s Windows 10 Team](device-restrictions-windows-10-teams.md).

### <a name="support-for-windows-10-edition-upgrade-policy------903672-1119689---"></a>Podpora zásad upgradu edice Windows 10 <!-- 903672, 1119689 -->  
Budete moci vytvořit zásady upgradu edice Windows 10, které zařízení s Windows 10 upgradují na Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education a Windows 10 Professional Education N. Podrobnosti o upgradech edic Windows 10 najdete v článku [Jak nakonfigurovat upgrady edicí Windows 10](edition-upgrade-configure-windows-10.md).

### <a name="review-policy-compliance-for-windows-10-update-rings----1352223---"></a>Kontrola dodržování zásad pro aktualizační okruhy Windows 10 <!-- 1352223 -->  
Přes **Aktualizace softwaru** > **Stav nasazení podle kruhu aktualizace** budete moci zkontrolovat sestavu zásad pro aktualizační okruhy Windows 10. Tato sestava zásad obsahuje stav nasazení pro nakonfigurované aktualizační okruhy. 

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Do zásad povolení Windows Information Protection byla přidána aplikace Portál společnosti pro Windows 10 <!-- 677129 -->  
Aplikace Portál společnosti pro Windows 10 bude aktualizována o podporu WIP (Windows Information Protection). Tuto aplikaci lze přidat do zásad povolení WIP. Díky této změně se už tato aplikace nemusí přidávat do seznamu **výjimek**. 

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Vzdálená podpora zařízení s Windows a Windows Mobile <!-- 1070473 -->    
Intune vám pomocí samostatně zakoupeného softwaru [TeamViewer](https://www.teamviewer.com) umožní poskytovat vzdálenou pomoc uživatelům, kteří používají zařízení s Windows a Windows Mobile.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Kontrola zařízení pomocí programu Windows Defender <!-- 1280988  1280990   -->
Na spravovaných zařízeních s Windows 10 budete pomocí Antivirové ochrany v programu Windows Defender moci provést **rychlou kontrolu**, **úplnou kontrolu** a **aktualizaci signatur**. V okně s přehledem zařízení zvolte akci, která se má na zařízení spustit. Před odesláním příkazu do zařízení budete vyzváni k potvrzení. 

**Rychlá kontrola:** Při rychlé kontrole se kontrolují místa, kde se registruje spuštění malwaru, jako jsou klíče registru a známé spouštěcí složky Windows. Rychlá kontrola trvá průměrně pět minut. V kombinaci s nastavením **trvalé ochrany v reálném čase**, která soubory kontroluje při otevření, zavření a vždy, když uživatel přejde do nějaké složky, poskytuje rychlá kontrola ochranu před malwarem, který se může nacházet v systému nebo jádru. Uživatelé uvidí na svých zařízeních výsledky kontroly potom, co se dokončí. 

**Úplná kontrola:** Úplnou kontrolu využijete u zařízení napadených malwarem, kdy umožňuje zjistit, jestli v zařízení nezůstaly nějaké neaktivní komponenty, které vyžadují důkladnější vyčištění. Slouží také ke spuštění kontrol na vyžádání. Úplná kontrola může trvat hodinu. Uživatelé uvidí na svých zařízeních výsledky kontroly potom, co se dokončí. 

**Aktualizace signatur:** Tímto příkazem se u Antivirové ochrany v programu Windows Defender aktualizují definice a signatury malwaru. Tím se zajistí účinnost Antivirové ochrany v programu Windows Defender při zjišťování malwaru. Tato funkce je určená jen pro zařízení s Windows 10 a očekává, že je zařízení připojené k internetu. 

### <a name="bitlocker-device-configuration----1397398---"></a>Konfigurace zařízení s BitLockerem <!-- 1397398 -->  
Možnost **Šifrování Windows > Základní nastavení** bude obsahovat nové nastavení **Upozornění na jiné šifrování disku**, které vám umožní zakázat [výzvu s upozorněním](https://docs.microsoft.com/en-us/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) na jiné šifrování disku, které se na zařízení uživatele může používat.  Tato výzva s upozorněním vyžaduje svolení koncového uživatele před nastavením BitLockeru na zařízení a blokuje jeho nastavení, dokud není potvrzené koncovým uživatelem.  Toto nové nastavení zakazuje upozornění koncového uživatele.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Portál společnosti pro Windows 8.1 a Windows Phone 8.1 přechází do udržovacího režimu <!--1428681-->
Počínaje říjnem 2017 přejdou aplikace Portál společnosti pro Windows 8.1 a Windows Phone 8.1 do udržovacího režimu. To znamená, že tyto aplikace a existující scénáře (například registrace a dodržování předpisů) budou pro tyto platformy nadále podporovány. Tyto aplikace budu pořád dostupné ke stažení přes existující vydávací kanály, jako je Microsoft Store. 

Jakmile tyto aplikace budou v udržovacím režimu, budou dostávat jen důležité aktualizace zabezpečení. Pro tyto aplikace se už nebudou vydávat další aktualizace ani funkce. Kvůli novým funkcím doporučujeme zařízení aktualizovat na Windows 10 nebo Windows 10 Mobile. 

###  <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Blokování kopírování a vkládání mezi pracovním a osobním profilem pro Android for Work <!-- 1098994 -->   
V této verzi můžete pracovní profil pro Android for Work nakonfigurovat tak, aby bylo zablokované kopírování a vkládání mezi pracovními a osobními aplikacemi. Toto nové nastavení najdete v profilu **Omezení zařízení** pro platformu **Android for Work** v **Nastavení pracovního profilu**.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nové chování aplikace Portál společnosti pro Android s pracovními profily <!---1485783--->
Při registraci zařízení s Androidem for Work s pracovním profilem se o správu úloh na tomto zařízení stará aplikace Portál společnosti v pracovním profilu. Pokud v osobním profilu nepoužíváte nějakou aplikaci s podporou MAM, neslouží už aplikace Portál společnosti k žádnému účelu. Kvůli příjemnější práci v pracovním profilu Intune po úspěšné registraci pracovního profilu automaticky skryje osobní aplikaci Portál společnosti.

Aplikaci Portál společnosti pro Android můžete v osobním profilu kdykoli povolit tak, že přejdete na [Portál společnosti v Obchodě Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) a klepnete na **Povolit**.

### <a name="intune-mam--outlook-for-android-add-ins-----1450688---"></a>Doplňky Intune MAM a Outlook pro Android <!-- 1450688 -->
V příštích týdnech oznámí tým Office doplňky pro Outlook na Androidu. Tato sada doplňkových funkcí už existuje v Outlooku pro Windows, iOS, web a Mac. Protože se doplňky spravují přes Exchange, budou uživatelé moci kopírovat a sdílet data a zprávy mezi Outlookem a nespravovanými doplňkovými aplikacemi, dokud správce Exchange přístup k doplňkům nevypne. 

Pokud chcete spravovat přístupová oprávnění uživatele k doplňkům, ve spolupráci se správcem Exchange zajistěte, aby se zásady ochrany dat MAM vztahovaly na doplňky.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Pokud už máte zásady Exchange nastavené tak, že zakazují instalaci doplňků bokem nebo běžnou instalaci doplňků, nemusíte číst dál. Vaše zásady MAM se uplatní podle očekávání. Pokud ale máte zásady MAM nastavené tak, že zakazují operace vyjmutí, kopírování a vložení v Outlooku na Androidu a nenastavili jste zásady doplňků v Exchangi, měli byste vědět, že uživatelé budou moci do Outlooku instalovat doplňky. Tyto doplňky můžou mít přístup k textu, předmětu a jiným vlastnostem zprávy. Koncovým uživatelům můžete v instalaci doplňků zabránit tak, že správce Exchange požádáte o odebrání rolí Moje aplikace z Marketplace a Moje vlastní aplikace. Další podrobnosti najdete pod odkazem na další informace níže.

Tato změna nastavení v Exchangi se uplatní na Outlook pro Windows, iOS, web, Mac a mobilní zařízení. 

#### <a name="what-do-i-need-to-do"></a>Co musím udělat?
Ještě dnes zkontrolujte zásady Exchange. Informujte pracovníky IT oddělení a helpdesku. S konkrétními otázkami nebo obavami se obraťte na náš tým podpory. 

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Do datového modelu datového skladu Intune byla přidána kolekce entit přidružení uživatelů a zařízení <!-- 1187917 -->
Pomocí informací o přidružení uživatelů a zařízení, které přidružují kolekce entit uživatelů a zařízení, budete moci vytvářet sestavy a vizualizace dat. Tento datový model lze zpřístupnit přes soubor Power BI (PBIX) načtený ze stránky Datový sklad v Intune, přes koncový bod OData nebo vývojem vlastního klienta.


<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--"></a>Akce při nedodržení předpisů  <!--730266-->     
*Akce při nedodržení předpisů* je nová funkce zásad dodržování předpisů, která umožňuje provádět akce na zařízeních, které nedodržují předpisy. Můžete zadat jednu nebo více akcí a určit časové období, během kterého se tyto akce musí provést. Třeba uživatelům zařízení, která nedodržují předpisy, můžete poslat e-mailem oznámení, hned jak zařízení přestane předpisy dodržovat. Nebo pomocí podmíněného přístupu můžete takovým zařízením zablokovat přístup k prostředkům společnosti po 3denním období odkladu.

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nová sestava obsahující seznam zařízení se staršími verzemi iOSu   <!-- 1352223 -->
Sestava **zařízení se zastaralým iOSem** bude k dispozici z pracovního prostoru **Aktualizace softwaru**. V sestavě můžete zobrazit seznam zařízení s iOSem pod dohledem, na která byla zacílena zásada aktualizace iOSu a pro která jsou k dispozici aktualizace. Pro každé zařízení můžete zobrazit stav, proč nebylo automaticky aktualizováno. 

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>Nová nastavení pro profil omezení zařízení s Windows 10
<!--- 978575, 1308849, -->
Do profilu omezení zařízení s Windows 10 v kategorii filtru SmartScreen v programu Windows Defender přidáváme nová nastavení.

Podrobnosti o profilu omezení zařízení s Windows 10 najdete v tématu [Nastavení omezení pro zařízení Windows 10 a novější]( device-restrictions-windows-10.md).

### <a name="android-for-work-support-for-lookout----1087312---"></a>Podpora Androidu for Work pro Lookout <!-- 1087312 -->   
Při použití aplikace Lookout for Work bude konektor Intune s Lookoutem podporovat zařízení s Androidem for Work. Aplikaci Lookout můžete nasadit uvnitř nebo vně kontejneru.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune App Protection a nástroje pro vývoj Citrix MDX <!-- 709185 -->
Můžete spravovat zařízení a aplikace s kombinací Citrix XenMobile MDX a Microsoft Intune. To umožňuje spravovat aplikace pomocí zásad ochrany aplikací Intune při použití technologie mVPN společnosti Citrix.

Můžete najít úložiště kódu, které obsahuje Intune App Wrapping Tool a sadu Intune App SDK pro iOS a Android, a využít integraci s technologií Citrix MDX mVPN.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium – nový partner ochrany před mobilními hrozbami   <!-- 954681 -->
Přístup mobilních zařízení k podnikovým prostředkům můžete regulovat pomocí podmíněného přístupu na základě posouzení rizik, které provádí služba Zimperium. Je to řešení ochrany před mobilními hrozbami integrované v Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak integrace se službou Intune funguje?
Riziko se posuzuje na základě telemetrie, která se shromažďuje ze zařízení, na kterých služba Zimperium běží. Zásady podmíněného přístupu EMS založené na posouzení rizika službou Zimperium můžete nakonfigurovat prostřednictvím zásad dodržování předpisů zařízení služby Intune, kterými můžete na základě odhalených hrozeb u zařízení, které nedodržují předpisy, povolit nebo zablokovat přístup k firemním prostředkům.

### <a name="new-azure-ad-conditional-access-policy-ui-link-from-intune-----1016201---"></a>Odkaz na nové uživatelské rozhraní zásad podmíněného přístupu Azure AD z Intune  <!-- 1016201 -->
Správci IT můžou nastavit podmíněné zásady na základě aplikací prostřednictvím nového uživatelského rozhraní zásad podmíněného přístupu v úloze Azure AD. Zásady podmíněného přístupu na základě aplikací, které jsou v části Intune App Protection v Azure, prozatím zůstávají a vynucují se souběžně. Na nové uživatelské rozhraní zásad podmíněného přístupu v Azure AD bude také užitečný odkaz z úlohy Intune.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Podpora vysoké dostupnosti místního konektoru Exchange Connector  <!-- 676614 -->   
U místního konektoru Exchange Connector máte možnost mít několik rolí serveru pro klientský přístup (CAS). Například pokud hlavní server pro klientský přístup selže, konektor Exchange Connector obdrží výzvu, aby využíval jiné servery pro klientský přístup. Tato funkce zajišťuje, že se služba nepřeruší.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Sada System Center Operations Manager Management Pack pro konektor Exchange Connector <!-- 885457 -->   
Pro pomoc s analýzou protokolů konektoru Exchange Connector bude dostupná sada System Center Operations Manager Management Pack pro konektor Exchange Connector. Pokud potřebujete řešit potíže, tento Management Pack poskytuje různé možnosti monitorování Intune.

### <a name="end-of-support-for-ios-80----1164477---"></a>Konec podpory pro systém iOS 8.0 <!---1164477--->
Spravované aplikace a aplikace Portál společnosti pro iOS budou pro přístup k firemním prostředkům vyžadovat operační systém iOS 9.0 nebo novější. Zařízení, která nebudou do tohoto září aktualizována, již nebudou mít k těmto aplikacím nebo k Portálu společnosti přístup. Od prosince jim bude zakázán veškerý přístup k firemním prostředkům včetně e-mailu. 

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Konec podpory pro Android verze 4.3 a nižší <!---1171127, 1326920 --->
Spravované aplikace a aplikace Portál společnosti pro Android budou pro přístup k firemním prostředkům vyžadovat operační systém Android 4.4 nebo novější. Zařízení, která nebudou do začátku října aktualizována, již nebudou mít k těmto aplikacím nebo k Portálu společnosti přístup. Od prosince budou všechna zaregistrovaná zařízení vyřazena, čímž dojde ke ztrátě přístupu k firemním prostředkům. Pokud používáte zásady ochrany aplikací bez správy mobilních zařízení MDM, aplikace nebudou získávat aktualizace a kvalita jejich činnosti bude časem upadat.

### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>Připomenutí podpory platformy: všeobecná podpora Windows Phone 8.1 končí 11. července 2017 <!-- 1327781 -->  
11. července 2017 končí všeobecná podpora platformy Windows Phone 8.1. Podporu počítačů s Windows 8.1 to neovlivní.

Na žádné zařízení s Windows Phone 8.1, které je spravováno službou Intune, to nebude mít okamžitý vliv. Zaregistrovaná zařízení dál fungují a všechny zásady, konfigurace a aplikace budou fungovat podle očekávání. Všimněte si, že pro aplikaci Portál společnosti Windows Phone 8.1 ani pro platformu Windows Phone 8.1 v rámci služby Intune neexistují žádná cílená vylepšení.

Doporučujeme vám při nejbližší příležitosti způsobilá zařízení s Windows Phone 8.1 upgradovat na Windows 10 Mobile. 





## <a name="intune-apps"></a>Aplikace Intune
### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Do aplikace Portál společnosti pro Windows 10 byla přidána akce aktualizace <!--1132468-->
Aplikace Portál společnosti pro Windows 10 umožní uživatelům aktualizovat data v aplikaci, a to buď potažením prstem, nebo stisknutím klávesy F5 na počítačích.


### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Aplikace, které jsou dostupné s registrací nebo bez registrace, lze nyní nainstalovat bez výzvy k registraci <!-- 1334712 -->
Firemní aplikace, které byly u aplikace Portál společnosti pro Android zpřístupněny s registrací nebo bez registrace, lze nainstalovat bez výzvy k registraci.

### <a name="ios-company-portal-display-large-icons----1454593---"></a>Portál společnosti pro iOS zobrazuje velké ikony <!-- 1454593 -->
Opravujeme známý problém s tím, jak Portál společnosti pro iOS zobrazuje ikony v dlaždici aplikace. Pokud nahrajete ikony aplikace o rozměru 120×120 pixelů nebo větší, zobrazí se teď na [webu Portálu společnosti] (https://portal.manage.microsoft.com) a na stránkách aplikací Portál společnosti pro iOS v plné velikosti dlaždice aplikace.

### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android------1396349---"></a>Srozumitelnější text v aplikaci Portál společnosti pro Android <!---1396349--->    
Proces registrace aplikace Portál společnosti pro Android byl zjednodušen novým textem, který koncovým uživatelům umožňuje jednodušší registraci. 


<!-- the following are present prior to 1709 -->


### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Podpora Intune Managed Browser pro iOS a Android <!---1374196--->
Od října 2017 bude aplikace Intune Managed Browser pro Android podporovat jen zařízení se systémem Android 4.4 a novější. Aplikace Intune Managed Browser pro iOS bude podporovat jen zařízení se systémem iOS 9.0 a novější. Starší verze systému Android a iOS budou moct Managed Browser dál používat, ale nepůjde do nich nainstalovat nové verze této aplikace a nebudou mít přístup ke všem jejím možnostem. Doporučujeme vám tato zařízení aktualizovat na podporovanou verzi operačního systému.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Možnost pro koncové uživatele získat přístup k aplikaci Portál společnosti pro Android bez registrace <!---1169910--->  
Koncoví uživatelé brzy nebudou muset svá zařízení registrovat, aby získali přístup k aplikaci Portál společnosti pro Android. Koncovým uživatelům v organizacích, které používají zásady ochrany aplikací, už nebudou při otevření aplikace Portál společnosti chodit výzvy k registraci jejich zařízení. Koncoví uživatelé budou také moct bez registrace zařízení z Portálu společnosti instalovat aplikace. 

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Vylepšená chybová zpráva, když uživatel dosáhne maximálního povoleného počtu zařízení k registraci <!-- 1270370 -->
Místo obecné chybové zprávy se koncovým uživatelům zobrazí popisná chybová zpráva, na kterou se dá reagovat: „Zaregistrovali jste maximální počet zařízení, který povoluje váš IT správce. Odeberte prosím zaregistrované zařízení, nebo se obraťte s žádostí o pomoc na IT správce.“

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Informování koncových uživatelů o tom, jaké informace o zařízení si můžou zobrazit v iOSu <!--739894-->
Na obrazovku Podrobnosti o zařízení v aplikaci Portál společnosti pro iOS přidáváme **Typ vlastnictví**. To uživatelům umožňuje zjistit další informace o ochraně osobních údajů přímo z této stránky z dokumentace Intune pro koncové uživatele. Tyto informace najdou také na obrazovce s informacemi o produktu.

### <a name="apps-details-pages-display-new-information-for-android-devices---1287476--"></a>Stránky podrobností o aplikacích zobrazují nové informace pro zařízení s Androidem <!--1287476-->
Na stránce podrobností o aplikacích v aplikaci Portál společnosti pro Android se zobrazí kategorie aplikací, které správce IT pro tuto aplikaci určil.

### <a name="intune-mobile-application-management-mam-dialog-boxes-now-have-a-modern-interface----1199015---"></a>Dialogová okna správy mobilních aplikací (MAM) Intune teď mají moderní rozhraní <!-- 1199015 -->
Dialogová okna správy mobilních aplikací (MAM) Intune byla aktualizována na moderní vzhled. Dialogová okna fungují stejně jako v předchozím stylu.

Na moderních zařízeních s Androidem teď budou mít dialogová okna chyb nebo oznámení zobrazená službou Intune aktualizovaný vzhled.



## <a name="notices"></a>Sdělení
### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple bude vyžadovat aktualizace ATS (Application Transport Security) <!--748318-->   
Apple oznámil, že od jara 2017 začne vynucovat specifické požadavky na ATS (Application Transport Security). ATS se používá k vynucení vyššího zabezpečení veškeré komunikace aplikací přes protokol HTTPS. Tato změna ovlivní zákazníky Intune, kteří používají aplikace Portál společnosti pro iOS. Další podrobnosti najdete v [blogu podpory služby Intune](https://aka.ms/compportalats).

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Plánovaná změna: Intune mění způsob fungování portálu Intune Partner Portal<!-- 1050016 -->
Počínaje aktualizací služby v polovině května 2017 odstraníme stránku Intune Partner z manage.microsoft.com.  

Pokud jste partnerským správcem, nebude už moct stránku Intune Partner zobrazit a provádět z ní jménem vašich zákazníků kroky, ale místo toho se budete muset přihlásit k jednomu ze dvou dalších partnerských portálů Microsoftu.

K účtům zákazníků, které spravujete, se budete moct přihlásit z [Partnerského centra Microsoftu](https://partnercenter.microsoft.com/) a [Centra pro partnerskou správu Office 365](https://portal.office.com/). V budoucnu jako partneři prosím ke správě svých zákazníků používejte jeden z těchto webů.



### <a name="see-also"></a>Související témata
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).
