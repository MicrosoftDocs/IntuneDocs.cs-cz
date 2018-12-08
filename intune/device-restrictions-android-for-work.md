---
title: Nastavení zařízení s androidem Enterprise v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Na Androidu Enterprise nebo zařízení Android for Work omezení nastavení na zařízení, včetně kopírování a vkládání, zobrazit oznámení, oprávnění aplikací, sdílení dat, délky hesla, neúspěšných přihlášení, použijte otisků prstů k odemknutí, opakované použití hesla a povolit bluetooth sdílení pracovních kontaktů. Konfigurace zařízení jako veřejný terminál pro spuštění aplikace jeden nebo více aplikací.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.openlocfilehash: c9e2e0df79625329310171c509327395989f3a7c
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/07/2018
ms.locfileid: "53032533"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>Nastavení zařízení s androidem Enterprise k povolení nebo zakázání funkcí pomocí Intune

Tento článek uvádí a popisuje různá nastavení, které můžete řídit na zařízeních s Androidem Enterprise. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete povolit nebo zakázat funkce, spuštění aplikace v režimu veřejného terminálu, ovládací prvek zabezpečení a další.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](device-restrictions-configure.md).

## <a name="device-owner-only"></a>Pouze vlastník zařízení

### <a name="general-settings"></a>Obecná nastavení

- **Snímek obrazovky**: Zvolte **bloku** k zabránění snímky obrazovky nebo na zařízení snímky obrazovky. Brání tím také zobrazení obsahu na zobrazovacích zařízeních, která nemají bezpečný výstup videa. **Není nakonfigurováno** umožňuje uživateli zachytit obsah obrazovky jako obrázek.
- **Fotoaparát**: Zvolte **bloku** zabránit přístupu k fotoaparátu v zařízení. **Není nutné** umožňuje přístup k fotoaparátu zařízení.
- **Výchozí zásady oprávnění**: Toto nastavení definuje výchozí zásady oprávnění pro žádosti o oprávnění za běhu. Mezi možné hodnoty patří:
  - **Výchozí ze zařízení**: Použije se výchozí nastavení zařízení.
  - **Zeptat se**: Uživateli se zobrazí výzva ke schválení oprávnění.
  - **Automaticky udělit**: Oprávnění jsou udělena automaticky.
  - **Automaticky odepřít**: Oprávnění jsou odepřena automaticky.
