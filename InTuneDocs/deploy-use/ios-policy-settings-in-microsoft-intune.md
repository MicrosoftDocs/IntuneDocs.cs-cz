---
title: "Nastavení zásad pro iOS | Microsoft Intune"
description: "Vytvořte zásady, které řídí nastavení a funkce na zařízeních s iOSem, která spravujete pomocí Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: dfde68e4ef889ba881ff2fa93b226f879d01cbc8


---

# <a name="ios-policy-settings-in-microsoft-intune"></a>Nastavení zásad pro iOS v Microsoft Intune

Intune poskytuje řadu předdefinovaných obecných nastavení, která můžete konfigurovat v zařízeních s iOSem. Navíc můžete použít nástroj Apple Configurator k vytvoření vlastních nastavení, která nejsou k dispozici prostřednictvím Intune.

## <a name="general-configuration-policy-settings"></a>Obecná nastavení zásad konfigurace

Pomocí **zásad obecné konfigurace pro iOS** v Microsoft Intune můžete nakonfigurovat nastavení pro:

-   **Obecná nastavení zařízení a zabezpečení** Vyberte možnost ze seznamu předdefinovaných nastavení, která umožňují kontrolovat celou řadu vlastností a funkcí zařízení.

-   **Celoobrazovkový režim** Umožňuje uzamknout zařízení a povolit fungování jenom některých funkcí. Můžete třeba povolit, aby v zařízení běžela jenom jedna vámi určená spravovaná aplikace, nebo můžete na zařízení zakázat tlačítka hlasitosti. Tato nastavení se dají používat pro ukázkový model zařízení nebo pro zařízení, které je vyhrazené jenom pro jednu funkci, jako je třeba zařízení POS.

-   **Kompatibilní a nekompatibilní aplikace** Umožňuje určit seznam aplikací pro iOS, které vyhovují nebo nevyhovují předpisům ve vaší společnosti. Na zařízeních s Androidem a iOS je možné použít **aplikací nesplňujících požadavky** k zobrazení shody aplikací, které zadáte v seznamu, s aplikacemi, které si uživatelé nainstalovali (sestava neslouží ke skutečnému zablokování instalace aplikací).

> [!TIP]
> Můžete nakonfigurovat podmínky pro uživatele a zajistit tak, aby věděli, že aplikace na jejich zařízení (včetně osobních aplikací) se vyhodnotí a nekompatibilní aplikace se zablokují nebo nahlásí jako nevyhovující. Uživatelé musí přijmout tyto podmínky předtím, než můžou zaregistrovat své zařízení a používat firemní portál k získání aplikací. Další informace o podmínkách a ujednáních týkajících se použití najdete v tématu [Nastavení zásad podmínek a ujednání v Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md).

Pokud v tomto tématu není uvedené nastavení, které hledáte, je možné, že ho budete moct vytvořit pomocí vlastních zásad pro iOS, které vám umožní naimportovat nastavení vytvořená pomocí [nástroje Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). Další informace najdete v části Nastavení vlastních zásad dál v tomto tématu.

