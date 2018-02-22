---
title: "Microsoft Intune App SDK pro iOS – Příručka pro vývojáře"
description: "Microsoft Intune App SDK pro iOS umožňuje začlenit do vaší aplikace pro iOS zásady ochrany aplikace Intune, a to ve formě správy mobilních aplikací (MAM)."
keywords: 
author: erikre
manager: dougeby
ms.author: erikre
ms.date: 01/10/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f74b996b3b96dfa808771f3dd4fc70f9c29324c2
ms.sourcegitcommit: 2c7794848777e73d6a9502b4e1000f0b07ac96bc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>Microsoft Intune App SDK pro iOS – Příručka pro vývojáře

> [!NOTE]
> Možná byste si mohli nejdříve přečíst článek [Začínáme s Intune App SDK](app-sdk-get-started.md), který vysvětluje postup přípravy integrace na jednotlivých podporovaných platformách.

Sada Microsoft Intune App SDK pro iOS umožňuje začlenit do vaší nativní aplikace pro iOS zásady ochrany aplikací Intune (označované také jako **zásady APP** nebo **MAM**). Aplikace s povolenou funkcí MAM je integrovaná se sadou Intune App SDK. Správci IT můžou zásady ochrany aplikací nasadit do vaší mobilní aplikace, když Intune tuto aplikaci aktivně spravuje.

## <a name="prerequisites"></a>Požadavky

* Budete potřebovat počítač Mac se systémem OS X 10.8.5 nebo novějším a nainstalovaným nástrojem Xcode 9 nebo novějším.

* Cílem vaší aplikace musí být iOS 9.3.5 nebo novější.

* Přečtěte si [licenční podmínky Intune App SDK pro iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf). Licenční podmínky si vytiskněte a uchovejte pro své záznamy. Stažením a použitím Intune App SDK pro iOS s licenčními podmínkami souhlasíte.  Pokud je nepřijímáte, software nepoužívejte.

* Stáhněte soubory pro sadu Intune App SDK pro iOS z [GitHubu](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios).

## <a name="whats-in-the-sdk"></a>Co je v sadě SDK

Intune App SDK pro iOS zahrnuje statickou knihovnu, soubory prostředků, záhlaví API, seznam vlastností (plist) s nastavením pro ladění a nástroj konfigurátoru. Mobilní aplikace můžou pro vynucení většiny zásad jednoduše zahrnout soubory prostředků a staticky se propojit ke knihovnám. Pokročilé funkce Intune MAM se vynucují prostřednictvím rozhraní API.

Tato příručka se věnuje tomu, jak používat následující komponenty sady Intune App SDK pro iOS:

* **libIntuneMAM.a**: Statická knihovna Intune App SDK. Pokud vaše aplikace nepoužívá rozšíření, připojte tuhle knihovnu k projektu, abyste aplikaci mohli spravovat pomocí Intune.

* **IntuneMAM.framework**: Model Intune App SDK. Pokud chcete aplikaci spravovat pomocí Intune, připojte tento model k projektu. Použijte ho místo statické knihovny v případě, že aplikace používá rozšíření, aby se v projektu nevytvořilo několik kopií statické knihovny.

* **IntuneMAMResources.bundle**: Sada prostředků s prostředky, které SDK využívá.

* **Hlavičky**: Zveřejňují rozhraní API sady Intune App SDK. Pokud použijete rozhraní API, musíte zahrnout soubor hlaviček, který toto rozhraní API obsahuje. Následující soubory hlaviček obsahují rozhraní API, datové typy a protokoly, které Intune App SDK zpřístupňuje vývojářům:

    * IntuneMAMAppConfig.h
    * IntuneMAMAppConfigManager.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMDefs.h
    * IntuneMAMEnrollmentDelegate.h
    * IntuneMAMEnrollmentManager.h
    * IntuneMAMEnrollmentStatus.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMLogger.h
    * IntuneMAMPolicy.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMPolicyManager.h
    * IntuneMAMVersionInfo.h
    
Vývojáři můžou obsah všech výše uvedených hlaviček zpřístupnit pouhým importováním souboru IntuneMAM.h


## <a name="how-the-intune-app-sdk-works"></a>Jak Intune App SDK funguje

Cílem sady Intune App SDK pro iOS je doplnit do aplikací pro iOS možnosti správy s minimálními změnami kódu. Čím méně je změn kódu, tím rychlejší může být uvedení aplikace na trh, přičemž konzistence a stabilita mobilní aplikace zůstávají beze změn.


## <a name="build-the-sdk-into-your-mobile-app"></a>Použití sady SDK v mobilní aplikaci

Pokud chcete povolit sadu Intune App SDK, postupujte takto:

1. **Možnost 1 (doporučeno)**: Propojit `IntuneMAM.framework` s projektem. Přetáhněte `IntuneMAM.framework` do seznamu **vložených binárních souborů** cíle projektu.

    > [!NOTE]
    > Pokud tento model použijete, nezapomeňte z univerzálního modelu před odesláním aplikace do App Storu odstranit architektury simulátoru. Viz část [Odeslání aplikace do App Storu](#Submit-your-app-to-the-App-Store), kde najdete další podrobnosti.

2. **Možnost 2**: Vytvořte propojení s knihovnou `libIntuneMAM.a`. Přetáhněte knihovnu `libIntuneMAM.a` do **seznamu propojených modelů a knihoven** cíle projektu.

    ![Intune App SDK iOS: propojené architektury a knihovny](./media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    Přidejte `-force_load {PATH_TO_LIB}/libIntuneMAM.a` do následujících nastavení a nahraďte přitom `{PATH_TO_LIB}` umístěním Intune App SDK:
      * nastavení konfigurace buildu `OTHER_LDFLAGS` v projektu
      * nastavení **Další příznaky linkeru** uživatelského rozhraní Xcode

        > [!NOTE]
        > Pokud chcete zjistit cestu `PATH_TO_LIB`, vyberte soubor `libIntuneMAM.a` a v nabídce **Soubor** klikněte na **Získat informace**. Cestu (údaj **Kde**) zkopírujte z části **Obecné** v okně **Informace**.

    Přidejte do projektu sadu prostředků `IntuneMAMResources.bundle`. Přetáhněte ji do části **Kopírovat prostředky balíčku** v rámci položky **Fáze buildu**.

    ![Intune App SDK iOS: kopírování prostředků sady](./media/intune-app-sdk-ios-copy-bundle-resources.png)

    Do projektu přidejte tyto modely iOS:  
            * MessageUI.framework  
            * Security.framework  
            * MobileCoreServices.framework  
            * SystemConfiguration.framework  
            * libsqlite3.tbd  
            * libc++.tbd  
            * ImageIO.framework  
            * LocalAuthentication.framework  
            * AudioToolbox.framework  
            * QuartzCore.framework  
            * WebKit.framework  

3. Povolte sdílení řetězce klíčů (pokud ještě není povolené) tak, že v každém cíli projektu kliknete na **Možnosti** a zapnete přepínač **Sdílení řetězce klíčů**. Sdílení řetězce klíčů se vyžaduje pro přechod k dalšímu kroku.

  > [!NOTE]
    > Profil zřizování musí podporovat nové hodnoty sdílení řetězce klíčů. Přístupové skupiny pro řetězce klíčů by měly podporovat zástupné znaky. Můžete to ověřit tak, že soubor .mobileprovision otevřete v textovém editoru, najdete **keychain-access-groups** a ověříte, že obsahuje zástupný znak. Příklad:
    ```xml
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```

4. Po povolení sdílení řetězce klíčů vytvořte následujícím postupem samostatnou přístupovou skupinu, do které sada Intune App SDK uloží svoje data. Přístupovou skupinu pro řetězce klíčů můžete vytvořit pomocí uživatelského rozhraní nebo pomocí souboru nároků. Pokud k vytvoření přístupové skupiny pro řetězce klíčů používáte uživatelské rozhraní, je třeba dodržovat následující postup:

    1. Pokud mobilní aplikace nemá definované žádné přístupové skupiny pro řetězce klíčů, přidejte jako první skupinu ID sady prostředků aplikace.

    2. Přidejte sdílenou skupinu pro řetězce klíčů `com.microsoft.intune.mam` do existujících přístupových skupin. Tuto přístupovou skupinu používá Intune App SDK k ukládání dat.

    3. Do existujících přístupových skupin přidejte `com.microsoft.adalcache`.

        ![Intune App SDK iOS: sdílení řetězců klíčů](./media/intune-app-sdk-ios-keychain-sharing.png)

    4. Pokud přímo upravujete soubor nároků a nepoužíváte k vytvoření přístupové skupiny pro řetězce klíčů výše popsané uživatelské rozhraní Xcode, dejte na začátek přístupové skupiny pro řetězce klíčů předponu `$(AppIdentifierPrefix)` (Xcode to dělá automaticky). Příklad:

            * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
            * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    > [!NOTE]
    > Soubor nároků je soubor XML, který je pro vaši mobilní aplikaci jedinečný. Slouží k určení speciálních oprávnění a schopností ve vaší aplikaci pro iOS. Pokud vaše aplikace dříve neměla soubor nároků, při povolení sdílení řetězců klíčů (krok 3) by ho měl pro ni Xcode vygenerovat.

5. Zahrňte všechny protokoly, které aplikace předává do `UIApplication canOpenURL`, do pole `LSApplicationQueriesSchemes` v souboru Info.plist této aplikace. Než přejdete k dalšímu kroku, uložte změny.

6. K dokončení konfigurace souboru Info.plist této aplikace použijte nástroj IntuneMAMConfigurator, který najdete v [úložišti SDK](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios). Nástroj má 3 parametry:
|Vlastnost|Jak ji použít|
|---------------|--------------------------------|
|- i |  `<Path to the input plist>` |
|- e | `<Path to the entitlements file>` |
|- o |  (Volitelné) `<Path to the output plist>` |

Pokud není parametr -o zadaný, upraví se vstupní soubor na místě. Nástroj je idempotentní a po provedení změn souboru Info.plist dané aplikace nebo nároků by se měl spustit znovu. Nejnovější verzi tohoto nástroje byste měli stáhnout a spustit také při aktualizaci Intune SDK, pokud se v nejnovější verzi změnily požadavky na konfiguraci souboru Info.plist.

## <a name="configure-azure-active-directory-authentication-library-adal"></a>Konfigurace knihovny ADAL (Azure Active Directory Authentication Library)

Intune App SDK využívá [Azure Active Directory Authentication Library](https://github.com/AzureAD/azure-activedirectory-library-for-objc) ke svému ověřování a podmíněnému spouštění. Knihovnu ADAL potřebuje taky kvůli registraci identity uživatele ve službě MAM, která slouží ke správě ve scénářích bez registrace zařízení.

Knihovna ADAL zpravidla vyžaduje, aby se aplikace registrovaly u služby Azure Active Directory (AAD) a získaly jedinečné ID (ID klienta) a další identifikátory. Zaručí se tak zabezpečení tokenů udělených aplikaci. Pokud není určeno jinak, Intune App SDK využívá při kontaktování Azure AD výchozí registrační hodnoty.  

Pokud už aplikace k ověřování uživatelů používá ADAL, musí používat svoje stávající registrační hodnoty a přepsat výchozí hodnoty Intune App SDK. Tím se zajistí, že se uživatelům nebude výzva k ověřování zobrazovat dvakrát (jednou ze sady Intune App SDK a jednou z aplikace).

### <a name="recommendations"></a>Doporučení

Je doporučeno, aby se vaše aplikace propojovala na [nejnovější verzi ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) na své hlavní větvi. Intune App SDK v současnosti využívá zprostředkovatelskou větev ADAL, aby podporovala aplikace, které vyžadují podmíněný přístup. (Tyto aplikace proto závisí na aplikaci Microsoft Authenticator.) Sada SDK je ale stále kompatibilní s hlavní větví ADAL. Používejte větev, která je vhodná pro vaši aplikaci.

### <a name="link-to-adal-binaries"></a>Propojení na binární soubory ADAL

Propojte aplikaci s binárními soubory ADAL podle následujících pokynů:

1. Stáhněte si [Azure Active Directory ověřování Library (ADAL) pro Objective-C](https://github.com/AzureAD/azure-activedirectory-library-for-objc) z Githubu a postupujte podle [pokynů](https://github.com/AzureAD/azure-activedirectory-library-for-objc#download) ke stažení ADALu pomocí dílčích modulů Git nebo CocoaPods.

2. Přidejte do projektu rozhraní ADAL (možnost 1) nebo statickou knihovnu (možnost 2):
    
    **Možnost 1 (doporučeno)**: Přetáhněte `ADAL.framework` do seznamu **vložených binárních souborů** cíle projektu.
    
    **Možnost 2**: Přetáhněte knihovnu `libADALiOS.a` do **seznamu propojených modelů a knihoven** cíle projektu. Přidejte `-force_load {PATH_TO_LIB}/libADALiOS.a` do nastavení konfigurace buildu `OTHER_LDFLAGS` v projektu nebo do nastavení **Další příznaky linkeru** v uživatelském rozhraní Xcode. Hodnotu `PATH_TO_LIB` byste měli nahradit umístěním binárních souborů ADAL.



### <a name="share-the-adal-token-cache-with-other-apps-signed-with-the-same-provisioning-profile"></a>Sdílet mezipaměť tokenů ADAL s jinými aplikacemi podepsanými pomocí stejného zřizovacího profilu?**

Pokud chcete sdílet tokeny ADAL mezi aplikacemi, které jsou podepsané pomocí stejného zřizovacího profilu, postupujte následovně:

1. Pokud aplikace nemá definované žádné přístupové skupiny pro řetězce klíčů, přidejte jako první skupinu ID sady prostředků aplikace.

2. Přidáním `com.microsoft.adalcache` do přístupových skupin řetězce klíčů povolte jednotné přihlašování (SSO) ADAL.

3. Pokud chcete `com.microsoft.adalcache` nahradit vlastní skupinou řetězce klíčů, uveďte ji pomocí klíče `ADALCacheKeychainGroupOverride` v souboru Info.plist pod IntuneMAMSettings.

### <a name="configure-adal-settings-for-the-intune-app-sdk"></a>Konfigurace nastavení ADALu pro Intune App SDK

Pokud už vaše aplikace používá ADAL k ověřování a má své vlastní nastavení ADALu, můžete přinutit sadu App SDK Intune, aby používala stejné nastavení během ověřování vůči Azure Active Directory. To zajistí, že aplikace nebude uživatele žádat o ověření dvakrát. Přečtěte si část [Konfigurace nastavení pro sadu Intune App SDK](#configure-settings-for-the-intune-app-sdk), kde najdete informace o naplnění těchto nastavení:  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

Pokud už vaše aplikace používá ADAL, vyžadují se následující konfigurace:

1. V souboru Info.plist projektu zadejte ve slovníku **IntuneMAMSettings** s názvem klíče `ADALClientId` ID klienta, které se má použít pro volání ADALu.

2. Ve slovníku **IntuneMAMSettings** s názvem klíče `ADALAuthority` zadejte autoritu Azure AD.

3. Ve slovníku **IntuneMAMSettings** s názvem klíče `ADALRedirectUri` také zadejte identifikátor URI pro přesměrování, který se má použít pro volání ADALu. Alternativně můžete místo toho zadat `ADALRedirectScheme`, pokud identifikátor URI pro přesměrování dané aplikace je ve formátu `scheme://bundle_id`.


Dále můžou aplikace přepsat tato nastavení Azure AD za běhu. K tomu stačí nastavit vlastnosti `aadAuthorityUriOverride`, `aadClientIdOverride` a `aadRedirectUriOverride` v instanci `IntuneMAMPolicyManager`.

> [!NOTE]
    > Použití souboru Info.plist se doporučuje pro všechna nastavení, která jsou statická a nevyžadují, aby se určovala za běhu. Hodnoty přiřazené vlastnostem v instanci `IntuneMAMPolicyManager` mají přednost před odpovídajícími hodnotami zadanými v souboru Info.plist a zachovají se i po restartování aplikace. Sada SDK je bude dále používat pro kontroly zásad, dokud se registrace daného uživatele nezruší nebo se tyto hodnoty nevymažou nebo nezmění.

### <a name="if-your-app-does-not-use-adal"></a>Pokud vaše aplikace nepoužívá ADAL

Pokud vaše aplikace nepoužívá ADAL, bude sada Intune App SDK poskytovat výchozí hodnoty pro parametry ADAL a zpracovávat ověřování proti Azure AD. Pro výše uvedená nastavení ADALu nemusíte zadávat žádné hodnoty.

## <a name="receiving-app-protection-policy"></a>Příjem zásad ochrany aplikací

### <a name="overview"></a>Přehled
Kvůli příjmu zásad ochrany aplikací Intune musí aplikace inicializovat žádost o registraci ve službě Intune MAM. Aplikace lze v konzole Intune nakonfigurovat tak, aby přijímaly zásady ochrany aplikací s registrací zařízení nebo bez registrace zařízení. Zásady ochrany aplikací bez registrace, označované také jako **APP-WE** nebo MAM-WE, umožňují správu aplikací přes Intune bez nutnosti registrace zařízení do správy mobilních zařízení Intune (MDM). V obou případech se pro příjem zásad vyžaduje registrace ve službě Intune MAM.

### <a name="apps-that-use-adal"></a>Aplikace, které používají ADAL

Aplikace, které už používají ADAL, by měly po úspěšném ověření uživatele zavolat metodu `registerAndEnrollAccount` v instanci `IntuneMAMEnrollmentManager`:

```objc
/*
 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;

```

Po zavolání metody `registerAndEnrollAccount` SDK uživatelský účet zaregistruje a pokusí se jeho jménem zaregistrovat aplikaci. Pokud se registrace z jakéhokoli důvodu nepodaří, SDK se o ni automaticky znovu pokusí za 24 hodin. Za účelem ladění může aplikace prostřednictvím delegáta přijímat [oznámení](#Status-result-and-debug-notifications) o výsledcích veškerých žádostí o registraci.

Po zavolání tohoto rozhraní API může aplikace dál normálně fungovat. Pokud se registrace podaří, SDK uživateli oznámí, že se vyžaduje restartování aplikace. V tu chvíli může uživatel aplikaci hned restartovat.

```objc
[[IntuneMAMEnrollmentManager instance] registerAndEnrollAccount:@”user@foo.com”];
```

### <a name="apps-that-do-not-use-adal"></a>Aplikace, které nepoužívají knihovnu ADAL

Aplikace, které uživatele nepřihlašují pomocí knihovny ADAL, můžou od služby Intune MAM přesto přijímat zásady ochrany aplikací voláním rozhraní API, které nechá ověření vyřídit prostřednictvím sady SDK. Aplikace by tento postup měly používat, když neověřily uživatele pomocí Azure AD, ale potřebují načítat zásady ochrany aplikací na pomoc s ochranou dat. (například, když se k ověřování přihlášení aplikace používá jiná služba ověřování nebo když aplikace přihlašování vůbec nepodporuje). Aplikace to provede zavoláním metody `loginAndEnrollAccount` v instanci `IntuneMAMEnrollmentManager`:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;

```

Zavoláním této metody vyzve SDK uživatele k zadání přihlašovacích údajů, pokud nejde najít žádný existující token. Sada SDK se pak pokusí aplikaci zaregistrovat ve službě Intune MAM jménem zadaného uživatelského účtu. Metodu je možné volat s identitou nil. V tom případě SDK provede registraci s existujícím spravovaným uživatelem, kterého najde na zařízení (pokud se používá MDM), nebo pokud žádného takového nenajde, vyzve uživatele k zadání uživatelského jména.

Pokud se registrace nepovede, aplikace by na základě podrobností selhání měla zvážit, jestli rozhraní API nezavolá za nějaký čas znovu. Aplikace může prostřednictvím delegáta přijímat [oznámení](#Status-result-and-debug-notifications) o výsledcích veškerých žádostí o registraci.

Po zavolání tohoto rozhraní API může aplikace dál normálně fungovat. Pokud se registrace podaří, SDK uživateli oznámí, že se vyžaduje restartování aplikace.

Příklad:
```objc
[[IntuneMAMEnrollmentManager instance] loginAndEnrollAccount:@”user@foo.com”];
```

### <a name="deregister-user-accounts"></a>Zrušení registrace uživatelských účtů

Než se uživatel z aplikace odhlásí, měla by aplikace zrušit jeho registraci v SDK. Díky tomu:

1. Nebudou probíhat opětovné pokusy o registraci tohoto uživatelského účtu.

2. Zásady ochrany aplikací budou odebrány.

3. Pokud aplikace zahájí (volitelné) selektivní vymazání, odstraní se všechna firemní data.

Před odhlášením uživatele by aplikace měla v instanci `IntuneMAMEnrollmentManager` zavolat následující metodu:

```objc
/*
 *  This method will remove the provided account from the list of
 *  registered accounts.  Once removed, if the account has enrolled
 *  the application, the account will be un-enrolled.
 *  @note In the case where an un-enroll is required, this method will block
 *  until the Intune MAM AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */
(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;

```

Metoda musí být volána před odstraněním tokenů Azure AD uživatelského účtu. Sada SDK potřebuje tokeny AAD uživatelského účtu k tomu, aby mohla jménem uživatele posílat službě Intune MAM určité žádosti.

Pokud aplikace odstraní firemní data uživatele sama, může být příznak `doWipe` nastaven na false. Jinak může aplikace přimět sadu SDK k zahájení selektivního vymazání. Výsledkem bude volání delegáta selektivního vymazání aplikace.

Příklad:
```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

## <a name="status-result-and-debug-notifications"></a>Oznámení o stavu, výsledku a ladění

Aplikace může přijmout oznámení o stavu, výsledku a ladění v souvislosti s následujícími požadavky na službu Intune MAM:

 - Žádosti o registraci
 - Žádosti o aktualizaci zásad
 - Žádosti o zrušení registrace

Tato oznámení se zobrazují prostřednictvím metod delegáta v souboru `Headers/IntuneMAMEnrollmentDelegate.h`:

```objc
/**
 *  Called when an enrollment request operation is completed.
 * @param status status object containing debug information
 */

(void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a MAM policy request operation is completed.
 *  @param status status object containing debug information
 */
(void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a un-enroll request operation is completed.
 *  @Note: when a user is un-enrolled, the user is also de-registered with the SDK
 *  @param status status object containing debug information
 */

(void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

```

Tyto metody delegáta vracejí objekt `IntuneMAMEnrollmentStatus`, který obsahuje následující informace:

- Identitu účtu přidruženého k žádosti
- Stavový kód označující výsledek žádosti
- Chybový řetězec s popisem stavového kódu
- Objekt `NSError`

Tento objekt je definovaný v souboru `IntuneMAMEnrollmentStatus.h` společně s konkrétními stavovými kódy, které můžou být vráceny.


### <a name="sample-code"></a>Příklad kódu

Toto jsou ukázky implementace metod delegáta:

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}


- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

```

## <a name="app-restart"></a>Restartování aplikace

Když aplikace poprvé obdrží zásady ochrany aplikací, musí se restartovat, aby mohla použít požadované zachycení volání a přesměrování funkce (hook). K upozornění aplikace, že je potřeba restartování, slouží jedna z metod delegáta SDK v umístění Headers/IntuneMAMPolicyDelegate.h.

```objc
 - (BOOL) restartApplication
```
Z návratové hodnoty této metody sada SDK pozná, jestli požadované restartování musí provést aplikace:   

 - Pokud se vrátí hodnota true, musí restartování provést aplikace.   

 - Pokud se vrátí hodnota false, aplikaci následně restartuje SDK. Sada SDK ihned zobrazí dialogové okno, které uživatele vyzve k restartování aplikace.

## <a name="customize-your-apps-behavior"></a>Přizpůsobení chování aplikace

Sada Intune App SDK má několik rozhraní API, které můžete volat, abyste získali informace o zásadách ochrany aplikací Intune nasazených do aplikace. Pomocí těchto dat můžete přizpůsobit chování aplikace. Většinu nastavení zásad ochrany aplikací automaticky vynucuje sada SDK, nikoli aplikace. Jediné nastavení, které by aplikace měla implementovat, je ovládací prvek Uložit jako.

### <a name="get-app-protection-policy"></a>Získání zásad ochrany aplikací

#### <a name="intunemampolicymanagerh"></a>IntuneMAMPolicyManager.h
Třída IntuneMAMPolicyManager zveřejňuje zásady ochrany aplikací Intune nasazené do aplikace. Zveřejňuje zejména rozhraní API, která slouží k [povolení více identit](#-enable-multi-identity-optional).

#### <a name="intunemampolicyh"></a>IntuneMAMPolicy.h
Třída IntuneMAMPolicy zveřejňuje zásady ochrany aplikací Intune nasazené do aplikace. Většinu nastavení zásad zveřejněných v této třídě vynucuje sada SDK, ale vždy je možné přizpůsobit chování aplikace v závislosti na tom, jak se nastavení zásad vynucují.

Tato třída zveřejňuje některá rozhraní API nezbytná k implementaci ovládacích prvků Uložit jako, které jsou podrobně popsané v další části.

### <a name="implement-save-as-controls"></a>Implementace ovládacích prvků Uložit jako

Intune umožňuje správcům IT vybrat, do kterých spravovaných umístění úložiště může aplikace ukládat data. Aplikace se můžou sady Intune App SDK na povolená umístění úložiště dotazovat pomocí rozhraní API **isSaveToAllowedForLocation** definovaného v **IntuneMAMPolicy.h**.

Před uložením spravovaných dat do cloudového úložiště nebo místního umístění musí aplikace v rozhraní API **isSaveToAllowedForLocation** zjistit, jestli do nich správce IT povolil data ukládat.

Při použití rozhraní API **isSaveToAllowedForLocation** musí aplikace předat hlavní název uživatele (UPN) používaný pro umístění úložiště, pokud je k dispozici.

#### <a name="supported-save-locations"></a>Podporovaná umístění pro ukládání

Rozhraní API **IsSaveToAllowedForLocation** poskytuje konstanty ke kontrole, jestli správce IT povoluje ukládání dat do následujících umístění definovaných v IntuneMAMPolicy.h:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationLocalDrive

Aplikace by měly konstanty v rozhraní API **isSaveToAllowedForLocation** používat k zjištění, jestli je možné data ukládat do umístění považovaných za „spravovaná“, jako je OneDrive pro firmy, nebo za „osobní“. Kromě toho by se mělo rozhraní API použít, když aplikace není schopná zjistit, jestli je umístění „spravované“, nebo „osobní“.

Umístění, o kterých se ví, že jsou „osobní“, jsou vyjádřená konstantou `IntuneMAMSaveLocationOther`.

Konstanta `IntuneMAMSaveLocationLocalDrive` by se měla použít, když aplikace ukládá data do jakéhokoli umístění na místním zařízení.

## <a name="configure-settings-for-the-intune-app-sdk"></a>Konfigurace nastavení pro sadu Intune App SDK

K nastavení a konfiguraci sady Intune App SDK můžete použít slovník **IntuneMAMSettings** v souboru Info.plist aplikace. Pokud slovník IntuneMAMSettings v souboru Info.plist neexistuje, měli byste v souboru Info.plist aplikace vytvořit slovník s názvem pole IntuneMAMSettings.

V rámci tohoto slovníku IntuneMAMSettings můžete sadu SDK nakonfigurovat přidáním řádků klíč/hodnota pro konfigurační nastavení. Následující tabulka obsahuje seznam všech podporovaných nastavení.

Některá z těchto nastavení jsou možná popsaná v předchozích částech a některá se nevztahují na všechny aplikace.

Nastavení  | Typ  | Definice | Požadováno?
--       |  --   |   --       |  --
ADALClientId  | Řetězec  | Identifikátor klienta Azure AD aplikace | Požadován, pokud aplikace používá ADAL. |
ADALAuthority | Řetězec | Autorita Azure AD aplikace se používá. Měli byste použít vlastní prostředí, ve kterém jsou nakonfigurované účty AAD. | Požadován, pokud aplikace používá ADAL. Pokud tato hodnota chybí, použije se výchozí hodnota Intune.|
ADALRedirectUri  | Řetězec  | Identifikátor URI aplikace pro přesměrování Azure AD | Pokud aplikace používá ADAL, je požadován ADALRedirectUri nebo ADALRedirectScheme.  |
ADALRedirectScheme  | Řetězec  | Schéma přesměrování Azure AD aplikace Dá se použít místo ADALRedirectUri, pokud má aplikace identifikátor URI pro přesměrování ve formátu `scheme://bundle_id`. | Pokud aplikace používá ADAL, je požadován ADALRedirectUri nebo ADALRedirectScheme. |
ADALLogOverrideDisabled | Logická hodnota  | Určuje, jestli SDK bude všechny protokoly ADAL (včetně všech případných volání ADAL z aplikace) směrovat do vlastního souboru protokolu. Výchozí hodnota je NE. Pokud aplikace chce nastavit vlastní zpětné volání protokolu ADAL, nastaví se hodnota ANO. | Volitelný parametr. |
ADALCacheKeychainGroupOverride | Řetězec  | Určuje skupinu řetězce klíčů, která se má použít pro mezipaměť ADAL místo com.microsoft.adalcache. Všimněte si, že nemá předponu app-id. Předpona se použije u zadaného řetězce za běhu. | Volitelný parametr. |
AppGroupIdentifiers | Pole řetězců  | Pole skupin aplikací z části com.apple.security.application-groups nároků aplikace. | Vyžaduje se, když aplikace využívá skupiny aplikací. |
ContainingAppBundleId | Řetězec | Určuje ID sady rozšíření obsahující aplikaci. | Vyžaduje se rozšíření pro iOS. |
DebugSettingsEnabled| Logická hodnota | Pokud je nastaveno na ANO, dají se uplatnit testovací zásady v rámci sady Nastavení. Publikované aplikace by *neměly* mít tohle nastavení povolené. | Volitelný parametr. |
MainNibFile<br>MainNibFile~ipad  | Řetězec  | Toto nastavení by mělo mít název souboru pro hlavní nib aplikace.  | Vyžaduje se, pokud aplikace v souboru Info.plist definuje MainNibFile. |
MainStoryboardFile<br>MainStoryboardFile~ipad  | Řetězec  | Toto nastavení by mělo obsahovat název souboru pro hlavní storyboard aplikace. | Vyžaduje se, pokud aplikace v souboru Info.plist definuje UIMainStoryboardFile. |
AutoEnrollOnLaunch| Logická hodnota| Určuje, zda se má aplikace pokusit o automatickou registraci při spuštění, pokud se zjistí existující spravovaná identita a aplikace se ještě nezaregistrovala. Výchozí hodnota je NE. <br><br> Poznámka: Pokud se nenajde žádná spravovaná identita nebo pokud v mezipaměti ADAL není platný token identity, pokus o registraci se bez upozornění nezdaří a nezobrazí se výzva k zadání přihlašovacích údajů, pokud ovšem aplikace nemá možnost MAMPolicyRequired nastavenou na hodnotu ANO. | Volitelný parametr. |
MAMPolicyRequired| Logická hodnota| Určuje, jestli se aplikaci zabrání ve spuštění, pokud nebude mít zásady ochrany aplikací Intune. Výchozí hodnota je NE. <br><br> Poznámka: Aplikace není možné odesílat do App Storu, pokud mají možnost MAMPolicyRequired nastavenou na ANO. Při nastavení možnosti MAMPolicyRequired na ANO je vhodné nastavit na ANO také možnost AutoEnrollOn. | Volitelný parametr. |
MAMPolicyWarnAbsent | Logická hodnota| Určuje, jestli aplikace při spuštění upozorní uživatele v případě, že nebude mít zásady ochrany aplikací Intune. <br><br> Poznámka: Po zavření upozornění budou uživatelé i nadále moci používat aplikaci bez zásad. | Volitelný parametr. |
MultiIdentity | Logická hodnota| Určuje, jestli aplikace umožňuje rozlišovat více identit. | Volitelný parametr. |
SplashIconFile <br>SplashIconFile~ipad | Řetězec  | Určuje soubor úvodní (spouštěcí) ikony Intune. | Volitelný parametr. |
SplashDuration | Číslo | Minimální doba v sekundách, po kterou se při spuštění aplikace bude zobrazovat úvodní obrazovka Intune. Výchozí hodnota je 1,5. | Volitelný parametr. |
BackgroundColor| Řetězec| Určuje barvu pozadí úvodní obrazovky a obrazovky se zadáváním kódu PIN. Zadat je možné šestnáctkový řetězec RGB ve formátu #XXXXXX, kde každé X může mít hodnotu 0–9 nebo A–F. Symbol křížku můžete vynechat.   | Volitelný parametr. Výchozí hodnota je světle šedá. |
ForegroundColor| Řetězec| Určuje barvu popředí úvodní obrazovky a obrazovky se zadáváním kódu PIN, jako je barva textu. Zadat je možné šestnáctkový řetězec RGB ve formátu #XXXXXX, kde každé X může mít hodnotu 0–9 nebo A–F. Symbol křížku můžete vynechat.  | Volitelný parametr. Výchozí hodnota je černá. |
AccentColor | Řetězec| Určuje barvu motivu obrazovky se zadáváním kódu PIN, například barvu textu tlačítka a zvýraznění pole. Zadat je možné šestnáctkový řetězec RGB ve formátu #XXXXXX, kde každé X může mít hodnotu 0–9 nebo A–F. Symbol křížku můžete vynechat.| Volitelný parametr. Výchozí hodnota je systémová modrá. |
MAMTelemetryDisabled| Logická hodnota| Určuje, jestli SDK nebude odesílat žádná telemetrická data do back-endu.| Volitelný parametr. |
WebViewHandledURLSchemes | Pole řetězců | Určuje schémata URL zpracovávaná komponentami WebView vaší aplikace. | Povinný parametr, pokud aplikace používá komponenty WebView, které zpracovávají adresy URL prostřednictvím odkazů nebo JavaScriptu. |  

> [!NOTE]
> Pokud bude aplikace vydaná v App Storu, možnost `MAMPolicyRequired` musí být podle standardů App Storu nastavená na NE.

## <a name="enabling-mam-targeted-configuration-for-your-ios-applications"></a>Povolení konfigurace určené pro správu mobilních aplikací pro iOS
Konfigurace určená pro správu mobilních aplikací (MAM) umožňuje aplikacím přijímat konfigurační data prostřednictvím sady SDK aplikace Intune. Formát a varianty těchto dat musí vlastník aplikace nebo její vývojář definovat a oznámit zákazníkům, kteří využívají Intune. Správci Intune mohou konfigurační data zacílit a nasadit prostřednictvím Intune na portálu Azure Portal. Od verze 7.0.1 sady Intune App SDK pro iOS můžou aplikace s konfigurací určenou pro MAM získávat prostřednictvím služby MAM konfigurační data určená pro správu mobilních zařízení. Konfigurační data aplikace se odešlou přímo do aplikace přes službu MAM, nikoliv prostřednictvím kanálu MDM. Sada Intune App SDK nabízí třídu pro přístup k datům načteným z těchto konzol. Následující požadavky je potřeba vzít v úvahu: <br>
* Kvůli přístupu k uživatelskému rozhraní pro konfiguraci MAM musí být aplikace zaregistrovaná ve službě Intune MAM. Další informace najdete v části [Příjem zásad ochrany aplikací](#receiving-app-protection-policy).
* Do zdrojových souborů aplikace je potřeba zahrnout soubor ```IntuneMAMAppConfigManager.h```.
* K získání konfiguračního objektu aplikace je potřeba volat ```[[IntuneMAMAppConfigManager instance] appConfigForIdentity:]```.
* U objektu ```IntuneMAMAppConfig``` je potřeba volat odpovídající selektor. Pokud je například klíčem aplikace řetězec, měli byste použít ```stringValueForKey``` nebo ```allStringsForKey```. Soubor ```IntuneMAMAppConfig.h header``` se týká vrácených hodnot / chybových podmínek.

Další informace o možnostech rozhraní Graph API s ohledem na hodnoty konfigurace určené pro MAM najdete v článku [Referenční informace o rozhraní Graph API týkající se konfigurace určené pro MAM](https://developer.microsoft.com/graph/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create). <br>

Další informace o vytváření zásad konfigurace aplikací určených pro MAM v iOSu najdete v části o konfiguraci aplikací určených pro MAM v článku [Použití zásad konfigurace aplikací v Microsoft Intune pro iOS](https://docs.microsoft.com/intune/app-configuration-policies-use-ios).

## <a name="telemetry"></a>Telemetrie

Intune App SDK pro iOS ve výchozím nastavení protokoluje telemetrická data týkající se následujících událostí použití. Tato data se odešlou do Microsoft Intune.

* **Spuštění aplikace**: Pomáhá službě Microsoft Intune zjistit informace o používání aplikací s MAM podle typu správy (MAM s MDM, MAM bez registrace MDM atd.).

* **Volání registrace**: Pomáhá službě Microsoft Intune zjistit míru úspěšnosti a další metriky výkonu volání registrace ze strany klienta.

> [!NOTE]
> Pokud se rozhodnete neodesílat telemetrická data sady Intune App SDK z vaší aplikace do Microsoft Intune, musíte zakázat zachycování telemetrie sady Intune App SDK. Ve slovníku IntuneMAMSettings nastavte vlastnost `MAMTelemetryDisabled` na ANO.

## <a name="enable-multi-identity-optional"></a>Povolení více identit (volitelné)

SDK ve výchozím nastavení uplatní zásady na aplikaci jako celek. Funkce více identit je funkcí MAM, kterou můžete povolit pro použití zásady na úrovni podle identity. K tomu je od aplikace potřeba větší účast než u ostatních funkcí MAM.

Aplikace musí svou sadu SDK informovat, když chce změnit aktivní identitu. SDK také oznámí aplikaci, kdy je změna identity nutná. V současné době je podporována jen jedna spravovaná identita. Jakmile uživatel zařízení nebo aplikaci zaregistruje, SDK tuto identitu použije a bude ji považovat za primární spravovanou. Ostatní uživatelé v aplikaci budou považováni za nespravované s nastavením zásad bez omezení.

Identita je definována jednoduše jako řetězec. V identitách se rozlišují malá a velká písmena. Žádosti odeslané sadě SDK je ale nemusí vrátit se stejnou velikostí písmen, s jakou byla identita nastavena.

### <a name="identity-overview"></a>Přehled identity

Identita je jednoduše uživatelské jméno účtu, například user@contoso.com). Vývojáři můžou identitu aplikace nastavit na těchto úrovních:

* **Identita procesu**: Stanoví identitu v rámci procesu a používá se hlavně pro aplikace s jedinou identitou. Tato identita ovlivňuje všechny úlohy a soubory a také uživatelské rozhraní.

* **Identita uživatelského rozhraní**: Určuje, jaké zásady se uplatní u úloh uživatelského rozhraní v hlavním vlákně, jako je vyjmutí, kopírování, vložení, PIN, ověřování, sdílení dat atd. Identita uživatelského rozhraní nemá vliv na úlohy se soubory jako šifrování, zálohování atd.

* **Identita vlákna**: Má vliv na to, jaké zásady se použijí pro aktuální vlákno. Tato identita ovlivňuje všechny úlohy a soubory a také uživatelské rozhraní.

Bez ohledu na to, jestli je uživatel spravován, zodpovídá za vhodné nastavení identit aplikace.

Každé vlákno má v každém okamžiku platnou identitu pro úlohy uživatelského rozhraní a pro úlohy se soubory. Jde o identitu, která kontroluje, jaké zásady (pokud vůbec) by se měly použít. Pokud identita chybí („žádná identita“) nebo uživatel není spravován, nepoužijí se žádné zásady. Níže uvedené diagramy znázorňují, jak se určují platné identity.

  ![Intune App SDK iOS: propojené architektury a knihovny](./media/ios-thread-identities.png)

### <a name="thread-queues"></a>Fronty vláken

Aplikace často expedují asynchronní a synchronní úlohy do front vláken. SDK zachycuje volání Grand Central Dispatch (GCD) a expedovaným úlohám přiřazuje aktuální identitu vlákna. Při dokončení úloh sada SDK dočasně změní identitu vlákna na identitu přidruženou úloze, úlohu dokončí a potom obnoví původní identitu vlákna.


Vzhledem k tomu, že je fronta `NSOperationQueue` postavená na GCD, úloha `NSOperations` poběží v době přidání do `NSOperationQueue` na identitě vlákna. Úloha `NSOperations` nebo funkce expedované přímo prostřednictvím GCD jsou při běhu také schopné změnit aktuální identitu vlákna. Tato identita přepíše identitu zděděnou od expedujícího vlákna.

### <a name="file-owner"></a>Vlastník souboru

Sada SDK sleduje identity místních vlastníků souborů a podle nich určuje, které zásady uplatnit. Vlastník souboru se určí při vytvoření souboru nebo jeho otevření v režimu zkrácení. Jako vlastník je nastavena platná identita pro úlohy se soubory náležející vláknu, které úlohu provádí.

Aplikace případně můžou identitu vlastníka souboru nastavit explicitně pomocí `IntuneMAMFilePolicyManager`. Pomocí `IntuneMAMFilePolicyManager` můžou aplikace načíst vlastníka souboru a nastavit identitu uživatelského rozhraní před zobrazením obsahu souboru.

### <a name="shared-data"></a>Sdílená data

Pokud aplikace vytvoří soubory obsahující data od spravovaných i nespravovaných uživatelů, zodpovídá pak za to, aby data spravovaných uživatelů byla zašifrovaná. Data můžete šifrovat pomocí rozhraní API `protect` a `unprotect` v `IntuneMAMDataProtectionManager`.

Metoda `protect` přijímá identitu spravovaného i nespravovaného uživatele. Pokud je uživatel spravován, data budou zašifrovaná. Pokud uživatel spravován není, hlavička přidaná k datům zašifruje identitu, ale data zašifrovaná nebudou. Vlastník dat se dá načíst pomocí metody `protectionInfo`.

### <a name="share-extensions"></a>Rozšíření pro sdílení

Pokud aplikace obsahuje rozšíření pro sdílení, vlastníka sdílené položky je možné načíst pomocí metody `protectionInfoForItemProvider` v `IntuneMAMDataProtectionManager`. Pokud je sdílenou položkou soubor, postará se o nastavení vlastníka souboru sada SDK. Pokud jsou sdílenou položkou data, bude za nastavení vlastníka souboru zodpovídat aplikace v případě, že má vlastník data v souboru uložená. Aplikace bude zodpovídat také za volání rozhraní API `setUIPolicyIdentity` před zobrazením těchto dat v uživatelském rozhraní.

### <a name="turning-on-multi-identity"></a>Zapnutí více identit

Ve výchozím nastavení se všechny aplikace považují za aplikace s jedinou identitou. SDK nastaví identitu procesu pro registrovaného uživatele. Pokud chcete povolit podporu více identit, přidejte do slovníku IntuneMAMSettings v souboru Info.plist aplikace logické nastavení s názvem `MultiIdentity` a hodnotou ANO.

> [!NOTE]
> Po povolení více identit se identita procesu, uživatelského rozhraní a vlákna nastaví na hodnotu nil. Aplikace zodpovídá za jejich příslušné nastavení.

### <a name="switching-identities"></a>Přepínání identit

* **Přepnutí identity iniciované aplikací**:

    Aplikace s více identitami jsou při spuštění považovány za aplikace běžící pod neznámým, nespravovaným účtem. Podmíněné spuštění uživatelského rozhraní neproběhne a po aplikaci nebudou vyžadovány žádné zásady. Aplikace zodpovídá za to, že sadě SDK vždy oznámí, že by měla být změněna identita. K tomu nejčastěji dochází, kdykoli se aplikace chystá zobrazit data konkrétního uživatelského účtu.

    Třeba když se uživatel pokusí na notebooku otevřít dokument, poštovní schránku nebo kartu. Aplikace musí SDK upozornit předtím, než se soubor, schránka nebo karta skutečně otevře. K tomu slouží rozhraní API `setUIPolicyIdentity` v `IntuneMAMPolicyManager`. Toto rozhraní API by se mělo zavolat bez ohledu na to, jestli jde o spravovaného uživatele. Pokud jde o spravovaného uživatele, SDK provede kontroly podmíněného spuštění (detekce jailbreaku, PIN a ověřování).

    Výsledek přepnutí identity se do aplikace vrátí asynchronně prostřednictvím obslužné rutiny dokončení. Aplikace by měla otevření dokumentu, poštovní schránky nebo karty odložit na vrácení úspěšného výsledného kódu. Pokud se přepnutí identity nepodaří, aplikace by měla úlohu zrušit.

* **Přepnutí identity iniciované sadou SDK**:

    V některý případech SDK žádá aplikaci, aby se přepnula na konkrétní identitu. Kvůli tomuto požadavku je potřeba, aby aplikace s více identitami implementovali metodu `identitySwitchRequired` z `IntuneMAMPolicyDelegate`.

    Pokud je aplikace po zavolání této metody schopna přepnout na požadovanou identitu, měla by obslužné rutině dokončení předat `IntuneMAMAddIdentityResultSuccess`. Pokud identitu přepnout nemůže, měla by obslužné rutině dokončení předat `IntuneMAMAddIdentityResultFailed`.

    V reakci na toto volání aplikace nemusí zavolat `setUIPolicyIdentity`. Pokud SDK po aplikaci chce, aby se přepnula na nespravovaný uživatelský účet, předá se volání `identitySwitchRequired` prázdný řetězec.

* **Selektivní vymazání**:

    Při selektivním vymazání aplikace volá sada SDK metodu `wipeDataForAccount` z `IntuneMAMPolicyDelegate`. Za odebrání zadaného uživatelského účtu a veškerých dat, která jsou s ním spojená, zodpovídá aplikace. SDK dokáže odebrat všechny soubory, které uživatel vlastní, a udělá to, pokud aplikace po zavolání `wipeDataForAccount` vrátí FALSE.

    Tato metoda se volá z vlákna na pozadí. Aplikace by neměly vracet hodnotu, dokud se neodeberou všechna data uživatele (s výjimkou souborů, u kterých aplikace vrací hodnotu FALSE).

## <a name="ios-best-practices"></a>Doporučené postupy pro iOS

Tady jsou uvedeny některé doporučené osvědčené postupy při vývoji pro iOS:

* Systém souborů iOS rozlišuje malá a velká písmena. Zajistěte, aby byla velká a malá písmena pro názvy souborů jako `libIntuneMAM.a` a `IntuneMAMResources.bundle` správná.

* Pokud má Xcode potíže s vyhledáním `libIntuneMAM.a`, můžete je vyřešit tak, že cestu k této knihovně přidáte do cest hledání linkeru.

## <a name="faqs"></a>Nejčastější dotazy


**Jsou všechna rozhraní API řešená nativním jazykem Swift nebo spoluprací jazyků Objective-C a Swift?**

Rozhraní API sady Intune App SDK jsou pouze v Objective-C a nepodporují **nativní** Swift. Vyžaduje se interoperabilita mezi Swift a Objective-C.


**Musí být všichni uživatelé mojí aplikace zaregistrovaní ve službě APP-WE?**

Ne. V Intune App SDK by se měly registrovat jen pracovní a školní účty. Za zjištění, jestli je účet používán jako pracovní nebo školní, zodpovídají aplikace.   

**A co uživatelé, kteří se už do aplikace přihlásili? Musí se zaregistrovat?**

Za registraci uživatelů, kteří úspěšně prošli ověřením, zodpovídá aplikace. Aplikace zodpovídá také za registraci jakýchkoli stávajících účtů, které mohly být k dispozici před tím, než měla aplikace funkci MDM bez MAM.   

Aplikace by k tomu měla použít metodu `registeredAccounts:`. Tato metoda vrací slovník NSDictionary obsahující všechny účty zaregistrované ve službě Intune MAM. Pokud v seznamu chybí některé existující účty, aplikace by je měla zjistit a zaregistrovat pomocí `registerAndEnrollAccount:`.

**Jak často SDK opakuje pokusy o registraci?**

Všechny předchozí registrace, které selhaly, zkouší SDK opakovat každých 24 hodin. SDK to dělá proto, aby se úspěšně zaregistrovali a obdrželi zásady i uživatelé, jejichž organizace zapnula MAM až po tom, co se do aplikace přihlásili.

SDK s opakovanými pokusy přestane, jakmile rozpozná, že uživatel aplikaci úspěšně zaregistroval. To je proto, že aplikaci může v jednom okamžiku zaregistrovat jen jeden uživatel. Pokud se registrace uživatele zruší, opakované pokusy začnou znovu ve stejném 24hodinnovém intervalu.

**Proč musí být registrace uživatele zrušena?**

Sada SDK na pozadí pravidelně provádí tyto akce:

 - Pokud aplikace ještě není zaregistrovaná, SDK se každých 24 hodin pokusí zaregistrovat všechny registrované účty.
 - Pokud je aplikace zaregistrovaná, sada SDK každých 8 hodin hledá aktualizace zásad ochrany aplikací.

Zrušení registrace uživatele sadu SDK upozorní, že uživatel už aplikaci nebude používat, a výše uvedené opakované události tak pro jeho účet není potřeba zajišťovat. Pokud to bude potřeba, spustí se tím také zrušení registrace aplikace a selektivní vymazání.

**Mám příznak doWipe v metodě pro zrušení registrace nastavit na hodnotu true?**

Tato metoda by se měla zavolat, než se uživatel z aplikace odhlásí.  Pokud se data uživatele odstraní z aplikace v rámci odhlášení, můžete `doWipe` nastavit na false. Pokud ale aplikace data uživatele neodebírá, doporučujeme nastavit `doWipe` na true, aby je mohla ručně odstranit sama sada SDK.

**Existují i jiné způsoby, jak zrušit registraci aplikace?**

Ano, správce IT může do aplikace poslat příkaz k selektivnímu vymazání. Tím se zruší registrace uživatele a vymažou jeho data. SDK tento scénář provede automaticky a prostřednictvím metody delegáta potom odešle oznámení.



## <a name="submit-your-app-to-the-app-store"></a>Odeslání aplikace do App Storu

Buildy statické knihovny i modelu pro Intune App SDK jsou univerzální binární soubory. To znamená, že mají kód pro všechny architektury zařízení a simulátoru. Když mají aplikace poslané do App Storu kód simulátoru, Apple je odmítne. Když kompilujete sestavení jenom pro zařízení pomocí statické knihovny, linker kód simulátoru automaticky odstraní. Postupujte podle následujících kroků a před nahráním aplikace do App Storu zkontrolujte, jestli je odebraný celý kód simulátoru.

1. Ujistěte se, že na ploše máte `IntuneMAM.framework`.

2. Spusťte tyto příkazy:

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    První příkaz odstraní architektury simulátoru ze souboru DYLIB modelu. Druhý příkaz zkopíruje soubor DYLIB jen pro zařízení zpět do adresáře modelu.
