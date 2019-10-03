---
title: nastavení funkcí zařízení s iOS v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na všechna nastavení a nakonfigurujte zařízení s iOS pro účely tisku, rozložení domovské obrazovky, oznámení aplikací, sdílené zařízení, jednotné přihlašování a nastavení filtru webového obsahu v Microsoft Intune. Pomocí těchto nastavení v profilu konfigurace zařízení můžete nakonfigurovat, aby zařízení s iOS používala tyto funkce Apple ve vaší organizaci.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b8cd38174b9332f285e0dc4f938d99dbd5aecf74
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816890"
---
# <a name="ios-and-ipados-device-settings-to-use-common-ios-features-in-intune"></a>nastavení zařízení s iOS a iPadOS pro použití běžných funkcí iOS v Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune obsahuje některá vestavěná nastavení, která uživatelům iOS umožní používat na svých zařízeních jiné funkce společnosti Apple. Správci můžou například řídit, jak uživatelé iOS používají tiskárny pro průchozí tisk, přidávat aplikace a složky do Docku a stránky na domovské obrazovce, zobrazovat oznámení aplikací, zobrazit podrobnosti o značce assetu na zamykací obrazovce, používat ověřování pomocí jednotného přihlašování a ověřovat uživatele. s certifikáty.

Pomocí těchto funkcí můžete ovládat zařízení iOS jako součást řešení správy mobilních zařízení (MDM).

Tento článek uvádí tato nastavení a popisuje, co jednotlivé nastavení dělá. Další informace o těchto funkcích najdete v [Přidání nastavení funkcí zařízení se systémem iOS nebo MacOS](../device-features-configure.md).

## <a name="before-you-begin"></a>Než začnete

[Vytvořte konfigurační profil zařízení s iOS](../device-features-configure.md).

> [!NOTE]
> Tato nastavení platí pro různé typy registrace s některými nastaveními, která platí pro všechny možnosti registrace. Další informace o různých typech registrace najdete v tématu Registrace zařízení se [systémem iOS](../ios-enroll.md).

## <a name="airprint"></a>AirPrint

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: všechny typy registrace

- **IP adresa**: zadejte adresu IPv4 nebo IPv6 tiskárny. Pokud k identifikaci tiskáren používáte názvy hostitelů, můžete získat IP adresu tím, že v terminálu otestujete tiskárnu. Další podrobnosti najdete v článku získání IP adresy a cesty (v tomto článku).
- **Cesta**: cesta je obvykle `ipp/print` pro tiskárny v síti. Další podrobnosti najdete v článku získání IP adresy a cesty (v tomto článku).
- **Port**: zadejte port naslouchání cíle přenosu. Pokud necháte tuto vlastnost prázdnou, použije se při tisku výchozí port. K dispozici v iOS 11,0 a novějších verzích.
- **TLS**: vyberte **Povolit** a zabezpečte připojení přes tisk přes protokol TLS (Transport Layer Security). K dispozici v iOS 11,0 a novějších verzích.

Pokud chcete přidat servery pro tisk přes mosty, můžete:

- **Přidání** přidá do seznamu přidat server pro příjem. Je možné přidat spoustu tiskových serverů.
- **Importujte** textový soubor s oddělovači (. csv) s těmito informacemi. Případně můžete **exportovat** a vytvořit tak seznam serverů pro tisk do, které jste přidali.

### <a name="get-server-ip-address-resource-path-and-port"></a>Získat IP adresu serveru, cestu prostředku a port

Chcete-li přidat servery s modulem pro tisk, budete potřebovat IP adresu tiskárny, cestu k prostředku a port. Následující kroky ukazují, jak tyto informace získat.

1. Na Macu, který je připojený ke stejné místní síti (podsíti) jako tiskárny pro Protisk, otevřete **terminál** (z **/aplikace/Utility**).
2. Do terminálu zadejte `ippfind` a vyberte Enter.

    Poznamenejte si informace o tiskárně. Například může vracet něco podobného jako `ipp://myprinter.local.:631/ipp/port1`. První část je název tiskárny. Poslední část (`ipp/port1`) je cesta prostředku.

3. Do terminálu zadejte `ping myprinter.local` a vyberte Enter.

   Poznamenejte si IP adresu. Například může vracet něco podobného jako `PING myprinter.local (10.50.25.21)`.