### <a name="security-settings"></a>Nastavení zabezpečení
Všechna nastavení platí pro iOS 8.0 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Vyžadovat heslo k odemknutí mobilních zařízení**|Určete, jestli uživatel při přístupu ke svému zařízení musí zadat heslo.|
|**Vyžadovaný typ hesla**|Zadejte typ hesla, které se bude vyžadovat, například jenom číslice nebo alfanumerické znaky.|
|**Požadovaný počet složitých znaků v hesle**|Zadejte počet znaků symbolu (jako například **#** nebo **@**), které musí heslo obsahovat.|
|**Minimální délka hesla**|Zadejte minimální počet znaků v hesle.|
|**Povolit jednoduchá hesla**|Umožňuje použití jednoduchých hesel, jako je třeba **0000** nebo **1234**.|
|**Počet povolených opakovaných neúspěšných přihlášení, než se zařízení vymaže**|Zadejte počet neúspěšných pokusů o přihlášení, než toto nastavení vymaže zařízení.|
|**Počet minut nečinnosti před vyžádáním hesla**<sup>1</sup>|Zadejte, jak dlouho může zařízení zůstat nečinné, než uživatel musí znovu zadat heslo.|
|**Vypršení platnosti hesla (dny)**|Zadejte počet dní, než bude nutné změnit heslo zařízení.|
|**Pamatovat si historii hesel**|Určete, jestli uživatel může použít hesla, která už použil.|
|**Pamatovat si historii hesel** – **Zabránit opětovnému použití předchozích hesel**|Zadejte počet dříve použitých hesel, která si zařízení pamatuje.|
|**Počet minut nečinnosti před vypnutím displeje**<sup>1</sup>|Zadejte počet minut, než se displej zařízení vypne.|
|**Povolit odemknutí otiskem prstu**|Povolí odemknutí zařízení otiskem prstu.|
<sup>1</sup>Pokud pro zařízení s iOSem nakonfigurujete nastavení **Počet minut nečinnosti před vypnutím displeje** a **Počet minut nečinnosti před vyžádáním hesla**, použijí se postupně. Pokud například pro obě nastavení nastavíte hodnotu **5** minut, obrazovka se po 5 minutách automaticky vypne a po dalších 5 minutách se zařízení zamkne. Pokud ale uživatel vypne obrazovku ručně, druhé nastavení se použije okamžitě. V tomto příkladě se zařízení po tom, co uživatel vypne obrazovku, zamkne po 5 minutách.

### <a name="system-settings"></a>Nastavení systému
Všechna nastavení platí pro iOS 8.0 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit snímek obrazovky**|Povolí uživateli zachytit obsah obrazovky jako obrázek.|
|**Povolit řídicí centrum na zamykací obrazovce**|Povolí uživateli přístup k aplikaci řídicího centra, když je zařízení uzamčené.|
|**Povolit zobrazení oznámení na zamykací obrazovce**|Povolí uživateli přístup k zobrazení oznámení bez odemknutí zařízení.|
|**Povolit zobrazení informací o dnešku na zamykací obrazovce**|Povolí uživateli zobrazit oznámení, když je zařízení uzamčené.|
|**Povolit nedůvěryhodné certifikáty TLS**|Povolí v zařízení nedůvěryhodné certifikáty protokolu TLS (Transport Layer Security).|
|**Povolit odeslání diagnostických dat**|Povolí nebo blokuje odesílání diagnostických dat ze zařízení do společnosti Apple.|
|**Povolit aplikaci Passbook při uzamčení**|Povolí uživateli přístup k aplikaci Passbook, když je zařízení uzamčené.|

### <a name="cloud-settings-for-documents-and-data"></a>Nastavení cloudu pro dokumenty a data
Všechna nastavení platí pro iOS 8.0 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit zálohování na iCloud**|Povolí uživateli zálohovat zařízení do iCloudu.|
|**Povolit synchronizaci dokumentů s iCloudem**|Povolí synchronizaci dokumentu a párů klíč-hodnota s úložným prostorem iCloudu.|
|**Povolit synchronizaci streamu fotek s iCloudem**|Povolí synchronizaci fotografií na zařízení s iCloudem.|
|**Vyžadovat šifrované zálohování**|Vyžaduje, aby všechny zálohy zařízení byly šifrované.|
|**Povolit spravovaným aplikacím synchronizaci dat s iCloudem**|Povolí aplikacím, které spravujete přes Intune, synchronizaci dat s uživatelským účtem iCloudu.|
|**Povolit, aby Handoff pokračoval v činnosti na jiném zařízení**|Umožní uživateli, aby v práci, kterou zahájil na zařízení s iOSem, pokračoval na jiném zařízení s iOSem nebo Mac OS X.|
|**Povolit sdílení fotek na iCloudu**|Povolí používání sdíleného streamu fotografií iOS.|
|**Povolit Knihovnu fotografií na iCloudu**|Umožní uživateli ukládat fotky na iCloud. Pokud se zakáže, všechny dříve uložené fotky na iCloudu budou odebrány.|

### <a name="application-settings-for-the-browser"></a>Nastavení aplikace pro prohlížeč
Všechna nastavení platí pro iOS 8.0 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit Safari**|Určete, jestli se na zařízení může používat prohlížeč Safari.|
|**Povolit automatické vyplňování**|Umožňuje uživateli změnit nastavení automatického dokončování v prohlížeči.|
|**Povolit blokování automaticky otevíraných oken**|Povolí nebo zakáže blokování automaticky otevíraných oken v prohlížeči.|
|**Povolit soubory cookie**|Povolí prohlížeči používat soubory cookie.|
|**Povolit skriptování v Javě**|Povolí v prohlížeči spuštění skriptů jazyka Java.|
|**Povolit upozornění na podvod**|Povolí v prohlížeči upozornění na podvod.|

### <a name="application-settings-for-apps"></a>Nastavení aplikací pro aplikace
Všechna nastavení platí pro iOS 8.0 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit instalaci aplikací**|Povolí zařízení přistupovat k obchodu s aplikacemi a instalovat aplikace.|
|**Vyžadovat heslo pro přístup do obchodu s aplikacemi**|Vyžaduje, aby uživatel zadal heslo, než bude moci navštívit obchod s aplikacemi.|
|**Povolit nákupy v aplikaci**|Povolí ve spuštěné aplikaci nákupy v obchodě.|
|**Povolit spravované dokumenty v jiných nespravovaných aplikacích**|Povolí prohlížení podnikových dokumentů v jakékoliv aplikaci.<br>**Příklad:** Chcete zabránit uživatelům v ukládání souborů z aplikace OneDrive do Dropboxu. U tohoto nastavení vyberte možnost Ne. Až zařízení zásadu obdrží (třeba po restartování), už nebude povolovat ukládání.|
|**Povolit nespravované dokumenty v jiných spravovaných aplikacích**|Povolí prohlížení libovolného dokumentu ve spravovaných podnikových aplikacích.|
|**Povolit videokonference**|Povolí na zařízení videokonferenční aplikace, jako je třeba Facetime.|
|**Povolit uživateli důvěřovat autorům nových podnikových aplikací**|Umožní uživateli vybrat možnost, že důvěřuje aplikacím, které nebyly staženy z App Store.|


### <a name="application-settings-for-games"></a>Nastavení aplikací pro hry
Všechna nastavení platí pro iOS 8.0 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit přidávání přátel v herním centru**|Povolí uživateli přidat přátele z herního centra.|
|**Povolit hru s více hráči**|Povolí uživateli hrát na zařízení hry pro víc hráčů.|

### <a name="application-settings-for-media-content"></a>Nastavení aplikací pro mediální obsah
Všechna nastavení platí pro iOS 8.0 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Oblast hodnocení**|Vyberte oblast a pak vyberte, s jakým maximálním hodnocením můžou uživatelé stahovat obsah v kategoriích **Filmy**, **TV pořady** a **Aplikace**.|
|**Povolit obsah pro dospělé v obchodě s multimediálním obsahem**|Povolí zařízení přístup k obsahu úložiště, který je označený jako obsah pro dospělé.|
|**Povolit uživateli stažení obsahu z obchodu iBooks, který má označení „erotika“**|Povolí uživateli stahování knih z kategorie „erotika“.|


### <a name="device-capabilities-settings-for-hardware"></a>Nastavení možností zařízení pro hardware
Všechna nastavení platí pro iOS 8.0 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit fotoaparát**|Určete, jestli je možné použít fotoaparát v zařízení.|
|**Vynutit u spárovaných Apple Watch používání detekce zápěstí**|Když se povolí, Apple Watch nebudou zobrazovat oznámení, dokud si je uživatel nenasadí.|
|**Vyžadovat párovací heslo pro odchozí požadavky AirPlay**|Vyžaduje párovací heslo, pokud uživatel použije AirPlay ke streamování obsahu do dalších zařízení Apple.|

### <a name="device-capabilities-settings-for-cellular"></a>Nastavení možností zařízení pro mobilní funkce
Všechna nastavení platí pro iOS 8.0 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit hlasový roaming**|Povolí hlasový roaming, když je zařízení v mobilní síti.|
|**Povolit datový roaming**|Povolí datový roaming, když je zařízení v mobilní síti.|
|**Povolit globální načítání na pozadí při roamingu**|Povolí zařízení, aby při roamingu v mobilní síti načítalo data na pozadí, třeba e-maily.|

### <a name="device-capabilities-settings-for-features"></a>Nastavení možností zařízení pro funkce
Všechna nastavení platí pro iOS 8.0 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit Siri**|Povolí v zařízení používání hlasového pomocníka Siri.|
|**Povolit Siri při uzamčení zařízení**|Povolí používání hlasového pomocníka Siri, když je zařízení zamčené.|
|**Povolit hlasové vytáčení**|Umožňuje používat v zařízení funkci hlasového vytáčení.|
|**Nepovolovat AirDrop ze spravovaných aplikací**|Znemožní spravovaným aplikacím posílat data přes Airdrop.|


### <a name="settings-for-compliant-and-noncompliant-apps"></a>Nastavení pro aplikace dodržující a nedodržující předpisy
V seznamu **Kompatibilní a nekompatibilní aplikace** zadejte seznam kompatibilních a nekompatibilních aplikací s využitím následujících informací.

> [!NOTE]
> Jedna zásada může obsahovat seznam jenom kompatibilních aplikací, nebo jenom nekompatibilních aplikací. Nejde zadat oba seznamy v jedné zásadě.

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Ohlásit nekompatibilitu, když uživatelé nainstalují aplikace ze seznamu**|Zobrazí seznam aplikací (nespravovaných pomocí Intune), které nemají uživatelé dovolené nainstalovat a spustit.|
|**Ohlásit nekompatibilitu, když uživatelé nainstalují aplikace, které nejsou na seznamu**|Zobrazí seznam aplikací, které mají uživatelé dovoleno instalovat. Aby byla zachovaná kompatibilita, uživatelé nesmí instalovat aplikace, které nejsou v seznamu. Aplikace, které spravuje Intune, jsou povolené automaticky.|
|**Přidat**|Přidá aplikaci do vybraného seznamu. Zadejte název podle své volby, volitelně vydavatele aplikaci a adresu URL aplikace v úložišti aplikací. Další pomoc najdete v části Určení adres URL na obchody s aplikacemi dál v tomto tématu.|
|**Importovat aplikace**|Importuje seznam aplikací, které jste zadali v souboru hodnot oddělených čárkami. V souboru použijte tento formát: název aplikace, vydavatel, adresa URL aplikace.|
|**Upravit**|Upraví název, vydavatele a adresu URL vybrané aplikace.|
|**Odstranit**|Odstraňte vybranou aplikaci ze seznamu.|

### <a name="kiosk-mode-settings"></a>Nastavení celoobrazovkovém režimu

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Vyberte spravovanou aplikaci, která se bude dát spustit, když bude zařízení v celoobrazovkovém režimu**|Vyberte **Procházet** a zadejte spravovanou aplikaci nebo aplikaci z obchodu, která se bude moct spouštět, když je zařízení v celoobrazovkovém režimu. Žádné jiné aplikace nebudou mít dovoleno se na zařízení spouštět. Další nápovědu najdete v části Určení adres URL na obchody s aplikacemi dál v tomto tématu.|
|**Povolit dotykové ovládání**|Na příslušném zařízení povolí nebo zakáže dotykovou obrazovku.|
|**Povolit otočení obrazovky**|Povolí nebo zakáže změnu orientace obrazovky, když uživatel otočí zařízení.|
|**Povolit tlačítka hlasitosti**|Povolí nebo zakáže použití tlačítek hlasitosti na zařízení.|
|**Povolit přepínač vyzvánění**|Povolí nebo zakáže přepínač vyzvánění (ztlumení) na zařízení.|
|**Povolit tlačítko pro probuzení obrazovky z režimu spánku**|Povolí nebo zakáže na zařízení tlačítko probuzení z režimu spánku obrazovky.|
|**Povolit automatické uzamčení**|Povolí nebo zakáže automatické uzamykání zařízení.|
|**Povolit mono zvuk**|Povolí nebo zakáže nastavení usnadnění **Mono zvuk**.|
|**Povolit hlas na pozadí**|Povolí nebo zakáže nastavení usnadnění **VoiceOver**, které předčítá text na displeji zařízení.|
|**Povolit úpravy hlasu na pozadí**|Povolí nebo zakáže úpravy hlasového přednesu, které umožňují nastavit funkci nástroje VoiceOver (například rychlost čtení textu na obrazovce).|
|**Povolit lupu**|Povolí nebo zakáže nastavení usnadnění **Zvětšení**, které vám umožní používat na displeji zařízení funkci zvětšení zobrazení dotykem.|
|**Povolit úpravy lupy**|Povolí nebo zakáže úpravy zvětšení, které uživateli umožňují nastavit funkci zvětšení.|
|**Povolit invertování barev**|Povolí nebo zakáže nastavení usnadnění **Invertovat barvy**, které upraví displej pro potřeby uživatelů se zrakovým postižením.|
|**Povolit úpravy invertování barev**|Povolí nebo zakáže úpravy inverze barev, které uživateli umožňují nastavit funkci inverze barev.|
|**Povolit funkci dotykového ovládání pro usnadnění**|Povolí nebo zakáže nastavení usnadnění **dotykového ovládání**, která uživateli pomáhá provádět na obrazovce gesta, která by pro něho mohla být obtížná.|
|**Povolit úpravy funkce dotykového ovládání pro usnadnění**|Povolí nebo zakáže úpravy usnadnění dotykového ovládání, které uživateli umožňují upravit funkce usnadnění dotykového ovládání.|
|**Povolit výběr řeči**|Povolí nebo zakáže nastavení usnadnění **Výběr řeči**, které může nahlas přečíst text vybraný uživatelem.|
> [!NOTE]
> Následující poznámky platí pro nastavení celoobrazovkového režimu na zařízeních iOS:
>
> -   Než budete moct nakonfigurovat nastavení zařízení iOS pro celoobrazovkový režim, musíte převést zařízení do režimu dohledu pomocí nástroje [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) nebo [Programu registrace zařízení Apple](ios-device-enrollment-program-in-microsoft-intune.md). Další informace o nástroji Apple Configurator získáte v dokumentaci Apple.
> -   Pokud se určená aplikace pro iOS nainstaluje až po nasazení zásad konfigurace, zařízení nepřejde do celoobrazovkového režimu, dokud ho nerestartujete.

### <a name="reference-information-for-compliant-and-noncompliant-apps"></a>Referenční informace pro aplikace nesplňující předpisy

Pomocí **sestavy nekompatibilních aplikací** zobrazte kompatibilitu povolených a blokovaných aplikací.

##### <a name="to-run-the-noncompliant-apps-report"></a>Spuštění sestavy nekompatibilních aplikací

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Sestavy** &gt; **Sestava aplikací nedodržujících předpisy**.

2.  Vyberte skupiny zařízení, které chcete zkontrolovat, určete, jestli se mají kontrolovat aplikace dodržující předpisy, aplikace nedodržující předpisy nebo obojí, a potom vyberte **Zobrazit sestavu**.

#### <a name="how-to-specify-urls-to-app-stores"></a>Určení adres URL na obchody s aplikacemi
Pokud chcete zadat adresu URL aplikace do seznamu kompatibilních a nekompatibilních aplikací nebo použít možnost **Vybrat spravovanou aplikaci, která se může spouštět, když je zařízení v celoobrazovkovém režimu** (jenom iOS), použijte následující formát:

1. Pomocí vyhledávacího modulu najděte aplikaci, kterou chcete použít v iTunes App Storu, a otevřete stránku pro tuto aplikaci.

2. Zkopírujte adresu URL stránky a použijte ji jako URL ke konfiguraci seznamu kompatibilních nebo nekompatibilních aplikací nebo aplikace, kterou chcete spustit v celoobrazovkovém režimu.

**Příklad:** Vyhledejte **Microsoft Word pro iPad**. Použitá adresa URL bude **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE]
> Pomocí softwaru iTunes taky můžete najít aplikaci a pomocí příkazu **Kopírovat odkaz** získat adresu URL aplikace.

