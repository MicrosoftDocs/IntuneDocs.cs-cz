---
title: nastavení funkcí zařízení s iOS v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na všechna nastavení a nakonfigurujte zařízení s iOS pro účely tisku, rozložení domovské obrazovky, oznámení aplikací, sdílené zařízení, jednotné přihlašování a nastavení filtru webového obsahu v Microsoft Intune. Pomocí těchto nastavení v profilu konfigurace zařízení můžete nakonfigurovat, aby zařízení s iOS používala tyto funkce Apple ve vaší organizaci.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/16/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7eaed88adc8603ee1f79f47cbd94eec1c3b71b95
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2019
ms.locfileid: "71301853"
---
# <a name="ios-and-ipados-device-settings-to-use-common-ios-features-in-intune"></a>nastavení zařízení s iOS a iPadOS pro použití běžných funkcí iOS v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune obsahuje některá vestavěná nastavení, která uživatelům iOS umožní používat na svých zařízeních jiné funkce společnosti Apple. Správci můžou například řídit, jak uživatelé iOS používají tiskárny pro průchozí tisk, přidávat aplikace a složky do Docku a stránky na domovské obrazovce, zobrazovat oznámení aplikací, zobrazit podrobnosti o značce assetu na zamykací obrazovce, používat ověřování pomocí jednotného přihlašování a ověřovat uživatele. s certifikáty.

Pomocí těchto funkcí můžete ovládat zařízení iOS jako součást řešení správy mobilních zařízení (MDM).

Tento článek uvádí tato nastavení a popisuje, co jednotlivé nastavení dělá. Další informace o těchto funkcích najdete v [Přidání nastavení funkcí zařízení se systémem iOS nebo MacOS](device-features-configure.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte konfigurační profil zařízení s iOS](device-features-configure.md).

> [!NOTE]
> Tato nastavení platí pro různé typy registrace s některými nastaveními, která platí pro všechny možnosti registrace. Další informace o různých typech registrace najdete v tématu Registrace zařízení se [systémem iOS](ios-enroll.md).

## <a name="airprint"></a>AirPrint

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: Všechny typy registrace

- **IP adresa**: Zadejte adresu protokolu IPv4 nebo IPv6 tiskárny. Pokud k identifikaci tiskáren používáte názvy hostitelů, můžete získat IP adresu tím, že v terminálu otestujete tiskárnu. Další podrobnosti najdete v článku získání IP adresy a cesty (v tomto článku).
- **Cesta**: Cesta je typicky `ipp/print` pro tiskárny v síti. Další podrobnosti najdete v článku získání IP adresy a cesty (v tomto článku).
- **Port**: Zadejte port naslouchání cíle přenosu. Pokud necháte tuto vlastnost prázdnou, použije se při tisku výchozí port. K dispozici v iOS 11,0 a novějších verzích.
- **TLS**: Vyberte **Povolit** a zabezpečte připojení přes tisk přes protokol TLS (Transport Layer Security). K dispozici v iOS 11,0 a novějších verzích.

Pokud chcete přidat servery pro tisk přes mosty, můžete:

- **Přidání** přidá do seznamu přidat server pro příjem. Je možné přidat spoustu tiskových serverů.
- **Importujte** textový soubor s oddělovači (. csv) s těmito informacemi. Případně můžete **exportovat** a vytvořit tak seznam serverů pro tisk do, které jste přidali.

### <a name="get-server-ip-address-resource-path-and-port"></a>Získat IP adresu serveru, cestu prostředku a port

Chcete-li přidat servery s modulem pro tisk, budete potřebovat IP adresu tiskárny, cestu k prostředku a port. Následující kroky ukazují, jak tyto informace získat.

1. Na Macu, který je připojený ke stejné místní síti (podsíti) jako tiskárny pro Protisk, otevřete **terminál** (z **/aplikace/Utility**).
2. V terminálu zadejte `ippfind`a vyberte Enter.

    Poznamenejte si informace o tiskárně. Například může vracet něco podobného jako `ipp://myprinter.local.:631/ipp/port1`. První část je název tiskárny. Poslední část (`ipp/port1`) je cesta prostředku.

