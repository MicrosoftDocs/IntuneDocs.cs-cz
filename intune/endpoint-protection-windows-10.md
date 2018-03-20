---
title: "Nastavení ochrany koncového bodu Microsoft Intune pro Windows 10"
titlesuffix: 
description: "Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení ochrany koncového bodu, jako je BitLocker, na zařízeních s Windows 10."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 02a32f678b40b2b40535984e17b41e0a864d8fdf
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="create-endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune"></a>Vytvořte nastavení ochrany koncového bodu pro Windows 10 a novější ve službě Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Profil ochrany koncového bodu vám umožňuje ovládat funkce zabezpečení na zařízeních s Windows 10, jako je BitLocker nebo Windows Defender.

V tomto článku se dozvíte, jak vytvářet profily ochrany koncového bodu.

> [!Note]
> Tato nastavení nejsou podporována v edicích Windows 10 Home a Professional.

## <a name="create-an-endpoint-protection-profile"></a>Vytvoření profilu ochrany koncového bodu

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
2. V okně **Konfigurace zařízení** v části **Spravovat** zvolte **Profily**.
3. V okně profilů zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **Název** a **Popis** profilu pro funkce zařízení.
5. V rozevíracím seznamu **Platforma** vyberte **Windows 10 a novější**.
6. V rozevíracím seznamu **Typ profilu** zvolte **Ochrana koncového bodu**.
7. Nakonfigurujte požadované nastavení. V podrobných informacích v tomto článku se dozvíte, jaká je funkce každého nastavení. Po dokončení zvolte **OK**.
8. Vraťte se zpět do okna **Vytvořit profil** a zvolte **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.

## <a name="windows-defender-application-guard"></a>Ochrana Application Guard v programu Windows Defender

Ochrana Application Guard je dostupná jenom pro zařízení s Windows 10 (64bitovou verzí). Tento profil nainstaluje součást Win32, pomocí které se aktivuje ochrana Application Guard.

- **Application Guard** – Otevírá neschválené weby v kontejneru procházení virtualizovaném pomocí technologie Hyper-V.
- **Chování schránky** – Zvolte, které akce kopírování a vkládání jsou povolené mezi místním počítačem a virtuálním prohlížečem ochrany Application Guard.
- **Externí obsah na firemních webech** – Zablokuje načítání obsahu z neschválených webů.
- **Tisk z virtuálního prohlížeče** – Povolí tisknout obsah z virtuálního prohlížeče do souborů PDF, XPS a na místní nebo síťové tiskárny.
- **Shromažďovat protokoly** – Shromáždí protokoly pro události, ke kterým dojde v relaci procházení ochrany Application Guard.
- **Zachovat uživatelem vygenerovaná data prohlížeče** – Povolí ukládání dat uživatelů (třeba hesla, oblíbené položky a soubory cookie), která se vytvoří během virtuální relace procházení ochrany Application Guard.
- **Akcelerace grafiky** – Umožňuje rychleji načítat weby náročné na grafiku, když se pracuje v relaci virtuálního procházení ochrany Application Guard, díky umožnění přístupu k virtuálnímu grafickému procesoru.


## <a name="windows-defender-firewall"></a>Firewall v programu Windows Defender

### <a name="global-settings"></a>Globální nastavení

Tato nastavení platí pro všechny typy sítě.

