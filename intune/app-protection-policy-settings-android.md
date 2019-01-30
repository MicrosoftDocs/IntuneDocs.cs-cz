---
title: Nastavení zásad ochrany aplikací pro Android | Microsoft Intune
titlesuffix: Microsoft Intune
description: Toto téma popisuje nastavení zásad ochrany aplikací pro zařízení s Androidem.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 1/28/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9e9ef9f5-1215-4df1-b690-6b21a5a631f8
ms.reviewer: andcerat
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 08848853a70d0fbdabeb123960f36dc19478e6c2
ms.sourcegitcommit: 0142020a7cd75348c6367facf072ed94238e667f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2019
ms.locfileid: "55230048"
---
# <a name="android-app-protection-policy-settings-in-microsoft-intune"></a>Nastavení zásad ochrany aplikací pro Android v Microsoft Intune
Tento článek popisuje nastavení zásad ochrany aplikací pro zařízení s Androidem. Popsané nastavení zásad se dá [nakonfigurovat](app-protection-policies.md) pro zásady ochrany aplikací v okně **Nastavení** na portálu Azure Portal.
Existují tři kategorie nastavení zásad: nastavení ochrany dat, požadavky na přístup a podmíněného spuštění. Termín *aplikace spravované podle zásad* v tomto článku označuje aplikace, které mají nakonfigurované zásady ochrany aplikací.