3. V terminálu zadejte `ping myprinter.local`a vyberte Enter.

   Poznamenejte si IP adresu. Například může vracet něco podobného jako `PING myprinter.local (10.50.25.21)`.

4. Použijte hodnoty IP adresy a prostředku cesty. V tomto příkladu je IP adresa `10.50.25.21`a `/ipp/port1`cesta k prostředku.

## <a name="home-screen-layout"></a>Rozložení domovské obrazovky

Tato funkce platí pro:

- iOS 9,3 nebo novější

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

### <a name="dock"></a>Vyjměte

Pomocí nastavení **Dock** přidejte až šest položek nebo složek do Docku obrazovky iOS. Mnoho zařízení podporuje méně položek. Například zařízení iPhone podporují až čtyři položky. V takovém případě se na zařízení zobrazí jenom první čtyři položky, které přidáte.

Pro Dock zařízení můžete přidat až **šest** položek (kombinované aplikace a složky).

- **Přidat**: Přidá aplikace nebo složky do Docku na zařízení.
- **Zadejte**: Přidat **aplikaci** nebo **složku**:

  - **Aplikace**: Tuto možnost vyberte, pokud chcete přidat aplikace do Docku na obrazovce. Napište

    - **Název aplikace**: Zadejte název aplikace. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
    - **ID sady prostředků aplikace**: Zadejte ID sady prostředků aplikace. Některé příklady najdete v tématu [ID sad pro integrované aplikace pro iOS](bundle-ids-built-in-ios-apps.md) .

  - **Složka**: Tuto možnost vyberte, pokud chcete přidat složku do Docku na obrazovce.

    Aplikace, které přidáte na stránku ve složce, jsou seřazené zleva doprava a ve stejném pořadí jako seznam. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se aplikace na jinou stránku.

    - **Název složky**: Zadejte název složky. Tento název se zobrazí uživatelům na svém zařízení.
    - **Seznam stránek**: **Přidejte** stránku a zadejte následující vlastnosti:

      - **Název stránky**: Zadejte název stránky. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
      - **Název aplikace**: Zadejte název aplikace. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
      - **ID sady prostředků aplikace**: Zadejte ID sady prostředků aplikace. Některé příklady najdete v tématu [ID sad pro integrované aplikace pro iOS](bundle-ids-built-in-ios-apps.md) .

      Pro Dock zařízení můžete přidat až **20** stránek.

> [!NOTE]
> Když přidáváte ikony pomocí nastavení Dock, ikony na domovské obrazovce a stránkách jsou zamčené a nejde je přesunout. To může být záměrné pomocí zásad MDM a iOS pro iOS a Apple.

#### <a name="example"></a>Příklad

V následujícím příkladu se zobrazí docká obrazovka jenom aplikace Safari, pošta a akcie. Aplikace Pošta je vybrána k zobrazení vlastností:

![Ukázkové nastavení Docku iOSu](./media/FfFiUcP.png)

Když přiřadíte zásady k iPhonu, bude Dock vypadat podobně jako na následujícím obrázku:

![Ukázkové rozložení Docku iOSu na iPhonu](./media/bAgCe8F.png)

### <a name="pages"></a>Stránky

Přidejte stránky, které chcete zobrazit na domovské obrazovce, a aplikace, které chcete zobrazit na jednotlivých stránkách. Aplikace, které přidáte na stránku, jsou seřazené zleva doprava ve stejném pořadí jako seznam. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se aplikace na jinou stránku.

> [!TIP]
> Chcete-li změnit pořadí položek v seznamech na domovské obrazovce a na stránkách, můžete je přetáhnout.

Na zařízení můžete přidat až **40** stránek.

