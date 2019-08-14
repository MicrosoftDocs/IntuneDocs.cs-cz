---
title: Nastavení zařízení s androidem Enterprise v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Na Androidu Enterprise nebo zařízení Android for Work omezení nastavení na zařízení, včetně kopírování a vkládání, zobrazit oznámení, oprávnění aplikací, sdílení dat, délky hesla, neúspěšných přihlášení, použijte otisků prstů k odemknutí, opakované použití hesla a povolit bluetooth sdílení pracovních kontaktů. Nakonfigurovat zařízení jako veřejný terminál zařízení, aby spouštěl jednu aplikaci nebo více aplikací.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d4ab90a36254de49eb27e326086ffb137c782005
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "67883432"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>Nastavení zařízení s androidem Enterprise k povolení nebo zakázání funkcí pomocí Intune

Tento článek uvádí a popisuje různá nastavení, které můžete řídit na zařízeních s Androidem Enterprise. Jako součást řešení správy mobilních zařízení (MDM) pomocí těchto nastavení můžete povolit nebo zakázat funkce, spouštět aplikace na vyhrazených zařízeních, zabezpečení řízení a další.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](device-restrictions-configure.md).

## <a name="device-owner-only"></a>Pouze vlastník zařízení

### <a name="general-settings"></a>Obecná nastavení

- **Snímek obrazovky**: Vyberte možnost **blokovat** , pokud chcete zabránit snímku obrazovky nebo snímku obrazovky na zařízení. Brání tím také zobrazení obsahu na zobrazovacích zařízeních, která nemají bezpečný výstup videa. **Není nakonfigurováno** umožňuje uživateli zachytit obsah obrazovky jako obrázek.
- **Kamera**: Vyberte možnost **blokovat** , pokud chcete zabránit přístupu k fotoaparátu na zařízení. **Není nutné** umožňuje přístup k fotoaparátu zařízení.
- **Výchozí zásady oprávnění**: Toto nastavení definuje výchozí zásady oprávnění pro žádosti o oprávnění modulu runtime. Mezi možné hodnoty patří:
  - **Výchozí nastavení zařízení**: Použijte výchozí nastavení zařízení.
  - **Výzva**: Uživateli se zobrazí výzva k schválení oprávnění.
  - **Automaticky udělit**: Oprávnění jsou automaticky udělena.
  - **Automaticky odepřít**: Oprávnění jsou automaticky odepřena.
