---
title: "Časná edice"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 35bf193563deb34ac59df245c622bbc011d80b76
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/08/2017
---
# <a name="the-early-edition-for-microsoft-intune---december-2017"></a>Časná edice pro Microsoft Intune – prosinec 2017

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

### <a name="app-protection-policies-----679615---"></a>Zásady ochrany aplikací  <!-- 679615 -->
Zásady Intune App Protection nabízejí možnost vytvoření globálních výchozích zásad, které rychle aktivují ochranu přes všechny uživatele v celém tenantovi.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Odvolání aplikací pro iOS koupených přes Volume Purchase Program <!-- 820863 -->
Pro dané zařízení, které má jednu nebo více aplikací pro iOS koupených přes Volume Purchase Program (VPP), budete moct odvolat přidruženou licenci aplikace na základě zařízení. Odvoláním licence aplikace se příslušná aplikace VPP neodinstaluje ze zařízení. Pokud chcete odinstalovat aplikaci VPP, musíte nastavit akci přiřazení na **Odinstalovat**. Další informace najdete v tématu [Správa aplikací pro systém iOS nakoupených prostřednictvím programu hromadného nákupu pomocí Microsoft Intune](vpp-apps-ios.md).

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Odvolání licencí pro token Volume Purchase Program pro iOS <!-- 820870 -->
Pro daný token VPP budete moct odvolat licenci všech aplikací pro iOS koupených přes Volume Purchase Program (VPP).

### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Odstranění tokenu Volume Purchase Program pro iOS <!-- 820879 -->
Pomocí konzoly budete moct odstranit token programu Volume Purchase Program (VPP) pro iOS. To může být nutné v případě, že máte duplicitní instance tokenu VPP.

### <a name="network-access-control-nac-device-check-in-reporting-----1232250---"></a>Vytváření sestav ohlášení zařízení pro řízení přístupu k síti (NAC) <!-- 1232250 -->
Před touto změnou nemohli správci IT určit ze strany Intune, zda zařízení spravované pomocí NAC komunikovalo s jejich řešením NAC nebo ne. Když zařízení spravované pomocí NAC nekomunikuje s daným řešením NAC, považuje řešení NAC dané zařízení za nevyhovující, zablokuje ho a následně ho zablokují i zásady podmíněného přístupu, které jsou závislé na stavu dodržování předpisů pro zařízení.

Díky této změně mohou správci IT sledovat, která zařízení spravovaná pomocí NAC úspěšně komunikovala s jejich řešením NAC a která ne. Tento nový prvek se skládá z dvou nových funkcí monitorování umístěných v úloze dodržování předpisů zařízení v Intune. Viz statistika níže:
- **Průměrný počet volání NAC za poslední hodinu**
- **Poslední příchozí žádost NAC (datum a čas)**

### <a name="new-ios-device-action------1244701---"></a>Nová akce pro zařízení s iOSem  <!-- 1244701 -->
Zařízení s iOSem 10.3, která jsou pod dohledem, je možné vypnout. Tato akce vypne zařízení okamžitě, bez upozornění pro koncového uživatele. Akci **Vypnout (jen pod dohledem)** najdete ve vlastnostech zařízení, když zařízení vyberete v úloze **Zařízení**.

### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755-eeready---"></a>Podpora více konektorů pro zpracování certifikátů SCEP a PFX <!-- 1361755 eeready -->
Zákazníci, kteří používají místní konektor NDES k dodání certifikátů do zařízení, budou moci konfigurovat více konektorů v jednom tenantovi.

Tato nová funkce podporuje následující scénář:

- **Vysoká dostupnost**

    Každý konektor NDES si vyžádá žádosti o certifikát z Intune.  Pokud jeden konektor NDES přejde do offline režimu, může další konektor dál zpracovávat žádosti.

### <a name="new-automatic-redeployment-setting----1469168---"></a>Nové nastavení automatického opětovného nasazení <!-- 1469168 -->
Toto nastavení umožňuje uživatelům s právy správce odstranit všechna uživatelská data a nastavení pomocí **CTRL + Win + R** na zamykací obrazovce zařízení. Zařízení se znovu automaticky nakonfiguruje zaregistruje do správy.

Toto nastavení najdete v části Windows 10 -> Omezení zařízení -> Obecné -> Automatické opětovné nasazení.

