---
title: Nastavení zařízení s androidem Enterprise v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Na zařízeních s Androidem Enterprise nebo Androidem for Work můžete omezit nastavení zařízení, včetně kopírování a vkládání, zobrazování oznámení, oprávnění aplikací, sdílení dat, délky hesla, selhání přihlášení, použití otisku prstu k odemknutí, opětovnému použití hesla a povolení Bluetooth. sdílení pracovních kontaktů. Nakonfigurovat zařízení jako veřejný terminál zařízení, aby spouštěl jednu aplikaci nebo více aplikací.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7d9c385ff8c08f9f1df00a081bca1f61a2a5015a
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/05/2019
ms.locfileid: "74832550"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>Nastavení zařízení s androidem Enterprise k povolení nebo zakázání funkcí pomocí Intune

Tento článek uvádí a popisuje různá nastavení, které můžete řídit na zařízeních s Androidem Enterprise. Jako součást řešení správy mobilních zařízení (MDM) pomocí těchto nastavení můžete povolit nebo zakázat funkce, spouštět aplikace na vyhrazených zařízeních, zabezpečení řízení a další.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](device-restrictions-configure.md).

## <a name="device-owner-only"></a>Pouze vlastník zařízení

Tato nastavení se vztahují na typy registrace Androidu Enterprise, kde Intune řídí celé zařízení, jako jsou například plně spravovaná nebo vyhrazená zařízení se systémem Android Enterprise.

### <a name="general-settings"></a>Obecná nastavení

- **Snímek obrazovky**: Zvolte **bloku** k zabránění snímky obrazovky nebo na zařízení snímky obrazovky. Brání tím také zobrazení obsahu na zobrazovacích zařízeních, která nemají bezpečný výstup videa. **Není nakonfigurováno** umožňuje uživateli zachytit obsah obrazovky jako obrázek.
- **Fotoaparát**: Zvolte **bloku** zabránit přístupu k fotoaparátu v zařízení. **Není nutné** umožňuje přístup k fotoaparátu zařízení.
- **Výchozí zásady oprávnění**: Toto nastavení definuje výchozí zásady oprávnění pro žádosti o oprávnění za běhu. Mezi možné hodnoty patří:
  - **Výchozí ze zařízení**: Použije se výchozí nastavení zařízení.
  - **Zeptat se**: Uživateli se zobrazí výzva ke schválení oprávnění.
  - **Automaticky udělit**: Oprávnění jsou udělena automaticky.
  - **Automaticky odepřít**: Oprávnění jsou odepřena automaticky.
- **Datum a čas změny**: Zvolte **bloku** ručně nastavovat datum a čas, moct uživatelé. **Není nakonfigurováno** umožňuje uživatelům nastavit datum a čas na zařízení.
- **Změny svazku**: **blok** znemožní uživatelům měnit svazek zařízení a také mutes hlavní svazek. **Není nakonfigurováno** umožňuje používat nastavení hlasitosti na zařízení.
- **Obnovení továrního nastavení**: Zvolte **bloku** zabrání uživatelům využívat objekt factory, které obnoví nastavení možnost v nastavení zařízení. **Není nakonfigurováno** umožňuje uživatelům použít toto nastavení na zařízení.
- **Bezpečné spuštění**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v restartování zařízení do nouzového režimu. **Není nakonfigurováno** umožňuje restartovat zařízení v nouzovém režimu.
- **Stavový řádek**: Zvolte **bloku** chcete zabránit přístupu do stavového řádku, včetně oznámení a rychlých nastavení. **Není nakonfigurováno** umožňuje uživatelům přístup k stavový řádek.
- **Roaming dat služby**: Zvolte **bloku** zabránit datový roaming přes mobilní síť. **Není nakonfigurováno** povolí datový roaming, když je zařízení v mobilní síti.
- **Změny nastavení Wi-Fi**: Zvolte **bloku** zabránit uživatelům možnost měnit nastavení Wi-Fi vytvořených vlastníkem zařízení. Uživatelé můžou vytvářet své vlastní konfigurace Wi-Fi. **Není nakonfigurováno** umožňuje uživatelům změnit nastavení Wi-Fi na zařízení.
- **Konfigurace přístupového bodu Wi-Fi**: Zvolte **bloku** chcete zabránit uživatelům ve vytváření nebo změně konfigurace Wi-Fi. **Není nakonfigurováno** umožňuje uživatelům změnit nastavení Wi-Fi na zařízení.
- **Konfigurace technologie Bluetooth**: Zvolte **bloku** uživatelům zabránit v konfiguraci Bluetooth na zařízení. **Není nakonfigurováno** umožňuje používat Bluetooth na zařízení.
- **Sdílení internetového připojení přes a přístup k hotspotům**: Zvolte **bloku** chcete zabránit ve sdílení internetového připojení přes a přístup na přenosné aktivní. **Není nakonfigurováno** umožňuje sdílení internetového připojení přes a přístup na přenosné aktivní.
- **Úložiště USB**: Zvolte **povolit** do úložiště USB na zařízení. **Není nakonfigurováno** brání v přístupu k úložiště USB.
- **Přenos souborů USB**: Zvolte **bloku** aby se zabránilo přenosu souborů přes USB. **Není nakonfigurováno** umožňuje přenos souborů.
- **Externí médium**: Zvolte **bloku** zabránit použití nebo připojení všechny externí médium v zařízení. **Není nakonfigurováno** povoluje externí médium v zařízení.
- **Světlo dat pomocí NFC**: Zvolte **bloku** zabránit světla dat z aplikací pomocí technologie téměř Field Communication (NFC). **Není nakonfigurováno** umožňuje pomocí NFC ke sdílení dat mezi zařízeními.
- **Funkce ladění**: Zvolte **povolit** můžou uživatelé používat funkce ladění na zařízení. **Není nakonfigurováno** uživatelům bránit v použití funkce ladění na zařízení.
- **Úprava mikrofonu**: Zvolte **bloku** uživatelům zrušit ztlumení mikrofonu a upravit hlasitosti mikrofonu. **Není nakonfigurováno** umožňuje uživateli používat a hlasitosti mikrofonu v zařízení.
- **E-maily pro ochranu před resetováním do továrního nastavení**: Zvolte **e-mailové adresy účtů Google**. Zadejte e-mailové adresy správců zařízení, které můžete odemknout zařízení, poté, co se vymaže. Ujistěte se, zda jste e-mailové adresy oddělujte středníkem, třeba `admin1@gmail.com;admin2@gmail.com`. Pokud není zadán e-mailu, kdokoli odemknutí zařízení po obnovení do továrního nastavení. Tyto e-maily se použijí jenom v případě, že se spustilo obnovení uživatelem bez uživatele, jako je třeba spuštění obnovení továrního nastavení pomocí nabídky obnovení.
- **Sítě únikový poklop**: Zvolte **povolit** uživatelé zapnout funkci sítě řídicí šrafování. Pokud připojení k síti není proveden, jakmile se spustí zařízení, únikový poklop vyzve k dočasnému připojení k síti a aktualizovat zásady zařízení. Po uplatnění zásad se tato dočasná síť zapomene a zařízení pokračuje ve spouštění. Pokud tuto funkci připojení zařízení k síti:
  - V posledních zásadách není vhodné síťové.
  - Zařízení se spustí do aplikace v režimu uzamčení úloh.
  - Uživatel se nám kontaktovat nastavení zařízení.

  **Není nakonfigurováno** zabraňuje uživatelům v zapnutí funkce šrafování řídicí sítě na zařízení.