- **Seznam stránek**: **Přidejte** stránku a zadejte následující vlastnosti:

  - **Název stránky**: Zadejte název stránky. Tento název se používá pro váš odkaz v Azure Portal a *není* zobrazený na zařízení s iOS.

  Do zařízení můžete přidat až **60** položek (sloučené aplikace a složky).

  - **Přidat**: Přidá aplikace nebo složky na stránku na zařízení.

    - **Zadejte**: Přidat **aplikaci** nebo **složku**:

      - **Aplikace**: Tuto možnost vyberte, pokud chcete přidat aplikace na stránku na obrazovce. Dále zadejte:

        - **Název aplikace**: Zadejte název aplikace. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
        - **ID sady prostředků aplikace**: Zadejte ID sady prostředků aplikace. Některé příklady najdete v tématu [ID sad pro integrované aplikace pro iOS](bundle-ids-built-in-ios-apps.md) .

      - **Složka**: Tuto možnost vyberte, pokud chcete přidat složku do Docku na obrazovce.

        Aplikace, které přidáte na stránku ve složce, jsou seřazené zleva doprava a ve stejném pořadí jako seznam. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se aplikace na jinou stránku.

        - **Název složky**: Zadejte název složky. Tento název se zobrazí uživatelům na zařízení.
        - **Přidat**: Přidá stránky do složky. Zadejte také následující vlastnosti:

          - **Název stránky**: Zadejte název stránky. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
          - **Název aplikace**: Zadejte název aplikace. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
          - **ID sady prostředků aplikace**: Zadejte ID sady prostředků aplikace. Některé příklady najdete v tématu [ID sad pro integrované aplikace pro iOS](bundle-ids-built-in-ios-apps.md) .

#### <a name="example"></a>Příklad

V následujícím příkladu je přidána nová stránka s názvem **Contoso** . Na stránce se zobrazí aplikace najít přátele a nastavení. Vybraná aplikace nastavení zobrazuje vlastnosti:

![Příklad nastavení domovské obrazovky iOSu](./media/Jc2OxyX.png)

Když přiřadíte zásady k iPhonu, stránka bude vypadat podobně jako na následujícím obrázku:

![Zařízení s iOSem se změněnou domovskou obrazovkou](./media/Bd37PHa.png)

## <a name="app-notifications"></a>Oznámení aplikací

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

- **Přidat**: Přidat oznámení pro aplikace:

    ![Přidání oznámení aplikace v profilu iOS v Intune](./media/ios-macos-app-notifications.png)

  - **ID sady prostředků aplikace**: Zadejte **ID sady prostředků** aplikace, kterou chcete přidat. Některé příklady najdete v tématu [ID sad pro integrované aplikace pro iOS](bundle-ids-built-in-ios-apps.md) .
  - **Název aplikace**: Zadejte název aplikace, kterou chcete přidat. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení.
  - **Vydavatel**: Zadejte vydavatele aplikace, kterou přidáváte. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení.
  - **Oznámení**: **Povolí** nebo **zakáže** aplikaci odesílat oznámení do zařízení.
    - **Zobrazit v centru oznámení**: **Možnost Povolit** umožňuje aplikaci zobrazovat oznámení v centru oznámení zařízení. **Disable** zabrání aplikaci v zobrazování oznámení v centru oznámení.
    - **Zobrazit na zamykací obrazovce**: Výběrem **Povolit** zobrazíte oznámení z aplikace na zamykací obrazovce zařízení. **Disable** zabrání aplikaci zobrazovat oznámení na zamykací obrazovce.
    - **Typ výstrahy**: Když je zařízení odemknuté, vyberte, jak se má oznámení zobrazovat. Možnosti:
      - **Žádný**: Nezobrazuje se žádné oznámení.
      - **Banner**: Banner se krátce zobrazuje s oznámením.
      - **Modální okno**: Oznámení se zobrazí a uživatel je musí před pokračováním v používání zařízení zavřít ručně.
    - **Ikona označení v aplikaci**: Výběrem **Povolit** přidejte do ikony aplikace badge. BADGE znamená, že aplikace odeslala oznámení.
    - **Zvuky**: Vyberte **Povolit** pro přehrání zvuku při doručení oznámení.

## <a name="lock-screen-message"></a>Zpráva zamykací obrazovky

Tato funkce platí pro:

- iOS 9.3 nebo novější

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

- **Informace o inventárním štítku**: Zadejte informace o inventárním štítku zařízení. Zadejte například `Owned by Contoso Corp` nebo `Serial Number: {{serialnumber}}`.

  Text, který zadáte, se zobrazí v okně přihlášení a na zamykací obrazovce zařízení.

