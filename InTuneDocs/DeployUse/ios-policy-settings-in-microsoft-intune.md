---
title: "Nastavení zásad pro iOS | Microsoft Intune"
description: "Vytvořte zásady, které řídí nastavení a funkce na zařízeních s iOS, která spravujete pomocí Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bc5ff023b5d29ded999c7e49c5e7c2aee8a23bba
ms.openlocfilehash: e71cc1e8e2cb0f46507ff63d962f3d477acfb72e


---

# Nastavení zásad pro iOS v Microsoft Intune

Intune poskytuje řadu předdefinovaných obecných nastavení, která můžete konfigurovat v zařízeních s iOS. Navíc můžete použít nástroj Apple Configurator k vytvoření vlastních nastavení, která nejsou k dispozici prostřednictvím Intune.

## Obecná nastavení zásad konfigurace

Pomocí **zásad obecné konfigurace pro iOS** v Microsoft Intune můžete nakonfigurovat nastavení pro:

-   **Obecná nastavení zařízení a zabezpečení** Vyberte možnost ze seznamu předdefinovaných nastavení, která umožňují kontrolovat celou řadu vlastností a funkcí zařízení.

-   **Celoobrazovkový režim** Umožňuje uzamknout zařízení a povolit fungování jenom některých funkcí. Můžete třeba povolit, aby v zařízení běžela jenom jedna vámi určená spravovaná aplikace, nebo můžete na zařízení zakázat tlačítka hlasitosti. Tato nastavení se dají používat pro ukázkový model zařízení nebo pro zařízení, které je vyhrazené jenom pro jednu funkci, jako je třeba zařízení POS.

-   **Kompatibilní a nekompatibilní aplikace** Umožňuje určit seznam aplikací pro iOS, které vyhovují nebo nevyhovují předpisům ve vaší společnosti. Na zařízeních s Androidem a iOS je možné použít **aplikací nesplňujících požadavky** k zobrazení shody aplikací, které zadáte v seznamu, s aplikacemi, které si uživatelé nainstalovali (sestava neslouží ke skutečnému zablokování instalace aplikací).

> [!TIP]
> Můžete nakonfigurovat podmínky pro uživatele a zajistit tak, aby věděli, že aplikace na jejich zařízení (včetně osobních aplikací) se vyhodnotí a nekompatibilní aplikace se zablokují nebo nahlásí jako nevyhovující. Uživatelé musí přijmout tyto podmínky předtím, než můžou zaregistrovat své zařízení a používat firemní portál k získání aplikací. Další informace o podmínkách a ujednáních týkajících se použití najdete v tématu [Nastavení zásad podmínek a ujednání v Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md).

Pokud v tomto tématu není uvedené nastavení, které hledáte, je možné, že ho budete moct vytvořit pomocí vlastních zásad pro iOS, které vám umožní naimportovat nastavení vytvořená pomocí [nástroje Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). Další informace najdete v části Nastavení vlastních zásad dál v tomto tématu.

