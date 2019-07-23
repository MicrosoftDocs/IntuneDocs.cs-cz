---
title: nastavení funkcí zařízení s iOS v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na všechna nastavení a nakonfigurujte zařízení s iOS pro účely tisku, rozložení domovské obrazovky, oznámení aplikací, sdílené zařízení, jednotné přihlašování a nastavení filtru webového obsahu v Microsoft Intune. Pomocí těchto nastavení v profilu konfigurace zařízení můžete nakonfigurovat, aby zařízení s iOS používala tyto funkce Apple ve vaší organizaci.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/27/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bac591a625fd915056234a75b26bc2f90f50cae7
ms.sourcegitcommit: 8023ba7d42e61bd37305c69f52a649cf83bf72e2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2019
ms.locfileid: "68387110"
---
# <a name="ios-device-settings-to-use-common-ios-features-in-intune"></a>nastavení zařízení s iOS pro použití běžných funkcí iOS v Intune

Intune obsahuje některá vestavěná nastavení, která uživatelům iOS umožní používat na svých zařízeních jiné funkce společnosti Apple. Správci můžou například řídit, jak uživatelé iOS používají tiskárny pro průchozí tisk, přidávat aplikace a složky do Docku a stránky na domovské obrazovce, zobrazovat oznámení aplikací, zobrazit podrobnosti o značce assetu na zamykací obrazovce, používat ověřování pomocí jednotného přihlašování a ověřovat uživatele. s certifikáty.

Pomocí těchto funkcí můžete ovládat zařízení iOS jako součást řešení správy mobilních zařízení (MDM).