- **Datum a čas změny**: Zvolte **bloku** ručně nastavovat datum a čas, moct uživatelé. **Není nakonfigurováno** umožňuje uživatelům nastavit datum a čas na zařízení.
- **Změny hlasitosti**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit ve změně hlasitosti zařízení. **Není nakonfigurováno** umožňuje používat nastavení hlasitosti na zařízení.
- **Obnovení továrního nastavení**: Zvolte **bloku** zabrání uživatelům využívat objekt factory, které obnoví nastavení možnost v nastavení zařízení. **Není nakonfigurováno** umožňuje uživatelům použít toto nastavení na zařízení.
- **Bezpečné spuštění**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v restartování zařízení do nouzového režimu. **Není nakonfigurováno** umožňuje restartovat zařízení v nouzovém režimu.
- **Stavový řádek**: Zvolte **bloku** chcete zabránit přístupu do stavového řádku, včetně oznámení a rychlých nastavení. **Není nakonfigurováno** umožňuje uživatelům přístup k stavový řádek.
- **Roaming dat služby**: Zvolte **bloku** zabránit datový roaming přes mobilní síť. **Není nakonfigurováno** povolí datový roaming, když je zařízení v mobilní síti.
- **Změny nastavení Wi-Fi**: Zvolte **bloku** zabránit uživatelům možnost měnit nastavení Wi-Fi vytvořených vlastníkem zařízení. Uživatelé můžou vytvářet své vlastní konfigurace Wi-Fi. **Není nakonfigurováno** umožňuje uživatelům změnit nastavení Wi-Fi na zařízení.
- **Konfigurace přístupového bodu Wi-Fi**: Zvolte **bloku** chcete zabránit uživatelům ve vytváření nebo změně konfigurace Wi-Fi. **Není nakonfigurováno** umožňuje uživatelům změnit nastavení Wi-Fi na zařízení.
- **Konfigurace technologie Bluetooth**: Zvolte **bloku** uživatelům zabránit v konfiguraci Bluetooth na zařízení. **Není nakonfigurováno** umožňuje používat Bluetooth na zařízení.
- **Sdílení kontaktů přes Bluetooth**: Zvolte **bloku** zabránit přístupu k pracovním kontaktům z jiného zařízení, například systém automobilu, když zařízení s Androidem je spárováno pomocí Bluetooth. **Není nakonfigurováno** umožňuje přístup k pracovním kontaktům na jiném zařízení Bluetooth, které je spárováno na zařízení s Androidem.
- **Sdílení internetového připojení přes a přístup k hotspotům**: Zvolte **bloku** chcete zabránit ve sdílení internetového připojení přes a přístup na přenosné aktivní. **Není nakonfigurováno** umožňuje sdílení internetového připojení přes a přístup na přenosné aktivní.
- **Úložiště USB**: Zvolte **povolit** do úložiště USB na zařízení. **Není nakonfigurováno** brání v přístupu k úložiště USB.
- **Přenos souborů USB**: Zvolte **bloku** aby se zabránilo přenosu souborů přes USB. **Není nakonfigurováno** umožňuje přenos souborů.
- **Externí médium**: Zvolte **bloku** zabránit použití nebo připojení všechny externí médium v zařízení. **Není nakonfigurováno** povoluje externí médium v zařízení.
- **Světlo dat pomocí NFC**: Zvolte **bloku** zabránit světla dat z aplikací pomocí technologie téměř Field Communication (NFC). **Není nakonfigurováno** umožňuje pomocí NFC ke sdílení dat mezi zařízeními.
- **Funkce ladění**: Zvolte **povolit** můžou uživatelé používat funkce ladění na zařízení. **Není nakonfigurováno** uživatelům bránit v použití funkce ladění na zařízení.
- **Úprava mikrofonu**: Zvolte **bloku** uživatelům zrušit ztlumení mikrofonu a upravit hlasitosti mikrofonu. **Není nakonfigurováno** umožňuje uživateli používat a hlasitosti mikrofonu v zařízení.
- **E-maily pro ochranu před resetováním do továrního nastavení**: Zvolte **e-mailové adresy účtů Google**. Zadejte e-mailové adresy správců zařízení, které můžete odemknout zařízení, poté, co se vymaže. Ujistěte se, zda jste e-mailové adresy oddělujte středníkem, třeba `admin1@gmail.com;admin2@gmail.com`. Pokud není zadán e-mailu, kdokoli odemknutí zařízení po obnovení do továrního nastavení.
- **Sítě únikový poklop**: Zvolte **povolit** uživatelé zapnout funkci sítě řídicí šrafování. Pokud připojení k síti není proveden, jakmile se spustí zařízení, únikový poklop vyzve k dočasnému připojení k síti a aktualizovat zásady zařízení. Po uplatnění zásad se tato dočasná síť zapomene a zařízení pokračuje ve spouštění. Pokud tuto funkci připojení zařízení k síti:
  - V posledních zásadách není vhodné síťové.
  - Zařízení se spustí do aplikace v režimu uzamčení úloh.
  - Uživatel se nám kontaktovat nastavení zařízení.

  **Není nakonfigurováno** zabraňuje uživatelům v zapnutí funkce šrafování řídicí sítě na zařízení.