- **Protokol FTP (File Transfer Protocol)** – Zablokuje stavový protokol FTP.
- **Doba nečinnosti přidružení zabezpečení před odstraněním** – Přidružení zabezpečení se odstraní, když se po dobu *n* sekund nezaznamenají v síti žádné přenosy.
- **Kódování předsdíleného klíče** – Kóduje předsdílené klíče pomocí UTF-8.
- **Výjimky protokolu IPsec** – Nakonfigurujte konkrétní přenosy, u kterých budou platit výjimky protokolu IPsec, například **Zjišťování kódů typu ICMP IPv6 sousedem**, **Protokol ICMP**, **Zjišťování kódů typu ICMP IPv6 směrovačem** a **Přenosy DHCP IPv4 i IPv6**.
- **Ověření seznamu odvolaných certifikátů** – Nastavte, jak se bude vynucovat ověření seznamu odvolaných certifikátů, například **Zakázat ověření seznamu CRL**, **Neúspěšné ověření seznamu CRL jenom u odvolaného certifikátu** a **Neúspěšné ověření seznamu CRL při každé zjištěné chybě**.
- **Oportunisticky přiřadit sadu ověřování na klíčovací modul** – Nastaví klíčovací moduly tak, aby v případě, že nepodporují všechny sady ověřování v dané sadě, se celá sada ověřování ignorovala.
- **Fronty paketů** – Určete, jak se povoluje škálování softwaru na straně příjmu u scénáře se šifrovaným příjmem a předáváním nešifrovaného textu pro bránu tunelového propojení IPsec. Tím se zajistí zachování pořadí paketů.

### <a name="network-settings"></a>Nastavení sítě

Tato nastavení platí pro určité typy sítě, například pro typy **Doménová (firemní) síť**, **Privátní (zjistitelná) síť** a **Veřejná (nezjistitelná) síť**.

#### <a name="general-settings"></a>Obecná nastavení

- **Firewall v programu Windows Defender** – Toto nastavení povolte, pokud chcete blokovat přenosy v síti.
- **Neviditelný režim** – Zablokuje provoz firewallu v neviditelném režimu. Toto nastavení blokování vám umožňuje zablokovat také **výjimku zabezpečených paketů protokolu IPsec**.
- **Stíněné** – Pokud je toto nastavení i nastavení firewallu povolené, budou se všechny příchozí přenosy blokovat.
- **Jednosměrové odpovědi na vícesměrová vysílání** – Zablokuje jednosměrové odpovědi na vícesměrová vysílání. Jednosměrové odpovědi na zprávy vícesměrového nebo všesměrového vysílání obvykle nebudete chtít přijímat, protože takové odpovědi můžou naznačovat útok DoS nebo pokus útočníka otestovat známý aktivní počítač.
- **Příchozí upozornění** – Zablokuje zobrazování upozornění uživatelům, když se blokuje naslouchání aplikace na portu.
- **Výchozí akce pro příchozí připojení** – Zablokuje výchozí akci, kterou firewall provádí u příchozích připojení.

#### <a name="rule-merging"></a>Sloučení pravidel

- **Pravidla brány firewall v programu Windows Defender pro autorizované aplikace z místního úložiště** – Bude používat a vynucovat autorizovaná pravidla brány firewall v místním úložišti.
- **Globální pravidla brány firewall v programu Windows Defender pro porty z místního úložiště** – Bude používat a vynucovat globální pravidla brány firewall portu v místním úložišti.
- **Pravidla brány firewall v programu Windows Defender z místního úložiště** – Bude používat a vynucovat globální pravidla brány firewall v místním úložišti.
- **Pravidla IPsec z místního úložiště** – Použije pravidla zabezpečení připojení z místního úložiště bez ohledu na verze schématu nebo pravidel zabezpečení připojení.

## <a name="windows-defender-smartscreen-settings"></a>Nastavení filtru SmartScreen v programu Windows Defender

- **Filtr SmartScreen pro aplikace a soubory** – Povolí filtr Windows SmartScreen pro provádění souborů a spuštěné aplikace.
- **Provádění neověřených souborů** – Zablokuje koncovému uživateli možnost provádět soubory, které nebyly ověřeny filtrem Windows SmartScreen.

## <a name="windows-encryption"></a>Šifrování Windows

### <a name="windows-settings"></a>Nastavení systému Windows

Tato nastavení platí pro všechny verze Windows 10.

