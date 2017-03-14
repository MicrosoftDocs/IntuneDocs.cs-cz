---
title: "Nastavení omezení pro zařízení s iOSem v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s iOSem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73590192-54ca-4833-9f1d-83e1b654399f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: a062b92cba0042153ffe22b949ce8a3b7b740b3f
ms.lasthandoff: 02/18/2017


---

# <a name="ios-device-restriction-settings-in-microsoft-intune"></a>Nastavení omezení pro zařízení s iOSem v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Obecné
-     **Kamera** – Vyberte, jestli je možné používat fotoaparát v zařízení.     
-     **Odeslání diagnostických dat** – Povolí nebo zablokuje odesílání diagnostických dat ze zařízení do společnosti Apple.
-     **FaceTime** – Povolí používání aplikace FaceTime v zařízení.
-     **Snímek obrazovky** – Povolí uživateli zachytit obsah obrazovky jako obrázek.
-     **Siri** – Povolí v zařízení používání hlasové asistentky Siri.
    -     **Siri na uzamčeném zařízení** – Povolí používání hlasové asistentky Siri, když je zařízení zamknuté.
    -     **Filtr vulgárních výrazů v Siri (jenom pod dohledem)** – Zabrání Siri diktovat a vyslovovat vulgární výrazy.
    -     **Siri a dotazování na uživateli generovaný obsah z internetu (jenom pod dohledem)** – Povolí Siri přístup k webům, aby mohla odpovídat na otázky.
-     **Nedůvěryhodné certifikáty TLS** – Povolí v zařízení nedůvěryhodné certifikáty protokolu TLS (Transport Layer Security).
-     **Přístup k Řídicímu centru z uzamčeného zařízení** – Povolí uživateli přístup k aplikaci řídicího centra, když je zařízení zamknuté.
-     **Oznámení na uzamčeném zařízení** – Povolí uživateli přístup k zobrazení oznámení bez odemknutí zařízení.
-     **Passbook na uzamčeném zařízení** – Povolí uživateli přístup k aplikaci Passbook, když je zařízení zamknuté.
-     **Zobrazení Dnes na uzamčené obrazovce** – Povolí uživateli zobrazovat zobrazení Dnes, když je zařízení zamknuté.
-     **Vztah důvěryhodnosti podnikové aplikace** – Umožní uživateli vybrat možnost, že důvěřuje aplikacím, které nebyly staženy z App Storu.
-     **AirDrop (jenom pod dohledem)** – Povolí použití funkce Airdrop k výměně obsahu s blízkými zařízeními.
-     **Vyhledávání Spotlight a vracení výsledků z internetu (jenom pod dohledem)** – Povolí vyhledávání Spotlight připojit se k internetu, aby bylo možné poskytnout další výsledky.
-     **Vyhledávání definic slov (jenom pod dohledem)** – Povolí funkci iOSu, která umožňuje zvýraznit slovo a vyhledat jeho definici.
-     **Prediktivní klávesnice (jenom pod dohledem)** – Povolí používání prediktivních klávesnic, které uživateli navrhují slova, co by se mu mohla hodit.
-     **Automatické opravy (jenom pod dohledem)** – Povolí zařízení automaticky opravovat slova s překlepem.
-     **Kontrola pravopisu klávesnice (jenom pod dohledem)** – Povolí v zařízení kontrolu pravopisu.
-     **Klávesové zkratky (jenom pod dohledem)** – Umožní používání klávesových zkratek.
-     **Detekce zápěstí pro spárované hodinky Apple Watch** – Když se povolí, Apple Watch nebudou zobrazovat oznámení, dokud si je uživatel nenasadí.
- **Vyžadovat párovací heslo pro odchozí požadavky AirPlay** – Vyžaduje párovací heslo, pokud uživatel použije AirPlay ke streamování obsahu do jiných zařízení Apple.
- **Úpravy účtu (jenom pod dohledem)** – Povolí uživateli změnu nastavení účtu, jako je například konfigurace e-mailu.
- **Párování s Apple Watch (jenom pod dohledem)** – Povolí zařízení spárovat se s Apple Watch.
- **Úpravy Bluetooth (jenom pod dohledem)** – Zablokuje koncovému uživateli možnost měnit nastavení Bluetooth na zařízení.
- **Sledování vzdálených obrazovek v aplikaci Classroom (jenom pod dohledem)** – Povolí nebo zablokuje aplikaci Classroom pozorovat obrazovku na vzdálených zařízeních.
- **Povolení omezení v nastavení zařízení (jenom pod dohledem)** – Umožní uživateli na zařízení konfigurovat omezení (rodičovské kontroly).
- **Použití možnosti pro vymazání veškerého obsahu a nastavení na zařízení (jenom pod dohledem)** – Zpřístupní uživateli možnost pro vymazání veškerého obsahu a nastavení na zařízení.
- **Úprava názvu zařízení (jenom pod dohledem)** – Umožní uživateli změnit název zařízení.
- **Úpravy nastavení odesílání diagnostických informací (jenom pod dohledem)** – Povolí nebo zablokuje odesílání diagnostických dat ze zařízení do společnosti Apple.
- **Párování hostitele, aby bylo možné určovat zařízení, se kterými se zařízení s iOSem může spárovat (jenom pod dohledem)** – Povolí hostitelské párování, díky kterému může správce určit, se kterými zařízeními se dá spárovat zařízení s iOSem.
- **Úprava nastavení oznámení (jenom pod dohledem)** – Umožní uživateli přenastavit v zařízení oznámení.
- **Úprava hesla (jenom pod dohledem)** – Povolí přidání, úpravu a odebrání hesla zařízení.
- **Úprava tapety (jenom pod dohledem)** – Umožní uživateli změnit v zařízení tapetu.
- **Úprava nastavení vztahu důvěryhodnosti podnikové aplikace (jenom pod dohledem)** – Umožní uživateli vybrat možnost, že důvěřuje aplikacím, které nebyly staženy z App Storu.
- **Instalace aplikací z App Storu (jenom pod dohledem)** – Povolí zařízení přístup do obchodu s aplikacemi a instalování aplikací.
- **Změny nastavení aplikace Hledat přátele (jenom pod dohledem)** – Umožní uživateli změnu nastavení pro aplikaci Hledat přátele.
- **Obchod iBooks (jenom pod dohledem)** – Umožní uživateli procházení a nákup knih z obchodu iBooks.
- **Aplikace Zprávy na zařízení (jenom pod dohledem)** – Povolí použití aplikace Zprávy k posílání a čtení textových zpráv.
- **Podcasty (jenom pod dohledem)** – Povolí používání aplikace Podcasty.
- **Služba Music (jenom pod dohledem)** – Povolí používání aplikace Apple Music.
- **Služba iTunes Radio (jenom pod dohledem)** – Povolí používání aplikace iTunes Radio.
- **Apple News (jenom pod dohledem)** – Povolí používání aplikace Apple News.
- **Změny profilu konfigurace** – Povolí uživateli instalovat konfigurační profily.