### <a name="enrollment-settings"></a>Nastavení registrace
Všechna nastavení platí pro iOS 8.0 a novější.

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Povolit zámek aktivace, když je zařízení v režimu pod dohledem**|Povolí zámek aktivace na zařízeních s iOSem, které jsou pod dohledem.|

### <a name="supervised-mode-settings"></a>Nastavení režimu dohledu
Na zařízeních se systémem iOS 8.0 a novějším, která jsou v režimu pod dohledem, je možné nakonfigurovat následující nastavení.

### <a name="supervised-mode-settings-for-device-restrictions"></a>Nastavení režimu dohledu – omezení zařízení

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Povolit změnu účtu**|Povolí uživateli změnu nastavení účtu, jako je například konfigurace e-mailu.|
|**Povolit změny nastavení využití mobilních dat v aplikaci**|Umožní uživateli řídit, které aplikace můžou používat mobilní data.|
|**Povolit použití možnosti pro vymazání veškerého obsahu a nastavení na zařízení**|Zpřístupní uživateli možnost pro vymazání veškerého obsahu a nastavení na zařízení.|
|**Povolit uživateli aktivaci omezení v nastavení zařízení**|Umožní uživateli konfigurovat omezení (rodičovské kontroly) na zařízení.|
|**Povolit určování zařízení, s nimiž se může zařízení s iOSem párovat, podle hostitelského párování**|Povolí hostitelské párování, díky kterému může správce určit, se kterými zařízeními se dá spárovat zařízení s iOSem.|
|**Povolit uživateli instalaci konfiguračních profilů a certifikátů**|Povolí uživateli instalaci konfiguračních profilů a certifikátů.|
|**Povolit úpravy názvu zařízení**|Umožní uživateli změnit název zařízení.|
|**Povolit úpravu hesla**|Povolí přidání, úpravu a odebrání hesla zařízení.|
|**Povolit spárování Apple Watch**|Povolí zařízení spárovat se s Apple Watch.|
|**Povolit úpravy nastavení oznámení**|Umožní uživateli přenastavit v zařízení oznámení.|
|**Povolit úpravy tapety**|Umožní uživateli změnit v zařízení tapetu.|