### <a name="install-office-apps-on-macos-devices----1494311---"></a>Instalace aplikací Office na zařízeních macOS <!-- 1494311 -->
Budete moct nainstalovat aplikace Office v zařízeních macOS. Tento nový typ aplikace vám umožní nainstalovat Word, Excel, PowerPoint, Outlook a OneNote. Tyto aplikace se také dodávají s nástrojem Microsoft AutoUpdater (MAU), abyste je měli zabezpečené a aktuální.

### <a name="surface-hub-resource-account-supported----1566442-eeready---"></a>Podpora účtu zdroje pro Surface Hub <!-- 1566442 eeready -->
Přibude nová akce zařízení, která umožní správcům definovat a aktualizovat účet zdroje přidružený k zařízení Surface Hub.

Surface Hub využívá účet zdroje k ověření přes Skype nebo Exchange, aby bylo možné se připojit ke schůzce. Můžete vytvořit jedinečný účet zdroje, takže se Surface Hub zobrazí ve schůzce jako konferenční místnost. Účet zdroje se například může zobrazit jako *Konferenční místnost B41/6233*. Účet zdroje (známý také jako účet zařízení) pro Surface Hub je obvykle potřeba nakonfigurovat pro umístění konferenční místnosti a v případě, kdy je nutné změnit další parametry účtu zdroje.

Pokud chtějí správci aktualizovat účet zdroje v zařízení, musí zadat aktuální přihlašovací údaje služby Active Directory nebo Azure Active Directory přidružené k tomuto zařízení. Pokud je na zařízení aktivní rotace hesla, musí správce přejít do Azure Active Directory a heslo najít.

> [!NOTE]
> Všechna pole se odešlou ve skupině a přepíšou všechna dříve nakonfigurovaná pole. Také prázdná pole mohou přepsat existující pole.

Správci mohou nakonfigurovat následující nastavení:

- **Účet zdroje**  

   - **Uživatel služby Active Directory**   
   Název_domény\uživatelské_jméno nebo hlavní název uživatele (UPN): user@domainname.com
   - **Heslo**


- **Volitelné parametry účtu zdroje** (musí se nastavit pomocí daného účtu zdroje)
   - **Období rotace hesla**   
     Zajišťuje, že Surface Hub automaticky aktualizuje heslo k účtu každý týden z bezpečnostních důvodů. Pokud chcete nakonfigurovat jakékoli parametry po zapnutí této možnosti, musíte nejprve resetovat heslo k účtu ve službě Azure Active Directory.

   - **Adresa protokolu SIP (Session Initiation Protocol)**    
     Používá se pouze v případě nezdařeného automatického zjišťování.

   - **E-mail**    
     E-mailová adresu účtu zdroje nebo zařízení.

   - **Server Exchange**    
     Je potřeba, pouze pokud se nezdaří automatické zjišťování.

   - **Synchronizace kalendáře**    
     Určuje, zda je povolená synchronizace kalendáře a dalších služeb serveru Exchange. Například: synchronizace schůzek.

### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a>Intune teď poskytuje operaci přesunutí účtu <!-- 1573558, 1579830 -->
Funkce **Přesunutí účtu** migruje tenanta z jedné jednotky škálování Azure (ASU) do jiné. Funkci **Přesunutí účtu** lze použít jak pro scénář zahájený zákazníkem, kdy o přesunutí požádáte tým podpory Intune, tak pro scénář řízený společností Microsoft, kdy musí Microsoft provést úpravy služby na straně back-end. Během **Přesunutí účtu** tenant přejde do režimu jen pro čtení (ROM). Operace služby, jako je registrace, přejmenování zařízení nebo aktualizuje stavu dodržování předpisů, se během režimu jen pro čtení nezdaří.

### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Nové nastavení v profilu konfigurace zařízení v aplikaci Centrum zabezpečení v programu Windows Defender (WDSC) <!-- 1335507 -->
Intune přidá nový oddíl nastavení profilu konfigurace zařízení v části Endpoint Protection s názvem **Centrum zabezpečení v programu Windows Defender**. Správci IT mohou nakonfigurovat, ke kterým pilířům aplikace Centrum zabezpečení v programu Windows Defender mají mít koncoví uživatelé přístup. Pokud správce IT skryje pilíř v aplikaci Centrum zabezpečení v programu Windows Defender, nezobrazují se v zařízení uživatele žádná oznámení související s skrytým pilířem.