- **Šifrovat zařízení** – Pokud je toto nastavení povolené, zobrazí se uživatelům výzva, aby povolili šifrování zařízení. Kromě toho jsou požádání o potvrzení, že nebylo povoleno šifrování od jiného zprostředkovatele. Pokud je zapnuto šifrování Windows a současně je aktivní jiná metoda šifrování, mohlo by to narušit stabilitu zařízení.
- **Šifrovat paměťovou kartou** – Pokud je toto nastavení povolené, zašifrují se případné vyměnitelné paměťové karty použité v zařízení.


### <a name="bitlocker-base-settings"></a>Základní nastavení BitLockeru

Základní nastavení jsou univerzální nastavení BitLockeru pro všechny typy datových jednotek. Nastavení Zásad skupiny BitLockeru určují, které úkoly šifrování jednotek nebo možnosti konfigurace může koncový uživatel upravit na všech typech datových jednotek.

- **Upozornění pro další šifrování disku** – Zakáže upozornění pro další šifrování disku v počítačích koncových uživatelů.
- **Konfigurovat metody šifrování** – Povolení tohoto nastavení umožní konfiguraci algoritmů šifrování operačního systému, dat a vyměnitelných jednotek.
    - **Šifrování jednotek s operačním systémem** – Umožňuje vybrat metodu šifrování pro jednotky s operačním systémem. Doporučujeme použít algoritmus XTS-AES.
    - **Šifrování pevných datových jednotek** – Umožňuje vybrat metodu šifrování pro pevné (vestavěné) datové jednotky. Doporučujeme použít algoritmus XTS-AES.
    - **Šifrování vyměnitelných datových jednotek** – Umožňuje vybrat metodu šifrování pro vyměnitelné datové jednotky. Pokud se vyměnitelná jednotka používá se zařízeními s jiným systémem než Windows 10, doporučujeme použít algoritmus AES-CBC.

### <a name="bitlocker-os-drive-settings"></a>Nastavení BitLockeru pro jednotky s operačním systémem

Tato nastavení platí konkrétně pro datové jednotky s operačním systémem.

- **Další ověření při spuštění** – Umožňuje konfigurovat požadavky na ověření pro spuštění počítače, včetně využití čipu TPM (Trusted Platform Module).
    - **BitLocker s nekompatibilním čipem TPM**
    - **Kompatibilní spouštění s čipem TPM** – Umožňuje konfigurovat, jestli je, nebo není povolený čip TMP, nebo jestli je povinný.
    - **Kompatibilní spouštěcí PIN kód čipu TPM** – Umožňuje konfigurovat, jestli je, nebo není povoleno použití spouštěcího PIN kódu u čipu TPM, nebo jestli je povinné.
    - **Kompatibilní spouštěcí klíč TPM** – Umožňuje konfigurovat, jestli je, nebo není povoleno použití spouštěcího klíče u čipu TPM, nebo jestli je povinné.
    - **Kompatibilní spouštěcí klíč a PIN kód čipu TPM** – Umožňuje konfigurovat, jestli je, nebo není povoleno použití spouštěcího klíče a PIN kódu u čipu TPM, nebo jestli je povinné.
- **Minimální délka PIN kódu** – Po povolení tohoto nastavení můžete konfigurovat minimální délku spouštěcího PIN kódu u čipu TPM.
    - **Minimální počet znaků** – Zadejte počet znaků požadovaný pro spouštěcí PIN kód v rozmezí **4**-**20**.
