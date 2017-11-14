---
title: "Časná edice"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 11/6/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f7cc595655950ef1bf2586e939b6f02e270e7afc
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/08/2017
---
# <a name="the-early-edition-for-microsoft-intune---november-2017"></a>Časná edice Microsoft Intune – listopad 2017

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


### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Přiřazení mobilních aplikací Office 365 k zařízením s iOSem a Androidem pomocí integrovaného typu aplikace <!-- 1332318 -->
**Integrovaný** typ aplikace vám usnadní vytvoření aplikací Office 365 a jejich přiřazení k zařízením s iOSem a Androidem, která spravujete. Mezi tyto aplikace O365 se řadí například Word, Excel, PowerPoint a OneDrive. K typu aplikace můžete přiřadit konkrétní aplikace a pak upravit konfiguraci informací o aplikaci.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Podpora jednotného přihlašování pro iOS <!-- 1333645 -->  
Pro uživatele iOSu budete moct využít jednotné přihlašování. Díky této aktualizaci konfigurace datové části fungují aplikace pro iOS, které jsou naprogramovány tak, aby v datové části jednotného přihlašování hledaly přihlašovací údaje uživatele. Ke konfiguraci hlavního názvu a sféry můžete použít také hlavní název uživatele (UPN) a ID zařízení v Intune.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>Rozhraní API inventáře aplikací pro iOS 11 pro ochranu před mobilními hrozbami <!-- 1391759 -->
Intune shromažďuje informace o inventáři aplikací ze zařízení jak v osobním, tak i firemním vlastnictví, a zpřístupňuje je zprostředkovatelům služby ochrany před mobilními hrozbami, jako je třeba aplikace Lookout for Work. Inventář aplikací budete moct shromažďovat od uživatelů zařízení s iOSem 11 a novějším.

**Inventář aplikací**  
Inventáře ze zařízení s iOSem 11 a novějším v osobním i firemním vlastnictví se posílají zprostředkovateli služby ochrany před mobilními hrozbami. Data v inventáři aplikací zahrnují tyto údaje:

 - ID aplikace
 - Verze aplikace
 - Krátká verze aplikace
 - Název aplikace
 - Velikost sady prostředků aplikace
 - Dynamická velikost aplikace
 - Zda je aplikace ověřena nebo ne
 - Zda je aplikace spravována nebo ne

### <a name="audit-updates----1412961---"></a>Aktualizace auditu <!-- 1412961 -->  
Auditování Intune poskytuje záznam o operacích změn souvisejících s Intune.  Zachycují se a po dobu jednoho roku uchovávají veškeré operace vytvoření, aktualizace, odstranění a odebrání.  Azure Portal zobrazuje data auditování v každé úloze za posledních 30 dnů, která se dají filtrovat.  Příslušné rozhraní Graph API umožňuje načíst data auditování uložená za poslední rok. 

Auditování najdete ve skupině **MONITOROVAT**. Pro každou úlohu existuje položka nabídky **Protokoly auditu**.   

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Povolení textového protokolu ze spravovaných aplikací <!-- 1414050  -->
Aplikace spravované prostřednictvím sady Intune App SDK budou moct posílat SMS zprávy.

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Vzdálené restartování zařízení s iOSem (jenom v režimu pod dohledem) <!-- 1424595 -->
Pomocí akce zařízení budete moct aktivovat restartování zařízení s iOSem 10.3 a novějším, které je v režimu pod dohledem. Další informace o použití akce restartování zařízení najdete v tématu [Vzdálené restartování zařízení přes Intune](device-restart.md).

> [!Note]  
> Tento příkaz vyžaduje, aby byla zařízení v režimu pod dohledem, a přístupová práva k **zámku zařízení**. Zařízení se restartuje okamžitě. Zařízení s iOSem zamčená pomocí hesla se po restartování k síti Wi-Fi znovu nepřipojí a je možné, že po restartování nebudou moct komunikovat se serverem.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Vzdálené uzamčení spravovaných zařízení s macOS přes Intune <!-- 1437691 -->
Ztracené zařízení s macOS budete moct zamknout a nastavit pro ně 6místný číselný kód PIN pro obnovení. Když se zařízení zamkne, v okně **přehledu zařízení** se bude zobrazovat kód PIN, dokud se nepošle jiná akce zařízení.