Tento článek uvádí tato nastavení a popisuje, co jednotlivé nastavení dělá.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte konfigurační profil zařízení s iOS](device-features-configure.md#create-a-device-profile).

## <a name="airprint"></a>AirPrint

- **IP adresa**: Zadejte adresu protokolu IPv4 nebo IPv6 tiskárny. Pokud k identifikaci tiskáren používáte názvy hostitelů, můžete získat IP adresu tím, že v terminálu otestujete tiskárnu. Další podrobnosti najdete v článku získání IP adresy a cesty (v tomto článku).
- **Cesta**: Cesta je typicky `ipp/print` pro tiskárny v síti. Další podrobnosti najdete v článku získání IP adresy a cesty (v tomto článku).
- **Port**: Zadejte port naslouchání cíle přenosu. Pokud necháte tuto vlastnost prázdnou, použije se při tisku výchozí port. K dispozici v iOS 11,0 a novějších verzích.
- **TLS**: Vyberte **Povolit** a zabezpečte připojení přes tisk přes protokol TLS (Transport Layer Security). K dispozici v iOS 11,0 a novějších verzích.

**Přidání** přidá do seznamu přidat server pro příjem. Je možné přidat spoustu tiskových serverů. Pomocí těchto informací můžete také **importovat** textový soubor s oddělovači (. csv). Při **exportu** se vytvoří seznam tiskových serverů, které jste přidali.

Vyberte **OK** a seznam uložte.

### <a name="get-server-ip-address-resource-path-and-port"></a>Získat IP adresu serveru, cestu prostředku a port

Chcete-li přidat servery s modulem pro tisk, budete potřebovat IP adresu tiskárny, cestu k prostředku a port. Následující kroky ukazují, jak tyto informace získat.

1. Na Macu, který je připojený ke stejné místní síti (podsíti) jako tiskárny pro Protisk, otevřete **terminál** (z **/aplikace/Utility**).
2. V terminálu zadejte `ippfind`a vyberte Enter.

    Poznamenejte si informace o tiskárně. Například může vracet něco podobného jako `ipp://myprinter.local.:631/ipp/port1`. První část je název tiskárny. Poslední část (`ipp/port1`) je cesta prostředku.

3. V terminálu zadejte `ping myprinter.local`a vyberte Enter.

   Poznamenejte si IP adresu. Například může vracet něco podobného jako `PING myprinter.local (10.50.25.21)`.

4. Použijte hodnoty IP adresy a prostředku cesty. V tomto příkladu je IP adresa `10.50.25.21`a `/ipp/port1`cesta k prostředku.

## <a name="home-screen-layout-settings"></a>Nastavení rozložení domovské obrazovky

Tato nastavení konfigurují rozložení a složky aplikace v Dock a na domovské obrazovce zařízení s iOS. Aby bylo možné tuto funkci používat, musí být zařízení s iOS v režimu pod dohledem a musí používat iOS 9,3 nebo novější.

### <a name="dock"></a>Vyjměte

Pomocí nastavení **Dock** přidejte až šest položek nebo složek do Docku obrazovky iOS. Mnoho zařízení podporuje méně položek. Například zařízení iPhone podporují až čtyři položky. V takovém případě se na zařízení zobrazí jenom první čtyři položky, které přidáte.

Pro Dock zařízení můžete přidat až **šest** položek (kombinované aplikace a složky).

- **Přidat**: Přidá aplikace nebo složky do Docku na zařízení.
- **Zadejte**: Přidat **aplikaci** nebo **složku**:

  - **Aplikace**: Tuto možnost vyberte, pokud chcete přidat aplikace do Docku na obrazovce. Napište

    - **Název aplikace**: Zadejte název aplikace. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
    - **ID sady prostředků aplikace**: Zadejte ID sady prostředků aplikace. Některé příklady najdete v tématu [ID sad pro integrované aplikace pro iOS](bundle-ids-built-in-ios-apps.md) .

    Vyberte **OK** uložte provedené změny.

  - **Složka**: Tuto možnost vyberte, pokud chcete přidat složku do Docku na obrazovce.

    Aplikace, které přidáte na stránku ve složce, jsou seřazené zleva doprava a ve stejném pořadí jako seznam. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se aplikace na jinou stránku.

    - **Název složky**: Zadejte název složky. Tento název se zobrazí uživatelům na svém zařízení.
    - **Seznam stránek**: **Přidejte** stránku a zadejte následující vlastnosti:

      - **Název stránky**: Zadejte název stránky. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
      - **Název aplikace**: Zadejte název aplikace. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
      - **ID sady prostředků aplikace**: Zadejte ID sady prostředků aplikace. Některé příklady najdete v tématu [ID sad pro integrované aplikace pro iOS](bundle-ids-built-in-ios-apps.md) .

      Pro Dock zařízení můžete přidat až **20** stránek.

    Vyberte **OK** uložte provedené změny.

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

      Vyberte **OK** uložte provedené změny.

      - **Složka**: Tuto možnost vyberte, pokud chcete přidat složku do Docku na obrazovce.

        Aplikace, které přidáte na stránku ve složce, jsou seřazené zleva doprava a ve stejném pořadí jako seznam. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se aplikace na jinou stránku.

        - **Název složky**: Zadejte název složky. Tento název se zobrazí uživatelům na zařízení.
        - **Přidat**: Přidá stránky do složky. Zadejte také následující vlastnosti:

          - **Název stránky**: Zadejte název stránky. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
          - **Název aplikace**: Zadejte název aplikace. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
          - **ID sady prostředků aplikace**: Zadejte ID sady prostředků aplikace. Některé příklady najdete v tématu [ID sad pro integrované aplikace pro iOS](bundle-ids-built-in-ios-apps.md) .

      Vyberte **OK** uložte provedené změny.

#### <a name="example"></a>Příklad

V následujícím příkladu je přidána nová stránka s názvem **Contoso** . Na stránce se zobrazí aplikace najít přátele a nastavení. Vybraná aplikace nastavení zobrazuje vlastnosti:

![Příklad nastavení domovské obrazovky iOSu](./media/Jc2OxyX.png)

Když přiřadíte zásady k iPhonu, stránka bude vypadat podobně jako na následujícím obrázku:

![Zařízení s iOSem se změněnou domovskou obrazovkou](./media/Bd37PHa.png)

## <a name="app-notifications-settings"></a>Nastavení oznámení aplikací

Vyberte, jak nainstalovaná aplikace na zařízeních s iOS odesílají oznámení. Tato nastavení podporují zařízení pod dohledem s iOSem 9.3 a novějším.

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

Vyberte **OK** uložte provedené změny.

## <a name="lock-screen-message-settings"></a>Nastavení zprávy zamykací obrazovky

Pomocí těchto nastavení můžete zobrazit vlastní zprávu nebo text v přihlašovacím okně a na zamykací obrazovce. Můžete například zadat "Pokud došlo ke ztrátě, vrátit se do..." informace o zprávě a inventární značce. 

Tato funkce podporuje zařízení pod dohledem se systémem iOS 9,3 a novějším.

- **Informace o inventárním štítku**: Zadejte informace o inventárním štítku zařízení. Zadejte například `Owned by Contoso Corp` nebo `Serial Number: {{serialnumber}}`.

  Text, který zadáte, se zobrazí v okně přihlášení a na zamykací obrazovce zařízení.

- **Poznámka pod čarou zamykací obrazovky**: Pokud dojde ke ztrátě nebo odcizení zařízení, zadejte poznámku, která by mohla získat informace o tom, jak zařízení vrátilo. Můžete zadat libovolný text, který chcete. Zadejte třeba `If found, call Contoso at ...`.

  Tokeny zařízení lze také použít k přidání informací o jednotlivých zařízeních do těchto polí. Chcete-li například zobrazit sériové číslo, zadejte `Serial Number: {{serialnumber}}`. Na zamykací obrazovce se text zobrazí jako podobný `Serial Number 123456789ABC`. Při zadávání proměnných nezapomeňte použít složené závorky `{{ }}`. [Tokeny konfigurace aplikace](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) obsahují seznam proměnných, které se dají použít. Můžete také použít `deviceName` nebo libovolná jiná hodnota specifická pro zařízení.

  > [!NOTE]
  > Proměnné nejsou v uživatelském rozhraní ověřeny a rozlišují se velká a malá písmena. V důsledku toho mohou být profily uloženy s nesprávným vstupem. Pokud například zadáte `{{DeviceID}}` `{{deviceid}}`místo, pak se místo jedinečného ID zařízení zobrazí literální řetězec. Nezapomeňte zadat správné informace.

Vyberte **OK** uložte provedené změny.

## <a name="single-sign-on-settings"></a>Nastavení jednotného přihlašování

Většina obchodních aplikací vyžaduje z důvodu zabezpečení určitou úroveň ověřování uživatelů. V mnoha případech ověřování vyžaduje, aby uživatel zadal stejné přihlašovací údaje opakovaně, což je frustrující pro uživatele. Pro zlepšení uživatelského prostředí můžou vývojáři vytvářet aplikace, které používají jednotné přihlašování (SSO). Použití jednotného přihlašování omezuje počet, kolikrát musí uživatel zadat přihlašovací údaje.

Pokud chcete použít jednotné přihlašování, ujistěte se, že máte:

- Aplikace, která je kódována tak, aby hledala úložiště přihlašovacích údajů uživatele v rámci jednotného přihlašování na zařízení.
- Nakonfigurování Intune na jednotné přihlašování pro zařízení s iOSem

![Podokno Jednotné přihlašování](./media/sso-blade.png)

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

Vyberte **OK** uložte provedené změny.

## <a name="web-content-filter-settings"></a>Nastavení filtru webového obsahu

Tato nastavení řídí přístup k adrese URL prohlížeče na zařízeních s iOS pod dohledem.

- **Typ filtru**: Vyberte, pokud chcete, aby byly povoleny konkrétní weby. Možnosti:

  - **Konfigurace adres URL**: Použijte integrovaný webový filtr společnosti Apple, který vyhledává pro dospělé výrazy, včetně vulgárních výrazů a sexuálního explicitního jazyka. Tato funkce vyhodnocuje každou webovou stránku jako načtenou a identifikuje a blokuje nevhodný obsah. Můžete také přidat adresy URL, které nechcete zkontrolovat pomocí filtru. Nebo zablokujte konkrétní adresy URL bez ohledu na nastavení filtru Apple.

    - **Povolené adresy URL**: **Přidejte** adresy URL, které chcete povolte. Tyto adresy URL obcházejí webový filtr společnosti Apple.

      > [!NOTE]
        > Adresy URL, které zadáte, jsou adresy URL, které nechcete evauluated webovým filtrem Apple. Tyto adresy URL nejsou seznamem povolených webů. Chcete-li vytvořit seznam povolených webů, nastavte **typ filtru** **pouze na konkrétní weby**.

      Vyberte **OK** uložte provedené změny.

    - **Blokované adresy URL**: **Přidejte** adresy URL, které chcete ukončit otevírání bez ohledu na nastavení webového filtru Apple.

      Vyberte **OK** uložte provedené změny.

  - **Pouze konkrétní weby** (jenom pro webový prohlížeč Safari): Tyto adresy URL se přidají do záložek prohlížeče Safari. Uživatel smí navštívit **jenom** tyto weby. žádné jiné weby nelze otevřít. Tuto možnost použijte jenom v případě, že znáte přesný seznam adres URL, ke kterým mají uživatelé přístup.

    - **ADRESA URL**: Zadejte adresu URL webu, který chcete udělit. Zadejte například `https://www.contoso.com`.
    - **Cesta**k záložek: Zadejte cestu pro uložení záložky. Zadejte například `/Contoso/Business Apps`. Pokud cestu nepřidáte, záložka se přidá do výchozí složky záložek na zařízení.
    - **Název**: Zadejte popisný název záložky.

    Pokud nezadáte žádné adresy URL, koncoví uživatelé nebudou mít přístup k žádným webům `microsoft.com`s `microsoft.net`výjimkou `apple.com`, a. Tyto adresy URL jsou automaticky povolené službou Intune.

    Vyberte **OK** uložte provedené změny.

## <a name="wallpaper-settings"></a>Nastavení tapety

Přidejte vlastní obrázek. png,. jpg nebo. jpeg do zařízení se systémem iOS pod dohledem. Můžete například použít logo společnosti na zamykací obrazovce.

Pokud se zařízením s existující imagí nepřiřazuje profil bez obrázku, může docházet k neočekávanému chování. Můžete například vytvořit profil bez obrázku. Tento profil je přiřazen k zařízením, která již mají bitovou kopii. V tomto scénáři se image může změnit na výchozí nastavení zařízení, jinak se v zařízení může zachovat původní image. Toto chování se řídí a je omezené platformou MDM od společnosti Apple.

- **Umístění zobrazení tapety**: Vyberte umístění na zařízení pro zobrazení obrázku. Možnosti:
  - Nenakonfigurováno: Vlastní image se do zařízení nepřidá. Zařízení používá výchozí operační systém.
  - **Zamykací obrazovka**: Přidá obrázek na zamykací obrazovku.
  - **Domovská obrazovka**: Přidá obrázek na domovskou obrazovku.
  - **Zamykací obrazovka a Domovská obrazovka**: Použije stejný obrázek na zamykací obrazovce a na domovské obrazovce.
- **Obrázek tapety**: Nahrajte stávající obrázek. png,. jpg nebo. jpeg, který chcete použít. Ujistěte se, že velikost souboru je menší než 750 KB. Můžete také **Odebrat** obrázek, který jste přidali.

> [!TIP]
> Chcete-li zobrazit různé obrázky na zamykací obrazovce a na domovské obrazovce, vytvořte profil s obrázkem zamykací obrazovky. Vytvořte jiný profil s obrázkem na domovské obrazovce. Přiřaďte oba profily ke skupinám uživatelů nebo zařízení s iOS.

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Můžete také vytvořit profily funkcí zařízení pro zařízení [MacOS](macos-device-features-settings.md) .