- **Změny data a času**: Vyberte možnost **blokovat** , pokud chcete uživatelům zabránit v ručním nastavení data a času. **Není nakonfigurováno** umožňuje uživatelům nastavit datum a čas na zařízení.
- **Změny svazku**: Vyberte možnost **blokovat** , aby uživatelé nemohli měnit hlasitost zařízení. **Není nakonfigurováno** umožňuje používat nastavení hlasitosti na zařízení.
- **Obnovení továrního nastavení**: Vyberte možnost **blokovat** , pokud chcete uživatelům zabránit v použití možnosti obnovení továrního nastavení v nastavení zařízení. **Není nakonfigurováno** umožňuje uživatelům použít toto nastavení na zařízení.
- **Bezpečné spuštění**: Vyberte možnost **blokovat** , pokud chcete uživatelům zabránit v restartování zařízení do nouzového režimu. **Není nakonfigurováno** umožňuje restartovat zařízení v nouzovém režimu.
- **Stavový řádek**: Vyberte možnost **blokovat** , pokud chcete zabránit přístupu ke stavovým řádku, včetně oznámení a rychlých nastavení. **Není nakonfigurováno** umožňuje uživatelům přístup k stavový řádek.
- **Roamingové datové služby**: Vyberte možnost **blokovat** , pokud chcete datový roaming zabránit v mobilní síti. **Není nakonfigurováno** povolí datový roaming, když je zařízení v mobilní síti.
- **Změny nastavení sítě Wi-Fi**: Vyberte možnost **blokovat** , pokud chcete uživatelům zabránit ve změně nastavení Wi-Fi vytvořeného vlastníkem zařízení. Uživatelé můžou vytvářet své vlastní konfigurace Wi-Fi. **Není nakonfigurováno** umožňuje uživatelům změnit nastavení Wi-Fi na zařízení.
- **Konfigurace přístupového bodu sítě Wi-Fi**: Vyberte možnost **blokovat** , pokud chcete uživatelům zabránit v vytváření nebo změně jakýchkoli konfigurací Wi-Fi. **Není nakonfigurováno** umožňuje uživatelům změnit nastavení Wi-Fi na zařízení.
- **Konfigurace Bluetooth**: Vyberte možnost **blokovat** , pokud chcete uživatelům zabránit v konfiguraci Bluetooth na zařízení. **Není nakonfigurováno** umožňuje používat Bluetooth na zařízení.
- **Sdílení a přístup k hotspotům**: Vyberte možnost **blokovat** , pokud chcete zabránit sdílení datových míst a přístup k přenosným hotspotům. **Není nakonfigurováno** umožňuje sdílení internetového připojení přes a přístup na přenosné aktivní.
- **Úložiště USB**: Vyberte možnost **povoluje** přístup k úložišti USB na zařízení. **Není nakonfigurováno** brání v přístupu k úložiště USB.
- **Přenos souborů USB**: Vyberte možnost **blokovat** , aby nedošlo k přenosu souborů přes USB. **Není nakonfigurováno** umožňuje přenos souborů.
- **Externí média**: Vyberte možnost **blokovat** , pokud chcete zabránit použití nebo připojení jakýchkoli externích médií na zařízení. **Není nakonfigurováno** povoluje externí médium v zařízení.
- **Data nosníku pomocí NFC**: Vyberte možnost **blokovat** , pokud chcete zabránit použití technologie NFC (Near Field Communication) pro světlou dat z aplikací. **Není nakonfigurováno** umožňuje pomocí NFC ke sdílení dat mezi zařízeními.
- **Funkce ladění**: Chcete-li uživatelům umožnit používání funkcí ladění na zařízení, vyberte možnost **Povolit** . **Není nakonfigurováno** uživatelům bránit v použití funkce ladění na zařízení.
- **Úpravy mikrofonu**: Vyberte možnost **blokovat** , pokud chcete uživatelům zabránit ve zrušení ztlumení mikrofonu a nastavení hlasitosti mikrofonu. **Není nakonfigurováno** umožňuje uživateli používat a hlasitosti mikrofonu v zařízení.
- **E-maily ochrany při obnovení továrního nastavení**: Vyberte **e-mailové adresy účtu Google**. Zadejte e-mailové adresy správců zařízení, které můžete odemknout zařízení, poté, co se vymaže. Ujistěte se, zda jste e-mailové adresy oddělujte středníkem, třeba `admin1@gmail.com;admin2@gmail.com`. Pokud není zadán e-mailu, kdokoli odemknutí zařízení po obnovení do továrního nastavení. Tyto e-maily se použijí jenom v případě, že se spustilo obnovení uživatelem bez uživatele, jako je třeba spuštění obnovení továrního nastavení pomocí nabídky obnovení.
- **Řídicí**znak v síti: Vyberte možnost **Povolit** , pokud chcete uživatelům povolit, aby zapnuli funkci řídicího panelu sítě. Pokud připojení k síti není proveden, jakmile se spustí zařízení, únikový poklop vyzve k dočasnému připojení k síti a aktualizovat zásady zařízení. Po uplatnění zásad se tato dočasná síť zapomene a zařízení pokračuje ve spouštění. Pokud tuto funkci připojení zařízení k síti:
  - V posledních zásadách není vhodné síťové.
  - Zařízení se spustí do aplikace v režimu uzamčení úloh.
  - Uživatel se nám kontaktovat nastavení zařízení.

  **Není nakonfigurováno** zabraňuje uživatelům v zapnutí funkce šrafování řídicí sítě na zařízení.

- **Aktualizace systému**: Vyberte možnost pro definování způsobu, jakým zařízení zpracovává aktualizace v ovzduší:
  - **Výchozí nastavení zařízení**: Použijte výchozí nastavení zařízení.
  - **Automaticky**: Aktualizace se automaticky instalují bez zásahu uživatele. Po nastavení této zásady se hned nainstalují všechny čekající aktualizace.
  - **Odloženo**: Aktualizace se odloží po dobu 30 dnů. Na konci na 30 dnů Android se zobrazí výzva k instalaci aktualizace. Výrobci zařízení nebo mobilní operátoři mohou zakázat (vyloučit) odklad důležitých aktualizací zabezpečení. Vynechaná aktualizace zobrazí uživateli zařízení zprávu systému. 
  - Časové **období údržby**: Nainstaluje aktualizace automaticky během každodenního časového období údržby, které jste nastavili v Intune. Instalace pokusí denně po dobu 30 dnů a může selhat, pokud je nedostatek místa či baterie úrovněmi. Po 30 dnech Android se zobrazí výzva k instalaci. Toto okno se také používá k instalaci aktualizací aplikací Play. Tuto možnost použijte pro vyhrazená zařízení, jako jsou veřejné terminály, protože je možné aktualizovat aplikace v popředí vyhrazené pro jednotlivé aplikace.

- **Okna oznámení**: Když je nastavení **zakázané**, oznámení v oknech, včetně informačních zpráv, příchozích volání, odchozích volání, systémových výstrah a systémových chyb, se v zařízení nezobrazují. Pokud je nastavené na Nenakonfigurováno, použije se výchozí operační systém, který může zobrazovat oznámení.
- **Přeskočit první tipy k použití**: Zvolením možnosti **Povolit** skryjete nebo přeskočíte návrhy aplikací a Projděte si kurzy, případně si přečtete všechny úvodní pokyny při spuštění aplikace. Pokud je nastavené na Nenakonfigurováno, použije se výchozí operační systém, což může ukázat tyto návrhy při spuštění aplikace.