Další informace si můžete přečíst v článku [Vzdálené uzamčení spravovaných zařízení přes Intune](device-remote-lock.md).

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings------1455974-----"></a>Nastavení četnosti hlášení Rozšířené ochrany před internetovými útoky v programu Windows Defender <!--- 1455974  --->
Služba Rozšířená ochrana před internetovými útoky v programu Windows Defender umožňuje správcům spravovat četnost hlášení u spravovaných zařízení. Pomocí nové možnosti **Zvýšit četnost hlášení telemetrie** služba Rozšířená ochrana před internetovými útoky v programu Windows Defender častěji shromažďuje a vyhodnocuje rizika. Výchozí nastavení hlášení optimalizuje rychlost a výkon. Zvýšení četnosti hlášení může být velmi cennou pomůckou pro zařízení s vysokým rizikem. Toto nastavení najdete v profilu **Ochrana ATP v programu Windows Defender** v části **Konfigurace zařízení**.

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

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Podpora více konektorů Služby zápisu síťových zařízení (NDES) <!-- 1528104 -->
Služba zápisu síťových zařízení umožňuje, aby mobilní zařízení spuštěná bez doménových přihlašovacích údajů získala certifikáty založené na protokolu SCEP (Simple Certificate Enrollment Protocol). Od této aktualizace se bude podporovat více konektorů NDES.

### <a name="new-scep-profile-details-supported----1559808---"></a>Podpora nových podrobností profilu SCEP <!-- 1559808 -->
Při vytváření profilu SCEP na platformách Windows, iOS, macOS a Android budou moct správci nakonfigurovat další nastavení.  Správci můžou nastavit IMEI, sériové číslo nebo běžný název včetně e-mailu ve formátu názvu subjektu.

### <a name="configure-an-ios-app-pin----1586774---"></a>Konfigurace kódu PIN pro aplikaci pro iOS <!-- 1586774 -->
Už brzy budete moct u cílených aplikací pro iOS vyžadovat kód PIN. Na portálu Azure Portal můžete nakonfigurovat požadavek na kód PIN a datum vypršení jeho platnosti (ve dnech). V případě potřeby bude uživatel muset nastavit a použít nový kód PIN, aby se dostal k aplikaci pro iOS. Tuto funkci budou podporovat jenom aplikace pro iOS, u kterých je povolená ochrana aplikace pomocí sady Intune App SDK.

### <a name="retain-data-during-a-factory-reset-----1588489---"></a>Zachování dat při obnovení továrního nastavení <!-- 1588489 -->
Přidáváme podporu nové funkce při obnovení továrního nastavení Windows. Správci teď můžou určit, jestli se při obnovení továrního nastavení data registrace zařízení a další zřízená data v zařízení zachovají. 
 
Při obnovení továrního nastavení se zachovají následující data:
- Uživatelské účty přidružené k zařízení
- Stav počítače (připojení k doméně, AADJ)
- Registrace správy mobilních zařízení
- Aplikace nainstalované výrobcem OEM (aplikace ze Storu a aplikace Win32)
- Profil uživatele
- Uživatelská data mimo profil uživatele
- Automatické přihlášení uživatele
 
Nezachovají se následující data:
- Soubory uživatele
- Aplikace nainstalované uživatelem (aplikace ze Storu a aplikace Win32)
- Nevýchozí nastavení zařízení 

### <a name="app-install-status-report-now-a-bar-chart----1249446---"></a>Sestava stavu instalace aplikace nově ve formě pruhového grafu <!-- 1249446 -->  
Sestava **Stav instalace aplikace** dostupná pro každou aplikaci v seznamu **Aplikace** v úloze **Mobilní aplikace** se už brzo bude vykreslovat jako pruhový graf.

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Přidání aplikace Najít iPhone pro osobní zařízení <!--1427287-->
Budete si moct zobrazit, zda je u zařízení s iOSem zapnutý zámek aktivace. Tato funkce se dříve nacházela v Intune na portálu Classic.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Omezení registrace přiřazená ke skupinám <!-- 747598 -->
Jako správce Intune budete moct vytvořit vlastní omezení registrace typů zařízení a limitu počtu zařízení u skupin uživatelů.
 
Intune Azure Portal vám umožňuje vytvořit až 25 instancí každého typu omezení, které pak můžete přiřadit ke skupinám uživatelů. Omezení přiřazená ke skupinám přepíší výchozí omezení.
 
Všechny instance typů omezení se budou uchovávat v seznamu se striktním pořadím. Toto pořadí definuje hodnotu priority pro případ řešení konfliktů. U uživatele, na něhož se vztahuje více instancí omezení, se uplatní jenom instance s nejvyšší prioritou. Prioritu dané instance můžete změnit tak, že ji přetáhnete na jiné místo v seznamu. 
 
