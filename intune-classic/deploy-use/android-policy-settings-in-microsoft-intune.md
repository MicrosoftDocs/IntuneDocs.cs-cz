---
title: "Nastavení zásad konfigurace pro Android a Samsung KNOX"
description: "Vytvořte zásady, které řídí nastavení a funkce na zařízeních s Androidem, která spravujete pomocí Intune."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e1b18486f84bb5d4d47caceb871bf6884b9b8f89
ms.sourcegitcommit: 53a1f5226d1e1172f013a1b192321dde610b2d6c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2017
---
# <a name="android-and-samsung-knox-standard-policy-settings-in-microsoft-intune"></a>Nastavení zásad konfigurace pro Android a Samsung KNOX Standard v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune poskytuje řadu předdefinovaných obecných nastavení, která můžete konfigurovat v zařízeních s Androidem. Navíc můžete určit hodnoty OMA-URI (Open Mobile Alliance Uniform Resource Identifier) k vytvoření vlastních nastavení, která nejsou k dispozici prostřednictvím Intune.

## <a name="general-configuration-policy"></a>Zásady obecné konfigurace

Pomocí **zásady obecné konfigurace pro Android** služby Intune můžete nakonfigurovat nastavení pro:

-   **Nastavení zabezpečení mobilního zařízení** – Zvolte ze seznamu předdefinovaných nastavení, která umožňují v zařízení ovládat celou řadu funkcí.

-   **Celoobrazovkový režim** (jenom pro zařízení Samsung KNOX Standard) – Umožňuje uzamknout zařízení a povolit fungování jenom některých funkcí. Můžete třeba povolit, aby v zařízení běžela jenom jedna vámi určená spravovaná aplikace, nebo můžete na zařízení zakázat tlačítka hlasitosti. Tato nastavení se dají používat pro ukázkový model zařízení nebo zařízení, které může provádět jenom jednu funkci, jako je třeba zařízení POS.

-   **Seznam aplikací dodržujících a nedodržujících předpisy** – Určete seznam aplikací, které splňují nebo nesplňují předpisy ve vaší společnosti. Na zařízeních s Androidem a iOS je možné používat **Sestavu nekompatibilních aplikací** k zobrazení kompatibility aplikací, které jste uvedli v seznamu, s aplikacemi, které nainstalovali uživatelé. Sestava ale nemůže ve skutečnosti zablokovat instalaci aplikace.

> [!TIP]
> Můžete nakonfigurovat podmínky pro uživatele a zajistit tak jejich informovanost o tom, že všechny aplikace na jejich zařízení, včetně osobních aplikací, se budou hodnotit, a nekompatibilní aplikace se zablokují nebo nahlásí jako nevyhovující. Uživatelé musí přijmout tyto podmínky předtím, než můžou zaregistrovat své zařízení a používat firemní portál k získání aplikací. Další informace o podmínkách a ujednáních týkajících se použití najdete v tématu [Nastavení zásad podmínek a ujednání v Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md).