- **Obnovení jednotky s operačním systémem** – Po povolení tohoto nastavení můžete řídit obnovení jednotek s operačním systémem chráněných BitLockerem v situacích, kdy nejsou k dispozici požadované informace pro spuštění.
    - **Agent obnovení dat založený na certifikátech** – Toto nastavení povolte, pokud chcete, aby bylo u jednotek s operačním systémem chráněných BitLockerem možné používat agenty obnovení dat.
    - **Vytváření hesla pro obnovení uživatelem** – Můžete nakonfigurovat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 48místné heslo pro obnovení nebo jestli je vytvoření povinné.
    - **Vytváření obnovovacího klíče uživatelem** – Můžete nakonfigurovat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 256bitové heslo pro obnovení nebo jestli je vytvoření povinné.
    - **Možnosti obnovení v průvodci nastavením BitLockeru** – Povolením tohoto nastavení zabráníte uživatelům zobrazovat a měnit po zapnutí BitLockeru možnosti obnovení.
    - **Ukládat informace pro obnovení BitLockeru do AD DS** – Umožňuje ukládání informací pro obnovení BitLockeru do služby Active Directory.
    - **Informace BitLockeru o obnově uložené v AD DS** – Můžete nakonfigurovat, které části informací BitLockeru o obnově se ukládají ve službě Active Directory. Vybírejte z těchto možností:
        - **Zálohovat hesla pro obnovení a sady klíčů**
        - **Zálohovat jenom hesla pro obnovení**
    - **Ukládat informace o obnově v AD DS před povolením BitLockeru** – Povolením tohoto nastavení zabráníte uživatelům, aby zapínali BitLocker, pokud není zařízení připojené k doméně a informace BitLockeru o obnově nejsou úspěšně uložené ve službě Active Directory.
- **Zpráva o obnově a adresa URL před spuštěním** – Po povolení tohoto nastavení můžete konfigurovat zprávu a adresu URL, které se zobrazí na obrazovce pro obnovení klíče před spuštěním.
    - **Zpráva o obnovení před spuštěním** – Můžete konfigurovat, jak se zpráva o obnovení před spuštěním zobrazí uživatelům. Vybírejte z těchto možností:
        - **Použít výchozí zprávu a adresu URL pro obnovení**
        - **Použít prázdnou zprávu a adresu URL pro obnovení**
        - **Použít vlastní zprávu o obnovení**
        - **Použít vlastní adresu URL pro obnovení**


### <a name="bitlocker-fixed-data-drive-settings"></a>Nastavení nástroje BitLocker pro pevné datové jednotky

- **Oprávnění k zápisu na pevné datové disky, které nechrání BitLocker** – Pokud je tato možnost povolená, je zápis na všechny pevné (vestavěné) datové jednotky možný jenom tehdy, když je na nich povolený BitLocker.
- **Obnovení pevného disku** – Pokud povolíte toto nastavení, můžete řídit obnovu pevných jednotek chráněných BitLockerem v případě, že nejsou k dispozici požadované informace pro spuštění.
    - **Agent obnovení dat** – Toto nastavení povolte, pokud chcete u pevných jednotek chráněných BitLockerem používat agenty obnovení dat.
    - **Vytváření hesla pro obnovení uživatelem** – Můžete nakonfigurovat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 48místné heslo pro obnovení nebo jestli je vytvoření povinné.  
    - **Vytváření obnovovacího klíče uživatelem** – Můžete nakonfigurovat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 256bitové heslo pro obnovení nebo jestli je vytvoření povinné.
    - **Možnosti obnovení v průvodci nastavením BitLockeru** – Povolením tohoto nastavení zabráníte uživatelům zobrazovat a měnit po zapnutí BitLockeru možnosti obnovení.
    - **Ukládat informace pro obnovení BitLockeru do AD DS** – Umožňuje ukládání informací pro obnovení BitLockeru do služby Active Directory.
    - **Informace BitLockeru o obnově v AD DS** – Můžete nakonfigurovat, které části informací BitLockeru o obnově se ukládají ve službě Active Directory. Vybírejte z těchto možností:
        - **Zálohovat hesla pro obnovení a sady klíčů**
        - **Zálohovat jenom hesla pro obnovení**
    - **Ukládat informace o obnově v AD DS před povolením BitLockeru** – Povolením tohoto nastavení zabráníte uživatelům, aby zapínali BitLocker, pokud není zařízení připojené k doméně a informace BitLockeru o obnově nejsou úspěšně uložené ve službě Active Directory.