##  <a name="data-protection"></a>Ochrana dat 
### <a name="data-transfer"></a>Přenos dat
| Nastavení | Způsob použití | Výchozí hodnota |
|------|------|------|
| **Zálohování dat organizace pro Android do služeb zálohování** | Vyberte **bloku** k této aplikaci zabránit v zálohování pracovních nebo školních dat [Android Backup Service](https://developer.android.com/google/backup/index.html).<br><br> Vyberte **povolit** chcete této aplikaci k zálohování pracovních nebo školních dat povolit.| **Povoleno** |
| **Odeslání dat organizace do jiných aplikací** | Určete, jaké aplikace můžou přijímat data z této aplikace: <ul><li> **Aplikace spravované podle zásad**: Povolíte přenos jenom do jiných aplikací spravovaných pomocí zásad.</li> <li>**Všechny aplikace**: Povolíte přenos do všech aplikací. </li> <li>**Žádný**: Nepovolovat přenos dat do žádné aplikace, včetně jiných aplikací spravovaných pomocí zásad.</li></ul> <p>U některých aplikací a služeb, které mají výjimku, může být v Intune standardně povolený přenos dat. Pokud potřebujete povolit přenos dat do aplikace, která nepodporuje zásady ochrany aplikací Intune, můžete vytvořit vlastní výjimky. Další informace najdete v tématu [výjimky přenosu dat](#Data-transfer-exemptions).<p>Tato zásada může platit také pro odkazy na aplikace pro Android.  Spravuje obecné webové odkazy **otevřete aplikaci odkazy v aplikaci Intune Managed Browser** nastavení zásad.<p>**Poznámka:** *Intune aktuálně nepodporuje funkci Android Instant Apps. Intune jakékoli datové připojení k aplikaci nebo z aplikace zablokuje. Další informace najdete v tématu [Android Instant Apps](https://developer.android.com/topic/instant-apps/index.html) v dokumentaci pro vývojáře Androidu.*</p>| **Všechny aplikace** | 
|<ul><ui> **Vyberte aplikace, které se mají vyloučit** | Tato možnost je k dispozici, když vyberete *aplikace spravované podle zásad* pro možnost předchozí. | |
| **Přijímat data z jiných aplikací** | Určete, jaké aplikace můžou převádět data do této aplikace: <ul><li>**Aplikace spravované podle zásad**: Povolíte přenos jenom z ostatních aplikací spravovaných zásadou.</li><li>**Všechny aplikace**: Povolíte přenos dat ze žádné aplikace.</li><li>**Žádný**: Nepovolovat přenos dat ze žádné aplikace, včetně jiných aplikací spravovaných pomocí zásad. </li></ul> <p>Z některých aplikací a služeb, které mají výjimku, může Intune povolit přenos dat. Úplný seznam takových aplikací a služeb najdete v části [Výjimky přenosu dat](#data-transfer-exemptions). | **Všechny aplikace** |
| **Ukládejte si kopie dat organizace** | Zvolte **bloku** zakážete použití možnosti Uložit jako v této aplikaci. Zvolte **povolit** Pokud chcete povolit použití možnosti Uložit jako. **Poznámka:** *Toto nastavení je podporováno pro aplikaci Microsoft Excel, OneNote, PowerPoint a Word. Může být také podporován třetích stran a obchodní aplikace.*| **Povoleno** |  
|<ul><ui> **Uživateli umožňují uložit kopie vybraných služeb** |Uživatelé můžou k ukládání používat vybrané služby (OneDrive pro firmy, SharePoint a místní úložiště). Všechny ostatní služby budou blokované.  | **Vybraná 0** |
| **Omezit operace vyjmutí, kopírování a vkládání mezi jinými aplikacemi** | Určete, kdy se můžou v této aplikaci použít akce vyjmutí, kopírování a vložení. Vybírejte z těchto možností: <ul><li>**Zablokuje**:  Nepovoluje akce vyjmutí, kopírování a vložení mezi touto aplikací a jakoukoli jinou aplikaci.</li><li>**Aplikace spravované podle zásad**: Povolit akce vyjmutí, kopírování a vložení mezi touto a jinými aplikacemi spravovanými zásadami.</li><li>**S vložením spravované podle zásad**: Povoluje vyjmutí a kopírování mezi touto a jinými aplikacemi spravovanými zásadami. Povoluje vložení dat z jakékoliv aplikace do této aplikace.</li><li>**Libovolná aplikace**: Žádná omezení pro vyjmutí, kopírování a vložení do a z této aplikace. | **Libovolná aplikace** |
| **Snímek obrazovky a asistenta Google** | Vyberte **zakázat** chcete zablokovat zachytávání obrazovky a **Android Assistant** funkce zařízení při použití této aplikace. Výběr **zakázat** také rozostření aplikace rozmaže obrázek náhledu, při použití této aplikace pomocí pracovního nebo školního účtu.| **Povolit** |
  
### <a name="encryption"></a>Šifrování
| Nastavení | Způsob použití | Výchozí hodnota |
|------|------|------|
| **Šifrování dat organizace** | Zvolte **vyžadují** povolit šifrování pracovní nebo školní data v této aplikaci. Intune používá OpenSSL, 256bitového schéma šifrování AES systém Android Keystore k zabezpečenému šifrování dat aplikace. Data jsou mezi vstupně-výstupními úlohami souborů synchronně šifrovaná. Obsah v úložišti zařízení je zašifrovaný vždycky. Sady SDK bude dále poskytovat podpora 128bitových klíčů z důvodu kompatibility s obsahem a aplikace, které používají starší verze sady SDK. <br><br> Metoda šifrování **nemá** certifikaci FIPS 140-2.     |  **vyžadovat**|  



### <a name="functionality"></a>Funkce
| Nastavení | Způsob použití | Výchozí hodnota |
|------|------|------|
| **Synchronizace aplikace s využitím aplikací nativních kontaktů** | Zvolte **zakázat** nechcete, aby aplikace ukládala data do nativní aplikace kontakty na zařízení. Pokud se rozhodnete **povolit**, může aplikace ukládat data do nativní aplikace kontakty na zařízení. <br><br>Když budete z aplikace selektivně mazat pracovní nebo školní data, odeberou se kontakty synchronizované přímo z aplikace do nativní aplikace Kontakty. Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. To se v současné době týká jenom aplikace Microsoft Outlook. | **Povolit** |
| **Tisk dat organizace** | Zvolte **zakázat** zabránit tisk pracovních nebo školních dat aplikace. | **Povolit** |
|**Sdílená složka webového obsahu pomocí zásad spravovaného prohlížeče** | Určete, jakým způsobem se otevírá webový obsah (odkazy http/https) z aplikací spravovaných zásadami. Vybírejte z těchto možností:<ul><li>**Vyžadovat**: Povolit webový obsah, který otevíral jenom ve zásady spravovaného prohlížeče.</li><li>**Není nakonfigurováno**: Povolit webové odkazy v jakékoli aplikaci </li></ul><br><br> Pokud ke správě zařízení používáte Intune, přečtěte si téma [Správa přístupu k internetu pomocí prohlížeče chráněného zásadami Microsoft Intune](app-configuration-managed-browser.md).<br><br>**Prohlížeče spravované zásadami**<br>Pokud nasadíte více prohlížečů spravovaných zásadami, spustí se jen jeden.  Jako první se spustí Intune Managed Browser a následně Microsoft Edge.  Pokud není nainstalovaný ani Intune Managed Browser ani Microsoft Edge, mohou si v Androidu koncoví uživatelé zvolit z jiných aplikací spravovaných zásadami, které podporují odkazy http/https.<p>Pokud se vyžaduje prohlížeč spravovaný zásadami, ale není nainstalovaný, budou koncoví uživatelé vyzváni k instalaci řešení Intune Managed Browser.<p>Pokud se vyžaduje prohlížeč spravovaný zásadami, jsou odkazy na aplikace pro Android spravované nastavením zásady **Povolit aplikaci posílat data do jiných aplikací**.<p>**Registrace zařízení v Intune**<br>Pokud ke správě zařízení používáte Intune, přečtěte si článek Správa přístupu k internetu pomocí zásad aplikace Managed Browser v Microsoft Intune. <p>**Microsoft Edge spravovaný zásadami**<br>Prohlížeč Microsoft Edge pro mobilní zařízení (iOS a Android) podporuje zásady ochrany aplikací Intune. Uživatelé, kteří se v aplikaci prohlížeče Microsoft Edge přihlásí svými podnikovými účty Azure AD, budou chráněni službou Intune. Prohlížeč Microsoft Edge integruje sadu MAM SDK a podporuje všechny její zásady ochrany dat kromě těchto:<br><ul><li>**Uložit – jako**: Prohlížeč Microsoft Edge neumožňuje uživateli přidat s přímým přístupem, v aplikaci připojení ke cloudovým poskytovatelé úložiště (jako je třeba OneDrive).</li><li>**Obraťte se na synchronizaci**: Prohlížeč Microsoft Edge se neukládá do seznamu nativních kontaktů.</li></ul><br>**Poznámka:** *Sada APP SDK nelze určit, zda je cílové aplikace prohlížeče. Na zařízeních s Androidem jsou povolené další aplikace spravovaného prohlížeče, podporující záměr http/https.* | **Není nakonfigurováno** |
| **Klávesnice třetích stran** | Vyberte **zakázat** zabránit používání klávesnice třetích stran ve spravovaných aplikacích. <br><br>Když tuto možnost povolíte, obdrží uživatel jednorázově zprávu o tom, že použití takových klávesnic je zablokované. Tato zpráva se zobrazí při první komunikaci uživatele s daty organizace vyžadující použití klávesnice. Pouze standardní klávesnice je k dispozici při použití spravovaných aplikací a všechny ostatní klávesnice je zakázaná. Toto nastavení nemá vliv na používání klávesnic třetích stran v nespravovaných aplikacích. | **Povolit** |



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
  | com.android.settings | Nastavení systému Android |
  | com.azure.authenticator | Aplikace Azure Authenticator, která je nutná k úspěšnému ověřování v mnoha situacích |
  | com.microsoft.windowsintune.companyportal | Intune Portál společnosti|

  ### <a name="conditional-exemptions"></a>Podmíněné výjimky
  Tyto aplikace můžou přenášet data do aplikací spravovaných službou Intune a z nich za určitých podmínek.

  |Název aplikace nebo služby | Popis | Podmínka výjimky|
  | ------ | ---- | --- |
  | com.android.chrome | Prohlížeč Google Chrome | Prohlížeč Chrome se používá pro některé komponenty WebView na Androidu 7.0+ a není nikdy skrytý. Tok dat do aplikace a z ní je ale vždy omezený.  |
  | com.skype.raider | Skype | Aplikace Skype je povolená jenom pro určité akce, jejichž výsledkem je telefonní hovor. |
  | com.android.providers.media | Poskytovatel multimediálního obsahu pro Android | Poskytovatel multimediálního obsahu je povolený jenom pro akci výběru vyzváněcího tónu. |
  | com.google.android.gms, com.google.android.gsf | Balíčky Služeb Google Play | Tyto balíčky jsou povolené pro akce Google Cloud Messaging, například pro nabízená oznámení. |

Další informace najdete v tématu [Výjimky zásad přenosu dat pro aplikace](app-protection-policies-exception.md).

##  <a name="access-requirements"></a>Požadavky na přístup

| Nastavení | Způsob použití | Výchozí hodnota |
|------|------|------|
| **Pro přístup kód PIN** | Vyberte **vyžadují** vyžadování PIN kódu pro použití této aplikace. Uživateli se zobrazí výzva k nastavení tohoto kódu PIN při prvním spuštění aplikace v pracovním nebo školním kontextu. <br><br> Sílu kódu PIN nakonfigurujete pomocí následujících nastavení:| **vyžadovat** |
|<ul><ui> **Zadejte PIN kód** | Nastavte požadavek pro typ čísel nebo hesel PIN kódy před přístupem k aplikaci, která má zásady ochrany aplikací. Číselná podoba vyžaduje jen číslice, zatímco heslo může být definované s minimálně 1 abecedním písmenem **nebo** s minimálně 1 speciálním znakem. <br><br>**Poznámka:** *Povolené speciální znaky zahrnují speciální znaky a symboly na Androidu anglické klávesnici.*| **Číselné** |
|<ul><ui>  **Jednoduchý kód PIN** |Vyberte **povolit** chcete uživatelům povolit používání jednoduchých posloupností v PIN kódu třeba *1234*, *1111*, *abcd* nebo *aaaa* . Vyberte **bloku** tak tomu, aby jednoduché posloupnosti používali. <br><br>**Poznámka:** *Pokud typ PIN kód je nastaven na přístupový kód a jednoduchý kód PIN je nastavena na možnost povolit, uživatel musí alespoň jedno písmeno **nebo** ve svém PIN kódu aspoň jeden speciální znak. Pokud typ PIN kód je nastaven na přístupový kód a jednoduchý kód PIN je nastavená na blok, uživatel musí alespoň jednu číslici **a** jedno písmeno **a** ve svém PIN kódu aspoň jeden speciální znak.* | **Povoleno** |
| <ul><ui> **Vyberte minimální délku PIN kódu** | Zadejte minimální počet číslic v pinu.  | **4** |
|<ul><ui> **Otisků prstů místo kódu PIN pro přístup (Android 6.0 +)** | Vyberte **povolit** umožňující uživateli umožňuje využít [ověřování pomocí otisku prstu](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) místo kódu PIN pro přístup k aplikaci. <br><br>**Poznámka:** *Tato funkce podporuje obecných ovládacích prvků pro biometrické na zařízeních s Androidem. Biometrická nastavení specifické pro výrobce OEM, jako například *Samsung Pass*, nejsou podporovány.* <br><br>V Androidu můžete nechat uživatele prokázat svoji identitu [ověřením otiskem prstu v Androidu](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) namísto PIN kódu. Když se uživatel pokusí použít tuto aplikaci se svým pracovním nebo školním účtem, zobrazí se výzva k zadání otisku prstu a uživatel nemusí zadávat PIN kód. <br><br> K vynucování zásad **Povolit otisk prstu místo PIN kódu** vyžadují pracovní profily Androidu registraci samostatného otisku prstu. Tyto zásady platí jenom pro aplikace spravované pomocí zásad, které jsou nainstalované v pracovním profilu Androidu. Až se registrací na Portálu společnosti vytvoří pracovní profil Androidu, musí se samostatný otisk prstu zaregistrovat na zařízení. Další informace o otiscích prstů pro pracovní profily Androidu najdete v článku o [uzamknutí pracovního profilu](https://support.google.com/work/android/answer/7029958). |**Povoleno** |
| <ul><ul><ui>**Přepsat otisků prstů s kódem PIN po vypršení časového limitu** |  Pokud je nastavena na **vyžadují**, kódu PIN řádku přepíše Touch ID výzvy po nečinnosti pro aplikaci *vypršení časového limitu* období můžete zadat.   | **vyžadovat** |
| <ul><ul><ui>**Časový limit (v minutách neaktivity)** | Zadejte v minutách, jak dlouho aplikaci může být neaktivní, před nahrazením výzvy Touch ID podle pokynů PIN kód.  <br><br>Tato hodnota časového limitu musí být větší než hodnota zadaná v rámci *znovu zkontrolovat požadavky na přístup po (v minutách neaktivity)*.| **30** |
|<ul><ui> **PIN reset Service po počet dnů** | Vyberte **Ano** budou muset uživatelé změnit PIN kód jejich aplikace po nastavené období času ve dnech. <br><br> Výchozí hodnota = **Ne** <br><br> Pokud je nastavena na *Ano*, pak můžete nakonfigurovat počet dní, než se. | **Ne**|
| <ul><ul><ui>**Počet dnů** | Když *PIN reset Service po počet dnů* je nastaven na hodnotu Ano, zadejte dobu před PIN kód vynulování je nezbytné. | **0** | 
|<ul><ui> **Aplikace PIN kód při nastavit PIN kód zařízení** | Pokud hodnotu **zakázat**, nastavit PIN kód aplikace PIN kód není nutný na MDM zaregistrovaná zařízení, která má zařízení.   | **Povolit** |
| **Přihlašovací údaje pro přístup k pracovnímu nebo školnímu účtu** | Zvolte **vyžadují** uživatel muset přihlásit pomocí svého pracovního nebo školního účtu namísto zadávání kódu PIN pro přístup k aplikaci. Pokud je nastavena na **vyžadují**a PIN kód nebo biometrické výzvy jsou zapnuté, podnikové přihlašovací údaje a buď PIN kód nebo biometrické výzvy se zobrazí. | **Nepožaduje se** |
| **Znovu zkontrolovat požadavky na přístup po (v minutách neaktivity)** | Nakonfigurujte počet minut nečinnosti, která musí uplynout, než aplikace vyžaduje, aby uživatel znovu zadat požadavky na přístup.  <br><br>**Poznámka:** *V Androidu kód PIN sdílí se všemi aplikacemi spravovanými Intune. Časovač kódu PIN se vynuluje, když se aplikace v zařízení přestane zobrazovat na popředí. Po dobu časového limitu definovaného tímto nastavením nemusí uživatel zadávat PIN kód u žádné aplikace spravované přes Intune, která svůj PIN kód sdílí.*| **30** |


> [!NOTE]  
> Další informace o tom, jak v Androidu fungují různá nastavení Intune App Protection nakonfigurovaná v části Přístup u stejné skupiny aplikací a uživatelů, najdete v článku věnovaném [častým otázkám k Intune MAM](mam-faq.md) a v článku [Selektivní vymazání dat pomocí akcí přístupu zásad ochrany aplikací v Intune](app-protection-policies-access-actions.md).


## <a name="conditional-launch"></a>Podmíněné spouštění
Pokud chcete ve svých zásadách ochrany přístupu nastavit bezpečnostní požadavky, které se týkají přihlašování, nakonfigurujte podmíněné spouštění. 

Výchozí nastavení obsahuje předem nakonfigurované hodnoty a akce. Některé nastavení můžete odstranit, třeba *Minimální verze operačního systému*. Z rozevíracího seznamu **Vyberte jednu možnost** můžete také vybrat další nastavení. 

| Nastavení | Způsob použití |  
|---------|------------| 
| **Maximální počet pokusů o zadání PIN kódu** | Zadejte počet pokusů, které uživatel bude mít k úspěšnému zadání PIN kódu před provedením nakonfigurované akce. Tento formát nastavení zásady podporuje kladné celé číslo. *Akce* zahrnují: <br><ul><li>**Resetovat PIN kód** – uživatel musí resetovat svůj PIN.</li></ul> <ul><li>**Vymazat data** – uživatelský účet, který je přidružený k aplikaci, se ze zařízení vymaže.  </li></ul> </li></ul> Výchozí hodnota = **5** |
| **Období odkladu pro offline režim** | Kolik minut můžou aplikace MAM běžet offline. Zadejte dobu (v minutách) před opakovaným zkontrolováním požadavků na přístup k aplikaci. *Akce* zahrnují: <br><ul><li>**Zablokovat přístup (minuty)** – kolik minut můžou aplikace MAM běžet offline. Zadejte dobu (v minutách) před opakovaným zkontrolováním požadavků na přístup k aplikaci. Aby mohla aplikace po uplynutí této doby dál běžet, vyžaduje ověření uživatele v Azure Active Directory (Azure AD). <br><br>Tento formát nastavení zásady podporuje kladné celé číslo. <br><br>Výchozí hodnota = **720** minut (12 hodin) </li></ul> <ul><li>**Vymazat data (dny)** – po kolika dnech (definovaných správcem) provozu offline bude aplikace vyžadovat, aby se uživatel připojil k síti a znovu se přihlásil. Pokud je ověření uživatele úspěšné, může ke svým datům dál přistupovat a doba v offline režimu se resetuje.  Pokud se ověření uživatele nezdaří, aplikace provede selektivní vymazání uživatelova účtu a dat. Další informace najdete v tématu [Jak z aplikací spravovaných pomocí Intune vymazat jenom firemní data](https://docs.microsoft.com/intune/apps-selective-wipe).</li></ul> Tento formát nastavení zásady podporuje kladné celé číslo. <br><br>  Výchozí hodnota = **90 dní** </li></ul> <br><br>  Tato položka se může zobrazit vícekrát. V takovém případě každá instance podporuje jinou akci. |   
| **Zařízení s jailbreakem nebo rootem** |U tohoto nastavení se nezadává žádná hodnota. *Akce* zahrnují: <br><ul><li>**Blokovat přístup** – brání spuštění aplikace na zařízeních s jailbreakem nebo rootem (která mají odblokovaný systém). Uživatel může aplikaci dále používat pro své osobní účely, ale pokud v ní chce pracovat s pracovními nebo školními daty, musí použít jiné zařízení.</li></ul> <ul><li>**Vymazat data** – uživatelský účet, který je přidružený k aplikaci, se ze zařízení vymaže.  </li></ul> |
| **Minimální verze operačního systému** | Zadejte minimální Android verzi operačního systému, který je potřeba tuto aplikaci používat. *Akce* zahrnují: <br><ul><li>**Upozornit** – pokud verze Androidu v zařízení nevyhovuje tomuto požadavku, zobrazí se uživateli oznámení. Toto oznámení je možné zavřít.  </li></ul> <ul><li>**Blokovat přístup** – pokud verze iOSu v zařízení nevyhovuje tomuto požadavku, bude uživatel zablokován.</li></ul> <ul><li>**Vymazat data** – uživatelský účet, který je přidružený k aplikaci, se ze zařízení vymaže.  </li></ul> </li></ul>Tento formát nastavení zásady podporuje vlastnosti major.minor, major.minor.build a major.minor.build.revision. |
| **Minimální verze aplikace** | Zadejte minimální verzi operačního systému. *Akce* zahrnují: <br><ul><li>**Upozornit** – pokud verze aplikace v zařízení nevyhovuje tomuto požadavku, zobrazí se uživateli oznámení. Toto oznámení je možné zavřít.</li></ul> <ul><li>**Blokovat přístup** – pokud verze aplikace v zařízení nevyhovuje tomuto požadavku, zablokuje se uživateli přístup. </li></ul> <ul><li>**Vymazat data** – uživatelský účet, který je přidružený k aplikaci, se ze zařízení vymaže. </li></ul> </li></ul> Vzhledem k tomu, že aplikace mívají často odlišná schémata verzí, vytvořte zásadu, ve které bude jedna minimální verze zacílená na jednu aplikaci (např. *Zásada verze Outlooku*).<br><br> Tato položka se může zobrazit vícekrát. V takovém případě každá instance podporuje jinou akci.<br><br> Tento formát nastavení zásady podporuje vlastnosti major.minor, major.minor.build a major.minor.build.revision.|
| **Minimální verze opravy** | Vyžaduje, aby na zařízení byla nainstalovaná minimální oprava zabezpečení Androidu vydaná Googlem.  <br><ul><li>**Upozornit** – pokud verze Androidu v zařízení nevyhovuje tomuto požadavku, zobrazí se uživateli oznámení. Toto oznámení je možné zavřít.  </li></ul> <ul><li>**Blokovat přístup** – pokud verze iOSu v zařízení nevyhovuje tomuto požadavku, bude uživatel zablokován.</li></ul> <ul><li>**Vymazat data** – uživatelský účet, který je přidružený k aplikaci, se ze zařízení vymaže.  </li></ul></li></ul> Nastavení zásady podporuje formát kalendářního data *RRRR-MM-DD*. |
| **Výrobci zařízení** | Zadejte výrobce zařízení, který je k používání aplikace povinný. *Akce* zahrnují: <br><ul><li>**Povolit zadané (blokovat nezadané)** – aplikaci můžou používat jenom zařízení, která odpovídají zadanému výrobci. Všechna ostatní zařízení se zablokují. </li></ul> <ul><li>**Povolit zadané (vymazat nezadané)** – uživatelský účet, který je přidružený k aplikaci, se ze zařízení vymaže. </li></ul> |
