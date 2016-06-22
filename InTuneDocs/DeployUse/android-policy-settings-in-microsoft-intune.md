---
# required metadata

title: Nastavení zásad konfigurace pro Android a Samsung KNOX | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Nastavení zásad konfigurace pro Android a Samsung KNOX v Microsoft Intune

## Zásady obecné konfigurace

Pomocí **zásad obecné konfigurace pro Android** v Microsoft Intune můžete nakonfigurovat nastavení pro:

-   **Nastavení zabezpečení mobilního zařízení** – Zvolte ze seznamu předdefinovaných nastavení, která umožňují v zařízení ovládat celou řadu funkcí.

-   **Celoobrazovkový režim** (jenom pro zařízení Samsung KNOX) – Umožňuje uzamknout zařízení a povolit fungování jen některých funkcí. Můžete třeba povolit, aby v zařízení běžela jenom jedna vámi určená spravovaná aplikace, nebo můžete zakázat tlačítka hlasitosti na zařízení. Tato nastavení se dají používat pro ukázkový model zařízení nebo zařízení, které může provádět jenom jednu funkci, jako je třeba zařízení POS.

-   **Seznam aplikací dodržujících a nedodržujících předpisy** – Určete seznam aplikací, které splňují nebo nesplňují předpisy ve vaší společnosti. Na zařízeních s Androidem a iOS je možné používat **Sestavu nekompatibilních aplikací** k zobrazení kompatibility aplikací, které jste uvedli v seznamu, s aplikacemi, které nainstalovali uživatelé (ale nemůžete ve skutečnosti zablokovat instalaci aplikace).

> [!TIP]
> Můžete nakonfigurovat podmínky pro uživatele a zajistit tak jejich informovanost o tom, že aplikace na jejich zařízení, včetně osobních aplikací, se budou hodnotit, a nekompatibilní aplikace se zablokují nebo nahlásí jako nevyhovující. Uživatelé musí přijmout tyto podmínky předtím, než můžou zaregistrovat své zařízení a používat firemní portál k získání aplikací. Další informace o podmínkách a ujednáních týkajících se použití najdete v tématu [Nastavení zásad podmínek a ujednání v Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md).

Pokud se v tomto tématu nezobrazí nastavení, které hledáte, je možné, že ho budete moci vytvořit pomocí vlastních zásad pro Android, které vám k řízení zařízení umožňuje použít nastavení OMA-URI. Další informace najdete v tématu **Nastavení vlastních zásad** dál v tomto tématu.

### Nastavení hesla

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX|
|----------------|-|----------------|----------------|
|**Vyžadovat heslo k odemknutí mobilních zařízení**|Vyžaduje heslo na podporovaných zařízeních.|Ano|Ano|
|**Minimální délka hesla**|Vyžadovaná minimální délka hesla.|Ano|Ano|
|**Počet povolených opakovaných neúspěšných přihlášení, než bude zařízení vymazáno**|Vymaže zařízení, pokud tento počet pokusů o přihlášení selže.|Ano|Ano|
|**Počet minut nečinnosti před vypnutím displeje**|Zadejte počet minut, než se zařízení automaticky zamkne.|Ano|Ano|
|**Omezená platnost hesla (ve dnech)**|Počet dní, než bude heslo nutné změnit.|Ano|Ano|
|**Pamatovat si historii hesel**|Zapamatuje si tento počet dříve použitých hesel.|Ano|Ano|
|**Pamatovat si historii hesel** – **Zabránit opětovnému použití předchozích hesel**|Zabraňuje opakovanému použití už použitých hesel.|Ano|Ano|
|**Kvalita hesla**|Vyberte požadovanou úroveň složitosti hesla a taky to, jestli se můžou používat biometrická zařízení.|Ano|Ano|
|**Povolit odemknutí otiskem prstu**|Povolí odemknutí zařízení otiskem prstu.|Ne|Ano|

### Nastavení šifrování

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Vyžadovat šifrování u mobilního zařízení**|Vyžaduje, aby soubory v mobilním zařízení byly šifrované.|Ano|Ano|
|**Vyžadovat šifrování u paměťových karet**|Určuje, jestli musí být paměťová karta zařízení šifrovaná.|Ne|Ano|