- **Poznámka pod čarou zamykací obrazovky**: Pokud dojde ke ztrátě nebo odcizení zařízení, zadejte poznámku, která by mohla získat informace o tom, jak zařízení vrátilo. Můžete zadat libovolný text, který chcete. Zadejte třeba `If found, call Contoso at ...`.

  Tokeny zařízení lze také použít k přidání informací o jednotlivých zařízeních do těchto polí. Chcete-li například zobrazit sériové číslo, zadejte `Serial Number: {{serialnumber}}`. Na zamykací obrazovce se text zobrazí jako podobný `Serial Number 123456789ABC`. Při zadávání proměnných nezapomeňte použít složené závorky `{{ }}`. [Tokeny konfigurace aplikace](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) obsahují seznam proměnných, které se dají použít. Můžete také použít `deviceName` nebo libovolná jiná hodnota specifická pro zařízení.

  > [!NOTE]
  > Proměnné nejsou v uživatelském rozhraní ověřeny a rozlišují se velká a malá písmena. V důsledku toho mohou být profily uloženy s nesprávným vstupem. Pokud například zadáte `{{DeviceID}}` `{{deviceid}}`místo, pak se místo jedinečného ID zařízení zobrazí literální řetězec. Nezapomeňte zadat správné informace.

## <a name="single-sign-on"></a>Jednotné přihlašování

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Nastavení platí pro: Registrace zařízení, automatický zápis zařízení (pod dohledem)

- **Atribut uživatelského jména z AAD**: Intune vyhledá tento atribut pro každého uživatele ve službě Azure AD. Před vygenerováním XML, který se na zařízení nainstaluje, Intune pak naplní příslušné pole (například hlavní název uživatele (UPN)). Možnosti:

  - **Hlavní název uživatele**: Hlavní název uživatele (UPN) se analyzuje následujícím způsobem:

    ![Atribut uživatelského jména](media/User-name-attribute.png)

    Sféru také můžete přepsat textem, který zadáte do textového pole **Sféra**.

    Například contoso má několik oblastí, včetně Evropy, Asie a Severní Amerika. Společnost Contoso chce, aby uživatelé v Asii používali jednotné přihlašování a aplikace vyžaduje hlavní `username@asia.contoso.com` název uživatele (UPN) ve formátu. Když vyberete **hlavní název uživatele**, vyřadí se sféra pro každého uživatele ze služby Azure AD, která `contoso.com`je. Takže pro uživatele v Asii vyberte **hlavní název uživatele**a zadejte `asia.contoso.com`. Hlavní název uživatele (UPN) `username@asia.contoso.com`koncového uživatele `username@contoso.com`bude místo.

  - **ID zařízení**v Intune: Intune automaticky vybere ID zařízení v Intune.

    Ve výchozím nastavení aplikace používají ID zařízení. Pokud ale vaše aplikace používá sféru a ID zařízení, můžete zadat sféru do textového pole sféra.

    > [!NOTE]
    > Implicitně platí, že pokud používáte ID zařízení, sféru nevyplňujte.

  - **ID zařízení Azure AD**

- **Sféra**: Zadejte část domény adresy URL. Zadejte například `contoso.com`.
- **Předpony adres URL, které použijí jednotné přihlašování**: **Přidejte** všechny adresy URL ve vaší organizaci, které vyžadují ověřování s jednotným přihlašováním uživatele.

  Například pokud se uživatel připojí k některému z těchto webů, použije zařízení s iOSem přihlašovací údaje pro jednotné přihlašování. Uživatel nemusí zadávat další přihlašovací údaje. Je-li povoleno ověřování Multi-Factor Authentication, je nutné, aby uživatel zadal druhé ověření.

  > [!NOTE]
  > V těchto adresách URL se musí používat správně naformátovaný plně kvalifikovaný název domény. Apple vyžaduje, aby byly ve `http://<yourURL.domain>` formátu.

  Odpovídající vzory adres URL musí mít na začátku `http://` nebo `https://`. Je spuštěna jednoduchá řetězcová shoda, takže se `http://www.contoso.com/` předpona adresy URL `http://www.contoso.com:80/`neshoduje. V systému iOS 10,0 nebo novějším je možné \* použít k zadání všech vyhovujících hodnot jeden zástupný znak. Například `http://*.contoso.com/` odpovídá`http://store.contoso.com/` a .`http://www.contoso.com`

  Vzory `http://.com` a`https://.com` odpovídají všem adresám URL protokolu HTTP a HTTPS, v uvedeném pořadí.