- **Aktualizace systému**: Zvolte možnost definovat způsob, jakým zpracovává aktualizace distribuované bezdrátově zařízení:
  - **Výchozí ze zařízení**: Použije se výchozí nastavení zařízení.
  - **Automaticky**: Aktualizace se instalují automaticky bez zásahu uživatele. Po nastavení této zásady se hned nainstalují všechny čekající aktualizace.
  - **Odloženo**: Aktualizace se odloží o 30 dní. Na konci na 30 dnů Android se zobrazí výzva k instalaci aktualizace. Výrobci zařízení nebo mobilní operátoři mohou zakázat (vyloučit) odklad důležitých aktualizací zabezpečení. Vynechaná aktualizace zobrazí uživateli zařízení zprávu systému.
  - **Časové období údržby**: Aktualizace se instalují automaticky během časového období údržby, které nastavíte v Intune. Instalace pokusí denně po dobu 30 dnů a může selhat, pokud je nedostatek místa či baterie úrovněmi. Po 30 dnech Android se zobrazí výzva k instalaci. Toto okno se také používá k instalaci aktualizací aplikací Play. Tuto možnost použijte pro vyhrazená zařízení, jako jsou veřejné terminály, protože je možné aktualizovat aplikace v popředí vyhrazené pro jednotlivé aplikace.

- **Okna oznámení**: Pokud je nastavení **zakázané**, oznámení oken, včetně informačních zpráv, příchozích volání, odchozích volání, systémových výstrah a systémových chyb, se na zařízení nezobrazují. Pokud je nastavené na **Nenakonfigurováno**, použije se výchozí operační systém, který může zobrazovat oznámení.
- **Přeskočit první tipy k použití**: **Povolit** skryje nebo přeskočí návrhy z aplikací, které procházejí kurzy, nebo když se aplikace spustí. Pokud je nastavené na **Nenakonfigurováno**, použije se výchozí operační systém, který může zobrazovat tyto návrhy při spuštění aplikace.

### <a name="system-security-settings"></a>Systémové nastavení zabezpečení

- **Kontrola hrozeb v aplikacích**: **vyžadovat** (výchozí) umožňuje Google Play chránit před instalací a po jejich instalaci. Pokud zjistí hrozbu, může uživateli upozornit na odebrání aplikace ze zařízení. **Není nakonfigurováno** , nepovolí ani nespustí Google Play chránit pro kontrolu aplikací.

### <a name="dedicated-device-settings"></a>Nastavení vyhrazeného zařízení

Pomocí těchto nastavení můžete nakonfigurovat možnosti veřejného terminálu na vyhrazených zařízeních. Můžete nakonfigurovat zařízení tak, aby spouštělo jednu aplikaci nebo spustilo spoustu aplikací. Když je zařízení nastavené s beznabídkovým režimem, k dispozici jsou jenom aplikace, které přidáte. Tato nastavení platí pro zařízení s Androidem Enterprise vyhrazená. Nevztahují se na zařízení s plně spravovaným systémem Android Enterprise.

**Celoobrazovkový režim**: vyberte, jestli má zařízení spuštěnou jednu aplikaci, nebo spustí víc aplikací.

- **Jediná aplikace**: uživatelé mají přístup jenom k jedné aplikaci na zařízení. Při spuštění zařízení spustí jenom konkrétní aplikace. Uživatelé nemůžou otevírat nové aplikace ani měnit spuštěnou aplikaci.

  - **Vyberte spravovanou aplikaci**: ze seznamu vyberte spravovanou aplikaci Google Play.

    Pokud nemáte žádné aplikace, pak uvedené [přidat některé aplikace pro Android](../apps/apps-add-android-for-work.md) do zařízení. Nezapomeňte [aplikaci přiřadit ke skupině zařízení vytvořené pro vaše vyhrazená zařízení](../apps/apps-deploy.md).

  > [!IMPORTANT]
  > Pokud používáte celoobrazovkový režim s jednou aplikací, aplikace Dial/Phone nemusí správně fungovat. 
  
