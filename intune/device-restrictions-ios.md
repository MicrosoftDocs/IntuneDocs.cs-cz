---
title: "Nastavení omezení pro zařízení s iOSem v Intune"
titleSuffix: Azure portal
description: "Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s iOSem."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 09/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73590192-54ca-4833-9f1d-83e1b654399f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff2c9943a04ec02a83e821a65e1307e311a9d1c0
ms.sourcegitcommit: 4ce095c0c3fa2e42cf76207b6ff8edf1fe397165
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2017
---
# <a name="ios-device-restriction-settings-in-microsoft-intune"></a>Nastavení omezení pro zařízení s iOSem v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Obecné
    
-   **Odeslání diagnostických dat** – Povolí nebo zablokuje odesílání diagnostických dat ze zařízení do společnosti Apple.
-   **Snímek obrazovky** – Povolí uživateli zachytit obsah obrazovky jako obrázek.
    - **Sledování vzdálených obrazovek v aplikaci Classroom (jenom pod dohledem)** – Povolí nebo zablokuje aplikaci Apple Classroom zobrazovat obrazovku na vzdálených zařízeních s iOSem.
    - **Sledování obrazovek v aplikaci Classroom bez dotazu (jenom pod dohledem)** – Pokud je povoleno, učitelé můžou pomocí aplikace Classroom sledovat obrazovky zařízení s iOSem studentů, aniž by to studenti věděli.
-   **Nedůvěryhodné certifikáty TLS** – Povolí v zařízení nedůvěryhodné certifikáty protokolu TLS (Transport Layer Security).
-   **Vztah důvěryhodnosti podnikové aplikace** – Umožní uživateli vybrat možnost, že důvěřuje aplikacím, které nebyly staženy z App Storu.
- **Úpravy účtu (jenom pod dohledem)** – Když jsou zablokované, brání to uživateli upravovat nastavení spojená s konkrétním zařízením z aplikace pro nastavení iOSu, například vytváření nových účtů zařízení a změny uživatelského jména nebo hesla.
To platí také pro nastavení dostupná z aplikace pro nastavení iOSu, například Pošta, Kontakty, Kalendáře, Facebook a Twitter. Neplatí to pro aplikace s nastavením účtu, které není konfigurovatelné z aplikace pro nastavení iOSu, jako je například aplikace Microsoft Outlook.
- **Povolení omezení v nastavení zařízení (jenom pod dohledem)** – Umožní uživateli na zařízení konfigurovat omezení (rodičovské kontroly).
- **Použití možnosti pro vymazání veškerého obsahu a nastavení na zařízení (jenom pod dohledem)** – Zpřístupní uživateli možnost pro vymazání veškerého obsahu a nastavení na zařízení.
- **Úprava názvu zařízení (jenom pod dohledem)** – Umožní uživateli změnit název zařízení.
- **Úprava nastavení oznámení (jenom pod dohledem)** – Umožní uživateli přenastavit v zařízení oznámení.
- **Úprava tapety (jenom pod dohledem)** – Umožní uživateli změnit v zařízení tapetu.
- **Úprava nastavení vztahu důvěryhodnosti podnikové aplikace (jenom pod dohledem)** – Umožní uživateli vybrat možnost, že důvěřuje aplikacím, které nebyly staženy z App Storu.
- **Změny profilu konfigurace** – Povolí uživateli instalovat konfigurační profily.
- **Zámek aktivace (jenom pod dohledem)** – Povolí zámek aktivace na zařízeních s iOSem, která jsou pod dohledem.

