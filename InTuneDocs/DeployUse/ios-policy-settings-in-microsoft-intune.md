---
# required metadata

title: Nastavení zásad pro iOS | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Nastavení zásad pro iOS v Microsoft Intune

## Obecná nastavení zásad konfigurace

Pomocí **zásad obecné konfigurace pro iOS** v Microsoft Intune můžete nakonfigurovat nastavení pro:

-   **Nastavení zabezpečení mobilního zařízení** – Zvolte ze seznamu předdefinovaných nastavení, která umožňují v zařízení ovládat celou řadu funkcí.

-   **Celoobrazovkový režim** – Umožňuje uzamknout zařízení a povolit fungování jenom některých funkcí. Můžete třeba povolit, aby v zařízení běžela jenom jedna vámi určená spravovaná aplikace, nebo můžete zakázat tlačítka hlasitosti na zařízení. Tato nastavení se dají používat pro ukázkový model zařízení nebo zařízení, které může provádět jenom jednu funkci, jako je třeba zařízení POS.

-   **Seznam aplikací dodržujících a nedodržujících předpisy** – Určete seznam aplikací, které splňují nebo nesplňují předpisy ve vaší společnosti. Na zařízeních s Androidem a iOS je možné používat **Sestavu nekompatibilních aplikací** k zobrazení kompatibility aplikací, které jste uvedli v seznamu, s aplikacemi, které nainstalovali uživatelé (ale nemůžete ve skutečnosti zablokovat instalaci aplikace).

> [!TIP]
> Můžete nakonfigurovat podmínky pro uživatele a zajistit tak jejich informovanost o tom, že aplikace na jejich zařízení, včetně osobních aplikací, se budou hodnotit, a nekompatibilní aplikace se zablokují nebo nahlásí jako nevyhovující. Uživatelé musí přijmout tyto podmínky předtím, než můžou zaregistrovat své zařízení a používat firemní portál k získání aplikací. Další informace o podmínkách a ujednáních týkajících se použití najdete v tématu [Nastavení zásad podmínek a ujednání v Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md).

Pokud v tomto tématu není uvedené nastavení, které hledáte, je možné, že ho budete moct vytvořit pomocí vlastních zásad pro iOS, které vám umožní naimportovat nastavení vytvořená pomocí nástroje [Apple Configurator Tool](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). Další informace najdete v tématu **Nastavení vlastních zásad** dál v tomto tématu.

### Nastavení zabezpečení

|Název nastavení|Podrobnosti|iOS|
|----------------|-------|
|**Vyžadovat heslo k odemknutí mobilních zařízení**|Zadejte, jestli uživatelé při přístupu ke svému zařízení musí zadat heslo.|Ano|
|**Vyžadovaný typ hesla**|Určuje typ hesla, které se bude vyžadovat, například jenom číslice nebo alfanumerické znaky.|Ano|
|**Vyžadovaný typ hesla – Minimální počet znakových sad**|Používají se čtyři znakové sady: malá písmena, velká písmena, číslice a symboly. Toto nastavení určuje, kolik různých znakových sad musí být v hesle zahrnutých). Pro zařízení s iOS ale určuje počet znaků symbolu, které musí být v hesle.)|Ano|
|**Minimální délka hesla**|Určuje minimální počet znaků v hesle.|Ano|
|**Povolit jednoduchá hesla**|Umožňuje použití jednoduchých hesel, jako je třeba 0000 nebo 1234.|Ano|
|**Počet povolených opakovaných neúspěšných přihlášení, než bude zařízení vymazáno**|Vymaže zařízení, pokud tento počet pokusů o přihlášení selže.|Ano|
|**Počet minut nečinnosti před vypnutím displeje**<sup>1</sup>|Zadejte počet minut, než se displej zařízení vypne.|Ano|
|**Omezená platnost hesla (ve dnech)**|Určuje počet dní, než bude nutné změnit heslo zařízení.|Ano|
|**Pamatovat si historii hesel**|Určuje, jestli uživatel může použít hesla, která už použil.|Ano|
|**Pamatovat si historii hesel** – **Zabránit opětovnému použití předchozích hesel**|Určuje počet dříve použitých hesel, která se na zařízení zapamatovávají.|Ano|
|**Počet minut nečinnosti před vyžadováním hesla**<sup>1</sup>|Určuje, jak dlouho může zařízení zůstat nečinné, než uživatel musí znovu zadat heslo.|Ano|
|**Povolit odemknutí otiskem prstu**|Povolí odemknutí zařízení otiskem prstu.|iOS 7.1 nebo novější|
<sup>1</sup> Pokud pro zařízení s iOS nakonfigurujete nastavení **Počet minut nečinnosti před vypnutím displeje** a **Počet minut nečinnosti před vyžadováním hesla**, tato nastavení se použijí v uvedeném pořadí. Pokud například pro obě nastavení nastavíte hodnotu **5** minut, obrazovka se po 5 minutách automaticky vypne a po dalších 5 minutách se zařízení zamkne. Pokud ale uživatel vypne obrazovku ručně, druhé nastavení se použije okamžitě. V tomto příkladě se zařízení po tom, co uživatel vypne obrazovku, zamkne po 5 minutách.

