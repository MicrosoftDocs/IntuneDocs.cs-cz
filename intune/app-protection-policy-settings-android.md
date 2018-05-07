---
title: Nastavení zásad ochrany aplikací pro Android
titlesuffix: Microsoft Intune
description: Toto téma popisuje nastavení zásad ochrany aplikací pro zařízení s Androidem.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 04/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9e9ef9f5-1215-4df1-b690-6b21a5a631f8
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c9c14363d9d00a9beecb5eac41966734687f8a93
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="android-app-protection-policy-settings-in-microsoft-intune"></a>Nastavení zásad ochrany aplikací pro Android v Microsoft Intune
Toto téma popisuje nastavení zásad ochrany aplikací pro zařízení s Androidem. Popsané nastavení zásad se dá [nakonfigurovat](app-protection-policies.md) pro zásady ochrany aplikací v okně **Nastavení** na portálu Azure Portal.
Existují dvě kategorie nastavení zásad:nastavení přemístění dat a nastavení přístupu. *Aplikace spravované podle zásad* v tomto tématu označují aplikace, které mají nakonfigurované zásady ochrany aplikací.

##  <a name="data-relocation-settings"></a>Nastavení přemístění dat

| Nastavení | Způsob použití | Výchozí hodnoty |
|------|------|------|
| **Zakázat zálohování dat v zařízeních s Androidem** | Pokud chcete zabránit této aplikaci v zálohování pracovních nebo školních dat do služby **Android Backup Service**, zvolte [Ano](https://developer.android.com/google/backup/index.html). Pokud jí chcete zálohování pracovních nebo školních dat povolit, zvolte **Ne**.| Ano |
| **Povolit aplikaci přenos dat do ostatních aplikací** | Určete, jaké aplikace můžou přijímat data z této aplikace: <ul><li> **Aplikace spravované podle zásad:** Povoluje přenos jenom do jiných aplikací spravovaných podle zásad.</li> <li>**Všechny aplikace**: Povoluje přenos do všech aplikací. </li> <li>**Žádné:** Nepovoluje přenos dat do žádné aplikace, včetně ostatních aplikací spravovaných podle zásad.</li></ul> <p>U některých aplikací a služeb, které mají výjimku, může být v Intune standardně povolený přenos dat. Pokud potřebujete povolit přenos dat do aplikace, která nepodporuje aplikaci v Intune, můžete také vytvořit vlastní výjimky. Další informace najdete v tématu [Výjimky přenosu dat](#Data-transfer-exemptions).<p>**Poznámka:** Intune momentálně nepodporuje funkci Android Instant Apps. Intune jakékoli datové připojení k aplikaci nebo z aplikace zablokuje.  Další informace najdete v dokumentaci pro vývojáře Androidu v části [Android Instant Apps](https://developer.android.com/topic/instant-apps/index.html).</p>| Všechny aplikace |
| **Povolit aplikaci, aby přijímala data z jiných aplikací** | Určete, jaké aplikace můžou převádět data do této aplikace: <ul><li>**Aplikace spravované podle zásad:** Povoluje přenos jenom z jiných aplikací spravovaných podle zásad.</li><li>**Všechny aplikace**: Povoluje přenos dat ze všech aplikací.</li><li>**Žádné:** Nepovoluje přenos dat z žádné aplikace, včetně ostatních aplikací spravovaných podle zásad. </li></ul> <p>Z některých aplikací a služeb, které mají výjimku, může Intune povolit přenos dat. Úplný seznam takových aplikací a služeb najdete v části [Výjimky přenosu dat](#Data-transfer-exemptions). | Všechny aplikace |
| **Zakázat možnost Uložit jako** | Pokud chcete v této aplikaci zakázat možnost Uložit jako, zvolte **Ano**. Pokud chcete povolit použití možnosti Uložit jako, vyberte **Ne**. <p><br>**Vyberte, do kterých služeb úložiště se můžou ukládat firemní data** <br>Uživatelé můžou ukládat data do vybraných služeb (OneDrive pro firmy, SharePoint a Místní úložiště). Všechny ostatní služby budou blokované.</p> | Ne <br><br> Vybráno: 0 |
| **Omezit vyjmutí, kopírování a vkládání v ostatních aplikacích** | Určete, kdy se můžou v této aplikaci použít akce vyjmutí, kopírování a vložení. Vybírejte z těchto možností: <ul><li>**Blokováno:** Nepovoluje akce vyjmutí, kopírování a vložení mezi touto a jakoukoliv jinou aplikací.</li><li>**Aplikace spravované podle zásad:** Povoluje operace vyjmutí, kopírování a vložení mezi touto aplikací a jinými aplikacemi spravovanými podle zásad.</li><li>**Aplikace s vložením spravované podle zásad:** Povoluje vyjmutí a kopírování mezi touto aplikací a jinými aplikacemi spravovanými podle zásad. Povoluje vložení dat z jakékoliv aplikace do této aplikace.</li><li>**Libovolná aplikace:** Operace vyjmutí, kopírování a vložení do a z této aplikace nejsou nijak omezené. | Libovolná aplikace |
|**Omezit webový obsah tak, aby se spouštěl v Managed Browseru** | Pokud chcete vynutit, aby se webové odkazy v aplikaci otevíraly v aplikaci Managed Browser, zvolte **Ano**. <br><br> U zařízení, která nejsou zaregistrovaná v Intune, se webové odkazy v aplikacích spravovaných podle zásad můžou otevírat jenom v aplikaci Managed Browser. <br><br> Pokud ke správě zařízení používáte Intune, přečtěte si téma [Správa přístupu k internetu pomocí zásad spravovaného prohlížeče v Microsoft Intune](app-configuration-managed-browser.md). | Ne |
| **Zašifrovat data aplikací** | Pokud chcete v této aplikaci povolit pro pracovní nebo školní data šifrování, zvolte **Ano**. Intune používá k zabezpečenému šifrování dat aplikace 128bitové schéma šifrování AES OpenSSL a systém Android Keystore. Data jsou mezi vstupně-výstupními úlohami souborů synchronně šifrovaná. Obsah v úložišti zařízení je zašifrovaný vždycky. <br><br> Metoda šifrování **nemá** certifikaci FIPS 140-2.  | Ano |
| **Zakázat šifrování aplikace, když je povoleno šifrování zařízení** | Pokud chcete zakázat šifrování aplikace pro interní úložiště aplikace, když je na zaregistrovaném zařízení zjištěno šifrování zařízení, zvolte **Ano**. <br><br>**Poznámka:** Intune může zjistit jenom registraci zařízení ve správě mobilních zařízení Intune. Externí úložiště aplikace bude i dál šifrované, aby k datům nemohly mít přístup nespravované aplikace. | Ano |
| **Zakázat synchronizaci kontaktů** | Pokud nechcete, aby aplikace ukládala data do nativní aplikace Kontakty na zařízení, zvolte **Ano**. Když zvolíte **Ne**, může aplikace ukládat data do nativní aplikace Kontakty na zařízení. <br><br>Když budete z aplikace selektivně mazat pracovní nebo školní data, odeberou se kontakty synchronizované přímo z aplikace do nativní aplikace Kontakty. Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. To se v současné době týká jenom aplikace Microsoft Outlook. | Ne |
| **Zakázat tisk** | Pokud chcete v aplikaci zakázat tisk pracovních nebo školních dat, zvolte **Ano**. | Ne |

  >[!NOTE]
  >Metoda šifrování pro nastavení **Zašifrovat data aplikací** **nemá** certifikaci FIPS 140-2.

  ## <a name="data-transfer-exemptions"></a>Výjimky přenosu dat

  U některých aplikací a služeb platformy, které mají výjimku, můžou zásady ochrany aplikací Intune povolit přenos dat. Všechny aplikace na Androidu spravované přes Intune například musí mít možnost přenášet data do a z Převodu textu na řeč Google, aby se mohl nahlas číst text z obrazovky mobilního zařízení. Tento seznam se může měnit. Obsahuje služby a aplikace, které se považují za užitečné pro bezpečné a produktivní použití.

  ### <a name="full-exemptions"></a>Úplné výjimky

  Tyto aplikace můžou bez omezení přenášet data do aplikací spravovaných službou Intune a z nich.

  |Název aplikace nebo služby | Popis |
  | ------ | ---- |
  | com.android.phone | Nativní telefonní aplikace
  | com.android.vending | Obchod Google Play |
  | com.android.documentsui | Výběr dokumentů pro Android|
  | com.google.android.webview | Třída [WebView](https://developer.android.com/reference/android/webkit/WebView.html), která je nutná pro mnoho aplikací včetně Outlooku |
  | com.android.webview |Třída [WebView](https://developer.android.com/reference/android/webkit/WebView.html), která je nutná pro mnoho aplikací včetně Outlooku|
  | com.google.android.tts | Převod textu na řeč Google |
  | com.android.providers.settings | Nastavení systému Android |
  | com.azure.authenticator | Aplikace Azure Authenticator, která je nutná k úspěšnému ověřování v mnoha situacích |
  | com.microsoft.windowsintune.companyportal | Intune Portál společnosti|

  ### <a name="conditional-exemptions"></a>Podmíněné výjimky
  Tyto aplikace můžou přenášet data do aplikací spravovaných službou Intune a z nich za určitých podmínek.

  |Název aplikace nebo služby | Popis | Podmínka výjimky|
  | ------ | ---- | --- |
  | com.android.chrome | Prohlížeč Google Chrome | Prohlížeč Chrome se používá pro některé komponenty WebView na Androidu 7.0+ a není nikdy skrytý. Tok dat do aplikace a z ní je ale vždy omezený.
  | com.skype.raider | Skype | Aplikace Skype je povolená jenom pro určité akce, jejichž výsledkem je telefonní hovor. |
  | com.android.providers.media | Poskytovatel multimediálního obsahu pro Android | Poskytovatel multimediálního obsahu je povolený jenom pro akci výběru vyzváněcího tónu. |
  | com.google.android.gms, com.google.android.gsf | Balíčky Služeb Google Play | Tyto balíčky jsou povolené pro akce Google Cloud Messaging, například pro nabízená oznámení. |

Další informace najdete v tématu [Výjimky zásad přenosu dat pro aplikace](app-protection-policies-exception.md).

##  <a name="access-settings"></a>Nastavení přístupu

| Nastavení | Způsob použití | Výchozí hodnoty |
|------|------|------|
| **Vyžadovat pro přístup kód PIN** | Zvolte **Ano**, aby se k použití této aplikace vyžadoval kód PIN. Uživateli se zobrazí výzva k nastavení tohoto kódu PIN při prvním spuštění aplikace v pracovním nebo školním kontextu. Výchozí hodnota = **Ano**<br><br> Sílu kódu PIN nakonfigurujete pomocí následujících nastavení: <ul><li>**Vyberte typ**: Nastavte požadavek na PIN kódy, které můžou mít podobu čísel nebo hesel a slouží pro přístup k aplikacím, které používají zásady ochrany aplikací. Číselná podoba vyžaduje jen číslice, zatímco heslo může být definované s minimálně 1 abecedním písmenem **nebo** s minimálně 1 speciálním znakem. <br><br> **Poznámka:** Povolené speciální znaky zahrnují speciální znaky a symboly na anglické klávesnici pro Android. Výchozí hodnota = **Čísla**</li><br><li>**Počet pokusů před resetem PIN kódu:** Zadejte počet pokusů, které uživatel bude mít k úspěšnému zadání PINu, než bude nutné PIN resetovat. Výchozí hodnota = **5**</li><li> **Povolit jednoduchý PIN kód**: Pokud chcete uživatelům povolit používání jednoduchých posloupností v PIN kódu, třeba 1234, 1111, abcd nebo aaaa, zvolte **Ano**. V případě, že nechcete, aby jednoduché posloupnosti používali, zvolte **Ne**. <br><br>**Poznámka:** Pokud je nakonfigurovaný PIN kód typu heslo a možnost Povolit jednoduchý PIN kód je nastavená na Ano, uživatel musí mít ve svém PIN kódu alespoň 1 písmeno **nebo** alespoň 1 speciální znak. Pokud je nakonfigurovaný PIN kód typu heslo a možnost Povolit jednoduchý PIN kód je nastavená na Ne, uživatel musí mít ve svém PIN kódu alespoň 1 číslici **a** 1 písmeno **a** alespoň 1 speciální znak. Výchozí hodnota = **Ano** </li><br><li> **Délka kódu PIN:** Zadejte minimální počet číslic v PINu. Výchozí hodnota = **4**</li><li> **Povolit otisk prstu místo kódu PIN (Android 6.0+):** Pokud chcete uživateli ke zpřístupnění aplikace povolit, aby místo kódu PIN použil [ověření otiskem prstu](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication), zvolte **Ano**. Výchozí hodnota = **Ano** <br><br>**Poznámka**: Aby se vynucovaly zásady **Povolit otisk prstu místo kódu PIN**, Android for Work vyžaduje registraci samostatného otisku prstu. Tyto zásady budou platit jen pro aplikace spravované pomocí zásad nainstalované v profilu Androidu for Work. Až se registrací na Portálu společnosti vytvoří spravovaný profil Android for Work, musí se samostatný otisk prstu zaregistrovat na zařízení. Další informace o otiscích prstů pracovních profilů v Androidu for Work najdete v článku o [uzamknutí pracovního profilu](https://support.google.com/work/android/answer/7029958).</li></ul> Na zařízeních se systémem Android můžete nechat uživatele prokázat svoji identitu [ověřením otiskem prstu v Androidu](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) namísto kódu PIN. Když se uživatel pokusí použít tuto aplikaci se svým pracovním nebo školním účtem, zobrazí se výzva k zadání otisku prstu a uživatel nemusí zadávat kód PIN. </li></ul>| Požadovat kód PIN: Ano <br><br> Počet pokusů před resetováním kódu PIN: 5 <br><br> Povolit jednoduchý PIN: Ano <br><br> Délka PINu: 4 <br><br> Povolit otisk prstu: Ano |
| **Vyžadovat podnikové přihlašovací údaje pro přístup** | Pokud chcete, aby se uživatel k získání přístupu k aplikaci přihlašoval pomocí svého pracovního nebo školního účtu namísto zadávání kódu PIN, zvolte **Ano**. Pokud nastavíte **Ano**, přepíše se tím požadavek na PIN nebo Touch ID.  | Ne |
| **Blokovat spuštění spravovaných aplikací na zařízeních s jailbreakem nebo rootem** |Pokud chcete zabránit spuštění této aplikace v zařízeních s jailbreakem nebo rootem, zvolte **Ano**. Uživatel bude moct dál používat tuto aplikaci pro své osobní účely, ale k práci s pracovními nebo školními daty v této aplikaci bude muset používat jiné zařízení. | Ano |
| **Znovu zkontrolovat požadavky na přístup po (minuty)** | Proveďte konfiguraci následujících nastavení: <ul><li>**Časový limit:** Počet minut před opakovanou kontrolou požadavků na přístup (které byly dříve definovány v zásadách). Správce například v zásadách zapne kód PIN a zablokuje zařízení s rootem. Uživatel otevře aplikaci spravovanou přes Intune, musí zadat kód PIN a musí aplikaci používat na zařízení bez rootu. Při použití tohoto nastavení nemusí uživatel u žádné aplikace spravované přes Intune zadávat kód PIN ani podstupovat další kontrolu výskytu rootu dalších **30 minut** (výchozí hodnota). <br><br> **Poznámka:** Na Androidu se kód PIN sdílí mezi všemi aplikacemi spravovanými přes Intune. Časovač kódu PIN se vynuluje, když se aplikace v zařízení přestane zobrazovat na popředí. Po dobu časového limitu definovaného tímto nastavením nemusí uživatel zadávat kód PIN u žádné aplikace spravované přes Intune, která svůj kód PIN sdílí. <br><br> Tento formát nastavení zásady podporuje kladné celé číslo.<br></li><li>**Období odkladu pro offline režim:** Toto je počet minut, po které může aplikace MAM běžet offline. Zadejte dobu (v minutách) před opakovaným zkontrolováním požadavků na přístup k aplikaci. Výchozí hodnota = **720** minut (12 hodin) Aby mohla aplikace po uplynutí této doby dál běžet, bude vyžadovat ověření uživatele ve službě AAD.<br><br> Tento formát nastavení zásady podporuje kladné celé číslo.</li></ul>| Časový limit: 30 <br><br> Offline: 720 |
| **Doba v offline režimu (ve dnech) před vymazáním dat** | Po tomto počtu dnů (určeném správcem) spuštění v offline režimu bude aplikace vyžadovat, aby se uživatel připojil k síti a znovu provedl ověření. Pokud je ověření uživatele úspěšné, může ke svým datům dál přistupovat a doba v offline režimu se resetuje.  Pokud se ověření uživatele nezdaří, aplikace provede selektivní vymazání uživatelova účtu a dat.  Další informace o tom, která data se selektivním vymazáním odstraní, najdete v tématu [Jak z aplikací spravovaných pomocí Intune vymazat jenom firemní data](https://docs.microsoft.com/intune/apps-selective-wipe).<br><br> Tento formát nastavení zásady podporuje kladné celé číslo. | 90 dnů |
| **Blokovat snímek obrazovky a Android Assistant (Android 6.0+)** | Pokud chcete blokovat funkce zachytávání snímků obrazovky a **Android Assistant**, když zařízení používá tuto aplikaci, zvolte **Ano**. Možnost **Ano** navíc při používání této aplikace s pracovním nebo školním účtem rozmaže obrázek náhledu v přepínači aplikací. | Ne |
| **Zakázat PIN kód aplikace, když je PIN kód zařízení spravovaný** | Pokud chcete zakázat PIN kód aplikace, když bude na zaregistrovaném zařízení zjištěn zámek zařízení, zvolte **Ano**. | Ne |
| **Vyžadovat minimální verzi operačního systému Android** | Zvolte **Ano**, pokud k používání této aplikace vyžadujete minimální verzi operačního systému Android. Uživateli bude zablokován přístup, pokud verze Androidu v zařízení nesplňuje tento požadavek.<br><br> Tento formát nastavení zásady podporuje vlastnosti major.minor, major.minor.build a major.minor.build.revision.| Ne |
| **Vyžadovat minimální verzi operačního systému Android (jenom upozornění)** | Zvolte **Ano**, pokud k používání této aplikace vyžadujete minimální verzi operačního systému Android. Uživateli se zobrazí oznámení, pokud verze Androidu v zařízení nesplňuje tento požadavek. Toto oznámení je možné zavřít.<br><br> Tento formát nastavení zásady podporuje vlastnosti major.minor, major.minor.build a major.minor.build.revision. | Ne |
| **Vyžadovat minimální verzi aplikace** | Zvolte **Ano**, pokud k používání této aplikace vyžadujete minimální verzi aplikace. Uživateli bude zablokován přístup, pokud verze aplikace v zařízení nesplňuje tento požadavek.<br><br>Vzhledem k tomu, že aplikace mívají často odlišná schémata verzí, vytvořte zásadu, ve které bude jedna minimální verze zacílená na jednu aplikaci (např. „Zásada verze Outlooku“). <br><br> Tento formát nastavení zásady podporuje vlastnosti major.minor, major.minor.build a major.minor.build.revision.| Ne |
| **Vyžadovat minimální verzi aplikace (jenom upozornění)** | Zvolte **Ano**, pokud k používání této aplikace doporučujete minimální verzi aplikace. Uživateli se zobrazí oznámení, pokud verze aplikace v zařízení nesplňuje tento požadavek. Toto oznámení je možné zavřít.<br><br>Vzhledem k tomu, že aplikace mívají často odlišná schémata verzí, vytvořte zásadu, ve které bude jedna minimální verze zacílená na jednu aplikaci (např. „Zásada verze Outlooku“). <br><br> Tento formát nastavení zásady podporuje vlastnosti major.minor, major.minor.build a major.minor.build.revision.| Ne |
| **Vyžadovat minimální verzi opravy Androidu** | Zvolte **Ano**, pokud požadujete minimální opravu zabezpečení Androidu vydanou Googlem. Uživateli bude zablokován přístup, pokud oprava zabezpečení Androidu v zařízení nesplňuje tento požadavek.<br><br> Tento formát nastavení zásad podporuje formát data RRRR-MM-DD. | Ne |
| **Vyžadovat minimální verzi opravy Androidu (jen upozornění)** | Zvolte **Ano**, pokud požadujete minimální opravu zabezpečení Androidu vydanou Googlem. Uživateli se zobrazí oznámení, pokud oprava zabezpečení Androidu v zařízení nesplňuje tento požadavek. Toto oznámení je možné zavřít.<br><br> Tento formát nastavení zásad podporuje formát data RRRR-MM-DD. | Ne |

> [!NOTE]
> Další informace o tom, jak v Androidu fungují různá nastavení Intune App Protection nakonfigurovaná v části Přístup u stejné skupiny aplikací a uživatelů, najdete v tématu [Nejčastější dotazy k Intune MAM](mam-faq.md).