### <a name="supervised-mode-settings-for-feature-restrictions"></a>Nastavení režimu dohledu – omezení funkcí

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Povolit AirDrop**|Povolí použití funkce Airdrop k výměně obsahu s blízkými zařízeními.|
|**Povolit Siri dotazování na uživatelem generovaný obsah z internetu**|Umožní aplikaci Siri získat přístup k webům, aby mohla odpovídat na otázky.|
|**Používat filtr vulgárních výrazů v Siri**|Zabrání Siri diktovat a vyslovovat vulgární výrazy.|
|**Povolit vrácení výsledků z internetu pomocí vyhledávání Spotlight**|Povolí vyhledávání Spotlight připojit se k internetu, aby bylo možné poskytnout další výsledky.|
|**Povolit vyhledávání definic slov**|Povolit funkci iOS, která umožňuje zvýraznit slovo a vyhledat jeho definici.|
|**Povolit prediktivní klávesnice**|Povolí používání prediktivních klávesnic, které uživateli navrhují slova, co by se mu mohla hodit.|
|**Povolit automatické opravy**|Povolí zařízení automaticky opravovat slova s překlepem.|
|**Povolit kontrolu pravopisu klávesnice**|Povolí v zařízení kontrolu pravopisu.|
|**Povolit klávesové zkratky**|Umožní používání klávesových zkratek.|