### Nastavení systému

|Název nastavení|Podrobnosti|iOS|
|----------------|-------|
|**Povolit snímek obrazovky**|Povolí uživateli zachytit obsahu obrazovky jako obrázek.|Ano|
|**Povolit řídicí centrum na zamykací obrazovce**|Určuje, jestli je přístup k aplikaci řídicího centra, když je zařízení zamčené.|iOS 7.1 nebo novější|
|**Povolit zobrazení oznámení na zamykací obrazovce**|Povolí uživateli přístup k zobrazení oznámení bez odemknutí zařízení.|iOS 7.1 nebo novější|
|**Povolit zobrazení informací o dnešku na zamykací obrazovce**|Určuje, jestli jde zobrazit oznámení, když je zařízení zamčené.|iOS 7.1 nebo novější|
|**Povolit odeslání diagnostických dat**|Povolí nebo blokuje odesílání diagnostických dat ze zařízení do společnosti Apple.|Ano|
|**Povolit nedůvěryhodné certifikáty TLS**|Povolí v zařízení nedůvěryhodné certifikáty protokolu TLS (Transport Layer Security).|Ano|
|**Povolit aplikaci Passbook při uzamčení**|Povolí uživateli přístup k aplikaci Passbook, když je zařízení uzamčené.|Ano|

### Nastavení cloudu – dokumenty a data

|Název nastavení|Podrobnosti|iOS|
|----------------|-------|
|**Povolit zálohování na iCloud**|Povolí uživateli zálohování zařízení do iCloudu.|Ano|
|**Povolit synchronizaci dokumentů s iCloudem**|Povolí synchronizaci dokumentu a párů klíč-hodnota s úložným prostorem iCloudu. Ano|
|**Povolit synchronizaci datového proudu fotografií s iCloudem**|Povolí synchronizaci fotografií na zařízení s iCloudem.|Ano|
|**Vyžadovat šifrované zálohování**|Vyžaduje, aby všechny zálohy zařízení byly šifrované.|Ano|

### Nastavení aplikace – prohlížeč

|Název nastavení|Podrobnosti|iOS|
|----------------|-------|
|**Povolit Safari**|Určete, jestli se na zařízení může používat prohlížeč Safari.|Ano|
|**Povolit automatické vyplňování**|Uživatel může změnit nastavení automatického dokončování v prohlížeči.|Ano|
|**Povolit blokování automaticky otevíraných oken**|Povolí nebo zakáže blokování automaticky otevíraných oken v prohlížeči.|Ano|
|**Povolit soubory cookie**|Povolí webovému prohlížeči v zařízení používat soubory cookie.|Ano|
|**Povolit skriptování v Javě**|Povolí v prohlížeči spuštění skriptů jazyka Java.|Ano|
|**Povolit upozornění na podvod**|Povolí upozornění na podvod v prohlížeči zařízení.|Ano|