### Nastavení systému

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Povolit snímek obrazovky**|Umožňuje uživateli zachytit obsah obrazovky v podobě obrázku.|Ne|Ano|
|**Povolit odeslání diagnostických dat**|Umožňuje zařízení odesílat diagnostické informace Googlu.|Ne|Ano|
|**Povolit obnovení továrního nastavení**|Umožňuje uživateli obnovit v zařízení výrobní nastavení.|Ne|Ano|

### Nastavení cloudu – dokumenty a data

|Název nastavení|Podrobnosti|Android a Samsung KNOX|Android 4.0+|
|----------------|----------------------------|----------------|
|**Povolit zálohování Google**|Povoluje použití zálohování Google.|Ne|Ano|

### Nastavení cloudu – účty a synchronizace

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Povolit automatickou synchronizaci účtu Google**|Povoluje automatickou synchronizaci nastavení účtu Google.|Ne|Ano|

### Nastavení aplikace – prohlížeč

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Povolit webový prohlížeč**|Určuje, jestli je možné použít webový prohlížeč zařízení.|Ne|Ano|
|**Povolit automatické vyplňování**|Umožňuje používání funkce automatického vyplňování webového prohlížeče.|Ne|Ano|
|**Povolit blokování automaticky otevíraných oken**|Povolí používání blokování automaticky otevíraných oken ve webovém prohlížeči.|Ne|Ano|
|**Povolit soubory cookie**|Povolí webovému prohlížeči v zařízení používat soubory cookie.|Ne|Ano|
|**Povolit aktivní skriptování**|Povolí webovému prohlížeči v zařízení aktivní skriptování.|Ne|Ano|

### Nastavení aplikace – aplikace

|Název nastavení|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Povolit Google Play Store**|Povolí uživatelům na zařízení přístup do obchodu Google Play.|Ne|Ano|

### Nastavení možností zařízení – hardware

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Povolit fotoaparát**|Umožňuje použití fotoaparátu v zařízení.|Ano|Ano|
|**Povolit vyměnitelné úložiště**|Povolí použití vyjímatelného úložiště v zařízení, třeba SD karty.|Ne|Ano|
|**Povolit Wi-Fi**|Povolí použití možností Wi-Fi zařízení.|Ne|Ano|
|**Povolit sdílení internetového připojení přes Wi-Fi**|Povolí použití sdíleného internetového připojení přes Wi-Fi na zařízení.|Ne|Ano|
|**Povolit zeměpisnou polohu**|Umožňuje zařízení využívat informace o umístění.|Ne|Ano|
|**Povolit komunikaci NFC**|Umožňuje operace, které používají bezkontaktní komunikaci, pokud je zařízení podporuje.|Ne|Ano|
|**Povolit Bluetooth**|Povolí používání připojení Bluetooth na zařízení.|Ne|Ano|
|**Povolit vypnutí napájení**|Povolí uživateli vypnout zařízení.<br /><br />Pokud je toto nastavení zakázané, nastavení **Počet povolených opakovaných neúspěšných přihlášení, než bude zařízení vymazáno** pro zařízení Samsung KNOX není funkční.|Ne|Ano|

### Nastavení možností zařízení – mobilní

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Povolit hlasový roaming**|Povolí hlasový roaming, když je zařízení v mobilní síti.|Ne|Ano|
|**Povolit datový roaming**|Povolí datový roaming, když je zařízení v mobilní síti.|Ne|Ano|
|**Povolit SMS a MMS zprávy**|Povolí zařízení použití SMS a MMS zpráv.|Ne|Ano|

### Nastavení možností zařízení – funkce

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Povolit hlasového asistenta**|Povolí použití softwaru hlasového asistenta v zařízení.|Ne|Ano|
|**Povolit hlasové vytáčení**|Povolí nebo zakáže použití funkce hlasového vytáčení v zařízení.|Ne|Ano|
|**Povolit kopírování a vkládání**|Povolí v zařízení funkce kopírování a vkládání.|Ne|Ano|
|**Povolit sdílení schránky mezi aplikacemi**|Pro kopírování a vkládání mezi jednotlivými aplikacemi se používá schránka.|Ne|Ano|
|**Povolit YouTube**|Povolí použití YouTube v zařízení.|Ne|Ano|

