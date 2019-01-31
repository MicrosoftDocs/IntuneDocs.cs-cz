---
title: nastavení funkce zařízení s Iosem v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zobrazovat všechna nastavení konfigurace zařízení s Iosem pro AirPrint, rozložení domovské obrazovky, oznámení aplikací, sdílené zařízení, jednotné přihlašování a nastavení filtru webového obsahu v Microsoft Intune. Pomocí těchto nastavení v profilu konfigurace zařízení můžete nakonfigurovat zařízení s Iosem k používání těchto různých funkcí Apple ve vaší organizaci.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/30/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.openlocfilehash: 8656e480c292fc9ed1212f9d2c180b791cb4f94c
ms.sourcegitcommit: ce76541ceb783eb2e242032ef8579041d2f61532
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/31/2019
ms.locfileid: "55431486"
---
# <a name="ios-device-feature-settings-in-intune"></a>nastavení funkce zařízení s Iosem v Intune

Intune zahrnuje několik předdefinovaných nastavení umožníte uživatelům používat různé funkce Apple na svých zařízeních s Iosem. Například správci můžete řídit, jak uživatelé systému iOS pomocí tiskárny s Airprintem, přidání aplikací a složek do docku a stránky na domovské obrazovce zobrazit oznámení aplikací, zobrazit podrobnosti o značce asset na zamykací obrazovce, použijte ověření jednotného přihlašování a ověřování uživatelů s certifikáty.