- **Povolit instalaci z neznámých zdrojů**: Zvolte **povolit** tak můžou uživatelé můžou zapnout **neznámé zdroje**. Toto nastavení umožňuje aplikace k instalaci z neznámých zdrojů. **Není nakonfigurováno** zabrání uživatelům zapnete **neznámé zdroje**.
- **Aktualizace systému**: Zvolte možnost definovat způsob, jakým zpracovává aktualizace distribuované bezdrátově zařízení:
  - **Výchozí ze zařízení**: Použije se výchozí nastavení zařízení.
  - **Automaticky**: Aktualizace se instalují automaticky bez zásahu uživatele. Po nastavení této zásady se hned nainstalují všechny čekající aktualizace.
  - **Odloženo**: Aktualizace se odloží o 30 dní. Na konci na 30 dnů Android se zobrazí výzva k instalaci aktualizace. Výrobci zařízení nebo mobilní operátoři mohou zakázat (vyloučit) odklad důležitých aktualizací zabezpečení. Vynechaná aktualizace zobrazí uživateli zařízení zprávu systému. 
  - **Časové období údržby**: Aktualizace se instalují automaticky během časového období údržby, které nastavíte v Intune. Instalace pokusí denně po dobu 30 dnů a může selhat, pokud je nedostatek místa či baterie úrovněmi. Po 30 dnech Android se zobrazí výzva k instalaci. Toto okno se také používá k instalaci aktualizací aplikací Play. Tuto možnost použijte pro vyhrazené zařízení, jako jsou veřejné terminály, jako veřejný terminál s jednou aplikací popředí aplikace je možné aktualizovat.
- **Automatické aktualizace aplikací**: Zvolte, pokud mají automatické aktualizace instalovat. Možnosti:
  - **Není nakonfigurováno**
  - **Výběr uživatele**
  - **Nikdy**
  - **Pouze Wi-Fi**
  - **Vždy**

### <a name="system-security-settings"></a>Systémové nastavení zabezpečení

- **Kontrola ohrožení aplikací**: **vyžadují** , který vynucuje **ověřovat aplikace** nastavení je povoleno pro pracovní a osobní profily.

### <a name="kiosk-settings"></a>Nastavení veřejného terminálu

Můžete nakonfigurovat na zařízení běžela jedna aplikace nebo velký počet aplikací. Když se zařízení v celoobrazovkovém režimu, jsou k dispozici pouze aplikace, které přidáte.

**Celoobrazovkový režim**: Zvolte, pokud zařízení spustí aplikaci jednu nebo více aplikací.

- **Veřejný terminál aplikace s jedním**: uživatelé mají přístup pouze k jedné aplikaci na zařízení. Při spuštění zařízení spustí jenom konkrétní aplikace. Uživatelé nemůžou otevírat nové aplikace ani měnit spuštěnou aplikaci.

  **Kroky**
  1. Zvolte **Vyberte spravovanou aplikaci**a vyberte ze seznamu spravovaných aplikací Google Play. 

      Pokud nemáte žádné aplikace, pak uvedené [přidat některé aplikace pro Android](apps-add-android-for-work.md) do zařízení. Nezapomeňte [přiřadit aplikace do skupiny zařízení, vytvořené pro vaše zařízení v celoobrazovkovém režimu](apps-deploy.md).

  2. Zvolte **OK** > **OK** a přidejte tak aplikaci.