## <a name="password"></a>Heslo
-     **Zadání hesla nutné** – Vyžaduje, aby koncový uživatel zadal heslo k přístupu k zařízení.
-     **Jednoduchá hesla** – Umožňuje použití jednoduchých hesel, jako je třeba 0000 nebo 1234.
-     **Požadovaný typ hesla** – Určuje typ hesla, které se bude vyžadovat, například jenom číslice nebo alfanumerické znaky.
-     **Počet nealfanumerických znaků v hesle** – Určuje počet znaků symbolu (jako například **#** nebo **@**), které musí heslo obsahovat.
-     **Minimální délka hesla** – Určuje minimální počet znaků v hesle.
-     **Počet neúspěšných přihlášení před vymazáním obsahu zařízení** – Určuje počet neúspěšných pokusů o přihlášení, než toto nastavení vymaže zařízení.
-     **Maximální počet minut po uzamčení obrazovky, po kterém bude nutné zadat heslo**<sup>1</sup> – Určuje, jak dlouho může zařízení zůstat nečinné, než uživatel musí znovu zadat heslo.
-     **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**<sup>1</sup> – Určuje počet minut, než se displej zařízení vypne.
-     **Konec platnosti hesla (dny)** – Určuje počet dní, než bude nutné změnit heslo zařízení.
-     **Znemožnit opakované použití předchozích hesel** – Určuje počet dříve použitých hesel, která si zařízení pamatuje.
-     **Odemknutí pomocí otisků prstů** – Povolí odemknutí kompatibilních zařízení pomocí otisku prstu.

<sup>1</sup>Když nakonfigurujete nastavení **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka** a **Maximální počet minut po uzamčení obrazovky, po kterém bude nutné zadat heslo**, použijí se postupně. Pokud například pro obě nastavení nastavíte hodnotu **5** minut, obrazovka se po 5 minutách automaticky vypne a po dalších 5 minutách se zařízení zamkne. Pokud ale uživatel vypne obrazovku ručně, druhé nastavení se použije okamžitě. V tomto příkladě se zařízení po tom, co uživatel vypne obrazovku, zamkne po 5 minutách.

## <a name="app-store-doc-viewing-gaming"></a>App Store, zobrazování dokumentů, hraní her


-   **App Store (jenom pod dohledem)** – Zablokuje přístup k obchodu s aplikacemi v zařízeních pod dohledem.
-     **Heslo pro přístup k obchodu s aplikacemi** – Vyžaduje, aby uživatel zadal heslo, než bude moci navštívit obchod s aplikacemi.
-     **Nákupy v aplikaci** – Povolí ve spuštěné aplikaci nákupy v obchodě.
-     **Automatické stahování aplikací (jenom pod dohledem)** -
-     **Explicitní obsah v hudbě, podcastech nebo zprávách z iTunes (jenom pod dohledem)** – Povolí zařízení přístup k obsahu z obchodu, který je označený jako obsah pro dospělé.
-     **Stahovat obsah z úložiště iBook označený jako Erotika** – Povolí uživateli stahování knih z kategorie Erotika.
-     **Zobrazování firemních dokumentů v nespravovaných aplikacích** – Povolí prohlížení podnikových dokumentů v jakékoliv aplikaci.<br>**Příklad:** Chcete zabránit uživatelům v ukládání souborů z aplikace OneDrive do Dropboxu. U tohoto nastavení vyberte možnost Ne. Až zařízení zásadu obdrží (třeba po restartování), už nebude povolovat ukládání.
-     **Zobrazování nefiremních dokumentů ve firemních aplikacích** – Povolí prohlížení libovolného dokumentu ve spravovaných podnikových aplikacích.
-     **Považovat AirDrop za nespravovaný cíl** – Znemožní spravovaným aplikacím posílat data přes Airdrop.
-     **Přidávání přátel na Game Center (jenom pod dohledem)** – Povolí uživateli přidávat přátele na Game Center.
-     **Game Center (jenom pod dohledem)** – Zablokuje nebo povolí používání aplikace Game Center.
-     **Hry pro více hráčů** – Povolí uživateli hrát na zařízení hry pro více hráčů.
-     **Oblast hodnocení** – Zvolte oblast hodnocení, pro kterou chcete konfigurovat povolené soubory ke stažení, a potom zvolte povolená hodnocení pro **filmy** a **televizní pořady**.
-     **Aplikace** – Zvolte povolená hodnocení aplikací podle věku, které budou uživatelé moct stahovat, nebo můžete zvolit **Povolit všechny aplikace**.

## <a name="restricted-apps"></a>Omezené aplikace

V seznamu omezených aplikací můžete nakonfigurovat jeden z následujících seznamů:

**Zakázané aplikace** – Zobrazí seznam aplikací (nespravovaných pomocí Intune), které nemají uživatelé dovolené nainstalovat a spustit.
**Schválené aplikace** – Zobrazí seznam aplikací, které mají uživatelé dovolené instalovat. Aby byla zachovaná kompatibilita, uživatelé nesmí instalovat aplikace, které nejsou v seznamu. Aplikace, které spravuje Intune, jsou povolené automaticky.

Pokud chcete seznam nakonfigurovat, klikněte na **Přidat**, zadejte libovolný název, volitelně vydavatele aplikace a nakonec adresu URL aplikace v App Storu.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Jak zadat adresu URL pro aplikaci ve Storu

Pokud chcete zadat adresu URL aplikace do seznamu aplikací, použijte následující formát:

Pomocí vyhledávacího modulu najděte aplikaci, kterou chcete použít v iTunes App Storu, a otevřete stránku pro tuto aplikaci.
Zkopírujte adresu URL stránky a použijte ji jako URL ke konfiguraci seznamu povolených a zakázaných aplikací nebo aplikace, kterou chcete spustit v celoobrazovkovém režimu.
Profily zařízení, které obsahují nastavení aplikací s omezeným přístupem, se musí nasadit do skupin uživatelů.

Příklad: Vyhledejte Microsoft Word pro iPad. Použitá adresa URL bude https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> Pomocí softwaru iTunes taky můžete najít aplikaci a pomocí příkazu **Kopírovat odkaz** získat adresu URL aplikace.



### <a name="additional-options"></a>Další možnosti

Můžete také kliknout na **Import** a naplnit seznam ze souboru csv ve formátu <*adresa url aplikace*>, <*název aplikace*>, <*vydavatel aplikace*> nebo kliknout na **Export** a vytvořit si soubor csv obsahující seznam aplikací s omezeným přístupem ve stejném formátu.

## <a name="show-or-hide-apps"></a>Zobrazit nebo skrýt aplikace

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

### <a name="app-information-for-built-in-ios-apps"></a>Informace o aplikaci pro vestavěné aplikace iOS
Informace z tohoto seznamu můžete použít k identifikaci názvu, vydavatele a adresy URL nebo ID sady aplikace pro vestavěné aplikace iOS, které chcete skrýt nebo zobrazit. Pokud chcete zobrazit nebo skrýt všechny aplikace v seznamu, můžete zkopírovat následující data do textového souboru s příponou **.csv** a pak pomocí možnosti **Importovat** naimportovat všechny najednou.


    App Store,Apple,com.apple.AppStore
    Calculator,Apple,com.apple.calculator
    Calendar,Apple,com.apple.mobilecal
    Camera,Apple,com.apple.camera
    Clock,Apple,com.apple.mobiletimer
    Compass,Apple,com.apple.compass
    Contacts,Apple,com.apple.MobileAddressBook
    FaceTime,Apple,com.apple.facetime
    Find Friends,Apple,com.apple.mobileme.fmf1
    Find iPhone,Apple,com.apple.mobileme.fmip1
    Game Center,Apple,com.apple.gamecenter
    GarageBand,Apple,com.apple.mobilegarageband
    Health,Apple,com.apple.Health
    iBooks,Apple,com.apple.iBooks
    iTunes Store,Apple,com.apple.MobileStore
    iTunes U,Apple,com.apple.itunesu
    Keynote,Apple,com.apple.Keynote
    Mail,Apple,com.apple.mobilemail
    Maps,Apple,com.apple.Maps
    Messages,Apple,com.apple.MobileSMS
    Music,Apple,com.apple.Music
    News,Apple,com.apple.news
    Notes,Apple,com.apple.mobilenotes
    Numbers,Apple,com.apple.Numbers
    Pages,Apple,com.apple.Pages
    Photo Booth,Apple,com.apple.Photo-Booth
    Photos,Apple,com.apple.mobileslideshow
    Podcasts,Apple,com.apple.podcasts
    Reminders,Apple,com.apple.reminders
    Safari,Apple,com.apple.mobilesafari
    Settings,Apple,com.apple.Preferences
    Stocks,Apple,com.apple.stocks
    Tips,Apple,com.apple.tips
    Videos,Apple,com.apple.videos
    VoiceMemos,Apple,com.apple.VoiceMemos
    Wallet,Apple,com.apple.Passbook
    Watch,Apple,com.apple.Bridge
    Weather,Apple,com.apple.weather





## <a name="cellular"></a>Mobilní služby
-     **Datový roaming** – Povolí datový roaming, když je zařízení v mobilní síti.
-     **Globální načítání na pozadí při roamingu** – Povolí zařízení, aby při roamingu v mobilní síti načítalo data, třeba e-maily.
-     **Hlasové vytáčení** – Umožňuje používat v zařízení funkci hlasového vytáčení.
-     **Hlasový roaming** – Povolí hlasový roaming, když je zařízení v mobilní síti.
-     **Změny nastavení využití mobilních dat v aplikaci (jenom pod dohledem)** – Umožní uživateli řídit, které aplikace můžou používat mobilní data.

## <a name="cloud-and-storage"></a>Cloud a úložiště
-     **Zálohování do iCloudu** – Povolí uživateli zálohovat zařízení do iCloudu.
-     **Synchronizace dokumentů s iCloudem (jenom pod dohledem)** – Povolí synchronizaci dokumentu a párů klíč-hodnota s úložným prostorem iCloudu.
-     **Synchronizace datového proudu fotografií s iCloudem** – Umožňuje uživatelům povolit na jejich zařízeních **Můj fotostream**, který umožňuje synchronizovat fotky na iCloud, aby byly k dispozici na všech zařízeních uživatelů.
-     **Šifrované zálohování** – Vyžaduje, aby všechny zálohy zařízení byly šifrované.
-     **Knihovna fotografií na iCloudu** – Pokud je možnost nastavená na **Ne**, zakáže použití knihovny fotografií iCloudu, přes kterou můžou uživatelé ukládat fotografie a videa v cloudu.    Všechny fotky, které nejsou kompletně stažené z Knihovny fotografií na iCloudu do zařízení, se ze zařízení odeberou, pokud je tato možnost nastavená na **Ne**.
-     **Synchronizace spravovaných aplikací do cloudu** – Povolí aplikacím, které spravujete přes Intune, synchronizaci dat s uživatelským účtem iCloudu.
-     **Sdílený stream fotek** – Pokud chcete na zařízení zakázat **Sdílení fotek na iCloudu**, nastavte možnost na **Ne**.
-     **Pokračování aktivity** – Umožní uživateli, aby v práci, kterou zahájil na zařízení s iOSem, pokračoval na jiném zařízení s iOSem nebo Mac OS X (Handoff).

## <a name="kiosk"></a>Kiosk
-     **Zámek aktivace** – Povolí zámek aktivace na zařízeních s iOSem, které jsou pod dohledem.
-     **Aplikace, která běží v beznabídkovém režimu** – Zvolte **Spravovaná aplikace** a vyberte aplikaci, kterou jste přidali do Intune, nebo zvolte **Aplikace pro Store** a zadejte adresu URL k aplikaci v úložišti. Žádné jiné aplikace nebudou mít dovoleno se na zařízení spouštět. Další nápovědu najdete v části Určení adres URL na obchody s aplikacemi dál v tomto tématu.
-     **Dotykové ovládání s asistencí** – Povolí nebo zakáže nastavení usnadnění **dotykového ovládání**, která uživateli pomáhá provádět na obrazovce gesta, která by pro něho mohla být obtížná.
-     **Invertovat barvy** – Povolí nebo zakáže nastavení usnadnění Invertovat barvy, které upraví displej tak, aby pomáhal uživatelům se zrakovým postižením.
-     **Monofonní zvuk** – Povolí nebo zakáže nastavení usnadnění Monofonní zvuk.
-     **Hlas na pozadí** – Povolí nebo zakáže nastavení usnadnění **VoiceOver**, které předčítá text na displeji zařízení.
-     **Lupa** – Povolí nebo zakáže nastavení usnadnění **Lupa**, které vám umožní používat na displeji zařízení funkci zvětšení zobrazení dotykem.
-     **Automatické zamykání** – Povolí nebo zakáže automatické zamykání zařízení.
-     **Přepnutí vyzvánění** – Povolí nebo zakáže přepínač vyzvánění (ztlumení) na zařízení.
-     **Otočení obrazovky** – Povolí nebo zakáže změnu orientace obrazovky, když uživatel otočí zařízení.
-     **Tlačítko pro režim spánku obrazovky** – Povolí nebo zakáže na zařízení tlačítko probuzení z režimu spánku obrazovky.
-     **Dotykové ovládání** – Povolí nebo zakáže dotykovou obrazovku na zařízení.
-     **Tlačítka hlasitosti** – Povolí nebo zakáže použití tlačítek hlasitosti na zařízení.
-     **Dotykové ovládání s asistencí** – Povolí nebo zakáže úpravy usnadnění dotykového ovládání, které uživateli umožňují upravit funkce usnadnění dotykového ovládání.
-     **Ovládací prvek Invertovat barvy** – Povolí nebo zakáže úpravy inverze barev, které uživateli umožňují nastavit funkci inverze barev.
-     **Přečíst vybraný text** – Povolí nebo zakáže nastavení usnadnění pro výběr řeči, které může nahlas přečíst text vybraný uživatelem.
-     **Ovládací prvek VoiceOver** – Povolí nebo zakáže úpravy hlasového přednesu, které umožňují nastavit funkci VoiceOver (například rychlost čtení textu na obrazovce).
-     **Ovládání lupy** – Povolí nebo zakáže úpravy zvětšení, které uživateli umožňují nastavit funkci zvětšení.

>[!NOTE]
> Než budete moct nakonfigurovat nastavení zařízení s iOSem pro celoobrazovkový (beznabídkový) režim, musíte převést zařízení do režimu dohledu pomocí nástroje Apple Configurator nebo Programu registrace zařízení Apple. Další informace o nástroji Apple Configurator získáte v dokumentaci Apple.
>Pokud se určená aplikace pro iOS nainstaluje až po nasazení zásad konfigurace, zařízení nepřejde do celoobrazovkového režimu, dokud ho nerestartujete.

## <a name="safari"></a>Safari
-     **Safari (jenom pod dohledem)** – Určuje, jestli se na zařízení může používat prohlížeč Safari.
-     **Automatické vyplňování** – Umožní uživatelům měnit nastavení automatického dokončování v prohlížeči.
-     **Soubory cookie** – Povolí prohlížeči používat soubory cookie.
-     **JavaScript** – Povolí v prohlížeči spouštění skriptů Java.
-     **Upozornění na podvody** – Povolí v prohlížeči upozornění na podvody.
-     **Automaticky otevíraná okna** – Povolí nebo zakáže blokování automaticky otevíraných oken v prohlížeči.