Toto jsou pilíře, které mohou správci skrýt z nastavení profilu konfigurace zařízení v aplikaci Centrum zabezpečení v programu Windows Defender:
- Ochrana proti virům a ohrožením
- Výkon a stav zařízení
- Ochrana brány firewall a sítě
- Aplikace a ovládací prvek Prohlížeč
- Možnosti pro rodinu

Správci IT mohou také přizpůsobit výběr oznámení, která budou uživatelé dostávat. Můžete například nakonfigurovat, jestli uživatelé dostanou všechna oznámení vygenerovaná viditelnými pilíři WDSC nebo pouze závažná oznámení. Nezávažná oznámení zahrnují pravidelné přehledy aktivity nástroje Antivirová ochrana v programu Windows Defender a oznámení o času dokončení kontroly. Všechna další oznámení se považují za závažná. Kromě toho můžete také upravit samotný obsah oznámení. Například můžete přidat kontaktní informace oddělení IT, která se vloží do oznámení publikovaných v zařízeních uživatelů.




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Přiřazení mobilních aplikací Office 365 k zařízením s iOSem a Androidem pomocí integrovaného typu aplikace <!-- 1332318 -->
**Integrovaný** typ aplikace vám usnadní vytvoření aplikací Office 365 a jejich přiřazení k zařízením s iOSem a Androidem, která spravujete. Mezi tyto aplikace O365 se řadí například Word, Excel, PowerPoint a OneDrive. K typu aplikace můžete přiřadit konkrétní aplikace a pak upravit konfiguraci informací o aplikaci.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Podpora jednotného přihlašování pro iOS <!-- 1333645 -->  
Pro uživatele iOSu budete moct využít jednotné přihlašování. Díky této aktualizaci konfigurace datové části fungují aplikace pro iOS, které jsou naprogramovány tak, aby v datové části jednotného přihlašování hledaly přihlašovací údaje uživatele. Ke konfiguraci hlavního názvu a sféry můžete použít také hlavní název uživatele (UPN) a ID zařízení v Intune.

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Povolení textového protokolu ze spravovaných aplikací <!-- 1414050  -->
Aplikace spravované prostřednictvím sady Intune App SDK budou moct posílat SMS zprávy.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Vzdálené uzamčení spravovaných zařízení s macOS přes Intune <!-- 1437691 -->
Ztracené zařízení s macOS budete moct zamknout a nastavit pro ně 6místný číselný kód PIN pro obnovení. Když se zařízení zamkne, v okně **přehledu zařízení** se bude zobrazovat kód PIN, dokud se nepošle jiná akce zařízení.

Další informace si můžete přečíst v článku [Vzdálené uzamčení spravovaných zařízení přes Intune](device-remote-lock.md).


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

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Přidání aplikace Najít iPhone pro osobní zařízení <!--1427287-->
Budete si moct zobrazit, zda je u zařízení s iOSem zapnutý zámek aktivace. Tato funkce se dříve nacházela v Intune na portálu Classic.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Webové stránky Azure Active Directory můžou vyžadovat aplikaci Intune Managed Browser a podporovat jednotné přihlašování pro Managed Browser (Public Preview) <!-- 710595 -->   
Pomocí Azure Active Directory (Azure AD) budete moct přístup k webovým stránkám na mobilních zařízeních omezit na aplikaci Intune Managed Browser. V Managed Browseru zůstanou data webových stránek zabezpečená a oddělená od osobních dat koncových uživatelů. Kromě toho bude Managed Browser podporovat možnosti jednotného přihlašování pro weby chráněné pomocí Azure AD. Přihlášení k Managed Browseru nebo jeho používání na zařízení s jinou aplikací, kterou spravuje Intune, umožňuje, aby měl Managed Browser přístup k podnikovým webům chráněným pomocí Azure AD, aniž by uživatel musel zadávat své přihlašovací údaje. Tato funkce se vztahuje na weby jako Outlook Web Access (OWA) a SharePoint Online i na jiné podnikové weby jako prostředky v intranetu, ke kterým se přistupuje prostřednictvím proxy aplikace Azure.


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