Tato funkce bude vydána spolu s migrací nastavení Androidu for Work z nabídky registrace Androidu for Work do nabídky Omezení registrace. Tato migrace může trvat několik dnů, a proto je možné, že v rámci listopadové verze se nejprve upgradují jiné části vašeho účtu a teprve poté se u omezení registrace povolí přiřazení skupin.

### <a name="windows-10-update-ring-assignments-are-displayed----1621837---"></a>Zobrazení přiřazení aktualizačního kanálu Windows 10 <!-- 1621837 -->
Při **řešení potíží** u aktuálně zobrazeného uživatele si budete moct zobrazit veškerá přiřazení aktualizačních kanálů Windows 10.  



<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Webové stránky Azure Active Directory můžou vyžadovat aplikaci Intune Managed Browser a podporovat jednotné přihlašování pro Managed Browser (Public Preview) <!-- 710595 -->   
Pomocí Azure Active Directory (Azure AD) budete moct přístup k webovým stránkám na mobilních zařízeních omezit na aplikaci Intune Managed Browser. V Managed Browseru zůstanou data webových stránek zabezpečená a oddělená od osobních dat koncových uživatelů. Kromě toho bude Managed Browser podporovat možnosti jednotného přihlašování pro weby chráněné pomocí Azure AD. Přihlášení k Managed Browseru nebo jeho používání na zařízení s jinou aplikací, kterou spravuje Intune, umožňuje, aby měl Managed Browser přístup k podnikovým webům chráněným pomocí Azure AD, aniž by uživatel musel zadávat své přihlašovací údaje. Tato funkce se vztahuje na weby jako Outlook Web Access (OWA) a SharePoint Online i na jiné podnikové weby jako prostředky v intranetu, ke kterým se přistupuje prostřednictvím proxy aplikace Azure.

### <a name="troubleshoot-enrollment-issues------746324----"></a>Řešení potíží s registrací  <!--- 746324 --->  
Pracovní prostor Řešení potíží zobrazí problémy s registrací uživatelů. Podrobnosti o problému a navrhované nápravné kroky můžou správcům a pracovníkům technické podpory pomoct problém vyřešit. Některé problémy s registrací nejsou zaznamenané a k některým chybám nemusí návrhy k odstranění problému existovat.


















<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Podpora zásad upgradu edice Windows 10 <!-- 903672(archived), 1119689 -->  
Budete moci vytvořit zásady upgradu edice Windows 10, které zařízení s Windows 10 upgradují na Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education a Windows 10 Professional Education N. Podrobnosti o upgradech edic Windows 10 najdete v článku [Jak nakonfigurovat upgrady edicí Windows 10](edition-upgrade-configure-windows-10.md).




<!-- the following are present prior to 1709 -->



### <a name="android-for-work-support-for-lookout----1087312---"></a>Podpora Androidu for Work pro Lookout <!-- 1087312 -->   
Při použití aplikace Lookout for Work bude konektor Intune s Lookoutem podporovat zařízení s Androidem for Work. Aplikaci Lookout můžete nasadit uvnitř nebo vně kontejneru.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune App Protection a nástroje pro vývoj Citrix MDX <!-- 709185 -->
Můžete spravovat zařízení a aplikace s kombinací Citrix XenMobile MDX a Microsoft Intune. To umožňuje spravovat aplikace pomocí zásad ochrany aplikací Intune při použití technologie mVPN společnosti Citrix.

Můžete najít úložiště kódu, které obsahuje Intune App Wrapping Tool a sadu Intune App SDK pro iOS a Android, a využít integraci s technologií Citrix MDX mVPN.


### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Podpora vysoké dostupnosti místního konektoru Exchange Connector  <!-- 676614 -->   
U místního konektoru Exchange Connector máte možnost mít několik rolí serveru pro klientský přístup (CAS). Například pokud hlavní server pro klientský přístup selže, konektor Exchange Connector obdrží výzvu, aby využíval jiné servery pro klientský přístup. Tato funkce zajišťuje, že se služba nepřeruší.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Sada System Center Operations Manager Management Pack pro konektor Exchange Connector <!-- 885457 -->   
Pro pomoc s analýzou protokolů konektoru Exchange Connector bude dostupná sada System Center Operations Manager Management Pack pro konektor Exchange Connector. Pokud potřebujete řešit potíže, tento Management Pack poskytuje různé možnosti monitorování Intune.