### <a name="bitlocker-removable-data-drive-settings"></a>Nastavení nástroje BitLocker pro vyměnitelné datové jednotky

- **Oprávnění k zápisu na vyměnitelné datové disky, které nechrání BitLocker** – Můžete zadat, jestli se u vyměnitelných datových jednotek musí povinně používat šifrování BitLockeru.
  - **Oprávnění k zápisu na zařízení nakonfigurovaná jinou organizací** – Můžete zadat, jestli je možné zapisovat na zařízení patřící jiné organizaci.

## <a name="windows-defender-exploit-guard"></a>Ochrana Exploit Guard v programu Windows Defender

[Ochrana Exploit Guard v programu Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard) se používá ke správě a omezení možností útoku na aplikace, které používají vaši zaměstnanci.

### <a name="attack-surface-reduction"></a>Omezení možností útoku

Používejte [ochranu před akcemi a aplikacemi](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard), které obvykle využívá malware s cílem zneužití a nakažení počítačů.

#### <a name="rules-to-prevent-office-macro-threats"></a>Pravidla pro ochranu před hrozbami od maker Office

Aplikacím Office zablokujte provádění následujících akcí:

- **Injektáž aplikací Office do jiných procesů (bez výjimek)**
- **Aplikace a makra Office vytvářející spustitelný obsah**
- **Aplikace Office spouštějící podřízené procesy**
- **Importy Win32 z kódu maker v Office**

#### <a name="rules-to-prevent-script-threats"></a>Pravidla pro ochranu před hrozbami od skriptů

Kvůli ochraně před hrozbami od skriptů zablokujte tyto akce:

- **Obfuskovaný kód js, vbs, ps nebo makra**
- **Skripty js a vbs spouštějící datovou část staženou z internetu (bez výjimek)**

#### <a name="rules-to-prevent-email-threats"></a>Pravidla pro ochranu před e-mailovými hrozbami

Kvůli ochraně před e-mailovými hrozbami zablokujte tuto akci:

- **Spuštění spustitelného obsahu (exe, dll, ps, js, vbs atd.) doručeného v e-mailu (webová pošta/poštovní klient) (bez výjimek)**

#### <a name="attack-surface-reduction-exceptions"></a>Výjimky pro omezení možností útoku

- **Soubory a složky, které se mají vyloučit z pravidel pro omezení možností útoku** – Umožňuje naimportovat nebo přidat seznam umístění, která se mají vyloučit z nakonfigurovaných pravidel.

### <a name="controlled-folder-access"></a>Řízený přístup ke složkám

Chraňte cenná data před škodlivými aplikacemi a hrozbami, jako je například ransomware.

- **Ochrana složek** – Umožňuje chránit soubory a složky před nežádoucími změnami, které provádějí škodlivé aplikace. Můžete naimportovat **seznam aplikací, které mají přístup do chráněných složek**, nebo je můžete přidat ručně. Můžete také nahrát **seznam dalších složek, které mají být chráněny**, nebo je můžete přidat ručně.

### <a name="network-filtering"></a>Filtrování sítě

Zablokujte odchozí připojení z libovolné aplikace na IP adresy a domény s nízkou reputací.

### <a name="exploit-protection"></a>Ochrana Exploit Protection

Můžete zablokovat **úpravy rozhraní ochrany Exploit Protection provedené uživatelem** tak, že nahrajete soubor XML umožňující konfiguraci omezení paměti, toku řízení a zásad, pomocí kterých můžete ochránit aplikaci před zneužitím.