### Nastavení zabezpečení
Všechna nastavení platí pro iOS 7.1 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Vyžadovat heslo k odemknutí mobilních zařízení**|Určete, jestli uživatel při přístupu ke svému zařízení musí zadat heslo.|
|**Vyžadovaný typ hesla**|Zadejte typ hesla, které se bude vyžadovat, například jenom číslice nebo alfanumerické znaky.|
|**Počet složitých znaků požadovaných v hesle**|Zadejte počet znaků symbolu (jako například **#** nebo **@**), které musí heslo obsahovat.|
|**Minimální délka hesla**|Zadejte minimální počet znaků v hesle.|
|**Povolit jednoduchá hesla**|Umožňuje použití jednoduchých hesel, jako je třeba **0000** nebo **1234**.|
|**Počet povolených opakovaných neúspěšných přihlášení, než bude zařízení vymazáno**|Zadejte počet neúspěšných pokusů o přihlášení, než toto nastavení vymaže zařízení.|
|**Počet minut nečinnosti před vyžadováním hesla**<sup>1</sup>|Zadejte, jak dlouho může zařízení zůstat nečinné, než uživatel musí znovu zadat heslo.|
|**Omezená platnost hesla (ve dnech)**|Zadejte počet dní, než bude nutné změnit heslo zařízení.|
|**Pamatovat si historii hesel**|Určete, jestli uživatel může použít hesla, která už použil.|
|**Pamatovat si historii hesel** – **Zabránit opětovnému použití předchozích hesel**|Zadejte počet dříve použitých hesel, která si zařízení pamatuje.|
|**Počet minut nečinnosti před vypnutím displeje**<sup>1</sup>|Zadejte počet minut, než se displej zařízení vypne.|
|**Povolit odemknutí otiskem prstu**|Povolí odemknutí zařízení otiskem prstu.|
<sup>1</sup> Pokud pro zařízení s iOS nakonfigurujete nastavení **Počet minut nečinnosti před vypnutím displeje** a **Počet minut nečinnosti před vyžadováním hesla**, tato nastavení se použijí v uvedeném pořadí. Pokud například pro obě nastavení nastavíte hodnotu **5** minut, obrazovka se po 5 minutách automaticky vypne a po dalších 5 minutách se zařízení zamkne. Pokud ale uživatel vypne obrazovku ručně, druhé nastavení se použije okamžitě. V tomto příkladě se zařízení po tom, co uživatel vypne obrazovku, zamkne po 5 minutách.

### Nastavení systému
Všechna nastavení platí pro iOS 7.1 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit snímek obrazovky**|Povolí uživateli zachytit obsah obrazovky jako obrázek.|
|**Povolit řídicí centrum na zamykací obrazovce**|Povolí uživateli přístup k aplikaci řídicího centra, když je zařízení uzamčené.|
|**Povolit zobrazení oznámení na zamykací obrazovce**|Povolí uživateli přístup k zobrazení oznámení bez odemknutí zařízení.|
|**Povolit zobrazení informací o dnešku na zamykací obrazovce**|Povolí uživateli zobrazit oznámení, když je zařízení uzamčené.|
|**Povolit nedůvěryhodné certifikáty TLS**|Povolí v zařízení nedůvěryhodné certifikáty protokolu TLS (Transport Layer Security).|
|**Povolit odeslání diagnostických dat**|Povolí nebo blokuje odesílání diagnostických dat ze zařízení do společnosti Apple.|
|**Povolit aplikaci Passbook při uzamčení**|Povolí uživateli přístup k aplikaci Passbook, když je zařízení uzamčené.|

### Nastavení cloudu pro dokumenty a data
Všechna nastavení platí pro iOS 7.1 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit zálohování na iCloud**|Povolí uživateli zálohovat zařízení do iCloudu.|
|**Povolit synchronizaci dokumentů s iCloudem**|Povolí synchronizaci dokumentu a párů klíč-hodnota s úložným prostorem iCloudu.|
|**Povolit synchronizaci datového proudu fotografií s iCloudem**|Povolí synchronizaci fotografií na zařízení s iCloudem.|
|**Vyžadovat šifrované zálohování**|Vyžaduje, aby všechny zálohy zařízení byly šifrované.|
|**Povolit spravovaným aplikacím synchronizaci dat s iCloudem**|Povolí aplikacím, které spravujete přes Intune, synchronizaci dat s uživatelským účtem iCloudu.|
|**Povolit, aby Handoff pokračoval v činnosti na jiném zařízení**|Umožní uživateli, aby v práci, kterou zahájil na zařízení s iOS, pokračoval na jiném zařízení s iOS nebo Mac OS X.|

### Nastavení aplikace pro prohlížeč
Všechna nastavení platí pro iOS 7.1 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit Safari**|Určete, jestli se na zařízení může používat prohlížeč Safari.|
|**Povolit automatické vyplňování**|Umožňuje uživateli změnit nastavení automatického dokončování v prohlížeči.|
|**Povolit blokování automaticky otevíraných oken**|Povolí nebo zakáže blokování automaticky otevíraných oken v prohlížeči.|
|**Povolit soubory cookie**|Povolí prohlížeči používat soubory cookie.|
|**Povolit skriptování v Javě**|Povolí v prohlížeči spuštění skriptů jazyka Java.|
|**Povolit upozornění na podvod**|Povolí v prohlížeči upozornění na podvod.|

### Nastavení aplikací pro aplikace
Všechna nastavení platí pro iOS 7.1 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit obchod s aplikacemi**|Povolí zařízení přístup k obchodu s aplikacemi.|
|**Vyžadovat heslo pro přístup do obchodu s aplikacemi**|Vyžaduje, aby uživatel zadal heslo, než bude moci navštívit obchod s aplikacemi.|
|**Povolit nákupy v aplikaci**|Povolí ve spuštěné aplikaci nákupy v obchodě.|
|**Povolit spravované dokumenty v jiných nespravovaných aplikacích**|Povolí prohlížení podnikových dokumentů v jakékoliv aplikaci.<br>**Příklad:** Chcete zabránit uživatelům v ukládání souborů z aplikace OneDrive do Dropboxu. U tohoto nastavení vyberte možnost Ne. Až zařízení zásadu obdrží (třeba po restartování), už nebude povolovat ukládání.|
|**Povolit nespravované dokumenty v jiných spravovaných aplikacích**|Povolí prohlížení libovolného dokumentu ve spravovaných podnikových aplikacích.|
|**Povolit videokonference**|Povolí na zařízení videokonferenční aplikace, jako je třeba Facetime.|
|**Povolit obsah pro dospělé v obchodě s mediálním obsahem**|Povolí zařízení přístup k obsahu úložiště, který je označený jako obsah pro dospělé.|
|**Povolit uživateli stažení obsahu z obchodu iBooks, který má označení „erotika“**|Povolí uživateli stahování knih z kategorie „erotika“.|

### Nastavení aplikací pro hry
Všechna nastavení platí pro iOS 7.1 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit přidávání přátel v herním centru**|Povolí uživateli přidat přátele z herního centra.|
|**Povolit hru s více hráči**|Povolí uživateli hrát na zařízení hry pro víc hráčů.|

### Nastavení možností zařízení pro hardware
Všechna nastavení platí pro iOS 7.1 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit fotoaparát**|Určete, jestli je možné použít fotoaparát v zařízení.|
|**Vyžadovat párovací heslo pro odchozí požadavky AirPlay**|Vyžaduje párovací heslo, pokud uživatel použije AirPlay ke streamování obsahu do dalších zařízení Apple.|

### Nastavení možností zařízení pro mobilní funkce
Všechna nastavení platí pro iOS 7.1 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit hlasový roaming**|Povolí hlasový roaming, když je zařízení v mobilní síti.|
|**Povolit datový roaming**|Povolí datový roaming, když je zařízení v mobilní síti.|
|**Povolit globální načítání na pozadí při roamingu**|Povolí zařízení, aby při roamingu v mobilní síti načítalo data na pozadí, třeba e-maily.|

### Nastavení možností zařízení pro funkce
Všechna nastavení platí pro iOS 7.1 a novější.

|Název nastavení|Podrobnosti|
|----------------|-------|
|**Povolit Siri**|Povolí v zařízení používání hlasového pomocníka Siri.|
|**Povolit Siri při uzamčení zařízení**|Povolí používání hlasového pomocníka Siri, když je zařízení zamčené.|
|**Povolit hlasové vytáčení**|Umožňuje používat v zařízení funkci hlasového vytáčení.|


### Nastavení pro aplikace dodržující a nedodržující předpisy
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
|**Odstranit**|Odstraní vybranou aplikaci ze seznamu.|

### Nastavení celoobrazovkovém režimu

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Vyberte spravovanou aplikaci, která se bude moct spustit, když je zařízení v celoobrazovkovém režimu**|Vyberte **Procházet** a zadejte spravovanou aplikaci nebo aplikaci z obchodu, která se bude moct spouštět, když je zařízení v celoobrazovkovém režimu. Žádné jiné aplikace nebudou mít dovoleno se na zařízení spouštět. Další nápovědu najdete v části Určení adres URL na obchody s aplikacemi dál v tomto tématu.|
|**Povolit dotykové ovládání**|Na příslušném zařízení povolí nebo zakáže dotykovou obrazovku.|
|**Povolit otočení obrazovky**|Povolí nebo zakáže změnu orientace obrazovky, když uživatel otočí zařízení.|
|**Povolit tlačítka hlasitosti**|Povolí nebo zakáže použití tlačítek hlasitosti na zařízení.|
|**Povolit přepínač vyzvánění**|Povolí nebo zakáže přepínač vyzvánění (ztlumení) na zařízení.|
|**Povolit tlačítko probuzení z režimu spánku obrazovky**|Povolí nebo zakáže na zařízení tlačítko probuzení z režimu spánku obrazovky.|
|**Povolit automatické uzamčení**|Povolí nebo zakáže automatické uzamykání zařízení.|
|**Povolit mono zvuk**|Povolí nebo zakáže nastavení usnadnění **Mono zvuk**.|
|**Povolit hlasitý přednes**|Povolí nebo zakáže nastavení usnadnění **VoiceOver**, které předčítá text na displeji zařízení.|
|**Povolit úpravy hlasového přednesu**|Povolí nebo zakáže úpravy hlasového přednesu, které umožňují nastavit funkci nástroje VoiceOver (například rychlost čtení textu na obrazovce).|
|**Povolit zvětšení**|Povolí nebo zakáže nastavení usnadnění **Zvětšení**, které vám umožní používat na displeji zařízení funkci zvětšení zobrazení dotykem.|
|**Povolit úpravy zvětšení**|Povolí nebo zakáže úpravy zvětšení, které uživateli umožňují nastavit funkci zvětšení.|
|**Povolit inverzi barev**|Povolí nebo zakáže nastavení usnadnění **Invertovat barvy**, které upraví displej pro potřeby uživatelů se zrakovým postižením.|
|**Povolit úpravy inverze barev**|Povolí nebo zakáže úpravy inverze barev, které uživateli umožňují nastavit funkci inverze barev.|
|**Povolit usnadnění dotykového ovládání**|Povolí nebo zakáže nastavení usnadnění **dotykového ovládání**, která uživateli pomáhá provádět na obrazovce gesta, která by pro něho mohla být obtížná.|
|**Povolit úpravy usnadnění dotykového ovládání**|Povolí nebo zakáže úpravy usnadnění dotykového ovládání, které uživateli umožňují upravit funkce usnadnění dotykového ovládání.|
|**Povolit výběr řeči**|Povolí nebo zakáže nastavení usnadnění **Výběr řeči**, které může nahlas přečíst text vybraný uživatelem.|
> [!NOTE]
> Následující poznámky platí pro nastavení celoobrazovkového režimu na zařízeních iOS:
>
> -   Než budete moct nakonfigurovat nastavení zařízení iOS pro celoobrazovkový režim, musíte převést zařízení do režimu dohledu pomocí [nástroje Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) nebo manažera registrace zařízení. Další informace o nástroji Apple Configurator získáte v dokumentaci Apple.
> -   Pokud se určená aplikace pro iOS nainstaluje až po nasazení zásad konfigurace, zařízení nepřejde do celoobrazovkového režimu, dokud ho nerestartujete.

### Referenční informace pro aplikace nesplňující předpisy

Pomocí **sestavy nekompatibilních aplikací** zobrazte kompatibilitu povolených a blokovaných aplikací.

##### Spuštění sestavy nekompatibilních aplikací

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Sestavy** &gt; **Sestava aplikací nedodržujících předpisy**.

2.  Vyberte skupiny zařízení, které chcete zkontrolovat, určete, jestli se mají kontrolovat aplikace dodržující předpisy, aplikace nedodržující předpisy nebo obojí, a potom vyberte **Zobrazit sestavu**.

#### Určení adres URL na obchody s aplikacemi
Pokud chcete zadat adresu URL aplikace do seznamu kompatibilních a nekompatibilních aplikací nebo použít možnost **Vybrat spravovanou aplikaci, která se může spouštět, když je zařízení v celoobrazovkovém režimu** (jenom iOS), použijte následující formát:

1. Pomocí vyhledávacího modulu najděte aplikaci, kterou chcete použít v iTunes App Storu, a otevřete stránku pro tuto aplikaci.

2. Zkopírujte adresu URL stránky a použijte ji jako URL ke konfiguraci seznamu kompatibilních nebo nekompatibilních aplikací nebo aplikace, kterou chcete spustit v celoobrazovkovém režimu.

**Příklad:** Vyhledejte **Microsoft Word pro iPad**. Použitá adresa URL bude **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE]
> Pomocí softwaru iTunes taky můžete najít aplikaci a pomocí příkazu **Kopírovat odkaz** získat adresu URL aplikace.

