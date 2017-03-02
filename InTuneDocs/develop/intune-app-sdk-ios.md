---
title: "Microsoft Intune App SDK pro iOS – Příručka pro vývojáře | Dokumentace Microsoftu"
description: "Microsoft Intune App SDK pro iOS umožňuje začlenit do vaší aplikace pro iOS zásady ochrany aplikace Intune, a to ve formě správy mobilních aplikací (MAM)."
keywords: 
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 96861614075d4eed41ca440af8a8cc42e5f2ff38
ms.openlocfilehash: 8633de5aea6cc3f98c5e331fc3de43daf85903ae
ms.lasthandoff: 02/23/2017


---

# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>Microsoft Intune App SDK pro iOS – Příručka pro vývojáře

> [!NOTE]
> Možná si budete chtít nejprve přečíst článek [Příručka Začínáme s Intune App SDK](intune-app-sdk-get-started.md), který vysvětluje postup přípravy integrace na jednotlivých podporovaných platformách.

Sada Microsoft Intune App SDK pro iOS umožňuje začlenit do vaší aplikace pro iOS zásady ochrany aplikací Intune označované také jako zásady MAM. Aplikace s povolenou funkcí MAM je integrovaná se sadou Intune App SDK. Umožňuje správcům IT nasadit zásady ochrany aplikací do mobilní aplikace, když Intune aplikaci aktivně spravuje.

## <a name="prerequisites"></a>Požadavky

* Potřebujete počítač s Mac OS, na kterém běží OS X 10.8.5 nebo novější a je na něm nainstalovaná sada nástrojů XCode verze 5 nebo novější.

* Přečtěte si [licenční podmínky Intune App SDK pro iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf). Vytisknout a uchovat pro své záznamy kopii licenčních podmínek. Stažením a použitím Intune App SDK pro iOS s licenčními podmínkami souhlasíte.  Pokud je nepřijímáte, software nepoužívejte.

* Stáhněte soubory pro sadu Intune App SDK pro iOS z [GitHubu](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios).

## <a name="whats-in-the-sdk"></a>Co je v sadě SDK

Intune App SDK pro iOS zahrnuje statickou knihovnu, soubory prostředků, záhlaví API, seznam vlastností (plist) s nastavením pro ladění a nástroj konfigurátoru. Mobilní aplikace můžou pro vynucení většiny zásad jednoduše zahrnout soubory prostředků a staticky se propojit ke knihovnám. Pokročilé funkce Intune MAM se vynucují prostřednictvím rozhraní API.

Tato příručka se věnuje tomu, jak používat následující komponenty sady Intune App SDK pro iOS:

* **libIntuneMAM.a**: Statická knihovna Intune App SDK. Pokud vaše aplikace nepoužívá rozšíření, připojte tuhle knihovnu k projektu, abyste aplikaci mohli spravovat pomocí Intune.

* **IntuneMAM.framework**: Model Intune App SDK. Pokud chcete aplikaci spravovat pomocí Intune, připojte tento model k projektu. Použijte ho místo statické knihovny v případě, že aplikace používá rozšíření, aby se v projektu nevytvořilo několik kopií statické knihovny.

* **IntuneMAMResources.bundle**: Sada prostředků s prostředky, které SDK využívá.

* **Hlavičky**: Zveřejňují rozhraní API sady Intune App SDK. Pokud použijete rozhraní API, musíte zahrnout soubor hlaviček, který toto rozhraní API obsahuje. Následující soubory hlaviček zahrnují volání funkcí API nutné k povolení funkcí Intune App SDK:

    * IntuneMAMAsyncResult.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMLogger.h


## <a name="how-the-intune-app-sdk-works"></a>Jak Intune App SDK funguje

Cílem sady Intune App SDK pro iOS je doplnit do aplikací pro iOS možnosti správy s minimálními změnami kódu. Čím méně je změn kódu, tím rychlejší může být uvedení aplikace na trh, přičemž konzistence a stabilita mobilní aplikace zůstávají beze změn.


## <a name="build-the-sdk-into-your-mobile-app"></a>Použití sady SDK v mobilní aplikaci

Pokud chcete povolit sadu Intune App SDK, postupujte takto:

1. **Možnost 1**: Vytvořte propojení s knihovnou `libIntuneMAM.a`. Přetáhněte knihovnu `libIntuneMAM.a` do **seznamu propojených modelů a knihoven** cíle projektu.
    ![Intune App SDK iOS: propojené architektury a knihovny](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    > [!NOTE]
    > Pokud se aplikaci chystáte vydat v App Storu, použijte prosím verzi `libIntuneMAM.a` sestavenou pro prodej, ne ladicí verzi. Prodejní verze bude ve složce **Release**. Ladicí verze má podrobný výstup určený k tomu, aby se v Intune App SDK snadněji řešily potíže.

    **Možnost 2**: K projektu připojte `IntuneMAM.framework`. Přetáhněte `IntuneMAM.framework` do **seznamu propojených modelů a knihoven** cíle projektu.

    > [!NOTE]
    > Pokud tento model použijete, nezapomeňte z univerzálního modelu před odesláním aplikace do App Storu odstranit architektury simulátoru. Viz část Odeslání aplikace do App Storu.

2. Do projektu přidejte tyto modely iOS:
    * MessageUI.framework
    * Security.framework
    * MobileCoreServices.framework
    * SystemConfiguration.framework
    * libsqlite3.dylib
    * libc++.dylib
    * ImageIO.framework
    * LocalAuthentication.framework
    * AudioToolbox.framework

    > [!NOTE]
    > Pokud je aplikace určená pro iOS 7, nastavte atribut `Status` modelu `LocalAuthentication.framework` na Volitelný. Bez nastaveného atributu `Status` se aplikace v iOSu 7 nespustí.
    >
    > Xcode 7 navíc přepnul rozšíření `.dylib` na `.tbd`.

3. Přidejte do projektu sadu prostředků `IntuneMAMResources.bundle`. Přetáhněte ji do části **Kopírovat prostředky balíčku** v rámci položky **Fáze buildu**.
![Intune App SDK iOS – kopírování prostředků sady](../media/intune-app-sdk-ios-copy-bundle-resources.png)

4. Přidejte `-force_load {PATH_TO_LIB}/libIntuneMAM.a` do následujících nastavení a nahraďte přitom `{PATH_TO_LIB}` umístěním Intune App SDK:
    * nastavení konfigurace buildu `OTHER_LDFLAGS` v projektu
    * nastavení **Další příznaky linkeru** uživatelského rozhraní<br>

    > [!NOTE]
    > Pokud chcete zjistit cestu `PATH_TO_LIB`, vyberte soubor `libIntuneMAM.a` a v nabídce **Soubor** klikněte na **Získat informace**. Cestu (údaj **Kde**) zkopírujte z části **Obecné** v okně **Informace**.

5. Pokud vaše mobilní aplikace definuje v souboru Info.plist hlavní Nib nebo Storyboard, odeberte pole souboru **Hlavní Storyboard** nebo **Hlavní Nib**. Hodnoty Storyboard nebo nib, které jste předtím odebrali, přidejte do nového slovníku nazvaného IntuneMAMSettings s následujícími názvy klíčů:
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad

    > [!NOTE]
    > Pokud mobilní aplikace v souboru Info.plist nedefinuje hlavní Nib nebo Storyboard, tato nastavení se nevyžadují.

    Soubor Info.plist můžete zobrazit v nezpracovaném formátu (abyste zjistili názvy klíčů) tak, že kliknete pravým tlačítkem kamkoli do těla dokumentu a změníte typ zobrazení na **Zobrazit nezpracované klíče/hodnoty**.

6. Povolte sdílení řetězce klíčů (pokud ještě není povolené) tak, že v každém cíli projektu kliknete na **Možnosti** a zapnete přepínač **Sdílení řetězce klíčů**. Sdílení řetězce klíčů se vyžaduje pro přechod k dalšímu kroku.

    > [!NOTE]
    > Profil zřizování musí podporovat nové hodnoty sdílení řetězce klíčů. Přístupové skupiny pro řetězce klíčů by měly podporovat zástupné znaky. Můžete to ověřit tak, že soubor .mobileprovision otevřete v textovém editoru, najdete **keychain-access-groups** a ověříte, že obsahuje zástupný znak. Například:
    ```xml
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```

7. Po povolení sdílení řetězce klíčů použijte následující postup a vytvořte samostatnou přístupovou skupinu, ve které se uloží data Intune App SDK. Přístupovou skupinu pro řetězce klíčů můžete vytvořit pomocí uživatelského rozhraní nebo pomocí souboru nároků.

    Pokud k vytvoření přístupové skupiny pro řetězce klíčů použijete uživatelské rozhraní:

    a. Pokud mobilní aplikace nemá definované žádné přístupové skupiny pro řetězce klíčů, přidejte jako první skupinu ID sady prostředků aplikace.

    b. Přidejte skupinu sdíleného řetězce klíčů `com.microsoft.intune.mam`. Tuto přístupovou skupinu používá Intune App SDK k ukládání dat.

    c. Do existujících přístupových skupin přidejte `com.microsoft.adalcache`.

    ![Intune App SDK iOS: sdílení řetězců klíčů](../media/intune-app-sdk-ios-keychain-sharing.png)

    Pokud k vytvoření přístupové skupiny pro řetězce klíčů používáte soubor nároků, předřaďte v tomto souboru tuto přístupovou skupinu pro řetězce klíčů s `$(AppIdentifierPrefix)`. Například:  

    * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
    * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    > [!NOTE]
    > Soubor nároků je soubor XML, který je pro vaši mobilní aplikaci jedinečný. Slouží k určení speciálních oprávnění a schopností v aplikaci pro iOS.

8. Pokud aplikace v souboru Info.plist definuje schémata URL, přidejte pro každé schéma URL další schéma s příponou `-intunemam`.

9. U mobilních aplikací vyvíjených pro iOS 9+ zahrňte všechny protokoly, které aplikace předává do `UIApplication canOpenURL`, do pole `LSApplicationQueriesSchemes` v souboru Info.plist této aplikace. Pro každý protokol uvedený v seznamu přidejte nový protokol s příponou `-intunemam`. Do pole musíte taky zahrnout `http-intunemam`, `https-intunemam`a `ms-outlook-intunemam` .

10. Pokud má aplikace ve svých nárocích definované skupiny aplikací, přidejte tyto skupiny jako pole řetězců do slovníku IntuneMAMSettings pod klíč `AppGroupIdentifiers`.

11. Připojte mobilní aplikaci ke knihovně Azure Directory Authentication Library (ADAL). Knihovna ADAL pro Objective C je [dostupná na GitHubu](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    > [!NOTE]
    > Sada Intune App SDK je testovaná s kódem větve zprostředkovatele ADAL ze dne 19. června 2015. Ověřte, že se připojujete k nejnovější/pracovní verzi knihovny ADAL.

12. Přidejte do projektu sadu prostředků `ADALiOSBundle.bundle`. Přetáhněte ji do části **Kopírovat prostředky balíčku** v rámci položky **Fáze buildu**.

13. Při připojování ke knihovně použijte parametr linkeru `-force_load PATH_TO_ADAL_LIBRARY`.

    Přidejte `-force_load {PATH_TO_LIB}/libADALiOS.a` do nastavení konfigurace buildu `OTHER_LDFLAGS` v projektu nebo do nastavení **Další příznaky linkeru** v uživatelském rozhraní. Hodnotu `PATH_TO_LIB` byste měli nahradit umístěním binárních souborů ADAL.



## <a name="set-up-azure-directory-authentication-library"></a>Nastavení knihovny ADAL (Azure Directory Authentication Library)

Intune App SDK využívá ADAL ke svému ověřování a k podmíněnému spuštění. Knihovnu ADAL potřebuje taky kvůli registraci identity uživatele ve službě MAM, která slouží ke správě ve scénářích bez registrace zařízení.

ADAL zpravidla vyžaduje, aby se aplikace registrovaly na Azure Active Directory (Azure AD) a získaly jedinečné ID (označované jako ID klienta) a další identifikátory. Zaručí se tak zabezpečení tokenů udělených aplikaci. Intune App SDK využívá při kontaktování Azure AD výchozí registrační hodnoty.  

Pokud aplikace pro scénář ověřování používá ADAL, musí používat stávající hodnoty registrace a přepsat výchozí hodnoty Intune App SDK. Tím se zajistí, že se uživatelům nebude výzva k ověřování zobrazovat dvakrát (jednou ze sady Intune App SDK a jednou z aplikace).

### <a name="adal-faqs"></a>Nejčastější dotazy k ADAL

**Jaké binární soubory ADAL mám používat?**

Intune App SDK v současnosti využívá zprostředkovatelskou větev [ADAL na GitHubu](https://github.com/AzureAD/azure-activedirectory-library-for-objc), aby podporovala aplikace, které vyžadují podmíněný přístup. (Tyto aplikace proto závisí na aplikaci Microsoft Authenticator.) Sada SDK je ale stále kompatibilní s hlavní větví ADAL. Používejte větev, která je vhodná pro vaši aplikaci.

**Jak připojím binární soubory ADAL?**

Přidejte `-force_load {PATH_TO_LIB}/libADALiOS.a` do nastavení konfigurace buildu `OTHER_LDFLAGS` v projektu nebo do nastavení **Další příznaky linkeru** v uživatelském rozhraní. Hodnotu `PATH_TO_LIB` byste měli nahradit umístěním binárních souborů ADAL. Kromě toho taky zkopírujte sadu ADAL do aplikace.  

Další podrobnosti najdete v pokynech [ADAL na GitHubu](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

**Jak se dá sdílet mezipaměť ADAL s dalšími aplikacemi, které jsou přihlášené prostřednictvím stejného zřizovacího profilu?**

Pokud aplikace nemá definované žádné přístupové skupiny pro řetězce klíčů, přidejte jako první skupinu ID sady prostředků aplikace.

Přidáním přístupových skupin `com.microsoft.adalcache` a `com.microsoft.workplacejoin` do nároků řetězce klíčů povolte jednotné přihlašování (SSO) ADAL.

V případě, že explicitně nastavujete skupinu pro sdílený řetězec klíčů mezipaměti, ujistěte se, že je nastavena na `<app_id_prefix>.com.microsoft.adalcache`. Pokud ho nepřepíšete, knihovna ADAL tohle nastavení provede za vás. Pokud chcete `com.microsoft.adalcache` nahradit vlastní skupinou řetězce klíčů, uveďte ji pomocí klíče `ADALCacheKeychainGroupOverride` v souboru Info.plist pod IntuneMAMSettings.

**Jak u sady Intune App SDK vynutit, aby používala nastavení ADAL, které už používá moje aplikace?**

Pokud už aplikace používá ADAL, přečtěte si část [Konfigurace nastavení pro sadu Intune App SDK](#configure-settings-for-the-intune-app-sdk), kde najdete informace o naplnění těchto nastavení:  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride


**Jak přepíšu adresu URL autority Azure AD specifickou adresou URL tenanta zadanou za běhu?**

Nastavte vlastnost `aadAuthorityUriOverride` na instanci IntuneMAMPolicyManager.

> [!NOTE]
> To by bylo potřeba ve scénáři MAM bez registrace zařízení, kdybyste chtěli sadě SDK povolit, aby znovu použila obnovovací token ADAL získaný aplikací.

SDK bude tuto adresu URL autority dále používat k obnovení zásad a veškerým následným žádostem o registraci, pokud hodnotu nesmažete nebo nezměníte.  Proto je důležité hodnotu smazat, když se uživatel organizace z aplikace odhlásí, a obnovit ji, když se přihlásí nový uživatel organizace.

**Co dělat, když ADAL pro ověřování používá sama aplikace?**

Pokud už aplikace využívá ADAL pro ověřování, vyžadují se následující akce:

1. Ve slovníku IntuneMAMSettings v souboru Info.plist projektu ke klíči s názvem `ADALClientId` zadejte ID klienta, které se má použít pro volání ADAL.

2. Ve slovníku IntuneMAMSettings s názvem klíče `ADALAuthority` zadejte autoritu Azure AD.

3. Ve slovníku IntuneMAMSettings s názvem klíče `ADALRedirectUri` zadejte identifikátor URI pro přesměrování, který se má použít pro volání ADAL. Budete možná muset zadat také `ADALRedirectScheme`. To záleží na formátu identifikátoru URI přesměrování vaší aplikace.

**Co když už moje aplikace k ověřování nepoužívá ADAL?**

Pokud vaše aplikace nepoužívá ADAL, bude sada Intune App SDK poskytovat výchozí hodnoty pro parametry ADAL a zpracovávat ověřování proti Azure AD.

## <a name="register-your-app-with-the-intune-mam-service"></a>Registrace aplikace ve službě Intune MAM

### <a name="use-the-apis"></a>Použití rozhraní API
Sada Intune App SDK teď aplikacím pro iOS umožňuje přijímat z Intune zásady ochrany aplikací bez toho, aby musely být do Intune zaregistrované v rámci systému správy mobilních zařízení (MDM). Tuto funkci sada SDK poskytuje prostřednictvím nových rozhraní API, která aplikacím umožňují zásady ochrany aplikací přijímat. Pokud chcete používat nová rozhraní API, postupujte takto:

1. Použijte nejnovější vydání Intune App SDK, které podporuje správu aplikací s registrací i bez registrace zařízení. .

2. Do všech souborů, které budou volat rozhraní API, přidejte IntuneMAMEnrollment.h.

### <a name="register-accounts"></a>Registrace účtů

Aplikace může ze služby Intune přijímat zásady ochrany aplikací, pokud je registrovaná jménem konkrétního uživatelského účtu. Aplikace zodpovídá za registraci jakýchkoli nově přihlášených uživatelů v Intune App SDK. Po ověření nového uživatelského účtu by aplikace měla zavolat metodu `registerAndEnrollAccount`, kterou najdete v umístění Headers/IntuneMAMEnrollment.h:

```objc
/**


 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;

```
Po zavolání metody `registerAndEnrollAccount` SDK uživatelský účet zaregistruje a pokusí se jeho jménem zaregistrovat aplikaci. Pokud se registrace z jakéhokoli důvodu nepodaří, SDK se o ni automaticky znovu pokusí za 24 hodin. Za účelem ladění může aplikace prostřednictvím delegáta přijímat oznámení o výsledcích veškerých žádostí o registraci.

Po zavolání tohoto rozhraní API může aplikace dál normálně fungovat. Pokud se registrace podaří, SDK uživateli oznámí, že se vyžaduje restartování aplikace. V tu chvíli může uživatel aplikaci hned restartovat.

### <a name="deregister-accounts"></a>Zrušení registrace účtů

Než se uživatel z aplikace odhlásí, měla by aplikace zrušit jeho registraci v SDK. Díky tomu:

1. Nebudou probíhat opětovné pokusy o registraci tohoto uživatelského účtu.

2. Pokud uživatel aplikaci úspěšně zaregistroval, registrace uživatele i aplikace se ve službě Intune MAM zruší a zásady ochrany aplikací se odeberou.

3. Pokud aplikace zahájí (volitelné) selektivní vymazání, odstraní se jakákoli data související s prací nebo školou.

Před odhlášením uživatele by aplikace měla zavolat následující API z umístění Headers/IntuneMAMEnrollment.h:

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

Metoda musí být volána před odstraněním tokenů Azure AD uživatelského účtu. SDK uživatelův token aplikace potřebuje, aby mohla jeho jménem posílat službě Intune MAM určité požadavky.

Pokud aplikace pracovní nebo školní data uživatele odstraní sama, může být příznak `doWipe` nastaven na false. Jinak může aplikace přimět sadu SDK k zahájení selektivního vymazání. Výsledkem bude volání delegáta selektivního vymazání aplikace.

```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

### <a name="enroll-without-prior-sign-in"></a>Registrace bez předchozího přihlášení

Aplikace, která uživatele nepřihlašuje pomocí Azure Active Directory, může od služby Intune přijímat zásady ochrany aplikací, pokud zavolá rozhraní API, které nechá ověření vyřídit prostřednictvím sady SDK. Aplikace by tento postup měly používat, když neověřily uživatele pomocí Azure AD, ale potřebují načítat zásady ochrany aplikací na pomoc s ochranou dat. (například, když se k ověřování přihlášení aplikace používá jiná služba ověřování nebo když aplikace přihlašování vůbec nepodporuje). Aplikace to provede zavoláním metody `loginAndEnrollAccount` z umístění Headers/IntuneMAMEnrollment.h:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;

```

Zavoláním této metody vyzve SDK uživatele k zadání přihlašovacích údajů, pokud nejde najít žádný existující token. SDK se pak pokusí zaregistrovat aplikaci jménem tohoto účtu. Metodu je možné volat s identitou nil. V takovém případě provede SDK registraci s existujícím uživatelem MAM, kterého najde na zařízení, nebo pokud žádného takového nenajde, vyzve uživatele k zadání uživatelského jména.

Pokud se registrace nepovede, aplikace by na základě podrobností selhání měla zvážit, jestli rozhraní API nezavolá za nějaký čas znovu. Aplikace může prostřednictvím delegáta přijímat oznámení o výsledcích veškerých žádostí o registraci.

Po zavolání tohoto rozhraní API může aplikace dál normálně fungovat. Pokud se registrace podaří, SDK uživateli oznámí, že se vyžaduje restartování aplikace.

## <a name="status-result-and-debug-notifications"></a>Oznámení o stavu, výsledku a ladění

Aplikace může přijmout oznámení o stavu, výsledku a ladění v souvislosti s následujícími požadavky na službu Intune MAM:

 - Žádosti o registraci
 - Žádosti o aktualizaci zásad
 - Žádosti o zrušení registrace

Oznámení se zobrazují prostřednictvím metod delegáta, které najdete v umístění Headers/IntuneMAMEnrollmentDelegate.h:

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

Tento objekt je definovaný v IntuneMAMEnrollmentStatus.h, kde jsou popsané také konkrétní stavové kódy, které se můžou vrátit.




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
Z hodnoty vrácené z této metody SDK pozná, jestli aplikace požadované restartování zvládne sama:   

 - Pokud se vrátí hodnota true, aplikace si zajistí restartování.   

 - Pokud se vrátí hodnota false, aplikaci následně restartuje SDK. Sada SDK ihned zobrazí dialogové okno, které uživatele vyzve k restartování aplikace.

## <a name="customize-your-apps-behavior"></a>Přizpůsobení chování aplikace

Sada Intune App SDK má několik rozhraní API, které můžete volat, abyste získali informace o zásadách ochrany aplikací Intune nasazených do aplikace. Pomocí těchto dat můžete přizpůsobit chování aplikace. Většinu nastavení zásad ochrany aplikací automaticky vynucuje sada SDK, nikoli aplikace. Jediné nastavení, které by aplikace měla implementovat, je ovládací prvek Uložit jako.

### <a name="get-the-app-protection-policy-settings"></a>Získání nastavení zásad ochrany aplikací

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
* IntuneMAMSaveLocationBox
* IntuneMAMSaveLocationDropbox
* IntuneMAMSaveLocationGoogleDrive
* IntuneMAMSaveLocationLocalDrive

Aplikace by měly konstanty v rozhraní API **isSaveToAllowedForLocation** používat k zjištění, jestli je možné data ukládat do umístění považovaných za „spravovaná“, jako je OneDrive pro firmy, nebo za „osobní“. Kromě toho by se mělo rozhraní API použít, když aplikace není schopná zjistit, jestli je umístění „spravované“, nebo „osobní“.

Umístění, o kterých se ví, že jsou „osobní“, jsou vyjádřená konstantou `IntuneMAMSaveLocationOther`.

Konstanta `IntuneMAMSaveLocationLocalDrive` by se měla použít, když aplikace ukládá data do jakéhokoli umístění na místním zařízení.

## <a name="configure-settings-for-the-intune-app-sdk"></a>Konfigurace nastavení pro sadu Intune App SDK

K nastavení a konfiguraci sady Intune App SDK se používá slovník **IntuneMAMSettings** ze souboru Info.plist aplikace. Následující tabulka uvádí seznam všech podporovaných nastavení.

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
MAMPolicyRequired| Logická hodnota| Určuje, jestli se aplikaci zabrání ve spuštění, pokud nebude mít zásady ochrany aplikací Intune. Výchozí hodnota je NE. <br><br> Poznámka: Aplikace odeslané do App Storu nemůžou mít možnost MAMPolicyRequired nastavenou na ANO. | Volitelný parametr. |
MAMPolicyWarnAbsent | Logická hodnota| Určuje, jestli aplikace při spuštění upozorní uživatele v případě, že nebude mít zásady ochrany aplikací Intune. Aplikace odeslané do Storu nemůžou mít tuto možnost nastavenou na ANO. | Volitelný parametr. |
MultiIdentity | Logická hodnota| Určuje, jestli aplikace umožňuje rozlišovat více identit. | Volitelný parametr. |
SplashIconFile <br>SplashIconFile~ipad | Řetězec  | Určuje soubor úvodní (spouštěcí) ikony Intune. | Volitelný parametr. |
SplashDuration | Číslo | Minimální doba v sekundách, po kterou se při spuštění aplikace bude zobrazovat úvodní obrazovka Intune. Výchozí hodnota je 1,5. | Volitelný parametr. |
BackgroundColor| Řetězec| Určuje barvu pozadí úvodní obrazovky a obrazovky se zadáváním kódu PIN. Zadat je možné šestnáctkový řetězec RGB ve formátu #XXXXXX, kde každé X může mít hodnotu 0–9 nebo A–F. Symbol křížku můžete vynechat.   | Volitelný parametr. Výchozí hodnota je světle šedá. |
ForegroundColor| Řetězec| Určuje barvu popředí úvodní obrazovky a obrazovky se zadáváním kódu PIN, jako je barva textu. Zadat je možné šestnáctkový řetězec RGB ve formátu #XXXXXX, kde každé X může mít hodnotu 0–9 nebo A–F. Symbol křížku můžete vynechat.  | Volitelný parametr. Výchozí hodnota je černá. |
AccentColor | Řetězec| Určuje barvu motivu obrazovky se zadáváním kódu PIN, například barvu textu tlačítka a zvýraznění pole. Zadat je možné šestnáctkový řetězec RGB ve formátu #XXXXXX, kde každé X může mít hodnotu 0–9 nebo A–F. Symbol křížku můžete vynechat.| Volitelný parametr. Výchozí hodnota je systémová modrá. |
MAMTelemetryDisabled| Logická hodnota| Určuje, jestli SDK nebude odesílat žádná telemetrická data do back-endu.| Volitelný parametr. |

> [!NOTE]
> Pokud bude aplikace vydaná v App Storu, možnost `MAMPolicyRequired` musí být podle standardů App Storu nastavená na NE.

## <a name="telemetry"></a>Telemetrie

Intune App SDK pro iOS ve výchozím nastavení protokoluje telemetrická data týkající se následujících událostí použití. Tato data se odešlou do Microsoft Intune.

* **Spuštění aplikace**: Pomáhá službě Microsoft Intune zjistit informace o používání aplikací s MAM podle typu správy (MAM s MDM, MAM bez registrace MDM atd.).

* **Volání registrace**: Pomáhá službě Microsoft Intune zjistit míru úspěšnosti a další metriky výkonu volání registrace ze strany klienta.

> [!NOTE]
> Pokud se rozhodnete neodesílat telemetrická data sady Intune App SDK z vaší aplikace do Microsoft Intune, musíte zakázat zachycování telemetrie sady Intune App SDK. Ve slovníku IntuneMAMSettings nastavte vlastnost `MAMTelemetryDisabled` na ANO.

## <a name="enable-multi-identity-optional"></a>Povolení více identit (volitelné)

SDK ve výchozím nastavení uplatní zásady na aplikaci jako celek. Funkce více identit je funkcí MAM, kterou můžete povolit pro použití zásady na úrovni podle identity. K tomu je od aplikace potřeba větší účast než u ostatních funkcí MAM.

Aplikace musí svou sadu SDK informovat, když chce změnit aktivní identitu. SDK také oznámí aplikaci, kdy je změna identity nutná. V současné době je podporována jen jedna spravovaná identita. Jakmile uživatel zařízení nebo aplikaci zaregistruje, SDK tuto identitu použije a bude ji považovat za primární spravovanou. Ostatní uživatelé v aplikaci budou považováni za nespravované s nastavením zásad bez omezení.

Pamatujte si, že identita je definována jednoduše jako řetězec. V identitách se rozlišují malá a velká písmena. Žádosti odeslané sadě SDK je ale nemusí vrátit se stejnou velikostí písmen, s jakou byla identita nastavena.

### <a name="identity-overview"></a>Přehled identity

Identita je jednoduše uživatelské jméno účtu, například user@contoso.com). Vývojáři můžou identitu aplikace nastavit na těchto úrovních:

* **Identita procesu**: Stanoví identitu v rámci procesu a používá se hlavně pro aplikace s jedinou identitou. Tato identita ovlivňuje všechny úlohy a soubory a také uživatelské rozhraní.

* **Identita uživatelského rozhraní**: Určuje, jaké zásady se uplatní u úloh uživatelského rozhraní v hlavním vlákně, jako je vyjmutí, kopírování, vložení, PIN, ověřování, sdílení dat atd. Identita uživatelského rozhraní nemá vliv na úlohy se soubory jako šifrování, zálohování atd.

* **Identita vlákna**: Má vliv na to, jaké zásady se použijí pro aktuální vlákno. Tato identita ovlivňuje všechny úlohy a soubory a také uživatelské rozhraní.

Bez ohledu na to, jestli je uživatel spravován, zodpovídá za vhodné nastavení identit aplikace.

Každé vlákno má v každém okamžiku platnou identitu pro úlohy uživatelského rozhraní a pro úlohy se soubory. Jde o identitu, která kontroluje, jaké zásady (pokud vůbec) by se měly použít. Pokud identita chybí („žádná identita“) nebo uživatel není spravován, nepoužijí se žádné zásady. Níže uvedené diagramy znázorňují, jak se určují platné identity.

  ![Intune App SDK iOS: propojené architektury a knihovny](../media/intune-app-sdk/ios-thread-identities.png)

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

## <a name="debug-the-intune-app-sdk-in-xcode"></a>Ladění Intune App SDK v Xcode

Před ručním testováním aplikace s podporou MAM pomocí Microsoft Intune můžete v Xcode použít soubor Settings.bundle. Můžete tak nastavit zásady testování a není potřeba připojení k Intune. Postup při povolení:

1. Soubor Settings.bundle přidejte kliknutím pravým tlačítkem na složku nejvyšší úrovně ve svém projektu. V nabídce vyberte **Přidat** > **Nový soubor**. V části **Prostředky** vyberte šablonu **Settings Bundle**.

2. Jenom u sestavení pro ladění zkopírujte MAMDebugSettings.plist do Settings.bundle.

3. V části Root.plist (které je v Settings.bundle) přidejte předvolbu s `Type` = `Child Pane` a `FileName` = `MAMDebugSettings`.

4. V **Nastavení** > **Název_aplikace** přepněte **Povolit zásady testování**.

5. Spusťte aplikaci (v prostředí Xcode nebo mimo ně).

6. V **Nastavení** > **Název_aplikace** > **Povolit zásady testování** zapněte zásadu, třeba **PIN**.

7. Spusťte aplikaci (v prostředí Xcode nebo mimo ně). Ověřte, že PIN funguje podle očekávání.

> [!NOTE]
> Teď můžete prostřednictvím možností **Nastavení** > **Název_aplikace** > **Povolit zásady testování** povolit a přepínat nastavení.

## <a name="ios-best-practices"></a>Doporučené postupy pro iOS

Tady jsou uvedeny některé doporučené osvědčené postupy při vývoji pro iOS:

* Systém souborů iOS rozlišuje malá a velká písmena. Zajistěte, aby byla velká a malá písmena pro názvy souborů jako `libIntuneMAM.a` a `IntuneMAMResources.bundle` správná.

* Pokud má Xcode potíže s vyhledáním `libIntuneMAM.a`, můžete je vyřešit tak, že cestu k této knihovně přidáte do cest hledání linkeru.

## <a name="faq"></a>Nejčastější dotazy


**Jsou všechna rozhraní API řešená nativním jazykem Swift nebo spoluprací jazyků Objective-C a Swift?**

Rozhraní API sady Intune App SDK jsou pouze v objective-C a nepodporují nativní Swift.  


**Musí být všichni uživatelé mojí aplikace zaregistrovaní ve službě MAM?**

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

Buildy statické knihovny i modelu pro Intune App SDK jsou univerzální binární soubory. To znamená, že mají kód pro všechny architektury zařízení a simulátoru. Když mají aplikace poslané do App Storu kód simulátoru, Apple je odmítne. Když kompilujete buildy jen pro zařízení pomocí statické knihovny, linker kód simulátoru automaticky odstraní. Postupujte podle následujících kroků a před nahráním aplikace do App Storu zkontrolujte, jestli je odebraný celý kód simulátoru.

1. Ujistěte se, že na ploše máte `IntuneMAM.framework`.

2. Spusťte tyto příkazy:

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    První příkaz odstraní architektury simulátoru ze souboru DYLIB modelu. Druhý příkaz zkopíruje soubor DYLIB jen pro zařízení zpět do adresáře modelu.