4. Použijte hodnoty IP adresy a prostředku cesty. V tomto příkladu je IP adresa `10.50.25.21` a cesta k prostředku je `/ipp/port1`.

## <a name="home-screen-layout"></a>Rozložení domovské obrazovky

Tato funkce se týká:

- iOS 9,3 nebo novější

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: automatický zápis zařízení (pod dohledem)

### <a name="dock"></a>Vyjměte

Pomocí nastavení **Dock** přidejte až šest položek nebo složek do Docku obrazovky iOS. Mnoho zařízení podporuje méně položek. Například zařízení iPhone podporují až čtyři položky. V takovém případě se na zařízení zobrazí jenom první čtyři položky, které přidáte.

Pro Dock zařízení můžete přidat až **šest** položek (kombinované aplikace a složky).

- **Přidat**: přidá aplikace nebo složky do Docku na zařízení.
- **Zadejte**: přidat **aplikaci** nebo **složku**:

  - **Aplikace**: tuto možnost vyberte, pokud chcete přidat aplikace do Dock na obrazovce. Napište

    - **Název aplikace**: zadejte název aplikace. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
    - **ID sady prostředků aplikace**: Zadejte ID sady prostředků aplikace. Některé příklady najdete v tématu [ID sad pro integrované aplikace pro iOS](bundle-ids-built-in-ios-apps.md) .

  - **Složka**: tuto možnost vyberte, pokud chcete přidat složku do Docku na obrazovce.

    Aplikace, které přidáte na stránku ve složce, jsou seřazené zleva doprava a ve stejném pořadí jako seznam. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se aplikace na jinou stránku.

    - **Název složky**: zadejte název složky. Tento název se zobrazí uživatelům na svém zařízení.
    - **Seznam stránek**: **přidejte** stránku a zadejte následující vlastnosti:

      - **Název stránky**: zadejte název stránky. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
      - **Název aplikace**: zadejte název aplikace. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
      - **ID sady prostředků aplikace**: Zadejte ID sady prostředků aplikace. Některé příklady najdete v tématu [ID sad pro integrované aplikace pro iOS](bundle-ids-built-in-ios-apps.md) .

      Pro Dock zařízení můžete přidat až **20** stránek.

> [!NOTE]
> Když přidáváte ikony pomocí nastavení Dock, ikony na domovské obrazovce a stránkách jsou zamčené a nejde je přesunout. To může být záměrné pomocí zásad MDM a iOS pro iOS a Apple.

#### <a name="example"></a>Příklad:

V následujícím příkladu se zobrazí docká obrazovka jenom aplikace Safari, pošta a akcie. Aplikace Pošta je vybrána k zobrazení vlastností:

![Ukázka nastavení Dock Dock pro iOS](./media/ios-device-features-settings/FfFiUcP.png)

Když přiřadíte zásady k iPhonu, bude Dock vypadat podobně jako na následujícím obrázku:

![Ukázka rozložení Dock pro iOS na iPhonu](./media/ios-device-features-settings/bAgCe8F.png)

### <a name="pages"></a>Stránky

Přidejte stránky, které chcete zobrazit na domovské obrazovce, a aplikace, které chcete zobrazit na jednotlivých stránkách. Aplikace, které přidáte na stránku, jsou seřazené zleva doprava ve stejném pořadí jako seznam. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se aplikace na jinou stránku.

> [!TIP]
> Chcete-li změnit pořadí položek v seznamech na domovské obrazovce a na stránkách, můžete je přetáhnout.

Na zařízení můžete přidat až **40** stránek.