### Nastavení registrace
Všechna nastavení platí pro iOS 7.1 a novější.

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Povolit zámek aktivace, když je zařízení v režimu pod dohledem**|Povolí zámek aktivace na zařízeních s iOS, které jsou pod dohledem.|

### Dohled
Na zařízeních se systémem iOS 7.1 a novějším, které jsou v režimu pod dohledem, je možné nakonfigurovat následující nastavení.

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Povolit změnu účtu**|Povolí uživateli změnu nastavení účtu, jako je například konfigurace e-mailu.|
|**Povolit AirDrop**|Povolí použití funkce Airdrop k výměně obsahu s blízkými zařízeními.|
|**Povolit změny nastavení využití mobilních dat v aplikaci**|Umožní uživateli řídit, které aplikace můžou používat mobilní data.|
|**Povolit Siri dotazování na uživatelem generovaný obsah z internetu**|Umožní aplikaci Siri získat přístup k webům, aby mohla odpovídat na otázky.|
|**Povolit přístup k obchodu iBooks**|Umožní uživateli procházení a nákup knih z úložiště iBooks.|
|**Povolit změny v nastavení aplikace Find My Friends**|Umožní uživateli změnu nastavení pro aplikaci Find My Friends.|
|**Povolit použití možnosti pro vymazání veškerého obsahu a nastavení na zařízení**|Zpřístupní uživateli možnost pro vymazání veškerého obsahu a nastavení na zařízení.|
|**Povolit uživateli aktivaci omezení v nastavení zařízení**|Umožní uživateli konfigurovat omezení (rodičovské kontroly) na zařízení.|
|**Povolit vrácení výsledků z internetu pomocí vyhledávání Spotlight**|Povolí vyhledávání Spotlight připojit se k internetu, aby bylo možné poskytnout další výsledky.|
|**Povolit použití aplikace Herní centrum**|Povolí použití aplikace Herní centrum.|
|**Povolit určování zařízení, s nimiž se může zařízení s iOS párovat, podle hostitelského párování**|Povolí hostitelské párování, díky kterému může správce určit, se kterými zařízeními se dá spárovat zařízení s iOS 7.|
|**Povolit uživateli instalaci konfiguračních profilů a certifikátů**|Povolí uživateli instalaci konfiguračních profilů a certifikátů.|
|**Povolit použití aplikace Zprávy na zařízení**|Povolit použití aplikace Zprávy k posílání textových zpráv.|


