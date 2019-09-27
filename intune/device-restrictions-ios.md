---
title: nastavení zařízení s iOS v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Přidání, konfigurace nebo vytvoření nastavení na zařízeních s iOS k omezení funkcí, včetně nastavení požadavků na heslo, řízení uzamčené obrazovky, používání integrovaných aplikací, přidávání omezených nebo schválených aplikací, zpracování zařízení Bluetooth, připojení ke cloudu pro zálohování a ukládání, Povolit celoobrazovkový režim, přidat domény a řídit, jak uživatelé pracují s webovým prohlížečem Safari v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/26/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4b9b2db7aa58d2db519615ca2741b28c09f29096
ms.sourcegitcommit: ec0a69c88fdb30b538df1ac4f407a62a28ddf8d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/27/2019
ms.locfileid: "71320031"
---
# <a name="ios-and-ipados-device-settings-to-allow-or-restrict-features-using-intune"></a>nastavení zařízení s iOS a iPadOS pro povolení nebo omezení funkcí pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek obsahuje seznam a popisuje různá nastavení, která můžete řídit na zařízeních s iOS a iPadOS. V rámci řešení pro správu mobilních zařízení (MDM) pomocí těchto nastavení můžete povolit nebo zakázat funkce, nastavit pravidla pro hesla, povolit nebo omezit konkrétní aplikace a další.

Tato nastavení se přidají do konfiguračního profilu zařízení v Intune a pak se přiřadí nebo nasadí na vaše zařízení s iOS.