### Nastavení aplikace – aplikace

|Název nastavení|Podrobnosti|iOS|
|----------------|-------|
|**Povolit obchod s aplikacemi**|Povolí zařízení přístup k obchodu s aplikacemi.|Ano|
|**Vyžadovat heslo pro přístup do obchodu s aplikacemi**|Ano|
|**Povolit nákupy v aplikaci**|Povolí ve spuštěné aplikaci nákupy v obchodě.|Ano|
|**Povolit spravované dokumenty v jiných nespravovaných aplikacích**|Povolí prohlížení podnikových dokumentů v libovolné aplikaci.<br>**Příklad:** Chcete zabránit uživatelům v ukládání souborů z aplikace OneDrive na Dropbox. U tohoto nastavení vyberte možnost Ne. Až zařízení zásadu obdrží (třeba po restartování), už nebude povolovat ukládání.|iOS 7.1 nebo novější|
|**Povolit nespravované dokumenty v jiných spravovaných aplikacích**|Povolí prohlížení libovolného dokumentu ve spravovaných podnikových aplikacích.|iOS 7.1 nebo novější|
|**Povolit videokonference**|Povolí na zařízení videokonferenční aplikace, jako je třeba Facetime.|Ano|
|**Povolit obsah pro dospělé v obchodě s mediálním obsahem**|Povolí zařízení přístup k obsahu úložiště, který je označený jako obsah pro dospělé.|Ano|

### Nastavení aplikace – hry

|Název nastavení|Podrobnosti|iOS|
|----------------|-------|
|**Povolit přidávání přátel v herním centru**|Povolí uživateli přidat přátele z herního centra.|Ano|
|**Povolit hru s více hráči**|Povolí uživateli hrát na zařízení hry pro víc hráčů.|Ano|

### Nastavení možností zařízení – hardware

|Název nastavení|Podrobnosti|iOS|
|----------------|-------|
|**Povolit fotoaparát**|Určuje, jestli je možné použít fotoaparát v zařízení.|Ano|

### Nastavení možností zařízení – mobilní

|Název nastavení|Podrobnosti|iOS|
|----------------|-------|
|**Povolit hlasový roaming**|Povolí hlasový roaming, když je zařízení v mobilní síti.|Ano|
|**Povolit datový roaming**|Povolí datový roaming, když je zařízení v mobilní síti.|Ano|
|**Povolit globální načítání na pozadí při roamingu**|Povolí zařízení, aby při roamingu v mobilní síti načítalo data na pozadí, třeba e-maily.|Ano|

### Nastavení možností zařízení – funkce

|Název nastavení|Podrobnosti|iOS|
|----------------|-------|
|**Povolit Siri**|Povolí v zařízení používání hlasového pomocníka Siri.|Ano|
|**Povolit Siri při uzamčení zařízení**|Povolí používání hlasového pomocníka Siri, když je zařízení zamčené.|Ano|
|**Povolit hlasové vytáčení**|Umožňuje používat v zařízení funkci hlasového vytáčení.|Ano|


### Nastavení pro aplikace dodržující a nedodržující předpisy
V seznamu **Kompatibilní a nekompatibilní aplikace** zadejte seznam kompatibilních a nekompatibilních aplikací s využitím následujících informací:

> [!NOTE]
> Jedna zásada může obsahovat seznam jenom kompatibilních, nebo jenom nekompatibilních aplikací. Nejde zadat oba seznamy v jedné zásadě.

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Ohlásit nekompatibilitu, když uživatelé nainstalují aplikace ze seznamu**|Zobrazí seznam aplikací, které Intune nespravuje a které nemají uživatelé dovolené nainstalovat a spustit.|
|**Neoznamovat nekompatibilitu, když uživatel nainstaluje uvedené aplikace**|Zobrazí seznam aplikací, které mají uživatelé dovoleno instalovat. Aby byla zachovaná kompatibilita, uživatelé nesmí instalovat aplikace, které nejsou v seznamu. Aplikace, které spravuje Intune, jsou povolené automaticky.|
|**Přidat**|Přidá aplikaci do vybraného seznamu. Zadejte název podle své volby, volitelně vydavatele aplikaci a adresu URL aplikace v úložišti aplikací. Další pomoc najdete v části **Určení adres URL na obchody s aplikacemi** dál v tomto tématu.|
|**Importovat aplikace**|Importuje seznam aplikací, které jste zadali v souboru hodnot oddělených čárkami. V souboru použijte formát, název aplikace, vydavatele, adresu URL aplikace.|
|**Upravit**|Tady můžete upravit název, vydavatele a adresu URL vybrané aplikace.|
|**Odstranit**|Odstraní vybranou aplikaci ze seznamu.|

### Nastavení celoobrazovkovém režimu

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Vyberte spravovanou aplikaci, která se bude moct spustit, když je zařízení v celoobrazovkovém režimu**|Vyberte **Procházet** a zadejte spravovanou aplikaci nebo aplikaci z obchodu, která se bude moct spouštět, když je zařízení v celoobrazovkovém režimu. Žádné jiné aplikace nebudou mít dovoleno se na zařízení spouštět. Další nápovědu najdete v části **Určení adres URL na obchody s aplikacemi** dál v tomto tématu.|
|**Povolit dotykové ovládání**|Povolí nebo zakáže dotykovou obrazovku na zařízení.|
|**Povolit otočení obrazovky**|Povolí nebo zakáže změnu orientace obrazovky při otočení zařízení.|
|**Povolit tlačítka hlasitosti**|Povolí nebo zakáže použití tlačítek hlasitosti na zařízení.|
|**Povolit přepínač vyzvánění**|Povolí nebo zakáže přepínač vyzvánění (ztlumení) na zařízení.|
|**Povolit tlačítko probuzení z režimu spánku obrazovky**|Povolí nebo zakáže na zařízení tlačítko probuzení z režimu spánku obrazovky.|
|**Povolit automatické uzamčení**|Povolí nebo zakáže automatické uzamykání zařízení.|
|**Povolit mono zvuk**|Povolí nebo zakáže nastavení usnadnění **Mono zvuk**.|
|**Povolit hlasitý přednes**|Povolí nebo zakáže nastavení usnadnění **VoiceOver** , které předčítá text na displeji zařízení.|
|**Povolit úpravy hlasového přednesu**|Povolí nebo zakáže úpravy hlasového přednesu, které umožňují nastavit funkci nástroje VoiceOver (například rychlost čtení textu na obrazovce).|
|**Povolit zvětšení**|Povolí nebo zakáže nastavení usnadnění **Zvětšení** , které vám umožní používat dotykové ovládání pro zvětšení zobrazení zařízení.|
|**Povolit úpravy zvětšení**|Povolí nebo zakáže úpravy zvětšení, které umožňují nastavit funkci zvětšení.|
|**Povolit inverzi barev**|Povolí nebo zakáže nastavení usnadnění **Invertovat barvy** , které upraví displej tak, aby pomáhal uživatelům se zrakovým postižením.|
|**Povolit úpravy inverze barev**|Povolí nebo zakáže úpravy inverze barev, které umožňuje nastavit funkci inverze barev.|
|**Povolit usnadnění dotykového ovládání**|Povolí nebo zakáže nastavení usnadnění **dotykového ovládání** , která uživatelům pomáhá provádět na obrazovce gesta, která by se jim mohla těžko provádět.|
|**Povolit úpravy usnadnění dotykového ovládání**|Povolí nebo zakáže úpravy usnadnění dotykového ovládání, které umožňují upravit funkce usnadnění dotykového ovládání.|
|**Povolit výběr řeči**|Povolí nebo zakáže nastavení usnadnění **Výběr řeči** , které může nahlas přečíst vybraný text.|
> [!NOTE] Následující poznámky platí pro nastavení celoobrazovkového režimu na zařízeních iOS:
> 
> -   Než budete moct nakonfigurovat nastavení zařízení iOS pro celoobrazovkový režim, musíte převést zařízení do režimu dohledu pomocí [nástroje Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) nebo manažera registrace zařízení. Další informace o nástroji Apple Configurator získáte v dokumentaci Apple.
> -   Pokud je určená aplikace pro iOS nainstalovaná až po nasazení zásad konfigurace, zařízení nepřejde do celoobrazovkového, dokud ho nerestartujete.