### Nastavení pro aplikace dodržující a nedodržující předpisy
V seznamu **Kompatibilní a nekompatibilní aplikace** zadejte seznam kompatibilních a nekompatibilních aplikací s využitím následujících informací:

> [!NOTE]
> Jedna zásada může obsahovat seznam jenom kompatibilních, nebo jenom nekompatibilních aplikací. Nejde zadat oba seznamy v jedné zásadě.

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Ohlásit nekompatibilitu, když uživatelé nainstalují aplikace ze seznamu**|Zobrazí seznam aplikací, které nejsou spravované pomocí Intune a u kterých nechcete, aby je uživatelé instalovali a spouštěli. Pokud si uživatelé některé z těchto aplikací nainstalují, objeví se na v sestavě aplikací nesplňujících požadavky.|
|**Neoznamovat nekompatibilitu, když uživatel nainstaluje uvedené aplikace**|Zobrazí seznam aplikací, které chcete v rámci společnosti povolit. Kvůli zachování kompatibility nesmí uživatelé instalovat aplikace, které nejsou v seznamu uvedené. Aplikace, které spravuje Intune, jsou povolené automaticky.|
|**Přidat**|Přidá aplikaci do vybraného seznamu. Zadejte název podle své volby, volitelně vydavatele aplikaci a adresu URL aplikace v úložišti aplikací.<br /><br />Další nápovědu najdete v části Určení adres URL na obchody s aplikacemi dál v tomto tématu.|
|**Importovat aplikace**|Importuje seznam aplikací, které jste zadali v souboru hodnot oddělených čárkami. V souboru použijte formát, název aplikace, vydavatele, adresu URL aplikace.|
|**Upravit**|Tady můžete upravit název, vydavatele a adresu URL vybrané aplikace.|
|**Odstranit**|Odstraní vybranou aplikaci ze seznamu.|

### Nastavení celoobrazovkovém režimu
Zadejte pro **zařízení Samsung KNOX** následující nastavení:

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Vyberte spravovanou aplikaci, která se bude moct spustit, když je zařízení v celoobrazovkovém režimu**|Zvolte **Procházet** a vyberte spravovanou aplikaci, která se bude moct spustit, když je zařízení v celoobrazovkovém režimu (v současné době se nepodporují aplikace v podobě odkazu na obchod). Žádné jiné aplikace nebudou mít dovoleno se na zařízení spouštět.|
|**Povolit tlačítka hlasitosti**|Povolí nebo zakáže použití tlačítek hlasitosti na zařízení.|
|**Povolit tlačítko probuzení z režimu spánku obrazovky**|Povolí nebo zakáže na zařízení tlačítko probuzení z režimu spánku obrazovky.|

### Referenční informace pro aplikace nesplňující předpisy

#### Monitorování aplikací, které splňují a nesplňují předpisy
Pomocí **sestavy nekompatibilních aplikací** zobrazte kompatibilitu povolených a blokovaných aplikací.

###### Spuštění sestavy nekompatibilních aplikací

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Sestavy** &gt; **Sestava aplikací nedodržujících předpisy**.

2.  Vyberte skupiny zařízení, které chcete zkontrolovat, určete, jestli se mají kontrolovat aplikace dodržující předpisy, aplikace nedodržující předpisy nebo obojí a potom vyberte **Zobrazit sestavu**.

#### Určení adres URL na obchody s aplikacemi
Pokud chcete zadat adresu URL aplikace do seznamu kompatibilních a nekompatibilních aplikací, použijte následující formát:

V [oddílu Aplikace na Google Play](https://play.google.com/store/apps) najděte aplikaci, kterou chcete použít.

Otevřete instalační stránku aplikace a zkopírujte adresu URL do schránky. Tu teď můžete použít jako adresu URL v seznamu kompatibilních nebo nekompatibilních aplikací.

**Příklad:** Na webu Google Play vyhledejte systém Microsoft Office Mobile. Použijete adresu URL **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

## Nastavení vlastních zásad
Pomocí možnosti Microsoft Intune **Zásady vlastní konfigurace pro Android** nasaďte nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier), které se dá používat k ovládání funkcí na zařízeních s Androidem. Jsou to standardní nastavení, která k ovládání funkcí zařízení používá spousta výrobců mobilních zařízení.