- **Aplikace, které budou používat jednotné přihlašování**: **Přidejte** aplikace do zařízení koncových uživatelů, která můžou používat jednotné přihlašování.

  `AppIdentifierMatches` Pole musí zahrnovat řetězce, které odpovídají ID sady prostředků aplikace. Tyto řetězce můžou být přesné shody, `com.contoso.myapp`jako je, nebo zadejte shodu předpony u ID sady prostředků \* pomocí zástupného znaku. Zástupný znak musí být uveden za znakem tečky (.) a může se objevit pouze jednou, na konci řetězce, například `com.contoso.*`. Při použití zástupného znaku se udělí přístup k účtu všem aplikacím, jejichž ID sady prostředků začíná příslušnou předponou.

  **Název aplikace** použijte k zadání popisného názvu, který pomůže při identifikaci ID sady prostředků.

- **Certifikát pro obnovení přihlašovacích údajů**: Pokud používáte certifikáty pro ověřování (nikoli hesla), vyberte jako ověřovací certifikát existující certifikát SCEP nebo PFX. Obvykle se jedná o stejný certifikát, který je nasazený pro uživatele pro jiné profily, jako je VPN, Wi-Fi nebo e-mail.

## <a name="web-content-filter"></a>Filtr webového obsahu

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

- **Typ filtru**: Vyberte, pokud chcete, aby byly povoleny konkrétní weby. Možnosti:

  - **Konfigurace adres URL**: Použijte integrovaný webový filtr společnosti Apple, který vyhledává pro dospělé výrazy, včetně vulgárních výrazů a sexuálního explicitního jazyka. Tato funkce vyhodnocuje každou webovou stránku jako načtenou a identifikuje a blokuje nevhodný obsah. Můžete také přidat adresy URL, které nechcete zkontrolovat pomocí filtru. Nebo zablokujte konkrétní adresy URL bez ohledu na nastavení filtru Apple.

    - **Povolené adresy URL**: **Přidejte** adresy URL, které chcete povolte. Tyto adresy URL obcházejí webový filtr společnosti Apple.

        > [!NOTE]
        > Adresy URL, které zadáte, jsou adresy URL, které nechcete evauluated webovým filtrem Apple. Tyto adresy URL nejsou seznamem povolených webů. Chcete-li vytvořit seznam povolených webů, nastavte **typ filtru** **pouze na konkrétní weby**.

    - **Blokované adresy URL**: **Přidejte** adresy URL, které chcete ukončit otevírání bez ohledu na nastavení webového filtru Apple.

  - **Pouze konkrétní weby** (jenom pro webový prohlížeč Safari): Tyto adresy URL se přidají do záložek prohlížeče Safari. Uživatel smí navštívit **jenom** tyto weby. žádné jiné weby nelze otevřít. Tuto možnost použijte jenom v případě, že znáte přesný seznam adres URL, ke kterým mají uživatelé přístup.

    - **ADRESA URL**: Zadejte adresu URL webu, který chcete udělit. Zadejte například `https://www.contoso.com`.
    - **Cesta**k záložek: Zadejte cestu pro uložení záložky. Zadejte například `/Contoso/Business Apps`. Pokud cestu nepřidáte, záložka se přidá do výchozí složky záložek na zařízení.
    - **Název**: Zadejte popisný název záložky.

    Pokud nezadáte žádné adresy URL, koncoví uživatelé nebudou mít přístup k žádným webům `microsoft.com`s `microsoft.net`výjimkou `apple.com`, a. Tyto adresy URL jsou automaticky povolené službou Intune.

## <a name="single-sign-on-app-extension"></a>Rozšíření aplikace s jednotným přihlašováním

Tato funkce platí pro:

- iOS 13,0 a novější
- iPadOS 13,0 a novější

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: Všechny typy registrace

