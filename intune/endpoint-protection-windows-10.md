---
title: Přidání ochrany koncových bodů pro Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Na zařízeních s Windows 10 můžete v Intune použít nebo nakonfigurovat nastavení ochrany koncového bodu a povolit tak na místních zařízeních funkce Windows Defender, mezi něž patří Application Guard, brána firewall, filtr SmartScreen, šifrování a BitLocker, Exploit Guard, řízení aplikací, Security Center a zabezpečení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 069f71d75c0a9c7cec083a929f89a2b39bb4aac5
ms.sourcegitcommit: 4c06fa8e9932575e546ef2e880d96e96a0618673
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-intune"></a>Nastavení ochrany koncového bodu pro Windows 10 a novější v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profil ochrany koncového bodu vám umožňuje ovládat funkce zabezpečení na zařízeních s Windows 10, jako je BitLocker nebo Windows Defender.

V tomto článku se dozvíte, jak vytvářet profily ochrany koncového bodu. Pokud chcete nakonfigurovat antivirovou ochranu v programu Windows Defender, přečtěte si téma [Omezení pro zařízení s Windows 10](device-restrictions-windows-10.md#windows-defender-antivirus). 

> [!NOTE]
> Tato nastavení nejsou podporována v edicích Windows 10 Home a Professional.

## <a name="windows-defender-application-guard"></a>Ochrana Application Guard v programu Windows Defender

Když budete používat Microsoft Edge, Ochrana Application Guard v programu Windows Defender ochrání vaše prostředí před weby, které vaše organizace nedefinovala jako důvěryhodné. Když uživatelé navštíví weby, které nejsou uvedené v ohraničení vaší izolované sítě, otevřou se tyto weby ve virtuální relaci procházení v Hyper-V. Důvěryhodné weby se definují prostřednictvím ohraničení sítě, které se dá konfigurovat v Konfiguraci zařízení. 

Ochrana Application Guard je dostupná jenom pro zařízení s Windows 10 (64bitovou verzí). Tento profil nainstaluje součást Win32, pomocí které se aktivuje ochrana Application Guard.

- **Application Guard**: Otevírá neschválené weby v kontejneru procházení virtualizovaném pomocí technologie Hyper-V.
- **Chování schránky**: Zvolte, které akce kopírování a vkládání jsou povolené mezi místním počítačem a virtuálním prohlížečem ochrany Application Guard.
- **Externí obsah na firemních webech**: Zablokuje načítání obsahu z neschválených webů.
- **Tisk z virtuálního prohlížeče**: Povolí tisknout obsah z virtuálního prohlížeče do souborů PDF, XPS a na místní nebo síťové tiskárny.
- **Shromažďovat protokoly**: Shromáždí protokoly pro události, ke kterým dojde v relaci procházení ochrany Application Guard.
- **Zachovat uživatelem vygenerovaná data prohlížeče**: Umožní ukládání dat uživatelů (například hesel, oblíbených položek a souborů cookie), která se vytvoří během virtuální relace procházení ochrany Application Guard.
- **Akcelerace grafiky**: Umožňuje rychleji načítat weby náročné na grafiku, když se pracuje v relaci virtuálního procházení ochrany Application Guard. Když povolíte přístup k virtuálnímu grafickému procesoru, budou se weby načítat rychleji.
- **Stahovat soubory do systému souborů hostitele**: Umožňuje uživatelům stahovat soubory z virtualizovaného prohlížeče do hostitelského operačního systému.

## <a name="windows-defender-firewall"></a>Firewall v programu Windows Defender

### <a name="global-settings"></a>Globální nastavení

Tato nastavení platí pro všechny typy sítě.

- **Protokol FTP (File Transfer Protocol)**: Zablokuje stavový protokol FTP.
- **Doba nečinnosti přidružení zabezpečení před odstraněním**: Přidružení zabezpečení se odstraní, když se po dobu *n* sekund nezaznamenají v síti žádné přenosy.
- **Kódování předsdíleného klíče**: Kóduje předsdílené klíče pomocí UTF-8.
- **Výjimky protokolu IPsec**: Nakonfigurujte konkrétní přenosy, u kterých budou platit výjimky protokolu IPsec, například **Zjišťování kódů typu ICMP IPv6 sousedem**, **Protokol ICMP**, **Zjišťování kódů typu ICMP IPv6 směrovačem** a **Přenosy DHCP IPv4 i IPv6**.
- **Ověření seznamu odvolaných certifikátů**: Nastavte, jak se bude vynucovat ověření seznamu odvolaných certifikátů, například **Zakázat ověření seznamu CRL**, **Neúspěšné ověření seznamu CRL jenom u odvolaného certifikátu** a **Neúspěšné ověření seznamu CRL při každé zjištěné chybě**.
- **Oportunisticky přiřadit sadu ověřování na klíčovací modul**: Nastaví klíčovací moduly tak, aby v případě, že nepodporují všechny sady ověřování v dané sadě, se celá sada ověřování ignorovala.
- **Fronty paketů**: Zadejte, jak se povoluje škálování softwaru na straně příjmu u scénáře se šifrovaným příjmem a předáváním nešifrovaného textu pro bránu tunelového propojení IPsec. Toto nastavení zajišťuje zachování pořadí paketů.

### <a name="network-settings"></a>Nastavení sítě

Tato nastavení platí pro určité typy sítě, například pro typy **Doménová (firemní) síť**, **Privátní (zjistitelná) síť** a **Veřejná (nezjistitelná) síť**.

#### <a name="general-settings"></a>Obecná nastavení

- **Firewall v programu Windows Defender**: Toto nastavení povolte, pokud chcete blokovat přenosy v síti.
- **Neviditelný režim**: Zablokuje provoz firewallu v neviditelném režimu. Blokování neviditelného režimu vám umožňuje zablokovat také **výjimku zabezpečených paketů protokolu IPsec**.
- **Stíněné**: Pokud je toto nastavení i nastavení firewallu povolené, budou se všechny příchozí přenosy blokovat.
- **Jednosměrové odpovědi na vícesměrová vysílání**: Zablokuje jednosměrové odpovědi na vícesměrová vysílání. Jednosměrové odpovědi na zprávy vícesměrového nebo všesměrového vysílání obvykle nebudete chtít přijímat. Takové odpovědi můžou naznačovat útok DoS nebo pokus útočníka otestovat známý aktivní počítač.
- **Příchozí upozornění**: Zablokuje zobrazování upozornění uživatelům, když se blokuje naslouchání aplikace na portu.
- **Výchozí akce pro příchozí připojení**: Zablokuje výchozí akci, kterou firewall provádí u příchozích připojení.

#### <a name="rule-merging"></a>Sloučení pravidel

- **Pravidla brány firewall v programu Windows Defender pro autorizované aplikace z místního úložiště**: Bude používat a vynucovat autorizovaná pravidla brány firewall v místním úložišti.
- **Globální pravidla brány firewall v programu Windows Defender pro porty z místního úložiště**: Bude používat a vynucovat globální pravidla brány firewall portu v místním úložišti.
- **Pravidla brány firewall v programu Windows Defender z místního úložiště**: Bude používat a vynucovat globální pravidla brány firewall v místním úložišti.
- **Pravidla IPsec z místního úložiště**: Použije pravidla zabezpečení připojení z místního úložiště bez ohledu na verze schématu nebo pravidel zabezpečení připojení.

## <a name="windows-defender-smartscreen-settings"></a>Nastavení filtru SmartScreen v programu Windows Defender

- **Filtr SmartScreen pro aplikace a soubory**: Povolí filtr Windows SmartScreen pro provádění souborů a spuštěné aplikace.
- **Provádění neověřených souborů**: Zablokuje koncovému uživateli možnost provádět soubory, které nebyly ověřeny filtrem Windows SmartScreen.

## <a name="windows-encryption"></a>Šifrování Windows

### <a name="windows-settings"></a>Nastavení systému Windows

Tato dvě nastavení platí pro všechny verze Windows 10:

- **Šifrovat zařízení**: Pokud je toto nastavení povolené, zobrazí se uživatelům výzva, aby povolili šifrování zařízení. Kromě toho jsou požádání o potvrzení, že nebylo povoleno šifrování od jiného zprostředkovatele. Pokud je zapnuto šifrování Windows a současně je aktivní jiná metoda šifrování, mohlo by to narušit stabilitu zařízení.
- **Šifrovat paměťovou kartou**: Pokud je toto nastavení povolené, zašifrují se případné vyměnitelné paměťové karty použité v zařízení.


### <a name="bitlocker-base-settings"></a>Základní nastavení BitLockeru

Základní nastavení jsou univerzální nastavení BitLockeru pro všechny typy datových jednotek. Nastavení Zásad skupiny BitLockeru určují, které úkoly šifrování jednotek nebo možnosti konfigurace může koncový uživatel upravit na všech typech datových jednotek.

- **Upozornění pro další šifrování disku**: Zakáže upozornění pro další šifrování disku v počítačích koncových uživatelů.
- **Konfigurovat metody šifrování**: Povolení tohoto nastavení umožní konfiguraci algoritmů šifrování operačního systému, dat a vyměnitelných jednotek.
  - **Šifrování jednotek s operačním systémem**: Umožňuje vybrat metodu šifrování pro jednotky s operačním systémem. Doporučujeme použít algoritmus XTS-AES.
  - **Šifrování pevných datových jednotek**: Umožňuje vybrat metodu šifrování pro pevné (vestavěné) datové jednotky. Doporučujeme použít algoritmus XTS-AES.
  - **Šifrování vyměnitelných datových jednotek**: Umožňuje vybrat metodu šifrování pro vyměnitelné datové jednotky. Pokud se vyměnitelná jednotka používá se zařízeními s jiným systémem než Windows 10, doporučujeme použít algoritmus AES-CBC.

### <a name="bitlocker-os-drive-settings"></a>Nastavení BitLockeru pro jednotky s operačním systémem

Tato nastavení platí konkrétně pro datové jednotky s operačním systémem.

- **Další ověření při spuštění**: Umožňuje konfigurovat požadavky na ověření pro spuštění počítače, včetně využití čipu TPM (Trusted Platform Module).
  - **BitLocker s nekompatibilním čipem TPM**
  - **Kompatibilní spouštění s čipem TPM**: Umožňuje vybrat, jestli je čip TPM povolený, nepovolený nebo povinný.
  - **Kompatibilní spouštěcí PIN kód čipu TPM**: Umožňuje vybrat, jestli je použití spouštěcího PIN kódu s čipem TPM povolené, nepovolené nebo povinné.
  - **Kompatibilní spouštěcí klíč čipu TPM**: Umožňuje vybrat, jestli je použití spouštěcího klíče s čipem TPM povolené, nepovolené nebo povinné.
  - **Kompatibilní spouštěcí klíč a PIN kód čipu TPM**: Umožňuje vybrat, jestli je použití spouštěcího klíče a PIN kódu s čipem TPM povolené, nepovolené nebo povinné.
- **Minimální délka PIN kódu**: Po povolení tohoto nastavení můžete konfigurovat minimální délku spouštěcího PIN kódu u čipu TPM.
  - **Minimální počet znaků**: Zadejte počet znaků požadovaný pro spouštěcí PIN kód v rozmezí **4**-**20**.
- **Obnovení jednotky s operačním systémem**: Po povolení tohoto nastavení můžete řídit obnovení jednotek s operačním systémem chráněných BitLockerem v situacích, kdy nejsou k dispozici požadované informace pro spuštění.
  - **Agent obnovení dat založený na certifikátech**: Toto nastavení povolte, pokud chcete, aby bylo u jednotek s operačním systémem chráněných BitLockerem možné používat agenty obnovení dat.
  - **Vytváření hesla pro obnovení uživatelem**: Můžete vybrat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 48místné heslo pro obnovení nebo jestli je vytvoření povinné.
  - **Vytváření obnovovacího klíče uživatelem**: Můžete vybrat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 256bitové heslo pro obnovení nebo jestli je vytvoření povinné.
  - **Možnosti obnovení v průvodci nastavením BitLockeru**: Povolením tohoto nastavení zabráníte uživatelům zobrazovat a měnit po zapnutí BitLockeru možnosti obnovení.
  - **Ukládat informace pro obnovení BitLockeru do AD DS**: Umožňuje ukládání informací pro obnovení BitLockeru do služby Active Directory.
  - **Informace BitLockeru o obnově uložené v AD DS**: Můžete nakonfigurovat, které části informací BitLockeru o obnově se ukládají ve službě Active Directory. Vybírejte z těchto možností:
    - **Zálohovat hesla pro obnovení a sady klíčů**
    - **Zálohovat jenom hesla pro obnovení**
  - **Ukládat informace o obnově v AD DS před povolením BitLockeru**: Povolením tohoto nastavení zabráníte uživatelům, aby zapínali BitLocker, pokud není zařízení připojené k doméně a informace BitLockeru o obnově nejsou úspěšně uložené ve službě Active Directory.
- **Zpráva o obnově a adresa URL před spuštěním**: Po povolení tohoto nastavení můžete konfigurovat zprávu a adresu URL, které se zobrazí na obrazovce pro obnovení klíče před spuštěním.
  - **Zpráva o obnovení před spuštěním**: Můžete konfigurovat, jak se zpráva o obnovení před spuštěním zobrazí uživatelům. Vybírejte z těchto možností:
    - **Použít výchozí zprávu a adresu URL pro obnovení**
    - **Použít prázdnou zprávu a adresu URL pro obnovení**
    - **Použít vlastní zprávu o obnovení**
    - **Použít vlastní adresu URL pro obnovení**

### <a name="bitlocker-fixed-data-drive-settings"></a>Nastavení nástroje BitLocker pro pevné datové jednotky

- **Oprávnění k zápisu na pevné datové disky, které nechrání BitLocker**: Pokud je tato možnost povolená, je zápis na všechny pevné (vestavěné) datové jednotky možný jenom tehdy, když je na nich povolený BitLocker.
- **Obnovení pevného disku**: Pokud povolíte toto nastavení, můžete řídit obnovu pevných jednotek chráněných BitLockerem v případě, že nejsou k dispozici požadované informace pro spuštění.
  - **Agent obnovení dat**: Toto nastavení povolte, pokud chcete u pevných jednotek chráněných BitLockerem používat agenty obnovení dat.
  - **Vytváření hesla pro obnovení uživatelem**: Můžete nakonfigurovat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 48místné heslo pro obnovení nebo jestli je vytvoření povinné.  
  - **Vytváření obnovovacího klíče uživatelem**: Můžete nakonfigurovat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 256bitové heslo pro obnovení nebo jestli je vytvoření povinné.
  - **Možnosti obnovení v průvodci nastavením BitLockeru**: Povolením tohoto nastavení zabráníte uživatelům zobrazovat a měnit po zapnutí BitLockeru možnosti obnovení.
  - **Ukládat informace pro obnovení BitLockeru do AD DS**: Umožňuje ukládání informací pro obnovení BitLockeru do služby Active Directory.
  - **Informace BitLockeru o obnově v AD DS**: Můžete nakonfigurovat, které části informací BitLockeru o obnově se ukládají ve službě Active Directory. Vybírejte z těchto možností:
    - **Zálohovat hesla pro obnovení a sady klíčů**
    - **Zálohovat jenom hesla pro obnovení**
  - **Ukládat informace o obnově v AD DS před povolením BitLockeru**: Povolením tohoto nastavení zabráníte uživatelům, aby zapínali BitLocker, pokud není zařízení připojené k doméně a informace BitLockeru o obnově nejsou úspěšně uložené ve službě Active Directory.

### <a name="bitlocker-removable-data-drive-settings"></a>Nastavení nástroje BitLocker pro vyměnitelné datové jednotky

- **Oprávnění k zápisu na vyměnitelné datové disky, které nechrání BitLocker**: Můžete zadat, jestli se u vyměnitelných datových jednotek musí povinně používat šifrování BitLockeru.
  - **Oprávnění k zápisu na zařízení nakonfigurovaná jinou organizací**: Můžete zadat, jestli je možné zapisovat na zařízení patřící jiné organizaci.

## <a name="windows-defender-exploit-guard"></a>Ochrana Exploit Guard v programu Windows Defender

[Ochrana Exploit Guard v programu Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard) se používá ke správě a omezení možností útoku na aplikace, které používají vaši zaměstnanci.

### <a name="attack-surface-reduction"></a>Omezení možností útoku

- **Označit zcizování přihlašovacích údajů ze subsystému místního úřadu zabezpečení Windows**

Používejte [ochranu před akcemi a aplikacemi](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard), které obvykle využívá malware s cílem zneužití a nakažení počítačů.

#### <a name="rules-to-prevent-office-macro-threats"></a>Pravidla pro ochranu před hrozbami od maker Office

Aplikacím Office zablokujte provádění následujících akcí:

- **Injektáž aplikací Office do jiných procesů (bez výjimek)**
- **Aplikace a makra Office vytvářející spustitelný obsah**
- **Aplikace Office spouštějící podřízené procesy**
- **Importy Win32 z kódu maker v Office**

#### <a name="rules-to-prevent-script-threats"></a>Pravidla pro ochranu před hrozbami od skriptů

Z důvodu ochrany před hrozbami od skriptů zablokujte tyto akce:

- **Obfuskovaný kód js, vbs, ps nebo makra**
- **Skripty js a vbs spouštějící datovou část staženou z internetu (bez výjimek)**
- **Vytváření procesů z příkazů PSExec a WMI**
- **Nedůvěryhodné a nepodepsané procesy, které se spouštějí z USB**
- **Spustitelné soubory, které nesplňují kritéria četnosti, stáří nebo seznamu důvěryhodných souborů**

#### <a name="rules-to-prevent-email-threats"></a>Pravidla pro ochranu před e-mailovými hrozbami

Z důvodu ochrany před e-mailovými hrozbami zablokujte tuto akci:

- **Spuštění spustitelného obsahu (exe, dll, ps, js, vbs atd.) doručeného v e-mailu (webová pošta/poštovní klient) (bez výjimek)**

#### <a name="rules-to-protect-against-ransomware"></a>Pravidla, která chrání před ransomwarem
- **Rozšířená ochrana před ransomwarem**

> [!TIP]
> Více podrobností o těchto pravidlech najdete v článku [Zmenšení potenciální oblasti útoku pomocí ochrany Exploit Guard v programu Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard).

#### <a name="attack-surface-reduction-exceptions"></a>Výjimky pro omezení možností útoku

- **Soubory a složky, které se mají vyloučit z pravidel pro omezení možností útoku**: Umožňuje naimportovat nebo přidat seznam umístění, která se mají vyloučit z nakonfigurovaných pravidel.

### <a name="controlled-folder-access"></a>Řízený přístup ke složkám

Chraňte cenná data před škodlivými aplikacemi a hrozbami, jako je například ransomware.

- **Ochrana složek**: Umožňuje chránit soubory a složky před nežádoucími změnami, které provádějí škodlivé aplikace. Můžete naimportovat **seznam aplikací, které mají přístup do chráněných složek**, nebo je můžete přidat ručně. Můžete také nahrát **seznam dalších složek, které mají být chráněny**, nebo je můžete přidat ručně.

### <a name="network-filtering"></a>Filtrování sítě

Zablokujte odchozí připojení z libovolné aplikace na IP adresy a domény s nízkou reputací.

### <a name="exploit-protection"></a>Ochrana Exploit Protection

Můžete zablokovat **úpravy rozhraní ochrany Exploit Protection provedené uživatelem** tak, že nahrajete soubor XML umožňující konfiguraci omezení paměti, toku řízení a zásad. Nastavení v souboru XML se dají použít k ochraně aplikace před zneužitím.

Pokud chcete zapnout ochranu Exploit Protection, vytvořte soubor XML, který bude představovat vámi zvolená nastavení zmírňování pro systém a aplikace. Můžete to udělat dvěma způsoby:

 1. PowerShell: Použijte jednu nebo více powershellových rutin Get-ProcessMitigation, Set-ProcessMitigation a ConvertTo-ProcessMitigationPolicy. Tyto rutiny nakonfigurují nastavení zmírňování a exportují jejich reprezentaci v jazyce XML.

 2. Uživatelské rozhraní Centra zabezpečení v programu Windows Defender: V Centru zabezpečení v programu Windows Defender klikněte na ovládací prvek Aplikace a prohlížeč a posuňte zobrazenou obrazovku až dolů, kde najdete ochranu Exploit Protection. Nejprve nakonfigurujte nastavení zmírňování na kartách Nastavení systému a Nastavení programů. Pak ve spodní části obrazovky najděte odkaz Exportovat nastavení a exportujte reprezentaci daného nastavení v jazyce XML.

## <a name="windows-defender-application-control"></a>Řízení aplikací programu Windows Defender

Pomocí **zásad integrity kódu pro řízení aplikací** zvolte další aplikace, které se musí auditovat pomocí Řízení aplikací v programu Windows Defender nebo které tento nástroj může považovat za důvěryhodné, aby bylo možné povolit jejich spuštění. Součásti systému Windows a všechny aplikace z obchodu Windows Store se za důvěryhodné považují automaticky.

Aplikace spuštěné v režimu **Pouze audit** nejsou blokované. Režim **Pouze audit** zapisuje všechny události do protokolů místního klienta.

Po aktivaci se dá řízení aplikací deaktivovat jenom změnou režimu z **Vynutit** na **Pouze audit**. Změna režimu z **Vynutit** na **Nenakonfigurováno** způsobí, že řízení aplikací se na přiřazených zařízeních bude dále vynucovat.

## <a name="windows-defender-credential-guard"></a>Ochrana Credential Guard v programu Windows Defender
Ochrana Credential Guard v programu Windows Defender chrání před útoky zaměřenými na krádež přihlašovacích údajů. Izoluje tajné kódy, aby k nim měl přístup jenom privilegovaný software systému.

Nastavení ochrany **Credential Guard** zahrnuje:

- **Zakázáno**: Vzdáleně vypne ochranu Credential Guard, pokud byla dříve zapnutá pomocí možnosti **Povolit bez zámku UEFI**.
- **Enabled with UEFI lock** (Povoleno s uzamčením UEFI): Zajistí, že ochrana Credential Guard nepůjde vzdáleně vypnout pomocí klíčů registru nebo zásad skupiny.

    > [!NOTE]
    > Pokud toto nastavení použijete a chcete ochranu Credential Guard později zakázat, musíte nastavit zásady skupiny na **Zakázáno**. Musíte také fyzicky vymazat informace o konfiguraci UEFI z jednotlivých počítačů. Dokud je uložená konfigurace UEFI, je povolená i ochrana přihlašovacích údajů Credential Guard.

- **Enabled without UEFI lock** (Povoleno bez zámku UEFI): Umožňuje vzdáleně zakázat ochranu Credential Guard v zásadách skupiny. Na zařízeních s tímto nastavením musí běžet Windows 10 verze 1511 a novější.

Pokud povolíte ochranu Credential Guard, jsou povolené také tyto požadované funkce:

- **Zabezpečení na základě virtualizace** (VBS): Zapne se při příštím restartování počítače. Zabezpečení na základě virtualizace nabízí podporu služeb zabezpečení pomocí hypervisoru Windows.
- **Zabezpečené spouštění s přímým přístupem do paměti**: Zapne VBS se zabezpečeným spouštěním a ochranami přímého přístupu do paměti (DMA). Ochrany DMA vyžadují hardwarovou podporu a povolí se jenom na správně nakonfigurovaných zařízeních.

## <a name="windows-defender-security-center"></a>Centrum zabezpečení v programu Windows Defender

Aplikace Centrum zabezpečení v programu Windows Defender funguje jako samostatná aplikace nebo proces z každé jednotlivé funkce. Zobrazuje oznámení prostřednictvím Centra akcí. Funguje jako kolektor nebo jednotné místo, kde lze zjistit stav a nastavit část konfigurace jednotlivých funkcí. Další informace najdete v dokumentaci k programu [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).

#### <a name="windows-defender-security-center-app-and-notifications"></a>Aplikace a oznámení Centra zabezpečení v programu Windows Defender

Zablokujte přístup koncových uživatelů k různým oblastem aplikace Centrum zabezpečení v programu Windows Defender. Když se skryje nějaká část, zablokují se i související oznámení.

- **Ochrana před viry a hrozbami**
- **Výkon a stav zařízení**
- **Firewall a ochrana sítě**
- **Řízení aplikací a prohlížečů**
- **Možnosti pro rodinu**
- **Oznámení ze zobrazených oblastí aplikace**: Zvolte si, která oznámení se budou zobrazovat koncovým uživatelům. Mezi nezávažná oznámení patří souhrny aktivity Antivirové ochrany v programu Windows Defender, včetně oznámení o dokončení kontrol. Všechna další oznámení se považují za závažná.

#### <a name="it-contact-information"></a>Informace o kontaktu IT

Zadejte kontaktní informace oddělení IT, které se zobrazí v aplikaci Security Center v programu Windows Defender a v oznámeních aplikací. Můžete zvolit možnost **Zobrazovat v aplikacích a v oznámeních**, **Zobrazovat jen v aplikaci**, **Zobrazovat jen v oznámeních** nebo **Nezobrazovat**. Je nutné zadat **Název organizace IT** a aspoň jednu z následujících možností kontaktu:

- **Telefonní číslo nebo skypové jméno oddělení IT**
- **E-mailová adresa IT oddělení**
- **Adresa URL webu podpory IT**

## <a name="local-device-security-options"></a>Možnosti místního zabezpečení zařízení

Pomocí těchto možností můžete konfigurovat nastavení místního zabezpečení na zařízeních s Windows 10.

### <a name="accounts"></a>Účty

- **Přidat nové účty Microsoft**: Můžete uživatelům zabránit v přidávání nových účtů Microsoft na tento počítač.
- **Vzdálené přihlášení bez hesla**: Můžete povolit, aby se místní účty, které nejsou chráněné heslem, mohly přihlašovat z jiných umístění než z fyzického zařízení.

#### <a name="admin"></a>Správce

- **Účet místního správce**: Můžete určit, jestli je účet místního správce povolený nebo zakázaný.
- **Přejmenovat účet správce**: Můžete definovat jiný název účtu, který se má přidružit k identifikátoru zabezpečení (SID) pro účet správce.

#### <a name="guest"></a>Guest

- **Účet Guest**: Můžete určit, jestli je účet Guest povolený nebo zakázaný.
- **Přejmenovat účet hosta**: Můžete definovat jiný název účtu, který se má přidružit k identifikátoru zabezpečení (SID) pro účet Guest.

### <a name="devices"></a>Zařízení

- **Vyjmout zařízení z dokovací stanice bez přihlášení**: Můžete zabránit vyjmutí přenosného počítače z dokovací stanice bez nutnosti přihlášení.
- **Instalace ovladače tiskárny pro sdílené tiskárny**: Instalaci ovladačů tiskárny v rámci připojení ke sdílené tiskárně můžete omezit jenom na správce.
- **Omezit přístup k jednotce CD-ROM na místního aktivního uživatele**: Tímto nastavením povolíte přístup k médiím CD-ROM jenom interaktivně přihlášenému uživateli.
- **Formátovat a vysouvat vyměnitelná média**: Můžete definovat, kdo může formátovat a vysouvat vyměnitelná média NTFS:
  - **Není nakonfigurováno**
  - **Správci a členové skupiny Power Users**
  - **Správci a interaktivní uživatelé**

### <a name="interactive-logon"></a>Interaktivní přihlášení

- **Počet minut neaktivity na zamykací obrazovce, než se aktivuje šetřič obrazovky**: Můžete zadat maximální počet minut nečinnosti na přihlašovací obrazovce interaktivní relace plochy, než se spustí šetřič obrazovky.
- **K přihlášení vyžadovat CTRL + ALT + DEL**: Můžete vyžadovat, aby uživatel před přihlášením stiskl CTRL + ALT + DEL.
- **Chování při vyjmutí čipové karty**: Určuje, co se stane, když se ze čtečky čipových karet vyjme čipová karta přihlášeného uživatele.
Další podrobnosti nabízí [možnosti LocalPoliciesSecurity](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior).

#### <a name="display"></a>Zobrazit

- **Informace o uživateli na zamykací obrazovce**: Můžete konfigurovat informace o uživateli, které se zobrazí, když je relace uzamčená. Pokud tato možnost není nakonfigurovaná, zobrazí se zobrazované jméno uživatele, doména a uživatelské jméno.
  - **Jen zobrazované jméno uživatel**
  - **Nezobrazovat informace o uživateli**
  - **Nenakonfigurováno**: Zobrazované jméno uživatele, doména a uživatelské jméno
- **Skrýt naposledy přihlášeného uživatele**: Můžete zvolit, aby se nezobrazovalo uživatelské jméno posledního uživatele, který se na tomto zařízení přihlásil.
- **Skrýt uživatelské jméno při přihlašování**: Můžete zvolit, aby se po zadání přihlašovacích údajů a před zobrazením plochy zařízení nezobrazovalo uživatelské jméno uživatele, který se k tomuto zařízení přihlašuje.
- **Nadpis zprávy přihlášení**: Můžete nastavit nadpis zprávy pro uživatele pokoušející se přihlásit.
- **Text zprávy přihlášení**: Můžete nastavit text zprávy pro uživatele pokoušející se přihlásit.

### <a name="network-access-and-security"></a>Přístup k síti a zabezpečení

- **Anonymní přístup k pojmenovaným kanálům a sdíleným složkám**: Omezuje anonymní přístup k nastavením sdílené složky a pojmenovaného kanálu. Platí pro nastavení, ke kterým se dá přistupovat anonymně.
- **Anonymní výčty účtů SAM**: Umožňuje anonymním uživatelům vytvořit výčet účtů SAM. Windows umožňuje anonymním uživatelům vytvořit výčet názvů účtů domén a síťových sdílených složek.
- **Anonymní výčty účtů SAM a sdílených složek**: Může blokovat anonymní výčet účtů SAM a sdílených složek. Windows umožňuje anonymním uživatelům vytvořit výčet názvů účtů domén a síťových sdílených složek.
- **Ukládání hodnoty hash LAN Manageru při změně hesla**: Můžete vybrat, jestli se při další změně hesla uloží hodnota hash LAN Manageru (LM) pro nové heslo. Ve výchozím nastavení se neukládá.
- **Žádosti ověření PKU2U**: Můžete blokovat používání online identit žádostmi ověření PKU2U na toto zařízení.
- **Omezit vzdálená připojení RPC k SAM**: Můžete upravit výchozí řetězec jazyka SDDL (Security Descriptor Definition Language), abyste uživatelům a skupinám povolili nebo odepřeli vzdálená volání SAM.
- **Popisovač zabezpečení**

### <a name="recovery-console-and-shutdown"></a>Konzola pro zotavení a vypnutí

- **Při vypínání vymazat stránkovací soubor virtuální paměti**: Můžete vymazat stránkovací soubor virtuální paměti, když se zařízení vypne.
- **Vypnutí bez přihlášení**: Můžete blokovat možnost vypnutí počítače z přihlašovací obrazovky Windows. V takovém případě musí být uživatelé schopní se k počítači úspěšně přihlásit, než můžou provést vypnutí systému.

### <a name="user-account-control"></a>Řízení uživatelských účtů

- **Integrita UIA bez zabezpečeného umístění**: Můžete povolit spuštění aplikací z nezabezpečených umístění v systému souborů s úrovní integrity UIAccess.
- **Virtualizovat chyby zápisu souboru a registru do umístění podle uživatele**: Můžete určit, jestli se chyby zápisu aplikace přesměrují do definovaného umístění registru a systému souborů. Nebo jestli způsobí selhání aplikace.
- **Zvýšit oprávnění jen spustitelným souborům, které se podepsaly a ověřily**: Můžete vynutit ověření cesty certifikace infrastruktury veřejných klíčů pro daný spustitelný soubor, než se povolí jeho spuštění.

#### <a name="uia-elevation-prompt-behavior-settings"></a>Nastavení chování výzvy ke zvýšení úrovně oprávnění UIA

- **Výzva ke zvýšení úrovně oprávnění pro správce**: Můžete definovat chování výzvy ke zvýšení úrovně oprávnění pro správce v Režimu schválení správcem:
  - **Zvýšit oprávnění bez dotaz**
  - **Požádat o přihlašovací údajů na zabezpečené ploše**
  - **Požádat o souhlas na zabezpečené ploše**
  - **Vyzvat k zadání pověření**
  - **Požádat o souhlas**
  - **Nenakonfigurováno**: Požádat o souhlas pro binární soubory jiného systému než Windows
- **Výzva ke zvýšení úrovně oprávnění pro standardní uživatele**: Můžete definovat chování výzvy ke zvýšení úrovně oprávnění pro standardní uživatele:
  - **Automaticky zamítat žádosti o zvýšení oprávnění**
  - **Požádat o přihlašovací údajů na zabezpečené ploše**
  - **Nenakonfigurováno**: Výzva k zadání přihlašovacích údajů
- **Směrovat výzvy ke zvýšení úrovně oprávnění na interaktivní relaci plochy uživatele**: Můžete povolit, aby všechny žádosti o zvýšení oprávnění přešly na interaktivní relaci plochy uživatele místo zabezpečené plochy. Použijí se nastavení zásad chování výzev pro správce a standardní uživatele.
- **Výzva ke zvýšení úrovně oprávnění pro instalace aplikací**: Instalace aplikací vyžadující zvýšená oprávnění zobrazí výzvu k zadání přihlašovacích údajů správce.
- **Výzva ke zvýšení oprávnění UIA bez zabezpečené plochy**: Můžete aplikacím UIAccess povolit zobrazení výzvy ke zvýšení úrovně oprávnění bez použití zabezpečené plochy.

#### <a name="admin-approval-mode-settings"></a>Nastavení režimu schválení správcem

- **Režim schválení správcem pro předdefinovaný účet Administrator**: Definuje, jestli předdefinovaný účet správce používá režim schválení správcem, nebo všechny aplikace spouští s plnými oprávněními správce.
- **Spustit všechny správce v režimu schválení správcem**: Můžete definovat, jestli je povolený režim schválení správcem a všechna nastavení zásad řízení uživatelských účtů.

### <a name="microsoft-network-client"></a>Microsoft Network Client

- **Digitálně podepisovat komunikaci (pokud server souhlasí)**: Určuje, jestli se klient SMB pokusí vyjednat podepisování paketů. Když je tato možnost povolená (výchozí), klient sítě Microsoft požádá server o podepisování paketů SMB při nastavení relace. Pokud je na serveru podepisování paketů povolené, podepisování paketů se vyjedná. Pokud je tato zásada zakázaná, klient SMB podepisování paketů nikdy vyjednávat nebude.
- **Posílat nešifrované hesla serverům SMB třetích stran**: Když je tato možnost povolená, přesměrovač SMB (Server Message Block) může posílat hesla ve formátu prostého textu jiným serverům SMB než Microsoft, které nepodporují šifrování hesel při ověřování.

### <a name="microsoft-network-server"></a>Server sítě Microsoft

- **Digitálně podepisovat komunikaci (pokud klient souhlasí)**: Určuje, jestli server SMB vyjednává podepisování paketů SMB s klienty, kteří to požadují. Když je tato možnost povolená, server sítě Microsoft vyjedná podepisování paketů SMB podle požadavku klienta. To znamená, že pokud je v klientovi podepisování paketů povolené, podepisování paketů se vyjedná. Když je tato možnost zakázaná, klient SMB podepisování paketů nikdy vyjednávat nebude.
- **Digitálně podepisovat komunikaci (vždy)**: Určuje, jestli komponenta serveru SMB požaduje podepisování paketů. Když je tato možnost povolená, nebude server sítě Microsoft s klientem sítě Microsoft komunikovat, pokud tento klient nesouhlasí s podepisováním paketů SMB. Když je zakázaná (výchozí), podepisování paketů SMB mezi klientem a serverem se vyjedná.

## <a name="next-steps"></a>Další kroky

Pokud chcete tento profil přiřadit ke skupinám, přečtěte si článek [Přiřazení profilů zařízení](device-profile-assign.md).