- **Veřejný terminál s více aplikacemi**: uživatelé mají přístup k omezenou sadu aplikací na zařízení. Při spuštění zařízení, spustit pouze aplikace, které přidáte. Můžete také přidat některé webové odkazy, které uživatelé můžou otevírat. Když se zásady vztahují, uživatelé uvidí ikony pro povolené aplikace na domovské obrazovce.

  > [DŮLEŽITÉ] Pro zařízení v celoobrazovkovém režimu s více aplikacemi [spravované domovskou obrazovku aplikace](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) na webu Google Play **musí být**:
  >   - [Přidat jako klientskou aplikaci](apps-add-android-for-work.md) v Intune
  >   - [Přiřazené ke skupině zařízení](apps-deploy.md) vytvořené pro vaše zařízení v celoobrazovkovém režimu
  > 
  > **Spravované domovskou obrazovku** aplikace nemusí být v profilu konfigurace, ale je potřeba přidat jako klientská aplikace. Když **spravované domovskou obrazovku** aplikace se přidá jako klientskou aplikaci, všechny ostatní aplikace, které přidáte do configiration profilu se zobrazují jako ikony na **spravované domovskou obrazovku** aplikace. 

  - Zvolte **přidat**a vyberte ze seznamu aplikací.

    Pokud **spravované domovskou obrazovku** aplikace není uvedená, pak [přidat na webu Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Nezapomeňte [aplikaci přiřadit](apps-deploy.md) do skupiny zařízení, vytvořené pro vaše zařízení v celoobrazovkovém režimu.

    Můžete také přidat další [aplikace pro Android](apps-add-android-for-work.md) a [webové aplikace](web-app.md) vytvořená vaší organizací na zařízení. Nezapomeňte [přiřadit aplikace do skupiny zařízení, vytvořené pro vaše zařízení v celoobrazovkovém režimu](apps-deploy.md).

  - **Virtuální tlačítko Domů**: Zvolte **povolit** na zařízení beznabídkového režimu Zobrazit tlačítko Domů. Při výběru, vrátí uživatele na domovské obrazovce zařízení, uživatelé mohou snadno přepínat mezi aplikacemi. Na některých zařízeních s Androidem můžou uživatelé muset potažením prstem přejděte na obrazovce zobrazit tlačítko Domů. **Zakázat** nezobrazí tlačítko Domů, takže uživatelé musí použijte tlačítko Zpět. Chcete-li přepnout mezi aplikacemi.
  - **Ukončit režim veřejného terminálu**: Zvolte **povolit** umožňují správcům dočasně pozastavit celoobrazovkový režim pro aktualizaci zařízení. Pokud chcete používat tuto funkci, správce provede následující akce: 
  
    1. Dál vyberte tlačítko Zpět. až se zobrazí tlačítko "Konec veřejného terminálu". 
    2. Klikněte na tlačítko a zadejte **ponechte kódu celoobrazovkový režim** PIN kód.
    3. Po dokončení změn, vyberte **spravované domovskou obrazovku** aplikace. Tento krok relocks zařízení do režimu veřejného terminálu s více aplikacemi. 
    
    **Zakázat** nedává možnost pozastavit beznabídkový režim. Pokud správce pokračuje s výběrem tlačítka Zpět a vybere tlačítko "Konec veřejného terminálu", pak zobrazí zpráva, že heslo je povinné.
    
    - **Ponechte kódu celoobrazovkový režim**: zadejte číslice 4 až 6 číselný kód PIN. Správce používá tento PIN kód se dočasně pozastavit beznabídkový režim.
 
  - **Nastavit vlastní adresu URL pozadí**: Zadejte adresu URL přizpůsobení pozadí obrazovky na zařízení beznabídkového režimu.

### <a name="device-password-settings"></a>Nastavení hesla zařízení

- **Keyguard**: Zvolte **zakázat** zabránit funkci Keyguard zámek obrazovky na zařízení používá. **Není nakonfigurováno** umožňuje uživateli používat Keyguard funkce.
- **Požadovaný typ hesla**: Definujte typ hesla požadovaného pro zařízení. Možnosti:
  - **Aspoň číslice**
  - **Číselné komplexní**: opakovaných nebo po sobě jdoucí čísla, jako je například "1111" nebo "1234" nejsou povoleny.
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**
- **Minimální délka hesla**: Zadejte minimální délku hesla uživatel musí zadat (mezi 4 a 16 znaky).
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: Zadejte počet neúspěšných přihlášení povolit předtím, než se zařízení vymaže (mezi 1 – 11).

### <a name="power-settings"></a>Nastavení napájení

- **Čas do zamknutí obrazovky**: Nastavte dobu nečinnosti, po jejímž uplynutí se zařízení uzamkne.
- **Zapnutá obrazovka, když se zařízení napájí ze sítě**: Zvolte zdroje napájení, při jejichž použití zůstane obrazovka zařízení zapnutá.

### <a name="users-and-accounts-settings"></a>Nastavení uživatelů a účtů

- **Přidat nové uživatele**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v přidávání nových uživatelů. Každý uživatel má osobní pracovní prostor na zařízení pro vlastní domovské obrazovky, účty, aplikace a nastavení. **Není nakonfigurováno** umožňuje uživatelům přidávat ostatním uživatelům na zařízení.
- **Odebírání uživatelů**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v odebírání uživatelů. **Není nakonfigurováno** umožňuje uživatelům odebírat další uživatele ze zařízení.
- **Změny účtu**: Zvolte **Blokovat**, pokud chcete uživatelům zabránit v úpravě účtů. **Není nakonfigurováno** umožňuje uživatelům aktualizovat uživatelských účtů v zařízení.

## <a name="work-profile-only"></a>Pouze pracovní profil 

### <a name="work-profile-settings"></a>Nastavení pracovního profilu

#### <a name="general"></a>Obecné

- **Kopírování a vkládání mezi pracovními a osobními profily**: Zvolte **bloku** zabránit kopírování a vkládání mezi pracovními a osobními aplikacemi. **Není nakonfigurováno** umožňuje uživatelům sdílet data s aplikacemi v osobním profilu pomocí kopírování a vkládání 
- **Sdílení dat mezi pracovním a osobním profilem**: Zvolte, pokud může aplikace v pracovním profilu sdílení s aplikacemi v osobním profilu. Například můžete řídit akce sdílení v rámci aplikace, jako **sdílenou složku...** v aplikaci prohlížeče Chrome. Toto nastavení se nevztahuje na chování schránky při kopírování/vkládání. Vaše možnosti sdílení:
  - **Výchozí omezení sdílení**: jedná se o výchozí chování zařízení při sdílení, které se liší v závislosti na verzi Androidu. Ve výchozím nastavení je povolené sdílení z osobního profilu do pracovního profilu. Ve výchozím nastavení je také blokované sdílení z pracovního profilu do osobního profilu. Toto nastavení zabraňuje sdílení dat z pracovního do osobního profilu. Google neblokuje sdílení z osobního do pracovního profilu na zařízeních, která používají verze 6.0 a novější.
  - **Aplikace v pracovním profilu můžou zpracovat žádost o sdílení z osobního profilu**: povoluje integrovanou funkci Androidu, která umožňuje sdílet data z osobního do pracovního profilu. Pokud je tato možnost povolená, žádost o sdílení z aplikace v osobním profilu může sdílet data s aplikacemi v pracovním profilu. Toto nastavení je výchozí chování zařízení s Androidem, která používají verze starší než 6.0.
  - **Povolit sdílení přes hranice**: umožňuje sdílení přes hranice pracovního profilu v obou směrech. Když vyberete toto nastavení, můžou aplikace v pracovním profilu sdílet data s neoznačenými aplikacemi v osobním profilu. Toto nastavení povoluje spravovaným aplikacím v pracovním profilu sdílení s aplikacemi v nespravované oblasti zařízení. Proto ho používejte opatrně.

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

#### <a name="work-profile-password"></a>Heslo pracovního profilu

- **Vyžadovat heslo pracovního profilu**: platí pro Android 7.0 a vyšší s aktivovaným pracovním profilem. Zvolte **vyžadují** zadat zásady hesla, která se vztahuje pouze k aplikacím v pracovním profilu. Ve výchozím nastavení může koncový uživatel použít dva samostatně definované PIN kódy, nebo se může rozhodnout zkombinovat PIN kódy do silnějšího z nich. **Není nakonfigurováno** umožňuje uživateli používat pracovní aplikace, bez zadávání hesla.
- **Minimální délka hesla**: zadejte minimální počet znaků, které uživatelské heslo musí obsahovat, **4**-**16**.
- **Maximální doba neaktivity v minutách, než se pracovní profil zamkne**: umožňuje vybrat dobu, po které se pracovní profil zamkne. Potom musí uživatel zadat svoje přihlašovací údaje znovu, když bude chtít získat přístup.
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: zadejte, kolikrát může uživatel zadat nesprávné heslo, než se pracovní profil ze zařízení vymaže.
- **Konec platnosti hesla (dny)**: zadejte počet dnů, po kterém uživatel bude muset změnit heslo (**1**-**255**).
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
- **Smart Lock a jiné agenty pro určování důvěryhodnosti**: Zvolte **bloku** zabránit Smart Lock a jiné agenty pro určování důvěryhodnosti úpravy nastavení zamykací obrazovky na kompatibilních zařízeních. Tuto funkci, někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo uzamčené obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění. Je možné například obejít heslo pracovního profilu, když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.

### <a name="device-password"></a>Heslo zařízení

Tato nastavení hesla platí pro osobní profilů na zařízeních používajících pracovní profil.

- **Minimální délka hesla**: zadejte minimální počet znaků, které uživatelské heslo musí obsahovat, **4**-**14**.
- **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka**: umožňuje vybrat dobu, po které neaktivní zařízení automaticky zamkne.
- **Počet neúspěšných přihlášení před vymazáním obsahu zařízení**: zadejte, kolikrát může uživatel zadat nesprávné heslo, než se ze zařízení vymažou veškerá data.
- **Konec platnosti hesla (dny)**: zadejte počet dnů, po kterém uživatel bude muset změnit heslo (**1**-**255**).
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
- **Smart Lock a jiné agenty pro určování důvěryhodnosti**: Zvolte **bloku** zabránit Smart Lock a jiné agenty pro určování důvěryhodnosti úpravy nastavení zamykací obrazovky na kompatibilních zařízeních. Tuto funkci, někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo uzamčené obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění. Je možné například obejít heslo pracovního profilu, když je zařízení připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC. Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.

### <a name="system-security"></a>Zabezpečení systému

- **Kontrola ohrožení aplikací**: **vyžadují** , který vynucuje **ověřovat aplikace** nastavení je povoleno pro pracovní a osobní profily.

   > [!Note]
   > Toto nastavení funguje jenom u zařízení s Androidem O a vyšším.

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
  >  - Klient VPN, kterého zvolíte, musí být nainstalovaný na zařízení a musí podporovat VPN pro jednotlivé aplikace v pracovních profilech. V opačném případě dojde k chybě. 
  >  - Aplikaci klienta VPN je potřeba schválit ve **spravovaném obchodu Google Play**, synchronizovat ji do Intune a nasadit ji do zařízení. Až to vše uděláte, bude aplikace nainstalovaná v pracovním profilu uživatele.
  >  - Může zde být známé problémy při pomocí F5 přístup pro Android 3.0.4 VPN pro jednotlivé aplikace. Zobrazit [F5 zpráva k vydání verze pro F5 přístup pro Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) Další informace.

- **Režim uzamčení**: **Povolte**, abyste vynutili používání tunelu VPN veškerým síťovým provozem. Pokud připojení k VPN není vytvořené, potom nebude mít zařízení přístup k síti.

  Vyberte **Nenakonfigurováno** a povolte, aby provoz používal tunel VPN nebo mobilní síť.

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Můžete také vytvořit profily beznabídkového režimu pro [Android](device-restrictions-android.md#kiosk) a [Windows 10](kiosk-settings.md) zařízení.