- **Typ rozšíření aplikace jednotného přihlašování**: Vyberte typ rozšíření aplikace jednotného přihlašování. Možnosti:

  - Nenakonfigurováno: Rozšíření aplikací se nepoužívají. Pokud chcete zakázat rozšíření aplikace, můžete přepnout typ rozšíření aplikace jednotného přihlašování z **protokolu Kerberos** nebo **přihlašovacích údajů** na **Nenakonfigurováno**.
  - **Přihlašovací údaje**: K provedení jednotného přihlašování použijte obecné přizpůsobitelné rozšíření aplikace s přizpůsobitelnými přihlašovacími údaji. Ujistěte se, že znáte ID rozšíření pro rozšíření aplikace jednotného přihlašování ve vaší organizaci.
  - **Protokol Kerberos**: Použijte integrované rozšíření protokolu Kerberos společnosti Apple, které je součástí iOS 13,0 (a novějších) a iPadOS 13,0 (a novější). Tato možnost je verze rozšíření **přihlašovacích údajů** specifická pro Kerberos.

  > [!TIP]
  > Pomocí typu **přihlašovacích údajů** přidáte vlastní hodnoty konfigurace, které chcete předat prostřednictvím rozšíření. Místo toho zvažte použití předdefinovaného nastavení konfigurace poskytované společností Apple v typu **Kerberos** .