### Referenční informace pro aplikace nesplňující předpisy

#### Monitorování aplikací, které splňují a nesplňují předpisy
Pomocí **sestavy nekompatibilních aplikací** zobrazte kompatibilitu povolených a blokovaných aplikací.

##### Spuštění sestavy nekompatibilních aplikací

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Sestavy** &gt; **Sestava aplikací nedodržujících předpisy**.

2.  Vyberte skupiny zařízení, které chcete zkontrolovat, určete, jestli se mají kontrolovat aplikace dodržující předpisy, aplikace nedodržující předpisy nebo obojí a potom vyberte **Zobrazit sestavu**.

#### Určení adres URL na obchody s aplikacemi
Pokud chcete zadat adresu URL aplikace do seznamu kompatibilních a nekompatibilních aplikací nebo použít možnost **Vybrat spravovanou aplikaci, která se může spouštět, když je zařízení v celoobrazovkovém režimu** (jenom iOS), použijte následující formát:

Pomocí vyhledávacího modulu najděte aplikaci, kterou chcete použít v iTunes App Storu, a otevřete stránku pro aplikaci.

Zkopírujte adresu URL stránky a použijte ji jako URL ke konfiguraci seznamu kompatibilních nebo nekompatibilních aplikací nebo aplikace, kterou chcete spustit v celoobrazovkovém režimu.

**Příklad:** Vyhledejte **Microsoft Word pro iPad**. Použitá adresa URL bude **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE] Pomocí softwaru iTunes taky můžete najít aplikaci a pomocí příkazu **Kopírovat odkaz** získat adresu URL aplikace.


## Nastavení vlastních zásad

Pomocí **vlastní zásady iOS** služby Microsoft Intune nasaďte do zařízení s iOS nastavení, které jste vytvořili pomocí nástroje [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). Pomocí tohoto nástroje se dá vytvořit spousta nastavení, která řídí provoz těchto zařízení, a exportovat je do konfiguračního profilu. Potom tento konfigurační profil můžete naimportovat do vlastní zásady iOS služby Intune a nasadit nastavení pro uživatele a zařízení ve vaší organizaci.

Díky této funkci můžete nasadit nastavení iOS, která nejdou konfigurovat pomocí obecných zásad konfigurace Intune.

### Požadavky
Než začnete, je potřeba nainstalovat Apple Configurator a vytvořit konfigurační soubor s nastaveními, která chcete nasadit pro uživatele nebo zařízení. Apple Configurator si můžete stáhnout z [Mac App Storu](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12), kde taky najdete informace o něm.

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
|**Soubor konfiguračního profilu**|Vyberte **Importovat** a potom vyhledejte konfigurační profil, který jste vytvořili pomocí nástroje Apple Configurator. **Poznámka:** Nastavení, které exportujete z nástroje Apple Configurator, musí být kompatibilní s verzí iOS na zařízeních, na která nasazujete vlastní zásady pro iOS. Informace o tom, jak se řeší nekompatibilní nastavení, najdete v **referenci na konfigurační profil** a **referenci na protokol správy mobilního zařízení** na [webu pro vývojáře Apple](https://developer.apple.com/).|
    |**Podrobnosti konfiguračního profilu**|Zobrazí kód XML pro konfigurační profil, který jste importovali.|

### Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jun16_HO2-->