> [!TIP]
> Tato nastavení používají nastavení MDM od společnosti Apple. Další informace o těchto nastaveních najdete v tématu [Nastavení správy mobilních zařízení společnosti Apple](https://support.apple.com/guide/mdm/welcome/web) (otevření webu společnosti Apple).

## <a name="before-you-begin"></a>Před zahájením

[Vytvoří konfigurační profil omezení zařízení](device-restrictions-configure.md).

> [!NOTE]
> Tato nastavení platí pro různé typy registrace s některými nastaveními, která platí pro všechny možnosti registrace. Další informace o různých typech registrace najdete v tématu Registrace zařízení se [systémem iOS](ios-enroll.md).

## <a name="general"></a>Obecné

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: Všechny typy registrace

- **Sdílet data o využití**: Vyberte možnost **blokovat** , pokud chcete zabránit tomu, aby zařízení odesílalo diagnostická data a data o využití do Applu. **Není nakonfigurováno** (výchozí) povolí odeslání těchto dat.

- **Snímek obrazovky**: Vyberte možnost **blokovat** , pokud chcete zabránit snímku obrazovky nebo snímku obrazovky na zařízení. V iOS 9,0 a novějších blokují také nahrávky obrazovky. **Není nakonfigurováno** (výchozí) umožní uživateli zachytit obsah obrazovky jako obrázek nebo jako video.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Nastavení platí pro: Registrace zařízení, automatický zápis zařízení (pod dohledem)

- **Nedůvěryhodné certifikáty TLS**: Vyberte možnost **blokovat** , pokud chcete zabránit nedůvěryhodným certifikátům TLS (Transport Layer Security) na zařízení. **Není nakonfigurováno** (výchozí) povolí certifikáty TLS.
- **Povolení vysoce doletových aktualizací PKI**: Možnost **povolí** uživatelům umožňuje přijímat aktualizace softwaru bez připojení zařízení k počítači.
- **Omezení sledování reklamy**: Zvolením možnosti **omezit** zakažte identifikátor inzerce zařízení. **Není nakonfigurováno** (výchozí) udržuje povolený.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

- **Úprava nastavení odeslání diagnostiky**: **Blok** znemožní uživateli měnit nastavení odesílání diagnostiky a analýzy aplikací v části **Diagnostika a využití** (nastavení zařízení). **Není nakonfigurováno** (výchozí) umožní uživateli změnit tato nastavení zařízení.

  Chcete-li použít toto nastavení, nastavte nastavení **sdílet data o využití** pro **blokování**.

  Tato funkce platí pro:  
  - iOS 9.3.2 a novější

- **Sledování vzdálené obrazovky podle aplikace učebny**: Vyberte možnost **blokovat** , pokud chcete aplikaci učebny zabránit ve vzdáleném zobrazení obrazovky na zařízení. **Není nakonfigurováno** (výchozí) umožňuje aplikaci Apple učeben zobrazit obrazovku.

  Chcete-li použít toto nastavení, nastavte nastavení **zachycení obrazovky** na **blokovat**.

  Tato funkce platí pro:  
  - iOS 9,3 a novější

- **Nezobrazilo se sledování obrazovky podle aplikace učebny**: Pokud je nastaveno na **Povolit**, učitelé můžou tiše sledovat obrazovku zařízení s iOS studenty pomocí aplikace učebny bez vědomí vašeho studenta. Studentská zařízení zaregistrovaná ve třídě pomocí aplikace učebny automaticky poskytnou oprávnění učiteli tohoto kurzu. **Není nakonfigurováno** (výchozí) zabrání této funkci.

  Chcete-li použít toto nastavení, nastavte nastavení **zachycení obrazovky** na **blokovat**.

- **Vztah důvěryhodnosti podnikových aplikací**: Vyberte možnost **blokovat** , pokud chcete v nastavení odebrat tlačítko **důvěřovat Enterprise Developer** , > Obecné profily > & správu zařízení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje uživateli zvolit důvěřování aplikacím, které se nestahují z App Storu.
- **Úprava účtu**: Když se tato možnost nastaví na **blokovat**, nemůže uživatel aktualizovat nastavení specifická pro zařízení z aplikace nastavení pro iOS. Uživatel například nemůže vytvořit nové účty zařízení nebo změnit uživatelské jméno nebo heslo. **Není nakonfigurováno** (výchozí) umožňuje uživatelům změnit tato nastavení.

  Tato funkce se vztahuje také na nastavení přístupná z aplikace nastavení pro iOS, jako je pošta, kontakty, kalendář, Twitter a další. Tato funkce se nevztahuje na aplikace s nastavením účtu, které nemůžete konfigurovat z aplikace nastavení pro iOS, jako je například aplikace Microsoft Outlook.

- **Čas obrazovky**: Vyberte možnost **blokovat** , pokud chcete uživatelům zabránit v nastavení vlastních omezení na obrazovce čas (nastavení zařízení). **Není nakonfigurováno** umožňuje uživateli nakonfigurovat na zařízení omezení zařízení (například Rodičovská kontrola nebo obsah a omezení ochrany osobních údajů).

  Toto nastavení bylo přejmenováno z **možnosti Povolit omezení v nastavení zařízení**. Dopad této změny:  
  
  - iOS 11.4.1 a starší: **Blok** zabraňuje koncovým uživatelům v nastavení zařízení v nastavení vlastních omezení. Chování je stejné. a pro koncové uživatele nejsou žádné změny.
  - iOS 12,0 a novější: **Blok** znemožní koncovým uživatelům nastavit vlastní **čas na obrazovku** v nastavení zařízení (nastavení > Obecné > čas obrazovky), včetně omezení obsahu a ochrany osobních údajů. V zařízeních upgradovaných na iOS 12,0 se už v nastavení zařízení nezobrazí karta omezení (Nastavení > Obecné > Správa zařízení > > omezení profilu správy. Tato nastavení se nacházejí v **čase obrazovky**.
  
- **Použití možnosti pro vymazání veškerého obsahu a nastavení na zařízení**: Vyberte možnost **blokovat** , aby uživatelé nemohli na zařízení používat možnost pro vymazání veškerého obsahu a nastavení. **Není nakonfigurováno** (výchozí) udělí uživatelům přístup k těmto nastavením.
- **Úprava názvu zařízení**: Vyberte možnost **blokovat** , aby se název zařízení nemohl změnit. **Není nakonfigurováno** (výchozí) umožní uživateli změnit název zařízení.
- **Úprava nastavení oznámení**: Vyberte možnost **blokovat** , takže nastavení oznámení nelze změnit. **Není nakonfigurováno** (výchozí) umožní uživateli změnit nastavení oznámení o zařízení.
- **Úprava tapety**: **Blok** brání v změně tapety. **Není nakonfigurováno** (výchozí) umožní uživateli změnit tapetu na zařízení.
- **Úprava nastavení vztahu důvěryhodnosti podnikových aplikací**: **Blok** znemožní uživateli měnit nastavení vztahu důvěryhodnosti podnikových aplikací na zařízeních pod dohledem. **Není nakonfigurováno** (výchozí) povolí uživateli důvěřovat aplikacím, které se nestahují z App Storu.
- **Změny profilu konfigurace**: **Blok** zabraňuje změnám profilu konfigurace na zařízení. **Není nakonfigurováno** (výchozí) umožní uživateli instalovat konfigurační profily.
- **Zámek aktivace**: Pokud chcete povolit Zámek aktivace na zařízeních s iOS pod dohledem, vyberte **Povolit** . Zámek aktivace znemožňuje opětovné aktivaci ztraceného nebo odcizeného zařízení.
- **Blokovat odebrání aplikace**: Vyberte možnost **blokovat** , pokud chcete uživatelům zabránit v odebírání aplikací. **Není nakonfigurováno** (výchozí) umožňuje uživatelům odebrat aplikace ze zařízení.
- **Zakázaný režim USB bloků**: Zvolením možnosti **blokovat** zakážete režim omezeného portu USB na zařízeních pod dohledem. Režim omezeného USB brání příslušenství USB v výměně dat se zařízením, které je po celou hodinu uzamčené. **Není nakonfigurováno** (výchozí) umožňuje režim s omezeným přístupem USB.
- **Vynutit automatické datum a čas**: **Vyžadovat** , aby zařízení, která jsou pod dohledem, automaticky nastavila data &ho času. Časové pásmo zařízení se aktualizuje, když má zařízení mobilní připojení nebo má Wi-Fi s povolenými službami zjišťování polohy.
- **Vyžadovat, aby studenti požádali o oprávnění k opuštění kurzu učebnosti**: **Vyžadovat** , aby studenti zaregistrovaní v nespravovaném kurzu pomocí aplikace učeben požádali o oprávnění od učitelů k opuštění tohoto kurzu. **Není nakonfigurováno** (výchozí) nenutí studenta požádat o oprávnění.

  Tato funkce platí pro:  
  - iOS 11,3 a novější

- **Povolit učebně zamknout aplikaci a uzamknout zařízení bez zobrazení výzvy**: **Možnost Povolit** učitelům umožňuje uzamknout aplikace nebo zamknout zařízení pomocí aplikace učebny bez vyzvání studenta. Uzamykání aplikací znamená, že zařízení může přistupovat jenom k aplikacím určeném pro učitele. **Není nakonfigurováno** (výchozí) znemožní učitelům uzamknout aplikace nebo zařízení pomocí aplikace učebny bez vyzvání studenta. 

  Tato funkce platí pro:  
  - iOS 11,0 a novější

- **Automaticky spojit třídy učeben bez zobrazení výzvy**: **Možnost Povolit** automaticky umožňuje studentům připojovat se ke třídě, která je v aplikaci učebny, bez zobrazení výzvy učitelům. **Není nakonfigurováno** (výchozí) vyzve učitele, aby se studenti chtěli připojit ke třídě, která je v aplikaci učeben.

  Tato funkce platí pro:  
  - iOS 11,0 a novější

- **Blokovat vytvoření sítě VPN**: **Blok** zabraňuje uživatelům v vytváření nastavení konfigurace sítě VPN. **Není nakonfigurováno** (výchozí) umožňuje uživatelům vytvářet v zařízení sítě VPN.
- **Mění se nastavení eSIM karty**: **Blok** zabraňuje uživatelům v zařízení odebrat nebo přidat plán pro mobilní zařízení do eSIM karty. **Není nakonfigurováno** (výchozí) umožňuje uživatelům změnit tato nastavení.

  Tato funkce platí pro:  
  - iOS 12,1 a novější

- **Odložit aktualizace softwaru**: Pokud je nastavené na **Nenakonfigurováno** (výchozí nastavení), v zařízení se zobrazí aktualizace softwaru, které Apple uvolňuje. Pokud se třeba aktualizace pro iOS uvolní od společnosti Apple na konkrétní datum, pak se tato aktualizace přirozeně zobrazuje na zařízení v datu vydání verze.

  **Možnost Povolit** umožňuje prodlevu při zobrazení aktualizací softwaru na zařízeních, od 0-90 dnů. Toto nastavení neřídí, kdy jsou aktualizace nebo nejsou nainstalovány. 

  - **Zpoždění viditelnosti aktualizací softwaru**: Zadejte hodnotu od 0-90 dnů. Po vypršení zpoždění budou uživatelé dostávat oznámení o aktualizaci na nejstarší verzi operačního systému, která je k dispozici při spuštění zpoždění.

    Pokud je například iOS 12. a k dispozici **1. ledna**a je **zpoždění viditelnosti** nastaveno na **5 dní**, pak se iOS 12. a nezobrazí jako dostupná aktualizace na zařízeních koncových uživatelů. Po **šestém dni** od vydání je tato aktualizace dostupná a koncoví uživatelé ji můžou nainstalovat.

    Toto nastavení platí pro:  
    - iOS 11,3 a novější

## <a name="password"></a>Heslo

> [!NOTE]
> V budoucí verzi se tato nastavení hesla v uživatelském rozhraní Intune aktualizují tak, aby odpovídala typu registrace.

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: Všechny typy registrace

- **Heslo**: **Vyžaduje** , aby koncový uživatel zadal heslo pro přístup k zařízení. **Není nakonfigurováno** (výchozí) umožňuje uživatelům přístup k zařízení bez zadání hesla.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Nastavení platí pro: Registrace zařízení, automatický zápis zařízení (pod dohledem)

> [!IMPORTANT]
> Pokud u zařízení zaregistrovaných uživatelem nakonfigurujete nastavení hesla, budou jednoduchá nastavení **hesla** automaticky nastavená tak, aby se **zablokovala**, a bude vynucený kód PIN s 6 číslicemi.
>
> Například nakonfigurujete nastavení **vypršení platnosti hesla** a tuto zásadu nahrajete do zařízení zaregistrovaných uživatelem. V zařízeních dojde k následujícímu:
>
>  - Nastavení **vypršení platnosti hesla** je ignorováno.
>  - Jednoduchá hesla, například `1111` nebo `1234`, nejsou povolena.
>  - Je vynutil kód PIN pro číslice 6. 

- **Jednoduchá hesla**: Vyberte možnost **blokovat** pro vyžadování složitějších hesel. **Nenakonfigurováno** umožňuje jednoduchá hesla, jako `0000` jsou `1234`a.

- **Požadovaný typ hesla**: Vyberte typ hesla, které vaše organizace vyžaduje. Možnosti:
    - **Výchozí ze zařízení**
    - **Číselné**
    - **Písmena**
- **Počet nealfanumerických znaků v hesle**: Zadejte počet znaků symbolu, například `#` nebo `@`, které musí heslo obsahovat.

- **Minimální délka hesla**: Zadejte minimální délku, kterou musí uživatel zadat, a to v rozmezí 4 až 14 znaků. Do zařízení zaregistrovaných uživatelem zadejte délku 4 až 6 znaků.
  
  > [!NOTE]
  > U zařízení, která jsou zaregistrovaná uživatelem, můžou uživatelé nastavit PIN kód o více než 6 číslic. V zařízení se ale neuplatní více než 6 číslic. Správce například nastaví minimální délku na `8`. U zařízení zaregistrovaných uživatelem se uživatelům vyžaduje jenom zadání kódu PIN pro 6 číslic. Intune nevynutí na uživatelem zaregistrovaná zařízení kód PIN delší než 6 číslic.

- **Počet neúspěšných přihlášení před vymazáním zařízení**: Zadejte počet neúspěšných přihlášení, než se zařízení vymaže (mezi 4-11).
  
  iOS má integrované zabezpečení, které může mít vliv na toto nastavení. IOS může například zpozdit spuštění zásad v závislosti na počtu neúspěšných přihlášení. Může také zvážit opakované zadání stejného hesla jako jednoho pokusu. [Příručka zabezpečení iOS](https://www.apple.com/business/site/docs/iOS_Security_Guide.pdf) společnosti Apple (Otevírá web společnosti Apple) je dobrým prostředkem a poskytuje konkrétnější údaje o heslech.
  
- **Maximální počet minut po uzamčení obrazovky před vyžadováním hesla** <sup>1</sup>: Zadejte, jak dlouho zůstane zařízení nečinné, než uživatel musí znovu zadat heslo. Pokud je čas, který zadáte, delší dobu, než je aktuálně nastaveno na zařízení, zařízení bude ignorovat čas, který zadáte. Podporováno v zařízeních iOS 8,0 a novějších.
- **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka** <sup>1</sup>: Zadejte maximální počet minut nečinnosti, která je povolena v zařízení, dokud se nezamkne obrazovka. Pokud je čas, který zadáte, delší dobu, než je aktuálně nastaveno na zařízení, zařízení bude ignorovat čas, který zadáte. Když se nastaví na hodnotu **okamžitě**, obrazovka se zamkne na základě minimálního času zařízení. Na iPhonu je 30 sekund. Na iPadu je to dvě minuty.
- **Vypršení platnosti hesla (dny)** : Zadejte počet dní, než bude nutné změnit heslo zařízení.
- **Zakázat opakované použití předchozích hesel**: Zadejte počet nových hesel, která se musí použít, až pak bude možné znovu použít starou jinou.
- **Dotykové ID a odemknutí ID obličeje**: Vyberte možnost **blokovat** , pokud chcete zabránit použití otisku prstu nebo obličeje k odemknutí zařízení. **Není nakonfigurováno** umožňuje uživateli odemknout zařízení pomocí těchto metod.

  Blokování tohoto nastavení také znemožňuje zařízení odemknout pomocí ověřování FaceID.

  ID obličeje platí pro:  
  - iOS 11,0 a novější

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

- **Úprava hesla**: Vyberte možnost **blok** a zastavte změnu, přidání nebo odebrání hesla. Po blokování této funkce se změny v omezeních hesla ignorují na zařízeních pod dohledem. **Není nakonfigurováno** (výchozí) umožňuje přidávat, měnit a odebírat hesla.

  - **Dotykové ID a úprava ID obličeje**: **Blok** zastaví uživateli měnit, přidávat nebo odebírat otisky prstů TOUCHID a ID obličeje. **Není nakonfigurováno** (výchozí) umožní uživateli aktualizovat otisky prstů TouchID a ID obličeje na zařízení.

    Blokování tohoto nastavení také uživateli brání v změně, přidání nebo odebrání ověřování FaceID.

    ID obličeje platí pro:  
    - iOS 11,0 a novější

- **Zablokovat automatické vyplňování hesla**: Vyberte možnost **blokovat** , pokud chcete zabránit použití funkce automatického vyplňování hesel v iOS. Výběr **bloku** má také následující dopad:

  - Uživatelům se nezobrazí výzva k použití uloženého hesla v Safari nebo ve všech aplikacích.
  - Automatická silná hesla jsou zakázaná a silná hesla se uživatelům nedoporučují.

  **Není nakonfigurováno** (výchozí) tyto funkce povolují.

- **Zablokovat žádosti o blízkost hesla**: Zvolit **blok** , aby zařízení uživatele nepožadovalo hesla z blízkých zařízení. **Není nakonfigurováno** (výchozí) povolí tyto požadavky na heslo.
- **Zablokovat sdílení hesla**: **Blok** zabraňuje sdílení hesel mezi zařízeními pomocí přetažení. **Není nakonfigurováno** (výchozí) umožňuje sdílet hesla.
- **Pro automatické vyplňování informací pro heslo nebo platební kartu vyžadovat ověřování Touch ID nebo obličeje**: Když se nastaví na **vyžadovat**, musí se uživatelé ověřit pomocí TouchID nebo FaceID, než se hesla nebo informace o kreditních kartách dají automaticky vyplnit v Safari a dalších aplikacích. **Není nakonfigurováno** (výchozí) umožňuje uživatelům řídit tuto funkci v nastavení zařízení.

  Tato funkce platí pro:  
  - iOS 11,0 a novější
  
<sup>1</sup> Když nakonfigurujete **maximální počet minut nečinnosti** , po kterém se zamkne obrazovka a **maximální počet minut po uzamčení obrazovky, které se budou povinně** použít, použije se v uvedeném pořadí. Pokud například nastavíte hodnotu pro obě nastavení na **5** minut, obrazovka se vypne automaticky po pěti minutách a zařízení se zamkne po dalších pět minut. Pokud ale uživatel vypne obrazovku ručně, druhé nastavení se použije okamžitě. Ve stejném příkladu potom, co uživatel vypne obrazovku, zařízení zamkne pět minut později.

## <a name="locked-screen-experience"></a>Prostředí zamknuté obrazovky

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: Všechny typy registrace

- **Přístup k řídicímu centru, když je zařízení uzamčené**: Vyberte možnost **blokovat** , pokud chcete zabránit přístupu k aplikaci řídicího centra, když je zařízení zamčené. **Není nakonfigurováno** (výchozí) umožňuje uživatelům přístup k aplikaci řídicího centra, když je zařízení zamčené.
- **Oznámení, když je zařízení uzamčené**: **Blok** zabraňuje přístupu k oznámením, když je zařízení zamčené. **Není nakonfigurováno** (výchozí) umožňuje uživateli přístup k oznámením bez odemknutí zařízení.
- **Zobrazení dnes, když je zařízení uzamčené**: **Blok** znemožní přístup k zobrazení dnes, když je zařízení zamčené. **Není nakonfigurováno** (výchozí) umožní uživateli zobrazit zobrazení dnes, když je zařízení zamčené.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Nastavení platí pro: Registrace zařízení, automatický zápis zařízení (pod dohledem)

- **Oznámení peněženky, když je zařízení uzamčené**: **Blok** znemožní přístup k aplikaci peněženky, když je zařízení zamčené. **Není nakonfigurováno** (výchozí) umožňuje uživateli přístup k aplikaci peněženky, když je zařízení zamčené.

## <a name="app-store-doc-viewing-gaming"></a>App Store, zobrazování dokumentů, hraní her

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: Všechny typy registrace

- **Zobrazení firemních dokumentů v nespravovaných aplikacích**: **Blok** zabraňuje zobrazení firemních dokumentů v nespravovaných aplikacích. **Není nakonfigurováno** (výchozí) umožňuje zobrazení podnikových dokumentů v libovolné aplikaci. Například chcete zabránit uživatelům v ukládání souborů z aplikace OneDrive do Dropboxu. Nakonfigurujte toto nastavení jako **blok**. Jakmile zařízení obdrží zásady (například po restartování), už neumožňuje uložení.

  - **Povoluje čtení nespravovaných aplikací ze spravovaných účtů kontaktů**: Když nastavíte možnost **Povolení**, můžou nespravované aplikace, jako je integrovaná aplikace kontaktů pro iOS, číst a přistupovat k kontaktním informacím ze spravovaných aplikací, včetně mobilní aplikace Outlook. **Není nakonfigurováno** (výchozí) zabraňuje čtení, včetně odebrání duplicit, z integrované aplikace kontaktů na zařízení.  
  
    Toto nastavení povoluje nebo znemožňuje čtení kontaktních informací. Neřídí synchronizaci kontaktů mezi aplikacemi.
  
    Pokud chcete použít toto nastavení, nastavte možnost **zobrazení firemních dokumentů v nespravovaných aplikacích** na **blokovat**.

  Další informace o těchto dvou nastaveních a jejich dopad na Outlook pro iOS synchronizace exportů najdete v tématu [podpora – Tip: Použijte nastavení vlastního profilu Intune s aplikací](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Use-Intune-custom-profile-settings-with-the-iOS/ba-p/298453)pro nativní kontakty pro iOS.

- **Považovat přetažení za nespravovaný cíl**: **Vyžadovat** , aby se přetažení prodalo považovat za nespravovaný cíl přetažení. Zastaví spravované aplikace z odesílání dat pomocí přetažení. 
- **Zobrazení nefiremních dokumentů v podnikových aplikacích**: **Blok** zabraňuje zobrazování nefiremních dokumentů v podnikových aplikacích. **Není nakonfigurováno** (výchozí) umožňuje zobrazit libovolný dokument v podnikových spravovaných aplikacích.

  Nastavení **blokování** taky brání synchronizaci exportu kontaktů v Outlooku pro iOS. Další informace najdete v [popisu podpory: Povolení synchronizace kontaktů pro iOS v Outlooku s](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Enabling-Outlook-iOS-Contact-Sync-with-iOS12-MDM/ba-p/298453)ovládacími prvky iOS12 MDM

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Nastavení platí pro: Registrace zařízení, automatický zápis zařízení (pod dohledem)

- **Vyžadovat heslo pro iTunes Store pro všechny nákupy**: **Vyžaduje** , aby uživatel zadal heslo Apple ID pro každý nákup v aplikaci nebo iTunes. **Není nakonfigurováno** (výchozí) umožňuje nákupy bez výzvy k zadání hesla pokaždé, když.
- **Nákupy v aplikaci**: Zvolením možnosti **blokovat** zabráníte nákupům v aplikaci ze Storu. **Není nakonfigurováno** (výchozí) umožňuje nákup obchodů v běžící aplikaci.
- **Stáhnout obsah z obchodu iBooks Storu označeného jako ' Erotika '** : Vyberte možnost **blokovat** , pokud chcete zabránit uživatelům v stahování médií z úložiště obchodu iBooks, které je označeno jako erotika. **Není nakonfigurováno** (výchozí) umožní uživateli stahovat knihy s kategorií "Erotika".
- **Povoluje spravovaným aplikacím psát kontakty na nespravované účty kontaktů**: Když nastavíte možnost **Povolení**, spravované aplikace, jako je například mobilní aplikace Outlook, můžou ukládat nebo synchronizovat kontaktní informace, včetně obchodních a firemních kontaktů, do integrované aplikace pro kontakty iOS. Pokud je nastavené na **Nenakonfigurováno** (výchozí), spravované aplikace nemůžou ukládat ani synchronizovat kontaktní informace na integrované aplikaci kontaktů pro iOS na zařízení.
  
  Pokud chcete použít toto nastavení, nastavte možnost **zobrazení firemních dokumentů v nespravovaných aplikacích** na **blokovat**.

- **Oblast hodnocení**: Vyberte oblast hodnocení, kterou chcete použít pro povolené soubory ke stažení. A pak zvolte povolené hodnocení **filmů**, **televizních**pořadů a **aplikací**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

- **App Store**: **Blok** zabraňuje přístupu k obchodu s aplikacemi na zařízeních pod dohledem. **Není nakonfigurováno** (výchozí) umožňuje přístup.

  Od iOS 13,0 Toto nastavení vyžaduje zařízení pod dohledem.

  - **Instalují se aplikace z App Storu**: Zvolit **blok** pro blokování obchodu s aplikacemi z domovské obrazovky zařízení. Koncoví uživatelé můžou aplikace dál instalovat pomocí iTunes nebo Apple Configuratoru. **Není nakonfigurováno** (výchozí) povolí App Storu na domovské obrazovce.
  - **Automatické stahování aplikací**: Vyberte možnost **blokovat** , pokud chcete zabránit automatickému stahování aplikací zakoupených na jiných zařízeních. Nemá vliv na aktualizace existujících aplikací. **Není nakonfigurováno** (výchozí) umožňuje, aby se aplikace nakoupily na jiných zařízeních iOS ke stažení na zařízení.

- **Explicitní obsah v hudbě, podcastech nebo zprávách v iTunes**: Zvolením možnosti **blokovat** zabráníte explicitnímu obsahu v hudbě, podcastech nebo novinkách iTunes. **Není nakonfigurováno** (výchozí) povolí zařízení přístup k obsahu, který je hodnocen jako dospělý ze Storu. iOS 13 a novější můžou vyžadovat jenom zařízení pod dohledem. 

  Od iOS 13,0 Toto nastavení vyžaduje zařízení pod dohledem.

- **Přidávání přátel Game Center**: **Blok** zabraňuje uživatelům přidávat Game Center přátelé. **Není nakonfigurováno** (výchozí) umožní uživateli přidávat přátele do Game Center.

  Od iOS 13,0 Toto nastavení vyžaduje zařízení pod dohledem.

- **Game Center**: **Zablokuje** použití aplikace Game Center. **Není nakonfigurováno** (výchozí) umožňuje použití aplikace Game Center v zařízení.
- **Hry pro více hráčů**: Zvolením možnosti **blokovat** zabráníte hraní her s více hráči. **Není nakonfigurováno** (výchozí) umožní uživateli hrát na zařízení hry pro více hráčů.

  Od iOS 13,0 Toto nastavení vyžaduje zařízení pod dohledem.

## <a name="built-in-apps"></a>Integrované aplikace

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: Všechny typy registrace

- **Siri**: **Blok** znemožňuje přístup k Siri. **Není nakonfigurováno** (výchozí) umožňuje použití hlasového asistenta Siri na zařízení.
  - **Siri, když je zařízení uzamčené**: Vyberte možnost **blokovat** , pokud chcete zabránit přístupu k Siri, když je zařízení zamčené. **Není nakonfigurováno** (výchozí) povolí použití hlasového asistenta Siri na zařízení, když je zamčený.

- **Upozornění na podvod v Safari**: **Vyžaduje** zobrazení upozornění na podvod ve webovém prohlížeči na zařízení. **Nenakonfigurováno** (výchozí) tuto funkci zakáže.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Nastavení platí pro: Registrace zařízení, automatický zápis zařízení (pod dohledem)

- **Vyhledávání Spotlightu, které vrátí výsledky z Internetu**: **Zablokování** zastaví vrácení jakýchkoli výsledků z hledání na internetu z Spotlightu. **Není nakonfigurováno** (výchozí) umožňuje vyhledávání Spotlightu připojit se k Internetu a poskytnout tak výsledky hledání.

- **Soubory cookie prohlížeče Safari**: Vyberte, jak se mají na zařízení zpracovávat soubory cookie. Možnosti:
  - Allow
  - Blokovat všechny soubory cookie
  - Povolení souborů cookie z navštívených webů
  - Povoluje soubory cookie z aktuálního webu

- **JavaScript Safari**: **Blok** zabraňuje spuštění skriptů Java v prohlížeči v zařízení. **Není nakonfigurováno** (výchozí) povolí skripty Java.

- **Automaticky otevíraná okna Safari**: **Blok** pro zakázání blokování automaticky otevíraných oken ve webovém prohlížeči. **Není nakonfigurováno** (výchozí) povolí blokování automaticky otevíraných oken.

- **Protokolování na straně serveru pro příkazy Siri**: Pokud je nastavení **zakázáno**, protokolování Siri na straně serveru je vypnuté. Může také bránit protokolování požadavků uživatelů na servery Siri. **Není nakonfigurováno** (výchozí) protokoluje příkazy Siri na straně serveru. Toto nastavení není závislé na nastavení Siri, které je blokováno nebo není nakonfigurováno.

  Tato funkce platí pro:  
  - iOS 12,2 a novější

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

- **Kamera**: Vyberte možnost **blokovat** , pokud chcete zabránit přístupu k fotoaparátu na zařízení. **Není nakonfigurováno** (výchozí) povolí přístup k kameře zařízení.

  Od iOS 13,0 Toto nastavení vyžaduje zařízení pod dohledem.

  - **FaceTime**: **Zablokuje** , aby se zabránilo přístupu k aplikaci FaceTime. **Není nakonfigurováno** (výchozí) povolí přístup k aplikaci FaceTime na zařízení.

    Od iOS 13,0 Toto nastavení vyžaduje zařízení pod dohledem.

- **Filtr vulgárních výrazů v Siri**: **Vyžadovat, aby** se v Siri zabránilo diktování nebo řeči vulgárního jazyka.

  Chcete-li použít toto nastavení, nastavte nastavení **Siri** na **blokovat**.

- **Siri dotazování na uživatelem generovaný obsah z Internetu**: **Blok** zabraňuje Siri přístupu k webům, aby mohla odpovídat na otázky. **Není nakonfigurováno** (výchozí) umožňuje Siri přistupovat k obsahu generovanému uživateli z Internetu.

  Chcete-li použít toto nastavení, nastavte nastavení **Siri** na **blokovat**.

- **Apple News**: Vyberte možnost **blokovat** , aby se zabránilo přístupu k aplikaci Apple News na zařízení. **Není nakonfigurováno** (výchozí) umožňuje použití aplikace Apple News.
- **iBooks Store**: **Blok** znemožňuje přístup k úložišti iBooks. **Není nakonfigurováno** (výchozí) umožňuje uživatelům procházet a kupovat knihy z iBooks Storu.
- **Aplikace zprávy na zařízení**: **Blok** zabraňuje uživatelům v používání aplikace zprávy pro iMessage. Pokud zařízení podporuje textové zasílání zpráv, může uživatel i nadále odesílat a přijímat textové zprávy pomocí serveru SMS. **Není nakonfigurováno** (výchozí) umožňuje použití aplikace zprávy k posílání a čtení zpráv přes Internet.
- **Podcasty**: **Blok** zabraňuje uživatelům používat aplikaci Podcasty. **Není nakonfigurováno** (výchozí) umožňuje použití aplikace Podcasty.
- **Hudební služba**: **Blok** vrátí aplikaci Hudba do klasického režimu a zakáže hudební službu. **Není nakonfigurováno** (výchozí) umožňuje použití aplikace Apple Music.
- **služba iTunes Radio**: **Blok** zabraňuje uživatelům v používání aplikace iTunes Radio. **Není nakonfigurováno** (výchozí) umožňuje používat aplikaci iTunes Radio.
- **iTunes Store**: **Není nakonfigurováno** (výchozí) povolí iTunes na zařízeních. **Blok** zabraňuje uživatelům v zařízení používat iTunes. 

  Tato funkce platí pro:  
  - iOS 4,0 a novější

- **Najít iPhone**: **Není nakonfigurováno** (výchozí) umožňuje pomocí této funkce najít moji aplikaci získat přibližnou polohu zařízení. **Blok** zabraňuje této funkci v aplikaci najít moji. 

  Tato funkce platí pro:  
  - iOS 13,0 a iPadOS 13,0 a novější

- **Najít přátele**: **Není nakonfigurováno** (výchozí) umožňuje pomocí této funkce najít moji aplikaci najít rodinu a přátele ze zařízení Apple nebo iCloud.com. **Blok** zabraňuje této funkci v aplikaci najít moji.

  Tato funkce platí pro:  
  - iOS 13,0 a iPadOS 13,0 a novější

- **Změny v nastavení aplikace Find My Friends**: **Blok** znemožňuje změny v nastavení aplikace Find My Friends. **Není nakonfigurováno** (výchozí) umožní uživateli změnit nastavení pro aplikaci najít přátele.

- **Vyhledávání Spotlightu, které vrátí výsledky z Internetu**: **Zablokování** zastaví vrácení jakýchkoli výsledků z hledání na internetu z Spotlightu. **Není nakonfigurováno** (výchozí) umožňuje vyhledávání Spotlightu připojit se k Internetu a poskytnout tak výsledky hledání.

- **Blokovat odebírání systémových aplikací ze zařízení**: Volba možnosti **blokovat** zakáže možnost odebrání systémových aplikací ze zařízení. **Není nakonfigurováno** (výchozí) umožňuje uživatelům odebrat systémové aplikace.

- **Safari**: **Blokuje** používání prohlížeče Safari na zařízení. **Není nakonfigurováno** (výchozí) umožňuje uživatelům používat prohlížeč Safari.

  Od iOS 13,0 Toto nastavení vyžaduje zařízení pod dohledem.

- **Automatické vyplňování prohlížeče Safari**: **Blok** zakáže funkci automatického vyplňování v prohlížeči Safari na zařízení. **Není nakonfigurováno** (výchozí) umožňuje uživatelům změnit nastavení automatického dokončování ve webovém prohlížeči.

  Od iOS 13,0 Toto nastavení vyžaduje zařízení pod dohledem.

## <a name="restricted-apps"></a>Omezené aplikace

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Nastavení platí pro: Registrace zařízení, automatický zápis zařízení (pod dohledem)

- **Typ seznamu omezených aplikací**: Vytvoří seznam aplikací, které uživatelé nemůžou instalovat ani používat. Možnosti:

  - **Není nakonfigurováno** (výchozí): Neexistují žádná omezení od Intune. Uživatelé mají přístup k aplikacím, které přiřadíte, a k integrovaným aplikacím.
  - **Zakázané aplikace**: Aplikace nespravované přes Intune, které nechcete instalovat na zařízení. Uživatelům není instalace zakázané aplikace znemožněna. Pokud ale uživatel z tohoto seznamu nainstaluje aplikaci, nahlásí se v Intune.
  - **Schválené aplikace**: Aplikace, které můžou uživatelé instalovat. Uživatelé nesmí instalovat aplikace, které nejsou uvedené. Aplikace, které spravuje Intune, jsou povolené automaticky. Uživatelům není znemožněna instalace aplikace, která není na seznamu schválených. Pokud tomu tak je, nahlásí se v Intune.

Pokud chcete do těchto seznamů přidat aplikace, můžete:

- **Přidejte** adresu URL obchodu iTunes pro aplikaci, kterou chcete. Pokud například chcete přidat aplikaci Microsoft work folders, zadejte `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` nebo. `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

  Pokud chcete najít adresu URL aplikace, otevřete aplikaci iTunes App Store a vyhledejte aplikaci. Vyhledejte `Microsoft Remote Desktop` například nebo `Microsoft Word`. Vyberte aplikaci a zkopírujte adresu URL.

  K vyhledání aplikace můžete také použít iTunes a potom pomocí úlohy **Kopírovat odkaz** získat adresu URL aplikace.

- **Importujte** soubor CSV s podrobnostmi o aplikaci, včetně adresy URL. Použijte formát `<app url>, <app name>, <app publisher>`. Případně **exportujte** existující seznam obsahující seznam aplikací s omezeným přístupem ve stejném formátu.

> [!IMPORTANT]
> Profily zařízení, které používají nastavení aplikací s omezeným přístupem, se musí přiřadit ke skupinám uživatelů.

## <a name="show-or-hide-apps"></a>Zobrazit nebo skrýt aplikace

Platí pro zařízení se systémem iOS 9,3 nebo novějším.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

- **Typ seznamu aplikací**: Vytvořte seznam aplikací, které chcete zobrazit nebo skrýt. Možnosti:

  - **Skryté aplikace**: Zadejte seznam aplikací, které jsou pro uživatele skryté. Uživatelé nemůžou tyto aplikace zobrazit ani otevřít.
  - **Viditelné aplikace**: Zadejte seznam aplikací, které uživatelé mohou zobrazit a spustit. Žádné jiné aplikace nebude možné zobrazit ani spustit.

- **Adresa URL aplikace**: Zadejte adresu URL aplikace pro Store aplikace, kterou chcete zobrazit nebo skrýt. Příklad:

  - Pokud chcete přidat aplikaci Microsoft work folders, zadejte `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` nebo `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`. 

  - Chcete-li přidat aplikaci Microsoft Word, `https://itunes.apple.com/de/app/microsoft-word/id586447913` zadejte `https://apps.apple.com/de/app/microsoft-word/id586447913`nebo.

  Pokud chcete najít adresu URL aplikace, otevřete aplikaci iTunes App Store a vyhledejte aplikaci. Vyhledejte `Microsoft Remote Desktop` například nebo `Microsoft Word`. Vyberte aplikaci a zkopírujte adresu URL.

  K vyhledání aplikace můžete také použít iTunes a potom pomocí úlohy **Kopírovat odkaz** získat adresu URL aplikace.
  
  Další informace o vyhledání ID sady prostředků najdete v tématu [Jak najít ID sady prostředků pro aplikaci pro iOS](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app).

- **ID sady prostředků aplikace**: Zadejte [ID sady prostředků](bundle-ids-built-in-ios-apps.md) aplikace, kterou chcete. Můžete zobrazit nebo skrýt integrované aplikace a obchodní aplikace. Na webu společnosti Apple je seznam [integrovaných aplikací Apple](https://support.apple.com/HT208094).
- **Název aplikace**: Zadejte název aplikace, kterou chcete. Můžete zobrazit nebo skrýt integrované aplikace a obchodní aplikace. Na webu společnosti Apple je seznam [integrovaných aplikací Apple](https://support.apple.com/HT208094).
- **Vydavatel**: Zadejte vydavatele aplikace, kterou chcete.

Pokud chcete přidat aplikace, můžete:

- **Přidat**: Tuto možnost vyberte, pokud chcete vytvořit seznam aplikací.
- **Importujte** soubor CSV s podrobnostmi o aplikaci, včetně adresy URL. Použijte formát `<app url>, <app name>, <app publisher>`. Případně můžete **exportovat** a vytvořit seznam aplikací s omezeným přístupem, které jste přidali, ve stejném formátu.

## <a name="wireless"></a>Bezdrátová síť

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Nastavení platí pro: Registrace zařízení, automatický zápis zařízení (pod dohledem)

- **Roaming dat**: Vyberte možnost **blokovat** , pokud chcete datový roaming zabránit v mobilní síti. **Není nakonfigurováno** (výchozí) povolí datový roaming, když je zařízení v mobilní síti.
- **Globální načítání na pozadí při roamingu**: Při roamingu v mobilní síti znemožní **blokování** použití globální funkce načítání na pozadí. **Není nakonfigurováno** (výchozí) umožňuje, aby zařízení při roamingu v mobilní síti načetlo data, jako je třeba e-mail.
- **Hlasové vytáčení**: Vyberte možnost **blokovat** , pokud chcete uživatelům zabránit v používání funkce hlasového vytáčení na zařízení. **Není nakonfigurováno** (výchozí) povolí hlasové vytáčení zařízení.
- **Hlasový roaming**: Vyberte možnost **blokovat** , pokud chcete hlasový roaming zabránit v mobilní síti. **Není nakonfigurováno** (výchozí) povolí hlasový roaming, když je zařízení v mobilní síti.
- **Osobní hotspot**: **Blok** vypne osobní hotspot na zařízení uživatelů při každé synchronizaci zařízení. Někteří mobilní operátoři toto nastavení nemusí podporovat. **Není nakonfigurováno** (výchozí) udržuje konfiguraci osobního hotspotu jako výchozí nastavenou uživatelem.
- **Pravidla pro mobilní použití (jenom spravované aplikace)** : Definujte typy dat, které spravované aplikace můžou používat, když používáte mobilní sítě. Možnosti:
  - **Zablokovat používání mobilních dat**: Můžete blokovat používání mobilních dat pro **všechny spravované aplikace** nebo **zvolit konkrétní aplikace**.
  - **Zablokovat používání mobilních dat při roamingu**: Blokovat používání mobilních dat při roamingu pro **všechny spravované aplikace** nebo **zvolit konkrétní aplikace**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

- **Změny nastavení využití mobilních dat v aplikaci**: Vyberte možnost **blokovat** , aby nedošlo ke změnám v nastavení využití mobilních dat v aplikaci. **Není nakonfigurováno** (výchozí) umožňuje uživateli řídit, které aplikace můžou používat mobilní data.
- **Změny nastavení plánu pro mobilní síť**: **Blok** zabraňuje uživatelům měnit nastavení v plánu pro mobilní síť. **Není nakonfigurováno** (výchozí) umožňuje uživatelům provádět změny.

  Tato funkce platí pro:  
  - iOS 11,0 a novější

- **Uživatelské úpravy osobního hotspotu**: Když se nastaví **blokování**, nemůže uživatel změnit nastavení osobního hotspotu. **Není nakonfigurováno** (výchozí) umožňuje koncovým uživatelům povolit nebo zakázat svůj osobní hotspot.

  Pokud zablokujete toto nastavení a zablokujete nastavení **osobní hotspotu** , bude osobní hotspot vypnutý.

  Tato funkce platí pro:  
  - iOS 12,2 a novější

- **Připojit se k sítím Wi-Fi jenom pomocí konfiguračních profilů**: **Vyžadovat** , aby zařízení používalo jenom sítě Wi-Fi nastavené prostřednictvím konfiguračních profilů Intune. **Není nakonfigurováno** (výchozí) umožňuje zařízení používat jiné sítě Wi-Fi.
- **Úprava stavu Wi-Fi**: **Není nakonfigurováno** (výchozí) umožňuje uživatelům zapnout nebo vypnout Wi-Fi na zařízení. **Blok** zabraňuje zapnutí nebo vypnutí Wi-Fi.

## <a name="connected-devices"></a>Připojená zařízení

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: Všechny typy registrace

- **Detekce zápěstí pro párované Apple Watch**: **Vyžadovat** , aby spárovaná Apple Watch používala detekci zápěstí. V případě potřeby nebude Apple Watch zobrazovat oznámení, pokud se nepoužívá. 

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Nastavení platí pro: Registrace zařízení, automatický zápis zařízení (pod dohledem)

- **Vyžadovat spárované heslo pro odchozí požadavky AirPlay**: Pokud uživatel používá AirPlay ke streamování obsahu do jiných zařízení Apple, **vyžadovat** párování hesla. **Není nakonfigurováno** (výchozí) povolí uživateli streamování obsahu pomocí AirPlay bez zadání hesla.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

- **Přetažení**: **Blok** zabraňuje použití přerušení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje použití funkce prohodit při výměně obsahu s blízkými zařízeními.
- **Párování Apple Watch**: **Blok** zabraňuje párování s Apple Watch. **Není nakonfigurováno** (výchozí) povolí zařízení párování s Apple Watch.
- **Úpravy Bluetooth**: **Blok** zastaví koncovému uživateli měnit nastavení Bluetooth na zařízení. **Není nakonfigurováno** (výchozí) umožní uživateli změnit tato nastavení.
- **Párování hostitelů pro řízení zařízení, se kterými se zařízení s iOS může spárovat**: **Není nakonfigurováno** (výchozí) umožňuje, aby správce mohl řídit, se kterými zařízeními se zařízení s iOS může spárovat. **Blok** zabraňuje párování hostitelů.
- **Blokovat tisk**: Vyberte možnost **blokovat** , pokud chcete zabránit použití funkce pro tisk do zařízení. **Není nakonfigurováno** (výchozí) umožní uživateli používat postupné tisku.
  - **Blokovat úložiště přihlašovacích údajů pro tisk v řetězci klíčů**: **Blok** zabraňuje použití úložiště řetězce klíčů pro uživatelské jméno a heslo v zařízení. **Není nakonfigurováno** (výchozí) umožňuje ukládání uživatelského jména a hesla pro tisk do aplikace pro řetězce klíčů.
  - **Vyžadovat důvěryhodný certifikát TLS pro Protisk**: **Vyžadovat** , aby zařízení používalo důvěryhodné certifikáty pro komunikaci tiskem TLS.
  - **Zablokovat blokovat iBeacon u rozpoznávání tiskových tiskáren**: **Blok** zabraňuje škodlivým signálům Bluetooth v přenosu dat ze sítě phishing. **Není nakonfigurováno** (výchozí) umožňuje reklamní tiskové tiskárny na zařízení.
- **Zablokovat nastavení nových okolních zařízení**: **Blok** zakáže výzvu k nastavení nových zařízení, která jsou v okolí. **Není nakonfigurováno** (výchozí) umožňuje uživatelům výzvy, aby se připojili k jiným blízkým zařízením Apple.

  Tato funkce platí pro:  
  - iOS 11,0 a novější

## <a name="keyboard-and-dictionary"></a>Klávesnice a slovník

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

- **Vyhledávání definic slov**: **Blok** znemožní uživateli zvýraznit slovo a pak na zařízení vyhledá jeho definici. **Není nakonfigurováno** (výchozí) umožňuje přístup k funkci vyhledávání definic.
- **Prediktivní klávesnice**: **Není nakonfigurováno** (výchozí) umožňuje pomocí prediktivních klávesnic navrhovat slova, která může chtít uživatel. **Blokování** brání této funkci.
- **Automatické opravy**: **Není nakonfigurováno** (výchozí) povolí zařízení automaticky opravovat slova s překlepem. **Blok** zabraňuje použití automatických oprav.
- **Kontrola pravopisu klávesnice**: **Není nakonfigurováno** (výchozí) umožňuje použití kontroly pravopisu na zařízení. **Blok** umožňuje kontrolu pravopisu.
- **Klávesové zkratky**: **Není nakonfigurováno** (výchozí) povolí používání klávesových zkratek na zařízení. **Blok** zabrání uživateli v používání klávesových zkratek.
- **Diktování**: **Blok** zabrání uživateli v zadávání textu pomocí hlasového vstupu. **Není nakonfigurováno** (výchozí) umožní uživateli používat vstup diktování.
- **QuickPath**: **Není nakonfigurováno** (výchozí) umožňuje uživatelům používat QuickPath, které umožňují nepřetržitý vstup na klávesnici zařízení. Uživatelé můžou k vytváření slov psát přetáhnutím prstem přes tyto klávesy. **Blok** zabraňuje uživatelům v používání QuickPath. 

  Tato funkce platí pro:  
  - iOS 13,0 a iPadOS 13,0 a novější

## <a name="cloud-and-storage"></a>Cloud a úložiště

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: Všechny typy registrace

- **Šifrované zálohování**: **Vyžadovat** , aby bylo zálohování zařízení nutné šifrovat.
- **Synchronizace spravovaných aplikací do cloudu**: **Není nakonfigurováno** (výchozí) umožňuje, aby aplikace Intune synchronizoval data s uživatelským účtem iCloud. **Blok** zabraňuje synchronizaci těchto dat s iCloud.
- **Zablokovat zálohu v podnikové knize**: Vyberte možnost **blokovat** , pokud chcete uživatelům zabránit v zálohování podnikových knih. **Není nakonfigurováno** (výchozí) umožňuje uživatelům zálohovat tyto knihy.
- **Blokovat synchronizaci metadat v podnikovém adresáři (poznámky a zvýraznění)** : **Blok** zabraňuje synchronizaci poznámek a zvýraznění v podnikových knihách. **Není nakonfigurováno** (výchozí) umožňuje synchronizaci.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Nastavení platí pro: Registrace zařízení, automatický zápis zařízení (pod dohledem)

- **Synchronizace datových proudů na iCloud**: **Není nakonfigurováno** (výchozí) umožňuje uživatelům povolit, aby se **Váš fotografický Stream** na svém zařízení synchronizoval s iCloud a aby byly na všech zařízeních uživatele dostupné fotky. **Blok** zabraňuje synchronizaci streamování fotografií do iCloud. Blokování této funkce může způsobit ztrátu dat. 
- **Knihovna fotografií iCloud**: Nastavením **zablokování** zakážete použití knihovny fotografií iCloud k ukládání fotek a videí do cloudu. Ze zařízení se odeberou všechny fotky, které nejsou kompletně stažené z knihovny fotografií iCloud. **Není nakonfigurováno** (výchozí) umožňuje použití knihovny fotografií iCloud.
- **Sdílený datový proud fotek**: Zvolením možnosti **blokovat** zakážete **Sdílení fotek iCloud** na zařízení. **Není nakonfigurováno** (výchozí) umožňuje sdílet streamování fotek.
- **Předání**: **Není nakonfigurováno** (výchozí) umožňuje uživatelům začít pracovat na zařízení s iOS a potom pokračovat v práci, kterou zahájili na jiném zařízení s iOS nebo macOS. **Blok** zabraňuje tomuto předání.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

- **Záloha na iCloud**: **Není nakonfigurováno** (výchozí) umožní uživateli zálohovat zařízení na iCloud. **Blokování** zabrání uživateli v zálohování zařízení do iCloud.

  Od iOS 13,0 Toto nastavení vyžaduje zařízení pod dohledem.

- **Zablokovat synchronizaci dokumentu iCloud**: **Není nakonfigurováno** (výchozí) povolí synchronizaci dokumentu a klíč-hodnota do iCloud prostoru úložiště. **Blok** zabraňuje iCloud synchronizaci dokumentů a dat.

  Od iOS 13,0 Toto nastavení vyžaduje zařízení pod dohledem.

- **Blokovat synchronizaci řetězce klíčů iCloud**: Zvolením možnosti **blokovat** zakážete synchronizaci přihlašovacích údajů uložených v řetězci klíčů do iCloud. **Není nakonfigurováno** (výchozí) umožňuje uživatelům synchronizovat tyto přihlašovací údaje.

  Od iOS 13,0 Toto nastavení vyžaduje zařízení pod dohledem.

## <a name="autonomous-single-app-mode"></a>Autonomní režim jedné aplikace

Pomocí těchto nastavení můžete nakonfigurovat zařízení s iOS tak, aby spouštěla konkrétní aplikace v autonomním režimu jedné aplikace. Když je tento režim nakonfigurovaný a aplikace se spustí, zařízení je uzamčené. Tuto aplikaci může spustit pouze. Přidejte například aplikaci, která umožní uživatelům provést test na zařízení. Když se akce aplikace dokončí nebo tuto zásadu odeberete, zařízení se vrátí do normálního stavu.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

- **Název aplikace**: Zadejte název aplikace, kterou chcete.
- **ID sady prostředků aplikace**: Zadejte [ID sady](bundle-ids-built-in-ios-apps.md) aplikace, kterou chcete.
- **Přidat**: Tuto možnost vyberte, pokud chcete vytvořit seznam aplikací.

Soubor CSV můžete také **naimportovat** se seznamem názvů aplikací a jejich ID sady. Případně **exportujte** existující seznam obsahující aplikace.

## <a name="kiosk"></a>Kiosk

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

- **Aplikace, která se má spustit v celoobrazovkovém režimu**: Vyberte typ aplikací, které chcete spustit v celoobrazovkovém režimu. Možnosti:
  - **Není nakonfigurováno** (výchozí): Nastavení veřejného terminálu se nepoužijí. Zařízení neběží v celoobrazovkovém režimu.
  - **Aplikace pro Store**: Zadejte adresu URL aplikace v iTunes App Storu.
  - **Spravovaná aplikace**: Vyberte aplikaci, kterou jste přidali do Intune.
  - **Integrovaná aplikace**: Zadejte [ID sady](bundle-ids-built-in-ios-apps.md) předdefinovaných aplikací.

- **Dotykové ovládání pro usnadnění**: **Vyžaduje** , aby na zařízení bylo nastavení usnadnění dotykového ovládání. Tato funkce pomáhá uživatelům s gesty na obrazovce, která by pro ně mohla být obtížná. **Není nakonfigurováno** , nespustí nebo povolí tuto funkci v celoobrazovkovém režimu.
- **Invertovat barvy**: **Vyžaduje** nastavení usnadnění invertování barev, aby uživatelé s zrakovým postižením mohli obrazovku pro zobrazení změnit. **Není nakonfigurováno** , nespustí nebo povolí tuto funkci v celoobrazovkovém režimu.
- **Mono zvuk**: **Vyžaduje** , aby na zařízení bylo nastavení usnadnění Mono zvuk. **Není nakonfigurováno** , nespustí nebo povolí tuto funkci v celoobrazovkovém režimu.
- **Ovládání hlasu**: **Vyžadovat** v zařízení umožňuje ovládání hlasu a umožňuje uživatelům plně ovládat operační systém pomocí příkazů Siri. **Nenakonfigurováno** zakáže ovládací prvek hlasu na zařízení.

  Toto nastavení platí pro:  
  - iOS 13,0 a novější
  - iPadOS 13,0 a novější
  
  > [!TIP]
  > Pokud máte ve vaší organizaci k dispozici obchodní aplikace a nejsou v nich k dispozici **hlasové řízení** připravené na den 0 při vydání iOS 13,0, doporučujeme toto nastavení ponechat **nenakonfigurované**.

- **VoiceOver**: **Vyžaduje** , aby se na zařízení načetlo nastavení usnadnění VoiceOver, aby se text na obrazovce načetl po nahlasu. **Není nakonfigurováno** , nespustí nebo povolí tuto funkci v celoobrazovkovém režimu.
- **Přiblížení**: **Vyžadovat** nastavení přiblížení na zařízení, aby uživatelé mohli používat dotykové ovládání k přiblížení na obrazovce. **Není nakonfigurováno** , nespustí nebo povolí tuto funkci v celoobrazovkovém režimu.
- **Automatický zámek**: **Blokování** znemožňuje automatické uzamykání zařízení. **Nenakonfigurováno** umožňuje tuto funkci.
- **Přepínač vyzvánění**: **Blok** zakáže přepínač vyzvánění (ztlumení) na zařízení. **Nenakonfigurováno** umožňuje tuto funkci.
- **Otočení obrazovky**: **Blok** zabraňuje změně orientace obrazovky, když uživatel otočí zařízení. **Nenakonfigurováno** umožňuje tuto funkci.
- **Tlačítko pro režim spánku obrazovky**: Zvolením možnosti **blokovat** zakážete na zařízení tlačítko probuzení z režimu spánku obrazovky. **Nenakonfigurováno** umožňuje tuto funkci.
- **Dotykové ovládání**: **Blok** zakáže dotykovou obrazovku na zařízení. **Není nakonfigurováno** umožňuje uživateli používat dotykovou obrazovku.
- **Tlačítka hlasitosti**: **Blok** zabraňuje použití tlačítek hlasitosti na zařízení. **Není nakonfigurováno** , umožňuje tlačítka hlasitosti.
- **Řízení dotykového ovládání pro usnadnění**: **Povolit** uživatelům používat funkci usnadnění dotykového ovládání. **Není nakonfigurováno** , zakáže tuto funkci.
- **Barva ovládacího prvku invertování barev**: **Povolit** změnu Invertovat barvy, aby uživatelé mohli upravovat funkci invertování barev. **Není nakonfigurováno** , zakáže tuto funkci.
- **Mluvit na vybraném textu**: **Povolí** na zařízení nastavení usnadnění pro výběr řeči. Tato funkce přečte text, který uživatel vybírá nahlas. **Není nakonfigurováno** , zakáže tuto funkci.
- **Změna ovládání hlasu**: **Umožňuje** uživatelům změnit stav ovládacího prvku hlas na svých zařízeních. **Nenakonfigurovaní** znemožní uživatelům měnit stav ovládacího prvku hlas na svých zařízeních.

  Toto nastavení platí pro:  
  - iOS 13,0 a novější
  - iPadOS 13,0 a novější

- **Ovládací prvek VoiceOver**: **Povolí** VoiceOver změny, aby uživatelé mohli aktualizovat funkci VoiceOver, například to, jak rychlý text na obrazovce se čte nahlas. **Není nakonfigurováno** , zabraňuje VoiceOver změnám.
- **Ovládací prvek Lupa**: **Povolí** změny přiblížení uživatele. **Není nakonfigurováno** , zabraňuje změnám lupy.

> [!NOTE]
> Než budete moct nakonfigurovat nastavení zařízení s iOSem pro celoobrazovkový (beznabídkový) režim, musíte převést zařízení do režimu dohledu pomocí nástroje Apple Configurator nebo Programu registrace zařízení Apple. Podívejte se na téma Příručka Apple na používání nástroje Apple Configuratoru.
> Pokud je aplikace pro iOS, kterou zadáte, nainstalovaná po přiřazení profilu, zařízení nepřejde do celoobrazovkového režimu, dokud se zařízení nerestartuje.

## <a name="domains"></a>Domény

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Nastavení platí pro: Registrace zařízení, automatický zápis zařízení (pod dohledem)

-  > **Adresa URL e-mailové domény**v neoznačeném e-mailu: Přidejte do seznamu jednu nebo více adres URL. Když koncoví uživatelé dostanou e-mail z jiné domény než z domén, které zadáte, e-mail se v aplikaci iOS mail označí jako nedůvěryhodný.

-  > **Adresa URL webové domény**spravované webové domény; Přidejte do seznamu jednu nebo více adres URL. Po stažení dokumentů z domén, které zadáte, se považují za spravované. Toto nastavení platí jenom pro dokumenty stažené prostřednictvím prohlížeče Safari.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

-  > **Adresa URL domény**pro automatické vyplňování hesel v Safari: Přidejte do seznamu jednu nebo více adres URL. Uživatelé si mohou uložit jenom webová hesla z adres URL uvedených v tomto seznamu. Toto nastavení platí jenom pro prohlížeč Safari a zařízení v režimu pod dohledem. Pokud nezadáte žádné adresy URL, bude možné ukládat hesla ze všech webů.

  Toto nastavení platí pro:  
  - iOS 9,3 a novější

## <a name="settings-that-require-supervised-mode"></a>Nastavení, které vyžaduje režim pod dohledem

Režim iOSu pod dohledem je možné povolit jenom během počátečního nastavování zařízení prostřednictvím Programu registrace zařízení společnosti Apple nebo prostřednictvím Apple Configuratoru. Po povolení režimu pod dohledem může Intune v zařízení nakonfigurovat následující funkce:

- Zámek aplikace (režim jedné aplikace) 
- Globální proxy server HTTP 
- Vyřazení zámku aktivace 
- Autonomní režim jedné aplikace 
- Filtr webového obsahu 
- Nastavení pozadí a zamykací obrazovky 
- Tiché doručení aplikací bez vyžádání 
- Vždy zapnutá síť VPN 
- Povolení pouze instalace spravovaných aplikací 
- iBooks Store 
- Zprávy iMessage 
- Herní centrum 
- AirDrop 
- AirPlay 
- Hostitelské párování 
- Synchronizace cloudu 
- Vyhledávání Spotlight 
- Handoff 
- Vymazání zařízení 
- Uživatelské rozhraní pro omezení 
- Instalace konfiguračních profilů uživatelským rozhraním 
- News 
- Klávesové zkratky 
- Změny hesla 
- Změny názvu zařízení 
- Automatická stahování aplikací 
- Úpravy vztahu důvěryhodnosti u podnikových aplikací 
- Apple Music 
- Doručení pošty 
- Spárování s Apple Watch 

> [!NOTE]
> Apple potvrzuje, že určitá nastavení se přesunou do režimu pod dohledem – jenom v 2019. Při použití těchto nastavení doporučujeme tuto možnost vzít v úvahu, takže nemusíte čekat, až společnost Apple je migruje do režimu pod dohledem:
>
> - Instalace aplikací koncovými uživateli
> - Odebrání aplikace
> - FaceTime
> - Safari
> - iTunes
> - Explicitní obsah
> - Dokumenty a data v iCloudu
> - Hry pro více hráčů
> - Přidat Game Center přátelé
> - Siri

## <a name="next-steps"></a>Další kroky

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Na zařízeních [MacOS](device-restrictions-macos.md) můžete také omezit funkce a nastavení zařízení.