- **Multi-aplikace**: uživatelé mají přístup k omezené sadě aplikací na zařízení. Při spuštění zařízení, spustit pouze aplikace, které přidáte. Můžete také přidat některé webové odkazy, které uživatelé můžou otevírat. Když se zásady vztahují, uživatelé uvidí ikony pro povolené aplikace na domovské obrazovce.

  > [!IMPORTANT]
  > U vyhrazených zařízení s více aplikacemi **musí být** [aplikace spravované domovské obrazovky](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) z Google Play:
  >   - [Přidat jako klientskou aplikaci](../apps/apps-add-android-for-work.md) v Intune
  >   - [Přiřazeno ke skupině zařízení](../apps/apps-deploy.md) vytvořené pro vyhrazená zařízení
  >
  > **Spravované domovskou obrazovku** aplikace nemusí být v profilu konfigurace, ale je potřeba přidat jako klientská aplikace. Když se **spravovaná aplikace pro domovskou obrazovku** přidá jako klientská aplikace, všechny ostatní aplikace, které přidáte do konfiguračního profilu, se zobrazí jako ikony v aplikaci **spravované domovské obrazovky** .
  >
  > Při použití celoobrazovkového režimu s více aplikacemi nemusí aplikace Dial/Phone fungovat správně. 

  - **Přidat**: vyberte své aplikace ze seznamu.

    Pokud **spravované domovskou obrazovku** aplikace není uvedená, pak [přidat na webu Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Nezapomeňte [aplikaci přiřadit](../apps/apps-deploy.md) ke skupině zařízení vytvořené pro vaše vyhrazená zařízení.

    Můžete také přidat další [aplikace pro Android](../apps/apps-add-android-for-work.md) a [webové aplikace](../apps/web-app.md) vytvořená vaší organizací na zařízení. Nezapomeňte [aplikaci přiřadit ke skupině zařízení vytvořené pro vaše vyhrazená zařízení](../apps/apps-deploy.md).

  - **Tlačítko virtuální domů**: tlačítko měkkého klíče, které vrátí uživatele do spravované domovské obrazovky, aby uživatelé mohli přepínat mezi aplikacemi. Možnosti:

    - **Nenakonfigurováno** (výchozí): tlačítko domů není zobrazeno. Uživatelé musí použít tlačítko zpět k přepínání mezi aplikacemi.
    - **Potažení nahoru**: na domovském tlačítku se zobrazí, když uživatel na zařízení potáhne.
    - **Float**: zobrazuje na zařízení trvalé a plovoucí tlačítko domů.

  - **Ukončit režim veřejného terminálu**: Zvolte **povolit** umožňují správcům dočasně pozastavit celoobrazovkový režim pro aktualizaci zařízení. Chcete-li použít tuto funkci, správce:
  
    1. Pokračuje v výběru tlačítka zpět, dokud se nezobrazí tlačítko **ukončit veřejný terminál** . 
    2. Vybere tlačítko **ukončit veřejný terminál** a přejde do kódu PIN pro **celoobrazovkový režim** .
    3. Po dokončení vyberte aplikaci **spravovaná domovskou obrazovku** . Tento krok relocks zařízení do režimu veřejného terminálu s více aplikacemi.

      Pokud se nastaví jako **nenakonfigurované**, správci nemůžou pozastavit celoobrazovkový režim. Pokud správce pokračuje v výběru tlačítka zpět a vybere tlačítko **ukončit veřejný terminál** , pak se zobrazí zpráva, že je vyžadováno heslo.

    - **Ponechte kódu celoobrazovkový režim**: zadejte číslice 4 až 6 číselný kód PIN. Správce používá tento PIN kód se dočasně pozastavit beznabídkový režim.

  - **Nastavit vlastní adresu URL pozadí**: zadejte adresu URL pro přizpůsobení obrazovky na pozadí na vyhrazeném zařízení.

    > [!NOTE]
    > Ve většině případů doporučujeme začít s imagemi alespoň následujících velikostí:
    >
    > - Telefon: 1080x1920 px
    > - Tablet: 1080 px
    >
    > Pro dosažení co nejlepších výsledků a zaostření podrobností je navrženo, že se pro jednotlivé položky obrázku zařízení vytvořily specifikace zobrazení.
    >
    > Moderní displeje mají vyšší hustotu pixelů a můžou zobrazovat ekvivalentní image definice 2K/4K.

  - **Konfigurace Wi-Fi**: **možnost Povolit** zobrazí ovládací prvek Wi-Fi na spravované domovské obrazovce a koncovým uživatelům umožňuje připojit zařízení k různým sítím Wi-Fi. Povolením této funkce se taky zapne umístění zařízení. **Nenakonfigurováno** (výchozí): nezobrazuje ovládací prvek Wi-Fi na spravované domovské obrazovce. Zabraňuje uživatelům v připojení k sítím Wi-Fi při použití spravované domovské obrazovky.

  - **Konfigurace Bluetooth**: **Povolit** zobrazí ovládací prvek Bluetooth na spravované domovské obrazovce a koncovým uživatelům umožňuje párovat zařízení přes Bluetooth. Povolením této funkce se taky zapne umístění zařízení. **Nenakonfigurováno** (výchozí): nezobrazuje ovládací prvek Bluetooth na spravované domovské obrazovce. Brání tak uživatelům v konfiguraci zařízení Bluetooth a párování zařízení při použití spravované domovské obrazovky.

  - **Svítící Access**: **Enable** zobrazí ovládací prvek svítící na spravované domovské obrazovce a umožní koncovým uživatelům zapnout nebo vypnout svítící. **Nenakonfigurováno** (výchozí): nezobrazuje ovládací prvek svítící na spravované domovské obrazovce. Zabraňuje uživatelům v používání svítící při použití spravované domovské obrazovky.

  - **Ovládání hlasitosti médií**: **Povolit** zobrazí ovládací prvek hlasitost média na spravované domovské obrazovce a koncovým uživatelům umožňuje upravit hlasitost média zařízení pomocí posuvníku. **Nenakonfigurováno** (výchozí): nezobrazuje ovládací prvek hlasitost multimédií na spravované domovské obrazovce. Zabraňuje uživatelům upravovat hlasitost médií zařízení při použití spravované domovské obrazovky, pokud jim jejich hardwarová tlačítka nepodporují. 

  - **Režim spořiče obrazovky**: **možnost Povolit** zobrazí na spravované domovské obrazovce spořič obrazovky, když je zařízení uzamčeno nebo vypršel časový limit. **Nenakonfigurováno** (výchozí): Nezobrazovat šetřič obrazovky na spravované domovské obrazovce.

    Pokud je tato možnost povolená, nakonfigurujte taky:

    - **Nastavit vlastní obrázek spořiče obrazovky**: zadejte adresu URL pro vlastní PNG, jpg, JPEG, GIF, BMP, WEBP nebo ICOimage. Zadejte například:

      - `http://www.contoso.com/image.jpg`
      - `www.contoso.com/image.bmp`
      - `https://www.contoso.com/image.webp`

      Pokud adresu URL nezadáte, použije se výchozí image zařízení, pokud je k dispozici výchozí image.
      
      > [!TIP]
      > Je podporována jakákoli adresa URL prostředku souboru, která může být převedena do rastrového obrázku.

    - **Počet sekund, po které zařízení zobrazuje spořič obrazovky před**vypnutím obrazovky: vyberte, jak dlouho zařízení zobrazí spořič obrazovky. Zadejte hodnotu v rozmezí 0-9999999 sekund. Výchozí hodnota je `0` sekund. Pokud je ponecháno prázdné nebo je nastaveno na hodnotu nula (`0`), je spořič obrazovky aktivní, dokud uživatel nekomunikuje se zařízením.
    - **Počet sekund neaktivních zařízení před zobrazením spořiče obrazovky**: vyberte, jak dlouho bude zařízení nečinné, než se zobrazí. Zadejte hodnotu v rozmezí 1-9999999 sekund. Výchozí hodnota je `30` sekund. Je nutné zadat číslo větší než nula (`0`).
    - **Rozpoznat médium před spuštěním spořiče obrazovky**: **Povolit** (výchozí) nezobrazuje spořič obrazovky, pokud se na zařízení přehrává zvuk nebo video. **Nenakonfigurováno** zobrazuje spořič obrazovky i v případě, že přehrávání zvuku nebo videa probíhá.

### <a name="device-password-settings"></a>Nastavení hesla zařízení

- **Zakázat zamykací obrazovku**: Pokud chcete zabránit uživatelům používat na zařízení funkci zámku zamykací obrazovky, vyberte **Zakázat** . **Není nakonfigurováno** umožňuje uživateli používat Keyguard funkce.
- **Zakázané funkce zamykací obrazovky**: Pokud je na zařízení povolená klávesa Guard, vyberte, které funkce se mají zakázat. Pokud je například zaškrtnuto políčko **Zabezpečená kamera** , funkce kamery je na zařízení zakázaná. Na zařízení jsou povolené všechny funkce, které nejsou zaškrtnuté.

  Tyto funkce jsou uživatelům k dispozici, když je zařízení zamčené. Uživatelům se nezobrazí nebo nebudou mít přístup k vybraným funkcím.

- **Požadovaný typ hesla**: Definujte typ hesla požadovaného pro zařízení. Možnosti:
  - **Výchozí ze zařízení**
  - **Vyžaduje se heslo, žádná omezení.**
  - **Slabý biometrika**: [silný vs. slabý biometrika](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (otevře web v Androidu)
  - **Číselná**: heslo musí obsahovat pouze čísla, například `123456789`. Zadejte **minimální délku hesla** , kterou musí uživatel zadat, a to v rozmezí 4 až 16 znaků.
  - **Číselné komplexní**: opakovaných nebo po sobě jdoucí čísla, jako je například "1111" nebo "1234" nejsou povoleny. Zadejte **minimální délku hesla** , kterou musí uživatel zadat, a to v rozmezí 4 až 16 znaků.
  - **Abecedy**: jsou vyžadovány písmena v abecedě. Čísla a symboly nejsou požadovány. Zadejte **minimální délku hesla** , kterou musí uživatel zadat, a to v rozmezí 4 až 16 znaků.
  - **Alfanumerické**znaky: obsahuje velká písmena, malá písmena a číslice. Zadejte **minimální délku hesla** , kterou musí uživatel zadat, a to v rozmezí 4 až 16 znaků.
  - **Alfanumerické znaky se symboly**: zahrnují velká písmena, malá písmena, číslice, interpunkční znaménka a symboly. Dále zadejte:

    - **Minimální délka hesla**: zadejte minimální délku hesla, která musí být delší než 4 až 16 znaků.
    - **Požadovaný počet znaků**: zadejte počet znaků, které musí heslo obsahovat, a to v rozmezí 0 až 16 znaků.
    - **Počet požadovaných malých**písmen: zadejte počet malých písmen, které musí heslo obsahovat, a to v rozmezí 0 až 16 znaků.
    - **Počet požadovaných velkých znaků**: zadejte počet velkých písmen, které musí heslo obsahovat, a to v rozmezí 0 až 16 znaků.
    - **Počet požadovaných znaků bez**písmen: zadejte počet jiných než písmen (kromě písmen v abecedě), které musí heslo obsahovat, 0 až 16 znaků.
    - **Požadovaný počet**číslic: zadejte počet číselných znaků (`1`, `2`, `3`atd.) heslo musí mít 0 až 16 znaků.
    - **Požadovaný počet znaků symbolu**: zadejte počet znaků symbolu (`&`, `#`, `%`atd.) heslo musí mít 0 až 16 znaků.

- **Počet dní do vypršení platnosti hesla**: zadejte počet dnů (v rozmezí 1-365), do kterého se musí heslo zařízení změnit. Pokud například chcete změnit heslo po 60 dnech, zadejte `60`. Po vypršení platnosti hesla se uživatelům zobrazí výzva k vytvoření nového hesla.
- **Počet hesel požadovaných před tím, než uživatel může resuse heslo**: zadejte počet nedávných hesel, která se nesmí znovu použít, mezi 1-24. Toto nastavení použijte, pokud chcete uživateli zabránit ve vytváření hesel, která používal dříve.
- **Počet neúspěšných přihlášení před vymazáním zařízení**: zadejte číslo, od 4-11 neúspěšných přihlášení, která se mají připustit, než se zařízení vymaže.

### <a name="power-settings"></a>Nastavení napájení

- **Čas na zamykací obrazovku**: zadejte maximální dobu, kterou může uživatel nastavit, dokud se zařízení nezamkne. Pokud například nastavíte toto nastavení na **10 minut**, můžou uživatelé nastavit čas z 15 sekund až na 10 minut. Pokud je nastavené na **Nenakonfigurováno** (výchozí nastavení), Intune se nezmění ani neřídí toto nastavení.

- **Zapnutá obrazovka, když se zařízení napájí ze sítě**: Zvolte zdroje napájení, při jejichž použití zůstane obrazovka zařízení zapnutá.

### <a name="users-and-accounts-settings"></a>Nastavení uživatelů a účtů

- **Přidat nové uživatele**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v přidávání nových uživatelů. Každý uživatel má osobní pracovní prostor na zařízení pro vlastní domovské obrazovky, účty, aplikace a nastavení. **Nenakonfigurováno** (výchozí) umožňuje uživatelům přidávat do zařízení další uživatele.
- **Odebírání uživatelů**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v odebírání uživatelů. **Nenakonfigurováno** (výchozí) umožňuje uživatelům odebrat ze zařízení další uživatele.
- **Změny účtu** (jenom vyhrazená zařízení): Pokud chcete uživatelům zabránit v úpravách účtů, vyberte **blokovat** . **Nenakonfigurováno** (výchozí) umožňuje uživatelům aktualizovat uživatelské účty v zařízení.

  > [!NOTE]
  > Toto nastavení se nedodržuje u zařízení vlastníka zařízení (plně spravovaná). Pokud toto nastavení nakonfigurujete, nastavení se ignoruje a nemá žádný vliv.

- **Osobní účty Google**: **blok** zabraňuje uživatelům v přidávání osobního účtu Google do zařízení. **Nenakonfigurováno** (výchozí) umožňuje uživatelům přidat svůj osobní účet Google.

### <a name="applications"></a>Aplikací

- **Povolit instalaci z neznámých zdrojů**: vyberte **Povolit** , aby uživatelé mohli zapnout **neznámé zdroje**. Toto nastavení umožňuje aplikacím instalovat z neznámých zdrojů, včetně jiných zdrojů než Obchod Google Play. **Není nakonfigurováno** zabrání uživatelům zapnete **neznámé zdroje**.
- **Povolení přístupu ke všem aplikacím v Google Play Storu**: Pokud je nastavení **povolené**, uživatelé získají přístup ke všem aplikacím v obchodě Google Play Store. Nezískají přístup k aplikacím, které správce zablokuje v [klientských aplikacích](../apps/apps-add-android-for-work.md). **Nenakonfigurováno** přinutí uživatelům přístup pouze k aplikacím, které správce zpřístupňuje Google Play Store nebo aplikace vyžadované v [klientských aplikacích](../apps/apps-add-android-for-work.md).
- **Automatické aktualizace aplikací**: Zvolte, pokud mají automatické aktualizace instalovat. Možnosti:
  - **Není nakonfigurováno**
  - **Výběr uživatele**
  - **Nikdy**
  - **Pouze Wi-Fi**
  - **Vždy**

### <a name="connectivity"></a>Připojení

- **Neustále aktivní připojení VPN**: výběrem možnosti **Povolit** nastavte klienta VPN tak, aby se automaticky připojoval a znovu připojoval k VPN. Neustále aktivní připojení VPN zůstávají ve spojení nebo se ihned připojí, jakmile uživatel zamkne zařízení, zařízení se restartuje nebo se změní bezdrátová síť. 

  Výběrem možnosti **Nenakonfigurováno** zakažte neustále aktivní připojení VPN pro všechny klienty VPN.

  > [!IMPORTANT]
  > Ujistěte se, že na jedno zařízení nasadíte pouze jednu zásadu neustále aktivního připojení VPN. Nasazení více zásad neustále aktivního připojení VPN na jedno zařízení se nepodporuje.

- **Klient VPN**: vyberte klienta VPN, který podporuje neustále aktivní připojení VPN. Možnosti:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Vlastní
    - **ID balíčku**: zadejte ID balíčku aplikace v obchodu Google Play. Pokud je například adresa URL aplikace v obchodu Play `https://play.google.com/store/details?id=com.contosovpn.android.prod`, potom je ID balíčku `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  > - Klient VPN, kterého zvolíte, musí být nainstalovaný na zařízení a musí podporovat VPN pro jednotlivé aplikace v pracovních profilech. V opačném případě dojde k chybě. 
  > - Aplikaci klienta VPN je potřeba schválit ve **spravovaném obchodu Google Play**, synchronizovat ji do Intune a nasadit ji do zařízení. Až to vše uděláte, bude aplikace nainstalovaná v pracovním profilu uživatele.
  > - Může zde být známé problémy při pomocí F5 přístup pro Android 3.0.4 VPN pro jednotlivé aplikace. Zobrazit [F5 zpráva k vydání verze pro F5 přístup pro Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) Další informace.

- **Režim uzamčení**: vyberte **Povolit** , pokud chcete vynutit, aby všechny síťové přenosy používaly tunel VPN. Pokud připojení k VPN není vytvořené, potom nebude mít zařízení přístup k síti.

  Vyberte **Nenakonfigurováno** a povolte, aby provoz používal tunel VPN nebo mobilní síť.

- **Doporučený globální proxy server**: výběrem možnosti **Povolit** přidejte do zařízení globální proxy server. Pokud je povolený přenos přes protokol HTTP a HTTPS, včetně některých aplikací v zařízení, použijte proxy, který zadáte. Tato proxy je jenom doporučení. Je možné, že některé aplikace nepoužívají proxy server. **Nenakonfigurováno** (výchozí) nepřidá doporučený globální proxy server.

  Další informace o této funkci najdete v tématu [setRecommendedGlobalProxy](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setRecommendedGlobalProxy(android.content.ComponentName,%20android.net.ProxyInfo)) (otevře web s Androidem).

  Pokud je povoleno, zadejte také **typ** proxy serveru. Možnosti:

  - **Direct**: tuto možnost vyberte, pokud chcete zadat informace o proxy server ručně, včetně:
    - **Hostitel**: zadejte název hostitele nebo IP adresu vašeho proxy server. Zadejte například `proxy.contoso.com` nebo `127.0.0.1`.
    - **Číslo portu**: zadejte číslo portu TCP používaného proxy server. Zadejte například `8080`.
    - **Vyloučení hostitelé**: Zadejte seznam názvů hostitelů nebo IP adres, které nepoužívají proxy server. Tento seznam může obsahovat zástupný znak hvězdičky (`*`) a několik hostitelů oddělených středníky (`;`) bez mezer. Zadejte například `127.0.0.1;web.contoso.com;*.microsoft.com`.

  - **Automatická konfigurace proxy serveru**: zadejte **adresu URL PAC** do skriptu pro automatickou konfiguraci proxy serveru. Zadejte například `https://proxy.contoso.com/proxy.pac`.

    Další informace o souborech PAC najdete v tématu [soubor automatické konfigurace proxy serveru](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (otevře se na webu, který není Microsoft).

## <a name="work-profile-only"></a>Pouze pracovní profil

Tato nastavení se vztahují na typy registrace Androidu Enterprise, kde Intune řídí jenom pracovní profil, jako je například registrace v systému Android Enterprise Worker na osobním zařízení (BYOD).

### <a name="work-profile-settings"></a>Nastavení pracovního profilu

#### <a name="general"></a>Obecné

- **Kopírování a vkládání mezi pracovními a osobními profily**: Zvolte **bloku** zabránit kopírování a vkládání mezi pracovními a osobními aplikacemi. **Není nakonfigurováno** umožňuje uživatelům sdílet data s aplikacemi v osobním profilu pomocí kopírování a vkládání 
- **Sdílení dat mezi pracovním a osobním profilem**: Zvolte, pokud může aplikace v pracovním profilu sdílení s aplikacemi v osobním profilu. Například můžete řídit akce sdílení v rámci aplikace, jako **sdílenou složku...** v aplikaci prohlížeče Chrome. Toto nastavení se nevztahuje na chování schránky při kopírování/vkládání. Vaše možnosti sdílení:
  - **Výchozí nastavení zařízení**: výchozí chování zařízení při sdílení, které se liší v závislosti na verzi Androidu. Ve výchozím nastavení je povolené sdílení z osobního profilu do pracovního profilu. Ve výchozím nastavení je také blokované sdílení z pracovního profilu do osobního profilu. Toto nastavení zabraňuje sdílení dat z pracovního do osobního profilu. Google neblokuje sdílení z osobního do pracovního profilu na zařízeních, která používají verze 6.0 a novější.
  - **Aplikace v pracovním profilu můžou zpracovat žádost o sdílení z osobního profilu**: povoluje integrovanou funkci Androidu, která umožňuje sdílet data z osobního do pracovního profilu. Pokud je tato možnost povolená, žádost o sdílení z aplikace v osobním profilu může sdílet data s aplikacemi v pracovním profilu. Toto nastavení je výchozí chování zařízení s Androidem, která používají verze starší než 6.0.
  - **Zabránit jakémukoli sdílení přes hranice**: zabraňuje sdílení mezi pracovními a osobními profily.
  - **Žádná omezení sdílení**: umožňuje sdílení přes hranice pracovního profilu v obou směrech. Když vyberete toto nastavení, můžou aplikace v pracovním profilu sdílet data s neoznačenými aplikacemi v osobním profilu. Toto nastavení povoluje spravovaným aplikacím v pracovním profilu sdílení s aplikacemi v nespravované oblasti zařízení. Proto ho používejte opatrně.

- **Oznámení z pracovního profilu když je zařízení zamknuté**: Určuje, jestli aplikace v pracovním profilu můžete zobrazovat data v oznámeních, když je zařízení zamknuté. **Blok** data nezobrazí. **Není nakonfigurováno** zobrazí data.
- **Výchozí oprávnění aplikace**: umožňuje nastavit zásady výchozích oprávnění pro všechny aplikace v pracovním profilu. Od verze Android 6 se uživateli při spuštění aplikace zobrazuje výzva k udělení určitých oprávnění, která aplikace vyžadují. Nastavení této zásady vám umožňuje určit, jestli se uživatelům zobrazí výzva k udělení oprávnění všem aplikacím v pracovním profilu. Můžete například přiřadit do pracovního profilu aplikaci, která vyžaduje přístup k poloze. Taková aplikace obvykle uživatele vyzve, aby přístup k poloze pro aplikaci schválil nebo zamítl. Tyto zásady používejte k automatickému udělování oprávnění bez výzvy, automatickému odepření oprávnění bez výzvy nebo ponechání rozhodnutí na koncovém uživateli. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Zeptat se**
  - **Automaticky udělit**
  - **Automaticky odepřít**

  Zásady konfigurace aplikace můžete použít také k udělení oprávnění pro jednotlivé aplikace (**Klientské aplikace** > **Zásady konfigurace aplikací**).

- **Přidat nebo odebrat účty**: Zvolte **bloku** aby koncoví uživatelé ručně přidávali nebo odebírali účty v pracovním profilu. Když do pracovního profilu Androidu nasadíte například aplikaci Gmail, můžete zabránit tomu, aby koncoví uživatelé přidávali nebo odebírali účty v tomto pracovním profilu. **Není nakonfigurováno** umožňuje přidání účtů v pracovním profilu.  

- **Sdílení kontaktů přes Bluetooth**: Povoluje přístup k pracovním kontaktům z jiného zařízení, například ze zařízení v autě, které je spárováno pomocí Bluetooth. Ve výchozím nastavení toto nastavení není nakonfigurováno a pracovní kontakty se nezobrazují. Vyberte **Povolit** a sdílení povolte, aby se zobrazily kontakty pracovního profilu. Toto nastavení platí pro zařízení s pracovním profilem Android v systému Android OS v6.0 a novějších. Když toto nastavení povolíte, budou určitá zařízení Bluetooth ukládat pracovní kontakty do mezipaměti při prvním připojení. V případě jejího zakázání po počátečním zpárování/synchronizaci se pracovní kontakty ze zařízení Bluetooth nemusí odstranit.

- **Snímek obrazovky**: Zvolte **bloku** k zabránění snímky obrazovky nebo v pracovním profilu zařízení snímky obrazovky. Brání tím také zobrazení obsahu na zobrazovacích zařízeních, která nemají bezpečný výstup videa. **Není nakonfigurováno** umožňuje získat snímky obrazovky.

- **Zobrazit v osobním profilu id pracovního kontaktu volající**: při povolené (**Nenakonfigurováno**), se zobrazují podrobnosti volajícího pracovního kontaktu v osobním profilu. Pokud je nastavena na **bloku**, číslo volajícího pracovního kontaktu v osobním profilu nezobrazuje. Platí pro operační systém Android 6.0 a novější verze.

- **Hledat pracovní kontakty z osobního profilu**: Zvolte **bloku** uživatelům zabránit v hledání pracovní kontakty v aplikacích v osobním profilu. **Není nutné** umožňuje vyhledat pracovní kontakty v osobním profilu.

- **Fotoaparát**: Zvolte **bloku** zabránit přístupu k fotoaparátu v zařízení v pracovním profilu. Nastavení nemá vliv na kameru v osobním profilu. **Není nutné** umožňuje přístup k fotoaparátu/kamery v pracovním profilu.

- **Povolit widgety z pracovních profilů aplikace**: **možnost Povolit** koncovým uživatelům umožní umístit widgety, které jsou vystavené aplikacemi na domovské obrazovce. **Nenakonfigurováno** (výchozí) tuto funkci zakáže.

  Například Outlook se nainstaluje do pracovních profilů uživatelů. Když je tato možnost nastavená na **Povolit**, můžou uživatelé na domovské obrazovce zařízení umístit widget agendy.

#### <a name="work-profile-password"></a>Heslo pracovního profilu

- **Vyžadovat heslo pracovního profilu**: platí pro Android 7.0 a vyšší s aktivovaným pracovním profilem. Zvolte **vyžadují** zadat zásady hesla, která se vztahuje pouze k aplikacím v pracovním profilu. Ve výchozím nastavení může koncový uživatel použít dva samostatně definované PIN kódy, nebo se může rozhodnout zkombinovat PIN kódy do silnějšího z nich. **Není nakonfigurováno** umožňuje uživateli používat pracovní aplikace, bez zadávání hesla.
- **Minimální délka hesla**: zadejte minimální počet znaků, které uživatelské heslo musí obsahovat, **4**-**16**.
- **Maximální doba neaktivity v minutách, než se pracovní profil zamkne**: umožňuje vybrat dobu, po které se pracovní profil zamkne. Potom musí uživatel zadat svoje přihlašovací údaje znovu, když bude chtít získat přístup.
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: zadejte, kolikrát může uživatel zadat nesprávné heslo, než se pracovní profil ze zařízení vymaže.
- **Konec platnosti hesla (dny)** : zadejte počet dnů, po kterém uživatel bude muset změnit heslo (**1**-**255**).
- **Požadovaný typ hesla**: vyberte typ hesla, které musí být na zařízení nastaveno. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Požadováno**
  - **Aspoň číslice**
  - **Číselné komplexní**: opakující se nebo po sobě jdoucí čísla, jako jsou 1111 nebo 1234, nejsou povolena.
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**
- **Znemožnit opakované použití předchozích hesel**: zadejte počet nových hesel, které je třeba použít, než uživatel bude moct znovu použít staré heslo (**1**-**24**).
- **Odemknutí pomocí otisků prstů**: Zvolte **bloku** která zabrání koncovým uživatelům používat skener otisků prstů zařízení k odemknutí zařízení. **Není nakonfigurováno** umožňuje uživatelům k odemknutí zařízení otiskem prstu v pracovním profilu.
- **Smart Lock a jiné agenty pro určování důvěryhodnosti**: Zvolte **bloku** zabránit Smart Lock a jiné agenty pro určování důvěryhodnosti úpravy nastavení zamykací obrazovky na kompatibilních zařízeních. Tato funkce, označovaná také jako agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo zamykací obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění. Je možné například obejít heslo pracovního profilu, když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.

### <a name="device-password"></a>Heslo zařízení

Tato nastavení hesla platí pro osobní profilů na zařízeních používajících pracovní profil.

- **Minimální délka hesla**: zadejte minimální počet znaků, které uživatelské heslo musí obsahovat, **4**-**14**.
- **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**: umožňuje vybrat dobu, po které neaktivní zařízení automaticky zamkne.
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: zadejte, kolikrát může uživatel zadat nesprávné heslo, než se ze zařízení vymažou veškerá data.
- **Konec platnosti hesla (dny)** : zadejte počet dnů, po kterém uživatel bude muset změnit heslo (**1**-**255**).
- **Požadovaný typ hesla**: vyberte typ hesla, které musí být na zařízení nastaveno. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Požadováno**
  - **Aspoň číslice**
  - **Číselné komplexní**: opakující se nebo po sobě jdoucí čísla, jako jsou 1111 nebo 1234, nejsou povolena.
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**
- **Znemožnit opakované použití předchozích hesel**: zadejte počet nových hesel, které je třeba použít, než uživatel bude moct znovu použít staré heslo (**1**-**24**).
- **Odemknutí pomocí otisků prstů**: Zvolte **bloku** aby koncový uživatel používat skener otisků prstů zařízení k odemknutí zařízení. **Není nakonfigurováno** uživatel k odemknutí zařízení otiskem prstu.
- **Smart Lock a jiné agenty pro určování důvěryhodnosti**: Zvolte **bloku** zabránit Smart Lock a jiné agenty pro určování důvěryhodnosti úpravy nastavení zamykací obrazovky na kompatibilních zařízeních. Tato funkce, označovaná také jako agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo zamykací obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění. Je možné například obejít heslo pracovního profilu, když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.

### <a name="system-security"></a>Zabezpečení systému

- **Kontrola ohrožení aplikací**: **vyžadují** , který vynucuje **ověřovat aplikace** nastavení je povoleno pro pracovní a osobní profily.

   > [!Note]
   > Toto nastavení funguje jenom u zařízení s Androidem 8 (Oreo) a novějším.

- **Zabránění instalaci aplikací z neznámých zdrojů v osobním profilu**: podle návrhu zařízení s Androidem Enterprise Work profilování nemůžou instalovat aplikace ze zdrojů, které nejsou obchod Play. Zařízení pracovního profilu mají podle povahy možnost duální profil:

  - Pracovní profil spravovaný pomocí MDM.
  - Osobní profil, který je izolovaný od správy MDM.

  Toto nastavení umožňuje správcům větší kontrolu nad instalací aplikací z neznámých zdrojů. **Nenakonfigurováno** (výchozí) umožňuje instalaci aplikací z neznámých zdrojů v osobním profilu. **Blok** zabraňuje instalaci aplikací z jiných zdrojů než obchod Play v osobním profilu.

### <a name="connectivity"></a>Připojení

- **Neustále aktivní připojení VPN**: výběrem možnosti **Povolit** nastavte klienta VPN tak, aby se automaticky připojoval a znovu připojoval k VPN. Neustále aktivní připojení VPN zůstávají ve spojení nebo se ihned připojí, jakmile uživatel zamkne zařízení, zařízení se restartuje nebo se změní bezdrátová síť. 

  Výběrem možnosti **Nenakonfigurováno** zakažte neustále aktivní připojení VPN pro všechny klienty VPN.

  > [!IMPORTANT]
  > Ujistěte se, že na jedno zařízení nasadíte pouze jednu zásadu neustále aktivního připojení VPN. Nasazení více zásad neustále aktivního připojení VPN na jedno zařízení se nepodporuje.

- **Klient VPN**: vyberte klienta VPN, který podporuje neustále aktivní připojení VPN. Možnosti:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Vlastní
    - **ID balíčku**: zadejte ID balíčku aplikace v obchodu Google Play. Pokud je například adresa URL aplikace v obchodu Play `https://play.google.com/store/details?id=com.contosovpn.android.prod`, potom je ID balíčku `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  > - Klient VPN, kterého zvolíte, musí být nainstalovaný na zařízení a musí podporovat VPN pro jednotlivé aplikace v pracovních profilech. V opačném případě dojde k chybě. 
  > - Aplikaci klienta VPN je potřeba schválit ve **spravovaném obchodu Google Play**, synchronizovat ji do Intune a nasadit ji do zařízení. Až to vše uděláte, bude aplikace nainstalovaná v pracovním profilu uživatele.
  > - Může zde být známé problémy při pomocí F5 přístup pro Android 3.0.4 VPN pro jednotlivé aplikace. Zobrazit [F5 zpráva k vydání verze pro F5 přístup pro Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) Další informace.

- **Režim uzamčení**: vyberte **Povolit** , pokud chcete vynutit, aby všechny síťové přenosy používaly tunel VPN. Pokud připojení k VPN není vytvořené, potom nebude mít zařízení přístup k síti.

  Vyberte **Nenakonfigurováno** a povolte, aby provoz používal tunel VPN nebo mobilní síť.

## <a name="next-steps"></a>Další kroky

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Pro zařízení s [Androidem](device-restrictions-android.md#kiosk) a [Windows 10](kiosk-settings.md) můžete  také vytvořit profily pro celoobrazovkový terminály na vyhrazené zařízení.

## <a name="see-also"></a>Související témata

[Konfigurace a řešení potíží se zařízeními s Androidem Enterprise v Microsoft Intune](https://support.microsoft.com/help/4476974)
