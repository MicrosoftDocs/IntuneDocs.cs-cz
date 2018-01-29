---
title: "Časná edice"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/18/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 12f4a09fe10ec792abe8183369a21f53c23f5d1a
ms.sourcegitcommit: 53d272defd2ec061dfdfdae3668d1b676c8aa7c6
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2018
---
# <a name="the-early-edition-for-microsoft-intune---january-2018"></a>Časná edice Microsoft Intune – leden 2018

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

### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546---"></a>Snadnější řešení problémů s dodržováním předpisů v aplikaci Portál společnosti pro Windows 10 <!--676546 -->

Koncoví uživatelé, kteří používají zařízení s Windows, budou moct v aplikaci Portál společnosti klepnout na důvod nedodržení předpisů. Pokud to bude možné, přejdou tímto klepnutím přímo do správného umístění v aplikaci Nastavení, aby mohli problém vyřešit.

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Nová možnost ověřování uživatelů při hromadné registraci Apple <!-- 747625 -->
Intune nabízí možnost ověřovat zařízení pomocí aplikace Portál společnosti u těchto metod registrace:

- Program Apple Device Enrollment Program
- Apple School Manager
- Registrace Apple Configuratoru

Při použití možnosti Portálu společnosti lze vynutit vícefaktorové ověřování Azure Active Directory bez blokování těchto metod registrace.

Při použití možnosti Portálu společnosti pro registraci přidružení uživatelů přeskočí Intune ověřování uživatelů v Pomocníkovi s nastavením iOSu. To znamená, že zařízení se napřed zaregistruje bez uživatelů a neobdrží tedy konfigurace ani zásady pro skupiny uživatelů. Obdrží jenom konfigurace a zásady pro skupiny zařízení. Intune ale na toto zařízení automaticky nainstaluje aplikaci Portál společnosti. První uživatel, který aplikaci Portál společnosti spustí a přihlásí se do ní, se v Intune přidruží k tomuto zařízení. Daný uživatel pak obdrží konfigurace a zásady pro skupiny uživatelů. Přidružení uživatelů není možné změnit bez opětovné registrace.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Podpora Intune pro více účtů Apple DEP nebo Apple School Manager <!-- 747685 -->
Intune podporuje registraci zařízení z až 100 různých účtů Apple DEP (Device Enrollment Program) nebo Apple School Manager. Pro každý nahraný token lze profily registrace a zařízení spravovat samostatně. K jednotlivým nahraným tokenům DEP nebo School Manager lze automaticky přiřadit různé profily registrace. Pokud je nahraných více tokenů School Manager, může se v každém okamžiku sdílet pomocí služby Microsoft School Data Sync jenom jeden.