- **Seznam stránek**: **přidejte** stránku a zadejte následující vlastnosti:

  - **Název stránky**: zadejte název stránky. Tento název se používá pro váš odkaz v Azure Portal a *není* zobrazený na zařízení s iOS.

  Do zařízení můžete přidat až **60** položek (sloučené aplikace a složky).

  - **Přidat**: přidá aplikace nebo složky na stránku na zařízení.

    - **Zadejte**: přidat **aplikaci** nebo **složku**:

      - **Aplikace**: tuto možnost vyberte, pokud chcete přidat aplikace na stránku na obrazovce. Zadejte také:

        - **Název aplikace**: zadejte název aplikace. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
        - **ID sady prostředků aplikace**: Zadejte ID sady prostředků aplikace. Některé příklady najdete v tématu [ID sad pro integrované aplikace pro iOS](bundle-ids-built-in-ios-apps.md) .

      - **Složka**: tuto možnost vyberte, pokud chcete přidat složku do Docku na obrazovce.

        Aplikace, které přidáte na stránku ve složce, jsou seřazené zleva doprava a ve stejném pořadí jako seznam. Pokud přidáte více aplikací, než se vejde na stránku, přesunou se aplikace na jinou stránku.

        - **Název složky**: zadejte název složky. Tento název se zobrazí uživatelům na zařízení.
        - **Přidat**: přidá stránky do složky. Zadejte také následující vlastnosti:

          - **Název stránky**: zadejte název stránky. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
          - **Název aplikace**: zadejte název aplikace. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení s iOS.
          - **ID sady prostředků aplikace**: Zadejte ID sady prostředků aplikace. Některé příklady najdete v tématu [ID sad pro integrované aplikace pro iOS](bundle-ids-built-in-ios-apps.md) .

#### <a name="example"></a>Příklad:

V následujícím příkladu je přidána nová stránka s názvem **Contoso** . Na stránce se zobrazí aplikace najít přátele a nastavení. Vybraná aplikace nastavení zobrazuje vlastnosti:

![Příklad nastavení domovské obrazovky pro iOS](./media/ios-device-features-settings/Jc2OxyX.png)

Když přiřadíte zásady k iPhonu, stránka bude vypadat podobně jako na následujícím obrázku:

![zařízení s iOS s upravenou domovskou obrazovkou](./media/ios-device-features-settings/Bd37PHa.png)

## <a name="app-notifications"></a>Oznámení aplikací

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: automatický zápis zařízení (pod dohledem)

- **Přidat**: Přidat oznámení pro aplikace:

    ![Přidání oznámení aplikace v profilu iOS v Intune](./media/ios-device-features-settings/ios-macos-app-notifications.png)

  - **ID sady prostředků aplikace**: zadejte **ID sady prostředků** aplikace, kterou chcete přidat. Některé příklady najdete v tématu [ID sad pro integrované aplikace pro iOS](bundle-ids-built-in-ios-apps.md) .
  - **Název aplikace**: zadejte název aplikace, kterou chcete přidat. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení.
  - **Vydavatel**: zadejte vydavatele aplikace, kterou přidáváte. Tento název se používá pro váš odkaz v Azure Portal. Nezobrazuje *se* na zařízení.
  - **Oznámení**: **povolí** nebo **zakáže** aplikaci odesílat oznámení do zařízení.
    - **Zobrazit v centru oznámení**: **Povolit** aplikaci umožní zobrazovat oznámení v centru oznámení zařízení. **Disable** zabrání aplikaci v zobrazování oznámení v centru oznámení.
    - **Zobrazit na zamykací obrazovce**: výběrem **Povolit** zobrazíte oznámení z aplikace na zamykací obrazovce zařízení. **Disable** zabrání aplikaci zobrazovat oznámení na zamykací obrazovce.
    - **Typ výstrahy**: když se zařízení odemkne, vyberte, jak se má oznámení zobrazit. Vaše možnosti:
      - **Žádné**: nezobrazuje se žádné oznámení.
      - **Banner**: krátce se zobrazí zpráva s oznámením.
      - **Modální**: zobrazí se oznámení a uživatel ho musí před pokračováním v používání tohoto zařízení zavřít ručně.
    - Ikona příznaku **u aplikace**: výběrem **Povolit** přidejte do ikony aplikace badge. BADGE znamená, že aplikace odeslala oznámení.
    - **Zvuky**: výběrem **Povolit zapnete** zvuk, když se doručí oznámení.

## <a name="lock-screen-message"></a>Zpráva zamykací obrazovky

Tato funkce se týká:

- iOS 9,3 a novější

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: automatický zápis zařízení (pod dohledem)

- Informace o inventárním **štítku**: zadejte informace o inventárním štítku zařízení. Zadejte například `Owned by Contoso Corp` nebo `Serial Number: {{serialnumber}}`.

  Text, který zadáte, se zobrazí v okně přihlášení a na zamykací obrazovce zařízení.