Pokud chcete zapnout ochranu Exploit Protection, vytvořte soubor XML, který bude představovat vámi zvolená nastavení zmírňování pro systém a aplikace. Můžete to udělat dvěma způsoby:

 1. PowerShell: Pomocí jedné nebo více powershellových rutin Get-ProcessMitigation, Set-ProcessMitigation a ConvertTo-ProcessMitigationPolicy nakonfigurujte nastavení zmírňování a exportujte jejich reprezentaci v jazyce XML.

 2. Uživatelské rozhraní Centra zabezpečení v programu Windows Defender: V Centru zabezpečení v programu Windows Defender klikněte na ovládací prvek Aplikace a prohlížeč a posuňte zobrazenou obrazovku až dolů, kde najdete ochranu Exploit Protection. Nejprve nakonfigurujte nastavení zmírňování na kartách Nastavení systému a Nastavení programů. Pak ve spodní části obrazovky najděte odkaz Exportovat nastavení a exportujte reprezentaci daného nastavení v jazyce XML.

## <a name="windows-defender-application-control"></a>Řízení aplikací programu Windows Defender

Pomocí **zásad integrity kódu pro řízení aplikací** zvolte další aplikace, které je potřeba auditovat pomocí Řízení aplikací v programu Windows Defender nebo které tento nástroj může považovat za důvěryhodné, aby bylo možné povolit jejich spuštění. Součásti systému Windows a všechny aplikace z obchodu Windows Store se za důvěryhodné považují automaticky.

Aplikace spuštěné v režimu **Pouze audit** nebudou blokované. Režim **Pouze audit** zapisuje všechny události do protokolů místního klienta.

Po aktivaci se dá řízení aplikací deaktivovat jenom změnou režimu z **Vynutit** na **Pouze audit**. Změna režimu z **Vynutit** na **Nenakonfigurováno** způsobí, že řízení aplikací se na přiřazených zařízeních bude dále vynucovat.

## <a name="windows-defender-security-center"></a>Centrum zabezpečení v programu Windows Defender

Aplikace Centrum zabezpečení v programu Windows Defender funguje jako samostatná aplikace nebo proces z každé jednotlivé funkce a zobrazuje oznámení prostřednictvím Centra akcí. Funguje jako kolektor nebo jednotné místo, kde lze zjistit stav a nastavit část konfigurace jednotlivých funkcí. Další informace najdete v dokumentaci k programu [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).

#### <a name="windows-defender-security-center-app-and-notifications"></a>Aplikace a oznámení Centra zabezpečení v programu Windows Defender

Zablokujte přístup koncových uživatelů k různým oblastem aplikace Centrum zabezpečení v programu Windows Defender. Když se skryje nějaká část, zablokují se i související oznámení.

- **Ochrana před viry a hrozbami**
- **Výkon a stav zařízení**
- **Firewall a ochrana sítě**
- **Řízení aplikací a prohlížečů**
- **Možnosti pro rodinu**
- **Oznámení ze zobrazených oblastí aplikace** – Zvolte si, která oznámení se budou zobrazovat koncovým uživatelům. Mezi nezávažná oznámení patří souhrny aktivity Antivirové ochrany v programu Windows Defender, včetně oznámení o dokončení kontrol. Všechna další oznámení se považují za závažná.

#### <a name="it-contact-information"></a>Informace o kontaktu IT

Zadejte kontaktní informace oddělení IT, které se zobrazí v aplikaci Centra zabezpečení v programu Windows Defender a v oznámeních aplikací. Můžete zvolit možnost **Zobrazovat v aplikacích a v oznámeních**, **Zobrazovat jen v aplikaci**, **Zobrazovat jen v oznámeních** nebo **Nezobrazovat**. Je nutné definovat **Název organizace IT** a aspoň jednu z následujících možností kontaktu:

- **Telefonní číslo nebo skypové jméno oddělení IT**
- **E-mailová adresa IT oddělení**
- **Adresa URL webu podpory IT**

## <a name="next-steps"></a>Další kroky

Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).