### <a name="supervised-mode-settings-for-app-restrictions"></a>Nastavení režimu dohledu – omezení aplikací

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Povolit úpravy nastavení vztahu důvěryhodnosti u podnikových aplikací**|Umožňuje uživatelům změnit nastavení vztahu důvěryhodnosti pro podnikové aplikace.|
|**Povolit instalaci aplikací pouze pomocí Apple Configuration a iTunes**|Povolí nebo zakáže App Store z domovské obrazovky zařízení. Uživatelé mohou nadále instalovat a aktualizovat aplikace pomocí iTunes nebo nástroje Apple Configurator.|
|**Povolit automatické stahování aplikací**|Povolit, aby aplikace zakoupené na jiných zařízeních byly automaticky staženy na toto zařízení. Toto nastavení nemá vliv na aktualizace aplikací.|
|**Povolit změny v nastavení aplikace Find My Friends**|Umožní uživateli změnu nastavení pro aplikaci Find My Friends.|
|**Povolit přístup k obchodu iBooks**|Umožní uživateli procházení a nákup knih z úložiště iBooks.|
|**Povolit použití aplikace Zprávy na zařízení**|Povolit použití aplikace Zprávy k posílání textových zpráv.|
|**Povolit používání Podcastů**|Povolí používání aplikace Podcasty.|
|**Povolit používání služby Music**|Povolí používání aplikace Apple Music.|
|**Povolit službu iTunes Radio**|Povolí používání aplikace iTunes Radio.|
|**Povolit Apple News**|Povolí používání aplikace Apple News.|
|**Povolit Game Center**|Povolí použití aplikace Herní centrum.|