- **ID rozšíření** (Pouze přihlašovací údaje): Zadejte identifikátor sady prostředků, který identifikuje vaše rozšíření aplikace jednotného přihlašování `com.apple.extensiblesso`, například.
- **ID týmu** (Pouze přihlašovací údaje): Zadejte identifikátor týmu rozšíření aplikace jednotného přihlašování. Identifikátor týmu je alfanumerický řetězec (čísla a písmena), který vygenerovala společnost Apple, `ABCDE12345`jako je například. ID týmu se nevyžaduje.

  [Najít ID týmu](https://help.apple.com/developer-account/#/dev55c3c710c) (otevře se webová stránka společnosti Apple) obsahuje další informace.

- **Sféra**: Zadejte název sféry protokolu Kerberos. Název sféry by měl být velkými písmeny, `CONTOSO.COM`například. Název vaší sféry je typicky stejný jako název vaší domény DNS, ale jenom na velká písmena.

- **Domény**: Zadejte doménu nebo názvy hostitelů pro weby, které se dají ověřit pomocí jednotného přihlašování. Například pokud je `mysite.contoso.com`váš web, pak `mysite` je název hostitele a `contoso.com` je název domény. Když se uživatelé připojí k některé z těchto webů, aplikace App Extension zpracuje výzvu ověřování. Toto ověřování umožňuje uživatelům k přihlášení použít ID obličeje, dotykové ID nebo Apple PINCODE/přístupový kód.

  - Všechny domény v profilech služby Intune, které mají rozšíření pro aplikace jednotného přihlašování, musí být jedinečné. Doménu nemůžete opakovat v žádném profilu rozšíření aplikace pro přihlášení, i když používáte různé typy rozšíření aplikace jednotného přihlašování.
  - U těchto domén se nerozlišují velká a malá písmena.

- **Další konfigurace** (Pouze přihlašovací údaje): Zadejte další data specifická pro rozšíření, která chcete předat rozšíření aplikace jednotného přihlašování:
  - **Konfigurační klíč**: Zadejte název položky, kterou chcete přidat, například `user name`.
  - **Typ hodnoty**: Zadejte typ dat. Možnosti:

    - Řetězec
    - Datového Do **hodnoty konfigurace**zadejte `True` nebo `False`.
    - čísla Do **hodnoty konfigurace**zadejte číslo.
    
  - **Hodnota konfigurace**: Zadejte data.

  - **Přidat**: Tuto možnost vyberte, pokud chcete přidat konfigurační klíče.

- **Použití řetězce klíčů** (Jenom Kerberos): Vyberte možnost **blokovat** , pokud chcete zabránit ukládání a ukládání hesel do řetězce klíčů. **Není nakonfigurováno** (výchozí) umožňuje ukládat a ukládat hesla do řetězce klíčů.
- **ID obličeje, dotykové ID nebo heslo** (Jenom Kerberos): **Vyžadovat** , aby uživatelé zadali své ID obličeje, dotykové ID nebo Apple heslo pro přihlášení k doménám, které jste přidali. **Není nakonfigurováno** (výchozí) nevyžaduje, aby uživatelé používali biometrika nebo heslo pro přihlášení.
- **Výchozí sféra** (Jenom Kerberos): Zvolením možnosti **Povolit** nastavte hodnotu **sféry** , kterou jste zadali jako výchozí sféru. **Není nakonfigurováno** (výchozí) nenastavuje výchozí sféru.

  > [!TIP]
  > - Toto nastavení **Povolte** , pokud konfigurujete více rozšíření aplikace pro jednotné přihlašování pomocí protokolu Kerberos ve vaší organizaci.
  > - Toto nastavení **Povolte** , pokud používáte více sfér. Nastaví hodnotu **sféry** , kterou jste zadali jako výchozí sféru.
  > - Pokud máte pouze jednu sféru, ponechte ji **nenakonfigurovanou** (výchozí).

- **Hlavní název** (Jenom Kerberos): Zadejte uživatelské jméno objektu zabezpečení protokolu Kerberos. Nemusíte zahrnovat název sféry. Například v `user@contoso.com`, `user` je hlavní název a `contoso.com` je název sféry.
- **Kód lokality služby Active Directory** (Jenom Kerberos): Zadejte název lokality služby Active Directory, kterou má rozšíření protokolu Kerberos použít. Tuto hodnotu pravděpodobně nebudete muset měnit, protože rozšíření protokolu Kerberos může automaticky najít kód lokality služby Active Directory.
- **Název mezipaměti** (Jenom Kerberos): Zadejte název obecné služby zabezpečení (GSS) mezipaměti protokolu Kerberos. Tuto hodnotu pravděpodobně nemusíte nastavovat.
- **ID sady prostředků aplikace** (Jenom Kerberos): **Přidejte** identifikátory sady prostředků aplikace, které by měly používat jednotné přihlašování na vašich zařízeních. Těmto aplikacím je udělen přístup k lístku pro udělení lístku protokolu Kerberos, ověřovacímu lístku a ověřování uživatelů pro služby, kterým mají oprávnění k přístupu.
- **Mapování sféry domény** (Jenom Kerberos): **Přidejte** přípony DNS domény, které by měly být namapovány na vaši sféru. Toto nastavení použijte, pokud názvy DNS hostitelů neodpovídají názvu sféry. Pravděpodobně nemusíte vytvářet vlastní mapování domén na sféru.

## <a name="wallpaper"></a>Lock

Pokud se zařízením s existující imagí nepřiřazuje profil bez obrázku, může docházet k neočekávanému chování. Můžete například vytvořit profil bez obrázku. Tento profil je přiřazen k zařízením, která již mají bitovou kopii. V tomto scénáři se image může změnit na výchozí nastavení zařízení, jinak se v zařízení může zachovat původní image. Toto chování se řídí a je omezené platformou MDM od společnosti Apple.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: Automatický zápis zařízení (pod dohledem)

- **Umístění zobrazení tapety**: Vyberte umístění na zařízení pro zobrazení obrázku. Možnosti:
  - Nenakonfigurováno: Vlastní image se do zařízení nepřidá. Zařízení používá výchozí operační systém.
  - **Zamykací obrazovka**: Přidá obrázek na zamykací obrazovku.
  - **Domovská obrazovka**: Přidá obrázek na domovskou obrazovku.
  - **Zamykací obrazovka a Domovská obrazovka**: Použije stejný obrázek na zamykací obrazovce a na domovské obrazovce.
- **Obrázek tapety**: Nahrajte stávající obrázek. png,. jpg nebo. jpeg, který chcete použít. Ujistěte se, že velikost souboru je menší než 750 KB. Můžete také **Odebrat** obrázek, který jste přidali.

> [!TIP]
> Chcete-li zobrazit různé obrázky na zamykací obrazovce a na domovské obrazovce, vytvořte profil s obrázkem zamykací obrazovky. Vytvořte jiný profil s obrázkem na domovské obrazovce. Přiřaďte oba profily ke skupinám uživatelů nebo zařízení s iOS.

## <a name="next-steps"></a>Další kroky

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Můžete také vytvořit profily funkcí zařízení pro zařízení [MacOS](macos-device-features-settings.md) .
