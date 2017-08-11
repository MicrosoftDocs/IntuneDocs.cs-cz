---
title: "Nastavení zásad ochrany aplikací pro Android"
titleSuffix: Intune on Azure
description: "Toto téma popisuje nastavení zásad ochrany aplikací pro zařízení s Androidem."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 06/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9e9ef9f5-1215-4df1-b690-6b21a5a631f8
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a0da2e96e6e80672f666b8bbca160a1fc1515d1c
ms.sourcegitcommit: 2ee1e8248814d74cef80b609a8e43f59fa0b2618
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2017
---
# <a name="android-app-protection-policy-settings"></a>Nastavení zásad ochrany aplikací pro Android
Nastavení zásad popsané v tomto tématu se dá [nakonfigurovat](app-protection-policies.md) pro zásady ochrany aplikací v okně **Nastavení** na portálu Azure Portal.
Existují dvě kategorie nastavení zásad:nastavení přemístění dat a nastavení přístupu. *Aplikace spravované podle zásad* v tomto tématu označují aplikace, které mají nakonfigurované zásady ochrany aplikací.

##  <a name="data-relocation-settings"></a>Nastavení přemístění dat

| Nastavení | Způsob použití | Výchozí hodnoty |
|------|------|------|
| **Zakázat zálohování dat v zařízeních s Androidem** | Pokud chcete zabránit této aplikaci v zálohování pracovních nebo školních dat do služby **Android Backup Service**, zvolte [Ano](https://developer.android.com/google/backup/index.html). Pokud jí chcete zálohování pracovních nebo školních dat povolit, zvolte **Ne**.| Ano |
| **Povolit aplikaci přenos dat do ostatních aplikací** | Určete, jaké aplikace můžou přijímat data z této aplikace: <ul><li> **Aplikace spravované podle zásad:** Povoluje přenos jenom do jiných aplikací spravovaných podle zásad.</li> <li>**Všechny aplikace**: Povoluje přenos do všech aplikací. </li> <li>**Žádné:** Nepovoluje přenos dat do žádné aplikace, včetně ostatních aplikací spravovaných podle zásad.</li></ul> <p>Do některých aplikací a služeb, které mají výjimku, může Intune povolit přenos dat. Úplný seznam takových aplikací a služeb najdete v části [Výjimky přenosu dat](#Data-transfer-exemptions).| Všechny aplikace |
| **Povolit aplikaci, aby přijímala data z jiných aplikací** | Určete, jaké aplikace můžou převádět data do této aplikace: <ul><li>**Aplikace spravované podle zásad:** Povoluje přenos jenom z jiných aplikací spravovaných podle zásad.</li><li>**Všechny aplikace**: Povoluje přenos dat ze všech aplikací.</li><li>**Žádné:** Nepovoluje přenos dat z žádné aplikace, včetně ostatních aplikací spravovaných podle zásad. </li></ul> <p>Z některých aplikací a služeb, které mají výjimku, může Intune povolit přenos dat. Úplný seznam takových aplikací a služeb najdete v části [Výjimky přenosu dat](#Data-transfer-exemptions). | Všechny aplikace |
| **Zakázat možnost Uložit jako** | Pokud chcete v této aplikaci zakázat možnost Uložit jako, zvolte **Ano**. Pokud chcete povolit použití možnosti Uložit jako, vyberte **Ne**. <p><br>**Vyberte, do kterých služeb úložiště se můžou ukládat firemní data** <br>Uživatelé můžou ukládat data do vybraných služeb (OneDrive pro firmy, SharePoint a Místní úložiště). Všechny ostatní služby budou blokované.</p> | Ne <br><br> Vybráno: 0 |
| **Omezit vyjmutí, kopírování a vkládání v ostatních aplikacích** | Určete, kdy se můžou v této aplikaci použít akce vyjmutí, kopírování a vložení. Vybírejte z těchto možností: <ul><li>**Blokováno:** Nepovoluje akce vyjmutí, kopírování a vložení mezi touto a jakoukoliv jinou aplikací.</li><li>**Aplikace spravované podle zásad:** Povoluje operace vyjmutí, kopírování a vložení mezi touto aplikací a jinými aplikacemi spravovanými podle zásad.</li><li>**Aplikace s vložením spravované podle zásad:** Povoluje vyjmutí a kopírování mezi touto aplikací a jinými aplikacemi spravovanými podle zásad. Povoluje vložení dat z jakékoliv aplikace do této aplikace.</li><li>**Libovolná aplikace:** Operace vyjmutí, kopírování a vložení do a z této aplikace nejsou nijak omezené. | Libovolná aplikace |
|**Omezit webový obsah tak, aby se spouštěl v Managed Browseru** | Pokud chcete vynutit, aby se webové odkazy v aplikaci otevíraly v aplikaci Managed Browser, zvolte **Ano**. <br><br> U zařízení, která nejsou zaregistrovaná v Intune, se webové odkazy v aplikacích spravovaných podle zásad můžou otevírat jenom v aplikaci Managed Browser. <br><br> Pokud ke správě zařízení používáte Intune, přečtěte si téma [Správa přístupu k internetu pomocí zásad spravovaného prohlížeče v Microsoft Intune](app-configuration-managed-browser.md). | Ne |
| **Zašifrovat data aplikací** | Pokud chcete v této aplikaci povolit pro pracovní nebo školní data šifrování, zvolte **Ano**. Intune používá k zabezpečenému šifrování dat aplikace 128bitové schéma šifrování AES OpenSSL a systém Android Keystore. Data jsou mezi vstupně-výstupními úlohami souborů synchronně šifrovaná. Obsah v úložišti zařízení je zašifrovaný vždycky. <br><br> Metoda šifrování **nemá** certifikaci FIPS 140-2.  | Ano |
| **Zakázat synchronizaci kontaktů** | Pokud nechcete, aby aplikace ukládala data do nativní aplikace Kontakty na zařízení, zvolte **Ano**. Když zvolíte **Ne**, může aplikace ukládat data do nativní aplikace Kontakty na zařízení. <br><br>Když budete z aplikace selektivně mazat pracovní nebo školní data, odeberou se kontakty synchronizované přímo z aplikace do nativní aplikace Kontakty. Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. To se v současné době týká jenom aplikace Microsoft Outlook. | Ne |
| **Zakázat tisk** | Pokud chcete v aplikaci zakázat tisk pracovních nebo školních dat, zvolte **Ano**. | Ne |

  >[!NOTE]
  >Metoda šifrování pro nastavení **Zašifrovat data aplikací** **nemá** certifikaci FIPS 140-2.


  ## <a name="data-transfer-exemptions"></a>Výjimky přenosu dat

  U některých aplikací a služeb platformy, které mají výjimku, můžou zásady ochrany aplikací Intune povolit přenos dat. Například všechny aplikace s podporou Intune na Androidu musí mít možnost přenášet data do a z Převodu textu na řeč Google, aby se mohl nahlas číst text z obrazovky mobilního zařízení. Tento seznam se může měnit. Obsahuje služby a aplikace, které se považují za užitečné pro bezpečné a produktivní použití.

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



##  <a name="access-settings"></a>Nastavení přístupu

| Nastavení | Způsob použití | Výchozí hodnoty |
|------|------|------|
| **Vyžadovat pro přístup kód PIN** | Zvolte **Ano**, aby se k použití této aplikace vyžadoval kód PIN. Uživateli se zobrazí výzva k nastavení tohoto kódu PIN při prvním spuštění aplikace v pracovním nebo školním kontextu. Výchozí hodnota = **Ano**<br><br> Sílu kódu PIN nakonfigurujete pomocí následujících nastavení: <ul><li>**Počet pokusů před resetem PIN kódu:** Zadejte počet pokusů, které uživatel bude mít k úspěšnému zadání PINu, než bude nutné PIN resetovat. Výchozí hodnota = **5**</li><li> **Povolit jednoduchý kód PIN:** Pokud chcete uživatelům povolit používání jednoduchých posloupností v kódu PIN, třeba 1234 nebo 1111, zvolte **Ano**. V případě, že nechcete, aby jednoduché posloupnosti používali, zvolte **Ne**. Výchozí hodnota = **Ano** </li><li> **Délka kódu PIN:** Zadejte minimální počet číslic v PINu. Výchozí hodnota = **4** </li><li> **Povolit otisk prstu místo kódu PIN (Android 6.0+):** Pokud chcete uživateli ke zpřístupnění aplikace povolit, aby místo kódu PIN použil [ověření otiskem prstu](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication), zvolte **Ano**. Výchozí hodnota = **Ano**</li></ul> Na zařízeních se systémem Android můžete nechat uživatele prokázat svoji identitu [ověřením otiskem prstu v Androidu](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) namísto kódu PIN. Když se uživatel pokusí použít tuto aplikaci se svým pracovním nebo školním účtem, zobrazí se výzva k zadání otisku prstu a uživatel nemusí zadávat kód PIN. </li></ul>| Požadovat kód PIN: Ano <br><br> Počet pokusů před resetováním kódu PIN: 5 <br><br> Povolit jednoduchý PIN: Ano <br><br> Délka PINu: 4 <br><br> Povolit otisk prstu: Ano |
| **Vyžadovat podnikové přihlašovací údaje pro přístup** | Pokud chcete, aby se uživatel k získání přístupu k aplikaci přihlašoval pomocí svého pracovního nebo školního účtu namísto zadávání kódu PIN, zvolte **Ano**. Pokud nastavíte **Ano**, přepíše se tím požadavek na PIN nebo Touch ID.  | Ne |
| **Blokovat spuštění spravovaných aplikací na zařízeních s jailbreakem nebo rootem** |Pokud chcete zabránit spuštění této aplikace v zařízeních s jailbreakem nebo rootem, zvolte **Ano**. Uživatel bude moct dál používat tuto aplikaci pro své osobní účely, ale k práci s pracovními nebo školními daty v této aplikaci bude muset používat jiné zařízení. | Ano |
| **Znovu zkontrolovat požadavky na přístup po (minuty)** | Proveďte konfiguraci následujících nastavení: <ul><li>**Časový limit:** Toto je počet minut před opakovaným zkontrolováním požadavků na přístup k aplikaci (definovaným dříve v zásadách). Správce například v zásadách zapne kód PIN, uživatel otevře aplikaci MAM a musí zadat PIN. Při použití tohoto nastavení nemusí uživatel u žádné aplikace MAM zadávat PIN dalších **30 minut** (výchozí hodnota).</li><li>**Období odkladu pro offline režim:** Toto je počet minut, po které může aplikace MAM běžet offline. Zadejte dobu (v minutách) před opakovaným zkontrolováním požadavků na přístup k aplikaci. Výchozí hodnota = **720** minut (12 hodin) Aby mohla aplikace po uplynutí této doby dál běžet, bude vyžadovat ověření uživatele ve službě AAD.</li></ul>| Časový limit: 30 <br><br> Offline: 720 |
| **Doba v offline režimu (ve dnech) před vymazáním dat** | Po tomto počtu dnů (definovaném správcem) běhu v offline režimu provede aplikace sama selektivní vymazání. Je to stejné selektivní vymazání, jaké může vyvolat správce v pracovním postupu vymazání MAM. <br><br> | 90 dnů |
| **Blokovat snímek obrazovky a Android Assistant (Android 6.0+)** | Pokud chcete blokovat funkce zachytávání snímků obrazovky a **Android Assistant**, když zařízení používá tuto aplikaci, zvolte **Ano**. Možnost **Ano** navíc při používání této aplikace s pracovním nebo školním účtem rozmaže obrázek náhledu v přepínači aplikací. | Ne |
| **Zakázat PIN kód aplikace, když je PIN kód zařízení spravovaný** | Pokud chcete zakázat PIN kód aplikace, když bude na zaregistrovaném zařízení zjištěn zámek zařízení, zvolte **Ano**. | Ne |