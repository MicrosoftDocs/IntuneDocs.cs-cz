---
title: "Microsoft Intune App SDK pro iOS – Příručka pro vývojáře | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 952cfa4f23f8ba080ce53f6785baceb8a0a367c6
ms.openlocfilehash: 0d69d0b230771a87c1103682b17336dc47d26622


---

# Microsoft Intune App SDK pro iOS – Příručka pro vývojáře

> [!NOTE]
> Možná si budete chtít nejdřív přečíst příručku [Začínáme s Intune App SDK](intune-app-sdk-get-started.md), která vysvětluje postup přípravy integrace na jednotlivých podporovaných platformách.* 

Microsoft Intune App SDK pro iOS umožňuje začlenit správu mobilních aplikací (MAM) Intune do vaší aplikace pro iOS. Aplikace s podporou MAM je integrovaná se sadou Intune App SDK a umožňuje správcům IT nasadit zásady do mobilní aplikace, když je aktivně spravovaná.

## Co je v sadě SDK

Intune App SDK pro iOS zahrnuje statickou knihovnu, soubory prostředků, záhlaví API, seznam vlastností (plist) s nastavením pro ladění a nástroj konfigurátoru. Mobilní aplikace můžou pro vynucení většiny zásady jednoduše zahrnout soubory prostředků a staticky se propojit ke knihovnám. Pokročilé funkce Intune MAM se vynucují prostřednictvím rozhraní API.
Tato příručka popisuje použití následujících objektů při integraci Intune App SDK pro iOS:

* **`libIntuneMAM.a`**: Knihovna Intune App SDK. Propojením této knihovny se svým projektem zajistíte podporu MAM pro mobilní aplikace. Pokyny najdete v tomto článku v části Sestavení aplikace pomocí Intune App SDK.

* **`IntuneMAMResources.Bundle`**: Balíček prostředků obsahující prostředky, které SDK využívá. 

* **Hlavičky**: Zveřejňují rozhraní API sady Intune App SDK. Pokud použijete rozhraní API, musíte zahrnout soubor hlaviček, který toto rozhraní API obsahuje. 

## Jak Intune App SDK funguje

Cílem sady Intune App SDK pro iOS je doplnit do aplikací pro iOS možnosti správy s minimálními změnami kódu. Omezení změn kódu zkracuje dobu uvedení na trh a současně zvyšuje konzistenci a stabilitu mobilní aplikace. 

Aplikace musí být propojená se statickou knihovnou a musí zahrnovat balíček prostředků. Soubor MAMDebugSettings.plist je volitelný a může být v balíčku zahrnutý proto, aby simuloval použití zásad MAM v aplikaci, aniž by ji bylo nutné nasazovat pomocí Microsoft Intune. Dál se v sestavení pro ladění zásady v souboru MAMDebugSettings.plist můžou použít tak, že se soubor MAMDebugSettings.plist přenese do adresáře dokumentů aplikace pomocí sdílení souborů iTunes.

## Sestavení aplikace pomocí Intune App SDK 

Dokončením tohoto postupu povolíte Intune App SDK:

1. Připojte se ke knihovně `libIntuneMAM.a` pomocí těchto kroků:

    Přetáhněte knihovnu libIntuneMAM.a do seznamu propojených architektur a knihoven cíle projektu.  

    ![Intune App SDK iOS – propojené architektury a knihovny](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)
 
    **Poznámka**: Při uvolnění do App Storu použijte verzi libIntuneMAM.a, která je sestavená pro vydání, a ne ladicí verzi. Prodejní verze bude ve složce Release. Ladicí verze má podrobný výstup, který je vhodný pro ladění problémů s Intune App SDK.

