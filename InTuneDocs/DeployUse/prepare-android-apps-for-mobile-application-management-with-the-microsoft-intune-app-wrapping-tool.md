---
# required metadata

title: Příprava aplikací pro Android na správu nástrojem App Wrapping Tool |  Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Příprava aplikací pro Android na správu mobilních aplikací pomocí nástroje Intune App Wrapping Tool
Pokud chcete změnit chování aplikací pro Android na pracovišti, tak abyste mohli nastavovat funkce aplikací pro Android beze změny kódu aplikace, použijte nástroj **Microsoft Intune App Wrapping Tool pro Android**.

Nástroj je aplikace příkazového řádku Windows, která běží v prostředí PowerShell a vytvoří okolo vaší aplikace „obálku“. Po zpracování aplikace můžete změnit její funkce pomocí [zásad správy mobilní aplikace](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md), které nakonfigurujete.

Jestli vaše aplikace používá knihovnu Azure Active Directory Authentication Library (ADAL), musíte před zabalením aplikace dokončit kroky v části [Postup při zabalení aplikací, které používají knihovnu Azure Active Directory Library](#how-to-wrap-apps-that-use-the-azure-active-directory-library). Pokud si nejste jistí, jestli vaše aplikace tuto knihovnu používá, obraťte se na vývojáře aplikace.

Před spuštěním nástroje zkontrolujte [Důležité informace o zabezpečení při spuštění nástroje pro zabalení aplikace](#security-considerations-for-running-the-app-wrapping-tool). Nástroj si můžete stáhnout na stránce [Microsoft Intune App Wrapping pro Android](https://www.microsoft.com/download/details.aspx?id=47267)..

## Krok 1: Splnění požadavků na používání nástroje App Wrapping

-   Nástroj pro zabalení aplikace se musí spustit v počítači s Windows 7 nebo novějším systémem.

-   Vstupní aplikace musí být platný balíček aplikace pro Android se souborem s přílohou **.apk** a:

    -   Nedá se zašifrovat.

    -   Nesmí už být zabalený pomocí nástroje pro zabalení aplikace.

    -   Musí být napsaný pro Android 4.0 nebo vyšší.

-   Aplikace musí být vyvinutá vaší společností nebo pro ni. Tento nástroj se nedá používat ke zpracování aplikací stažených z Google Play Storu.

-   Pokud chcete spustit nástroj pro zabalení aplikace, nainstalujte nejnovější verzi [prostředí Java Runtime](http://java.com/download/) a ověřte, jestli je proměnná cesty Java v proměnných prostředí Windows nastavená na **C:\ProgramData\Oracle\Java\javapath**. Další nápovědu najdete v [dokumentaci Java](http://java.com/download/help/)..

    > [!NOTE]
    > V některých případech může 32bitová verze Javy způsobit potíže s pamětí. Doporučujeme nainstalovat místo toho 64bitovou verzi.

## Krok 2: Instalace nástroje App Wrapping

1.  Stáhněte si instalační soubor nástroje pro zabalení aplikace ze služby Stažení softwaru a nainstalujte ho do počítače s Windows.

2.  Přijměte licenční smlouvu a dokončete instalaci.

Poznamenejte si složku, do které jste nainstalovali nástroj. Výchozí umístění: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**..

## Krok 3: Spuštění nástroje App Wrapping

1.  Na počítači s Windows, na který jste nainstalovali nástroj pro zabalení aplikace, otevřete okno PowerShell.

2.  Ze složky, do které jste nástroj nainstalovali, importujte modul PowerShell nástroje pro zabalení aplikace:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Spusťte nástroj pomocí příkazu **invoke-AppWrappingTool** společně s následujícími parametry. Parametry, které jsou označené jako „volitelné“, jsou určené pro aplikace využívající knihovnu ADAL (Azure Active Directory Library). Další informace naleznete v části [Postup při zabalení aplikací, které používají knihovnu Azure Active Directory Library](#how-to-wrap-apps-that-use-the-azure-active-directory-library)..

|Parametr|Další informace|Příklady|
|-------------|--------------------|---------|
|**-InputPath**&lt;řetězec&gt;|Cesta ke zdrojové aplikaci pro Android (.apk).| |
|**-OutputPath**&lt;řetězec&gt;|Cesta k „výstupní“ aplikaci pro Android. Když je to cesta ke stejnému adresáři jako InputPath, vytváření balíčků selže.| |
|**-KeyStorePath**&lt;řetězec&gt;|Cesta k souboru úložiště klíčů, který obsahuje pár veřejného a privátního klíče pro podepisování.| |
|**-KeyStorePassword**&lt;řetězec zabezpečení&gt;|Heslo použité k dešifrování úložiště klíčů.| |
|**-KeyAlias**&lt;řetězec&gt;|Název klíče, který se má použít pro podepisování.| |
|**-KeyPassword**&lt;řetězec zabezpečení&gt;|Heslo použité k dešifrování privátního klíče, který se použije pro podepisování.| |
|**-SigAlg**&lt;řetězec zabezpečení&gt;|Název podpisového algoritmu, který se má použít k podepsání. Algoritmus musí být kompatibilní s privátním klíčem.|Příklady: SHA256withRSA, SHA1withRSA, MD5withRSA|
|**-ClientID**&lt;GUID&gt;|ID klienta Azure Active Directory vstupní aplikace (volitelné).| |
|**-AuthorityURI**&lt;identifikátor URI&gt;|Identifikátor URI autority Azure Active Directory vstupní aplikace (volitelné).| |
|**-SkipBroker**&lt;logická hodnota&gt;|Určuje, jestli vstupní aplikace podporuje zprostředkované jednotné přihlašování v celém zařízení (volitelné). |**True** – vstupní aplikace nepodporuje zprostředkované jednotné přihlašování v celém zařízení. Použijte parametr NonBrokerRedirectURI. **False** – vstupní aplikace podporuje zprostředkované jednotné přihlašování v celém zařízení.|
|**-NonBrokerRedirectURI**&lt;identifikátor URI&gt;|Identifikátor URI pro přesměrování služby Azure Active Directory, pokud má SkipBroker hodnotu true (volitelné).|  |


**&lt;CommonParameters&gt;**
    (volitelné – podporuje společné parametry prostředí PowerShell jako podrobné nastavení, ladění atd.)

- Seznam společných parametrů najdete na webu [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx)..

- Pokud chcete zobrazit nápovědu k nástroji, zadejte příkaz:

    ```
    Help Invoke-AppWrappingTool
    ```
- Další informace o integraci služby Azure Active Directory (AAD) najdete v části [Postup při zabalení aplikací, které používají knihovnu Azure Active Directory Library](#how-to-wrap-apps-that-use-the-azure-active-directory-library)..

**Příklad:**


    Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
    Invoke-AppWrappingTool –InputPath <input-app.apk> -OutputPath <output-app.apk> -KeyStorePath <path-to-signing.keystore> -KeyAlias <signing-key-name> -ClientID <xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx> -AuthorityURI <http://AzureActiveDirectory.Authority.URL> -SkipBroker<$True|$False> -NonBrokerRedirectURI <urn:xxx:xx:xxxx:xx:xxx>

Pak se zobrazí výzva k zadání parametrů **KeyStorePassword** a **KeyPassword**..

Zabalená aplikace se generuje a uloží se souborem protokolu do zadané výstupní cesty.

## Důležité informace o zabezpečení při spuštění nástroje pro zabalení aplikace
Pro zabránění potenciálnímu falšování identity, zpřístupnění informací a zvýšení oprávnění pro útoky zajistěte toto:

-   Vstupní obchodní aplikace, výstupní aplikace a Java KeyStore musí být ve stejném počítači, na kterém je spuštěný nástroj pro zabalení aplikace.

-   Importujte výstupní aplikaci do konzoly Intune na stejném počítači, na kterém je nástroj spuštěný.

-   Pokud jsou výstupní aplikace a nástroj v cestě Universal Naming Convention (UNC) a nespouštíte nástroj a vstupní soubory na stejném počítači, nakonfigurujte prostředí tak, aby bylo zabezpečené, pomocí protokolů [Internet Protocol Security (IPsec)](http://en.wikipedia.org/wiki/IPsec) nebo [podepsání protokolu Server Message Block (SMB)](https://support.microsoft.com/en-us/kb/887429)..

-   Ujistěte se, jestli aplikace pochází z důvěryhodného zdroje, zvlášť pokud používáte službu Azure Active Directory (AAD), která může aplikaci umožnit přístup k tokenu AAD v běhovém prostředí.

-   Zabezpečte výstupní adresář, který obsahuje zabalenou aplikaci. Zvažte použití adresáře na úrovni uživatele pro výstup.

## Postup při zabalení aplikací, které používají knihovnu Azure Active Directory Library
Jestli vaše aplikace používá knihovnu Azure Active Directory Authentication Library (ADAL), musíte před zabalením aplikace dokončit tyto kroky.

### Krok 1: Ověření, že splňujete požadavky pro ADAL
Pro aplikace, které používají ADAL, musí platit následující:

-   Aplikace musí mít verzi ADAL větší nebo rovnou hodnotě 1.0.2.

-   Vývojář musí své aplikaci udělit přístup k prostředku Správa mobilních aplikací Intune podle popisu v části [Krok 3: Konfigurace přístupu ke správě mobilních aplikací v AAD](#step-3-configure-access-to-mobile-app-management-in-aad)..

### Krok 2: Kontrola identifikátorů, které potřebujete získat při registraci aplikace
V dalším kroku použijete portál pro správu Azure k registraci aplikací (které používají ADAL se službou Azure Active Directory (AAD)) a k získání jedinečných identifikátorů uvedených v následující tabulce. Identifikátory pak předáte vývojářům při integraci knihovny ADAL s aplikací.

|Identifikátor|Další informace|Výchozí hodnota|
|--------------|--------------------|-----------------|
|**ID klienta**|Jedinečný identifikátor GUID, který se vygeneruje pro aplikaci po dokončení registrace ve službě AAD.<br /><br />Pokud víte ID klienta aplikace, zadejte tuto hodnotu. Jinak použijte výchozí hodnotu.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**URI autority**|Hodnota URI (Uniform Resource Identifier) autority pro objekty AAD, například uživatele a skupiny.<br /><br />U nástroje pro zabalení aplikace je parametr AuthorityURI volitelný. Pokud tento parametr nepoužijete, použije se výchozí URI.||
|**SkipBroker**|Hodnota označující, jestli se portál společnosti použije jako zprostředkovatel.<br /><br />**True** – portál společnosti se nepoužije pro ověřování ADAL.<br /><br />**False** – portál společnosti se použije pro ověřování ADAL. Portál společnosti používá registrovaného uživatele pro účely jednotného přihlašování.||
|**Identifikátor URI pro přesměrování bez zprostředkovatele**|Přihlašovací identifikátor URI, který se použije, když ADAL nepoužívá aplikaci zprostředkovatele (portál společnosti služby Intune).|urn:ietf:wg:oauth:2.0:oob|
|**ID prostředku**|Ukazatel na prostředky AAD aplikace.||

### Krok 3: Konfigurace přístupu ke správě mobilních aplikací v AAD
Než budete moct v nástroji App Wrapping použít hodnoty registrace AAD aplikace, musí vývojář aplikace udělit této aplikaci přístup k prostředku správy mobilní aplikace Intune pomocí následujícího postupu:

1.  Přihlaste se k existujícímu účtu AAD na portálu pro správu Azure.

2.  Zvolte **existující registraci aplikace LOB**..

3.  V části **konfigurace** zvolte **Konfigurovat přístup k webovým rozhraním API v ostatních aplikacích**..

4.  V prvním rozevíracím seznamu v části **Oprávnění k ostatním aplikacím** vyberte **Správa mobilní aplikace Intune**..

Teď můžete použít ID klienta aplikace v nástroji pro zabalení aplikace. ID klienta aplikace najdete na portálu pro správu Azure Active Directory podle popisu v tabulce v části [Krok 2: Kontrola identifikátorů, které potřebujete získat při registraci aplikace](#step-2-review-the-identifiers-you-need-to-get-when-you-register-the-app)..

### Krok 4: Použití hodnot identifikátoru AAD v nástroji App Wrapping
Použijte hodnoty identifikátorů, které jste získali při registraci, a v nástroji pro zabalení aplikace zadejte hodnoty jako vlastnosti příkazového řádku. Aby koncoví uživatelé mohli aplikaci úspěšně ověřit, musíte zadat všechny hodnoty v tabulce. Když nezadáte hodnotu, použijí se výchozí hodnoty.

|Identifikátor|Parametr|
|--------------|-------------|
|ID klienta|ClientID|
|URI autority|Authority-URI|
|SkipBroker|SkipBroker|
|Identifikátor URI pro přesměrování bez zprostředkovatele|NonBrokerRedirectURI|
|ID prostředku|ResourceID|
Při balení aplikace byste měli brát v úvahu následující pravidla:

-   Nástroj pro zabalení aplikace nehledá v aplikaci binární soubory ADAL (pokud existují). Pokud aplikace odkazuje na zastaralou verzi binárních souborů a jsou zapnuté zásady ověřování, můžou se během přihlašování objevit chyby za běhu.

-   Pro kontrolu, jestli ověření proběhlo úspěšně,
  [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] načte token AAD, který je přidružen ID prostředku MAM. Token se ale nepoužije v žádném volání, které by ověřilo jeho platnost. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] přečte jen hlavní název (UPN) přihlášeného uživatele a zjistí přístup k aplikaci. Token AAD se nepoužívá pro žádná další servisní volání.

-   Tokeny ověřování se sdílejí mezi aplikacemi od stejného vydavatele, protože jsou uložené ve sdíleném řetězci klíčů. Když chcete izolovat konkrétní aplikaci, použijte jiný podpisový certifikát, úložiště klíčů profilu zřizování a alias klíče pro tuto aplikaci.

-   Zadáním ID klienta a identifikátoru URI autority zabráníte zdvojení výzev k přihlášení. Přístup k publikovanému ID prostředku MAM služby [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] v řídicím panelu AAD vyžaduje registraci ID klienta. Když ID klienta nezaregistrujete, uživatelům při spuštění aplikace selže přihlašování.


### Související témata
- [Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Použití sady SDK k povolení správy mobilních aplikací pro aplikace](use-the-sdk-to-enable-apps-for-mobile-application-management.md)


<!--HONumber=May16_HO1-->