### <a name="show-or-hide-apps"></a>Zobrazit nebo skrýt aplikace

Pomocí seznamu **Skryté a zobrazené aplikace** můžete na dozorovaných zařízeních se systémem iOS 9.3 kontrolovat následující:

- Určení seznamu aplikací, které budou uživatelům skryté. Uživatelé nebudou moci tyto aplikace zobrazit ani spustit.
- Určení seznamu aplikací, které uživatelé mohou zobrazit a spustit. Žádné jiné aplikace nebude možné zobrazit ani spustit.


#### <a name="how-to-create-a-hidden-or-shown-app-list"></a>Jak vytvořit seznamy skrytých nebo zobrazených aplikací

Určete následující nastavení:

|Název nastavení|Podrobnosti|
|-|-|
|**Seznam skrytých a zobrazených aplikací**|Povolte toto nastavení, jestli chcete vytvořit seznamy skrytých nebo zobrazených aplikací.|
|**Skrýt aplikace uvedené v seznamu pro uživatele**|Vyberte tuto možnost, pokud chcete vytvořit seznam aplikací, které budou před uživateli skryté.<br>Když vytvoříte tento seznam, můžou být všechny aplikace kromě **Nastavení** a **Telefon** (pro iPhony) skryté.|
|**Zobrazit uživatelům jenom aplikace uvedené v seznamu**|Vyberte tuto možnost, pokud chcete vytvořit seznam aplikací, které budou pro uživatele viditelné.<br>Když vytvoříte tento seznam, budou všechny v něm neuvedené aplikace kromě **Nastavení** a **Telefon** (pro iPhony) skryté.<br>Kromě toho je do seznamu nutné přidat aplikaci portálu společnosti a všechny nasazené aplikace, spravované v Intune.|
|**Přidat**|Přidá aplikaci do vybraného seznamu.<br>Pro seznam skrytých aplikací je třeba uvést **Název**, **Vydavatele** a **Adresu URL nebo ID sady aplikace** každé aplikace, kterou chcete skrýt.<br>Pro seznam zobrazených aplikací můžete buď **Vybrat spravovanou aplikaci** ze seznamu aplikací, které spravujete v Intune, nebo vybrat aplikaci ze Storu, pro kterou je pak nutné zadat **Název**, **Vydavatele** a **Adresu URL nebo ID sady aplikace**.|
|**Importovat aplikace**|Importuje seznam aplikací, které jste zadali v souboru hodnot oddělených čárkami. V souboru použijte formát, název aplikace, vydavatele, adresu URL aplikace.|
|**Upravit**|Tady můžete upravit název, vydavatele a adresu URL vybrané aplikace.|
|**Odstranit**|Odstraní vybranou aplikaci ze seznamu.|