### <a name="system-security-settings"></a>Systémové nastavení zabezpečení

- **Kontrola hrozeb v aplikacích**: **Vyžadovat** (výchozí) umožňuje Google Play chránit před instalací aplikace a po jejich instalaci. Pokud zjistí hrozbu, může uživateli upozornit na odebrání aplikace ze zařízení. **Není nakonfigurováno** , nepovolí ani nespustí Google Play chránit pro kontrolu aplikací.

### <a name="dedicated-device-settings"></a>Nastavení vyhrazeného zařízení

Pomocí těchto nastavení můžete nakonfigurovat možnosti veřejného terminálu na vyhrazených zařízeních. Můžete nakonfigurovat zařízení tak, aby spouštělo jednu aplikaci nebo spustilo spoustu aplikací. Když je zařízení nastavené s beznabídkovým režimem, k dispozici jsou jenom aplikace, které přidáte. Tato nastavení platí pro zařízení s Androidem Enterprise vyhrazená. Nevztahují se na zařízení s plně spravovaným systémem Android Enterprise.

**Celoobrazovkový režim**: Vyberte, jestli zařízení spouští jednu aplikaci, nebo spustí víc aplikací.

- **Jedna aplikace**: Uživatelé mají přístup jenom k jedné aplikaci na zařízení. Při spuštění zařízení spustí jenom konkrétní aplikace. Uživatelé nemůžou otevírat nové aplikace ani měnit spuštěnou aplikaci.

  **Kroky**
  1. Zvolte **Vyberte spravovanou aplikaci**a vyberte ze seznamu spravovaných aplikací Google Play. 

      Pokud nemáte žádné aplikace, pak uvedené [přidat některé aplikace pro Android](apps-add-android-for-work.md) do zařízení. Nezapomeňte [aplikaci přiřadit ke skupině zařízení vytvořené pro vaše vyhrazená zařízení](apps-deploy.md).

  2. Zvolte **OK** > **OK** a přidejte tak aplikaci.