- **Poznámka pod čarou na zamykací obrazovce**: Pokud dojde ke ztrátě nebo odcizení zařízení, zadejte poznámku, která může přispět k vrácení zařízení zpět. Můžete zadat libovolný text, který chcete. Například zadejte něco jako `If found, call Contoso at ...`.

  Tokeny zařízení lze také použít k přidání informací o jednotlivých zařízeních do těchto polí. Pokud například chcete zobrazit sériové číslo, zadejte `Serial Number: {{serialnumber}}`. Na zamykací obrazovce se text zobrazuje podobně jako `Serial Number 123456789ABC`. Při zadávání proměnných nezapomeňte použít složené závorky `{{ }}`. [Tokeny konfigurace aplikace](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) obsahují seznam proměnných, které se dají použít. Můžete také použít `deviceName` nebo jiná hodnota specifická pro zařízení.

  > [!NOTE]
  > Proměnné nejsou v uživatelském rozhraní ověřeny a rozlišují se velká a malá písmena. V důsledku toho mohou být profily uloženy s nesprávným vstupem. Pokud například zadáte `{{DeviceID}}` namísto `{{deviceid}}`, pak se místo jedinečného ID zařízení zobrazí literální řetězec. Nezapomeňte zadat správné informace.

## <a name="single-sign-on"></a>Jednotné přihlašování

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Nastavení platí pro: registrace zařízení, automatický zápis zařízení (pod dohledem)

- **Atribut uživatelského jména z AAD**: Intune vyhledá tento atribut pro každého uživatele ve službě Azure AD. Před vygenerováním XML, který se na zařízení nainstaluje, Intune pak naplní příslušné pole (například hlavní název uživatele (UPN)). Vaše možnosti:

  - **Hlavní název uživatele**: hlavní název uživatele (UPN) se analyzuje následujícím způsobem:

    ![Atribut UserName](./media/ios-device-features-settings/User-name-attribute.png)

    Sféru můžete také přepsat textem, který zadáte do textového pole **sféra** .

    Například contoso má několik oblastí, včetně Evropy, Asie a Severní Amerika. Společnost Contoso chce, aby uživatelé Asie používali jednotné přihlašování a aplikace vyžaduje hlavní název uživatele (UPN) ve formátu `username@asia.contoso.com`. Když vyberete **hlavní název uživatele**, vyřadí se sféra pro každého uživatele z Azure AD, což je `contoso.com`. Takže pro uživatele v Asii vyberte **hlavní název uživatele**a zadejte `asia.contoso.com`. Hlavní název uživatele (UPN) koncového uživatele se `username@asia.contoso.com` místo `username@contoso.com`.

  - **ID zařízení v Intune**: Intune automaticky vybere ID zařízení v Intune.

    Ve výchozím nastavení aplikace potřebují používat jenom ID zařízení. Pokud ale vaše aplikace používá sféru a ID zařízení, můžete zadat sféru do textového pole sféra.

    > [!NOTE]
    > Ve výchozím nastavení ponechejte sféru prázdnou, pokud použijete ID zařízení.

  - **ID zařízení Azure AD**

- **Sféra**: zadejte část domény adresy URL. Zadejte například `contoso.com`.
- **Předpony adres URL, které budou používat jednotné přihlašování**: **přidejte** všechny adresy URL ve vaší organizaci, které vyžadují ověřování pomocí jednotného přihlašování uživatele.

  Když se například uživatel připojí k některé z těchto webů, zařízení s iOS používá přihlašovací údaje jednotného přihlašování. Uživatel nemusí zadávat žádné další přihlašovací údaje. Je-li povoleno ověřování Multi-Factor Authentication, je nutné, aby uživatel zadal druhé ověření.

  > [!NOTE]
  > Tyto adresy URL musí mít správně formátovaný plně kvalifikovaný název domény. Apple vyžaduje, aby byly ve formátu `http://<yourURL.domain>`.

  Vzorová adresa URL musí začínat buď `http://`, nebo `https://`. Je spuštěna jednoduchá řetězcová shoda, takže předpona adresy URL `http://www.contoso.com/` neodpovídá `http://www.contoso.com:80/`. V systému iOS 10,0 nebo novějším se dá k zadání všech vyhovujících hodnot použít jeden zástupný znak \*. Například `http://*.contoso.com/` odpovídá `http://store.contoso.com/` a `http://www.contoso.com`.

  Vzory `http://.com` a `https://.com` odpovídají všem adresám URL protokolu HTTP a HTTPS v uvedeném pořadí.

