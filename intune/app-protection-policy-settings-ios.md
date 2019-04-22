---
title: Nastavení zásad ochrany aplikací pro iOS
titleSuffix: Microsoft Intune
description: Toto téma popisuje nastavení zásad (aplikace) ochrany aplikací iOS pro zařízení s Iosem.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/12/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f8b08f2-504c-4b38-bea2-b8a4ef0526b8
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 25fd89335d290cef5d100d58fddf7cbd56370393
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59895689"
---
#  <a name="ios-app-protection-policy-settings"></a>Nastavení zásad ochrany aplikací pro iOS
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek popisuje nastavení zásad ochrany aplikací pro zařízení s Iosem. Nastavení zásad, které jsou popsány dá [nakonfigurované](app-protection-policies.md) pro zásady ochrany aplikací na **nastavení** okna portálu Azure portal, když vytvoříte novou zásadu.

Existují tři kategorie nastavení zásad: *Přemístění dat*, *požadavky na přístup*, a *podmíněného spuštění*. Termín ***aplikace spravované podle zásad*** v tomto článku označuje aplikace, které mají nakonfigurované zásady ochrany aplikací.

##  <a name="data-protection"></a>Ochrana dat

### <a name="data-transfer"></a>Přenos dat
| Nastavení | Způsob použití | Výchozí hodnota |
|------|----------|-------|
| **Zálohování dat organizace k zálohám iTunes a Icloudu** | Vyberte **bloku** k této aplikaci zabránit v zálohování pracovních nebo školních dat na iTunes a iCloud. Vyberte **povolit** na tato aplikace bude k zálohování pracovních nebo školních dat na iTunes a iCloud. | **Povoleno**  |
| **Odeslání dat organizace do jiných aplikací** | Určete, jaké aplikace můžou přijímat data z této aplikace: <ul><li>**Všechny aplikace**: Povolíte přenos do všech aplikací.</li><li>**Žádný**: Nepovolovat přenos dat do žádné aplikace, včetně jiných aplikací spravovaných pomocí zásad.</li><li> **Aplikace spravované podle zásad**: Povolíte přenos jenom do jiných aplikací spravovaných pomocí zásad.</li><li>**Zásady spravovaných aplikací s operačním systémem sdílení**: Povolte jenom přenos dat do jiných aplikací spravovaných podle zásad, a také přenosy souborů do jiných aplikací spravováno pomocí MDM v zaregistrovaných zařízeních.<p><p>**Poznámka:** _**s operačním systémem sdílení aplikace spravované podle zásad** hodnota platí pro pouze zařízení v MDM zaregistrované. Pokud toto nastavení platí pro uživatele neregistrovaného zařízení, použije se chování, které odpovídá hodnotě **Aplikace spravované podle zásad**._<p><p></li><li>**Zásady spravovaných aplikací s Open-v a sdílet filtrování**: Povolit přenos jenom do jiných aplikací spravovaných podle zásad a dialogových oknech Filtr Open v a sdílet operačního systému, aby se zobrazily pouze aplikací spravovaných podle zásad.<p><p>**Poznámka:** _Konfigurace filtrování **Open-v a sdílet** dialogového okna, vyžaduje i aplikace, který funguje jako zdrojový soubor nebo dokument a aplikace, které můžete otevřít tento dokument nebo soubor měla sadu Intune SDK pro systém iOS verze 8.1.1 nebo vyšší._<p><p></li></ul><br>Kromě toho, pokud je nastavena na **aplikace spravované podle zásad** nebo **žádný**, je blokovaná funkce iOS 9, která umožňuje vyhledávání Spotlight dat v rámci aplikací. <p><p>Tyto zásady můžete také použít operační systém na iOS univerzální odkazy.  Spravuje obecné webové odkazy **otevřete aplikaci odkazy v aplikaci Intune Managed Browser** nastavení zásad. <p> U některých aplikací a služeb, které mají výjimku, může být v Intune standardně povolený přenos dat. Pokud potřebujete povolit přenos dat do aplikace, která nepodporuje zásady ochrany aplikací Intune, můžete vytvořit vlastní výjimky. Další informace najdete v tématu [Výjimky přenosu dat](#data-transfer-exemptions).  | **Všechny aplikace**   |
| <ul><ui> **Vyberte aplikace, které se mají vyloučit** | Tato možnost je k dispozici, když vyberete *aplikace spravované podle zásad* pro možnost předchozí.   |   |
| **Přijímat data z jiných aplikací** | Určete, jaké aplikace můžou převádět data do této aplikace: <ul><li>**Všechny aplikace**: Povolíte přenos dat ze žádné aplikace.</li><li>**Žádný**: Nepovolovat přenos dat ze žádné aplikace, včetně jiných aplikací spravovaných pomocí zásad.</li><li>**Aplikace spravované podle zásad**: Povolíte přenos jenom z ostatních aplikací spravovaných zásadou.</li><li>**Všechny aplikace s příchozí data organizace**: Povolíte přenos dat ze žádné aplikace. Se všemi příchozími daty, u kterých není známá identita uživatele, je možné zacházet jako s daty z vaší organizace. Data budou označena identitou uživatele zaregistrovanou ve správě mobilních zařízení, kterou definujete v nastavení `IntuneMAMUPN`.<p><p>**Poznámka:** _**Všechny aplikace s příchozí data organizace** hodnota platí pro pouze zařízení v MDM zaregistrované. Pokud se toto nastavení vztahuje na uživatele neregistrovaného zařízení, použije se chování, které odpovídá hodnotě **Všechny aplikace**._</li></ul> Z některých aplikací a služeb, které mají výjimku, může Intune povolit přenos dat. Kompletní seznam těchto aplikací a služeb najdete v části [Výjimky přenosu dat](#data-transfer-exemptions). Aplikace, které podporují více identit a umožňují správu mobilních aplikací (MAM) na neregistrovaných zařízeních s iOSem, tuto zásadu ignorují a povolí všechna příchozí data.<br><br> | **Všechny aplikace**    |
| **Ukládejte si kopie dat organizace** | Vyberte **bloku** zakázat použití *uložit jako* možnost v této aplikaci. Vyberte **povolit** Pokud chcete povolit použití *uložit jako*. <br><br>**Poznámka:** *Toto nastavení je podporováno pro aplikaci Microsoft Excel, OneNote, Outlook, PowerPoint a Word. Podporovat ho můžou i aplikace třetích stran a podnikové aplikace.* <br><br> Pokud je nastavena na *bloku*, můžete nakonfigurovat následující nastavení *povolit uživateli k uložení kopie vybraných služeb*.   | <br><br> **Povoleno**   |
| <ul><ui> **Uživateli umožňují uložit kopie vybraných služeb** | Uživatelé můžou k ukládání používat vybrané služby (OneDrive pro firmy, SharePoint a místní úložiště). Všechny ostatní služby jsou blokované.| **Vybraná 0**  |
| **Omezit operace vyjmutí, kopírování a vkládání mezi jinými aplikacemi** | Určete, kdy se můžou v této aplikaci použít akce vyjmutí, kopírování a vložení. Vyberte z těchto možností: <ul><li>**Zablokuje**:  Nepovolit akce vyjmutí, kopírování a vložení mezi touto aplikací a jakoukoli jinou aplikaci.</li><li>**Aplikace spravované podle zásad**: Povolit akce vyjmutí, kopírování a vložení mezi touto a jinými aplikacemi spravovanými zásadami.</li><li>**S vložením spravované podle zásad**: Povoluje vyjmutí a kopírování mezi touto a jinými aplikacemi spravovanými zásadami. Povoluje vložení dat z jakékoliv aplikace do této aplikace.</li><li>**Libovolná aplikace**: Žádná omezení pro vyjmutí, kopírování a vložení do a z této aplikace.</ul> | **Libovolná aplikace**   |
| **Vyjmutí a kopírování omezení znaků pro libovolnou aplikaci** | Zadejte počet znaků, které mohou být vyjmutých nebo zkopírovaných z dat organizace a účty.  To vám umožní sdílení zadaný počet znaků k jakékoli aplikaci, bez ohledu **omezit vyjmutí, kopírování a vkládání v ostatních aplikacích** nastavení.<p>Výchozí hodnota = 0<p>**Poznámka**: Vyžaduje, aby aplikace měla sadu Intune SDK verze 9.0.14 nebo novější.  | **0**   |


### <a name="encryption"></a>Šifrování
| Nastavení | Způsob použití | Výchozí hodnota |
|------|----------|-------|
| **Šifrování dat organizace** | Zvolte možnost vyžadovat, aby povolili šifrování pracovních nebo školních dat v této aplikaci.  Intune zajišťuje šifrování zařízení s Iosem k ochraně dat aplikací při uzamčení zařízení zašifrovaná.  Aplikace může volitelně šifrovat data aplikace pomocí sady Intune APP SDK šifrování.  Intune APP SDK využívá iOS metody šifrování dat v aplikaci použít 128bitové šifrování AES. <br><br> Pokud povolíte toto nastavení, je možné, že si uživatel bude muset nastavit kód PIN a používat ho pro přístup k zařízení. Pokud neexistuje žádné zařízení PIN kód a vyžaduje se šifrování, bude uživatel vyzván k nastavení PIN zprávou "vaše organizace vyžaduje, abyste nejdřív povolili použití PIN pro přístup k této aplikaci zařízení." <br><br> Přejděte na [oficiální dokumentaci společnosti Apple](https://support.apple.com/en-us/HT202739) a podívejte se, které šifrovací moduly iOS jsou certifikované jako FIPS 140-2 nebo které na tuto certifikaci čekají. | **vyžadovat**  |


### <a name="functionality"></a>Funkce
| Nastavení | Způsob použití | Výchozí hodnota |
|------|----------|-------|
| **Synchronizace aplikace s využitím aplikací nativních kontaktů** |  Vyberte **zakázat** nechcete, aby aplikace ukládala data do nativní aplikace kontakty na zařízení. Pokud vyberete **povolit**, může aplikace ukládat data do nativní aplikace kontakty na zařízení. <br><br>Když budete z aplikace selektivně mazat pracovní nebo školní data, odeberou se kontakty synchronizované přímo z aplikace do nativní aplikace Kontakty. Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. To se v současné době týká jenom aplikace Microsoft Outlook.   | **Povolit**  |
| **Tisk dat organizace** | Vyberte **zakázat** zabránit tisk pracovních nebo školních dat aplikace.   | **Povolit**  |
| **Sdílená složka webového obsahu pomocí zásad spravovaného prohlížeče** | Určete, jakým způsobem se otevírá webový obsah (odkazy http/https) z aplikací spravovaných zásadami. Vybírejte z těchto možností: <ul><li>**Zásady spravovaného prohlížeče**: Povolit webový obsah, který otevíral jenom ve zásady spravovaného prohlížeče.</li><li>**Libovolná aplikace**: Povolit webové odkazy v jakékoli aplikaci </li></ul> Pokud ke správě zařízení používáte Intune, přečtěte si téma [Správa přístupu k internetu pomocí prohlížeče chráněného zásadami Microsoft Intune](app-configuration-managed-browser.md).<br><br>**Prohlížeče spravované zásadami**<br>Pokud nasadíte více prohlížečů spravovaných zásadami, spustí se jen jeden.  Jako první se spustí Intune Managed Browser a následně Microsoft Edge.<p>Pokud se vyžaduje prohlížeč spravovaný zásadami, ale není nainstalovaný, budou koncoví uživatelé vyzváni k instalaci řešení Intune Managed Browser.<p>Pokud se vyžaduje prohlížeč spravovaný zásadami, jsou univerzální odkazy iOS spravované nastavením zásady **Povolit aplikaci posílat data do jiných aplikací**. <p>**Registrace zařízení v Intune**<br>Pokud ke správě zařízení používáte Intune, přečtěte si článek Správa přístupu k internetu pomocí zásad aplikace Managed Browser v Microsoft Intune. <p>**Microsoft Edge spravovaný zásadami**<br>Prohlížeč Microsoft Edge pro mobilní zařízení (iOS a Android) podporuje zásady ochrany aplikací Intune. Uživatelé, kteří se v aplikaci prohlížeče Microsoft Edge přihlásí svými podnikovými účty Azure AD, budou chráněni službou Intune. Prohlížeč Microsoft Edge integraci sady Intune SDK a podporuje všechny její zásady ochrany dat, s výjimkou brání:<br><ul><li>**Uložit – jako**: Prohlížeč Microsoft Edge neumožňuje uživateli přidat s přímým přístupem, v aplikaci připojení ke cloudovým poskytovatelé úložiště (jako je třeba OneDrive).</li><li>**Obraťte se na synchronizaci**: Prohlížeč Microsoft Edge se neukládá do seznamu nativních kontaktů.</li></ul><br>**Poznámka**:<br>Intune SDK nelze určit, pokud je cílové aplikace v prohlížeči. Na zařízeních s iOSem nejsou povolené žádné jiné aplikace spravovaného prohlížeče.    | **Není nakonfigurováno**  |

> [!NOTE]  
> Žádné z nastavení ochrany dat řídit Apple spravované open in funkce na zařízeních s Iosem. Pokud chcete spravovat funkci Otevřít v od Applu, přečtěte si [Správa přenosu dat mezi aplikacemi pro iOS pomocí Microsoft Intune](data-transfer-between-apps-manage-ios.md).

## <a name="data-transfer-exemptions"></a>Výjimky přenosu dat

U některých aplikací a služeb platformy, které mají výjimku, můžou zásady ochrany aplikací Intune v některých scénářích povolit přenos dat. Tento seznam se může měnit. Obsahuje služby a aplikace, které se považují za užitečné pro bezpečné a produktivní použití.

| Název aplikace nebo služby | Popis |
| ---- | --- |
|<code>tel; telprompt</code> | Nativní telefonní aplikace |
| <code>skype</code> | Skype |
| <code>app-settings</code> | Nastavení zařízení |
| <code>itms; itmss; itms-apps; itms-appss; itms-services</code> | App Store |
| <code>calshow</code> | Nativní kalendář |


## <a name="access-requirements"></a>Požadavky na přístup

| Nastavení | Způsob použití | Výchozí hodnota |
|------|----------|-------|
| **Pro přístup kód PIN** | Vyberte **vyžadují** vyžadování PIN kódu pro použití této aplikace. Uživateli se zobrazí výzva k nastavení tohoto kódu PIN při prvním spuštění aplikace v pracovním nebo školním kontextu. PIN kód se používá při práci online nebo offline.    <br><br> Sílu kódu PIN, pomocí nastavení dostupných v části můžete nakonfigurovat **kód PIN pro přístup** oddílu.   | **vyžadovat** |
| <ul><ui> **Zadejte PIN kód** | Nastavte požadavek pro typ čísel nebo hesel PIN kódy před přístupem k aplikaci, která má zásady ochrany aplikací. Číselná podoba vyžaduje jen číslice, zatímco heslo může být definované s minimálně 1 abecedním písmenem **nebo** s minimálně 1 speciálním znakem.  <br><br> **Poznámka:** *Konfigurace typu hesla, se vyžaduje, aby aplikace měla sadu Intune SDK verze 7.1.12 nebo vyšší. Číselný typ nemá žádné omezení, pokud se jedná o verzi sady Intune SDK. Povolené speciální znaky zahrnují speciální znaky a symboly na anglické klávesnici pro iOS.*  | **Číselné**  |
| <ul><ui> **Jednoduchý kód PIN** | Vyberte **povolit** umožníte uživatelům používat jednoduchý kód PIN jako 1234, 1111, abcd nebo aaaa. Vyberte **bloku** tak tomu, aby jednoduché posloupnosti používali. <br><br>**Poznámka**: *Pokud je nakonfigurovaný kód PIN typu heslo a povolit jednoduchý kód PIN je nastavená na Ano, uživatel musí alespoň 1 písmeno **nebo** ve svém PIN kódu alespoň 1 speciální znak. Pokud je nakonfigurovaný PIN kód typu heslo a možnost Povolit jednoduchý PIN kód je nastavená na Ne, uživatel musí mít ve svém PIN kódu alespoň 1 číslici **a** 1 písmeno **a** alespoň 1 speciální znak.*   |**Povoleno**  |
| <ul><ui> **Vyberte minimální délku PIN kódu** | Zadejte minimální počet číslic v pinu.  | **4**  |
|  <ul><ui> **Touch ID místo kódu PIN pro přístup (iOS 8 +)** | Vyberte **povolit** umožňující uživateli umožňuje využít [Touch ID](https://support.apple.com/HT201371) místo kódu PIN pro přístup k aplikaci.    | **Povoleno**  |
|  <ul><ui> <ul><ui> **Přepsat Touch ID pomocí kódu PIN po vypršení časového limitu** |  Chcete-li toto nastavení použít, vyberte **vyžadují** a potom nakonfigurujte vypršení časového limitu nečinnosti.  |**vyžadovat**  |
|  <ul><ui> <ul><ui> **Časový limit (v minutách neaktivity)** | Zadejte čas v minutách, po jejichž uplynutí bude PIN kód přepsat pomocí otisku prstu.  |**30**  |
|  <ul><ui> **Face ID místo kódu PIN pro přístup (iOS 11 +)** | Vyberte **povolit** umožňující uživateli umožňuje využít technologii rozpoznávání obličeje k ověřování uživatelů na zařízeních s Iosem. Pokud je povoleno, musí pro přístup k aplikaci na zařízení podporující Face ID použít Face ID.    | **Povoleno**  |
|  <ul><ui>**PIN reset Service po počet dnů** | Vyberte **Ano** budou muset uživatelé změnit PIN kód jejich aplikace po nastavené období času ve dnech.  <br><br>Pokud je nastavena na *Ano*, nastavte počet dní před obnovení kódu PIN je povinný. |**Ne**  |  
|  <ul><ui> <ul><ui> **Počet dnů** | Nakonfigurujte počet dní před obnovení kódu PIN je povinný.  |**0**  |
|  <ul><ui>**Aplikace PIN kód při nastavit PIN kód zařízení** | Vyberte **zakázat** chcete zakázat PIN kód aplikace, když zámek zařízení se na zaregistrovaném zařízení zjistí pomocí portálu společnosti, které jsou nakonfigurované.<br><br> **Poznámka:** *Vyžaduje, aby aplikace měla verzi Intune SDK 7.0.1 nebo vyšší.*  <br><br>Na zařízeních s iOSem můžete nechat uživatele prokazovat svoji identitu pomocí [Touch ID](https://support.apple.com/HT201371) nebo [Face ID](https://support.apple.com/HT208109) místo PINu. Intune používá k ověřování uživatelů pomocí Touch ID a Face ID rozhraní [LocalAuthentication](https://developer.apple.com/documentation/localauthentication/) API. Další informace o Touch ID a Face ID najdete v [příručce zabezpečení iOS](https://www.apple.com/business/docs/iOS_Security_Guide.pdf).  <br><br> Pokud se uživatel pokusí tuto aplikaci použít spolu s pracovním nebo školním účtem, zobrazí se mu výzva, aby místo PIN kódu použil k identifikaci otisk prstu nebo svou tvář. Když je toto nastavení povolené, bude při používání pracovního nebo školního účtu obrázek náhledu v přepínači aplikací rozostřený.  |  **Povolit** |  
| **Přihlašovací údaje pro přístup k pracovnímu nebo školnímu účtu** | Vyberte **vyžadují** uživatel muset přihlásit pomocí svého pracovního nebo školního účtu namísto zadávání kódu PIN pro přístup k aplikaci. Pokud nastavíte **vyžadují**a PIN kód nebo biometrické výzvy jsou zapnuté, podnikové přihlašovací údaje a buď PIN kód nebo biometrické výzvy se zobrazí.  | **Nepožaduje se** |
| **Znovu zkontrolovat požadavky na přístup po (v minutách neaktivity)** | Nakonfigurujte počet minut nečinnosti, která musí uplynout, než aplikace vyžaduje, aby uživatel znovu zadat požadavky na přístup. <br><br> Správce například v zásadách zapne PIN kód a zablokuje zařízení s rootem. Uživatel otevře aplikaci spravovanou přes Intune, musí zadat PIN kód a musí aplikaci používat na zařízení bez rootu. Při použití tohoto nastavení nemusí uživatel u žádné aplikace spravované přes Intune zadávat PIN kód ani podstupovat další kontrolu výskytu rootu po dobu, která odpovídá nakonfigurované hodnotě.  <br><br>**Poznámka:** *V Iosu se kód PIN sdílí mezi všemi aplikacemi spravovanými Intune z **stejného vydavatele**. Časovač konkrétního kódu PIN se vynuluje, jakmile se aplikace přestane v zařízení zobrazovat na popředí. Toto nastavení definuje časový limit, po který uživatel nemusí zadávat PIN u žádné aplikace spravované v Intune, která ho sdílí. Tento formát nastavení zásady podporuje kladné celé číslo.*     | **30** |

> [!NOTE]
> Další informace o tom, jak v iOSu fungují různá nastavení Intune App Protection nakonfigurovaná v části Přístup u stejné skupiny aplikací a uživatelů, najdete v článku věnovaném [častým otázkám k Intune MAM](https://docs.microsoft.com/intune/mam-faq#app-experience-on-ios) a v článku [Selektivní vymazání dat pomocí akcí přístupu zásad ochrany aplikací v Intune](app-protection-policies-access-actions.md).

## <a name="conditional-launch"></a>Podmíněné spouštění
Pokud chcete ve svých zásadách ochrany přístupu nastavit bezpečnostní požadavky, které se týkají přihlašování, nakonfigurujte podmíněné spouštění. 

Výchozí nastavení obsahuje předem nakonfigurované hodnoty a akce. Některé z nich můžete odstranit, třeba *minimální verzi operačního systému*. Z rozevíracího seznamu **Vyberte jednu možnost** můžete také vybrat další nastavení. 

| Nastavení | Způsob použití |  
|---------|------------| 
| **Minimální verze operačního systému** | Zadejte minimální verzi systému iOS, kterou tato aplikace používá. *Akce* zahrnují: <br><ul><li>**Upozornit** – uživateli se zobrazí oznámení, pokud verze iOSu v zařízení nevyhovuje tomuto požadavku. Toto oznámení je možné zavřít. <br><br> </li></ul> <ul><li>**Blokovat přístup** – pokud verze iOSu v zařízení nevyhovuje tomuto požadavku, bude uživatel zablokován.</li></ul> <ul><li>**Vymazat data** – uživatelský účet, který je přidružený k aplikaci, se ze zařízení vymaže.  </li></ul> </li></ul> _**Poznámka:** Vyžaduje, aby aplikace měla verzi Intune SDK 7.0.1 nebo vyšší._ |
| **Maximální počet pokusů o zadání PIN kódu** | Zadejte počet pokusů, které uživatel bude mít k úspěšnému zadání PIN kódu před provedením nakonfigurované akce. Tento formát nastavení zásady podporuje kladné celé číslo. *Akce* zahrnují: <br><ul><li>**Resetovat PIN kód** – uživatel musí resetovat svůj PIN.</li></ul> <ul><li>**Vymazat data** – uživatelský účet, který je přidružený k aplikaci, se ze zařízení vymaže.  </li></ul></li></ul> Výchozí hodnota = **5** |
| **Období odkladu pro offline režim** | Kolik minut můžou aplikace MAM běžet offline. Zadejte dobu (v minutách) před opakovaným zkontrolováním požadavků na přístup k aplikaci. *Akce* zahrnují: <br><ul><li>**Zablokovat přístup (minuty)** – kolik minut můžou aplikace MAM běžet offline. Zadejte dobu (v minutách) před opakovaným zkontrolováním požadavků na přístup k aplikaci. Po uplynutí nakonfigurované doby aplikace zablokuje přístup k pracovním nebo školním datům, dokud nebude k dispozici přístup k síti. Tento formát nastavení zásady podporuje kladné celé číslo.<br><br>Výchozí hodnota = **720** minut (12 hodin) </li></ul> <ul><li>**Vymazat data (dny)** – po kolika dnech (definovaných správcem) provozu offline bude aplikace vyžadovat, aby se uživatel připojil k síti a znovu se přihlásil. Pokud je ověření uživatele úspěšné, může ke svým datům dál přistupovat a doba v offline režimu se resetuje.  Pokud se uživateli nepodaří ověřit, aplikace provede selektivní vymazání účet a data uživatelů.  Další informace o tom, která data se selektivním vymazáním odstraní, najdete v tématu [Jak z aplikací spravovaných pomocí Intune vymazat jenom firemní data](https://docs.microsoft.com/intune/apps-selective-wipe). Tento formát nastavení zásady podporuje kladné celé číslo. <br><br> Výchozí hodnota = **90 dní** </li></ul>  Tato položka se může zobrazit vícekrát. V takovém případě každá instance podporuje jinou akci. |
| **Zařízení s jailbreakem nebo rootem** | U tohoto nastavení se nezadává žádná hodnota. *Akce* zahrnují: <br><ul><li>**Blokovat přístup** – brání spuštění aplikace na zařízeních s jailbreakem nebo rootem (která mají odblokovaný systém). Uživatel může aplikaci dál používat pro své osobní účely, ale pro přístup k pracovním nebo školním datům v této aplikaci musí použít jiné zařízení.</li></ul> <ul><li>**Vymazat data** – uživatelský účet, který je přidružený k aplikaci, se ze zařízení vymaže. </li></ul> |
| **Minimální verze aplikace** | Zadejte minimální verzi operačního systému. *Akce* zahrnují: <br><ul><li>**Upozornit** – pokud verze aplikace v zařízení nevyhovuje tomuto požadavku, zobrazí se uživateli oznámení. Toto oznámení je možné zavřít.</li></ul> <ul><li>**Blokovat přístup** – pokud verze aplikace v zařízení nevyhovuje tomuto požadavku, zablokuje se uživateli přístup. </li></ul> <ul><li>**Vymazat data** – uživatelský účet, který je přidružený k aplikaci, se ze zařízení vymaže. </li></ul> </li></ul>   Vzhledem k tomu, že aplikace mívají často odlišná schémata verzí, vytvořte zásadu, ve které bude jedna minimální verze zacílená na jednu aplikaci (např. *Zásada verze Outlooku*).<br><br> Tato položka se může zobrazit vícekrát. V takovém případě každá instance podporuje jinou akci.<br><br> Tento formát nastavení zásady podporuje vlastnosti major.minor, major.minor.build a major.minor.build.revision.||
| **Minimální verze sady SDK** | Zadejte hodnotu minimální verze sady Intune SDK. *Akce* zahrnují: <br><ul><li>**Blokovat přístup** – pokud verze sady SDK neodpovídá zásadě ochrany aplikace v Intune, uživateli se zablokuje přístup. <br> <br> Další informace o sadě SDK se zásadami ochrany aplikací Intune najdete v článku [Přehled sady Intune App SDK](app-sdk.md).</li></ul> <ul><li>**Vymazat data** – uživatelský účet, který je přidružený k aplikaci, se ze zařízení vymaže. </li></ul>  </li></ul> Vzhledem k tomu, že aplikace mívají často odlišná schémata verzí, vytvořte zásadu, ve které bude jedna minimální verze zacílená na jednu aplikaci (např. *Zásada verze Outlooku*). <br><br> Tato položka se může zobrazit vícekrát. V takovém případě každá instance podporuje jinou akci.|
| **Modely zařízení** | Určuje model zařízení, který je k používání aplikace povinný. *Akce* zahrnují: <br><ul><li>**Povolit zadané (blokovat nezadané)** – aplikaci můžou používat jenom zařízení, která odpovídají zadanému modelu. Všechny ostatní modely zařízení budou zablokovány. </li></ul> <ul><li>**Povolit zadané (vymazat nezadané)** – uživatelský účet, který je přidružený k aplikaci, se ze zařízení vymaže.</li></ul> |



##  <a name="add-ins-for-outlook-app"></a>Doplňky pro aplikaci Outlook

Poměrně čerstvou novinkou jsou doplňky v Outlooku pro iOS, které umožňují integrovat do e-mailového klienta oblíbené aplikace. Doplňky pro Outlook jsou k dispozici na webu, v systému Windows, na Macu a v Outlooku pro iOS. Zásady, které jsou v sadách Intune SDK a Intune App Protection, sice nepodporují správu doplňků Outlooku, ale existují jiné způsoby, jak jejich používání omezit. Vzhledem k tomu, že se doplňky spravují přes Microsoft Exchange, budou uživatelé moct sdílet data a zprávy v rámci Outlooku a nespravovaných aplikací doplňků (pokud nemají doplňky vypnuté na Exchangi).

Pokud chcete svým koncovým uživatelům používání a instalaci doplňků Outlooku zakázat (bude to mít vliv na všechny klienty Outlooku), musíte v rolích v Centru pro správu Exchange provést následující změny:

- Pokud chcete uživatelům zabránit v instalaci doplňků z Office Storu, odeberte jim roli My Marketplace (Moje tržiště).
- Pokud chcete uživatelům zabránit v instalaci doplňků bokem (mimo Store), odeberte jim roli My Custom Apps (Moje vlastní aplikace).
- Pokud chcete uživatelům zabránit v instalaci všech doplňků, odeberte jim jak roli My Custom Apps, tak roli My Marketplace.

Tyto pokyny platí pro Office 365, Exchange 2016, Exchange 2013 v Outlooku na web, Windows, Mac a mobilní zařízení.

- Další informace o [doplňcích pro Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).
- Přečtěte si další informace o tom [jak určit, kteří správci a uživatelé můžou instalovat a spravovat doplňky pro aplikaci Outlook](https://technet.microsoft.com/library/jj943754(v=exchg.150).aspx).

##  <a name="linkedin-account-connections-for-microsoft-apps"></a>Připojení účtů LinkedIn pro aplikace Microsoft

Připojení účtů LinkedIn umožňuje uživatelům zobrazit informace veřejného profilu sítě LinkedIn v určitých aplikacích Microsoft. Ve výchozím nastavení si uživatelé mohou zvolit připojení svého účtu LinkedIn a pracovního nebo školního účtu Microsoft, aby se mohli podívat na další informace profilu sítě LinkedIn. 

> [!NOTE]
> Integrace LinkedIn je momentálně nedostupná pro zákazníky ze státní správy USA a pro organizace s poštovními schránkami Exchange Online v Austrálii, Číně, Francii, Indii, Japonsku, Jižní Koreji, Jihoafrické republice, Kanadě, Německu a Spojeném království.

Sada Intune SDK ani zásady služby Intune App Protection nepodporují správu připojených účtů LinkedIn, ale existují jiné způsoby, jak tyto účty spravovat. Připojení účtů LinkedIn můžete zakázat pro celou organizaci, nebo je můžete povolit pro vybrané skupiny uživatelů ve vaší organizaci. Tato nastavení ovlivňují připojení LinkedIn ve všech aplikacích Office 365 na všech platformách (webové, mobilní a desktopové). Můžete:

- Povolte nebo zakažte připojení účtů LinkedIn pro tenanta na portálu Azure Portal. 
- Povolte nebo zakažte připojení účtů LinkedIn pro aplikace Office 2016 ve vaší organizaci pomocí zásad skupiny.

Pokud je integrace LinkedIn pro vašeho tenanta povolena, mají uživatelé ve vaší organizaci při připojení svých účtů LinkedIn a pracovních nebo školních účtů Microsoft dvě možnosti: 

- Mohou udělit oprávnění ke sdílení dat mezi oběma účty. To znamená, že mohou udělit oprávnění svému účtu LinkedIn sdílet data s pracovním nebo školním účtem Microsoft a naopak. Data sdílená s LinkedIn opouští online služby. 
- Mohou udělit oprávnění ke sdílení dat pouze ze svého účtu LinkedIn do pracovního nebo školního účtu Microsoft.

Pokud uživatel souhlasí se sdílením dat mezi účty stejně jako u doplňků Office, integrace LinkedIn používá existující rozhraní Microsoft Graph API. Integrace LinkedIn používá pouze podmnožinu rozhraní API dostupných pro doplňky Office a podporuje různá vyloučení.


|Oprávnění Microsoft Graph  |Popis  |
|---------|---------|
|Oprávnění ke čtení pro možnost [Lidé](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#people-permissions)     |Umožňuje aplikaci přístup k seznamu osob se skóre, které jsou pro přihlášeného uživatele relevantní. Seznam může obsahovat místní kontakty, kontakty ze sociálních sítí nebo adresáře vaší organizace a osoby z posledních komunikací (například z e-mailu nebo Skypu).         |
|Oprávnění ke čtení pro možnost [Kalendáře](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#calendars-permissions)     |Umožňuje aplikaci přístup k událostem v uživatelských kalendářích. Zahrnuje schůzky v kalendářích přihlášených uživatelů, jejich časy, umístění a účastníky.         |
|Oprávnění ke čtení pro možnost [Profil uživatele](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#user-permissions)     |Umožňuje uživatelům přihlásit se k aplikaci a aplikaci umožňuje přístup k profilu přihlášených uživatelů. Také aplikaci umožňuje přístup k základním informacím o společnosti u přihlášených uživatelů.         |
|Předplatná     |Tento rozsah se zatím nepoužívá a není proto dostupný. Zahrnuje předplatná, která organizace uživatele poskytuje aplikacím a službám Microsoft, například Office 365.         |
|Insights     |Tento rozsah se zatím nepoužívá a není proto dostupný. Zahrnuje zájmy přidružené k účtu přihlášeného uživatele podle toho, jak uživatel používá služby Microsoft.         |

### <a name="learn-more"></a>Víc se uč

- Přečtěte si o [informacích a funkcích LinkedIn v aplikacích Microsoft](https://go.microsoft.com/fwlink/?linkid=850740).
- Přečtěte si o možnosti připojení účtů LinkedIn na [stránce roadmapy Office 365](https://products.office.com/en-US/business/office-365-roadmap?filters=%26freeformsearch=linkedin#abc). 
- Přečtěte si o [konfiguraci připojení účtů LinkedIn](https://docs.microsoft.com/azure/active-directory/linkedin-integration).
- Další informace o datech sdílených mezi účtem LinkedIn a pracovním nebo školním účtem Microsoft uživatele najdete v článku o [LinkedInu v aplikacích Microsoft v práci nebo ve škole](https://www.linkedin.com/help/linkedin/answer/84077).