2. Do projektu přidejte tyto architektury iOS (pokud chybí).
    * `MessageUI.framework`
    * `Security.framework`
    * `MobileCoreServices.framework`
    * `SystemConfiguration.framework`
    * `libsqlite3.dylib`
    * `libc++.dylib`
    * `ImageIO.framework`
    * `LocalAuthentication.Framework`
    * `AudioToolbox.framework`<br>

    **Poznámka**: Pokud aplikace cílí na iOS7, nastavte pro `LocalAuthentication.Framework` atribut Status na Volitelné. 

    Pokud atribut Status není nastavený, aplikace se v iOS7 nespustí.

    **Poznámka**: Xcode 7 přepnul rozšíření `.dylib` na `.tbd`.

3. Přidejte do projektu balíček prostředků `IntuneMAMResources.bundle` . Přetáhněte tento balíček prostředků do části Kopírovat prostředky balíčku pod Fáze buildu. 

    ![Intune App SDK iOS – kopírování prostředků sady](../media/intune-app-sdk-ios-copy-bundle-resources.png)

4. Přidejte `-force_load {PATH_TO_LIB}/libIntuneMAM.a` do následujících nastavení a nahraďte přitom `{PATH_TO_LIB}` umístěním Intune App SDK:
    * nastavení konfigurace sestavení OTHER_LDFLAGS projektu 
    * nastavení Další příznaky linkeru uživatelského rozhraní<br>

    **Poznámka**: Pokud chcete zjistit `PATH_TO_LIB`, vyberte soubor `libIntuneMAM.a` a pak vyberte Informace z nabídky Soubor. Zkopírujte informace Where (cesta) z části Obecné v okně Informace.

5. Pokud vaše mobilní aplikace definuje v souboru `info.plist`hlavní Nib nebo Storyboard, odeberte pole souboru Main Storyboard nebo Main Nib. Hodnoty Storyboard nebo Nib, které jste odebrali, přidejte do nového slovníku nazvaného `IntuneMAMSettings` s následujícími názvy klíčů:
    * `MainStoryboardFile`
    * `MainStoryboardFile~ipad`
    * `MainNibFile`
    * `MainNibFile~ipad `
    
    Pokud mobilní aplikace v souboru `info.plist`nedefinuje hlavní Nib nebo Storyboard, tato nastavení se **nevyžadují**. 

    **Poznámka**: Soubor `info.plist` můžete zobrazit v nezpracovaném formátu (abyste zjistili názvy klíčů) tak, že kliknete pravým tlačítkem kamkoli do těla dokumentu a změníte typ zobrazení na Zobrazit nezpracované klíče/hodnoty.

6. Povolte sdílení řetězce klíčů (pokud ještě není povolené) tak, že v každém cíli projektu kliknete na Možnosti a povolíte přepínač sdílení řetězce klíčů. Sdílení řetězce klíčů se vyžaduje pro přechod k dalšímu kroku.

    **Poznámka**: Profil zřizování musí podporovat nové hodnoty sdílení řetězce klíčů. Přístupové skupiny pro řetězce klíčů by měly podporovat zástupné znaky. Můžete to ověřit tak, že soubor `.mobileprovision` otevřete v textovém editoru, vyhledáte text keychain-access-groups a ověříte, že máte zástupný znak, třeba: 

       <key>keychain-access-groups</key>
       <array>
       <string>YOURBUNDLESEEDID.*</string>
       </array>

7. Když povolíte sdílení řetězce klíčů, použijte následující postup a vytvořte samostatnou přístupovou skupinu, ve které se uloží data Intune App SDK. Přístupovou skupinu pro řetězce klíčů můžete vytvořit pomocí uživatelského rozhraní nebo pomocí souboru nároků:

    Vytvoření přístupové skupiny pro řetězce klíčů pomocí uživatelského rozhraní: 
    
    * Pokud mobilní aplikace nemá definované žádné přístupové skupiny pro řetězce klíčů, přidejte jako první skupinu ID sady aplikace.
    * Přidejte sdílenou skupinu řetězce klíčů com.microsoft.intune.mam. Tuto přístupovou skupinu používá Intune App SDK k ukládání dat.  
    * Přidejte do projektu balíček prostředků `com.microsoft.adalcache` . 
 
    ![Intune App SDK iOS – sdílení řetězců klíčů](../media/intune-app-sdk-ios-keychain-sharing.png)

    Pokud k vytvoření přístupové skupiny pro řetězce klíčů místo běžného uživatelského rozhraní používáte soubor nároků, budete muset v souboru nároku před tuto přístupovou skupinu pro řetězce klíčů předřadit `$(AppIdentifierPrefix)` . Příklad: `$(AppIdentifierPrefix)com.microsoft.intune.mam` a `$(AppIdentifierPrefix)com.microsoft.adalcache`.

    **Poznámka**: Soubor nároků je soubor XML, který je pro vaši mobilní aplikaci jedinečný a používá se k určení speciálních povolení a možností aplikace pro iOS.