Díky této vlastnosti můžete nasadit nastavení Androidu, která nejde konfigurovat se zásadami Intune.

> [!NOTE] Vlastní zásady Androidu v současné době podporují konfiguraci nastavení Wi-Fi jenom pro taková zařízení s Androidem, která obsahují předsdílený klíč.

### Obecná nastavení

|Název nastavení|Podrobnosti|
    |----------------|--------------------|
    |**Název**|Zadejte jedinečný název vlastní zásady pro Android, abyste ji mohli v konzole Intune snadno identifikovat.|
    |**Popis**|Zadejte popis, který bude shrnovat účel vlastní zásady pro Android, a uveďte jakékoli další důležité informace, které vám pomůžou zásadu najít.|

### Nastavení OMA-URI

   |Název nastavení|Podrobnosti|
    |--------|--------------------|
    |**Název nastavení**|Zadejte jedinečný název nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení.|
    |**Popis nastavení**|Zadejte popis, který nastavení přehledně vystihne, a další důležité informace, které vám ho pomůžou najít.|
    |**Datový typ**|Vyberte datový typ, ve kterém toto nastavení OMA-URI určíte. Vyberte z možností **Řetězec, Řetězec (XML), Datum a čas, Celé číslo, Číslo s plovoucí desetinnou čárkou** nebo **Logická hodnota**.|
    |**OMA-URI (rozlišuje velká a malá písmena)**|Zadejte OMA-URI, pro který chcete zadat nastavení.|
    |**Hodnota**|Zadejte hodnotu pro přidružení k OMA-URI, který jste zadali dřív.|

### Příklad: Konfigurace vlastního profilu Wi-Fi s předsdíleným klíčem
I když Intune podporuje profily Wi-Fi pro zařízení s Androidem, tato funkce v současné době nepodporuje zahrnutí předsdíleného klíče do konfigurace. V tomto příkladu se dozvíte, jak vytvořit vlastní zásadu pro Android, která vytvoří profil Wi-Fi s předsdíleným klíčem na zařízení s Androidem.

#### Vytvoření profilu Wi-Fi s předsdíleným klíčem

1.  Ověřte, jestli uživatelé mají nejnovější verzi aplikace [Firemní portál Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) pro Android.

2.  Vytvořte vlastní zásadu pro Android a přidejte následující nastavení:

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Název nastavení**|Zadejte název svého výběru pro nastavení.|
|**Popis nastavení**|Zadejte popis nastavení.|
|**Datový typ**|Vyberte **Řetězec (XML)**.|
|**OMA-URI**|Zadejte následující: ./Vendor/MSFT/WiFi/Profile/*&lt;váš profil Wi-Fi&gt;*/Settings|

3.  Do položky **Hodnota** zkopírujte a vložte následující kód XML:

    ```
    <!--
    WEP Wifi Profile
                    <Name of wifi profile> = Name of profile 
                    <SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
                    <WEP password> = Password to connect to the network
    -->
    <WLANProfile 
    xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name><Name of wifi profile></name>
      <SSIDConfig>
        <SSID>
          <name><SSID of wifi profile></name>
        </SSID>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <MSM>
        <security>
          <authEncryption>
            <authentication>open</authentication>
            <encryption>WEP</encryption>
            <useOneX>false</useOneX>
          </authEncryption>
          <sharedKey>
            <keyType>networkKey</keyType>
            <protected>false</protected>
            <keyMaterial><WEP password></keyMaterial>
          </sharedKey>
          <keyIndex>0</keyIndex>
        </security>
      </MSM>
    </WLANProfile>
    ```

4.  Po dokončení uložte zásadu a nasaďte ji na požadovaná zařízení s Androidem. Nový profil Wi-Fi se zobrazí v seznamu připojení na zařízení.

### Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jun16_HO2-->


