---
title: nastavení pro zařízení s Iosem v Microsoft Intune – Azure | Dokumentace Microsoftu
titleSuffix: ''
description: Přidání, nakonfigurovat nebo vytvořit nastavení na zařízení s Iosem k omezení funkcí, včetně nastavení požadavky na heslo, řízení na uzamčené obrazovce, pomocí integrovaných aplikací, přidejte s omezením pomocí specifikátoru nebo schválené aplikace, zpracovávat zařízeními bluetooth, připojit ke cloudu k zálohování a úložiště, Povolit režim veřejného terminálu, přidejte domény a řízení, jak uživatelé pracují s webovým prohlížečem Safari v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/13/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 44f7c5b897dc1aedfe8ffc23c25ea479eceb35e5
ms.sourcegitcommit: 464cf677e3746eaba46836dedfb94572a75032f9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/21/2019
ms.locfileid: "58330491"
---
# <a name="ios-device-settings-to-allow-or-restrict-features-using-intune"></a>nastavení zařízení s Iosem k povolení nebo zakázání funkcí pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek uvádí a popisuje různá nastavení, které můžete řídit na zařízeních s Iosem. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete povolit nebo zakázat funkce, nastavte pravidla pro hesla, povolení nebo zakázání konkrétní aplikace a další.