## Nastavení vlastních zásad

Pomocí **vlastní zásady iOS** služby Microsoft Intune nasaďte do zařízení s iOS nastavení, které jste vytvořili pomocí nástroje [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). Pomocí tohoto nástroje se dá vytvořit spousta nastavení, která řídí provoz těchto zařízení, a exportovat je do konfiguračního profilu. Potom tento konfigurační profil můžete naimportovat do vlastní zásady iOS služby Intune a nasadit nastavení pro uživatele a zařízení ve vaší organizaci.

Díky této funkci můžete nasadit nastavení iOS, která nejdou konfigurovat pomocí obecných zásad konfigurace Intune.

### Požadavky
Než začnete, je potřeba nainstalovat Apple Configurator a vytvořit konfigurační soubor s nastaveními, která chcete nasadit pro uživatele nebo zařízení. Apple Configurator si můžete stáhnout z [Mac App Storu](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12), kde o něm také najdete další informace.

> [!NOTE]
> Intune nevytváří sestavu dodržování předpisů pro jednotlivá nastavení vlastní zásady iOS. Vytvoří se ale sestava celkového dodržování zásad.

### Obecná nastavení

|Název nastavení|Podrobnosti|
    |----------------|--------------------|
    |**Název**|Zadejte jedinečný název vlastní zásady pro iOS, abyste ji mohli v konzole Intune snadno identifikovat.|
    |**Popis**|Zadejte popis, který bude shrnovat účel vlastní zásady pro iOS, a uveďte jakékoli další důležité informace, které vám pomůžou zásadu najít.|

### Vlastní nastavení

|Název nastavení|Podrobnosti|
    |----------------|--------------------|
|**Vlastní název konfiguračního profilu (zobrazený uživatelům)**|Zadejte název zásady tak, jak se bude zobrazovat na zařízení a v sestavách zásad Intune.|
|**Soubor konfiguračního profilu**|Vyberte **Importovat** a potom vyhledejte konfigurační profil, který jste vytvořili pomocí nástroje Apple Configurator. **Poznámka:** Nastavení, které exportujete z nástroje Apple Configurator, musí být kompatibilní s verzí iOS na zařízeních, na která nasazujete vlastní zásady pro iOS. Informace o tom, jak se řeší nekompatibilní nastavení, najdete v **referenčních materiálech ke konfiguračnímu profil** a **referenčních materiálech k protokolu správy mobilního zařízení** na [webu pro vývojáře Apple](https://developer.apple.com/).|
    |**Podrobnosti konfiguračního profilu**|Zobrazí kód XML pro konfigurační profil, který jste importovali.|

### Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO1-->