## <a name="password"></a>Heslo
-   **Heslo** – Vyžaduje, aby koncový uživatel zadal heslo pro přístup k zařízení.
    -   **Jednoduchá hesla** – Umožňuje použití jednoduchých hesel, jako je třeba 0000 nebo 1234.
    -   **Požadovaný typ hesla** – Určuje typ hesla, které se bude vyžadovat, například jenom číslice nebo alfanumerické znaky.
    -   **Počet nealfanumerických znaků v hesle** – Určuje počet znaků symbolu (jako například **#** nebo **@**), které musí heslo obsahovat.
    -   **Minimální délka hesla** – Určuje minimální počet znaků v hesle.
    -   **Počet neúspěšných přihlášení před vymazáním obsahu zařízení** – Určuje počet neúspěšných pokusů o přihlášení, než toto nastavení vymaže zařízení.
    -   **Maximální počet minut po uzamčení obrazovky, po kterém bude nutné zadat heslo**<sup>1</sup> – Určuje, jak dlouho může zařízení zůstat nečinné, než uživatel musí znovu zadat heslo.
    -   **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**<sup>1</sup> – Určuje počet minut, než se displej zařízení vypne.
    -   **Konec platnosti hesla (dny)** – Určuje počet dní, než bude nutné změnit heslo zařízení.
    -   **Znemožnit opakované použití předchozích hesel** – Určuje počet dříve použitých hesel, která si zařízení pamatuje.
    -   **Odemknutí pomocí otisků prstů** – Povolí odemknutí kompatibilních zařízení pomocí otisku prstu.
- **Úprava hesla (jenom pod dohledem)** –Zamezí změně, přidání nebo odebrání hesla. 
    - **Úprava otisků prstů (jenom pod dohledem)** –Zamezí uživateli ve změně, přidání nebo odebrání nastavení Touch ID.

<sup>1</sup>Když nakonfigurujete nastavení **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka** a **Maximální počet minut po uzamčení obrazovky, po kterém bude nutné zadat heslo**, použijí se postupně. Pokud například pro obě nastavení nastavíte hodnotu **5** minut, obrazovka se po 5 minutách automaticky vypne a po dalších 5 minutách se zařízení zamkne. Pokud ale uživatel vypne obrazovku ručně, druhé nastavení se použije okamžitě. V tomto příkladě se zařízení po tom, co uživatel vypne obrazovku, zamkne po 5 minutách.

## <a name="locked-screen-experience"></a>Prostředí zamknuté obrazovky

-   **Přístup k Řídicímu centru z uzamčeného zařízení** – Povolí uživateli přístup k aplikaci řídicího centra, když je zařízení zamknuté.
-   **Oznámení na uzamčeném zařízení** – Povolí uživateli přístup k zobrazení oznámení bez odemknutí zařízení.
-   **Passbook na uzamčeném zařízení** – Povolí uživateli přístup k aplikaci Passbook, když je zařízení zamknuté.
-   **Zobrazení Dnes na uzamčené obrazovce** – Povolí uživateli zobrazovat zobrazení Dnes, když je zařízení zamknuté.

## <a name="app-store-doc-viewing-gaming"></a>App Store, zobrazování dokumentů, hraní her


-   **App Store** – Zablokuje přístup k obchodu s aplikacemi v zařízeních pod dohledem.
    - **Instalace aplikací z App Storu (jenom pod dohledem)** – Zablokuje App Store z domovské obrazovky zařízení. Koncoví uživatelé můžou aplikace dál instalovat pomocí iTunes nebo Apple Configuratoru.
    - **Automatické stahování aplikací (jenom pod dohledem) ** – Zamezí stažení aplikací zakoupených na jiném zařízení s iOSem do tohoto zařízení.
-   **Heslo pro přístup k obchodu s aplikacemi** – Vyžaduje, aby uživatel zadal heslo, než bude moci navštívit obchod s aplikacemi.
-   **Nákupy v aplikaci** – Povolí ve spuštěné aplikaci nákupy v obchodě.
-   **Explicitní obsah v hudbě, podcastech nebo zprávách z iTunes (jenom pod dohledem)** – Povolí zařízení přístup k obsahu z obchodu, který je označený jako obsah pro dospělé.
-   **Stahovat obsah z úložiště iBook označený jako Erotika** – Povolí uživateli stahování knih z kategorie Erotika.
-   **Zobrazování firemních dokumentů v nespravovaných aplikacích** – Povolí prohlížení podnikových dokumentů v jakékoliv aplikaci.<br>**Příklad:** Chcete zabránit uživatelům v ukládání souborů z aplikace OneDrive do Dropboxu. U tohoto nastavení vyberte možnost Ne. Až zařízení zásadu obdrží (třeba po restartování), už nebude povolovat ukládání.
-   **Zobrazování nefiremních dokumentů ve firemních aplikacích** – Povolí prohlížení libovolného dokumentu ve spravovaných podnikových aplikacích.
-   **Považovat AirDrop za nespravovaný cíl** – Znemožní spravovaným aplikacím posílat data přes Airdrop.
-   **Přidávání přátel na Game Center (jenom pod dohledem)** – Povolí uživateli přidávat přátele na Game Center.
-   **Game Center (jenom pod dohledem)** – Zablokuje nebo povolí používání aplikace Game Center.
-   **Hry pro více hráčů** – Povolí uživateli hrát na zařízení hry pro více hráčů.
-   **Oblast hodnocení** – Zvolte oblast hodnocení, pro kterou chcete konfigurovat povolené soubory ke stažení, a potom zvolte povolená hodnocení pro **filmy** a **televizní pořady**.
-   **Aplikace** – Zvolte povolená hodnocení aplikací podle věku, které budou uživatelé moct stahovat, nebo můžete zvolit **Povolit všechny aplikace**.

## <a name="built-in-apps"></a>Integrované aplikace

-   **Kamera** – Vyberte, jestli je možné používat fotoaparát v zařízení. 
    -   **FaceTime** – Povolí používání aplikace FaceTime v zařízení.
-   **Siri** – Povolí v zařízení používání hlasové asistentky Siri.
    -   **Siri na uzamčeném zařízení** – Povolí používání hlasové asistentky Siri, když je zařízení zamknuté.
    -   **Filtr vulgárních výrazů v Siri (jenom pod dohledem)** – Zabrání Siri diktovat a vyslovovat vulgární výrazy.
    -   **Siri a dotazování na uživateli generovaný obsah z internetu (jenom pod dohledem)** – Povolí Siri přístup k webům, aby mohla odpovídat na otázky.
- **Apple News (jenom pod dohledem)** – Povolí používání aplikace Apple News.
- **Obchod iBooks (jenom pod dohledem)** – Umožní uživateli procházení a nákup knih z obchodu iBooks.
- **Aplikace Zprávy na zařízení (jenom pod dohledem)** – Povolí použití aplikace Zprávy k posílání a čtení textových zpráv.
- **Podcasty (jenom pod dohledem)** – Povolí používání aplikace Podcasty.
- **Služba Music (jenom pod dohledem)** – Povolí používání aplikace Apple Music.
- **Služba iTunes Radio (jenom pod dohledem)** – Povolí používání aplikace iTunes Radio.
- **Změny nastavení aplikace Hledat přátele (jenom pod dohledem)** – Umožní uživateli změnu nastavení pro aplikaci Hledat přátele.
- **Vyhledávání Spotlight a vracení výsledků z internetu (jenom pod dohledem)** – Povolí vyhledávání Spotlight připojit se k internetu, aby bylo možné poskytnout další výsledky.

## <a name="restricted-apps"></a>Omezené aplikace

V seznamu omezených aplikací můžete nakonfigurovat jeden z následujících seznamů:

**Zakázané aplikace** – Zobrazí seznam aplikací (nespravovaných pomocí Intune), které nemají uživatelé dovolené nainstalovat a spustit.
**Schválené aplikace** – Zobrazí seznam aplikací, které mají uživatelé dovolené instalovat. Uživatelé nesmí instalovat aplikace, které nejsou v seznamu. Aplikace, které spravuje Intune, jsou povolené automaticky.

Pro uživatele není instalace zakázané aplikace znemožněna, ale pokud to udělají, dostanete příslušné hlášení.

Pokud chcete seznam nakonfigurovat, klikněte na **Přidat**, zadejte libovolný název, volitelně vydavatele aplikace a nakonec adresu URL aplikace v App Storu.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Jak zadat adresu URL pro aplikaci ve Storu

Pokud chcete zadat adresu URL aplikace do seznamu aplikací, použijte následující formát:

Pomocí vyhledávacího modulu najděte aplikaci, kterou chcete použít v iTunes App Storu, a otevřete stránku pro tuto aplikaci.
Zkopírujte adresu URL stránky a použijte ji jako URL ke konfiguraci seznamu povolených a zakázaných aplikací nebo aplikace, kterou chcete spustit v celoobrazovkovém režimu.
Profily zařízení, které obsahují nastavení aplikací s omezeným přístupem, se musí přiřadit skupinám uživatelů.

Příklad: Vyhledejte Microsoft Word pro iPad. Použitá adresa URL bude https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> Pomocí softwaru iTunes taky můžete najít aplikaci a pomocí příkazu **Kopírovat odkaz** získat adresu URL aplikace.



### <a name="additional-options"></a>Další možnosti

Můžete také kliknout na **Import** a naplnit seznam ze souboru csv ve formátu <*adresa url aplikace*>, <*název aplikace*>, <*vydavatel aplikace*> nebo kliknout na **Export** a vytvořit si soubor csv obsahující seznam aplikací s omezeným přístupem ve stejném formátu.

## <a name="show-or-hide-apps-supervised-only"></a>Zobrazit nebo skrýt aplikace (jenom pod dohledem)

V seznamu Zobrazit nebo skrýt aplikace můžete nakonfigurovat jeden z následujících seznamů (vyžaduje zařízení pod dohledem se systémem iOS 9.3 nebo novější).

Seznam **Skryté aplikace** – Určuje seznam aplikací, které budou uživatelům skryté. Uživatelé nebudou moci tyto aplikace zobrazit ani spustit.
Seznam **Viditelné aplikace** – Určuje seznam aplikací, které uživatelé můžou zobrazit a spustit. Žádné jiné aplikace nebude možné zobrazit ani spustit.

Pokud chcete seznam nakonfigurovat, klikněte na **Přidat**, zadejte libovolný název, volitelně vydavatele aplikace a nakonec adresu URL aplikace v App Storu.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Jak zadat adresu URL pro aplikaci ve Storu

Pokud chcete zadat adresu URL aplikace do seznamu aplikací, použijte následující formát:

Pomocí vyhledávacího modulu najděte aplikaci, kterou chcete použít v iTunes App Storu, a otevřete stránku pro tuto aplikaci.
Zkopírujte adresu URL stránky a použijte ji jako URL ke konfiguraci seznamu povolených a zakázaných aplikací nebo aplikace, kterou chcete spustit v celoobrazovkovém režimu.

Příklad: Vyhledejte Microsoft Word pro iPad. Použitá adresa URL bude https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> Pomocí softwaru iTunes taky můžete najít aplikaci a pomocí příkazu **Kopírovat odkaz** získat adresu URL aplikace.

### <a name="additional-options"></a>Další možnosti

Můžete také kliknout na **Import** a naplnit seznam ze souboru csv ve formátu <*adresa url aplikace*>, <*název aplikace*>, <*vydavatel aplikace*> nebo klikněte na **Export** a vytvořte soubor csv obsahující seznam skrytých nebo viditelných aplikací ve stejném formátu.


## <a name="wireless"></a>Bezdrátová síť
-   **Datový roaming** – Povolí datový roaming, když je zařízení v mobilní síti.
-   **Globální načítání na pozadí při roamingu** – Povolí zařízení, aby při roamingu v mobilní síti načítalo data, třeba e-maily.
-   **Hlasové vytáčení** – Umožňuje používat v zařízení funkci hlasového vytáčení.
-   **Hlasový roaming** – Povolí hlasový roaming, když je zařízení v mobilní síti.
-   **Změny nastavení využití mobilních dat v aplikaci (jenom pod dohledem)** – Umožní uživateli řídit, které aplikace můžou používat mobilní data.
-   **Osobní hotspot** – Nepovolí, aby se zařízení používalo jako osobní hotspot. Někteří mobilní operátoři toto nastavení nemusí podporovat.
-   **Připojit se k sítím Wi-Fi jenom pomocí konfiguračních profilů (jenom pod dohledem)** –Povolit zařízení připojení jenom k sítím Wi-Fi, které jsou nakonfigurované s Wi-Fi profilem Intune.

- **Pravidla používání mobilní sítě (jenom spravované aplikace)** – Umožňuje definovat typy dat, které spravované aplikace můžou používat, když jsou v mobilní síti. Vybírejte z těchto možností:
    - **Zablokovat používání mobilních dat**
    - **Zablokovat používání mobilních dat při roamingu**

## <a name="connected-devices"></a>Připojená zařízení

-   **AirDrop (jenom pod dohledem)** – Povolí použití funkce Airdrop k výměně obsahu s blízkými zařízeními.
-   **Párování s Apple Watch (jenom pod dohledem)** – Povolí zařízení spárovat se s Apple Watch.
-   **Detekce zápěstí pro spárované hodinky Apple Watch** – Když se povolí, Apple Watch nebudou zobrazovat oznámení, dokud si je uživatel nenasadí.
-   **Úpravy Bluetooth (jenom pod dohledem)** – Zablokuje koncovému uživateli možnost měnit nastavení Bluetooth na zařízení.
-   **Párování hostitele, aby bylo možné určovat zařízení, se kterými se zařízení s iOSem může spárovat (jenom pod dohledem)** – Povolí hostitelské párování, díky kterému může správce určit, se kterými zařízeními se dá spárovat zařízení s iOSem.
-   **Vyžadovat párovací heslo pro odchozí požadavky AirPlay** – Vyžaduje párovací heslo, pokud uživatel použije AirPlay ke streamování obsahu do jiných zařízení Apple.

## <a name="keyboard-and-dictionary"></a>Klávesnice a slovník

-   **Vyhledávání definic slov (jenom pod dohledem)** – Povolí funkci iOSu, která umožňuje zvýraznit slovo a vyhledat jeho definici.
-   **Prediktivní klávesnice (jenom pod dohledem)** – Povolí používání prediktivních klávesnic, které uživateli navrhují slova, co by se mu mohla hodit.
-   **Automatické opravy (jenom pod dohledem)** – Povolí zařízení automaticky opravovat slova s překlepem.
-   **Kontrola pravopisu klávesnice (jenom pod dohledem)** – Povolí v zařízení kontrolu pravopisu.
-   **Klávesové zkratky (jenom pod dohledem)** – Umožní používání klávesových zkratek.
-   **Diktování (jenom pod dohledem)** –Zamezí uživateli v zadávání textu pomocí hlasu.

## <a name="cloud-and-storage"></a>Cloud a úložiště
-   **Zálohování do iCloudu** – Povolí uživateli zálohovat zařízení do iCloudu.
-   **Synchronizace dokumentů s iCloudem (jenom pod dohledem)** – Povolí synchronizaci dokumentu a párů klíč-hodnota s úložným prostorem iCloudu.
-   **Synchronizace datového proudu fotografií s iCloudem** – Umožňuje uživatelům povolit na jejich zařízeních **Můj fotostream**, který umožňuje synchronizovat fotky na iCloud, aby byly k dispozici na všech zařízeních uživatelů.
-   **Šifrované zálohování** – Vyžaduje, aby všechny zálohy zařízení byly šifrované.
-   **Knihovna fotografií na iCloudu** – Pokud je možnost nastavená na **Ne**, zakáže použití knihovny fotografií iCloudu, přes kterou můžou uživatelé ukládat fotografie a videa v cloudu.    Všechny fotky, které nejsou kompletně stažené z Knihovny fotografií na iCloudu do zařízení, se ze zařízení odeberou, pokud je tato možnost nastavená na **Ne**.
-   **Synchronizace spravovaných aplikací do cloudu** – Povolí aplikacím, které spravujete přes Intune, synchronizaci dat s uživatelským účtem iCloudu.
-   **Sdílený stream fotek** – Pokud chcete na zařízení zakázat **Sdílení fotek na iCloudu**, nastavte možnost na **Ne**.
-   **Pokračování aktivity** – Umožní uživateli, aby v práci, kterou zahájil na zařízení s iOSem, pokračoval na jiném zařízení s iOSem nebo macOS (Handoff).

## <a name="autonomous-single-app-mode-supervised-only"></a>Autonomní režim jedné aplikace (jenom pod dohledem)

Tato nastavení použijte ke konfiguraci, aby zařízení s iOSem spouštěla zadané aplikace v autonomním režimu jedné aplikace. Pokud je tento režim nakonfigurovaný a uživatel spustí aplikaci, v zařízení se zablokuje spuštění jakékoli další aplikace. Příkladem je nakonfigurování aplikace, která uživatelům umožňuje absolvovat na zařízení test. Když se akce aplikace dokončí nebo tuto zásadu odeberete, zařízení se vrátí do normálního stavu.

### <a name="settings"></a>Nastavení

- **Název aplikace** – zadejte název aplikace, jak se bude zobrazovat v seznamu aplikací v tomto okně.
- **ID sady prostředků aplikace** – zadejte ID sady prostředků aplikace. Pomůžou vám **Referenční informace o ID sady prostředků pro integrované aplikace pro iOS** v tomto tématu.

Po zadání názvů jednotlivých aplikací a ID prostředků aplikace zvolte **Přidat** a přidejte je do seznamu.

- **Importovat** – slouží k importu textového souboru s oddělovači (.csv), který obsahuje seznam názvů aplikací a k nim přidružených ID prostředků aplikace.
- **Exportovat** – slouží k exportu názvů aplikací a k nim přidružených ID prostředků aplikace, které jste nakonfigurovali, do textového souboru s oddělovači (.csv).

### <a name="bundle-id-reference-for-built-in-ios-apps"></a>Referenční informace o ID sady prostředků pro integrované aplikace pro iOS

Tento seznam zobrazuje ID sady prostředků některých běžných integrovaných aplikací pro iOS. Pokud chcete najít ID sady prostředků jiných aplikací, obraťte se na dodavatele softwaru.

```
,com.apple.AppStore,App Store,Apple
,com.apple.calculator,Calculator,Apple
,com.apple.mobilecal,Calendar,Apple
,com.apple.camera,Camera,Apple
,com.apple.mobiletimer,Clock,Apple
,com.apple.compass,Compass,Apple
,com.apple.MobileAddressBook,Contacts,Apple
,com.apple.facetime,FaceTime,Apple
,com.apple.mobileme.fmf1,Find Friends,Apple
,com.apple.mobileme.fmip1,Find iPhone,Apple
,com.apple.gamecenter,Game Center,Apple
,com.apple.mobilegarageband,GarageBand,Apple
,com.apple.Health,Health,Apple
,com.apple.iBooks,iBooks,Apple
,com.apple.MobileStore,iTunes Store,Apple
,com.apple.itunesu,iTunes U,Apple
,com.apple.Keynote,Keynote,Apple
,com.apple.mobilemail,Mail,Apple
,com.apple.MapsMaps,Apple
,com.apple.MobileSMS,Messages,Apple
,com.apple.Music,Music,Apple
,com.apple.news,News,Apple
,com.apple.mobilenotes,Notes,Apple
,com.apple.Numbers,Numbers,Apple
,com.apple.Pages,Pages,Apple
,com.apple.Photo-Booth,Photo Booth,Apple
,com.apple.mobileslideshow,Photos,Apple
,com.apple.podcasts,Podcasts,Apple
,com.apple.reminders,Reminders,Apple
,com.apple.mobilesafariSafari,Apple
,com.apple.Preferences,Settings,Apple
,com.apple.stocks,Stocks,Apple
,com.apple.tips,Tips,Apple
,com.apple.videos,Videos,Apple
,com.apple.VoiceMemos,VoiceMemos,Apple
,com.apple.Passbook,Wallet,Apple
,com.apple.Bridge,Watch,Apple
,com.apple.weather,Weather,Apple


```


## <a name="kiosk-supervised-only"></a>Veřejný terminál (jenom pod dohledem)
-   **Aplikace, která běží v beznabídkovém režimu** – Zvolte **Spravovaná aplikace** a vyberte aplikaci, kterou jste přidali do Intune, nebo zvolte **Aplikace pro Store** a zadejte adresu URL k aplikaci v úložišti. Žádné jiné aplikace nebudou mít dovoleno se na zařízení spouštět. Další nápovědu najdete v části Určení adres URL na obchody s aplikacemi dál v tomto tématu.
    -   **Dotykové ovládání s asistencí** – Povolí nebo zakáže nastavení usnadnění **dotykového ovládání**, která uživateli pomáhá provádět na obrazovce gesta, která by pro něho mohla být obtížná.
    -   **Invertovat barvy** – Povolí nebo zakáže nastavení usnadnění Invertovat barvy, které upraví displej tak, aby pomáhal uživatelům se zrakovým postižením.
    -   **Monofonní zvuk** – Povolí nebo zakáže nastavení usnadnění Monofonní zvuk.
    -   **Hlas na pozadí** – Povolí nebo zakáže nastavení usnadnění **VoiceOver**, které předčítá text na displeji zařízení.
    -   **Lupa** – Povolí nebo zakáže nastavení usnadnění **Lupa**, které vám umožní používat na displeji zařízení funkci zvětšení zobrazení dotykem.
    -   **Automatické zamykání** – Povolí nebo zakáže automatické zamykání zařízení.
    -   **Přepnutí vyzvánění** – Povolí nebo zakáže přepínač vyzvánění (ztlumení) na zařízení.
    -   **Otočení obrazovky** – Povolí nebo zakáže změnu orientace obrazovky, když uživatel otočí zařízení.
    -   **Tlačítko pro režim spánku obrazovky** – Povolí nebo zakáže na zařízení tlačítko probuzení z režimu spánku obrazovky.
    -   **Dotykové ovládání** – Povolí nebo zakáže dotykovou obrazovku na zařízení.
    -   **Tlačítka hlasitosti** – Povolí nebo zakáže použití tlačítek hlasitosti na zařízení.
    -   **Dotykové ovládání s asistencí** – Povolí nebo zakáže úpravy usnadnění dotykového ovládání, které uživateli umožňují upravit funkce usnadnění dotykového ovládání.
    -   **Ovládací prvek Invertovat barvy** – Povolí nebo zakáže úpravy inverze barev, které uživateli umožňují nastavit funkci inverze barev.
    -   **Přečíst vybraný text** – Povolí nebo zakáže nastavení usnadnění pro výběr řeči, které může nahlas přečíst text vybraný uživatelem.
    -   **Ovládací prvek VoiceOver** – Povolí nebo zakáže úpravy hlasového přednesu, které umožňují nastavit funkci VoiceOver (například rychlost čtení textu na obrazovce).
    -   **Ovládání lupy** – Povolí nebo zakáže úpravy zvětšení, které uživateli umožňují nastavit funkci zvětšení.

>[!NOTE]
> Než budete moct nakonfigurovat nastavení zařízení s iOSem pro celoobrazovkový (beznabídkový) režim, musíte převést zařízení do režimu dohledu pomocí nástroje Apple Configurator nebo Programu registrace zařízení Apple. Další informace o nástroji Apple Configurator získáte v dokumentaci Apple.
>Pokud se určená aplikace pro iOS nainstaluje až po přiřazení profilu, nepřejde zařízení do celoobrazovkového režimu, dokud ho nerestartujete.

## <a name="safari"></a>Safari
-   **Safari (jenom pod dohledem)** – Určuje, jestli se na zařízení může používat prohlížeč Safari.
-   **Automatické vyplňování** – Umožní uživatelům měnit nastavení automatického dokončování v prohlížeči.
-   **Soubory cookie** – Povolí prohlížeči používat soubory cookie.
-   **JavaScript** – Povolí v prohlížeči spouštění skriptů Java.
-   **Upozornění na podvody** – Povolí v prohlížeči upozornění na podvody.
-   **Automaticky otevíraná okna** – Povolí nebo zakáže blokování automaticky otevíraných oken v prohlížeči.


## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Zrušení označení e-mailových domén

V poli **Adresa URL e-mailové domény** přidejte do seznamu minimálně jednu adresu URL. Když koncoví uživatelé dostanou e-mail z jiné domény, než z té, kterou jste nakonfigurovali, označí se v aplikaci iOS Mail daný e-mail jako nedůvěryhodný.


### <a name="managed-web-domains"></a>Spravované webové domény

V poli **Adresa URL webové domény** přidejte do seznamu minimálně jednu adresu URL. Když pak z těchto zadaných domén stáhnete dokumenty, budou se považovat za spravované. Toto nastavení platí jenom pro dokumenty stažené prostřednictvím prohlížeče Safari.


### <a name="safari-password-auto-fill-domains"></a>Domény pro automatické vyplňování hesel v Safari

V poli **Adresa URL domény** přidejte do seznamu minimálně jednu adresu URL. Uživatelé si mohou uložit jenom webová hesla z adres URL uvedených v tomto seznamu. Toto nastavení platí jenom pro prohlížeč Safari a pro zařízení s iOSem 9.3 a novějším v režimu pod dohledem. Pokud nezadáte žádné adresy URL, můžete si uložit hesla ze všech webů.