Po dokončení migrace už nebudou fungovat beta verze rozhraní Graph API a publikované skripty pro správu Apple DEP nebo ASM přes rozhraní Graph. Nové beta verze rozhraní Graph API jsou ve vývoji a budou se vydávat po dokončení migrace.

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eeready---"></a>Výběr kategorií zařízení pomocí nastavení Přístup do práce nebo do školy <!-- 1058963 eeready -->
Pokud jste povolili [mapování skupin zařízení](https://docs.microsoft.com/en-us/intune/device-group-mapping), uživatelům s Windows 10 se po registraci prostřednictvím tlačítka **Připojit** v **Nastavení** > **Účty** > **Přístup do práce nebo do školy** nebo při prvním zapnutí počítače zobrazí výzva k výběru kategorie zařízení.

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Cílení zásad dodržování předpisů na zařízení ve skupinách zařízení <!--1307012 -->

Budete moct cílit zásady dodržování předpisů na uživatele ve skupinách uživatelů. Budete moct cílit zásady dodržování předpisů na zařízení ve skupinách zařízení.

### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Zahrnutí a vyloučení přiřazení aplikací na základě skupin <!-- 1406920 -->

Během přiřazování aplikací a po výběru typu přiřazení budete moct vybrat skupiny, které se mají zahrnout, a také skupiny, které se mají vyloučit.

### <a name="remote-erase-command-support----1438084---"></a>Podpora vzdáleného použití příkazu pro vymazání <!-- 1438084 -->

Správci budou moct používat příkaz pro vymazání vzdáleně.

> [!IMPORTANT]
> Příkaz pro vymazání se nedá vrátit zpět, a proto by se měl používat s rozvahou.

Příkaz pro vymazání odebere ze zařízení všechna data včetně operačního systému. Zároveň se tím dané zařízení odebere ze správy v Intune. Uživateli se nezobrazí žádné upozornění a mazání začne okamžitě po spuštění příkazu.

Budete moct nakonfigurovat 6místný PIN kód pro obnovení. Tento PIN kód lze použít k odemknutí vymazaného zařízení, po kterém se zahájí opětovná instalace operačního systému. Když mazání začne, zobrazí se PIN kód ve stavovém řádku v okně přehledu daného zařízení v Intune. PIN kód zůstane zobrazený, dokud probíhá mazání. Po dokončení mazání zařízení úplně zmizí ze správy Intune. Nezapomeňte si PIN kód pro obnovení poznamenat, aby se dal v případě potřeby použít k obnovení zařízení.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Šifrovaná data Windows Information Protection (WIP) ve výsledcích hledání ve Windows <!-- 1469193 -->

Nové nastavení v zásadách Windows Information Protection (WIP) vám umožní řídit, jestli se mají do výsledků hledání ve Windows zahrnovat šifrovaná data WIP.

### <a name="website-learning-mode----1631908---"></a>Výukový režim pro weby <!-- 1631908 -->

Intune zavede rozšíření výukového režimu WIP (Windows Information Protection). Kromě zobrazování informací o aplikacích s podporou WIP budete moct zobrazit souhrn zařízení, která sdílí pracovní data s weby. Pomocí těchto informací můžete určit, které weby by se měly přidat do zásad WIP pro skupiny a uživatele.

### <a name="updates-to-compliance-emails---1637547---"></a>Aktualizace e-mailů týkajících se dodržování předpisů <!--1637547 -->

E-mail, kterým se odesílá hlášení o zařízení nesplňujícím požadavky, bude obsahovat podrobnosti o zařízení nesplňujícím požadavky. S ohledem na tuto skutečnost se bude aktualizovat článek [Automatizace akcí při nedodržení předpisů](#actions-for-noncompliance).

### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Zásady podmíněného přístupu pro Intune budou dostupné jenom z portálu Azure Portal <!-- 1737088 1634311 -->
Zjednodušíme, kde a jak se konfiguruje a spravuje podmíněný přístup. Zásady budete moct konfigurovat a spravovat na portálu [Azure Portal](https://portal.azure.com) z **Azure Active Directory** > **Podmíněný přístup**. Na toto okno se také pohodlně dostanete z Intune na portálu Azure Portal přes **Intune** > **Podmíněný přístup**.

###  <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Upozornění na tokeny, jejichž platnost vypršela nebo brzy vyprší <!-- 1639263 -->
Na stránce s přehledem se budou zobrazovat upozornění na tokeny, jejichž platnost vypršela nebo brzy vyprší. Když kliknete na upozornění pro jeden token, přejdete na stránku s podrobnostmi o daném tokenu.  Když kliknete na upozornění s více tokeny, přejdete na seznam všech tokenů s jejich stavem. Správci by měli tokeny obnovovat před datem vypršení jejich platnosti.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Vzdálený tisk přes zabezpečenou síť <!-- 1709994  -->
Řešení PrinterOn pro bezdrátový mobilní tisk umožní uživatelům vzdáleně tisknout odkudkoli a kdykoli přes zabezpečenou síť. PrinterOn se integruje s Intune App SDK pro iOS i Android. Zásady ochrany aplikací budete moct cílit na tuto aplikaci pomocí okna **Zásady ochrany aplikací** v Intune v konzole pro správu. Koncoví uživatelé si budou moct stáhnout aplikaci PrinterOn for Microsoft prostřednictvím Obchodu Play nebo iTunes a pak ji používat ve svém ekosystému Intune.

### <a name="approve-the-company-portal-app-for-android-for-work---1797090---"></a>Schválení aplikace Portál společnosti pro Android for Work <!--1797090 -->
Pokud vaše organizace používá Android for Work a chcete, aby aplikace Portál společnosti dále přijímala automatické aktualizace ze spravovaného obchodu Google Play, budete muset aplikaci Portál společnosti pro Android ručně schválit.

### <a name="faceid-on-ios-devices----1807377---"></a>FaceID na zařízeních s iOSem <!-- 1807377 -->
Zásady ochrany aplikací Intune teď podporují nastavení, které řídí funkci FaceID na zařízeních s iOSem. Toto nastavení je určené pro zařízení, která podporují funkci FaceID (aktuálně jenom iPhone X). Toto nastavení je oddělené od aktuálně podporovaných ovládacích prvků TouchID. Organizace mají možnost rozhodnout, jestli při ověřování osob budou pro zadání kódu PIN důvěřovat funkci FaceID (jako alternativě k ovládacím prvkům TouchID).

### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>Rozhraní Microsoft Graph API pro Intune – obecná dostupnost <!-- 1833289 -->
Rozhraní Intune API v Microsoft Graphu budou poskytovat programový přístup k datům a metodám, aby se umožnila automatizace akcí správy služby Intune.  Díky **obecné dostupnosti** těchto rozhraní API je budou moct zákazníci, partneři a vývojáři využívat k integraci s interními nebo komerčními řešeními, která vyžadují podporu Intune nebo jiných služeb Microsoftu, jež jsou dostupné prostřednictvím Microsoft Graphu, nebo s těmito službami souvisejí.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Zásady ochrany aplikací  <!-- 679615 -->
Zásady Intune App Protection nabízejí možnost vytvoření globálních výchozích zásad, které rychle aktivují ochranu přes všechny uživatele v celém tenantovi.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Odvolání aplikací pro iOS koupených přes Volume Purchase Program <!-- 820863 -->
Pro dané zařízení, které má jednu nebo více aplikací pro iOS koupených přes Volume Purchase Program (VPP), budete moct odvolat přidruženou licenci aplikace na základě zařízení. Odvoláním licence aplikace se příslušná aplikace VPP neodinstaluje ze zařízení. Pokud chcete odinstalovat aplikaci VPP, musíte nastavit akci přiřazení na **Odinstalovat**. Další informace najdete v tématu [Správa aplikací pro systém iOS nakoupených prostřednictvím programu hromadného nákupu pomocí Microsoft Intune](vpp-apps-ios.md).

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Odvolání licencí pro token Volume Purchase Program pro iOS <!-- 820870 -->
Pro daný token VPP budete moct odvolat licenci všech aplikací pro iOS koupených přes Volume Purchase Program (VPP).

### <a name="new-ios-device-action------1244701---"></a>Nová akce pro zařízení s iOSem  <!-- 1244701 -->
Zařízení s iOSem 10.3, která jsou pod dohledem, je možné vypnout. Tato akce vypne zařízení okamžitě, bez upozornění pro koncového uživatele. Akci **Vypnout (jen pod dohledem)** najdete ve vlastnostech zařízení, když zařízení vyberete v úloze **Zařízení**.


### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a>Intune teď poskytuje operaci přesunutí účtu <!-- 1573558, 1579830 -->
Funkce **Přesunutí účtu** migruje tenanta z jedné jednotky škálování Azure (ASU) do jiné. Funkci **Přesunutí účtu** lze použít jak pro scénář zahájený zákazníkem, kdy o přesunutí požádáte tým podpory Intune, tak pro scénář řízený společností Microsoft, kdy musí Microsoft provést úpravy služby na straně back-end. Během **Přesunutí účtu** tenant přejde do režimu jen pro čtení (ROM). Operace služby, jako je registrace, přejmenování zařízení nebo aktualizuje stavu dodržování předpisů, se během režimu jen pro čtení nezdaří.




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Přiřazení mobilních aplikací Office 365 k zařízením s iOSem a Androidem pomocí integrovaného typu aplikace <!-- 1332318 -->
**Integrovaný** typ aplikace vám usnadní vytvoření aplikací Office 365 a jejich přiřazení k zařízením s iOSem a Androidem, která spravujete. Mezi tyto aplikace O365 se řadí například Word, Excel, PowerPoint a OneDrive. K typu aplikace můžete přiřadit konkrétní aplikace a pak upravit konfiguraci informací o aplikaci.


### <a name="assignment-conflict-resolution-has-changed-for-ios-store-apps----1480316---"></a>Změna řešení konfliktních přiřazení u aplikací pro iOS Store <!-- 1480316 -->
Koncoví uživatelé mohli zaznamenat změnu v dostupnosti aplikací pro iOS Store. V současné době se aplikace, která je přiřazená ke dvěma skupinám a u které došlo ke konfliktu mezi přiřazeními **Povinné a K dispozici** a **Neužívá se**, nastaví na **Povinné a K dispozici**. Po této změně se aplikace, u které dojde k takovému konfliktu, nastaví na **Neužívá se**.

Změna řeší nejasnosti v případě, kdy je jedna aplikace přiřazena k více skupinám s různými záměry aplikace.

Pokud byste chtěli aplikaci zpřístupnit na portálu pro informační pracovníky a na Portálu společnosti před listopadovým vydáním služby, máte dvě možnosti:

1. Odeberte u skupiny přiřazení **Neužívá se**.
2. Vytvořte novou skupinu, která nezahrnuje členy s přiřazeným záměrem **Povinné a K dispozici**, a přiřaďte tuto skupinu jako **Neužívá se**.

Další informace najdete v článku [Přiřazení aplikací do skupin pomocí Microsoft Intune](apps-deploy.md).

> [!Note]
> Po vydání už nebudete moct v klasické konzole Intune zobrazit ani změnit přiřazení aplikací správy mobilních zařízení. K přiřazení aplikací ale můžete použít konzolu Azure nebo rozhraní Intune Graph API.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731---"></a>Oddělená správa zařízení s Androidem for Work od zařízení s Androidem <!-- 1490731 -->
Intune bude podporovat správu registrace zařízení s Androidem for Work odděleně od platformy Android. Tato nastavení se spravují v části **Registrace zařízení** > **Omezení registrace** > **Omezení typů zařízení**. (Dříve se nacházela v části **Registrace zařízení** > **Registrace Androidu for Work** > **Nastavení registrace Android for Work**.)

Ve výchozím nastavení budou nastavení zařízení s Androidem for Work stejná jako nastavení zařízení s Androidem. Po změně nastavení Androidu for Work tomu už tak nebude.
 
Pokud zablokujete registraci Androidu for Work u osobních zařízení, budou se jako Android for Work moct zaregistrovat jenom firemní zařízení s Androidem.

Při práci s novými nastaveními vezměte v úvahu tyto informace:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Pokud jste ještě nikdy nepoužili registraci Androidu for Work
Nová platforma Android for Work je ve výchozím nastavení omezení typů zařízení zablokovaná. Jakmile začnete funkci používat, můžete zařízením povolit, aby se zaregistrovala v Androidu for Work. Uděláte to tak, že změníte výchozí omezení typu zařízení nebo vytvoříte nové, které bude mít přednost před výchozím omezením.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Pokud jste už registraci Androidu for Work použili
Pokud jste už platformu používali, závisí vaše situace na nastavení, která jste zvolili:

| Nastavení | Stav Androidu for Work ve výchozím omezení typu zařízení | Poznámky |
| --- | --- | --- |
| **Spravovat všechna zařízení jako Android for Work** | Blokované | Všechna zařízení s Androidem se musí zaregistrovat bez Androidu for Work. |
| **Spravovat podporovaná zařízení jako Android for Work** | Povoleno | Všechna zařízení s Androidem, která podporují Android for Work, se musí zaregistrovat s Androidem for Work. |
| **Spravovat podporovaná zařízení pro uživatele v těchto skupinách jako Android for Work** | Blokované | Vytvořila se samostatná zásada omezení typu zařízení, která přepíše výchozí zásadu. Tato zásada definuje skupiny, které jste dříve vybrali a povolili jim registraci Androidu for Work. Uživatelé ve vybraných skupinách budou moct dál zaregistrovat svoje zařízení s Androidem for Work. Žádní jiní uživatelé se v Androidu for Work nebudou moct zaregistrovat. |

Ve všech případech se vaše zamýšlená regulace zachová. K tomu, aby se zachovala možnost globálního používání Androidu for Work ve vašem prostředí nebo možnost používání této platformy konkrétními skupinami, nevyžadujeme z vaší strany žádnou akci.

Tyto změny začneme zavádět od listopadové aktualizace, ale než se promítnou u vašeho účtu, může to chvíli trvat. Jakmile tyto změny začnou platit i pro váš účet, pošleme vám oznámení s potvrzením přes portál Office 365.


### <a name="configure-an-ios-app-pin----1586774---"></a>Konfigurace kódu PIN pro aplikaci pro iOS <!-- 1586774 -->
Už brzy budete moct u cílených aplikací pro iOS vyžadovat kód PIN. Na portálu Azure Portal můžete nakonfigurovat požadavek na kód PIN a datum vypršení jeho platnosti (ve dnech). V případě potřeby bude uživatel muset nastavit a použít nový kód PIN, aby se dostal k aplikaci pro iOS. Tuto funkci budou podporovat jenom aplikace pro iOS, u kterých je povolená ochrana aplikace pomocí sady Intune App SDK.

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>Aktualizace uživatelského prostředí aplikace Portál společnosti pro iOS <!--1412866-->

Připravujeme k vydání důležitou aktualizaci uživatelského prostředí aplikace Portál společnosti pro iOS. Tato aktualizace bude mít zcela přepracovaný vizuální design, který bude zahrnovat modernizaci vzhledu a chování a lepší použitelnost a přístupnost. Všechny aktuální funkce aplikace Portál společnosti pro iOS budou zachované.

V rámci programu Apple TestFlight vám nabízíme předprodejní verzi aktualizované aplikace Portál společnosti pro iOS, abyste si ji mohli vyzkoušet a sdělit nám svoje názory. Pro přístup k programu TestFlight se zaregistrujte na https://aka.ms/intune_ios_cp_testflight. 

![obrázky upoutávek na novou aplikaci Portál společnosti pro iOS](./media/ios-cp-app-redesign-1801-teaser.png)


<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Webové stránky Azure Active Directory můžou vyžadovat aplikaci Intune Managed Browser a podporovat jednotné přihlašování pro Managed Browser (Public Preview) <!-- 710595 -->   
Pomocí Azure Active Directory (Azure AD) budete moct přístup k webovým stránkám na mobilních zařízeních omezit na aplikaci Intune Managed Browser. V Managed Browseru zůstanou data webových stránek zabezpečená a oddělená od osobních dat koncových uživatelů. Kromě toho bude Managed Browser podporovat možnosti jednotného přihlašování pro weby chráněné pomocí Azure AD. Přihlášení k Managed Browseru nebo jeho používání na zařízení s jinou aplikací, kterou spravuje Intune, umožňuje, aby měl Managed Browser přístup k podnikovým webům chráněným pomocí Azure AD, aniž by uživatel musel zadávat své přihlašovací údaje. Tato funkce se vztahuje na weby jako Outlook Web Access (OWA) a SharePoint Online i na jiné podnikové weby jako prostředky v intranetu, ke kterým se přistupuje prostřednictvím proxy aplikace Azure.


<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Podpora zásad upgradu edice Windows 10 <!-- 903672(archived), 1119689 -->  
Budete moci vytvořit zásady upgradu edice Windows 10, které zařízení s Windows 10 upgradují na Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education a Windows 10 Professional Education N. Podrobnosti o upgradech edic Windows 10 najdete v článku [Jak nakonfigurovat upgrady edicí Windows 10](edition-upgrade-configure-windows-10.md).




<!-- the following are present prior to 1709 -->


### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune App Protection a nástroje pro vývoj Citrix MDX <!-- 709185 -->
Můžete spravovat zařízení a aplikace s kombinací Citrix XenMobile MDX a Microsoft Intune. To umožňuje spravovat aplikace pomocí zásad ochrany aplikací Intune při použití technologie mVPN společnosti Citrix.

Můžete najít úložiště kódu, které obsahuje Intune App Wrapping Tool a sadu Intune App SDK pro iOS a Android, a využít integraci s technologií Citrix MDX mVPN.




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Přesměrování uživatelů macOS na naši novou aplikaci Portál společnosti <!--1380728-->   
Když se koncový uživatel přihlásí k webu Portál společnosti, aby zaregistroval svoje zařízení s macOS, bude přesměrován na to, aby proces dokončil stažením nové aplikace Portál společnosti pro macOS. K tomu dojde na zařízeních s macOS používajících OS X El Capitan 10.11 nebo novější. 



<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Podpora Intune Managed Browser pro iOS a Android <!-- 1374196 -->
Od října 2017 bude aplikace Intune Managed Browser pro Android podporovat jen zařízení se systémem Android 4.4 a novější. Aplikace Intune Managed Browser pro iOS bude podporovat jen zařízení se systémem iOS 9.0 a novější. Starší verze systému Android a iOS budou moct Managed Browser dál používat, ale nepůjde do nich nainstalovat nové verze této aplikace a nebudou mít přístup ke všem jejím možnostem. Doporučujeme vám tato zařízení aktualizovat na podporovanou verzi operačního systému.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Vylepšená chybová zpráva, když uživatel dosáhne maximálního povoleného počtu zařízení k registraci <!-- 1270370 -->
Místo obecné chybové zprávy se koncovým uživatelům používajícím zařízení s Androidem zobrazí popisná chybová zpráva, na kterou se dá reagovat: „Zaregistrovali jste maximální počet zařízení, který povoluje váš IT správce. Odeberte prosím zaregistrované zařízení, nebo se obraťte s žádostí o pomoc na IT správce.“




## <a name="notices"></a>Sdělení

V současné době nejsou aktivní žádná sdělení.




### <a name="see-also"></a>Viz taky
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).