Tato nastavení jsou přidány do konfiguračního profilu zařízení v Intune a potom přiřazené nebo nasazené do zařízení iOS.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení omezení](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Obecné

- **Sdílet data o využití**: Zvolte **bloku** zabránit zařízení odesílat data diagnostiky a použití společnosti Apple. **Není nakonfigurováno** (výchozí), umožňuje tato data k odeslání.
  - **Úpravy nastavení odesílání diagnostických informací (jenom pod dohledem)**: **Blok** zabrání uživateli ve změně odesílání a app analytics nastavení diagnostiky v **využití a Diagnostika** (nastavení zařízení). **Není nakonfigurováno** (výchozí) umožňuje uživateli změnit nastavení těchto zařízení.

    Tato funkce platí pro:  
    - iOS 9.3.2 a novější

- **Snímek obrazovky**: Zvolte **bloku** zabránit snímky obrazovky a obrazovky zachycuje na zařízení. V Iosu 9.0 a novější to zahrnuje také blokovat záznam obrazovky. **Není nakonfigurováno** (výchozí) umožňuje uživateli zachytit obsah obrazovky jako obrázek nebo video.
  - **Sledování vzdálených obrazovek v aplikaci Classroom (jenom pod dohledem)**: Zvolte **bloku** zabránit aplikaci Classroom vzdáleně zobrazovat obrazovku na zařízení. **Není nakonfigurováno** (výchozí) umožňuje aplikaci Apple Classroom zobrazovat obrazovku.

    Tato funkce platí pro:  
    - iOS 9.3 nebo novější

  - **Sledování obrazovek v aplikaci Classroom (jenom pod dohledem)**: Pokud hodnotu **povolit**, učitelé můžou sledovat obrazovky zařízení s Iosem studentů pomocí aplikace Classroom bez vědomí na studentů. Zařízení studentů zaregistrovaná do třídy přes aplikaci Classroom automaticky udělení oprávnění pro daného kurzu. **Není nakonfigurováno** této funkce zabraňuje (výchozí).
- **Nedůvěryhodné certifikáty TLS**: Zvolte **bloku** zabránit nedůvěryhodné certifikáty zabezpečení TLS (Transport Layer) na zařízení. **Není nakonfigurováno** umožňuje certifikáty TLS (výchozí).
- **Vztah důvěryhodnosti podnikové aplikace**: Zvolte **bloku** odebrat **důvěřovat vývojáři organizace** tlačítko v Nastavení > Obecné > Správa profilů a zařízení na zařízení. **Není nakonfigurováno** (výchozí) umožňuje uživatelům zvolit možnost, že důvěřuje aplikacím, které nebudou staženy z app storu.
- **Účtu (jenom pod dohledem)**: Pokud je nastavena na **bloku**, uživatel nemůže aktualizovat nastavení pro konkrétní zařízení z aplikace pro nastavení Iosu. Uživatele nelze například vytváření nových účtů zařízení nebo změnit uživatelské jméno nebo heslo. **Není nakonfigurováno** (výchozí) umožňuje uživatelům změnit tato nastavení.

  Tato funkce platí také pro nastavení dostupná z aplikace pro nastavení Iosu, například e-mailu, kontakty, kalendáře, Twitter a další. Tato funkce neplatí pro aplikace s nastavením účtu, které nejsou konfigurovatelné z aplikace pro nastavení Iosu, jako je například aplikace Microsoft Outlook.
- **Obrazovky (jenom pod dohledem) čas**: Zvolte **bloku** uživatelům zabránit v jejich vlastní omezení v čase obrazovky (nastavení zařízení). **Není nakonfigurováno** umožní uživateli konfiguraci omezení zařízení (například rodičovské nebo obsah a omezení ochrany osobních údajů) v zařízení.

  Toto nastavení se přejmenoval z **povolení omezení v nastavení zařízení**. Dopad této změny:  
  
  - iOS 11.4.1 a dříve: **Blok** zabrání koncovým uživatelům vlastní omezení v nastavení zařízení. Jedná se o stejné; a neexistují žádné změny pro koncové uživatele.
  - iOS 12,0 a novější: **Blok** koncovým uživatelům zabrání v nastavení své vlastní **obrazovky čas** v nastavení zařízení (Nastavení > Obecné > čas obrazovky), včetně omezení obsahu a ochrany osobních údajů. Zařízení upgradovat operační systém na iOS 12.0 už nezobrazí na kartě omezení v nastavení zařízení (Nastavení > Obecné > Správa zařízení > profil správy > omezení). Tato nastavení jsou v **obrazovky čas**.
  
- **Vymazání veškerého obsahu a možnost nastavení na zařízení (jenom pod dohledem)**: Zvolte **bloku** , uživatelé nemůžou používat vymazání veškerého obsahu a možnost nastavení na zařízení (jenom pod dohledem). **Není nakonfigurováno** (výchozí) poskytuje uživatelům přístup k těmto nastavením.
- **Změny názvu zařízení (jenom pod dohledem)**: Zvolte **bloku** , nelze změnit název zařízení. **Není nakonfigurováno** (výchozí) umožňuje uživateli změnit název zařízení.
- **Úprava nastavení oznámení (jenom pod dohledem)**: Zvolte **bloku** tak nastavení oznámení nelze změnit. **Není nakonfigurováno** (výchozí) umožní uživateli přenastavit v zařízení oznámení.
- **Úprava tapety (jenom pod dohledem)**: **Blok** zabrání změně tapetu. **Není nakonfigurováno** (výchozí) umožňuje uživateli změnit v zařízení tapetu.
- **Podnikové aplikace úpravy nastavení vztahu důvěryhodnosti (jenom pod dohledem)**: **Blok** zabrání uživateli ve změně nastavení vztahu důvěryhodnosti podnikových aplikací na zařízeních pod dohledem. **Není nakonfigurováno** (výchozí) umožňuje uživateli možnost, že důvěřuje aplikacím, které nebudou staženy z app storu.
- **Změny profilu konfigurace (jenom pod dohledem)**: **Blok** brání změny profilu konfigurace zařízení. **Není nakonfigurováno** (výchozí) umožní uživateli instalovat konfigurační profily.
- **Zámek aktivace (jenom pod dohledem)**: Zvolte **povolit** pro povolení zámku aktivace na hlídaných zařízeních s Iosem. Zámek aktivace ztěžuje ztraceného nebo odcizeného zařízení znovu aktivovat.
- **Blokovat odebrání aplikace (jenom pod dohledem)**: Zvolte **bloku** zabráníte uživatelům aplikace odebrat. **Není nakonfigurováno** (výchozí) umožňuje uživatelům odebere aplikaci ze zařízení.
- **Režim bloky s omezenými USB (jenom pod dohledem)**: Zvolte **bloku** zakázat USB omezeném režimu na zařízeních pod dohledem. USB omezený režim blokuje USB příslušenství z výměna dat se zařízením, která je uzamčena pro více než hodinu. **Není nakonfigurováno** (výchozí) umožňuje USB omezeném režimu.
- **Vynutit automatické datum a čas (jenom pod dohledem)**: **Vyžadovat** vynutí hlídaných zařízeních automatické nastavení data a času. Časové pásmo zařízení se aktualizuje, když zařízení mobilní připojení, nebo má povolenou Wi-Fi s zjišťování polohy.
- **Studenti mohli požádat o oprávnění k ponechte třídenní kurz ve třídě (jenom pod dohledem) vyžadují**: **Vyžadovat** vynutí studenti v nespravované kurzu se pomocí aplikace Classroom na žádost o oprávnění z učitele ponechte kurzu. **Není nakonfigurováno** (výchozí) nenutí studentů a požádejte o oprávnění.

  Tato funkce platí pro:  
  - iOS 11,3 a novější

- **Povolit Classroom uzamknout zařízení do aplikace a zařízení uzamknout bez zobrazení výzvy (jenom pod dohledem)**: **Povolit** umožňuje učitelů uzamčení aplikací a uzamčení zařízení pomocí aplikace Classroom bez zobrazení výzvy studenta. Uzamčení prostředků aplikace zařízení můžete pouze učitelů přístup k určité aplikace. **Není nakonfigurováno** uzamčení aplikace nebo zařízení pomocí aplikace Classroom bez zobrazení výzvy studenta učitelé zabraňuje (výchozí). 

  Tato funkce platí pro:  
  - Iosu 11.0 a novějších

- **Automaticky připojí k tříd Classroom bez zobrazení výzvy (jenom pod dohledem)**: **Povolit** automaticky umožňuje studentům připojit třídu, která je v aplikaci Classroom bez zobrazení výzvy učitele. **Není nakonfigurováno** (výchozí) zobrazí výzvu učitele, studenty chcete připojit k třídu, která je v aplikaci Classroom.

  Tato funkce platí pro:  
  - Iosu 11.0 a novějších

- **Povolit aktualizace distribuované bezdrátově infrastruktury veřejných KLÍČŮ**: **Povolit** umožňuje dostávat aktualizace softwaru bez připojení zařízení k počítači.
- **Limit ad sledování**: Zvolte **Limit** zakázat reklamy identifikátor zařízení. **Není nakonfigurováno** (výchozí) zůstane povolena.
- **Vytváření bloku virtuální privátní sítě (jenom pod dohledem)**: **Blok** zabraňuje uživatelům ve vytváření nastavení konfigurace sítě VPN. **Není nakonfigurováno** (výchozí) umožňuje vytvořit připojení VPN na zařízení.
- **Úprava nastavení karty eSIM (jenom pod dohledem)**: **Blok** zabraňuje uživatelům a přidat mobilní plán karty eSIM na zařízení. **Není nakonfigurováno** (výchozí) umožňuje uživatelům změnit tato nastavení.

  Tato funkce platí pro:  
  - iOS 12,1 a novější

- **Odložení aktualizací softwaru (jenom pod dohledem)**: Pokud je nastavena na **Nenakonfigurováno** (výchozí), aktualizací softwaru jsou zobrazeny na zařízení s Apple je uvolní. Například pokud aktualizace iOS získá vydané společností Apple v konkrétní den, pak tuto aktualizaci přirozeně zobrazuje v zařízení po datu vydání.

  **Povolit** umožňuje zpoždění při zobrazení aktualizací softwaru na zařízení z 0 – 90 dní. Toto nastavení nemá pod kontrolou, pokud aktualizace jsou nebo nejsou nainstalovány. 

  - **Zpoždění viditelnost aktualizací softwaru**: Zadejte hodnotu od 0 – 90 dní. Když vyprší platnost zpoždění, uživatelé získají oznámení, které nejstarší verzi operačního systému k dispozici při aktivaci zpoždění.

    Například pokud iOS 12a je k dispozici na **1. ledna**, a **zpoždění viditelnost** je nastavena na **5 dní**, pak iOS 12a nezobrazuje jako k dispozici aktualizace na zařízeních koncových uživatelů. Na **šestý den** po vydání, že je k dispozici aktualizace a koncoví uživatelé ji můžou nainstalovat.

    Toto nastavení platí pro:  
    - iOS 11,3 a novější

## <a name="password"></a>Heslo

- **Heslo**: **Vyžadovat** koncový uživatel zadal heslo pro přístup k zařízení. **Není nakonfigurováno** umožňuje uživatelům přístup k zařízení bez zadávání hesla.
  - **Jednoduchá hesla**: Zvolte **bloku** tak, aby vyžadovala složitějších hesel. **Není nakonfigurováno** umožňuje jednoduchá hesla, jako například `0000` a `1234`.
  - **Vyžadovaný typ hesla**: Vyberte typ hesla, které vaše organizace vyžadovat. Možnosti:
    - **Výchozí ze zařízení**
    - **Číselné**
    - **Alfanumerické znaky**
  - **Počet nealfanumerických znaků v hesle**: Zadejte počet znaků symbolu, jako například `#` nebo `@`, který musí obsahovat heslo.
  - **Minimální délka hesla**: Zadejte minimální délku, které uživatel musí zadat (mezi 4 a 14 znaky).
  - **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: Zadejte počet neúspěšných přihlášení povolit předtím, než se zařízení vymaže (mezi 1 – 11).
  - **Maximální počet minut po uzamčení obrazovky před vyžádáním hesla**<sup>1</sup>: Zadejte zařízení zůstane dobu nečinnosti, než uživatel musí znovu zadat heslo. Pokud je doba, kterou zadáte delší než hodnota aktuálně nastavená na zařízení, zařízení bude ignorovat dobu, kterou zadáte. Podporováno v iOS 8.0 a novější zařízení.
  - **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**<sup>1</sup>: Zadejte maximální počet minut nečinnosti, které jsou povoleny v zařízení po kterém se zamkne obrazovka. Pokud je doba, kterou zadáte delší než hodnota aktuálně nastavená na zařízení, zařízení bude ignorovat dobu, kterou zadáte.
  - **Vypršení platnosti hesla (dny)**: Zadejte počet dní, než se musí změnit heslo zařízení.
  - **Zakázat opakované použití předchozích hesel**: Zadejte počet nových hesel, která se musí použít, než můžete znovu použít staré heslo.
  - **Odemknutí pomocí otisků prstů**: Zvolte **bloku** zabránit k odemknutí zařízení otiskem prstu. **Není nakonfigurováno** uživatel k odemknutí zařízení otiskem prstu.
- **Úprava hesla (jenom pod dohledem)**: Zvolte **bloku** zastavit před změnou, přidání nebo odebrání hesla. Omezení se ignorují u zařízení pod dohledem po blokování tuto funkci. **Není nakonfigurováno** (výchozí) umožňuje k přidávání, změny a odebírání hesel.

  - **Otisků prstů (jenom pod dohledem)**: **Blok** zabrání uživateli změnu, přidávat nebo odebírat otisky prstů TouchID. **Není nakonfigurováno** (výchozí) otisky prstů TouchID povolí aktualizace uživatele v zařízení.

- **Heslo blokovat automatické vyplňování (jenom pod dohledem)**: Zvolte **bloku** zabránit pomocí funkce Automatické vyplňování hesel v systému iOS. Výběr **bloku** rovněž provede následující akce:

  - Uživatelé vyzváni k použít heslo uložené v prohlížeči Safari nebo v jakékoli aplikace.
  - Automatické silná hesla jsou zakázána a silná hesla nejsou navržené pro uživatele.

  **Není nakonfigurováno** (výchozí) umožňuje tyto funkce.

- **Blokovat požadavky blízkosti hesla (jenom pod dohledem)**: Zvolte **bloku** tak zařízení uživatele není žádat hesla blízkými zařízeními. **Není nakonfigurováno** (výchozí) umožňuje tyto požadavky na heslo.
- **Blokovat sdílení hesla (jenom pod dohledem)**: **Blok** zabraňuje sdílení hesla mezi zařízení pomocí AirDrop. **Není nakonfigurováno** (výchozí) umožňuje hesla ke sdílení.
- **Vyžadovat Touch ID a Face ID, heslo nebo kreditní karta informace automatické vyplňování (jenom pod dohledem)**: Pokud je nastavena na **vyžadují**, uživatelé musí ověřit pomocí TouchID nebo funkci FaceID před hesla nebo informace o platební kartě se nedají automaticky vyplněné v prohlížeči Safari nebo jiných aplikací. **Není nakonfigurováno** (výchozí) umožňuje uživatelům řídit tuto funkci v nastavení zařízení.

  Tato funkce platí pro:  
  - Iosu 11.0 a novějších

<sup>1</sup>při konfiguraci **maximální počet minut nečinnosti, po kterém se zamkne obrazovka** a **maximální počet minut po uzamčení obrazovky, po před vyžádáním hesla** nastavení, se použijí v uvedeném pořadí. Například, pokud pro obě nastavení nastavíte hodnotu **5** minut, po pěti minutách automaticky vypne obrazovku a zařízení uzamkne po dalších 5 minut. Pokud ale uživatel vypne obrazovku ručně, druhé nastavení se použije okamžitě. V tomto příkladě poté, co uživatel vypne obrazovku, zamkne zařízení pěti minutách.

## <a name="locked-screen-experience"></a>Prostředí zamknuté obrazovky

- **Přístup k řídicímu centru, když je zařízení zamknuté**: Zvolte **bloku** zabránit přístupu k řídicímu centru aplikací při uzamčení zařízení zašifrovaná. **Není nakonfigurováno** umožňuje uživatelům přístup k řídicímu centru aplikaci, když je zařízení zamknuté.
- **Oznámení na uzamčeném zařízení**: **Blok** brání přístupu k oznámení, když je zařízení zamknuté. **Není nakonfigurováno** mu umožní přístup k oznámení bez odemknutí zařízení.
- **Oznámení peněženky na uzamčeném zařízení**: **Blok** brání přístupu k aplikaci Wallet, když je zařízení zamknuté. **Není nakonfigurováno** mu umožní přístup k aplikaci Peněženka při uzamčení zařízení zašifrovaná.
- **Zobrazení dnes, když je zařízení zamknuté**: **Blok** brání přístupu k zobrazení dnes, když je zařízení zamknuté. **Není nakonfigurováno** umožňuje uživateli zobrazovat zobrazení dnes, když je zařízení zamknuté.

## <a name="app-store-doc-viewing-gaming"></a>App Store, zobrazování dokumentů, hraní her

- **App store**: **Blok** brání v přístupu k obchodu s aplikacemi v zařízeních pod dohledem. **Není nakonfigurováno** umožňuje přístup.
  - **Instalace aplikací z App Store (jenom pod dohledem)**: Zvolte **bloku** zablokovat app store z domovské obrazovky zařízení. Koncoví uživatelé můžou aplikace dál instalovat pomocí iTunes nebo Apple Configuratoru. **Není nakonfigurováno** umožňuje app storu na domovské obrazovce.
  - **Automatické stahování aplikací (jenom pod dohledem)**: Zvolte **bloku** zabránit automatické stahování aplikací koupených na jiných zařízeních. To nemá vliv na aktualizace stávajících aplikací. **Není nakonfigurováno** umožňuje aplikací koupených na jiných zařízeních s Iosem ke stažení na zařízení.
- **Heslo pro přístup k obchodu s aplikacemi**: **Vyžadovat** uživatel zadal heslo, než bude moci navštívit obchod s aplikacemi. **Není nakonfigurováno** umožňuje přístup k obchodu s aplikacemi, bez zadávání hesla.
- **Nákupy v aplikaci**: Zvolte **bloku** zabránit nákupy v aplikaci ve storu. **Není nakonfigurováno** povolí ve spuštěné aplikaci nákupy na storu.
- **Obsah hudbě, podcastech nebo zprávách explicitní iTunes (jenom pod dohledem)**: Zvolte **bloku** zabránit explicitní iTunes hudbě, podcastech nebo zprávách obsah. **Není nakonfigurováno** povolí zařízení přístup k obsahu označený jako obsah pro dospělé obchodě.
- **Stažení obsahu z obchodu ibooks, který má označení "Erotika"**: Zvolte **bloku** zastaví uživatelům zabránit ve stahování média z úložiště iBook označená jako erotická. **Není nakonfigurováno** povolí uživateli stahování knih z kategorie "Erotika".
- **Zobrazování firemních dokumentů v nespravovaných aplikacích**: **Blok** zabraňuje zobrazování nefiremních dokumentů v nespravovaných aplikacích. **Není nakonfigurováno** umožňuje podnikových dokumentů v jakékoli aplikaci zobrazit. Například chcete uživatelům zabránit v ukládání souborů z aplikace OneDrive do Dropboxu. Toto nastavení jako **bloku**. Až zařízení zásadu obdrží (třeba po restartování), již neumožňuje ukládání.
  - **Povolit spravovaným aplikacím zápis kontaktů na nespravované kontakty účty**: Pokud je nastavena na **povolit**, uživatelé mohou přidat nebo synchronizovat kontaktní údaje Outlook jakákoli osoba, včetně obchodních a podnikových kontaktů pro integrované aplikace kontakty na zařízení. Pokud je nastavena na **Nenakonfigurováno**, nebudou uživatelé moci přidávat kontaktům aplikace Outlook integrované aplikace kontakty na zařízení.
  
    Chcete-li toto nastavení použít, nastavte **zobrazování firemních dokumentů v nespravovaných aplikacích** nastavení **bloku**.
  
- **Zobrazování nefiremních dokumentů ve firemních aplikacích**: **Blok** zabraňuje zobrazování nefiremních dokumentů ve firemních aplikacích. **Není nakonfigurováno** umožňuje libovolného dokumentu ve spravovaných podnikových aplikacích prohlížení.
  - **Nespravované aplikace o čtení z účtů spravovaných kontakty**: Pokud je nastavena na **povolit**, uživatelé můžou přidávat jakákoli osoba iContacts aplikace kontaktní informace do aplikace Outlook. **Není nakonfigurováno** brání čtení, včetně odebrat duplicity, od integrované aplikace kontakty na zařízení.
  
    Chcete-li toto nastavení použít, nastavte **zobrazování nefiremních dokumentů ve firemních aplikacích** nastavení **bloku**.
  
- **Považovat AirDrop za nespravovaný cíl**: **Vyžadovat** vynutí AirDrop za nespravovaný cíl přetažení. To znemožní spravovaným aplikacím v odesílání dat pomocí Airdrop. 
- **Přidávání přátel na Game Center (jenom pod dohledem)**: **Blok** zabrání uživatelům v přidávání přátel v herním centru. **Není nakonfigurováno** umožňuje uživateli přidat přátele z Game Center.
- **Game Center (jenom pod dohledem)**: **Blok** použití aplikace herní centrum. **Není nakonfigurováno** umožňuje na zařízení použití aplikace herní centrum.
- **Hry pro víc hráčů (jenom pod dohledem)**: Zvolte **bloku** zabránit hry pro víc hráčů. **Není nakonfigurováno** povolí uživateli hrát na zařízení hry pro více hráčů.
- **Oblast hodnocení**: Zvolte oblast hodnocení, které chcete použít pro povolené soubory ke stažení. A potom zvolte povolená hodnocení pro **filmy** a **televizní pořady**.
- **Aplikace**: Zvolte povolené stáří hodnocení aplikace, které uživatelé můžou stahovat, nebo můžete zvolit **povolit všechny aplikace**.

## <a name="built-in-apps"></a>Integrované aplikace

- **Camera**: Zvolte **bloku** zabránit přístupu k fotoaparátu v zařízení. **Není nakonfigurováno** umožňuje přístup k fotoaparátu zařízení.
  - **FaceTime**: **Blok** zabránit přístupu k používání aplikace FaceTime. **Není nakonfigurováno** povolí přístup k používání aplikace FaceTime v zařízení.
- **Siri**: **Blok** brání v přístupu k Siri. **Není nakonfigurováno** povolí používání hlasového pomocníka Siri na zařízení.
  - **Siri při uzamčení zařízení zašifrovaná**: Zvolte **bloku** zabránit přístupu k Siri, když je zařízení zamknuté. **Není nakonfigurováno** povolí používání hlasového pomocníka Siri na zařízení, pokud je uzamčeno.
  - **Filtr vulgárních výrazů v Siri (jenom pod dohledem)**: **Vyžadovat** zabrání Siri diktovat a vyslovovat vulgární výrazy.
  - **Siri a dotazování na uživatelem generovaný obsah z Internetu (jenom pod dohledem)**: **Blok** zabrání Siri přístup na weby odpovědi na otázky. **Není nakonfigurováno** povolí Siri přístup k na uživatelem generovaný obsah z Internetu.
- **Apple News (jenom pod dohledem)**: Zvolte **bloku** zabránit přístupu k Apple News aplikace na zařízení. **Není nakonfigurováno** povolí používání aplikace Apple News.
- **obchod iBooks (jenom pod dohledem)**: **Blok** brání v přístupu k obchodu iBooks. **Není nakonfigurováno** umožňuje uživatelům procházení a nákup knih z obchodu iBooks.
- **Aplikace zprávy na zařízení (jenom pod dohledem)**: Zvolte **bloku** , uživatelé nemůžou používat aplikace zprávy na zařízení. **Není nakonfigurováno** umožňuje použití aplikace zprávy k odeslání a čtení textových zpráv.
- **Podcasty (jenom pod dohledem)**: **Blok** zabraňuje uživatelům používání aplikace podcasty. **Není nakonfigurováno** povolí používání aplikace podcasty.
- **Služba Music (jenom pod dohledem)**: **Blok** vrátí aplikace Music do klasického režimu a zakáže službu Hudba. **Není nakonfigurováno** povolí používání aplikace Apple Music.
- **Služba iTunes Radio (jenom pod dohledem)**: **Blok** zabrání uživatelům v používání aplikace iTunes Radio. **Není nakonfigurováno** povolí používání aplikace iTunes Radio.
- **Změny nastavení aplikace hledat přátele (jenom pod dohledem)**: **Blok** brání změny nastavení aplikace Find My Friends. **Není nakonfigurováno** umožňuje uživateli změnit nastavení aplikace Find My Friends.
- **Pomocí vyhledávání Spotlight a vracení výsledků z Internetu (jenom pod dohledem)**: **Blok** zastaví Spotlightu vracet výsledky z vyhledávání na Internetu. **Není nakonfigurováno** povolí Spotlightu hledání připojení k Internetu a výsledky hledání.
- **Blokovat odebírání systémových aplikací ze zařízení (jenom pod dohledem)**: Výběr **bloku** zakáže možnost odebrat aplikace pro systém ze zařízení. **Není nakonfigurováno** umožňuje uživatelům odebrat aplikace pro systém.

#### <a name="safari"></a>Safari

- **Safari**: **Blok** prostřednictvím prohlížeče Safari na zařízení. **Není nakonfigurováno** umožňuje uživatelům používat prohlížeč Safari.
- **Automatické vyplňování**: **Blok** zakáže funkci Automatické vyplňování v prohlížeči Safari na zařízení. **Není nakonfigurováno** umožňuje uživatelům změnit nastavení automatického dokončování v prohlížeči.
- **Soubory cookie**: Zvolte, jak se zpracovává soubory cookie v zařízení. Možnosti:
  - Povolit
  - Blokovat všechny soubory cookie
  - Povolit soubory cookie z navštívených webů
  - Povolit soubory cookie z aktuálního webu
- **JavaScript**: **Blok** brání skriptů Java v prohlížeči spuštěného v příslušném zařízení. **Není nakonfigurováno** umožňuje skriptů Java.
- **Upozornění na podvody**: **Vyžadovat** upozornění na podvody zobrazený ve webovém prohlížeči v zařízení. **Není nakonfigurováno** zakáže tuto funkci.
- **Automaticky otevíraná okna**: **Blok** zakázat blokování automaticky otevíraných oken ve webovém prohlížeči. **Není nakonfigurováno** umožňuje blokování automaticky otevíraných oken.

## <a name="restricted-apps"></a>Omezené aplikace

V seznamu omezených aplikací můžete nakonfigurovat jeden z následujících seznamů:

- **Zakázané aplikace**: Seznam aplikací, které nejsou spravované přes Intune, které nechcete, aby na zařízení nainstalovaná. Pokud uživatel aplikaci nainstaluje z tohoto seznamu, budete upozorněni prostřednictvím Intune.
- **Schválené aplikace**: Seznam aplikací, které uživatelé smějí instalovat. Chcete-li i nadále, nesmí uživatelé instalovat jiné aplikace. Aplikace, které spravuje Intune, jsou povolené automaticky. Pokud uživatel aplikaci nainstaluje z tohoto seznamu, budete upozorněni prostřednictvím Intune.

Přidání aplikací do těchto seznamů, můžete:

- **Přidat** v iTunes App storu adresu URL aplikace má. Například pokud chcete přidat aplikaci Microsoft Work Folders, zadejte `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`.

  Chcete-li vyhledat adresu URL aplikace, otevřete iTunes App Store a vyhledejte aplikaci. Například vyhledejte `Microsoft Remote Desktop` nebo `Microsoft Word`. Vyberte aplikaci a zkopírujte adresu URL.

  Pomocí iTunes taky můžete najít aplikaci a pak použít **Kopírovat odkaz** úloh získat adresu URL aplikace.

- Importujte soubor CSV s podrobnostmi o aplikaci, včetně adresy URL. Použijte formát `<app url>, <app name>, <app publisher>`. Nebo exportovat existující seznam, který obsahuje seznam aplikací s omezeným přístupem ve stejném formátu.

> [!IMPORTANT]
> Profily zařízení, které používají nastavení aplikace s omezeným přístupem musí přiřadit skupinám uživatelů.

## <a name="show-or-hide-apps-supervised-only"></a>Zobrazit nebo skrýt aplikace (jenom pod dohledem)

V seznamu zobrazit nebo skrýt aplikace můžete nakonfigurovat jeden z následujících seznamů na zařízeních pod dohledem s Iosem 9.3 nebo novější.

- **Skryté aplikace**: Zadejte seznam aplikací, které jsou skryté před uživateli. Uživatele nelze zobrazit, nebo otevřete tyto aplikace.
- **Viditelné aplikace**: Zadejte seznam aplikací, které uživatelé mohou zobrazit a spustit. Žádné jiné aplikace nebude možné zobrazit ani spustit.

Přidání aplikací do těchto seznamů, můžete:

- **Přidat** v iTunes App storu adresu URL aplikace má. Například pokud chcete přidat aplikaci Microsoft Work Folders, zadejte `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`.

  Chcete-li vyhledat adresu URL aplikace, otevřete iTunes App Store a vyhledejte aplikaci. Například vyhledejte `Microsoft Remote Desktop` nebo `Microsoft Word`. Vyberte aplikaci a zkopírujte adresu URL.

  Pomocí iTunes taky můžete najít aplikaci a pak použít **Kopírovat odkaz** úloh získat adresu URL aplikace.

- Importujte soubor CSV s podrobnostmi o aplikaci, včetně adresy URL. Použijte formát `<app url>, <app name>, <app publisher>`. Nebo exportovat existující seznam, který obsahuje seznam aplikací s omezeným přístupem ve stejném formátu.

## <a name="wireless"></a>Bezdrátová síť

- **Datový roaming**: Zvolte **bloku** zabránit datový roaming přes mobilní síť. **Není nakonfigurováno** (výchozí), povolí datový roaming, když je zařízení v mobilní síti.
- **Globální načítání na pozadí při roamingu**: **Blok** brání použití funkce načítání globální na pozadí při roamingu v mobilní síti. **Není nakonfigurováno** (výchozí) umožňuje, aby zařízení k načtení dat, jako jsou e-mailu, když používá roaming v mobilní síti.
- **Hlasové vytáčení**: Zvolte **bloku** k zabrání uživatelům využívat funkci hlasového vytáčení na zařízení. **Není nakonfigurováno** hlasového vytáčení na zařízení povolí (výchozí).
- **Hlasový roaming**: Zvolte **bloku** zabránit hlasový roaming přes mobilní síť. **Není nakonfigurováno** (výchozí), povolí hlasový roaming, když je zařízení v mobilní síti.
- **Změny nastavení využití mobilních dat aplikace (jenom pod dohledem)**: Zvolte **bloku** účelem Neumožnit změny nastavení využití mobilních dat v aplikaci. **Není nakonfigurováno** (výchozí) umožňuje uživateli řídit, které aplikace můžou používat mobilní data.
- **Změny nastavení plánu mobilní sítě (jenom pod dohledem)**: **Blok** zabraňuje uživatelům možnost měnit nastavení v mobilních plánu. **Není nakonfigurováno** (výchozí) umožňuje uživatelům provádět změny.

  Tato funkce platí pro:  
  - Iosu 11.0 a novějších

- **Osobní Hotspot**: **Blok** zabraňuje zařízení jako osobní hotspot. Někteří mobilní operátoři toto nastavení nemusí podporovat. **Není nakonfigurováno** (výchozí), umožňuje tato funkce.
- **Připojit se k sítím Wi-Fi jenom pomocí konfiguračních profilů (jenom pod dohledem)**: **Vyžadovat** zařízení donutí se použít jenom sítě Wi-Fi nastavily pomocí konfiguračních profilů Intune. **Není nakonfigurováno** (výchozí) umožňuje zařízení využívat jiné sítě Wi-Fi.
- **Pravidla používání mobilní sítě (jenom spravované aplikace)**: Definování dat, které typy, které spravované aplikace můžete použít při v mobilní síti. Možnosti:
  - **Zablokovat používání mobilních dat**: Zablokovat používání mobilních dat pro **všechny spravované aplikace** nebo **vybrat konkrétní aplikace**.
  - **Zablokovat používání mobilních dat při roamingu**: Zablokovat používání mobilních dat při roamingu pro **všechny spravované aplikace** nebo **vybrat konkrétní aplikace**.

## <a name="connected-devices"></a>Připojená zařízení

- **AirDrop (jenom pod dohledem)**: **Blok** brání použití AirDrop na zařízení. **Není nakonfigurováno** (výchozí) umožňuje použití funkce AirDrop k výměně obsahu s blízkými zařízeními.
- **Párování Apple Watch (jenom pod dohledem)**: **Blok** brání párování s Apple Watch. **Není nakonfigurováno** povolí zařízení spárovat se Apple Watch (výchozí).
- **Detekce zápěstí pro spárované Apple Watch**: **Vyžadovat** vynutí spárovaných Apple Watch používání detekce zápěstí. V případě potřeby, Apple Watch nebudou zobrazovat oznámení, když ho je uživatel nenasadí. 
- **Úpravy Bluetooth (jenom pod dohledem)**: **Blok** zabrání koncovému uživateli možnost měnit nastavení Bluetooth na zařízení. **Není nakonfigurováno** (výchozí) umožňuje uživatelům změnit tato nastavení.
- **Podle hostitelského párování určování zařízení, zařízení s Iosem může spárovat s (jenom pod dohledem)**: **Není nakonfigurováno** (výchozí) umožňuje, podle hostitelského párování může správce určit zařízení, která zařízení s Iosem může spárovat. **Blok** brání, podle hostitelského párování.
- **Vyžadovat odchozí požadavky párovací heslo**: **Vyžadovat** párovací heslo, když uživatel použije AirPlay ke streamování obsahu do jiných zařízení Apple. **Není nakonfigurováno** (výchozí) umožňuje uživateli ke streamování obsahu přes AirPlay bez zadávání hesla.
- **Blokování Airprintu (jenom pod dohledem)**: Zvolte **bloku** zabránit pomocí funkcí AirPrint na zařízení. **Není nakonfigurováno** (výchozí) umožňuje uživateli umožňuje využít AirPrint.
  - **Blokové úložiště přihlašovacích údajů AirPrint v řetězci klíčů (jenom pod dohledem)**: **Blok** brání použití řetězce klíčů úložiště pro uživatelské jméno a heslo na zařízení. **Není nakonfigurováno** (výchozí) umožní ukládání v aplikaci klíčenka AirPrint uživatelské jméno a heslo.
  - **Pro AirPrint (jenom pod dohledem) vyžadují důvěryhodný certifikát TLS**: **Vyžadovat** vynutí zařízení a používány důvěryhodné certifikáty pro komunikaci TLS tisku.
  - **Zablokuje zjišťování iBeacon z tiskárny s Airprintem (jenom pod dohledem)**: **Blok** brání škodlivým signály AirPrint Bluetooth před útoky typu phishing pro síťový provoz. **Není nakonfigurováno** (výchozí) umožňuje inzerování tiskárny s Airprintem na zařízení.
- **Blokovat nastavení si nové okolí zařízení (jenom pod dohledem)**: **Blok** zakáže výzvu k nastavení nová zařízení, která jsou poblíž. **Není nakonfigurováno** (výchozí) umožňuje výzvy pro uživatele pro připojení k dalším blízkým zařízením Apple.

  Tato funkce platí pro:  
  - Iosu 11.0 a novějších

## <a name="keyboard-and-dictionary"></a>Klávesnice a slovník

- **Vyhledávání definic slov (jenom pod dohledem)**: **Blok** zabraňuje uživatelům zvýraznění slovo a podívat se do její definice na zařízení. **Není nakonfigurováno** umožňuje přístup k definici funkce vyhledávání.
- **Prediktivní klávesnice (jenom pod dohledem)**: **Není nakonfigurováno** povolí používání prediktivních klávesnic navrhují slova uživatel může být vhodné. **Blok** brání tuto funkci.
- **Automatické opravy (jenom pod dohledem)**: **Není nakonfigurováno** umožňuje zařízení automaticky opravovat slova s překlepem. **Blok** brání použití automatických oprav.
- **(Jenom pod dohledem) Kontrola pravopisu klávesnice**: **Není nakonfigurováno** umožňuje používat v zařízení kontrolu pravopisu. **Blok** povolí kontrolu pravopisu.
- **Klávesové zkratky (jenom pod dohledem)**: **Není nakonfigurováno** umožní používání klávesových zkratek v zařízení. **Blok** zabrání uživateli v používání klávesových zkratek.
- **Diktování (jenom pod dohledem)**: **Blok** zabrání uživateli v používání hlasové zadávání textu. **Není nakonfigurováno** umožňuje uživateli používat vstup diktováním.

## <a name="cloud-and-storage"></a>Cloud a úložiště

- **Zálohování na iCloud**: **Není nakonfigurováno** povolí uživateli zálohovat zařízení do Icloudu. **Blok** zabrání uživateli zálohovat zařízení do Icloudu.
- **Zablokuje synchronizaci dokumentů s Icloudem**: **Není nakonfigurováno** povolí synchronizaci dokumentu a klíč hodnota s úložným prostorem Icloudu. **Blok** zabrání synchronizaci dokumenty a data serveru služby iCloud.
- **Synchronizace datového proudu fotografií s Icloudem**: **Není nakonfigurováno** umožňuje uživatelům povolit **tento Stream fotek** na svém zařízení synchronizovat na serveru služby iCloud a mít fotky, které jsou k dispozici na všech jeho zařízeních. **Blok** brání synchronizace datového proudu fotografií s Icloudem.
- **Šifrované zálohování**: **Vyžadovat** tak zálohy zařízení musí být zašifrován.
- **Knihovna fotografií na Icloudu**: Nastavte na **bloku** zakázat použití knihovny fotografií Icloudu, přes ukládat fotografie a videa v cloudu. Všechny fotky, které nejsou kompletně stažené z knihovny fotografií na Icloudu do zařízení se odebere ze zařízení. **Není nakonfigurováno** umožňuje použití knihovny fotografií Icloudu.
- **Synchronizace spravovaných aplikací do cloudu**: **Není nakonfigurováno** umožňuje aplikací Intune spravuje synchronizaci dat s účtem Icloudu. **Blok** zabraňuje tato synchronizace dat s Icloudem.
- **Sdílený stream fotek**: Zvolte **bloku** zakázat **sdílení fotek na Icloudu** na zařízení. **Není nakonfigurováno** umožňuje streamování fotek sdílené.
- **Pokračování aktivity**: **Není nakonfigurováno** umožňuje pokračovat v práci zahájil na zařízení s Iosem na jiném zařízení s Iosem nebo macOS (Handoff). **Blok** zabraňuje tato odložení.
- **Blokovat synchronizaci řetězce klíčů serveru služby iCloud**: Zvolte **bloku** zakázat synchronizaci přihlašovacích údajů uložených v řetězci klíčů s Icloudem. **Není nakonfigurováno** umožňuje uživatelům synchronizovat tyto přihlašovací údaje.
- **Zablokovat zálohu kniha Enterprise**: Zvolte **bloku** uživatelům zabránit v zálohování knihy enterprise. **Není nakonfigurováno** umožňuje uživatelům k zálohování těchto seznamů.
- **Blokovat synchronizace metadat kniha enterprise (poznámky a zvýraznění)**: **Blok** zabraňuje synchronizaci poznámky a zvýrazní v organizace knihy. **Není nakonfigurováno** umožňuje synchronizaci.

## <a name="autonomous-single-app-mode-supervised-only"></a>Autonomní režim jedné aplikace (jenom pod dohledem)

Pomocí těchto nastavení můžete nakonfigurovat zařízení s Iosem spustit konkrétní aplikace v autonomním režimu jedné aplikace. Když je tento režim nakonfigurovaný a spuštění aplikace, je zařízení uzamčené. Spustí tuto aplikaci. Například přidejte aplikaci, která uživatelům umožňuje absolvovat na zařízení test. Když se akce aplikace dokončí nebo tuto zásadu odeberete, zařízení se vrátí do normálního stavu.

Přidání aplikací, můžete:

- Zadejte **název aplikace** a **ID sady prostředků aplikace**a vyberte **přidat**. [ID sady pro vestavěné aplikace iOS](#bundle-ids-for-built-in-ios-apps) (v tomto článku) zahrnuje některé aplikace pomocí jejich identifikátorů.
- **Import** soubor CSV se seznamem názvů aplikací a jejich ID sady prostředků. Nebo, **exportovat** existujícího seznamu, který obsahuje aplikace.

## <a name="kiosk-supervised-only"></a>Veřejný terminál (jenom pod dohledem)

- **Aplikace ale běží v beznabídkovém režimu**: Zvolte typ aplikace, které chcete v beznabídkovém režimu spouštět. Možnosti:
  - **Není nakonfigurováno**: Veřejný terminál, nastavení se nepoužijí. Zařízení není spuštěna v režimu veřejného terminálu.
  - **App Store**: Zadejte adresu URL aplikace v iTunes App storu.
  - **Spravovaná aplikace**: Zvolte aplikaci, kterou jste přidali do Intune.
  - **Integrovaná aplikace**: Zadejte [ID sady](#bundle-ids-for-built-in-ios-apps) (v tomto článku) integrované aplikace.

- **Dotykového ovládání pro usnadnění**: **Vyžadovat** nastavení usnadnění dotykového ovládání bude na zařízení. Tato funkce pomáhá uživatelům na obrazovce gesta, která může být obtížné pro ně. **Není nakonfigurováno** nelze spustit nebo povolit tuto funkci v celoobrazovkovém režimu.
- **Invertovat barvy**: **Vyžadovat** Invertovat barvy pro usnadnění nastavení, uživatelům se zrakovým můžete změnit zobrazení obrazovky. **Není nakonfigurováno** nelze spustit nebo povolit tuto funkci v celoobrazovkovém režimu.
- **Monofonní zvuk**: **Vyžadovat** nastavení Mono zvuk usnadnění se v zařízení. **Není nakonfigurováno** nelze spustit nebo povolit tuto funkci v celoobrazovkovém režimu.
- **VoiceOver**: **Vyžadovat** nastavení usnadnění VoiceOver bude na zařízení nahlas číst text na obrazovce. **Není nakonfigurováno** nelze spustit nebo povolit tuto funkci v celoobrazovkovém režimu.
- **Přiblížení**: **Vyžadovat** nastavení přiblížení či oddálení bude na zařízení, umožníte uživatelům používat dotykové ovládání pro zvětšení na obrazovce. **Není nakonfigurováno** nelze spustit nebo povolit tuto funkci v celoobrazovkovém režimu.
- **Automatické zamykání**: **Povolit** automatické uzamykání zařízení. **Není nakonfigurováno** zakáže tuto funkci.
- **Přepnutí vyzvánění**: **Povolit** přepínač vyzvánění (ztlumení) na zařízení. **Není nakonfigurováno** zakáže tuto funkci.
- **Otočení obrazovky**: **Povolit** změnu orientace obrazovky, když uživatel otočí zařízení. **Není nakonfigurováno** zakáže tuto funkci.
- **Tlačítko režimu spánku obrazovky**: Zvolte **povolit** zakázat na zařízení tlačítko probuzení obrazovky z režimu spánku. **Není nakonfigurováno** povolí tuto funkci.
- **Touch**: **Blok** zakáže dotykovou obrazovku na zařízení. **Není nakonfigurováno** umožňuje uživateli umožňuje využít dotykovou obrazovku.
- **Tlačítka pro hlasitost**: **Povolit** použití tlačítek hlasitosti na zařízení. **Není nakonfigurováno** zakáže tlačítka hlasitosti.
- **Dotykové ovládání**: **Povolit** můžou uživatelé používat funkce usnadnění dotykového ovládání. **Není nakonfigurováno** zakáže tuto funkci.
- **Ovládací prvek Invertovat barvy**: **Povolit** Invertovat barvy změny, umožníte uživatelům nastavit funkci inverze barev. **Není nakonfigurováno** zakáže tuto funkci.
- **Přečíst vybraný text**: **Povolit** nastavení usnadnění výběr řeči bude na zařízení. Tato funkce přečte text, který uživatel vybere nahlas. **Není nakonfigurováno** zakáže tuto funkci.
- **Ovládací prvek voiceOver**: **Povolit** voiceover změny umožňuje uživatelům aktualizovat funkci nástroje VoiceOver, jako je například rychlost čtení na obrazovce text nahlas. **Není nakonfigurováno** zabránilo změnám voiceover.
- **Ovládací prvek Lupa**: **Povolit** přiblížení změny uživatelem. **Není nakonfigurováno** zabránilo změnám přiblížení.

> [!NOTE]
> Než budete moct nakonfigurovat nastavení zařízení s iOSem pro celoobrazovkový (beznabídkový) režim, musíte převést zařízení do režimu dohledu pomocí nástroje Apple Configurator nebo Programu registrace zařízení Apple. V příručce společnosti Apple pomocí Apple configuratoru.
> Pokud zadáte aplikace pro iOS nainstaluje až přiřadíte profil, zařízení nebude zadejte celoobrazovkový režim až po restartování zařízení.

## <a name="domains"></a>Domény

- **Zrušit označení e-mailových domén** > **e-mailová adresa URL domény**: Přidejte jeden nebo více adres URL do seznamu. Když koncoví uživatelé dostanou e-mail z jiné domény než domény můžete zadat, označí se e-mail jako nedůvěryhodný v aplikaci iOS Mail.

- **Spravované webové domény** > **adresa URL webové domény**; Přidejte jeden nebo více adres URL do seznamu. Pokud stahujete dokumenty z těchto zadaných domén, které jste zadali, budou považovány za spravované. Toto nastavení platí jenom pro dokumenty stažené prostřednictvím prohlížeče Safari.

- **Domény pro automatické vyplňování hesel v Safari** > **adresa URL domény**: Přidejte jeden nebo více adres URL do seznamu. Uživatelé si mohou uložit jenom webová hesla z adres URL uvedených v tomto seznamu. Toto nastavení platí jenom pro prohlížeč Safari a pro zařízení s iOSem 9.3 a novějším v režimu pod dohledem. Pokud nezadáte žádné adresy URL, můžete si uložit hesla ze všech webů.

## <a name="bundle-ids-for-built-in-ios-apps"></a>ID sady prostředků pro integrované aplikace pro iOS

Tento seznam zobrazuje ID sady prostředků některých běžných integrovaných aplikací pro iOS. Pokud chcete najít ID sady prostředků jiných aplikací, obraťte se na dodavatele softwaru.

| ID sady prostředků                   | Název aplikace     | Vydavatel |
|-----------------------------|--------------|-----------|
| com.apple.AppStore          | App Store    | Apple     |
| com.apple.calculator        | Kalkulačka   | Apple     |
| com.apple.mobilecal         | Kalendář     | Apple     |
| com.apple.camera            | Fotoaparát       | Apple     |
| com.apple.mobiletimer       | Hodiny        | Apple     |
| com.apple.compass           | Kompas      | Apple     |
| com.apple.MobileAddressBook | Kontakty     | Apple     |
| com.apple.facetime          | FaceTime     | Apple     |
| com.apple.DocumentsApp      | Soubory        | Apple     |
| com.apple.mobileme.fmf1     | Najít přátele | Apple     |
| com.apple.mobileme.fmip1    | Najít iPhone  | Apple     |
| com.apple.gamecenter        | Herní centrum  | Apple     |
| com.apple.mobilegarageband  | GarageBand   | Apple     |
| com.apple.Health            | Stav       | Apple     |
| com.apple.Home              | Domů         | Apple     |
| com.apple.iBooks            | iBooks       | Apple     |
| com.apple.iMovie            | iMovie       | Apple     |
| com.apple.itunesconnect.mobile | iTunes Connect | Apple |
| com.apple.MobileStore       | iTunes Store | Apple     |
| com.apple.itunesu           | iTunes U     | Apple     |
| com.apple.Keynote           | Keynote      | Apple     |
| com.apple.mobilemail        | Mail         | Apple     |
| com.apple.Maps              | Maps         | Apple     |
| com.apple.MobileSMS         | Zprávy     | Apple     |
| com.apple.Music             | Hudba        | Apple     |
| com.apple.news              | News         | Apple     |
| com.apple.mobilenotes       | Poznámky        | Apple     |
| com.apple.Numbers           | Numbers      | Apple     |
| com.apple.Pages             | Stránky        | Apple     |
| com.apple.Photo-Booth       | Photo Booth  | Apple     |
| com.apple.mobileslideshow   | Fotky       | Apple     |
| com.apple.podcasts          | Podcasty     | Apple     |
| com.apple.reminders         | Připomínky    | Apple     |
| com.apple.mobilesafari      | Safari       | Apple     |
| com.apple.Preferences       | Nastavení     | Apple     |
| com.apple.SiriViewService   | Siri         | Apple     |
| com.apple.stocks            | Stocks       | Apple     |
| com.apple.tips              | Tipy         | Apple     |
| com.apple.TV                | TV           | Apple     |
| com.apple.videos            | Videa       | Apple     |
| com.apple.VoiceMemos        | Diktafon   | Apple     |
| com.apple.Passbook          | Wallet       | Apple     |
| com.apple.Bridge            | Sledování        | Apple     |
| com.apple.weather           | Počasí      | Apple     |

## <a name="settings-that-require-supervised-mode"></a>Nastavení vyžadujících režim pod dohledem

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
> Apple potvrdil, že některá nastavení přesunout na pod dohledem v jen 2019. Doporučujeme, abyste to udělali v úvahu při používání těchto nastavení, místo abyste čekali, Apple k migraci je jenom pod dohledem pro:
> - Instalace aplikací koncovými uživateli
> - Odebrání aplikace
> - FaceTime
> - Safari
> - iTunes
> - Explicitní obsah
> - Dokumenty a data v iCloudu
> - Hry pro víc hráčů
> - Přidat přátele z herního centra
> - Siri

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Funkce a nastavení zařízení můžete taky omezit na [macOS](device-restrictions-macos.md) zařízení.