- **Aplikace, které budou používat jednotné přihlašování**: **Přidat** aplikace na zařízení koncových uživatelů, která můžou používat jednotné přihlašování

  Pole `AppIdentifierMatches` musí zahrnovat řetězce, které odpovídají identifikátorům ID sady prostředků aplikace. Tyto řetězce můžou být přesné shody, například `com.contoso.myapp`, nebo zadat shodu předpony u ID sady prostředků pomocí zástupného znaku \*. Zástupný znak musí být uveden za znakem tečky (.) a může se objevit pouze jednou, na konci řetězce, například `com.contoso.*`. Pokud je zahrnut zástupný znak, získá přístup k účtu všechny aplikace, jejichž ID sady začíná předponou.

  Pomocí **názvu aplikace** můžete zadat uživatelsky přívětivý název, který vám usnadní identifikaci ID sady prostředků.

- **Certifikát pro obnovení přihlašovacích údajů**: Pokud používáte certifikáty pro ověřování (ne hesla), vyberte jako ověřovací certifikát stávající certifikát SCEP nebo PFX. Obvykle se jedná o stejný certifikát, který je nasazený pro uživatele pro jiné profily, jako je VPN, Wi-Fi nebo e-mail.

## <a name="web-content-filter"></a>Filtr webového obsahu

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: automatický zápis zařízení (pod dohledem)

- **Typ filtru**: tuto možnost vyberte, pokud chcete určit konkrétní weby. Vaše možnosti:

  - **Konfigurace adres URL**: použijte integrovaný webový filtr společnosti Apple, který hledá výrazy pro dospělé, včetně vulgárních výrazů a sexuálního explicitního jazyka. Tato funkce vyhodnocuje každou webovou stránku jako načtenou a identifikuje a blokuje nevhodný obsah. Můžete také přidat adresy URL, které nechcete zkontrolovat pomocí filtru. Nebo zablokujte konkrétní adresy URL bez ohledu na nastavení filtru Apple.

    - **Povolené adresy URL**: **přidejte** adresy URL, které chcete povolit. Tyto adresy URL obcházejí webový filtr společnosti Apple.

        > [!NOTE]
        > Adresy URL, které zadáte, jsou adresy URL, které nechcete evauluated webovým filtrem Apple. Tyto adresy URL nejsou seznamem povolených webů. Chcete-li vytvořit seznam povolených webů, nastavte **typ filtru** **pouze na konkrétní weby**.

    - **Blokované adresy URL**: **přidejte** adresy URL, které chcete ukončit otevírání bez ohledu na nastavení webového filtru Apple.

  - **Jenom konkrétní weby** (jenom pro webový prohlížeč Safari): tyto adresy URL se přidají do záložek prohlížeče Safari. Uživatel smí navštívit **jenom** tyto weby. žádné jiné weby nelze otevřít. Tuto možnost použijte pouze v případě, že znáte přesný seznam adres URL, ke kterým mají uživatelé přístup.

    - **Adresa URL**: zadejte adresu URL webu, který chcete udělit. Zadejte například `https://www.contoso.com`.
    - **Cesta k záložek**: zadejte cestu k uložení záložky. Zadejte například `/Contoso/Business Apps`. Pokud cestu nepřidáte, záložka se přidá do výchozí složky záložek na zařízení.
    - **Title**: zadejte popisný název záložky.

    Pokud nezadáte žádné adresy URL, koncoví uživatelé nebudou mít přístup k žádným webům kromě `microsoft.com`, `microsoft.net` a `apple.com`. Tyto adresy URL jsou automaticky povolené službou Intune.

## <a name="single-sign-on-app-extension"></a>Rozšíření aplikace s jednotným přihlašováním

Tato funkce se týká:

- iOS 13,0 a novější
- iPadOS 13,0 a novější

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: všechny typy registrace