#### <a name="app-information-for-built-in-ios-apps"></a>Informace o aplikaci pro vestavěné aplikace iOS

Informace z tohoto seznamu můžete použít k identifikaci názvu, vydavatele a adresy URL nebo ID sady aplikace pro vestavěné aplikace iOS, které chcete skrýt nebo zobrazit. Pokud chcete zobrazit nebo skrýt všechny aplikace v seznamu, můžete zkopírovat následující data do textového souboru s příponou **.csv** a pak pomocí možnosti **Importovat aplikace** naimportovat všechny najednou.

```
App Store,Apple,com.apple.AppStore
Calculator,Apple,com.apple.calculator
Calendar,Apple,com.apple.mobilecal
Camera,Apple,com.apple.camera
Clock,Apple,com.apple.mobiletimer
Compass,Apple,com.apple.compass
Contacts,Apple,com.apple.MobileAddressBook
FaceTime,Apple,com.apple.facetime
Find Friends,Apple,com.apple.mobileme.fmf1
Find iPhone,Apple,com.apple.mobileme.fmip1
Game Center,Apple,com.apple.gamecenter
GarageBand,Apple,com.apple.mobilegarageband
Health,Apple,com.apple.Health
iBooks,Apple,com.apple.iBooks
iTunes Store,Apple,com.apple.MobileStore
iTunes U,Apple,com.apple.itunesu
Keynote,Apple,com.apple.Keynote
Mail,Apple,com.apple.mobilemail
Maps,Apple,com.apple.Maps
Messages,Apple,com.apple.MobileSMS
Music,Apple,com.apple.Music
News,Apple,com.apple.news
Notes,Apple,com.apple.mobilenotes
Numbers,Apple,com.apple.Numbers
Pages,Apple,com.apple.Pages
Photo Booth,Apple,com.apple.Photo-Booth
Photos,Apple,com.apple.mobileslideshow
Podcasts,Apple,com.apple.podcasts
Reminders,Apple,com.apple.reminders
Safari,Apple,com.apple.mobilesafari
Settings,Apple,com.apple.Preferences
Stocks,Apple,com.apple.stocks
Tips,Apple,com.apple.tips
Videos,Apple,com.apple.videos
VoiceMemos,Apple,com.apple.VoiceMemos
Wallet,Apple,com.apple.Passbook
Watch,Apple,com.apple.Bridge
Weather,Apple,com.apple.weather


```




