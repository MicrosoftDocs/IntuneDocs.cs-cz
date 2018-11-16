---
title: Přidání ochrany koncových bodů pro Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Na zařízeních s Windows 10 můžete v Intune použít nebo nakonfigurovat nastavení ochrany koncového bodu a povolit tak na místních zařízeních funkce Windows Defender, mezi něž patří Application Guard, brána firewall, filtr SmartScreen, šifrování a BitLocker, Exploit Guard, řízení aplikací, Security Center a zabezpečení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1a7c7ebca1c6472b58021a57b1b4a59fc42966b0
ms.sourcegitcommit: d8edd1c3d24123762dd6d14776836df4ff2a31dd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/13/2018
ms.locfileid: "51576949"
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-intune"></a>Nastavení ochrany koncového bodu pro Windows 10 a novější v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profil ochrany koncového bodu vám umožňuje ovládat funkce zabezpečení na zařízeních s Windows 10, jako je BitLocker nebo Windows Defender.

V tomto článku se dozvíte, jak vytvářet profily ochrany koncového bodu. Pokud chcete nakonfigurovat antivirovou ochranu v programu Windows Defender, přečtěte si téma [Omezení pro zařízení s Windows 10](device-restrictions-windows-10.md#windows-defender-antivirus). 

## <a name="windows-defender-application-guard"></a>Ochrana Application Guard v programu Windows Defender

Podporováno v následujících edicích Windows 10:

- Enterprise 
- Professional

Když budete používat Microsoft Edge, Ochrana Application Guard v programu Windows Defender ochrání vaše prostředí před weby, kterým vaše organizace nedůvěřuje. Když uživatelé navštíví weby, které nejsou uvedené v ohraničení vaší izolované sítě, otevřou se tyto weby ve virtuální relaci procházení Hyper-V. Důvěryhodné weby se definují prostřednictvím ohraničení sítě, které se dá konfigurovat v Konfiguraci zařízení.

Ochrana Application Guard je dostupná jenom pro zařízení s Windows 10 (64bitovou verzí). Tento profil nainstaluje součást Win32, pomocí které se aktivuje ochrana Application Guard.

- **Application Guard**: **Povolit** zapne funkci, která otevírá neschválené weby v kontejneru procházení virtualizovaném pomocí technologie Hyper-V. **Nenakonfigurováno** (výchozí) znamená, že se na zařízení otevře každá stránka (schválená i neschválená).
- **Chování schránky**: Zvolte, které akce kopírování a vkládání jsou povolené mezi místním počítačem a virtuálním prohlížečem ochrany Application Guard.
- **Externí obsah na firemních webech**: **Blokovat** neumožní načítání obsahu z neschválených webů. **Nenakonfigurováno** (výchozí) znamená, že se na zařízení mohou otevřít nefiremní weby.
- **Tisk z virtuálního prohlížeče**: **Povolit** umožní tisknutí obsahu z virtuálního prohlížeče do souborů PDF, XPS a na místní nebo síťové tiskárny. **Nenakonfigurováno** (výchozí) zakáže všechny tiskové funkce.
- **Shromažďovat protokoly**: **Povolit** umožní shromažďování protokolů pro události, ke kterým dojde v relaci procházení ochrany Application Guard. **Nenakonfigurováno** (výchozí) žádné protokoly v relaci procházení neshromažďuje.
- **Zachovat uživatelem vygenerovaná data prohlížeče**: **Povolit** umožní ukládání dat uživatelů (třeba hesla, oblíbené položky a soubory cookie), která se vytvoří během virtuální relace procházení ochrany Application Guard. **Nenakonfigurováno** (výchozí) zahodí všechny soubory a data stažená uživatelem při restartu zařízení nebo odhlášení uživatele.
- **Akcelerace grafiky**: **Povolit** umožní rychleji načítat weby a videa náročná na grafiku získáním přístupu k virtuálnímu grafickému procesoru. **Nenakonfigurováno** (výchozí) použije místo virtuálního grafického procesoru CPU zařízení.
- **Stahovat soubory do systému souborů hostitele**: **Povolit** umožní uživatelům stahovat soubory z virtualizovaného prohlížeče do hostitelského operačního systému. **Nenakonfigurováno** (výchozí) nestáhne soubory do hostitelského operačního systému, ale stáhne je do místního úložiště zařízení.

## <a name="windows-defender-firewall"></a>Firewall v programu Windows Defender

Podporováno v následujících edicích Windows 10:
- Domů
- Professional
- Do zaměstnání
- Enterprise
- Vzdělávání
- Mobilní
- Mobile Enterprise

### <a name="global-settings"></a>Globální nastavení

Tato nastavení platí pro všechny typy sítě.

- **Protokol FTP (File Transfer Protocol)**: **Blokovat** zakáže stavový protokol FTP. **Nenakonfigurováno** (výchozí) umožní firewallu filtrování stavového protokolu FTP, které povolí sekundární připojení.
- **Doba nečinnosti přidružení zabezpečení před odstraněním**: Přidružení zabezpečení se odstraní, když se po dobu *n* sekund nezaznamenají v síti žádné přenosy. Zadejte čas nečinnosti v sekundách.
- **Kódování předsdíleného klíče**: **Povolit** použije kódování předsdíleného klíče pomocí UTF-8. **Nenakonfigurováno** (výchozí) použije hodnotu místního úložiště.
- **Výjimky protokolu IPsec**: Nakonfigurujte konkrétní přenosy, u kterých budou platit výjimky protokolu IPsec, včetně těchto:
  - **Zjišťování kódů typu ICMP IPv6 sousedem**
  - **Protokol ICMP**
  - **Zjišťování kódů typu ICMP IPv6 směrovačem**
  - **Přenosy DHCP IPv4 i IPv6**
- **Ověření seznamu odvolaných certifikátů**: Určete, jak se bude vynucovat ověření seznamu odvolaných certifikátů, například **Zakázat ověření seznamu CRL**, **Neúspěšné ověření seznamu CRL jenom u odvolaného certifikátu** nebo **Neúspěšné ověření seznamu CRL při každé zjištěné chybě**.
- **Oportunisticky přiřadit sadu ověřování na klíčovací modul**: **Povolit** nastaví klíčovací moduly tak, aby ignorovaly pouze sady ověřování, které nepodporují. **Nenakonfigurováno** nastaví klíčovací moduly tak, aby v případě, že nepodporují všechny sady ověřování v dané sadě, se celá sada ověřování ignorovala.
- **Fronty paketů**: Zadejte, jak se povoluje škálování softwaru na straně příjmu u scénáře se šifrovaným příjmem a předáváním nešifrovaného textu pro bránu tunelového propojení IPsec. Toto nastavení zajišťuje zachování pořadí paketů.

### <a name="network-settings"></a>Nastavení sítě

Tato nastavení platí pro určité typy sítě, například pro typy **Doménová (firemní) síť**, **Privátní (zjistitelná) síť** a **Veřejná (nezjistitelná) síť**.

#### <a name="general-settings"></a>Obecná nastavení

- **Firewall v programu Windows Defender**: **Povolit** zapne bránu firewall s pokročilým zabezpečením. **Nenakonfigurováno** (výchozí) povolí veškerý provoz bez ohledu na ostatní nastavení zásad.
- **Neviditelný režim**: **Blokovat** zakáže provoz firewallu v neviditelném režimu. Blokování neviditelného režimu vám umožňuje zablokovat také **výjimku zabezpečených paketů protokolu IPsec**. **Nenakonfigurováno** (výchozí) provozuje firewall v neviditelném režimu, který pomáhá předejít odpovědím na zjišťovací požadavky.
- **Stíněné**: **Blokovat** tuto funkci vypne. **Nenakonfigurováno** (výchozí) toto nastavení povolí. Když je toto nastavení a Firewall v programu Windows Defender zapnutý, veškerý provoz bez ohledu na ostatní nastavení zásad se blokuje.
- **Jednosměrové odpovědi na vícesměrová vysílání**: **Blokovat** zakáže jednosměrové odpovědi na vícesměrová vysílání. Jednosměrové odpovědi na zprávy vícesměrového nebo všesměrového vysílání obvykle nebudete chtít přijímat. Takové odpovědi můžou naznačovat útok DoS nebo pokus útočníka otestovat známý aktivní počítač. **Nenakonfigurováno** (výchozí) toto nastavení povolí.
- **Příchozí upozornění**: **Blokovat** skryje zobrazování upozornění uživatelům, když se blokuje naslouchání aplikace na portu. **Nenakonfigurováno** (výchozí) toto nastavení povolí, a když se blokuje naslouchání aplikace na portu, může uživatelům upozornění zobrazit.
- **Výchozí akce pro příchozí připojení**: **Blokovat** nespustí výchozí akci, kterou brána firewall provádí u příchozích připojení. **Nenakonfigurováno** (výchozí) výchozí akci brány firewall u příchozích připojení provede.

#### <a name="rule-merging"></a>Sloučení pravidel

- **Pravidla brány firewall v programu Windows Defender pro autorizované aplikace z místního úložiště**: **Povolit** bude používat a vynucovat autorizovaná pravidla brány firewall v místním úložišti. **Nenakonfigurováno** (výchozí) bude pravidla brány firewall autorizované aplikace v místním úložišti ignorovat a nebude je vynucovat.
- **Globální pravidla brány firewall v programu Windows Defender pro porty z místního úložiště**: **Povolit** bude používat a vynucovat globální pravidla brány firewall portu v místním úložišti. **Nenakonfigurováno** (výchozí) bude globální pravidla brány firewall portu v místním úložišti ignorovat a nebude je vynucovat.
- **Pravidla brány firewall v programu Windows Defender z místního úložiště**: **Povolit** bude používat a vynucovat globální pravidla brány firewall v místním úložišti. **Nenakonfigurováno** (výchozí) bude pravidla brány firewall v místním úložišti ignorovat a nebude je vynucovat.
- **Pravidla IPsec z místního úložiště**: **Povolit** pravidla zabezpečení připojení z místního úložiště použije bez ohledu na verze schématu nebo pravidel zabezpečení připojení. **Nenakonfigurováno** (výchozí) pravidla zabezpečení připojení z místního úložiště bude bez ohledu na verze schématu nebo pravidel zabezpečení připojení ignorovat a nebude je vynucovat.

## <a name="windows-defender-smartscreen-settings"></a>Nastavení filtru SmartScreen v programu Windows Defender

Podporováno v následujících edicích Windows 10 s nainstalovaným prohlížečem Microsoft Edge:
- Domů
- Professional
- Do zaměstnání
- Enterprise
- Vzdělávání
- Mobilní
- Mobile Enterprise

**Nastavení**:

- **Filtr SmartScreen pro aplikace a soubory**: **Povolit** zapne filtr Windows SmartScreen, který ověřuje spustitelné soubory a běžící aplikace. SmartScreen je cloudová antiphisingová a antimalwarová vrstva ochrany. **Nenakonfigurováno** (výchozí) filtr SmartScreen zakáže.
- **Provádění neověřených souborů**: **Blokovat** zakáže koncovým uživatelům spouštět soubory, které filtr Windows SmartScreen neověřil. **Nenakonfigurováno** (výchozí) tuto funkci vypne a umožní uživatelům spouštět i neověřené soubory.

## <a name="windows-encryption"></a>Šifrování Windows

### <a name="windows-settings"></a>Nastavení systému Windows

Podporováno v následujících edicích Windows 10:

- Professional
- Do zaměstnání
- Enterprise
- Vzdělávání
- Mobilní
- Mobile Enterprise

**Nastavení**:

- **Šifrovat zařízení**: **Vyžadovat** zobrazí uživatelům výzvu, aby povolili šifrování zařízení. V závislosti na edici Windows a konfiguraci systému se může od uživatelů vyžadovat:  
  - Aby potvrdili, že není povolené šifrování od jiného zprostředkovatele.
  - Aby vypnuli nástroj BitLocker Drive Encryption a potom ho znovu zapnuli.
    
    Pokud je zapnuto šifrování Windows a současně je aktivní jiná metoda šifrování, mohlo by to narušit stabilitu zařízení. 
- **Šifrovat paměťovou kartou (jenom mobilní verze)**: **Vyžadovat** bude požadovat zašifrování případných vyměnitelných paměťových karet, které zařízení používá. **Nenakonfigurováno** (výchozí) nebude požadovat šifrování paměťových karet a nebude k tomu uživatele vyzývat. Toto nastavení platí jenom pro zařízení s Windows 10 Mobile.

### <a name="bitlocker-base-settings"></a>Základní nastavení BitLockeru

Podporováno v následujících edicích Windows 10:

- Enterprise
- Vzdělávání
- Mobilní
- Mobile Enterprise

Základní nastavení jsou univerzální nastavení BitLockeru pro všechny typy datových jednotek. Tato nastavení určují, které úkoly šifrování jednotek nebo možnosti konfigurace může koncový uživatel upravit na všech typech datových jednotek.

- **Upozornění pro další šifrování disku**: **Blokovat** zakáže upozornění, pokud je na daném zařízení jiná služba šifrování disku. **Nenakonfigurováno** (výchozí) zobrazení upozornění povolí.
- **Konfigurovat metody šifrování**: **Povolit** umožní konfiguraci algoritmů šifrování operačního systému, dat a vyměnitelných jednotek. **Nenakonfigurováno** (výchozí) znamená, že BitLocker používá jako výchozí metodu šifrování XTS-AES 128 bit nebo používá metodu šifrování určenou skriptem instalace.
  - **Šifrování jednotek s operačním systémem**: Umožňuje vybrat metodu šifrování pro jednotky s operačním systémem. Doporučujeme použít algoritmus XTS-AES.
  - **Šifrování pevných datových jednotek**: Umožňuje vybrat metodu šifrování pro pevné (vestavěné) datové jednotky. Doporučujeme použít algoritmus XTS-AES.
  - **Šifrování vyměnitelných datových jednotek**: Umožňuje vybrat metodu šifrování pro vyměnitelné datové jednotky. Pokud se vyměnitelná jednotka používá se zařízeními s jiným systémem než Windows 10, doporučujeme použít algoritmus AES-CBC.

### <a name="bitlocker-os-drive-settings"></a>Nastavení BitLockeru pro jednotky s operačním systémem
Podporováno v následujících edicích Windows 10:

- Enterprise
- Vzdělávání
- Mobilní
- Mobile Enterprise

Tato nastavení platí konkrétně pro datové jednotky s operačním systémem.

- **Další ověření při spuštění**: **Vyžadovat** konfiguruje požadavky na ověření pro spuštění počítače, včetně využití čipu TPM (Trusted Platform Module). **Nenakonfigurováno** (výchozí) na zařízeních s TPM konfiguruje pouze základní možnosti.
  - **BitLocker s nekompatibilním čipem TPM**: **Blokovat** zakáže použití BitLockeru, když zařízení nemá kompatibilní čip TPM. **Nenakonfigurováno** (výchozí) umožní uživatelům používat BitLocker bez kompatibilního čipu TPM. BitLocker může vyžadovat heslo nebo spouštěcí klíč.
  - **Kompatibilní spouštění s čipem TPM**: Umožňuje vybrat, jestli je čip TPM povolený, nepovolený nebo povinný.
  - **Kompatibilní spouštěcí PIN kód čipu TPM**: Umožňuje vybrat, jestli je použití spouštěcího PIN kódu s čipem TPM povolené, nepovolené nebo povinné. Povolení spouštěcího PIN kódu vyžaduje interakci koncového uživatele. 
  - **Kompatibilní spouštěcí klíč čipu TPM**: Umožňuje vybrat, jestli je použití spouštěcího klíče s čipem TPM povolené, nepovolené nebo povinné. Povolení spouštěcího klíče vyžaduje interakci koncového uživatele. 
  - **Kompatibilní spouštěcí klíč a PIN kód čipu TPM**: Umožňuje vybrat, jestli je použití spouštěcího klíče a PIN kódu s čipem TPM povolené, nepovolené nebo povinné. Povolení spouštěcího klíče a PIN kódu vyžaduje interakci koncového uživatele.
- **Minimální délka PIN kódu**: **Povolit** umožní u čipu TPM konfiguraci minimální délky spouštěcího PIN kódu. **Nenakonfigurováno** (výchozí) umožní uživatelům nakonfigurovat spouštěcí PIN kód s libovolnou délkou v rozmezí od 6 do 20 číslic.
  - **Minimální počet znaků**: Zadejte počet znaků požadovaný pro spouštěcí PIN kód v rozmezí **4**-**20**.
- **Obnovení jednotky s operačním systémem**: **Povolit** umožní řízení obnovení jednotek s operačním systémem chráněných BitLockerem v situacích, kdy nejsou k dispozici požadované informace ke spuštění. **Nenakonfigurováno** (výchozí) podporuje výchozí možnosti obnovení pomocí nástroje BitLocker. Ve výchozím nastavení je povolený Agent obnovování dat (DRA). Možnosti obnovení určuje uživatel – včetně hesla pro obnovení a obnovovacího klíče. Informace o obnovení se do služby AD DS nezálohují.
  - **Agent obnovení dat založený na certifikátech**: **Blokovat** zakáže použití agenta obnovení dat založeného na certifikátech na jednotkách s operačním systémem chráněných BitLockerem. **Nenakonfigurováno** (výchozí) použití agentů obnovení dat u jednotek s operačním systémem chráněných BitLockerem povolí.
  - **Vytváření hesla pro obnovení uživatelem**: Můžete vybrat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 48místné heslo pro obnovení nebo jestli je vytvoření povinné.
  - **Vytváření obnovovacího klíče uživatelem**: Můžete vybrat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 256bitové heslo pro obnovení nebo jestli je vytvoření povinné.
  - **Možnosti obnovení v průvodci nastavením BitLockeru**: **Blokovat** zabrání uživatelům zobrazovat a měnit možnosti obnovení. **Nenakonfigurováno** (výchozí) umožní uživatelům po spuštění BitLockeru zobrazovat a měnit možnosti obnovení.
  - **Ukládat informace pro obnovení BitLockeru do AD DS**: **Povolit** umožní ukládat informace pro obnovení BitLockeru do služby Azure Active Directory (AAD). **Nenakonfigurováno** (výchozí) ukládat informace pro obnovení BitLockeru do služby AAD nebude.
  - **Informace BitLockeru o obnově uložené v AD DS**: Můžete nakonfigurovat, které části informací BitLockeru o obnově se budou ve službě Azure AD ukládat. Vybírejte z těchto možností:
    - **Zálohovat hesla pro obnovení a sady klíčů**
    - **Zálohovat jenom hesla pro obnovení**
  - **Ukládat informace o obnově v AD DS před povolením BitLockeru**: **Vyžadovat** zabrání uživatelům, aby zapínali BitLocker, pokud informace BitLockeru o obnově nejsou úspěšně uložené ve službě Azure Active Directory. **Nenakonfigurováno** (výchozí) umožní uživatelům zapnout BitLocker, i když informace o obnově nejsou ve službě Azure Active Directory úspěšně uložené.
- **Zpráva o obnově a adresa URL před spuštěním**: **Povolit** umožní konfiguraci zprávy a adresy URL, které se zobrazí na obrazovce pro obnovení klíče před spuštěním. **Nenakonfigurováno** (výchozí) tuto funkci zakáže.
  - **Zpráva o obnovení před spuštěním**: Můžete konfigurovat, jak se zpráva o obnovení před spuštěním zobrazí uživatelům. Vybírejte z těchto možností:
    - **Použít výchozí zprávu a adresu URL pro obnovení**
    - **Použít prázdnou zprávu a adresu URL pro obnovení**
    - **Použít vlastní zprávu o obnovení**
    - **Použít vlastní adresu URL pro obnovení**

### <a name="bitlocker-fixed-data-drive-settings"></a>Nastavení nástroje BitLocker pro pevné datové jednotky

Podporováno v následujících edicích Windows 10:

- Enterprise
- Vzdělávání
- Mobilní
- Mobile Enterprise

**Nastavení**:

- **Oprávnění k zápisu na pevné datové disky, které nechrání BitLocker**: **Blokovat** umožní k datovým jednotkám, které nejsou chráněné BitLockerem, přístup jen pro čtení. **Nenakonfigurováno** (výchozí) umožní k datovým jednotkám, které nejsou chráněné BitLockerem, přístup pro čtení a zápis.
- **Obnovení pevného disku**: **Povolit** umožní řídit obnovu pevných jednotek chráněných BitLockerem v případě, že nejsou k dispozici požadované informace pro spuštění. **Nenakonfigurováno** (výchozí) tuto funkci zakáže.
  - **Agent obnovení dat**: **Blokovat** zakáže použití agentů obnovení dat u Editoru zásad pevných jednotek chráněných BitLockerem. **Nenakonfigurováno** (výchozí) použití agentů obnovení dat u pevných jednotek chráněných BitLockerem povolí.
  - **Vytváření hesla pro obnovení uživatelem**: Můžete nakonfigurovat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 48místné heslo pro obnovení nebo jestli je vytvoření povinné.  
  - **Vytváření obnovovacího klíče uživatelem**: Můžete nakonfigurovat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 256bitové heslo pro obnovení nebo jestli je vytvoření povinné.
  - **Možnosti obnovení v průvodci nastavením BitLockeru**: **Blokovat** zabrání uživatelům zobrazovat a měnit možnosti obnovení. **Nenakonfigurováno** (výchozí) umožní uživatelům po spuštění BitLockeru zobrazovat a měnit možnosti obnovení.
  - **Ukládat informace pro obnovení BitLockeru do AD DS**: **Povolit** umožní ukládat informace pro obnovení BitLockeru do služby Azure Active Directory (AAD). **Nenakonfigurováno** (výchozí) ukládat informace pro obnovení BitLockeru do služby AAD nebude.
  - **Informace BitLockeru o obnově v AD DS**: Můžete nakonfigurovat, které části informací BitLockeru o obnově se budou ve službě Azure Active Directory ukládat. Vybírejte z těchto možností:
    - **Zálohovat hesla pro obnovení a sady klíčů**
    - **Zálohovat jenom hesla pro obnovení**
  - **Ukládat informace o obnově v AD DS před povolením BitLockeru**: **Vyžadovat** zabrání uživatelům, aby zapínali BitLocker, pokud informace BitLockeru o obnově nejsou úspěšně uložené ve službě Azure Active Directory. **Nenakonfigurováno** (výchozí) umožní uživatelům zapnout BitLocker, i když informace o obnově nejsou ve službě Azure Active Directory úspěšně uložené.

### <a name="bitlocker-removable-data-drive-settings"></a>Nastavení nástroje BitLocker pro vyměnitelné datové jednotky

Podporováno v následujících edicích Windows 10:

- Enterprise
- Vzdělávání
- Mobilní
- Mobile Enterprise

**Nastavení**:

- **Oprávnění k zápisu na vyměnitelné datové disky, které nechrání BitLocker**: **Blokovat** umožní k datovým jednotkám, které nejsou chráněné BitLockerem, přístup jen pro čtení. **Nenakonfigurováno** (výchozí) umožní k datovým jednotkám, které nejsou chráněné BitLockerem, přístup pro čtení a zápis.
  - **Oprávnění k zápisu na zařízení nakonfigurovaná jinou organizací**: **Blokovat** zápis na zařízení nakonfigurovaná jinou organizací umožní. **Nenakonfigurováno** (výchozí) zápis neumožní.

## <a name="windows-defender-exploit-guard"></a>Ochrana Exploit Guard v programu Windows Defender

Podporováno v následujících edicích Windows 10:

- Domů
- Professional
- Do zaměstnání
- Enterprise
- Vzdělávání
- Mobilní
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

- **Soubory a složky, které se mají vyloučit z pravidel pro omezení možností útoku**: Umožňuje naimportovat nebo přidat seznam umístění, která se mají vyloučit z nakonfigurovaných pravidel.

### <a name="controlled-folder-access"></a>Řízený přístup ke složkám

Chraňte cenná data před škodlivými aplikacemi a hrozbami, jako je například ransomware.

- **Ochrana složek**: Umožňuje chránit soubory a složky před nežádoucími změnami, které provádějí škodlivé aplikace. Můžete naimportovat **seznam aplikací, které mají přístup do chráněných složek**, nebo je můžete přidat ručně. Můžete také nahrát **seznam dalších složek, které mají být chráněny**, nebo je můžete přidat ručně.

### <a name="network-filtering"></a>Filtrování sítě

Zablokujte odchozí připojení z libovolné aplikace na IP adresy a domény s nízkou reputací.

### <a name="exploit-protection"></a>Ochrana Exploit Protection

Pokud chcete zapnout ochranu Exploit Protection, vytvořte soubor XML, který bude obsahovat požadovaná nastavení zmírňování pro systém a aplikace. Existují dvě metody:

 1. PowerShell: Použijte jednu nebo více powershellových rutin Get-ProcessMitigation, Set-ProcessMitigation a ConvertTo-ProcessMitigationPolicy. Tyto rutiny nakonfigurují nastavení zmírňování a exportují jejich reprezentaci v jazyce XML.

 2. Uživatelské rozhraní Centra zabezpečení v programu Windows Defender: V Centru zabezpečení v programu Windows Defender klikněte na ovládací prvek Aplikace a prohlížeč a posuňte zobrazenou obrazovku až dolů, kde najdete ochranu Exploit Protection. Nejprve nakonfigurujte nastavení zmírňování na kartách Nastavení systému a Nastavení programů. Pak ve spodní části obrazovky najděte odkaz Exportovat nastavení a exportujte reprezentaci daného nastavení v jazyce XML.

Můžete zablokovat **úpravy rozhraní ochrany Exploit Protection provedené uživatelem** tak, že nahrajete soubor XML umožňující konfiguraci omezení paměti, toku řízení a zásad. Nastavení v souboru XML se dají použít k ochraně aplikace před zneužitím. **Nenakonfigurováno** (výchozí) neumožní odeslání vlastní konfigurace. 

## <a name="windows-defender-application-control"></a>Řízení aplikací programu Windows Defender

Podporováno v následujících edicích Windows 10:

**Správa mobilních zařízení (MDM)**: 
- Professional
- Do zaměstnání
- Enterprise
- Vzdělávání
- Mobilní
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

- **Zakázat**: Vzdáleně vypne ochranu Credential Guard, pokud byla dříve zapnutá pomocí možnosti **Povolit bez zámku UEFI**.

- **Povolit se zámkem UEFI**: Ochrana Credential Guard nepůjde pomocí klíčů registru ani zásad skupiny vzdáleně zakázat.

    > [!NOTE]
    > Pokud toto nastavení použijete a chcete ochranu Credential Guard později zakázat, musíte nastavit zásady skupiny na **Zakázáno**. Musíte také fyzicky vymazat informace o konfiguraci UEFI z jednotlivých počítačů. Dokud je uložená konfigurace UEFI, je povolená i ochrana přihlašovacích údajů Credential Guard.

- **Povolit bez zámku UEFI**: Umožňuje ochranu Credential Guard pomocí zásad skupiny vzdáleně zakázat. Na zařízeních s tímto nastavením musí běžet Windows 10 verze 1511 a novější.

Pokud povolíte ochranu Credential Guard, jsou povolené také tyto požadované funkce:

- **Zabezpečení na základě virtualizace** (VBS): Zapne se při příštím restartování počítače. Zabezpečení na základě virtualizace nabízí podporu služeb zabezpečení pomocí hypervisoru Windows.
- **Zabezpečené spouštění s přímým přístupem do paměti**: Zapne VBS se zabezpečeným spouštěním a ochranami přímého přístupu do paměti (DMA). Ochrany DMA vyžadují hardwarovou podporu a povolí se jenom na správně nakonfigurovaných zařízeních.

## <a name="windows-defender-security-center"></a>Centrum zabezpečení v programu Windows Defender

Podporováno v následujících edicích Windows 10:

- Domů
- Professional
- Do zaměstnání
- Enterprise
- Vzdělávání
- Mobilní
- Mobile Enterprise

Centrum zabezpečení v programu Windows Defender funguje jako samostatná aplikace nebo proces z každé jednotlivé funkce. Zobrazuje oznámení prostřednictvím Centra akcí. Funguje jako kolektor nebo jednotné místo, kde lze zjistit stav a nastavit část konfigurace jednotlivých funkcí. Další informace najdete v dokumentaci k programu [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).

#### <a name="windows-defender-security-center-app-and-notifications"></a>Aplikace a oznámení Centra zabezpečení v programu Windows Defender

Zablokujte přístup koncových uživatelů k různým oblastem aplikace Centrum zabezpečení v programu Windows Defender. Když se skryje nějaká část, zablokují se i související oznámení.

- **Ochrana před viry a hrozbami**
- **Výkon a stav zařízení**
- **Firewall a ochrana sítě**
- **Řízení aplikací a prohlížečů**
- **Možnosti pro rodinu**
- **Oznámení ze zobrazených oblastí aplikace**: Zvolte si, která oznámení se budou zobrazovat koncovým uživatelům. Mezi nezávažná oznámení patří souhrny aktivity Antivirové ochrany v programu Windows Defender, včetně oznámení o dokončení kontrol. Všechna další oznámení se považují za závažná.

#### <a name="it-contact-information"></a>Informace o kontaktu IT

Zadejte kontaktní informace oddělení IT, které se zobrazí v aplikaci Security Center v programu Windows Defender a v oznámeních aplikací. Můžete zvolit možnost **Zobrazovat v aplikacích a v oznámeních**, **Zobrazovat jen v aplikaci**, **Zobrazovat jen v oznámeních** nebo **Nezobrazovat**. Zadejte **Název organizace IT** a aspoň jednu z následujících možností kontaktu:

- **Telefonní číslo nebo skypové jméno oddělení IT**
- **E-mailová adresa IT oddělení**
- **Adresa URL webu podpory IT**

## <a name="local-device-security-options"></a>Možnosti místního zabezpečení zařízení

Podporováno v následujících edicích Windows 10:
 
- Domů
- Professional
- Do zaměstnání
- Enterprise
- Vzdělávání

Pomocí těchto možností můžete konfigurovat nastavení místního zabezpečení na zařízeních s Windows 10.

### <a name="accounts"></a>Účty

- **Přidat nové účty Microsoft**: **Blokovat** zabrání uživatelům v přidávání nových účtů Microsoft na dané zařízení. **Nenakonfigurováno** (výchozí) umožní uživatelům na daném zařízení účty Microsoft používat.
- **Vzdálené přihlášení bez hesla**: **Povolit** umožní místním účtům, které nejsou chráněné heslem, přihlásit se pomocí klávesnice daného zařízení. **Nenakonfigurováno** (výchozí) umožní místním účtům, které nejsou chráněné heslem, přihlásit se z jiných umístění než z fyzického zařízení.

#### <a name="admin"></a>Správce

- **Místní účet správce**: **Povolit** místní účet správce zapne. **Nenakonfigurováno** (výchozí) místní účet správce zakáže.
- **Přejmenovat účet správce**: Můžete definovat jiný název účtu, který se má přidružit k identifikátoru zabezpečení (SID) pro účet správce.

#### <a name="guest"></a>Guest

- **Účet Guest**: **Povolit** místní účet Guest zapne. **Nenakonfigurováno** (výchozí) místní účet Guest zakáže.
- **Přejmenovat účet hosta**: Můžete definovat jiný název účtu, který se má přidružit k identifikátoru zabezpečení (SID) pro účet Guest.

### <a name="devices"></a>Zařízení

- **Vyjmout zařízení z dokovací stanice bez přihlášení**: **Blokovat** umožní uživatelům stisknout fyzické tlačítko pro vyjmutí zařízení bez nutnosti přihlášení. **Nenakonfigurováno** (výchozí) bude vyžadovat přihlášení k zařízení, abyste získali oprávnění zařízení vyjmout.
- **Instalace ovladače tiskárny pro sdílené tiskárny**: **Povolit** umožní instalaci ovladačů tiskárny v rámci připojení ke sdílené tiskárně každému uživateli. **Nenakonfigurováno** (výchozí) umožní instalaci ovladačů tiskárny v rámci připojení ke sdílené tiskárně pouze správcům.
- **Omezit přístup k jednotce CD-ROM na místního aktivního uživatele**: **Povolit** umožní použití médií CD-ROM pouze interaktivně přihlášenému uživateli. Pokud je tato zásada povolená a nikdo není interaktivně přihlášený, je možné získat k jednotce CD-ROM přístup přes síť. **Nenakonfigurováno** (výchozí) umožní přístup k jednotce CD-ROM každému.
- **Formátovat a vysouvat vyměnitelná média**: Můžete definovat, kdo může formátovat a vysouvat vyměnitelná média NTFS:
  - **Není nakonfigurováno**
  - **Správci**
  - **Správci a členové skupiny Power Users**
  - **Správci a interaktivní uživatelé**

### <a name="interactive-logon"></a>Interaktivní přihlášení

- **Počet minut neaktivity na zamykací obrazovce, než se aktivuje šetřič obrazovky**: Zadejte maximální počet minut nečinnosti na přihlašovací obrazovce interaktivní relace plochy, než se spustí šetřič obrazovky.
- **K přihlášení vyžadovat CTRL + ALT + DEL**: **Povolit** nebude od uživatelů před přihlášením vyžadovat stisknutí CTRL + ALT + DEL. **Nenakonfigurováno** (výchozí) bude od uživatelů před přihlášením k systému Windows vyžadovat stisknutí CTRL + ALT + DEL.
- **Chování při vyjmutí čipové karty**: Určuje, co se stane, když se ze čtečky čipových karet vyjme čipová karta přihlášeného uživatele. Možnosti:

  - **Zamknout pracovní stanici**: Při vyjmutí čipové karty se pracovní stanice zamkne. Tato možnost umožňuje uživatelům opustit danou oblast, vzít si svoji čipovou kartu s sebou a přesto udržovat chráněnou relaci.
  - **Vynutit odhlášení**: Při vyjmutí čipové karty se uživatel automaticky odhlásí.
  - **Odpojit, pokud jde o relaci Vzdálené plochy**: Při vyjmutí čipové karty se relace odpojí bez odhlášení uživatele. Tato možnost umožňuje uživateli později vložením čipové karty obnovit danou relaci na tomto počítači nebo na jiném počítači se čtečkou čipových karet, aniž by se musel znovu přihlašovat. Pokud je relace místní, funguje tato zásada stejně jako možnost Zamknout pracovní stanici.

    Další podrobnosti nabízí [možnosti LocalPoliciesSecurity](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior).

#### <a name="display"></a>Zobrazit

- **Informace o uživateli na zamykací obrazovce**: Můžete konfigurovat informace o uživateli, které se zobrazí, když je relace uzamčená. Pokud tato možnost není nakonfigurovaná, zobrazí se zobrazované jméno uživatele, doména a uživatelské jméno.
  - **Není nakonfigurováno**
  - **Zobrazované jméno uživatele, doména a uživatelské jméno**
  - **Jen zobrazované jméno uživatel**
  - **Nezobrazovat informace o uživateli**
- **Skrýt naposledy přihlášeného uživatele**: **Povolit** uživatelské jméno skryje. **Nenakonfigurováno** (výchozí) uživatelské jméno zobrazí.
- **Skrýt uživatelské jméno při přihlašování**: **Povolit** uživatelské jméno skryje. **Nenakonfigurováno** (výchozí) uživatelské jméno zobrazí.
- **Nadpis zprávy přihlášení**: Nastavte nadpis zprávy pro přihlašující se uživatele.
- **Text zprávy přihlášení**: Nastavte text zprávy pro přihlašující se uživatele.

### <a name="network-access-and-security"></a>Přístup k síti a zabezpečení

- **Anonymní přístup k pojmenovaným kanálům a sdíleným složkám**: Možnost **Nenakonfigurováno** (výchozí) omezuje anonymní přístup k nastavením sdílené složky a pojmenovaného kanálu. Platí pro nastavení, ke kterým se dá přistupovat anonymně.
- **Anonymní výčty účtů SAM**: Možnost **Povolit** umožňuje anonymním uživatelům vytvořit výčet účtů SAM. Windows umožňuje anonymním uživatelům vytvořit výčet názvů účtů domén a síťových sdílených složek.
- **Anonymní výčty účtů SAM a sdílených síťových složek**: Možnost **Nenakonfigurováno** (výchozí) určuje, že anonymní uživatelé můžou vytvořit výčet názvů účtů domén a síťových sdílených složek. Pokud chcete zabránit anonymním výčtům účtů SAM a sdílených síťových složek, nastavte možnost **Blokovat**.
- **Ukládání hodnoty hash LAN Manageru při změně hesla**: Možnost **Povolit** určuje, že při další změně hesla se uloží hodnota hash LAN Manageru (LM) pro nové heslo. Pokud je nastavená možnost **Nenakonfigurováno** (výchozí), hodnota hash se neuloží.
- **Žádosti ověření PKU2U**: Možnost **Blokovat** zabraňuje, aby žádosti ověření PKU2U na toto zařízení používaly online identity. Možnost **Nenakonfigurováno** (výchozí) tyto žádosti povoluje.
- **Omezit vzdálená připojení RPC k SAM**: Možnost **Povolit** určuje, že výchozí řetězec jazyka SDDL (Security Descriptor Definition Language) může uživatelům a skupinám odepřít vzdálená volání SAM. Možnost **Nenakonfigurováno** (výchozí) určuje, že výchozí řetězec jazyka SDDL (Security Descriptor Definition Language) může uživatelům a skupinám povolit vzdálená volání SAM.
  - **Popisovač zabezpečení**

### <a name="recovery-console-and-shutdown"></a>Konzola pro zotavení a vypnutí

- **Při vypínání vymazat stránkovací soubor virtuální paměti**: **Povolit** vymaže stránkovací soubor virtuální paměti, když se zařízení vypne. **Nenakonfigurováno** virtuální paměť nevymaže.
- **Vypnutí bez přihlášení**: **Blokovat** skryje možnost vypnutí na přihlašovací obrazovce systému Windows. Uživatelé se musí k zařízení přihlásit, aby ho mohli vypnout. **Nenakonfigurováno** (výchozí) umožňuje uživatelům z přihlašovací obrazovky systému Windows zařízení vypnout.

### <a name="user-account-control"></a>Řízení uživatelských účtů

- **Integrita UIA bez zabezpečeného umístění**: **Povolit** umožní spuštění aplikací v zabezpečených umístěních v systému souborů pouze s integritou UIAccess. **Nenakonfigurováno** (výchozí) umožní spuštění aplikací s integritou UIAccess i v nezabezpečených umístěních v systému souborů.
- **Virtualizovat chyby zápisu souboru a registru do umístění podle uživatele**: **Blokovat** přesměruje za běhu chyby zápisu aplikace do definovaných umístění uživatele pro systém souborů a registr. **Nenakonfigurováno** (výchozí) nechá aplikace, které zapisují data do chráněných umístění, selhat.
- **Zvýšit oprávnění jen spustitelným souborům, které se podepsaly a ověřily**: **Povolit** vynutí ověření cesty certifikace infrastruktury veřejných klíčů spustitelného souboru, než se bude moct spustit. **Nenakonfigurováno** (výchozí) nebude vynucovat ověření cesty certifikace infrastruktury veřejných klíčů, než se bude moct spustitelný soubor spustit.

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
- **Směrovat výzvy ke zvýšení úrovně oprávnění na interaktivní relaci plochy uživatele**: **Povolit** umožní všem žádostem o zvýšení oprávnění přejít na interaktivní relaci plochy uživatele místo zabezpečené plochy. Použijí se všechna nastavení zásad chování výzev pro správce a standardní uživatele. **Nenakonfigurováno** (výchozí) vynutí přechod všech žádostí o zvýšení oprávnění na zabezpečenou plochu (bez ohledu na všechna nastavení zásad chování výzev pro správce a standardní uživatele).
- **Výzva ke zvýšení úrovně oprávnění pro instalace aplikací**: **Blokovat** zakáže rozpoznání a výzvy ke zvýšení úrovně instalačních balíčků aplikací. **Nenakonfigurováno** (výchozí) bude uživatele vyzývat k zadání přihlašovacích údajů správce, když instalační balíček aplikace vyžaduje zvýšená oprávnění.
- **Výzva ke zvýšení oprávnění UIA bez zabezpečené plochy**: **Povolit** umožní aplikacím UIAccess zobrazovat výzvy ke zvýšení úrovně oprávnění bez použití zabezpečené plochy. **Nenakonfigurováno** (výchozí) bude pro výzvy ke zvýšení úrovně oprávnění používat zabezpečenou plochu.

#### <a name="admin-approval-mode-settings"></a>Nastavení režimu schválení správcem

- **Režim schválení správcem pro předdefinovaný účet Administrator**: **Povolit** umožní předdefinovanému účtu správce používat režim schválení správcem. Všechny operace vyžadující zvýšení oprávnění zobrazí uživateli výzvu ke schválení operace. **Nenakonfigurováno** (výchozí) spustí všechny aplikace s plnými oprávněními správce.
- **Spustit všechny správce v režimu schválení správcem**: **Blokovat** zakáže režim schválení správcem a všechna nastavení zásad řízení uživatelských účtů. **Nenakonfigurováno** (výchozí) režim schválení správcem povolí.

### <a name="microsoft-network-client"></a>Microsoft Network Client

- **Digitálně podepisovat komunikaci (pokud server souhlasí)**: Určuje, jestli klient SMB vyjednává podepisování paketů. Když je tato možnost **nenakonfigurovaná** nebo povolená (výchozí), klient sítě Microsoft požádá server o podepisování paketů SMB při nastavení relace. Pokud je na serveru podepisování paketů povolené, podepisování paketů se vyjedná. Když je tato možnost **zakázaná**, klient SMB podepisování paketů nikdy vyjednávat nebude.
- **Posílat nešifrovaná hesla serverům SMB třetích stran**: **Povolit** umožní přesměrovači SMB (Server Message Block) posílat hesla ve formátu prostého textu serverům SMB třetích stran, které nepodporují šifrování hesel při ověřování. **Nenakonfigurováno** (výchozí) hesla šifruje.

### <a name="microsoft-network-server"></a>Server sítě Microsoft

- **Digitálně podepisovat komunikaci (pokud klient souhlasí)**: Určuje, jestli server SMB vyjednává podepisování paketů SMB s klienty, kteří to požadují. Když je tato možnost **povolená**, server sítě Microsoft vyjedná podepisování paketů SMB podle požadavku klienta. To znamená, že pokud je v klientovi podepisování paketů povolené, podepisování paketů se vyjedná. Když je tato možnost **nenakonfigurovaná** nebo zakázaná (výchozí), klient SMB podepisování paketů nikdy vyjednávat nebude.
- **Digitálně podepisovat komunikaci (vždy)**: Určuje, jestli komponenta serveru SMB požaduje podepisování paketů. Když je tato možnost **povolená**, nebude server sítě Microsoft s klientem sítě Microsoft komunikovat, pokud tento klient nesouhlasí s podepisováním paketů SMB. Když je tato možnost **nenakonfigurovaná** nebo zakázaná (výchozí), podepisování paketů SMB mezi klientem a serverem se vyjedná.

## <a name="next-steps"></a>Další kroky

Pokud chcete tento profil přiřadit ke skupinám, přečtěte si článek [Přiřazení profilů zařízení](device-profile-assign.md).