- **Typ rozšíření aplikace jednotného přihlašování**: Vyberte typ rozšíření aplikace jednotného přihlašování. Když uložíte profil rozšíření aplikace jednotného přihlašování, nemůžete změnit typ rozšíření aplikace jednotného přihlašování. Vaše možnosti:

  - **Nenakonfigurováno**: rozšíření aplikací se nepoužívají. Pokud chcete zakázat rozšíření aplikace, můžete přepnout typ rozšíření aplikace jednotného přihlašování z **protokolu Kerberos** nebo **přihlašovacích údajů** na **Nenakonfigurováno**.
  - **Pověření**: k provedení jednotného přihlašování použijte obecné přizpůsobitelné rozšíření aplikace s přizpůsobenými přihlašovacími údaji. Ujistěte se, že znáte ID rozšíření pro rozšíření aplikace jednotného přihlašování ve vaší organizaci.
  - **Kerberos**: použijte integrované rozšíření protokolu Kerberos společnosti Apple, které je součástí iOS 13,0 (a novějších) a iPadOS 13,0 (a novější). Tato možnost je verze rozšíření **přihlašovacích údajů** specifická pro Kerberos.

  > [!TIP]
  > Pomocí typu **přihlašovacích údajů** přidáte vlastní hodnoty konfigurace, které chcete předat prostřednictvím rozšíření. Místo toho zvažte použití předdefinovaného nastavení konfigurace poskytované společností Apple v typu **Kerberos** .