Pokud se v tomto tématu nezobrazí nastavení, které hledáte, je možné, že ho budete moct vytvořit pomocí vlastních zásad pro Android, které vám k řízení zařízení umožňuje použít nastavení OMA-URI. Další informace najdete v části [Nastavení vlastních zásad](#custom-policy-settings) dál v tomto tématu.

### <a name="password-settings"></a>Nastavení hesla

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|----------------|-|----------------|----------------|
|**Vyžadovat heslo k odemknutí mobilních zařízení**|Určuje, jestli se vyžaduje heslo na podporovaných zařízeních.|Ano|Ano|
|**Minimální délka hesla**|Určuje minimální délku hesla.|Ano|Ano|
|**Počet povolených opakovaných neúspěšných přihlášení, než se zařízení vymaže**|Určuje počet povolených neúspěšných přihlášení, než bude zařízení vymazáno.|Ano|Ano|
|**Počet minut nečinnosti před vypnutím displeje**|Určuje počet minut nečinnosti, než se zařízení automaticky zamkne.|Ano|Ano|
|**Vypršení platnosti hesla (dny)**|Určuje počet dní, než bude heslo nutné změnit.|Ano|Ano|
|**Pamatovat si historii hesel**|Určuje počet dříve použitých hesel, která se pamatují.|Ano|Ano|
|**Pamatovat si historii hesel** - **Zabránit opětovnému použití předchozích hesel**|Brání opakovanému použití předchozích hesel.|Ano|Ano|
|**Kvalita hesla**|Určuje požadovanou úroveň složitosti hesla a to, jestli se můžou používat biometrická zařízení.|Ano|Ano|
|**Povolit odemknutí otiskem prstu**|Povolí odemknutí zařízení otiskem prstu.|Ne|Ano|
|**Povolit Smart Lock a další důvěryhodné agenty**<br>(Android 5 nebo novější)|Umožňuje řídit funkci Smart Lock v kompatibilních zařízeních s Androidem. Tato funkce telefonů, které se někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo uzamčené obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění (například pokud je připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC). Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.|Ano|Ne|

### <a name="encryption-settings"></a>Nastavení šifrování

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|----------------|---|-------------|----------------|
|**Vyžadovat šifrování u mobilního zařízení**|Vyžaduje, aby soubory v mobilním zařízení byly šifrované.|Ano|Ano|
|**Vyžadovat šifrování u paměťových karet**|Určuje, jestli musí být paměťová karta zařízení šifrovaná.|Ne|Ano|

### <a name="system-settings"></a>Nastavení systému

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|----------------|---|-------------|----------------|
|**Povolit snímek obrazovky**|Umožňuje uživateli zachytit obsah obrazovky v podobě obrázku.|Ne|Ano|
|**Povolit odeslání diagnostických dat**|Umožňuje zařízení odesílat diagnostické informace Googlu.|Ne|Ano|
|**Povolit obnovení do výrobního nastavení**|Umožňuje uživateli obnovit v zařízení výrobní nastavení.|Ne|Ano|

### <a name="cloud-settings---documents-and-data"></a>Nastavení cloudu – dokumenty a data

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|----------------|----|------------------------|----------------|
|**Povolit zálohy na Googlu**|Povoluje použití zálohování Google.|Ne|Ano|

### <a name="cloud-settings---accounts-and-synchronization"></a>Nastavení cloudu – účty a synchronizace

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|----------------|-----|-----------|----------------|
|**Povolit automatickou synchronizaci účtu Google**|Povoluje automatickou synchronizaci nastavení účtu Google.|Ne|Ano|

### <a name="application-settings---browser"></a>Nastavení aplikace – prohlížeč

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|----------------|-----|-----------|----------------|
|**Povolit webový prohlížeč**|Určuje, jestli je možné použít výchozí webový prohlížeč zařízení.|Ne|Ano|
|**Povolit automatické vyplňování**|Umožňuje používání funkce automatického vyplňování webového prohlížeče.|Ne|Ano|
|**Povolit blokování automaticky otevíraných oken**|Povolí používání blokování automaticky otevíraných oken ve webovém prohlížeči.|Ne|Ano|
|**Povolit soubory cookie**|Povolí webovému prohlížeči v zařízení používat soubory cookie.|Ne|Ano|
|**Povolit aktivní skriptování**|Povolí webovému prohlížeči v zařízení aktivní skriptování.|Ne|Ano|

### <a name="application-settings---apps"></a>Nastavení aplikace – aplikace

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|----------------|----|------------|----------------|
|**Povolit obchod Google Play**|Povolí uživatelům na zařízení přístup do obchodu Google Play.|Ne|Ano|

### <a name="device-capabilities-settings---hardware"></a>Nastavení možností zařízení – hardware

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|----------------|-----|-----------|----------------|
|**Povolit fotoaparát**|Umožňuje použití fotoaparátu v zařízení.|Ano|Ano|
|**Povolit vyměnitelné úložiště**|Povolí použití vyjímatelného úložiště v zařízení, třeba SD karty.|Ne|Ano|
|**Povolit Wi-Fi**|Povolí použití možností Wi-Fi zařízení.|Ne|Ano|
|**Povolit Wi-Fi tethering**|Povolí použití sdíleného internetového připojení přes Wi-Fi na zařízení.|Ne|Ano|
|**Povolit zeměpisnou polohu**|Umožňuje zařízení využívat informace o umístění.|Ne|Ano|
|**Povolit komunikaci NFC**|Umožňuje operace, které používají bezkontaktní komunikaci, pokud je zařízení podporuje.|Ne|Ano|
|**Povolit Bluetooth**|Povolí používání připojení Bluetooth na zařízení.|Ne|Ano|
|**Povolit vypnutí**|Povolí uživateli vypnout zařízení.<br /><br />Pokud je toto nastavení zakázané, není nastavení **Počet povolených opakovaných neúspěšných přihlášení, než se zařízení vymaže** pro zařízení Samsung KNOX Standard funkční.|Ne|Ano|

### <a name="device-capabilities-settings---cellular"></a>Nastavení možností zařízení – mobilní

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|----------------|---|-------------|----------------|
|**Povolit hlasový roaming**|Povolí hlasový roaming, když je zařízení v mobilní síti.|Ne|Ano|
|**Povolit datový roaming**|Povolí datový roaming, když je zařízení v mobilní síti.|Ne|Ano|
|**Povolit SMS a MMS zprávy**|Povolí zařízení použití SMS a MMS zpráv.|Ne|Ano|

### <a name="device-capabilities-settings---features"></a>Nastavení možností zařízení – funkce

|Název nastavení|Podrobnosti|Android 4.0+|Samsung KNOX Standard|
|----------------|----|------------|----------------|
|**Povolit hlasového pomocníka**|Povolí použití softwaru hlasového asistenta v zařízení.|Ne|Ano|
|**Povolit hlasové vytáčení**|Povolí nebo zakáže použití funkce hlasového vytáčení v zařízení.|Ne|Ano|
|**Povolit kopírování a vkládání**|Povolí v zařízení funkce kopírování a vkládání.|Ne|Ano|
|**Povolit sdílení schránky mezi aplikacemi**|Povolí používání schránky pro kopírování a vkládání mezi jednotlivými aplikacemi.|Ne|Ano|
|**Povolit YouTube**|Povolí použití YouTube v zařízení.|Ne|Ano|

### <a name="settings-for-compliant-and-noncompliant-apps"></a>Nastavení pro aplikace dodržující a nedodržující předpisy
V seznamu **Kompatibilní a nekompatibilní aplikace** zadejte seznam kompatibilních a nekompatibilních aplikací s využitím následujících informací:

> [!NOTE]
> Jedna zásada může obsahovat seznam jenom kompatibilních aplikací, nebo jenom nekompatibilních aplikací. Nejde zadat oba seznamy v jedné zásadě.

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Ohlásit nekompatibilitu, když uživatelé nainstalují aplikace ze seznamu**|Zobrazí seznam aplikací, které nejsou spravované pomocí Intune a u kterých nechcete, aby je uživatelé instalovali a spouštěli. Pokud si uživatelé některé z těchto aplikací nainstalují, objeví se na v sestavě aplikací nesplňujících požadavky.|
|**Neohlásit nekompatibilitu, když uživatelé nainstalují aplikace ze seznamu**|Zobrazí seznam aplikací, které chcete povolit. Kvůli zachování kompatibility nesmí uživatelé instalovat aplikace, které nejsou v seznamu uvedené. Aplikace, které spravuje Intune, jsou povolené automaticky.|
|**Přidat**|Přidá aplikaci do vybraného seznamu. Zadejte název aplikace, vydavatele aplikace (volitelné) a adresu URL aplikace v úložišti aplikací.<br /><br />Další informace najdete v části [Určení adres URL na obchody s aplikacemi](#specify-urls-to-app-stores) dál v tomto tématu.|
|**Importovat aplikace**|Importuje seznam aplikací, které jste zadali v souboru hodnot oddělených čárkami. V souboru použijte formát: název aplikace, vydavatel a adresa URL aplikace.|
|**Upravit**|Tady můžete upravit název, vydavatele a adresu URL vybrané aplikace.|
|**Odstranit**|Odstraní vybranou aplikaci ze seznamu.|

Zásady, které obsahují kompatibilní a nekompatibilní nastavení aplikace, se musí nasadit do skupin uživatelů.

### <a name="kiosk-mode-settings"></a>Nastavení celoobrazovkovém režimu
Zadejte pro **zařízení Samsung KNOX Standard** následující nastavení:

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Vyberte spravovanou aplikaci, která se bude dát spustit, když bude zařízení v celoobrazovkovém režimu**|Zvolte **Procházet** a vyberte spravovanou aplikaci, která se může spustit, když je zařízení v celoobrazovkovém režimu (v současné době se nepodporují aplikace v podobě odkazu na obchod). Žádné jiné aplikace nebudou mít dovoleno se na zařízení spouštět.|
|**Povolit tlačítka hlasitosti**|Povolí nebo zakáže použití tlačítek hlasitosti na zařízení.|
|**Povolit tlačítko pro probuzení obrazovky z režimu spánku**|Povolí nebo zakáže na zařízení tlačítko probuzení z režimu spánku obrazovky.|

### <a name="reference-information-for-compliant-and-noncompliant-apps"></a>Referenční informace pro aplikace nesplňující předpisy

#### <a name="monitor-compliant-and-noncompliant-apps"></a>Monitorování aplikací, které splňují a nesplňují předpisy
Pomocí **sestavy nekompatibilních aplikací** zobrazte kompatibilitu povolených a blokovaných aplikací.

###### <a name="to-run-the-noncompliant-apps-report"></a>Spuštění sestavy nekompatibilních aplikací

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Sestavy** &gt; **Sestava aplikací nedodržujících předpisy**.

2.  Vyberte skupiny zařízení, které chcete zkontrolovat. Pak určete, jestli se mají kontrolovat aplikace dodržující předpisy, aplikace nedodržující předpisy nebo obojí. Nakonec vyberte **Zobrazit sestavu**.

#### <a name="specify-urls-to-app-stores"></a>Určení adres URL na obchody s aplikacemi
Pokud chcete zadat adresu URL aplikace do seznamu kompatibilních a nekompatibilních aplikací, použijte následující postup:

V [oddílu Aplikace na Google Play](https://play.google.com/store/apps) najděte aplikaci, kterou chcete použít.

Otevřete instalační stránku aplikace a zkopírujte adresu URL do schránky. Tu teď můžete použít jako adresu URL v seznamu kompatibilních nebo nekompatibilních aplikací.

Příklad: Na webu Google Play vyhledejte systém Microsoft Office Mobile. Použijete adresu URL **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

## <a name="custom-policy-settings"></a>Nastavení vlastních zásad
Pomocí možnosti Microsoft Intune **Zásady vlastní konfigurace pro Android** nasaďte nastavení OMA-URI, které se dá používat k ovládání funkcí na zařízeních s Androidem. Jsou to standardní nastavení, která k ovládání funkcí zařízení používá spousta výrobců mobilních zařízení.

Díky této vlastnosti můžete nasadit nastavení Androidu, která nejde konfigurovat se zásadami Intune.
Intune v současnosti podporuje omezený počet vlastních zásad Androidu. Pokud chcete zjistit, které zásady můžete nakonfigurovat, podívejte se na ukázky v tomto tématu.

### <a name="general-settings"></a>Obecná nastavení

|Název nastavení|Podrobnosti|
    |----------------|--------------------|
    | **Název** |Zadejte jedinečný název vlastní zásady pro Android, abyste ji mohli v konzole Intune snadno identifikovat.|
    | **Popis** |Zadejte popis, který bude shrnovat účel vlastní zásady pro Android, a uveďte jakékoli další důležité informace, které vám pomůžou zásadu najít.|

### <a name="oma-uri-settings"></a>Nastavení OMA-URI

   |Název nastavení|Podrobnosti|
    |--------|--------------------|
    | **Název nastavení** |Zadejte jedinečný název nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení.|
    | **Popis nastavení** |Zadejte popis, který nastavení přehledně vystihne, a další důležité informace, které vám ho pomůžou najít.|
    | **Datový typ** |Vyberte datový typ, ve kterém toto nastavení OMA-URI určíte. Vyberte z možností **Řetězec, Řetězec (XML), Datum a čas, Celé číslo, Číslo s plovoucí desetinnou čárkou** nebo **Logická hodnota**.|
    | **OMA-URI (rozlišování velkých a malých písmen)** |Zadejte OMA-URI, pro který chcete zadat nastavení.|
    | **Hodnota** |Zadejte hodnotu pro přidružení k OMA-URI, který jste zadali dřív.|

### <a name="examples"></a>Příklady

- [Vytvoření profilu Wi-Fi s předsdíleným klíčem](pre-shared-key-wi-fi-profile.md)
- [Použití vlastních zásad pro vytvoření profilu sítě VPN pro jednotlivé aplikace pro zařízení se systémem Android](per-app-vpn-for-android-pulse-secure.md)
- [Použití vlastních zásad povolených a blokovaných aplikací pro zařízení se systémem Samsung KNOX](custom-policy-to-allow-and-block-samsung-knox-apps.md)

## <a name="supported-samsung-knox-standard-devices"></a>Podporovaná zařízení Samsung KNOX Standard

Během registrace MDM se aplikace Portál společnosti pokusí aktivovat Samsung KNOX jenom v případě, že je zařízení uvedené v [seznamu podporovaných zařízení KNOX](https://www.samsungknox.com/knox-supported-devices/knox-workspace). To pomáhá předejít chybám aktivace KNOX, které brání v registraci MDM. Zařízení, která nepodporují aktivaci Samsung KNOX, se zaregistrují jako standardní zařízení s Androidem. Některá čísla modelů zařízení Samsung mohou podporovat KNOX, některá nemusí. Než si zařízení Samsung koupíte a nasadíte, ověřte si u prodejce, zda je vaše zařízení kompatibilní se systémem KNOX.

Následující modely zařízení Samsung nepodporují KNOX a aplikace Portál společnosti pro Android je nezaregistruje jako nativní zařízení s Androidem:

| **Název zařízení** | **Číslo modelu zařízení** |
| --- | --- |
| Galaxy A3 | SM-A300G<br>SM-A310Y<br>SM-A320FL |
| Galaxy A5 | SM-A500G |
| Galaxy Alpha | SM-G850M |
| Galaxy Avant | SM-G386T |
| Galaxy C9/C9 Pro | SM-C900F |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime | SM-G530M |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110F |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M<br>SM-J320W8 |
| Galaxy J5 | SM-J500G |
| Galaxy J7 | SM-J710F |
| Galaxy J7 Prime | SM-J727T1 |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 5 | SM-N920G<br>SM-N920I<br>SM-N920W8 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy NotePRO 12.2&quot; | SM-P902 |
| Galaxy On5 | SM-G570MSM-G570Y |
| Galaxy On7 | SM-G600FY<br>SM-G610M<br>SM-G610Y |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Active | GT-I9295 |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W<br>SM-G900M |
| Galaxy S5 Neo | SM-G903M |
| Galaxy S6 Edge | 404SCSM-G925I<br>SM-G928G |
| Galaxy Tab A 7.0&quot; | SM-T280SM-T285 |
| Galaxy Tab A 9.7&quot; | SM-P555M |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116SM-T210SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |



### <a name="see-also"></a>Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