- **Více aplikací**: Uživatelé mají přístup k omezené sadě aplikací na zařízení. Při spuštění zařízení, spustit pouze aplikace, které přidáte. Můžete také přidat některé webové odkazy, které uživatelé můžou otevírat. Když se zásady vztahují, uživatelé uvidí ikony pro povolené aplikace na domovské obrazovce.

  > [!IMPORTANT]
  > U vyhrazených zařízení s více aplikacemi **musí být** [aplikace spravované domovské obrazovky](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) z Google Play:
  >   - [Přidat jako klientskou aplikaci](apps-add-android-for-work.md) v Intune
  >   - [Přiřazeno ke skupině zařízení](apps-deploy.md) vytvořené pro vyhrazená zařízení
  > 
  > **Spravované domovskou obrazovku** aplikace nemusí být v profilu konfigurace, ale je potřeba přidat jako klientská aplikace. Když se **spravovaná** aplikace pro domovskou obrazovku přidá jako klientská aplikace, všechny ostatní aplikace, které přidáte do konfiguračního profilu, se zobrazí jako ikony v aplikaci **spravované domovské obrazovky** . 
  >
  > Pokud používáte celoobrazovkový režim s více aplikacemi se spravovanou domovskou obrazovkou, nemusí aplikace pro telefonování a telefon fungovat správně. 

  - Zvolte **přidat**a vyberte ze seznamu aplikací.

    Pokud **spravované domovskou obrazovku** aplikace není uvedená, pak [přidat na webu Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Nezapomeňte [aplikaci přiřadit](apps-deploy.md) ke skupině zařízení vytvořené pro vaše vyhrazená zařízení.

    Můžete také přidat další [aplikace pro Android](apps-add-android-for-work.md) a [webové aplikace](web-app.md) vytvořená vaší organizací na zařízení. Nezapomeňte [aplikaci přiřadit ke skupině zařízení vytvořené pro vaše vyhrazená zařízení](apps-deploy.md).

  - **Tlačítko virtuální domů**: Výběrem možnosti **Povolit** zobrazíte na vyhrazeném zařízení tlačítko domů. Při výběru, vrátí uživatele na domovské obrazovce zařízení, uživatelé mohou snadno přepínat mezi aplikacemi. Na některých zařízeních s Androidem můžou uživatelé muset potažením prstem přejděte na obrazovce zobrazit tlačítko Domů. **Zakázat** nezobrazí tlačítko Domů, takže uživatelé musí použijte tlačítko Zpět. Chcete-li přepnout mezi aplikacemi.
  - **Opustit celoobrazovkový režim**: Zvolením možnosti **Povolit** správcům umožníte dočasně pozastavit celoobrazovkový režim a aktualizovat zařízení. Chcete-li použít tuto funkci, správce: 
  
    1. Pokračuje v výběru tlačítka zpět, dokud se nezobrazí tlačítko Ukončit celoobrazovkový. 
    2. Vybere tlačítko a přejde do **režimu opuštění kódu PIN pro celoobrazovkový režim** .
    3. Po dokončení změn, vyberte **spravované domovskou obrazovku** aplikace. Tento krok relocks zařízení do režimu veřejného terminálu s více aplikacemi. 

    **Zakázat** nedává možnost pozastavit beznabídkový režim. Pokud správce pokračuje v výběru tlačítka zpět a vybere tlačítko Ukončit veřejný terminál, zobrazí se zpráva, že je vyžadováno heslo.

    - **Ponechat kód celoobrazovkového režimu**: Zadejte číslici PIN s číslem 4-6. Správce používá tento PIN kód se dočasně pozastavit beznabídkový režim.

  - **Nastavit vlastní pozadí adresy URL**: Zadejte adresu URL pro přizpůsobení obrazovky na pozadí na vyhrazeném zařízení.
    
    > [!NOTE]
    > Ve většině případů doporučujeme začít s imagemi alespoň následujících velikostí:
    >
    > - Hovor 1080x1920 px
    > - Tlačítk 1080 px
    >    
    > Pro dosažení co nejlepších výsledků a zaostření podrobností je navrženo, že se pro jednotlivé položky obrázku zařízení vytvořily specifikace zobrazení.
    >
    > Moderní displeje mají vyšší hustotu pixelů a můžou zobrazovat ekvivalentní image definice 2K/4K.
  - **Konfigurace Wi-Fi**: Vyberte **Povolit** , pokud chcete koncovým uživatelům povolit připojení zařízení k různým sítím Wi-Fi. Povolením této funkce se taky zapne umístění zařízení. **Není nakonfigurováno** (výchozí) zabraňuje uživatelům v připojení k sítím Wi-Fi na spravované domovské obrazovce (režim uzamčení úlohy).

    Další informace o [režimu uzamčení úloh](https://developer.android.com/work/dpc/dedicated-devices/lock-task-mode) (Otevírá web Androidu).

  - **Konfigurace Bluetooth**: Výběrem možnosti **Povolit** povolte Bluetooth na zařízení a koncovým uživatelům povolte párování zařízení přes Bluetooth. Povolením této funkce se taky zapne umístění zařízení. **Není nakonfigurováno** (výchozí) zabraňuje uživatelům v konfiguraci zařízení Bluetooth a párování zařízení, když se nachází na spravované domovské obrazovce (režim uzamčení úlohy). 

    Další informace o [režimu uzamčení úloh](https://developer.android.com/work/dpc/dedicated-devices/lock-task-mode) (Otevírá web Androidu).

### <a name="device-password-settings"></a>Nastavení hesla zařízení

- **Zakázat zamykací obrazovku**: Pokud chcete uživatelům zabránit v používání funkce zamykací obrazovky na zařízení, vyberte **Zakázat** . **Není nakonfigurováno** umožňuje uživateli používat Keyguard funkce.
- **Zakázané funkce zamykací obrazovky**: Když je na zařízení povolená funkce ochrany kláves, vyberte, které funkce se mají zakázat. Pokud je například zaškrtnuto políčko **Zabezpečená kamera** , funkce kamery je na zařízení zakázaná. Na zařízení jsou povolené všechny funkce, které nejsou zaškrtnuté.

  Tyto funkce jsou uživatelům k dispozici, když je zařízení zamčené. Uživatelům se nezobrazí nebo nebudou mít přístup k vybraným funkcím.

- **Požadovaný typ hesla**: Zadejte typ hesla, které se pro zařízení vyžaduje. Možnosti:
  - **Výchozí ze zařízení**
  - **Vyžaduje se heslo, žádná omezení.**
  - **Slabý**biometrika: [Silný vs. slabý biometrika](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (otevře se web Androidu)
  - **Číselná**: Heslo musí obsahovat jenom čísla, `123456789`třeba. Zadejte **minimální délku hesla** , kterou musí uživatel zadat, a to v rozmezí 4 až 16 znaků.
  - **Číselná složitá**: Opakující se nebo po sobě jdoucí čísla, například "1111" nebo "1234", nejsou povolena. Zadejte **minimální délku hesla** , kterou musí uživatel zadat, a to v rozmezí 4 až 16 znaků.
  - **Abecední**: Jsou požadována písmena v abecedě. Čísla a symboly nejsou požadovány. Zadejte **minimální délku hesla** , kterou musí uživatel zadat, a to v rozmezí 4 až 16 znaků.
  - **Alfanumerické znaky**: Obsahuje velká písmena, malá písmena a číselné znaky. Zadejte **minimální délku hesla** , kterou musí uživatel zadat, a to v rozmezí 4 až 16 znaků.
  - **Alfanumerické znaky se symboly**: Obsahuje velká písmena, malá písmena, číselné znaky, interpunkční znaménka a symboly. Dále zadejte:

    - **Minimální délka hesla**: Zadejte minimální délku hesla, které musí mít 4 až 16 znaků.
    - **Požadovaný počet znaků**: Zadejte počet znaků, které musí heslo obsahovat, a to v rozmezí 0 až 16 znaků.
    - **Počet požadovaných malých písmen**: Zadejte počet malých písmen, které musí heslo obsahovat, a to v rozmezí 0 až 16 znaků.
    - **Počet požadovaných velkých znaků**: Zadejte počet velkých písmen, které musí heslo obsahovat, a to v rozmezí 0 až 16 znaků.
    - **Počet požadovaných znaků bez písmen**: Zadejte počet nepísmenových znaků (cokoli kromě písmen v abecedě), které musí heslo obsahovat, a to v rozmezí 0 až 16 znaků.
    - **Požadovaný počet číselných znaků**: Zadejte počet číselných znaků (`1`, `2`, `3`atd.), které musí heslo obsahovat, a to v rozmezí 0 až 16 znaků.
    - **Požadovaný počet znaků symbolu**: Zadejte počet znaků symbolu (`&` `%`, `#`, atd.), které musí heslo obsahovat, a to v rozmezí 0 až 16 znaků.

- **Počet dní do vypršení platnosti hesla**: Zadejte počet dnů od 1-365, po jehož uplynutí se musí změnit heslo zařízení. Pokud například chcete změnit heslo po 60 dnech, zadejte `60`. Po vypršení platnosti hesla se uživatelům zobrazí výzva k vytvoření nového hesla.
- **Počet hesel vyžadovaných před tím, než uživatel může resuse heslo**: Zadejte počet nedávných hesel, která se nedají znovu použít, mezi 1-24. Toto nastavení použijte, pokud chcete uživateli zabránit ve vytváření hesel, která používal dříve.
- **Počet neúspěšných přihlášení před vymazáním zařízení**: Zadejte číslo, mezi 4-11 neúspěšnými přihlášeními, která se mají připustit, než se zařízení vymaže.

### <a name="power-settings"></a>Nastavení napájení

- **Doba, po kterou se má zamknout obrazovka**: Nastavte požadovanou dobu nečinnosti, než se zařízení zamkne.
- **Obrazovka při napájení zařízení**: Vyberte, které zdroje napájení způsobí, že obrazovka zařízení bude při napájení zapnutá.

### <a name="users-and-accounts-settings"></a>Nastavení uživatelů a účtů

- **Přidat nové uživatele**: Vyberte možnost **blokovat** , pokud chcete uživatelům zabránit v přidávání nových uživatelů. Každý uživatel má osobní pracovní prostor na zařízení pro vlastní domovské obrazovky, účty, aplikace a nastavení. **Není nakonfigurováno** umožňuje uživatelům přidávat ostatním uživatelům na zařízení.
- **Odebrání uživatele**: Vyberte možnost **blokovat** , pokud chcete uživatelům zabránit v odebírání uživatelů. **Není nakonfigurováno** umožňuje uživatelům odebírat další uživatele ze zařízení.
- **Změny účtu**: Vyberte možnost **blokovat** , pokud chcete uživatelům zabránit v úpravách účtů. **Není nakonfigurováno** umožňuje uživatelům aktualizovat uživatelských účtů v zařízení.

### <a name="applications"></a>Aplikace

- **Povolte instalaci z neznámých zdrojů**: Vyberte **Povolit** , aby uživatelé mohli zapnout **neznámé zdroje**. Toto nastavení umožňuje aplikacím instalovat z neznámých zdrojů, včetně jiných zdrojů než Obchod Google Play. **Není nakonfigurováno** zabrání uživatelům zapnete **neznámé zdroje**.
- **Povolí přístup ke všem aplikacím v Google Play Storu**: Když je nastavení **povoleno**, uživatelé získají přístup ke všem aplikacím v Google Play Storu. Nezískají přístup k aplikacím, které správce zablokuje v [klientských aplikacích](apps-add-android-for-work.md). Nenakonfigurováno přinutí uživatelům přístup pouze k aplikacím, které správce zpřístupňuje Google Play Store nebo aplikace vyžadované v [klientských aplikacích](apps-add-android-for-work.md).
- **Automatické aktualizace aplikací**: Vyberte, kdy se mají nainstalovat automatické aktualizace. Možnosti:
  - **Není nakonfigurováno**
  - **Výběr uživatele**
  - **Nikdy**
  - **Pouze Wi-Fi**
  - **Vždy**

### <a name="connectivity"></a>Připojení

- **Vždycky zapnutá síť VPN**: Zvolením možnosti **Povolit** nanastavíte klienta VPN tak, aby se automaticky připojoval a znovu připojil k síti VPN. Neustále aktivní připojení VPN zůstávají ve spojení nebo se ihned připojí, jakmile uživatel zamkne zařízení, zařízení se restartuje nebo se změní bezdrátová síť. 

  Výběrem možnosti **Nenakonfigurováno** zakažte neustále aktivní připojení VPN pro všechny klienty VPN.

  > [!IMPORTANT]
  > Ujistěte se, že na jedno zařízení nasadíte pouze jednu zásadu neustále aktivního připojení VPN. Nasazení více zásad neustále aktivního připojení VPN na jedno zařízení se nepodporuje.

- **Klient VPN**: Vyberte klienta VPN, který podporuje Always On. Možnosti:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Vlastní
    - **ID balíčku**: Zadejte ID balíčku aplikace v Google Play Storu. Pokud je například adresa URL aplikace v obchodu Play `https://play.google.com/store/details?id=com.contosovpn.android.prod`, potom je ID balíčku `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  > - Klient VPN, kterého zvolíte, musí být nainstalovaný na zařízení a musí podporovat VPN pro jednotlivé aplikace v pracovních profilech. V opačném případě dojde k chybě. 
  > - Aplikaci klienta VPN je potřeba schválit ve **spravovaném obchodu Google Play**, synchronizovat ji do Intune a nasadit ji do zařízení. Až to vše uděláte, bude aplikace nainstalovaná v pracovním profilu uživatele.
  > - Může zde být známé problémy při pomocí F5 přístup pro Android 3.0.4 VPN pro jednotlivé aplikace. Zobrazit [F5 zpráva k vydání verze pro F5 přístup pro Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) Další informace.

- **Režim uzamčení**: Zvolením možnosti **Povolit** vynutíte, aby veškerý síťový provoz používal tunel VPN. Pokud připojení k VPN není vytvořené, potom nebude mít zařízení přístup k síti.

  Vyberte **Nenakonfigurováno** a povolte, aby provoz používal tunel VPN nebo mobilní síť.

## <a name="work-profile-only"></a>Pouze pracovní profil 

### <a name="work-profile-settings"></a>Nastavení pracovního profilu

#### <a name="general"></a>Obecné

- **Kopírování a vkládání mezi pracovními a osobními profily**: Vyberte možnost **blokovat** , pokud chcete zabránit kopírování a vkládání mezi pracovními a osobními aplikacemi. **Není nakonfigurováno** umožňuje uživatelům sdílet data s aplikacemi v osobním profilu pomocí kopírování a vkládání 
- **Sdílení dat mezi pracovními a osobními profily**: Vyberte, jestli aplikace v pracovním profilu můžou sdílet s aplikacemi v osobním profilu. Například můžete řídit akce sdílení v rámci aplikace, jako **sdílenou složku...** v aplikaci prohlížeče Chrome. Toto nastavení se nevztahuje na chování schránky při kopírování/vkládání. Vaše možnosti sdílení:
  - **Výchozí omezení sdílení**: Výchozí chování zařízení při sdílení, které se liší v závislosti na verzi Androidu. Ve výchozím nastavení je povolené sdílení z osobního profilu do pracovního profilu. Ve výchozím nastavení je také blokované sdílení z pracovního profilu do osobního profilu. Toto nastavení zabraňuje sdílení dat z pracovního do osobního profilu. Google neblokuje sdílení z osobního do pracovního profilu na zařízeních, která používají verze 6.0 a novější.
  - **Aplikace v pracovním profilu můžou zpracovat žádost o sdílení z osobního profilu**: Povolí integrovanou funkci Androidu, která umožňuje sdílení z osobního do pracovního profilu. Pokud je tato možnost povolená, žádost o sdílení z aplikace v osobním profilu může sdílet data s aplikacemi v pracovním profilu. Toto nastavení je výchozí chování zařízení s Androidem, která používají verze starší než 6.0.
  - **Povolí sdílení přes hranice**: Umožňuje sdílení přes hranice pracovního profilu v obou směrech. Když vyberete toto nastavení, můžou aplikace v pracovním profilu sdílet data s neoznačenými aplikacemi v osobním profilu. Toto nastavení povoluje spravovaným aplikacím v pracovním profilu sdílení s aplikacemi v nespravované oblasti zařízení. Proto ho používejte opatrně.

- **Oznámení z pracovního profilu, když je zařízení uzamčené**: Určuje, jestli aplikace v pracovním profilu můžou zobrazovat data v oznámeních, když je zařízení zamčené. **Blok** data nezobrazí. **Není nakonfigurováno** zobrazí data.
- **Výchozí oprávnění aplikace**: Umožňuje nastavit zásady výchozích oprávnění pro všechny aplikace v pracovním profilu. Od verze Android 6 se uživateli při spuštění aplikace zobrazuje výzva k udělení určitých oprávnění, která aplikace vyžadují. Nastavení této zásady vám umožňuje určit, jestli se uživatelům zobrazí výzva k udělení oprávnění všem aplikacím v pracovním profilu. Můžete například přiřadit do pracovního profilu aplikaci, která vyžaduje přístup k poloze. Taková aplikace obvykle uživatele vyzve, aby přístup k poloze pro aplikaci schválil nebo zamítl. Tyto zásady používejte k automatickému udělování oprávnění bez výzvy, automatickému odepření oprávnění bez výzvy nebo ponechání rozhodnutí na koncovém uživateli. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Zeptat se**
  - **Automaticky udělit**
  - **Automaticky odepřít**

  Zásady konfigurace aplikace můžete použít také k udělení oprávnění pro jednotlivé aplikace (**Klientské aplikace** > **Zásady konfigurace aplikací**).

- **Přidat a odebrat účty**: Vyberte možnost **blokovat** , pokud chcete koncovým uživatelům zabránit v ručním přidávání a odebírání účtů v pracovním profilu. Když do pracovního profilu Androidu nasadíte například aplikaci Gmail, můžete zabránit tomu, aby koncoví uživatelé přidávali nebo odebírali účty v tomto pracovním profilu. **Není nakonfigurováno** umožňuje přidání účtů v pracovním profilu.  

- **Sdílení kontaktů přes Bluetooth**: Umožňuje přístup k pracovním kontaktům z jiného zařízení, jako je třeba automobil, který se spáruje pomocí Bluetooth. Ve výchozím nastavení toto nastavení není nakonfigurováno a pracovní kontakty se nezobrazují. Vyberte **Povolit** a sdílení povolte, aby se zobrazily kontakty pracovního profilu. Toto nastavení platí pro zařízení s pracovním profilem Android v systému Android OS v6.0 a novějších. Když toto nastavení povolíte, budou určitá zařízení Bluetooth ukládat pracovní kontakty do mezipaměti při prvním připojení. V případě jejího zakázání po počátečním zpárování/synchronizaci se pracovní kontakty ze zařízení Bluetooth nemusí odstranit.

- **Snímek obrazovky**: Vyberte možnost **blokovat** , pokud chcete, aby se snímky obrazovky nebo obrazovka na zařízení v pracovním profilu nemohly zachytit. Brání tím také zobrazení obsahu na zobrazovacích zařízeních, která nemají bezpečný výstup videa. **Není nakonfigurováno** umožňuje získat snímky obrazovky.

- **Zobrazit v osobním profilu ID volajícího pracovního kontaktu**: Pokud je povoleno(Nenakonfigurováno), zobrazí se v osobním profilu podrobnosti o volajícím pracovního kontaktu. Pokud je nastavena na **bloku**, číslo volajícího pracovního kontaktu v osobním profilu nezobrazuje. Platí pro operační systém Android 6.0 a novější verze.

- **Hledat pracovní kontakty z osobního profilu**: Vyberte možnost **blokovat** , pokud chcete uživatelům zabránit v hledání pracovních kontaktů v aplikacích v osobním profilu. **Není nutné** umožňuje vyhledat pracovní kontakty v osobním profilu.

- **Kamera**: Vyberte možnost **blokovat** , pokud chcete zabránit přístupu k fotoaparátu na zařízení v pracovním profilu. Nastavení nemá vliv na kameru v osobním profilu. **Není nutné** umožňuje přístup k fotoaparátu/kamery v pracovním profilu.

#### <a name="work-profile-password"></a>Heslo pracovního profilu

- **Vyžadovat heslo pracovního profilu**: Platí pro Android 7,0 a novější s povoleným pracovním profilem. Zvolte **vyžadují** zadat zásady hesla, která se vztahuje pouze k aplikacím v pracovním profilu. Ve výchozím nastavení může koncový uživatel použít dva samostatně definované PIN kódy, nebo se může rozhodnout zkombinovat PIN kódy do silnějšího z nich. **Není nakonfigurováno** umožňuje uživateli používat pracovní aplikace, bez zadávání hesla.
- **Minimální délka hesla**: Zadejte minimální počet znaků, které musí heslo uživatele mít, od **4**-**16**.
- **Maximální počet minut nečinnosti, po kterém se pracovní profil zamkne**: Vyberte dobu, po jejímž uplynutí se pracovní profil zamkne. Potom musí uživatel zadat svoje přihlašovací údaje znovu, když bude chtít získat přístup.
- **Počet neúspěšných přihlášení před vymazáním zařízení**: Zadejte, kolikrát může být zadání nesprávného hesla před vymazáním pracovního profilu ze zařízení.
- **Vypršení platnosti hesla (dny)** : Zadejte počet dní, než bude nutné změnit heslo koncového uživatele (z **1**-**255**).
- **Požadovaný typ hesla**: Vyberte typ hesla, které musí být nastavené na zařízení. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Požadováno**
  - **Aspoň číslice**
  - **Číselná složitá**: Opakující se nebo po sobě jdoucí čísla, jako je například "1111" nebo "1234", nejsou povolena.
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**
- **Zakázat opakované použití předchozích hesel**: Zadejte počet nových hesel, která se musí použít, aby bylo možné znovu použít staré heslo ( **1**-**24**).
- **Odemknutí otiskem prstu**: Vyberte možnost **blokovat** , pokud chcete, aby koncoví uživatelé nepoužívali skener otisků prstů zařízení k odemknutí zařízení. **Není nakonfigurováno** umožňuje uživatelům k odemknutí zařízení otiskem prstu v pracovním profilu.
- **Smart Lock a jiní agenti**pro určování důvěryhodnosti: Vyberte možnost **blokovat** , pokud chcete Smart Lock nebo jiným agentům pro určování důvěryhodnosti zabránit v úpravách nastavení zamykací obrazovky na kompatibilních zařízeních. Tuto funkci, někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo uzamčené obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění. Je možné například obejít heslo pracovního profilu, když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.

### <a name="device-password"></a>Heslo zařízení

Tato nastavení hesla platí pro osobní profilů na zařízeních používajících pracovní profil.

- **Minimální délka hesla**: Zadejte minimální počet znaků, které musí heslo uživatele mít, od **4**-do**14**.
- **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**: Vyberte dobu, po jejímž uplynutí se neaktivní zařízení automaticky zamkne.
- **Počet neúspěšných přihlášení před vymazáním zařízení**: Zadejte, kolikrát může být zadáno nesprávné heslo, než budou ze zařízení vymazána všechna data.
- **Vypršení platnosti hesla (dny)** : Zadejte počet dní, po kterém se musí změnit heslo koncového uživatele (od **1**-**255**).
- **Požadovaný typ hesla**: Vyberte typ hesla, které musí být nastavené na zařízení. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Požadováno**
  - **Aspoň číslice**
  - **Číselná složitá**: Opakující se nebo po sobě jdoucí čísla jako ' 1111 ' nebo ' 1234 ' nejsou povolena.
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**
- **Zakázat opakované použití předchozích hesel**: Zadejte počet nových hesel, která se musí použít, aby bylo možné znovu použít staré heslo ( **1**-**24**).
- **Odemknutí otiskem prstu**: Vyberte možnost **blokovat** , pokud chcete, aby koncový uživatel nepoužíval skener otisků prstů zařízení k odemknutí zařízení. **Není nakonfigurováno** uživatel k odemknutí zařízení otiskem prstu.
- **Smart Lock a jiní agenti**pro určování důvěryhodnosti: Vyberte možnost **blokovat** , pokud chcete Smart Lock nebo jiným agentům pro určování důvěryhodnosti zabránit v úpravách nastavení zamykací obrazovky na kompatibilních zařízeních. Tuto funkci, někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo uzamčené obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění. Je možné například obejít heslo pracovního profilu, když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.

### <a name="system-security"></a>Zabezpečení systému

- **Kontrola hrozeb v aplikacích**: **Vyžadovat** , aby se vynutilo, že nastavení **ověřit aplikace** je povolené pro pracovní a osobní profily.

   > [!Note]
   > Toto nastavení funguje jenom u zařízení s Androidem O a vyšším.

### <a name="connectivity"></a>Připojení

- **Vždycky zapnutá síť VPN**: Zvolením možnosti **Povolit** nanastavíte klienta VPN tak, aby se automaticky připojoval a znovu připojil k síti VPN. Neustále aktivní připojení VPN zůstávají ve spojení nebo se ihned připojí, jakmile uživatel zamkne zařízení, zařízení se restartuje nebo se změní bezdrátová síť. 

  Výběrem možnosti **Nenakonfigurováno** zakažte neustále aktivní připojení VPN pro všechny klienty VPN.

  > [!IMPORTANT]
  > Ujistěte se, že na jedno zařízení nasadíte pouze jednu zásadu neustále aktivního připojení VPN. Nasazení více zásad neustále aktivního připojení VPN na jedno zařízení se nepodporuje.

- **Klient VPN**: Vyberte klienta VPN, který podporuje Always On. Možnosti:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Vlastní
    - **ID balíčku**: Zadejte ID balíčku aplikace v Google Play Storu. Pokud je například adresa URL aplikace v obchodu Play `https://play.google.com/store/details?id=com.contosovpn.android.prod`, potom je ID balíčku `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  > - Klient VPN, kterého zvolíte, musí být nainstalovaný na zařízení a musí podporovat VPN pro jednotlivé aplikace v pracovních profilech. V opačném případě dojde k chybě. 
  > - Aplikaci klienta VPN je potřeba schválit ve **spravovaném obchodu Google Play**, synchronizovat ji do Intune a nasadit ji do zařízení. Až to vše uděláte, bude aplikace nainstalovaná v pracovním profilu uživatele.
  > - Může zde být známé problémy při pomocí F5 přístup pro Android 3.0.4 VPN pro jednotlivé aplikace. Zobrazit [F5 zpráva k vydání verze pro F5 přístup pro Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) Další informace.

- **Režim uzamčení**: Zvolením možnosti **Povolit** vynutíte, aby veškerý síťový provoz používal tunel VPN. Pokud připojení k VPN není vytvořené, potom nebude mít zařízení přístup k síti.

  Vyberte **Nenakonfigurováno** a povolte, aby provoz používal tunel VPN nebo mobilní síť.

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Pro zařízení s [Androidem](device-restrictions-android.md#kiosk) a [Windows 10](kiosk-settings.md) můžete  také vytvořit profily pro celoobrazovkový terminály na vyhrazené zařízení.

## <a name="see-also"></a>Viz také:

[Konfigurace a řešení potíží se zařízeními s Androidem Enterprise v Microsoft Intune](https://support.microsoft.com/help/4476974)