- **ID rozšíření** (jenom přihlašovací údaje): zadejte identifikátor sady prostředků, který identifikuje vaše rozšíření aplikace jednotného přihlašování, například `com.apple.extensiblesso`.
- **ID týmu** (pouze přihlašovací údaje): zadejte identifikátor týmu rozšíření aplikace jednotného přihlašování. Identifikátor týmu je alfanumerický řetězec (čísel a písmen) 10 znaků generovaný společností Apple, například `ABCDE12345`. ID týmu se nevyžaduje.

  [Najděte své ID týmu](https://help.apple.com/developer-account/#/dev55c3c710c) (otevře se webová stránka společnosti Apple), kde najdete další informace.

- **Sféra**: zadejte název sféry protokolu Kerberos. Název sféry by měl být velkými písmeny, například `CONTOSO.COM`. Název vaší sféry je typicky stejný jako název vaší domény DNS, ale jenom na velká písmena.

- **Domény**: zadejte doménu nebo názvy hostitelů pro weby, které se dají ověřit pomocí jednotného přihlašování. Například pokud je váš web `mysite.contoso.com`, pak `mysite` je název hostitele a `contoso.com` je název domény. Když se uživatelé připojí k některé z těchto webů, aplikace App Extension zpracuje výzvu ověřování. Toto ověřování umožňuje uživatelům k přihlášení použít ID obličeje, dotykové ID nebo Apple PINCODE/přístupový kód.

  - Všechny domény v profilech služby Intune, které mají rozšíření pro aplikace jednotného přihlašování, musí být jedinečné. Doménu nemůžete opakovat v žádném profilu rozšíření aplikace pro přihlášení, i když používáte různé typy rozšíření aplikace jednotného přihlašování.
  - U těchto domén se nerozlišují velká a malá písmena.

- **Další konfigurace** (jenom přihlašovací údaje): zadejte další data specifická pro rozšíření, která chcete předat rozšíření aplikace jednotného přihlašování:
  - **Konfigurační klíč**: zadejte název položky, kterou chcete přidat, například `user name`.
  - **Typ hodnoty**: zadejte typ dat. Vaše možnosti:

    - Řetězec
    - Boolean: v **hodnotě konfigurace**zadejte `True` nebo `False`.
    - Integer: v **hodnotě konfigurace**zadejte číslo.
    
  - **Hodnota konfigurace**: zadejte data.

  - **Přidat**: vyberte, pokud chcete přidat konfigurační klíče.

- **Použití řetězce klíčů** (jenom Kerberos): vyberte **blok** , aby se zabránilo ukládání a ukládání hesel do řetězce klíčů. **Nenakonfigurováno** (výchozí) umožňuje ukládat a ukládat hesla do řetězce klíčů.
- **ID obličeje, dotykové ID nebo heslo** (jenom Kerberos): **vyžaduje** , aby uživatelé zadali své ID a dotykové ID, nebo Apple heslo pro přihlášení k doménám, které jste přidali. **Nenakonfigurováno** (výchozí) nevyžaduje, aby uživatelé používali biometrika nebo heslo pro přihlášení.
- **Výchozí sféra** (pouze Kerberos): Chcete-li nastavit hodnotu **sféry** , kterou jste zadali jako výchozí sféru, vyberte možnost **Povolit** . **Nenakonfigurováno** (výchozí) nenastavuje výchozí sféru.

  > [!TIP]
  > - Toto nastavení **Povolte** , pokud konfigurujete více rozšíření aplikace pro jednotné přihlašování pomocí protokolu Kerberos ve vaší organizaci.
  > - Toto nastavení **Povolte** , pokud používáte více sfér. Nastaví hodnotu **sféry** , kterou jste zadali jako výchozí sféru.
  > - Pokud máte pouze jednu sféru, ponechte ji **nenakonfigurovanou** (výchozí).

- **Hlavní název** (jenom Kerberos): zadejte uživatelské jméno objektu zabezpečení protokolu Kerberos. Nemusíte zahrnovat název sféry. Například v `user@contoso.com` je `user` hlavní název a `contoso.com` je název sféry.
- **Kód lokality služby Active Directory** (pouze Kerberos): zadejte název lokality služby Active Directory, kterou má rozšíření protokolu Kerberos použít. Tuto hodnotu pravděpodobně nebudete muset měnit, protože rozšíření protokolu Kerberos může automaticky najít kód lokality služby Active Directory.
- **Název mezipaměti** (jenom Kerberos): zadejte název obecné služby zabezpečení (GSS) mezipaměti protokolu Kerberos. Tuto hodnotu pravděpodobně nemusíte nastavovat.
- **ID sady prostředků aplikace** (jenom Kerberos): **přidejte** identifikátory sady prostředků aplikace, které by měly na svých zařízeních používat jednotné přihlašování. Těmto aplikacím je udělen přístup k lístku pro udělení lístku protokolu Kerberos, ověřovacímu lístku a ověřování uživatelů pro služby, kterým mají oprávnění k přístupu.
- **Mapování sféry domény** (jenom Kerberos): **přidejte** přípony DNS domény, které by se měly namapovat do vaší sféry. Toto nastavení použijte, pokud názvy DNS hostitelů neodpovídají názvu sféry. Pravděpodobně nemusíte vytvářet vlastní mapování domén na sféru.

## <a name="wallpaper"></a>Tapeta

Pokud se zařízením s existující imagí nepřiřazuje profil bez obrázku, může docházet k neočekávanému chování. Můžete například vytvořit profil bez obrázku. Tento profil je přiřazen k zařízením, která již mají bitovou kopii. V tomto scénáři se image může změnit na výchozí nastavení zařízení, jinak se v zařízení může zachovat původní image. Toto chování se řídí a je omezené platformou MDM od společnosti Apple.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Nastavení platí pro: automatický zápis zařízení (pod dohledem)

- **Umístění zobrazení tapety**: vyberte umístění na zařízení pro zobrazení obrázku. Vaše možnosti:
  - **Nenakonfigurováno**: do zařízení se nepřidá vlastní image. Zařízení používá výchozí operační systém.
  - **Zamykací obrazovka**: Přidá obrázek na zamykací obrazovku.
  - **Domovská obrazovka**: Přidá obrázek na domovskou obrazovku.
  - **Zamykací obrazovka a Domovská obrazovka**: používá stejnou bitovou kopii na zamykací obrazovce a na domovské obrazovce.
- **Obrázek tapety**: nahrajte existující obrázek. png,. jpg nebo. jpeg, který chcete použít. Ujistěte se, že velikost souboru je menší než 750 KB. Můžete také **Odebrat** obrázek, který jste přidali.

> [!TIP]
> Chcete-li zobrazit různé obrázky na zamykací obrazovce a na domovské obrazovce, vytvořte profil s obrázkem zamykací obrazovky. Vytvořte jiný profil s obrázkem na domovské obrazovce. Přiřaďte oba profily ke skupinám uživatelů nebo zařízení s iOS.

## <a name="next-steps"></a>Další kroky

[Přiřaďte profil](../device-profile-assign.md) a [sledujte jeho stav](../device-profile-monitor.md).

Můžete také vytvořit profily funkcí zařízení pro zařízení [MacOS](macos-device-features-settings.md) .