## <a name="intune-apps"></a>Aplikace Intune

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Pomoc uživatelům při řešení problémů vlastními silami v aplikaci Portál společnosti pro Android <!---1573324, 1573150, 1558616, 1564878--->
Aplikace Portál společnosti pro Android přidává pokyn pro koncové uživatele, který jim pomůže porozumět novým případům použití a v případě potřeby i vyřešit problém vlastními silami. 

- Zobrazí se nová zpráva s vysvětlením, že se nasadily zásady dodržování předpisů pro šifrování, ale že [výrobce zařízení nešifruje zařízení](/intune-user-help/your-device-appears-encrypted-but-cp-says-otherwise-android) v souladu s [doporučenými pokyny Googlu](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setStorageEncryption(android.content.ComponentName, boolean).
- Koncoví uživatelé budou odkázáni na (portál Azure Active Directory)[https://account.activedirectory.windowsazure.com/r/#/profile], kde odeberou zařízení v případě, že dosáhli maximálního počtu zařízení, která mají povoleno přidat. 
- Koncovým uživatelům se zobrazí postup, který jim pomůže [opravit chyby aktivace na zařízení Samsung KNOX](https://go.microsoft.com/fwlink/?linkid=859718) nebo [vypnout režim snížené spotřeby](/intune-user-help/power-saving-mode-android). Pokud ani jedno z řešení jejich problém nevyřeší, zobrazí se jim vysvětlení, jak mohou [odeslat protokoly do Microsoftu](/intune-user-help/send-logs-to-microsoft-ios). 


### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nová akce Vyřešit pro zařízení s Androidem <!---1583480--->
Aplikace Portál společnosti pro Android představuje akci Vyřešit na stránce _Aktualizovat nastavení zařízení_. Výběrem této možnosti koncový uživatel přejde přímo na nastavení, které způsobuje, že jeho zařízení nevyhovuje předpisům. V současné době aplikace Portál společnosti podporuje tuto akci u [hesla zařízení](/intune-user-help/set-your-pin-or-password-android), [šifrování zařízení](/intune-user-help/encrypt-your-device-android), [ladění USB](/intune-user-help/you-need-to-turn-off-usb-debugging-android) a u nastavení [Neznámé zdroje](/intune-user-help/you-need-to-turn-off-unknown-sources-android). 




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Přesměrování uživatelů macOS na naši novou aplikaci Portál společnosti <!--1380728-->   
Když se koncový uživatel přihlásí k webu Portál společnosti, aby zaregistroval svoje zařízení s macOS, bude přesměrován na to, aby proces dokončil stažením nové aplikace Portál společnosti pro macOS. K tomu dojde na zařízeních s macOS používajících OS X El Capitan 10.11 nebo novější. 


<!-- the following are present prior to 1710 -->



### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Aplikace, které jsou dostupné s registrací nebo bez registrace, lze nyní nainstalovat bez výzvy k registraci <!-- 1334712 -->
Firemní aplikace, které byly u aplikace Portál společnosti pro Android zpřístupněny s registrací nebo bez registrace, lze nainstalovat bez výzvy k registraci.


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Podpora Intune Managed Browser pro iOS a Android <!-- 1374196 -->
Od října 2017 bude aplikace Intune Managed Browser pro Android podporovat jen zařízení se systémem Android 4.4 a novější. Aplikace Intune Managed Browser pro iOS bude podporovat jen zařízení se systémem iOS 9.0 a novější. Starší verze systému Android a iOS budou moct Managed Browser dál používat, ale nepůjde do nich nainstalovat nové verze této aplikace a nebudou mít přístup ke všem jejím možnostem. Doporučujeme vám tato zařízení aktualizovat na podporovanou verzi operačního systému.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Vylepšená chybová zpráva, když uživatel dosáhne maximálního povoleného počtu zařízení k registraci <!-- 1270370 -->
Místo obecné chybové zprávy se koncovým uživatelům zobrazí popisná chybová zpráva, na kterou se dá reagovat: „Zaregistrovali jste maximální počet zařízení, který povoluje váš IT správce. Odeberte prosím zaregistrované zařízení, nebo se obraťte s žádostí o pomoc na IT správce.“




## <a name="notices"></a>Sdělení

V současné době nejsou aktivní žádná sdělení.




### <a name="see-also"></a>Související témata
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new.md).
