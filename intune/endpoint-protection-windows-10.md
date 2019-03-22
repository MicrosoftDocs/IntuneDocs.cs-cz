---
title: Nastavení ochrany pro zařízení s Windows 10 v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Na zařízeních s Windows 10 můžete v Intune použít nebo nakonfigurovat nastavení ochrany koncového bodu a povolit tak na místních zařízeních funkce Windows Defender, mezi něž patří Application Guard, brána firewall, filtr SmartScreen, šifrování a BitLocker, Exploit Guard, řízení aplikací, Security Center a zabezpečení.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4c2df888e146a7f240530e5cbc6628dbce34cb61
ms.sourcegitcommit: b0b1030017e741d92c508130447a8242d9ad7a51
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2019
ms.locfileid: "58342993"
---
# <a name="windows-10-and-later-settings-to-protect-devices-using-intune"></a>Nastavení Windows 10 (a novější), aby ochrana zařízení pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune zahrnuje mnoho nastavení, která pomáhá chránit vaše zařízení. Tento článek popisuje všechna nastavení, můžete povolit a nakonfigurovat ve Windows 10 a novější zařízení. Tato nastavení se vytvoří v profil ochrany koncových bodů konfigurace v Intune pro řízení zabezpečení, včetně BitLocker nebo Windows Defender.