## <a name="custom-policy-settings"></a>Nastavení vlastních zásad

Pomocí **vlastní zásady iOSu** služby Microsoft Intune nasaďte do zařízení s iOSem nastavení, které jste vytvořili pomocí nástroje [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). Pomocí tohoto nástroje se dá vytvořit spousta nastavení, která řídí provoz těchto zařízení, a exportovat je do konfiguračního profilu. Potom tento konfigurační profil můžete naimportovat do vlastní zásady iOS služby Intune a nasadit nastavení pro uživatele a zařízení ve vaší organizaci.

Díky této funkci můžete nasadit nastavení iOS, která nejdou konfigurovat pomocí obecných zásad konfigurace Intune.

### <a name="prerequisites"></a>Požadavky
Než začnete, je potřeba nainstalovat Apple Configurator a vytvořit konfigurační soubor s nastaveními, která chcete nasadit pro uživatele nebo zařízení. Apple Configurator si můžete stáhnout z [Mac App Storu](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12), kde o něm také najdete další informace.

> [!NOTE]
> Intune nevytváří sestavu dodržování předpisů pro jednotlivá nastavení vlastní zásady iOS. Vytvoří se ale sestava celkového dodržování zásad.

### <a name="general-settings"></a>Obecná nastavení

|Název nastavení|Podrobnosti|
    |----------------|--------------------|
    |**Název**|Zadejte jedinečný název vlastní zásady pro iOS, abyste ji mohli v konzole Intune snadno identifikovat.|
    |**Popis**|Zadejte popis, který bude shrnovat účel vlastní zásady pro iOS, a uveďte jakékoli další důležité informace, které vám pomůžou zásadu najít.|

### <a name="custom-settings"></a>Vlastní nastavení

|Název nastavení|Podrobnosti|
    |----------------|--------------------|
|**Název vlastního konfiguračního profilu (zobrazí se uživatelům)**|Zadejte název zásady tak, jak se bude zobrazovat na zařízení a v sestavách zásad Intune.|
|**Soubor konfiguračního profilu**|Vyberte **Importovat** a potom vyhledejte konfigurační profil, který jste vytvořili pomocí nástroje Apple Configurator. **Poznámka:** Nastavení, které exportujete z nástroje Apple Configurator, musí být kompatibilní s verzí iOS na zařízeních, na která nasazujete vlastní zásady pro iOS. Informace o tom, jak se řeší nekompatibilní nastavení, najdete v **referenčních materiálech ke konfiguračnímu profil** a **referenčních materiálech k protokolu správy mobilního zařízení** na [webu pro vývojáře Apple](https://developer.apple.com/).|
    |**Podrobnosti konfiguračního profilu**|Zobrazí kód XML pro konfigurační profil, který jste importovali.|

### <a name="see-also"></a>Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Dec16_HO2-->