Tento článek uvádí tato nastavení a popisuje, co dělá jednotlivých nastavení.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení pro iOS](device-features-configure.md#create-a-device-profile).

## <a name="airprint-settings"></a>Nastavení AirPrint

Tato funkce umožňuje iOS uživatelům tisknout známé tiskárny s Airprintem.

1. V **nastavení**vyberte **AirPrint**. Zadejte následující vlastnosti AirPrint serveru:

    - **IP adresa**: Zadejte adresu IPv4 nebo IPv6 tiskárny. Pokud k identifikaci tiskáren používáte názvy hostitelů, můžete získat IP adresu pomocí příkazu ping tiskárny, v terminálu. [Získat IP adresu a cestu](#get-the-ip-address-and-path) (v tomto článku) poskytuje další podrobnosti.
    - **Cesta**: Cesta je obvykle `ipp/print` pro tiskárny ve vaší síti. [Získat IP adresu a cestu](#get-the-ip-address-and-path) (v tomto článku) poskytuje další podrobnosti.
    - **Port**: Zadejte naslouchající port cíle AirPrint. Pokud tuto vlastnost nezadáte, AirPrint použije výchozí port. K dispozici v Iosu 11.0 a novějších.
    - **TLS**: Zvolte **povolit** k zabezpečení připojení AirPrint pomocí zabezpečení TLS (Transport Layer). K dispozici v Iosu 11.0 a novějších.

2. Vyberte **Přidat**. AirPrint server se přidá do seznamu. Můžete přidat více serverů AirPrint.

    Můžete také **Import** souboru oddělený čárkami (CSV) s těmito informacemi. Po vytvoření seznamu, můžete také **exportovat** seznamu serverů AirPrint.

3. Až budete hotovi, vyberte **OK** k uložení seznamu.

Přidání serverů AirPrinter, potřebujete IP adresu z tiskárny, cestu prostředku a port. Následující kroky ukazují, jak získat tyto informace.

1. Na Macu, který je připojený ke stejné místní síti (stejná podsíť) jako tiskárny s Airprintem, otevřete **terminálu** (z **/aplikace/Utility**).
2. V terminálu zadejte `ippfind`, a vyberte možnost enter.

    Poznámka: informace o tiskárně. Například může vrátit podobně jako `ipp://myprinter.local.:631/ipp/port1`. První část je název tiskárny. Poslední část (`ipp/port1`) je cesta prostředku.

3. V terminálu zadejte `ping myprinter.local`, a vyberte možnost enter.

   Poznamenejte si IP adresu. Například může vrátit podobně jako `PING myprinter.local (10.50.25.21)`.

4. Použijte hodnoty IP adres a prostředků cestu. V tomto příkladu je IP adresa `10.50.25.21`, a cesta prostředku je `/ipp/port1`.

## <a name="home-screen-layout-settings"></a>Nastavení rozložení domovské obrazovky

Tato nastavení konfigurovat rozložení aplikací a složky v docku a domovské obrazovky zařízení s Iosem. Zařízení s Iosem pro tuto funkci používat, musíte být v režimu pod dohledem a používat iOS 9.3 nebo novější.

### <a name="dock"></a>Ukotvení

Použití **ukotvit** nastavení přidat až šest položek nebo složek do docku obrazovky Iosu. Mnoho zařízení podporuje méně položek. Zařízení iPhone například podporují maximálně čtyři položky. V takovém případě se zobrazí jenom první čtyři položky, které přidáte na zařízení.

1. V **nastavení**vyberte **rozložení domovské obrazovky (jenom pod dohledem)** > **Dock** > **přidat**. Můžete přidat až **šest** položek (aplikace a složky, v kombinaci) pro dock zařízení.
2. V **typ**, zvolte možnost Přidat **aplikace** nebo **složky**.

    - **Přidat aplikaci**: Tato možnost slouží k přidání aplikací do docku na obrazovce. Zadejte:

      - **Název aplikace**: Zadejte název aplikace. Tento název se používá pro vaši informaci na webu Azure Portal. To *není* zobrazí na zařízení s Iosem.
      - **ID sady prostředků aplikace**: Zadejte ID sady prostředků aplikace. Zobrazit [ID sady prostředků pro integrované aplikace pro iOS](#bundle-ids-for-built-in-ios-apps) (v tomto článku) pro několik příkladů.

      Vyberte **OK** uložte provedené změny.

    - **Přidat složku**: Tato možnost slouží k přidání složky do docku na obrazovce. 

      Aplikace, které přidáte na stránku ve složce jsou seřazené zleva doprava a ve stejném pořadí jako seznam. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se na jinou stránku.

      1. Zadejte **název složky**. Tento název se zobrazí uživatelům na jejich zařízení.
      2. Zvolte **přidat**a zadejte následující vlastnosti:

          - **Název stránky**: Zadejte název stránky. Tento název se používá pro vaši informaci na webu Azure Portal. To *není* zobrazí na zařízení s Iosem.
          - **Název aplikace**: Zadejte název aplikace. Tento název se používá pro vaši informaci na webu Azure Portal. To *není* zobrazí na zařízení s Iosem.
          - **ID sady prostředků aplikace**: Zadejte ID sady prostředků aplikace. Zobrazit [ID sady prostředků pro integrované aplikace pro iOS](#bundle-ids-for-built-in-ios-apps) (v tomto článku) pro několik příkladů.

      3. Zvolte **přidat**. Můžete přidat až **20** ukotvení stránky pro zařízení.
      4. Vyberte **OK** uložte provedené změny.

#### <a name="example"></a>Příklad

V následujícím příkladu docku obrazovky zobrazuje pouze aplikace Safari, e-mailu a akcie. Zobrazíte její vlastnosti je vybraná aplikace Mail:

![Ukázkové nastavení Docku iOSu](./media/FfFiUcP.png)

Když přiřadíte zásady k Iphonu, docku vypadá podobně jako na následujícím obrázku:

![Ukázkové rozložení Docku iOSu na iPhonu](./media/bAgCe8F.png)

### <a name="pages"></a>Stránky

Přidejte stránky, které chcete, aby zobrazený na domovské obrazovce a aplikace, které se mají zobrazit na jednotlivých stránkách. Aplikace, které přidáte na stránku, jsou seřazené zleva doprava, ve stejném pořadí jako seznam. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se na jinou stránku.

> [!TIP]
> Chcete-li změnit pořadí položek v jakékoli domovské obrazovce a v seznamech stránek, lze přetáhnout a jejich umístění.

1. V **nastavení**vyberte **rozložení domovské obrazovky (jenom pod dohledem)** > **stránky** > **přidat**. Můžete přidat až **40** stránky na zařízení.
2. Zadejte **název stránky**. Tento název se používá pro vaši informaci na webu Azure Portal a *není* zobrazí na zařízení s Iosem. 

    Vyberte **Přidat**. Můžete přidat až **60** položek (aplikace a složky v kombinaci) na zařízení.

3. V **typ**, zvolte možnost Přidat **aplikace** nebo **složky**.

    - **Přidat aplikaci**: Tato možnost přidat na stránku na obrazovce aplikace. Zadejte:

      - **Název aplikace**: Zadejte název aplikace. Tento název se používá pro vaši informaci na webu Azure Portal. To *není* zobrazí na zařízení s Iosem.
      - **ID sady prostředků aplikace**: Zadejte ID sady prostředků aplikace. Zobrazit [ID sady prostředků pro integrované aplikace pro iOS](#bundle-ids-for-built-in-ios-apps) (v tomto článku) pro několik příkladů.

      Vyberte **OK** uložte provedené změny.

    - **Přidat složku**: Tato možnost slouží k přidání složky do docku na obrazovce. 

      Aplikace, které přidáte na stránku ve složce jsou seřazené zleva doprava a ve stejném pořadí jako seznam. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se na jinou stránku.

      1. Zadejte **název složky**. Tento název se zobrazí uživatelům na jejich zařízení.
      2. Zvolte **přidat**a zadejte následující vlastnosti:

          - **Název stránky**: Zadejte název stránky. Tento název se používá pro vaši informaci na webu Azure Portal. To *není* zobrazí na zařízení s Iosem.
          - **Název aplikace**: Zadejte název aplikace. Tento název se používá pro vaši informaci na webu Azure Portal. To *není* zobrazí na zařízení s Iosem.
          - **ID sady prostředků aplikace**: Zadejte ID sady prostředků aplikace. Zobrazit [ID sady prostředků pro integrované aplikace pro iOS](#bundle-ids-for-built-in-ios-apps) (v tomto článku) pro několik příkladů.

      3. Zvolte **přidat**.
      4. Vyberte **OK** uložte provedené změny.

#### <a name="example"></a>Příklad

V následujícím příkladu se vytvoří nová stránka s názvem **Contoso** je přidána. Na stránce se zobrazí aplikace najít přátele a nastavení. V aplikaci nastavení se vybere zobrazíte jeho vlastnosti:

![Příklad nastavení domovské obrazovky iOSu](./media/Jc2OxyX.png)

Když přiřadíte zásady k Iphonu, bude stránka vypadat podobně jako na následujícím obrázku:

![Zařízení s iOSem se změněnou domovskou obrazovkou](./media/Bd37PHa.png)

## <a name="app-notifications-settings"></a>Nastavení oznámení aplikací

Zvolte, jak aplikace nainstalované na iOS zařízení odesílat oznámení. Tato nastavení podporují zařízení pod dohledem s iOSem 9.3 a novějším.

1. V **nastavení**vyberte **oznámení aplikací (jenom pod dohledem)** > **přidat**:

    ![Přidání oznámení aplikací v profilu iOS v Intune](./media/ios-macos-app-notifications.png)

2. Zadejte tyto vlastnosti:

    - **ID sady prostředků aplikace**: Zadejte **ID sady prostředků aplikace** aplikace, které chcete přidat. Zobrazit [ID sady prostředků pro integrované aplikace pro iOS](#bundle-ids-for-built-in-ios-apps) (v tomto článku) pro několik příkladů.
    - **Název aplikace**: Zadejte název aplikace, kterou chcete přidat. Tento název se používá pro vaši informaci na webu Azure Portal. To *není* zobrazené na zařízení.
    - **Publisher**: Zadejte vydavatele aplikace, kterou přidáváte. Tento název se používá pro vaši informaci na webu Azure Portal. To *není* zobrazené na zařízení.
    - **Oznámení**: **Povolit** nebo **zakázat** aplikaci zasílání oznámení do zařízení.
       - **Zobrazit v centru oznámení**: **Povolit** umožňuje, aby aplikace zobrazovala oznámení v centru oznámení zařízení. **Zakázat** brání aplikaci v zobrazení oznámení v centru oznámení.
       - **Zobrazit na zamykací obrazovce**: Vyberte **povolit** umožníte zobrazování oznámení z aplikace na zamykací obrazovce zařízení. **Zakázat** brání aplikaci v zobrazení oznámení na zamykací obrazovce.
       - **Typ výstrahy**: Když je zařízení odemčené z, zvolte, jak se zobrazí oznámení. Možnosti:
         - **Žádný**: Je zobrazena žádná oznámení.
         - **Banner**: Banner se krátce zobrazí oznámení.
         - **Modální**: Zobrazí oznámení a uživatel ho musí ručně zavřít než budete pokračovat s používáním zařízení.
       - **Odznáček na ikoně aplikace**: Vyberte **povolit** přidá Odznáček na ikonu aplikace. Oznámení "BADGE" znamená, že aplikace odeslala oznámení.
       - **Zvuky**: Vyberte **povolit** při doručení oznámení se přehraje zvuk.

3. Vyberte **OK** uložte provedené změny. Pokračujte v přidávání aplikací, které chcete. Až budete hotovi, vyberte **OK**.

## <a name="lock-screen-message-settings"></a>Zpráva nastavení zamykací obrazovky

Pomocí těchto nastavení můžete zobrazit vlastní zprávu nebo text na přihlašovací okno a na zamykací obrazovce. Například můžete zadat zprávu "Při ztrátě vrátit..." a informace z inventárního štítku. 

Tato funkce podporuje zařízení pod dohledem s:

- iOS 9.3 nebo novější

1. V **nastavení**vyberte **zpráva na zamčené obrazovce (jenom pod dohledem)**.
2. Zadejte následující nastavení:

    - **Informace z inventárního štítku**: Zadejte informace o inventárním štítku zařízení. Zadejte například `Owned by Contoso Corp` nebo `Serial Number: {{serialnumber}}`. 

      Text, který zadáte, se zobrazí na přihlašovací okno a na zamykací obrazovce zařízení.

    - **Zamykací obrazovka Poznámka pod čarou**: Pokud ke ztrátě nebo odcizení zařízení, zadejte poznámku, která může pomoci vrátit zařízení. Můžete zadat libovolný text, který chcete. Zadejte třeba `If found, call Contoso at ...`.

    Zařízení tokeny lze také přidat informace specifické pro zařízení s těmito poli. Chcete-li zobrazit sériové číslo, zadejte například `Serial Number: {{serialnumber}}`. Text se zobrazí na zamykací obrazovce, podobně jako `Serial Number 123456789ABC`. Při vstupu do proměnné, je potřeba použít složené závorky `{{ }}`. [Konfigurace tokenů aplikace](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) obsahuje seznam proměnných, které lze použít. Můžete také použít `deviceName` nebo libovolné jiné hodnoty konkrétní zařízení.

    > [!NOTE]
    > Proměnné pořadí úloh se neověřuje v uživatelském rozhraní. V důsledku toho se může zobrazit profily uložen s nesprávný vstup. Pokud zadáte například `{{Devicename}}` místo `{{devicename}}`, pak namísto jedinečný název zařízení se zobrazí řetězcový literál.

3. Až budete hotovi, vyberte **OK** uložte provedené změny.

## <a name="single-sign-on-settings"></a>Nastavení jednotného přihlašování

Většina obchodních aplikací vyžaduje z důvodu zabezpečení určitou úroveň ověřování uživatelů. V mnoha případech se ověření vyžaduje, aby uživatel zadat stejné přihlašovací údaje opakovaně, což je pro uživatele nepříjemné. Chcete-li vylepšit uživatelské prostředí, vývojáři mohou vytvářet aplikace, které používají jednotné přihlašování (SSO). Použití jednotného přihlašování se snižuje počet, kolikrát uživatel musí zadat přihlašovací údaje.

Použití jednotného přihlašování, nezapomeňte, že máte následující:

- Aplikace, která je kódem vyhledávajícím úložiště přihlašovacích údajů uživatele v jednotného přihlašování na zařízení.
- Nakonfigurování Intune na jednotné přihlašování pro zařízení s iOSem

1. V **nastavení**vyberte **jednotného přihlašování**:

   ![Podokno Jednotné přihlašování](./media/sso-blade.png)

2. Zadejte následující nastavení:

    - **Atribut uživatelského jména z AAD**: Intune bude vypadat pro tento atribut pro každého uživatele ve službě Azure AD. Intune pak vyplní příslušné pole (například hlavní název uživatele) před vytvořením kódu XML, který se nainstaluje na zařízení. Možnosti:

      - **Hlavní název uživatele**: Hlavní název uživatele je analyzován následujícím způsobem:

        ![Atribut uživatelského jména](media/User-name-attribute.png)

        Sféru také můžete přepsat textem, který zadáte do textového pole **Sféra**.

        Například Contoso má několik oblastí, včetně Evropa, Asie a Severní Amerika. Contoso chce, aby jejich uživatelé Asie přes jednotné přihlašování a daná aplikace vyžaduje hlavní název uživatele v `username@asia.contoso.com` formátu. Když vyberete **hlavní název uživatele**, sféra pro každého uživatele je převzata z Azure AD, která je `contoso.com`. Proto pro uživatele v Asii, vyberte **hlavní název uživatele**a zadejte `asia.contoso.com`. Koncový uživatel (UPN) se stane `username@asia.contoso.com`, namísto `username@contoso.com`.

      - **ID zařízení v Intune**: Intune automaticky vybere ID zařízení v Intune.

        Ve výchozím nastavení aplikace používají ID zařízení. Pokud vaše aplikace používá sféru a ID zařízení, můžete však zadat sféru v textovém poli sféru.

        > [!NOTE]
        > Implicitně platí, že pokud používáte ID zařízení, sféru nevyplňujte.

      - **ID zařízení Azure AD**

    - **Sféra**: Zadejte domény část adresy URL. Zadejte například `contoso.com`.
    - **Předpony adres URL, které použijí jednotné přihlašování**: **Přidat** všechny adresy URL ve vaší organizaci, které vyžadují jednotné přihlašování – ověřování uživatelů.

        Například pokud se uživatel připojí k některému z těchto webů, použije zařízení s iOSem přihlašovací údaje pro jednotné přihlašování. Uživatel nemusí zadávat další přihlašovací údaje. Pokud je povolené ověřování službou Multi-Factor Authentication, uživatelé budou muset i druhé ověření.

        > [!NOTE]
        > V těchto adresách URL se musí používat správně naformátovaný plně kvalifikovaný název domény. Apple vyžaduje, aby tyto v `http://<yourURL.domain>` formátu.

        Odpovídající vzory adres URL musí mít na začátku `http://` nebo `https://`. Prosté ověření shody řetězců běží, takže `http://www.contoso.com/` předponu adresy URL zadané informace neodpovídají `http://www.contoso.com:80/`. Se systémem iOS 10.0 nebo vyšší, jeden zástupný znak \* slouží k zadání všech odpovídajících hodnot. Například `http://*.contoso.com/` odpovídá obě `http://store.contoso.com/` a `http://www.contoso.com`.

        `http://.com` a `https://.com` vzorky odpovídají všechny HTTP a adresy URL HTTPS, v uvedeném pořadí.

    - **Aplikace, které použijí jednotné přihlašování**: **Přidat** aplikací na zařízeních koncových uživatelů, které můžou používat jednotné přihlašování.

        `AppIdentifierMatches` Pole musí obsahovat řetězce, které odpovídají ID sady prostředků aplikace. Tyto řetězce můžou být přesné shody, jako například `com.contoso.myapp`, nebo zadejte shodu předpony pomocí ID sady prostředků \* zástupný znak. Zástupný znak musí být uvedena po tečce (.) a může objevit jenom jednou, na konci řetězce, jako například `com.contoso.*`. Při použití zástupného znaku se udělí přístup k účtu všem aplikacím, jejichž ID sady prostředků začíná příslušnou předponou.

        **Název aplikace** použijte k zadání popisného názvu, který pomůže při identifikaci ID sady prostředků.

    - **Certifikát pro prodloužení platnosti přihlašovacích údajů**: Pokud používáte certifikáty pro ověřování (a ne hesla), vyberte existující certifikát SCEP nebo PFX jako ověřovací certifikát. Tento certifikát je obvykle stejný certifikát, který se nasazuje pro jiné profily, jako je například VPN, Wi-Fi nebo e-mailu uživatele.

3. Až budete hotovi, vyberte **OK** uložte provedené změny.

## <a name="web-content-filter-settings"></a>Nastavení filtru webového obsahu

Toto nastavení řídí přístup k adrese URL prohlížeče na zařízeních s Iosem.

1. V **nastavení**vyberte **filtr webového obsahu (jenom pod dohledem)**.
2. Zvolte **typ filtru**. Možnosti:

    - **Konfigurovat adresy URL**: Použijte integrovaný webový filtr společnosti Apple, který hledá, včetně vulgárních výrazů a sexuálně explicitní výrazy. Tato funkce vyhodnocuje každou webovou stránku, jako je načteno a identifikuje a blokovat nevhodný obsah. Můžete také přidat adresy URL, které nechcete, aby zkontroloval filtru. Nebo blokovat konkrétní adresu URL, bez ohledu na nastavení filtru společnosti Apple.

      - **Povolené adresy URL**: **Přidat** adresy URL, které chcete povolit. Těmto adresám URL obejít webový filtr společnosti Apple.

        > [!NOTE]
        > Adresy URL, kterou zadáte jsou adresy URL nechcete evauluated pomocí webového filtru Apple. Tyto adresy URL nejsou seznam povolených webů. Chcete-li vytvořit seznam povolených webů, nastavte **typ filtru** k **jenom konkrétní weby**.

        Vyberte **OK** uložte provedené změny.

      - **Blokované adresy URL**: **Přidat** adresy URL, které chcete zastavit otevřít, bez ohledu na nastavení webového filtru Apple.

        Vyberte **OK** uložte provedené změny.

    - **Jenom konkrétní weby** (pro webový prohlížeč Safari pouze): Tyto adresy URL se přidají do záložek prohlížeče Safari. Uživatel je **pouze** navštěvovat tyto weby; žádné jiné servery lze otevřít. Tuto možnost použijte jenom v případě, že znáte přesný seznam adres URL, ke kterým mají uživatelé přístup.

      - **ADRESA URL**: Zadejte adresu URL webu, který chcete povolit. Zadejte například `https://www.contoso.com`.
      - **Cesta k záložce**: Zadejte cestu k uložit záložku. Zadejte například `/Contoso/Business Apps`. Pokud cestu nepřidáte, záložka se přidá do výchozí složky záložek na zařízení.
      - **Název**: Zadejte popisný název záložky.

      Pokud nezadáte žádné adresy URL, pak koncoví uživatelé nemají přístup k žádným webům s výjimkou `microsoft.com`, `microsoft.net`, a `apple.com`. Tyto adresy URL jsou povolené automaticky službou Intune.

      Vyberte **OK** uložte provedené změny.

## <a name="wallpaper-settings"></a>Nastavení tapety

Přidání vlastní image ve formátu PNG, JPG nebo JPEG do zařízení s Iosem pod dohledem. Použijte například logo společnosti na zamykací obrazovce.

Pokud profil se žádné image je přiřazený k zařízení pomocí stávající image, může dojít k neočekávanému chování. Například vytvořit profil bez bitovou kopii. Tento profil je přiřazený k zařízení, která již mít nějakou image. V tomto scénáři image se může změnit výchozí nastavení zařízení nebo původní bitové kopie mohou zůstat na zařízení. Toto chování je řízen a omezené platformou MDM společnosti Apple.

- **Tapeta umístění zobrazení**: Vyberte umístění na zařízení zobrazit obrázek. Možnosti:
  - **Není nakonfigurováno**: Vlastní image se přidá do zařízení. Zařízení využívá výchozí operační systém.
  - **Zamykací obrazovka**: Přidá obrázek zamykací obrazovku.
  - **Domovské obrazovky**: Přidá image na domovskou obrazovku.
  - **Zamykací obrazovka a domovské obrazovce**: Používá stejnou bitovou kopii na zamykací obrazovce a domovské obrazovky.
- **Obrázek tapety**: Nahrajte existující .png, .jpg nebo .jpeg image, kterou chcete použít. Ujistěte se, že velikost souboru je menší než 750 KB. Můžete také **odebrat** bitovou kopii, kterou jste přidali.

> [!TIP]
> Chcete-li zobrazit různé obrázky na zamykací obrazovce a na domovské obrazovce, vytvoření profilu s obrázek zamykací obrazovky. Vytvořte jiný profil s použitím image domovskou obrazovku. Přiřaďte oba profily do skupin uživatelů nebo zařízení s Iosem.

## <a name="bundle-ids-for-built-in-ios-apps"></a>ID sady prostředků pro integrované aplikace pro iOS

Tento seznam zobrazuje ID sady prostředků některých běžných integrovaných aplikací pro iOS. Pokud chcete najít ID sady prostředků jiných aplikací, obraťte se na dodavatele softwaru.

|||
|-|-|
|Název aplikace|ID sady prostředků|
|App Store|com.apple.AppStore|
|Kalkulačka|com.apple.calculator|
|Kalendář|com.apple.mobilecal|
|Fotoaparát|com.apple.camera|
|Hodiny|com.apple.mobiletimer|
|Kompas|com.apple.compass|
|Kontakty|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Najít přátele|com.apple.mobileme.fmf1|
|Najít iPhone|com.apple.mobileme.fmip1|
|Herní centrum|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Stav|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.apple.mobilemail|
|Mapy|com.apple.Maps|
|Zprávy|com.apple.MobileSMS|
|Hudba|com.apple.Music|
|News|com.apple.news|
|Poznámky|com.apple.mobilenotes|
|Numbers|com.apple.Numbers|
|Pages|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Fotky|com.apple.mobileslideshow|
|Podcasty|com.apple.podcasts|
|Připomínky|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Nastavení|com.apple.Preferences|
|Stocks|com.apple.stocks|
|Tipy|com.apple.tips|
|Videa|com.apple.videos|
|Diktafon|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Watch|com.apple.Bridge|
|Počasí|com.apple.weather|

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Můžete také vytvořit zařízení profilů funkcí pro [macOS](macos-device-features-settings.md) zařízení.