8. U mobilních aplikací vyvíjených pro iOS 9+ musíte všechny protokoly, které mobilní aplikace předává `UIApplication canOpenURL` , zahrnout do pole `LSApplicationQueriesSchemes` v souboru `info.plist` této mobilní aplikace. Pro každý protokol uvedený v seznamu se navíc musí přidat nový protokol s příponou `-intunemam`. Do pole musíte taky zahrnout `http-intunemam`, `https-intunemam`a `ms-outlook-intunemam` . 

9. Pokud aplikace v `info.plist file`definuje schémata URL, přidejte pro každé schéma URL další schéma s příponou `-intunemam` .

10. Pokud má aplikace ve svých nárocích definované skupiny aplikací, přidejte tyto skupiny do slovníku `IntuneMAMSettings` v klíči `AppGroupIdentitifiers` jako pole řetězců.

11. Propojte mobilní aplikaci s knihovnou ADAL. Knihovna ADAL pro Objective C je [dostupná na Githubu](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    **Poznámka**: Sada Intune App SDK je testovaná s kódem větve zprostředkovatele ADAL ze dne 19. 6. 2015. Ověřte, že se připojujete k nejnovější/pracovní verzi knihovny ADAL.

12. Přidejte do projektu balíček prostředků `ADALiOSBundle.bundle resource` . Přetáhněte tento balíček prostředků do části Kopírovat prostředky balíčku pod Fáze buildu.

13. Při připojování ke knihovně použijte parametr linkeru `-force_load PATH_TO_ADAL_LIBRARY` .

    Přidejte `-force_load {PATH_TO_LIB}/libADALiOS.a` do nastavení konfigurace sestavení OTHER_LDFLAGS nebo do nastavení Další příznaky linkeru v uživatelském rozhraní. CESTA_KE_KNIHOVNĚ by měla být nahrazená umístěním binárních souborů ADAL. 

Pokud mobilní aplikace využívá ADAL k vlastnímu ověřování, přečtěte si v tomto článku část Konfigurace nastavení knihovny pro ověřování Azure Directory.

### Telemetrie 

Intune App SDK pro iOS ve výchozím nastavení protokoluje telemetrická data týkající se událostí použití, která se posílají Microsoft Intune.

Data se protokolují pro tyto události použití: 

1. Spuštění aplikace s cílem pomoct službě Microsoft Intune zjistit využití aplikací s podporou MAM podle typu správy.

2. Volání rozhraní API EnrollApplication s cílem pomoct službě Microsoft Intune zjistit procento úspěšnosti a různé další metriky výkonu volání enrollApplication ze strany klienta.

**Poznámka**Pokud se rozhodnete neodesílat telemetrická data sady Intune App SDK z vaší aplikace do Microsoft Intune, **musíte zakázat** zachycování telemetrie sady Intune App SDK nastavením vlastnosti `MAMTelemetryDisabled` na hodnotu ANO v `IntuneMAMSettings`.

## Konfigurace nastavení Azure Directory Authentication Library (ADAL) (volitelné)

Intune App SDK využívá ADAL ke svému ověřování a k podmíněnému spuštění. ADAL zpravidla vyžaduje, aby se aplikace registrovaly a získaly jedinečné ID označované jako `ClientID`a další identifikátory. Zaručí se tak zabezpečení tokenů udělených aplikaci. Intune App SDK využívá při kontaktování Azure Active Directory výchozí registrační hodnoty.  Pokud aplikace využívá ADAL ve svém vlastním ověřovacím scénáři, musí používat své existující registrační hodnoty a přepsat výchozí nastavení Intune App SDK. Zajistí tak, aby koncoví uživatelé  nebyli k ověřování vyzýváni dvakrát (jednou sadou Intune App SDK a jednou vlastní aplikací). 

Následující kroky jsou nutné, pokud aplikace využívá ADAL pro vlastní ověřování. Pokud mobilní aplikace nespoléhá na ADAL, není potřeba dělat nic. 

1. V souboru `Info.plist`projektu ve slovníku `IntuneMAMSettings` s názvem klíče `ADALClientId`zadejte `ClientID` , které se má použít pro volání ADAL. 

2. V souboru `Info.plist`projektu ve slovníku `IntuneMAMSettings` s názvem klíče `ADALRedirectUri`zadejte identifikátor URI přesměrování, který se má použít pro volání ADAL. Budete možná muset zadat taky `ADALRedirectScheme` . To záleží na formátu identifikátoru URI přesměrování vaší aplikace.

### Sestavování rozšíření (volitelné) 

Při sestavování rozšíření použijte stejné pokyny jako pro sestavení mobilní aplikace, které jsou uvedené  v tomto článku v části Sestavení aplikace pomocí Intune App SDK. Dál aktualizujte soubor info.plist jednotlivých rozšíření tak, že do slovníku IntuneMAMSettings přidáte klíč ContainingAppBundleId s hodnotou obsahující ID sady aplikace.

### Sestavování architektur (volitelné)

Vzhledem k nejnovějším změnám Intune App SDK už nemusíte mobilní aplikaci, která obsahuje vložené architektury aplikace, kompilovat s konkrétními příznaky linkeru. 

### Soubory obrázků při spuštění (volitelné)

Když je aplikace s podporou MAM aktivně spravovaná službou Microsoft Intune, Intune App SDK zobrazí při spuštění aplikace úvodní obrazovku a informuje tak uživatele, že aplikace je spravovaná. Pokud chcete. můžete přidat soubory obrázků, které se zobrazí na úvodní stránce Spravuje vaše společnost. Pro obrázky použijte následující pokyny:

* Názvy souborů přidejte do slovníku `IntuneMAMSettings` v souboru info.plist aplikace s názvy klíčů `SplashIconFile` a `SplashIconFile~ipad`. 

* Požadavky na obrázky a jejich velikost:

    * 180x180 pro iPhone 6s Plus a iPhone 6 Plus, 120x120 pro ostatní modely iPhonu a 152x152 pro iPad. 
    
    * Z názvů souborů odeberte příponu `.png` . 
    
    * Při připojování ke knihovně použijte parametr linkeru `@2x` a pro trojnásobnou verzi použijte příponu `@3x` . Pokud obrázky nemají správnou velikost, přizpůsobí se. Když nejsou zadané hodnoty SplashIconFile, Intune App SDK vybere jednu z ikon aplikace (60x60 pro všechny iPhony, 76x76 pro iPad).

**Poznámka**: Toto okno se aktivuje při spuštění, ale uživatel ho může trvale vynechat.

## Konfigurace nastavení Intune App SDK

Ke konfiguraci Intune App SDK se používá slovník `IntuneMAMSettings` , který je obsažený v souboru `info.plist` aplikace. Dál je uvedený seznam všech podporovaných nastavení. 

Některá z těchto nastavení jsou možná popsaná v předchozích částech a některá se nevztahují na všechny aplikace. 

Nastavení  | Typ  | Definice | Požadováno?
--|--|--|--
ADALClientId  | Řetězec  | Identifikátor klienta AAD aplikace. | Požaduje se, když aplikace použila ADAL.
ADALRedirectUri  | Řetězec  | Identifikátor URI přesměrování AAD aplikace. | Vyžaduje se, když aplikace použila ADAL. 
AppGroupIdentifier | Pole řetězců  | Pole skupin aplikací z části com.apple.security.application-groups nároků aplikace. | Vyžaduje se, když aplikace využívá skupiny aplikací.
ContainingAppBundleId  | Řetězec | Určuje id sady rozšíření obsahující aplikaci. | Vyžaduje se rozšíření pro iOS.
MainNibFile<br>MainNibFile~ipad  | Řetězec  | Toto nastavení by mělo obsahovat název souboru pro  hlavní nib aplikace.  | Vyžaduje se, když aplikace v souboru info.plist definuje MainNibFile.
MainStoryboardFile<br>MainStoryboardFile~ipad  | Řetězec  | Toto nastavení by mělo obsahovat název souboru pro hlavní storyboard aplikace. | Vyžaduje se, když aplikace v souboru info.plist definuje UIMainStoryboardFile.
SplashIconFile <br>SplashIconFile~ipad  | Řetězec  | Určuje soubor úvodní ikony Intune. Další podrobnosti najdete v tomto článku v části Soubory obrázků při spuštění. | Volitelný parametr.
SplashDuration | Číslo | Minimální doba v sekundách, po kterou se při spuštění aplikace zobrazí úvodní obrazovka Intune. Výchozí hodnota je 1,5. | Volitelný parametr.
ADALLogOverrideDisabled | Logická hodnota  | Určuje, jestli SDK bude všechny protokoly ADAL (včetně všech případných volání ADAL z aplikace) směrovat do vlastního souboru protokolu. Výchozí hodnota je NE. Pokud aplikace chce nastavit vlastní zpětné volání protokolu ADAL, nastaví se  ANO. | Volitelný parametr.

## Hlavičky pro Intune App SDK 

Následující hlavičky zahrnují volání funkcí API nutné k povolení funkcí Intune App SDK. 

    IntuneMAMAsyncResult.h
    IntuneMAMDataProtectionInfo.h
    IntuneMAMDataProtectionManager.h
    IntuneMAMFileProtectionInfo.h
    IntuneMAMFileProtectionManager.h
    IntuneMAMPolicyDelegate.h
    IntuneMAMLogger.h

## Ladění Intune App SDK v Xcode

Před testováním aplikace s podporou MAM pomocí Microsoft Intune můžete v Xcode použít `Settings.bundle` . Můžete tak nastavit zásady testování a není potřeba připojení k Intune. Postup při povolení:

* `Settings.bundle` přidejte kliknutím pravým tlačítkem na složku nejvyšší úrovně ve vašem projektu. V nabídce vyberte Přidat -> Nový soubor. V části Prostředky vyberte šablonu Settings Bundle.

* Jenom u sestavení pro ladění zkopírujte `MAMDebugSettings.plist` do `Settings.bundle`.

* V `Root.plist` (v Settings.bundle) přidejte předvolbu Type Child Pane a FileName `MAMDebugSettings`.

* V Nastavení -> Název_aplikace přepněte Povolit zásady testování.

* Spusťte aplikaci (v prostředí Xcode nebo mimo něj). 

* V Nastavení -> Název_aplikace -> Povolit zásady testování přepněte zásadu, třeba PIN.

* Spusťte aplikaci (v prostředí Xcode nebo mimo něj). Ověřte, že PIN funguje podle očekávání.

> [!NOTE]
> Teď můžete prostřednictvím možností „Nastavení -> Název_aplikace -> Povolit zásady testování“ povolit a přepínat nastavení.

## Doporučené osvědčené postupy pro iOS

Dál jsou uvedené některé doporučené osvědčené postupy při vývoji pro iOS:

Systém souborů iOS rozlišuje malá a velká písmena. Ověřte, že u názvů souborů, jako je `libIntuneMAM.a` a `IntuneMAMResources.bundle`.

Pokud má Xcode potíže s vyhledáním `libIntuneMAM.a`, můžete je vyřešit tak, že cestu k této knihovně přidáte do cest hledání linkeru.




<!--HONumber=Sep16_HO2-->