Ke konfiguraci antivirové ochrany v programu Windows Defender, najdete v článku [omezení pro zařízení Windows 10](device-restrictions-windows-10.md#windows-defender-antivirus).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení ochrany koncových bodů](endpoint-protection-configure.md).

## <a name="windows-defender-application-guard"></a>Ochrana Application Guard v programu Windows Defender

Podporováno v následujících edicích Windows 10:

- Enterprise
- Professional

Když budete používat Microsoft Edge, Ochrana Application Guard v programu Windows Defender ochrání vaše prostředí před weby, kterým vaše organizace nedůvěřuje. Když uživatelé navštíví weby, které nejsou uvedené v ohraničení vaší izolované sítě, weby otevřete v relaci virtuálního procházení Hyper-V. Důvěryhodné servery jsou definovány ohraničení sítě, které jsou nakonfigurované v konfiguraci zařízení.

Ochrana Application Guard je dostupná jenom pro zařízení s Windows 10 (64bitovou verzí). Tento profil nainstaluje součást Win32, pomocí které se aktivuje ochrana Application Guard.

- **Ochrana Application Guard**: **Povoleno pro Edge** zapnout tuto funkci, která se otevře nedůvěryhodné weby v technologií Hyper-V kontejneru procházení virtualizovaném pomocí. **Není nakonfigurováno** (výchozí) znamená, že žádné lokality (důvěryhodné a nedůvěryhodné) otevře v zařízení.
- **Chování schránky**: Zvolte, které akce kopírování a vkládání jsou povolené mezi místním Počítačem a virtuálním prohlížeči ochrany Application Guard.
- **Externí obsah na firemních webech**: **Blok** obsahu z neschválených webů načítání. **Nenakonfigurováno** (výchozí) znamená, že se na zařízení mohou otevřít nefiremní weby.
- **Tisk z virtuálního prohlížeče**: Zvolte **povolit** tak PDF, XPS, místní a síťové tiskárny můžete tisknout obsah z virtuálního prohlížeče. **Nenakonfigurováno** (výchozí) zakáže všechny tiskové funkce.
- **Shromažďování protokolů**: **Povolit** shromažďovat protokoly pro události, ke kterým došlo v relaci procházení ochrany Application Guard. **Nenakonfigurováno** (výchozí) žádné protokoly v relaci procházení neshromažďuje.
- **Zachovat uživatele vygenerovaná data prohlížeče**: **Povolit** uloží uživatelská data (jako jsou hesla, Oblíbené položky a soubory cookie), který je vytvořen při relaci virtuálního procházení ochrany Application Guard. **Nenakonfigurováno** (výchozí) zahodí všechny soubory a data stažená uživatelem při restartu zařízení nebo odhlášení uživatele.
- **Akcelerace grafiky**: Zvolte **povolit** načíst weby náročné na grafiku a video rychlejší získáním přístupu k virtuálnímu grafickému procesoru. **Nenakonfigurováno** (výchozí) použije místo virtuálního grafického procesoru CPU zařízení.
- **Stahovat soubory do hostitelského souborového systému**: **Povolit** tak uživatelům stahovat soubory z virtualizovaného prohlížeče do operačního systému hostitele. **Nenakonfigurováno** (výchozí) nestáhne soubory do hostitelského operačního systému, ale stáhne je do místního úložiště zařízení.

## <a name="windows-defender-firewall"></a>Firewall v programu Windows Defender

Podporováno v následujících edicích Windows 10:
- Domů
- Professional
- Firemní
- Enterprise
- Vzdělávání
- Mobilní zařízení
- Mobile Enterprise

### <a name="global-settings"></a>Globální nastavení

Tato nastavení platí pro všechny typy sítě.

- **File Transfer Protocol**: **Blok** zakázat stavový protokol FTP. **Nenakonfigurováno** (výchozí) umožní firewallu filtrování stavového protokolu FTP, které povolí sekundární připojení.
- **Doba nečinnosti přidružení zabezpečení před odstraněním**: Přidružení zabezpečení se odstraní po nezaznamenají žádné síťové přenosy pro *n* sekund. Zadejte čas nečinnosti v sekundách.
- **Kódování předsdíleného klíče**: Zvolte **povolit** používat předsdílené klíče kódování pomocí kódování UTF-8. **Nenakonfigurováno** (výchozí) použije hodnotu místního úložiště.
- **Výjimky protokolu IPsec**: Nakonfigurujte konkrétní přenosy, aby se vyjímá z protokolu IPsec, včetně:
  - **Zjišťování kódů typu ICMP IPv6 sousedem**
  - **Protokol ICMP**
  - **Zjišťování kódů typu ICMP IPv6 směrovačem**
  - **Přenosy DHCP IPv4 i IPv6**
- **Ověření seznamu odvolaných certifikátů**: Zvolte, jak zařízení ověří seznam odvolaných certifikátů. Mezi možnosti patří **zakázat ověření seznamu CRL**, **neúspěšné ověření seznamu CRL jenom u odvolaného certifikátu**, a **neúspěšné ověření seznamu CRL při každé zjištěné chybě**.
- **Oportunisticky přiřadit sadu ověřování na klíčovací modul**: **Povolit** tak klíčovací moduly tak musí ignorovat pouze sady ověřování, které nepodporují. **Nenakonfigurováno** nastaví klíčovací moduly tak, aby v případě, že nepodporují všechny sady ověřování v dané sadě, se celá sada ověřování ignorovala.
- **Fronty paketů**: Zadejte, jak je software škálování na straně příjmu s povolenou šifrovaným příjmem a předáváním nešifrovaného textu pro scénář bránu tunelového propojení IPsec. Toto nastavení potvrdí, že zachování pořadí paketů.

### <a name="network-settings"></a>Nastavení sítě

Tato nastavení platí pro určité typy sítě, například pro typy **Doménová (firemní) síť**, **Privátní (zjistitelná) síť** a **Veřejná (nezjistitelná) síť**.

#### <a name="general-settings"></a>Obecná nastavení  
- **Firewallu v programu Windows Defender**: Zvolte **povolit** zapnutí brány firewall a pokročilým zabezpečením. **Nenakonfigurováno** (výchozí) povolí veškerý provoz bez ohledu na ostatní nastavení zásad.
- **Neviditelný režim**: **Blok** provoz firewallu v neviditelném režimu. Blokování neviditelného režimu vám umožňuje zablokovat také **výjimku zabezpečených paketů protokolu IPsec**. **Nenakonfigurováno** (výchozí) provozuje firewall v neviditelném režimu, který pomáhá předejít odpovědím na zjišťovací požadavky.
- **Stíněné**: **Blok** vypne tuto funkci. **Nenakonfigurováno** (výchozí) toto nastavení povolí. Když je toto nastavení a Firewall v programu Windows Defender zapnutý, veškerý provoz bez ohledu na ostatní nastavení zásad se blokuje.
- **Jednosměrové odpovědi na vícesměrová vysílání**: Pokud je nastavena na **bloku**, zakáže jednosměrové odpovědi na vícesměrová vysílání. Jednosměrové odpovědi na zprávy vícesměrového nebo všesměrového vysílání obvykle nebudete chtít přijímat. Tyto odpovědi můžou naznačovat útok DoS (DOS), nebo útočník při pokusu o sběru dat známý aktivní počítač. **Nenakonfigurováno** (výchozí) toto nastavení povolí.
- **Příchozí upozornění**: Pokud je nastavena na **bloku**, zobrazovat oznámení uživatelům při aplikaci se blokuje naslouchání na portu. **Nenakonfigurováno** (výchozí) toto nastavení povolí, a když se blokuje naslouchání aplikace na portu, může uživatelům upozornění zobrazit.
- **Výchozí akce pro příchozí připojení**: Pokud je nastavena na **bloku**, výchozí akce pro brány firewall není spuštěna u příchozích připojení. **Nenakonfigurováno** (výchozí) výchozí akci brány firewall u příchozích připojení provede.

#### <a name="rule-merging"></a>Sloučení pravidel

- **Oprávnění aplikace pravidla firewallu v programu Windows Defender z místního úložiště**: Zvolte **povolit** použít pravidla brány firewall v místním úložišti, tak, že budete používat a vynucovat. **Nenakonfigurováno** (výchozí) bude pravidla brány firewall autorizované aplikace v místním úložišti ignorovat a nebude je vynucovat.
- **Pravidla pro globální porty firewallu v programu Windows Defender z místního úložiště**: Zvolte **povolit** k portu globální pravidla brány firewall v místním úložišti bude používat a vynucovat. **Nenakonfigurováno** (výchozí) bude globální pravidla brány firewall portu v místním úložišti ignorovat a nebude je vynucovat.
- **Pravidla firewallu v programu Windows Defender z místního úložiště**: Zvolte **povolit** do pravidla brány firewall v místním úložišti bude používat a vynucovat. **Nenakonfigurováno** (výchozí) bude pravidla brány firewall v místním úložišti ignorovat a nebude je vynucovat.
- **Pravidla IPsec z místního úložiště**: Zvolte **povolit** použít pravidla zabezpečení připojení z místního úložiště bez ohledu na verze schématu nebo připojení pravidel zabezpečení. **Nenakonfigurováno** (výchozí) pravidla zabezpečení připojení z místního úložiště bude bez ohledu na verze schématu nebo pravidel zabezpečení připojení ignorovat a nebude je vynucovat.

## <a name="windows-defender-smartscreen-settings"></a>Nastavení filtru SmartScreen v programu Windows Defender

Podporováno v následujících edicích Windows 10 s nainstalovaným prohlížečem Microsoft Edge:
- Domů
- Professional
- Firemní
- Enterprise
- Vzdělávání
- Mobilní zařízení
- Mobile Enterprise

**Nastavení**:

- **Filtr SmartScreen pro aplikace a soubory**: **Povolit** filtr Windows SmartScreen pro provádění souborů a spouštění aplikací. SmartScreen je cloudová antiphisingová a antimalwarová vrstva ochrany. **Nenakonfigurováno** (výchozí) filtr SmartScreen zakáže.
- **Neověřených souborů provádění**: **Blok** koncovým uživatelům ve spouštění souborů, které nebyly ověřeny filtrem Windows SmartScreen. **Nenakonfigurováno** (výchozí) tuto funkci vypne a umožní uživatelům spouštět i neověřené soubory.

## <a name="windows-encryption"></a>Šifrování Windows

### <a name="windows-settings"></a>Nastavení systému Windows

Podporováno v následujících edicích Windows 10:

- Professional
- Firemní
- Enterprise
- Vzdělávání
- Mobilní zařízení
- Mobile Enterprise

**Nastavení**:

- **Šifrovat zařízení**: **Vyžadovat** vyzve uživatele, aby povolili šifrování zařízení. V závislosti na edici Windows a konfiguraci systému se může od uživatelů vyžadovat:  
  - Aby potvrdili, že není povolené šifrování od jiného zprostředkovatele.
  - Aby vypnuli nástroj BitLocker Drive Encryption a potom ho znovu zapnuli.
    
    Pokud je zapnuto šifrování Windows a současně je aktivní jiná metoda šifrování, mohlo by to narušit stabilitu zařízení. 
- **Šifrovat paměťovou kartou (jenom mobilní verze)**: **Vyžadovat** pro šifrování případné vyměnitelné paměťové karty použité v zařízení. **Nenakonfigurováno** (výchozí) nebude požadovat šifrování paměťových karet a nebude k tomu uživatele vyzývat. Toto nastavení platí jenom pro zařízení s Windows 10 Mobile.

### <a name="bitlocker-base-settings"></a>Základní nastavení BitLockeru

Podporováno v následujících edicích Windows 10:

- Enterprise
- Vzdělávání
- Mobilní zařízení
- Mobile Enterprise
- Professional

Základní nastavení jsou univerzální nastavení BitLockeru pro všechny typy datových jednotek. Tato nastavení určují, které úkoly šifrování jednotek nebo možnosti konfigurace může koncový uživatel upravit na všech typech datových jednotek.

- **Upozornění pro další šifrování disku**: Vyberte **bloku** zakázat tato výzva s upozorněním, pokud jiná služba šifrování disku je v zařízení. **Nenakonfigurováno** (výchozí) zobrazení upozornění povolí.
    - **Standardní uživatelé k povolení šifrování během připojení ke službě Azure AD povolit**: Pokud zvolíte **povolit**, standardní uživatelé/bez oprávnění správce můžete povolit šifrování nástrojem BitLocker, pokud uživatel je přihlášený. Toto nastavení platí jenom pro Azure Active Directory zařízení připojená k (přídavné jméno Azure). **Není nakonfigurováno** pouze správcům umožňuje povolit nástroj BitLocker šifrování na zařízení.
      
      Toto nastavení platí jenom pro Azure Active Directory zařízení připojená k (přídavné jméno Azure). Také vyžaduje, aby **upozornění pro další šifrování disku** nastavení **bloku**.
- **Konfigurovat metody šifrování**: **Povolit** toto nastavení umožní konfiguraci algoritmů šifrování operačního systému, dat a vyměnitelných jednotek. **Nenakonfigurováno** (výchozí) znamená, že BitLocker používá jako výchozí metodu šifrování XTS-AES 128 bit nebo používá metodu šifrování určenou skriptem instalace.
  - **Šifrování pro operační systém jednotek**: Zvolte metodu šifrování pro jednotky s operačním systémem. Doporučujeme použít algoritmus XTS-AES.
  - **Šifrování pevných datových jednotek**: Zvolte metodu šifrování pro pevné (vestavěné) datové jednotky. Doporučujeme použít algoritmus XTS-AES.
  - **Šifrování pro vyměnitelné datové jednotky**: Vyberte metodu šifrování pro vyměnitelné datové jednotky. Pokud se vyměnitelná jednotka používá se zařízeními s jiným systémem než Windows 10, doporučujeme použít algoritmus AES-CBC.

### <a name="bitlocker-os-drive-settings"></a>Nastavení BitLockeru pro jednotky s operačním systémem
Podporováno v následujících edicích Windows 10:

- Enterprise
- Vzdělávání
- Mobilní zařízení
- Mobile Enterprise
- Professional

Tato nastavení platí konkrétně pro datové jednotky s operačním systémem.

- **Další ověření při spuštění**: Vyberte **vyžadují** konfigurovat požadavky na ověřování pro spuštění počítače, včetně využití čipu TPM z Trusted Platform Module (TPM). **Nenakonfigurováno** (výchozí) na zařízeních s TPM konfiguruje pouze základní možnosti.
  - **Nástroj BitLocker pomocí čipu TPM nekompatibilní**: **Blok** (zakázat) pomocí nástroje BitLocker, pokud zařízení nemá kompatibilního čipu TPM. **Nenakonfigurováno** (výchozí) umožní uživatelům používat BitLocker bez kompatibilního čipu TPM. BitLocker může vyžadovat heslo nebo spouštěcí klíč.
  - **Kompatibilní spouštění s čipem TPM**: Zvolte povolit, nechcete povolit nebo vyžadují čipu TPM.
  - **Kompatibilní spouštěcí PIN kód TPM**: Zvolte povolit, nechcete povolit nebo vyžadují použití spouštěcího PIN kódu u čipu TPM. Povolení spouštěcího PIN kódu vyžaduje interakci koncového uživatele. 
  - **Kompatibilní spouštěcí klíč TPM**: Zvolte povolit, aby nebo vyžadují použití spouštěcího klíče u čipu TPM. Povolení spouštěcího klíče vyžaduje interakci koncového uživatele. 
  - **Kompatibilní spouštěcí klíč TPM a PIN kód**: Zvolte povolit, aby nebo vyžadují použití spouštěcího klíče a PIN kódu u čipu TPM. Povolení spouštěcího klíče a PIN kódu vyžaduje interakci koncového uživatele.
- **Minimální délka kódu PIN**: **Povolit** tohoto nastavení můžete konfigurovat minimální délku pro spouštěcí PIN kód TPM. **Nenakonfigurováno** (výchozí) umožní uživatelům nakonfigurovat spouštěcí PIN kód s libovolnou délkou v rozmezí od 6 do 20 číslic.
  - **Minimální počet znaků**: Zadejte počet znaků vyžadovaný pro spouštěcí PIN kód z **4**-**20**.
- **Obnovení jednotky s operačním systémem**: **Povolit** tohoto nastavení můžete řídit operačním systémem chráněných Bitlockerem jednotek obnovení, když není k dispozici požadované informace. **Nenakonfigurováno** (výchozí) podporuje výchozí možnosti obnovení pomocí nástroje BitLocker. Ve výchozím nastavení je povolen DRA, možnosti obnovení je možné zvolit uživatelem, včetně heslo pro obnovení a obnovovací klíč, a informace pro obnovení není zálohovány do služby AD DS.
  - **Agent obnovení dat na základě certifikátů**: Pokud je nastavena na **bloku**, agent obnovení dat nelze použít s jednotkami operačního systému chráněné nástrojem BitLocker. **Nenakonfigurováno** (výchozí) použití agentů obnovení dat u jednotek s operačním systémem chráněných BitLockerem povolí.
  - **Vytváření hesla pro obnovení uživatelem**: Zvolte, pokud uživatelé jsou povolené, vyžaduje nebo nesmí generovat 48místné obnovení hesla.
  - **Vytváření obnovovacího klíče uživatelem**: Zvolte, pokud uživatelé jsou povolené, vyžaduje nebo nesmí generovat 256bitový obnovovací klíč.
  - **Možnosti obnovení v Průvodci nastavením Bitlockeru**: Nastavte na **bloku** tak uživatelů nelze zobrazit a změnit možnosti obnovení. **Nenakonfigurováno** (výchozí) umožní uživatelům po spuštění BitLockeru zobrazovat a měnit možnosti obnovení.
  - **Ukládání informací pro obnovení Bitlockeru do služby AD DS**: Zvolte **povolit** k ukládání informací pro obnovení Bitlockeru do Azure Active Directory (AAD). **Nenakonfigurováno** (výchozí) ukládat informace pro obnovení BitLockeru do služby AAD nebude.
  - **Uložit do služby AD DS informace Bitlockeru o obnově**: Konfigurace, které části informací Bitlockeru o obnově se ukládají ve službě Azure AD. Vybírejte z těchto možností:
    - **Zálohovat hesla pro obnovení a sady klíčů**
    - **Zálohovat jenom hesla pro obnovení**
  - **Store informace o obnově v AD DS před povolením Bitlockeru**: **Vyžadovat** tohoto nastavení zabráníte uživatelům, aby zapínali BitLocker, pokud informace Bitlockeru o obnově se úspěšně uložené v Azure Active Directory (AD). **Není nakonfigurováno** (výchozí) umožňuje uživatelům k zapnutí nástroje BitLocker, i v případě, že informace o obnovení nejsou úspěšně uloženy ve službě Azure AD.
- **Zpráva o obnově a adresa URL před spuštěním**: **Povolit** tohoto nastavení můžete konfigurovat zprávu a adresu URL, která se zobrazí na obrazovce pro obnovení klíče před spuštěním. **Nenakonfigurováno** (výchozí) tuto funkci zakáže.
  - **Zpráva o obnovení před spuštěním**: Nakonfigurujte, jak zprávu o obnovení před spuštěním zobrazí uživatelům. Vybírejte z těchto možností:
    - **Použít výchozí zprávu a adresu URL pro obnovení**
    - **Použít prázdnou zprávu a adresu URL pro obnovení**
    - **Použít vlastní zprávu o obnovení**
    - **Použít vlastní adresu URL pro obnovení**

### <a name="bitlocker-fixed-data-drive-settings"></a>Nastavení nástroje BitLocker pro pevné datové jednotky

Podporováno v následujících edicích Windows 10:

- Enterprise
- Vzdělávání
- Mobilní zařízení
- Mobile Enterprise
- Professional

**Nastavení**:

- **Přístup pro zápis na pevné datové jednotky, které nechrání BitLocker**: Nastavte na **bloku** dát přístup jen pro čtení datové jednotky, které nejsou chráněné Bitlockerem. Když **Nenakonfigurováno** (výchozí), existuje pro čtení a zápis do datových jednotek, které nejsou chráněné Bitlockerem.
- **Obnovení pevného disku**: **Povolit** toto nastavení, můžete řídit způsob, jakým obnovení pevných jednotek chráněných Bitlockerem, když není k dispozici požadované informace. **Nenakonfigurováno** (výchozí) tuto funkci zakáže.
  - **Agent obnovení dat**: **Blok** použití agenta obnovení dat pomocí chráněných Bitlockerem pevných jednotek editoru zásad. **Nenakonfigurováno** (výchozí) použití agentů obnovení dat u pevných jednotek chráněných BitLockerem povolí.
  - **Vytváření hesla pro obnovení uživatelem**: Nakonfigurujte, jestli uživatelé jsou povolené, vyžaduje nebo nesmí generovat 48místné obnovení hesla.  
  - **Vytváření obnovovacího klíče uživatelem**: Nakonfigurujte, jestli uživatelé jsou povolené, vyžaduje nebo nesmí generovat 256bitový obnovovací klíč.
  - **Možnosti obnovení v Průvodci nastavením Bitlockeru**: Nastavte na **bloku** tak uživatelů nelze zobrazit a změnit možnosti obnovení. **Nenakonfigurováno** (výchozí) umožní uživatelům po spuštění BitLockeru zobrazovat a měnit možnosti obnovení.
  - **Ukládání informací pro obnovení Bitlockeru do služby Azure Active Directory**: Zvolte **povolit** k ukládání informací pro obnovení Bitlockeru ve službě Azure Active Directory (Azure AD). Když **Nenakonfigurováno** (výchozí), informace o obnovení nejsou uloženy ve službě Azure AD.
  - **Uložit do služby Azure Active Directory informace Bitlockeru o obnově**: Konfigurace, které části informací Bitlockeru o obnově se ukládají ve službě Azure AD. Možnosti:
    - **Zálohovat hesla pro obnovení a sady klíčů**
    - **Zálohovat jenom hesla pro obnovení**
  - **Store informace pro obnovení v Azure Active Directory před povolením Bitlockeru**: **Vyžadovat** tohoto nastavení zabráníte uživatelům, aby zapínali BitLocker, pokud informace Bitlockeru o obnově se úspěšně uložené ve službě Azure AD. **Není nakonfigurováno** (výchozí) umožňuje uživatelům k zapnutí nástroje BitLocker, i v případě, že informace o obnovení nejsou úspěšně uloženy ve službě Azure AD.

### <a name="bitlocker-removable-data-drive-settings"></a>Nastavení nástroje BitLocker pro vyměnitelné datové jednotky

Podporováno v následujících edicích Windows 10:

- Enterprise
- Vzdělávání
- Mobilní zařízení
- Mobile Enterprise
- Professional

**Nastavení**:

- **Přístup pro zápis na vyměnitelné datové jednotky, které nechrání BitLocker**: Nastavte na **bloku** dát přístup jen pro čtení datové jednotky, které nejsou chráněné Bitlockerem. Když **Nenakonfigurováno** (výchozí), existuje pro čtení a zápis do datových jednotek, které nejsou chráněné Bitlockerem.
  - **Přístup pro zápis na zařízení nakonfigurovaná jinou organizací**: **Blok** umožňuje přístup pro zápis na zařízení nakonfigurovaná jinou organizací. **Nenakonfigurováno** (výchozí) zápis neumožní.

## <a name="windows-defender-exploit-guard"></a>Ochrana Exploit Guard v programu Windows Defender

Podporováno v následujících edicích Windows 10:

- Domů
- Professional
- Firemní
- Enterprise
- Vzdělávání
- Mobilní zařízení
- Mobile Enterprise

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

- **Soubory a složky, které chcete vyloučit z útoku pravidel pro omezení možností**: Naimportovat nebo přidáte seznam umístění, které chcete vyloučit z nakonfigurovaných pravidel.

> [!IMPORTANT]
> Povolit správné instalace a spuštění aplikace LOB Win32, by měl nastavení anti-malware vyloučení se má zkontrolovat následující adresáře:<p>
> **Na X64 klientské počítače**:<br>
> *C:\Program Files (x86)\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*
>  
> **Na X86 klientské počítače**:<br>
> *C:\Program Files\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*

### <a name="controlled-folder-access"></a>Řízený přístup ke složkám

Chraňte cenná data před škodlivými aplikacemi a hrozbami, jako je například ransomware.

- **Ochrana složek**: Chraňte soubory a složky před nežádoucími změnami škodlivých aplikací. Můžete naimportovat **seznam aplikací, které mají přístup do chráněných složek**, nebo je můžete přidat ručně. Můžete také nahrát **seznam dalších složek, které mají být chráněny**, nebo je můžete přidat ručně.

### <a name="network-filtering"></a>Filtrování sítě

- **Ochrana sítě**: Odchozí připojení z libovolné aplikace chrání špatnou reputací IP adresy nebo domény. Cílem je k ochraně koncových uživatelů z aplikací s přístupem k podvodných, servery hostující zneužití a škodlivý obsah na Internetu. Také brání prohlížeče třetích stran v připojení k nebezpečné weby.

  Možnosti:

  - **Nenakonfigurováno** (výchozí) tuto funkci zakáže. Uživatelé a aplikace nejsou blokované bránily v připojení k doménám nebezpečné. Správci neuvidí této aktivity ve službě Windows Defender Security Center.
  - **Povolit** zapne ochranu sítě a bloky uživatelů a aplikací v připojení k doménám nebezpečné. Správci mohou zobrazit tuto aktivitu ve službě Windows Defender Security Center.
  - **Pouze audit**: Uživatelé a aplikace nejsou blokované bránily v připojení k doménám nebezpečné. Správci mohou zobrazit tuto aktivitu ve službě Windows Defender Security Center.

  [Defender/EnableNetworkProtection CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)

### <a name="exploit-protection"></a>Ochrana Exploit Protection

Pokud chcete používat ochranu před zneužitím, vytvořte soubor XML, který obsahuje nastavení zmírňování systém a aplikace, potřebujete. Existují dvě metody:

 1. PowerShell: Pomocí jedné nebo více rutin Get-ProcessMitigation, Set-ProcessMitigation a ConvertTo-ProcessMitigationPolicy Powershellu. Tyto rutiny nakonfigurují nastavení zmírňování a exportují jejich reprezentaci v jazyce XML.

 2. Uživatelské rozhraní centra zabezpečení Windows Defender: Ve službě Windows Defender Security Center klikněte na ovládací prvek aplikace a prohlížeč a posuňte se dolů zobrazenou obrazovku na najdete ochranu Exploit Protection. Nejprve nakonfigurujte nastavení zmírňování na kartách Nastavení systému a Nastavení programů. Pak ve spodní části obrazovky najděte odkaz Exportovat nastavení a exportujte reprezentaci daného nastavení v jazyce XML.

Můžete zablokovat **úpravy rozhraní ochrany Exploit Protection provedené uživatelem** tak, že nahrajete soubor XML umožňující konfiguraci omezení paměti, toku řízení a zásad. Nastavení v souboru XML se dají použít k ochraně aplikace před zneužitím. **Nenakonfigurováno** (výchozí) neumožní odeslání vlastní konfigurace. 

## <a name="windows-defender-application-control"></a>Řízení aplikací programu Windows Defender

Podporováno v následujících edicích Windows 10:

**Správa mobilních zařízení (MDM)**: 
- Professional
- Firemní
- Enterprise
- Vzdělávání
- Mobilní zařízení
- Mobile Enterprise

**Správa zásad skupiny**: 
- Enterprise

Pomocí **zásad integrity kódu pro řízení aplikací** zvolte další aplikace, které se budou auditovat pomocí Řízení aplikací v programu Windows Defender nebo které tento nástroj může považovat za důvěryhodné, aby bylo možné povolit jejich spuštění. Součásti systému Windows a všechny aplikace z obchodu Windows Store se za důvěryhodné považují automaticky.

Aplikace spuštěné v režimu **Pouze audit** nejsou blokované. Režim **Pouze audit** zapisuje všechny události do protokolů místního klienta.

Po aktivaci se dá řízení aplikací deaktivovat jenom změnou režimu z **Vynutit** na **Pouze audit**. Změna režimu z **Vynutit** na **Nenakonfigurováno** způsobí, že řízení aplikací se na přiřazených zařízeních bude dále vynucovat.

## <a name="windows-defender-credential-guard"></a>Ochrana Credential Guard v programu Windows Defender

Podporováno v následujících edicích Windows 10:

- Enterprise

Ochrana Credential Guard v programu Windows Defender chrání před útoky zaměřenými na krádež přihlašovacích údajů. Izoluje tajné kódy, aby k nim měl přístup jenom privilegovaný software systému.

Nastavení ochrany **Credential Guard** zahrnuje:

- **Zakázat**: Credential Guard vzdáleně vypne, pokud to byla dříve zapnutá pomocí **povoleno bez zámku UEFI** možnost.

- **Povolit se zámkem UEFI**: Credential Guard nelze vzdáleně zakázat pomocí klíče registru nebo zásad skupiny.

    > [!NOTE]
    > Pokud toto nastavení použijete a chcete ochranu Credential Guard později zakázat, musíte nastavit zásady skupiny na **Zakázáno**. Musíte také fyzicky vymazat informace o konfiguraci UEFI z jednotlivých počítačů. Dokud je uložená konfigurace UEFI, je povolená i ochrana přihlašovacích údajů Credential Guard.

- **Povolit bez zámku UEFI**: Umožňuje Credential Guard vzdálené zakázání pomocí zásad skupiny. Na zařízeních s tímto nastavením musí běžet Windows 10 verze 1511 a novější.

Pokud povolíte ochranu Credential Guard, jsou povolené také tyto požadované funkce:

- **Zabezpečení na základě virtualizace** (VBS): Zapne se při příštím restartování počítače. Zabezpečení na základě virtualizace nabízí podporu služeb zabezpečení pomocí hypervisoru Windows.
- **Zabezpečené spouštění s přístupem do paměti Directory**: Zapne VBS se zabezpečeným spouštěním a ochranu přístupu (DMA) paměti. Ochrany DMA vyžadují hardwarovou podporu a povolí se jenom na správně nakonfigurovaných zařízeních.

## <a name="windows-defender-security-center"></a>Centrum zabezpečení v programu Windows Defender

Podporováno v následujících edicích Windows 10:

- Domů
- Professional
- Firemní
- Enterprise
- Vzdělávání
- Mobilní zařízení
- Mobile Enterprise

Centrum zabezpečení v programu Windows Defender funguje jako samostatná aplikace nebo proces z každé jednotlivé funkce. Zobrazuje oznámení prostřednictvím Centra akcí. Funguje jako kolektor nebo jednotné místo, kde k zobrazení stavu a spustit některé konfigurace pro každou funkci. Další informace najdete v dokumentaci k programu [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).

#### <a name="windows-defender-security-center-app-and-notifications"></a>Aplikace a oznámení Centra zabezpečení v programu Windows Defender

Zablokujte přístup koncových uživatelů k různým oblastem aplikace Centrum zabezpečení v programu Windows Defender. Když se skryje nějaká část, zablokují se i související oznámení.

- **Ochrana před viry a hrozbami**
- **Výkon a stav zařízení**
- **Firewall a ochrana sítě**
- **Řízení aplikací a prohlížečů**
- **Možnosti pro rodinu**
- **Oznámení ze zobrazených oblastí aplikace**: Vyberte oznámení, která se budou zobrazovat koncovým uživatelům. Mezi nezávažná oznámení patří souhrny aktivity Antivirové ochrany v programu Windows Defender, včetně oznámení o dokončení kontrol. Všechna další oznámení se považují za závažná.

#### <a name="it-contact-information"></a>Informace o kontaktu IT

Zadejte kontaktní informace oddělení IT, které se zobrazí v aplikaci Security Center v programu Windows Defender a v oznámeních aplikací. Můžete zvolit možnost **Zobrazovat v aplikacích a v oznámeních**, **Zobrazovat jen v aplikaci**, **Zobrazovat jen v oznámeních** nebo **Nezobrazovat**. Zadejte **Název organizace IT** a aspoň jednu z následujících možností kontaktu:

- **Telefonní číslo nebo skypové jméno oddělení IT**
- **E-mailová adresa IT oddělení**
- **Adresa URL webu podpory IT**

## <a name="local-device-security-options"></a>Možnosti místního zabezpečení zařízení

Podporováno v následujících edicích Windows 10:
 
- Domů
- Professional
- Firemní
- Enterprise
- Vzdělávání

Pomocí těchto možností můžete konfigurovat nastavení místního zabezpečení na zařízeních s Windows 10.

### <a name="accounts"></a>Účty

- **Přidat nové účty Microsoft**: Nastavte na **bloku** zabránit uživatelům v přidávání nových účtů Microsoft k zařízení. **Nenakonfigurováno** (výchozí) umožní uživatelům na daném zařízení účty Microsoft používat.
- **Vzdálené přihlášení bez hesla**: **Blok** umožňuje pouze místní účty s prázdnými hesly k přihlášení pomocí klávesnice zařízení. **Nenakonfigurováno** (výchozí) umožní místním účtům, které nejsou chráněné heslem, přihlásit se z jiných umístění než z fyzického zařízení.

#### <a name="admin"></a>Správce

- **Místní účet správce**: Nastavte na **povoleno** povolit účet místního správce. **Nenakonfigurováno** (výchozí) místní účet správce zakáže.
- **Přejmenovat účet správce**: Definuje název jiný účet, který přidruží k identifikátoru zabezpečení (SID) pro účet správce.

#### <a name="guest"></a>Guest

- **Účet Guest**: Nastavte na **povoleno** k povolení účtu guest místní. **Nenakonfigurováno** (výchozí) místní účet Guest zakáže.
- **Přejmenovat účet hosta**: Definuje název jiný účet, který přidruží k identifikátoru zabezpečení (SID) pro účet Guest.

### <a name="devices"></a>Zařízení

- **Vyjmutí z dokovací stanice bez přihlášení zařízení**: Nastavte na **bloku** tak mohou uživatelé stisknout ukotvených přenosném zařízení fyzické vysunout tlačítko bezpečně vyjmout z doku zařízení. **Nenakonfigurováno** (výchozí) bude vyžadovat přihlášení k zařízení, abyste získali oprávnění zařízení vyjmout.
- **Instalovat ovladače tiskáren pro sdílené tiskárny**: Když **povoleno**, každý uživatel může instalovat ovladače tiskáren v rámci připojování ke sdílené tiskárně. **Nenakonfigurováno** (výchozí) umožní instalaci ovladačů tiskárny v rámci připojení ke sdílené tiskárně pouze správcům.
- **Omezit přístup k jednotce CD-ROM na místního aktivního uživatele**: Když **povoleno**, jen interaktivně přihlášený uživatel můžete použít médiím CD-ROM. Pokud je tato zásada povolená a nikdo není interaktivně přihlášený, je možné získat k jednotce CD-ROM přístup přes síť. **Nenakonfigurováno** (výchozí) umožní přístup k jednotce CD-ROM každému.
- **Formátovat a vysouvat vyměnitelná média**: Definujte, kdo může formátovat a vysouvat vyměnitelná média NTFS:
  - **Není nakonfigurováno**
  - **Správci**
  - **Správci a členové skupiny Power Users**
  - **Správci a interaktivní uživatelé**

### <a name="interactive-logon"></a>Interaktivní přihlášení

- **Minut po uzamčení obrazovky nečinnosti, dokud se aktivuje šetřič obrazovky**: Zadejte maximální počet minut nečinnosti na interaktivní relace plochy přihlašovací obrazovka, dokud se spustí šetřič obrazovky.
- **Vyžadovat CTRL + ALT + DEL přihlášení**: Nastavte na **povolit** tak stisknutím kombinace kláves CTRL + ALT + DEL není potřeba pro uživatele k přihlášení. **Nenakonfigurováno** (výchozí) bude od uživatelů před přihlášením k systému Windows vyžadovat stisknutí CTRL + ALT + DEL.
- **Chování při vyjmutí čipové karty**: Určuje, co se stane, když se čipová karta přihlášeného uživatele se odebere ze čtečky čipových karet. Možnosti:

  - **Zamknout pracovní stanici**: Pracovní stanice uzamkne při odebrání čipové karty. Tato možnost umožňuje uživatelům opustit danou oblast, vzít si svoji čipovou kartu s sebou a přesto udržovat chráněnou relaci.
  - **Vynutit odhlášení**: Uživatel je automaticky odhlášen při odebrání čipové karty.
  - **Odpojit, pokud relace služby Vzdálená plocha**: Odebrání čipové karty odpojí relaci bez odhlášení uživatele. Tato možnost umožňuje uživateli později vložením čipové karty obnovit danou relaci na tomto počítači nebo na jiném počítači se čtečkou čipových karet, aniž by se musel znovu přihlašovat. Pokud je relace místní, funguje tato zásada stejně jako možnost Zamknout pracovní stanici.

    Další podrobnosti nabízí [možnosti LocalPoliciesSecurity](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior).

#### <a name="display"></a>Zobrazit

- **Informace o uživateli na zamykací obrazovce**: Nakonfigurujte informace o uživateli, který se zobrazí, když je relace uzamčena. Pokud tato možnost není nakonfigurovaná, zobrazí se zobrazované jméno uživatele, doména a uživatelské jméno.
  - **Není nakonfigurováno**  
  - **Zobrazované jméno uživatele, doména a uživatelské jméno**
  - **Jen zobrazované jméno uživatel**
  - **Nezobrazovat informace o uživateli**
- **Skrýt naposledy přihlášeného uživatele**: **Povolit** skryje uživatelské jméno. **Nenakonfigurováno** (výchozí) uživatelské jméno zobrazí.
- **Skrýt uživatelské jméno při přihlašování**: **Povolit** skryje uživatelské jméno. **Nenakonfigurováno** (výchozí) uživatelské jméno zobrazí.
- **Nadpis zprávy přihlášení**: Nastaví nadpis zprávy pro uživatele přihlášení.
- **Text zprávy přihlášení**: Nastavte text zprávy pro uživatele přihlášení.

### <a name="network-access-and-security"></a>Přístup k síti a zabezpečení

- **Anonymní přístup k pojmenovaným kanálům a sdíleným**: **Není nakonfigurováno** (výchozí) omezuje anonymní přístup ke sdílené složce a nastavení pojmenovaného kanálu. Platí pro nastavení, ke kterým se dá přistupovat anonymně.
- **Anonymní výčty účtů SAM**: **Povolit** anonymním uživatelům vytvořit výčet účtů SAM. Windows umožňuje anonymním uživatelům vytvořit výčet názvů účtů domén a síťových sdílených složek.
- **Anonymní výčty účtů SAM a sdílených složek**: **Není nakonfigurováno** (výchozí) znamená, že anonymní uživatelé mohou vytvořit výčet názvů účtů domén a sdílených síťových složek. Pokud chcete zabránit anonymním výčtům účtů SAM a sdílených síťových složek, nastavte možnost **Blokovat**.
- **Hodnoty hash LAN Manageru při změně hesla uložená**: Při příští změně hesla zvolte na **povolit** LM (LAN Manager) pro ukládání hodnoty hash pro nové heslo. Pokud je nastavená možnost **Nenakonfigurováno** (výchozí), hodnota hash se neuloží.
- **Žádosti o ověření pku2u odeslaným**: **Blok** o ověřování pku2u odeslaným na zařízení používat online identity. Možnost **Nenakonfigurováno** (výchozí) tyto žádosti povoluje.
- **Omezit vzdálená připojení RPC k SAM**: Nastavte na **povolit** k znemožňoval uživatelům a skupinám v provádění vzdáleného volání RPC na zabezpečení Správce účtů (SAM), který uchovává uživatelské účty a hesla. **Povolit** také umožňuje změnit výchozí řetězec zabezpečení SDDL Descriptor Definition Language () explicitně povolit nebo zakázat uživatele a skupiny pro tyto vzdálené volání. **Není nakonfigurováno** (výchozí) používá výchozí popisovač zabezpečení a může povolit uživatelům a skupinám vzdáleně volat SAM RPC.
  - **Popisovač zabezpečení**

### <a name="recovery-console-and-shutdown"></a>Konzola pro zotavení a vypnutí

- **Stránkovací soubor vymazat virtuální paměti při vypínání**: Nastavte na **povolit** Vymazat stránkovací soubor virtuální paměti, když se zařízení vypne. **Nenakonfigurováno** virtuální paměť nevymaže.
- **Vypnutí bez protokolu v**: **Blok** skryje možnost vypnutí na přihlašovací obrazovce Windows. Uživatelé se musí k zařízení přihlásit, aby ho mohli vypnout. **Není nakonfigurováno** (výchozí) umožňuje uživateli vypnout zařízení z přihlašovací obrazovky Windows.

### <a name="user-account-control"></a>Řízení uživatelských účtů

- **Integrita UIA bez zabezpečeného umístění**: Pokud je nastavena na **bloku**, aplikace v zabezpečeném umístění v systému souborů spusťte pouze s UIAccess integrity. **Nenakonfigurováno** (výchozí) umožní spuštění aplikací s integritou UIAccess i v nezabezpečených umístěních v systému souborů.
- **Virtualizovat chyby zápisu souboru a registru do umístění jednotlivých uživatelů**: Pokud je nastavena na **povoleno**, aplikace, které zapsat data do chráněných místa selhání. Pokud je nastavena na **Nenakonfigurováno** (výchozí), zapsat application selhání přesměrováni na dobu běhu na umístění uživatelů definovaný pro systém souborů a registr.
- **Zvýšit oprávnění pouze spustitelné soubory, které se podepsaly a ověřily**: Nastavte na **povoleno** k vynucení ověřování infrastruktury veřejných KLÍČŮ certifikační cesta pro spustitelný soubor, před spuštěním. **Nenakonfigurováno** (výchozí) nebude vynucovat ověření cesty certifikace infrastruktury veřejných klíčů, než se bude moct spustitelný soubor spustit.

#### <a name="uia-elevation-prompt-behavior-settings"></a>Nastavení chování výzvy ke zvýšení úrovně oprávnění UIA

- **Výzvy ke zvýšení oprávnění pro admins**: Definuje chování výzvy ke zvýšení oprávnění pro správce v režimu schválení správce:
  - **Zvýšit oprávnění bez dotaz**
  - **Požádat o přihlašovací údajů na zabezpečené ploše**
  - **Požádat o souhlas na zabezpečené ploše**
  - **Vyzvat k zadání pověření**
  - **Požádat o souhlas**
  - **Není nakonfigurováno**: Požádat o souhlas pro binární soubory bez Windows
- **Výzvy ke zvýšení oprávnění pro standardní uživatele**: Definuje chování výzvy ke zvýšení oprávnění pro standardní uživatele:
  - **Automaticky zamítat žádosti o zvýšení oprávnění**
  - **Požádat o přihlašovací údajů na zabezpečené ploše**
  - **Není nakonfigurováno**: Vyzvat k zadání pověření
- **Směrovat výzvy ke zvýšení oprávnění na interaktivní relaci plochy uživatele**: **Povolit** tak všechny požadavky na zvýšení oprávnění přejít na ploše interaktivního uživatele, ne zabezpečenou plochu. Použijí se všechna nastavení zásad chování výzev pro správce a standardní uživatele. **Nenakonfigurováno** (výchozí) vynutí přechod všech žádostí o zvýšení oprávnění na zabezpečenou plochu (bez ohledu na všechna nastavení zásad chování výzev pro správce a standardní uživatele).
- **Řádek se zvýšenými oprávněními pro instalace aplikací**: Pokud je nastavena na **povoleno**, instalační balíčky aplikací nejsou zjištěny nebo zobrazení výzvy ke zvýšení oprávnění. **Nenakonfigurováno** (výchozí) bude uživatele vyzývat k zadání přihlašovacích údajů správce, když instalační balíček aplikace vyžaduje zvýšená oprávnění.
- **Ke zvýšení oprávnění UIA bez zabezpečené plochy**: **Povolit** povolit aplikacím UIAccess Vyzývat ke zvýšení oprávnění, bez použití zabezpečené plochy. **Nenakonfigurováno** (výchozí) bude pro výzvy ke zvýšení úrovně oprávnění používat zabezpečenou plochu.

#### <a name="admin-approval-mode-settings"></a>Nastavení režimu schválení správcem

- **Schválení správcem pro předdefinovaný účet Administrator režimu**: **Povolené** umožňuje předdefinovaný účet správce použít režim schválení správcem. Všechny operace vyžadující zvýšení oprávnění zobrazí uživateli výzvu ke schválení operace. **Nenakonfigurováno** (výchozí) spustí všechny aplikace s plnými oprávněními správce.
- **Spustit všechny správce v režimu schválení správcem**: Nastavte na **povoleno** zakázat režim schválení správcem a všechny související zásady nastavení nástroje Řízení uživatelských účtů. **Nenakonfigurováno** (výchozí) režim schválení správcem povolí.

### <a name="microsoft-network-client"></a>Microsoft Network Client

- **Digitálně podepsat komunikaci (Pokud server souhlasí)**: Určuje, pokud klient SMB vyjedná podepisování paketů SMB. Když je tato možnost **nenakonfigurovaná** nebo povolená (výchozí), klient sítě Microsoft požádá server o podepisování paketů SMB při nastavení relace. Pokud je na serveru podepisování paketů povolené, podepisování paketů se vyjedná. Když je tato možnost **zakázaná**, klient SMB podepisování paketů nikdy vyjednávat nebude.
- **Posílat nešifrovaná hesla serverům SMB třetích stran**: Pokud je nastavena na **povolit**, přesměrovače zprávy bloku SMB (Server) posílat nešifrovaná hesla serverům SMB mimo Microsoft, které nepodporují šifrování hesel během ověřování. **Nenakonfigurováno** (výchozí) hesla šifruje.

### <a name="microsoft-network-server"></a>Server sítě Microsoft

- **Digitálně podepsat komunikaci (Pokud klient souhlasí)**: Určuje, pokud SMB server vyjedná podepisování paketů SMB s klienty, kteří si ji vyžádat. Když je tato možnost **povolená**, server sítě Microsoft vyjedná podepisování paketů SMB podle požadavku klienta. To znamená, že pokud je v klientovi podepisování paketů povolené, podepisování paketů se vyjedná. Když je tato možnost **nenakonfigurovaná** nebo zakázaná (výchozí), klient SMB podepisování paketů nikdy vyjednávat nebude.
- **Digitálně podepisovat komunikaci (vždy)**: Určuje, pokud součást serveru SMB vyžaduje podepisování paketů. Když je tato možnost **povolená**, nebude server sítě Microsoft s klientem sítě Microsoft komunikovat, pokud tento klient nesouhlasí s podepisováním paketů SMB. Když je tato možnost **nenakonfigurovaná** nebo zakázaná (výchozí), podepisování paketů SMB mezi klientem a serverem se vyjedná.

## <a name="next-steps"></a>Další postup

Profil je vytvořený, ale zatím se nepoužívá. Dále [přiřadit profil](device-profile-assign.md), a [monitorování jejího stavu](device-profile-monitor.md).

Konfigurace nastavení ochrany koncového bodu na [macOS](endpoint-protection-macos.md) zařízení.
