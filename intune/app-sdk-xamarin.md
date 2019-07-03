---
title: Xamarinové vazby sady Microsoft Intune App SDK
description: Xamarinové vazby sady Intune App SDK umožňují v aplikacích pro iOS a Android vytvořených v Xamarinu povolit zásady ochrany aplikací Intune.
keywords: SDK, Xamarin, Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/08/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: f404fb63f64f216c3732a4378fce383591d95565
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2019
ms.locfileid: "67529037"
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Xamarinové vazby sady Microsoft Intune App SDK

> [!NOTE]
> Možná si budete chtít nejdřív přečíst článek [Začínáme s Intune App SDK](app-sdk-get-started.md), který vysvětluje postup přípravy integrace na jednotlivých podporovaných platformách.

## <a name="overview"></a>Přehled
[Xamarinové vazby sady Intune App SDK](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) umožňují v aplikacích pro iOS a Android vytvořených v Xamarinu povolit [zásady ochrany aplikací Intune](app-protection-policy.md). Tyto vazby umožňují vývojářům jednoduše do aplikací založených na Xamarinu začlenit funkce ochrany aplikace Intune.

Xamarinové vazby sady Microsoft Intune App SDK umožňují začlenit do vašich aplikací vyvíjených v Xamarinu zásady ochrany aplikací Intune (také označované jako zásady APP nebo MAM). Aplikace s povolenou funkcí MAM je integrovaná se sadou Intune App SDK. Správci IT můžou zásady ochrany aplikací nasadit do vaší mobilní aplikace, když Intune tuto aplikaci aktivně spravuje.

## <a name="whats-supported"></a>Co se podporuje

### <a name="developer-machines"></a>Počítače pro vývojáře
* Windows (Visual Studio verze 15.7+)
* macOS

### <a name="mobile-app-platforms"></a>Platformy pro mobilní aplikace
* Android
* iOS

### <a name="intune-mobile-application-management-scenarios"></a>Scénáře Správy mobilních aplikací Intune

* Intune APP-WE (bez registrace zařízení)
* Zařízení zaregistrovaná v Intune MDM
* Zařízení zaregistrovaná v EMM třetích stran

Xamarinové aplikace vytvořené xamarinovými vazbami sady Intune App SDK přijímají zásady ochrany aplikací Intune na zařízeních zaregistrovaných ve správě mobilních zařízení (MDM) Intune i na neregistrovaných zařízeních.

## <a name="prerequisites"></a>Požadavky

Přečtěte si [licenční podmínky](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf). Vytisknout a uchovat pro své záznamy kopii licenčních podmínek. Stažením a použitím xamarinových vazeb sady Intune App SDK přijímáte tyto licenční podmínky. Pokud je nepřijímáte, software nepoužívejte.

Sada SDK spoléhá na [Active Directory Authentication Library (ADAL)](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) pro jeho [ověřování](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) a podmíněného spuštění scénáře, které vyžadují, aby byly aplikace nakonfigurovány s [Azure Active Adresář](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). 

Pokud vaše aplikace je již nakonfigurována pro použití ADAL nebo MSAL a má vlastní vlastní klientské ID používá k ověřování pomocí Azure Active Directory, ujistěte se, že se postup, jak udělit oprávnění aplikace Xamarin pro správu mobilních aplikací Intune (MAM) služby potom následují. Postupujte podle pokynů v "[vaší aplikaci dáte přístup ke službě Intune app protection](app-sdk-get-started.md#give-your-app-access-to-the-intune-app-protection-service-optional)" část [Začínáme s Intune SDK průvodce](app-sdk-get-started.md).

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Povolení zásad ochrany aplikací Intune v mobilní aplikaci pro iOS
1. Do svého projektu Xamarin.iOS přidejte [balíček NuGet Microsoft.Intune.MAM.Xamarin.iOS](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS).
2. Při integraci sady Intune App SDK do mobilní aplikace pro iOS dodržujte obecné pokyny. Začněte od 3. kroku popsaného v [příručce pro vývojáře k sadě Intune App SDK pro iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). Poslední krok v této části spuštění nástroje IntuneMAMConfigurator můžete přeskočit, protože tento nástroj je součástí balíčku Microsoft.Intune.MAM.Xamarin.iOS a spustí se automaticky při sestavení.
    **Důležité**: Povolení sdílení pro aplikaci pro řetězce klíčů se mírně liší v sadě Visual Studio z nástroje Xcode. Otevřete soubor Entitlements.plist aplikace a zkontrolujte, že je povolená možnost „Enable Keychain“ (Povolit klíčenku) a že jsou do oddílu přidané odpovídající skupiny pro sdílení klíčenky. Zkontrolujte, že je v poli „Custom Entitlements“ (Vlastní oprávnění) v možnostech podepsání sady prostředků aplikace pro iOS zadaný soubor Entitlements.plist, a to pro všechny kombinace konfigurace a platformy, které připadají v úvahu.
3. Jakmile přidáte vazby a aplikaci správně nakonfigurujete, může aplikace začít používat rozhraní API sady Intune SDK. Aby to bylo možné, musíte přidat následující obor názvů:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. Aby aplikace mohly začít přijímat zásady ochrany, musíte je zaregistrovat do služby Intune MAM. Pokud vaše aplikace nepoužívá k ověřování uživatelů knihovnu [ADAL](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) (Azure Active Directory Authentication Library) ani [MSAL](https://www.nuget.org/packages/Microsoft.Identity.Client) (Microsoft Authentication Library) a chtěli byste ověřování svěřit sadě Intune SDK, měla by aplikace poskytovat metodě LoginAndEnrollAccount třídy IntuneMAMEnrollmentManager hlavní název uživatele (UPN):
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```
      Aplikace mohou předat hodnotu null, pokud hlavní název uživatele není v době volání známý. V takovém případě budou uživatelé vyzváni k zadání e-mailové adresy a hesla.
      
      Pokud vaše aplikace už k ověřování uživatelů používá knihovnu ADAL nebo MSAL, můžete mezi aplikací a sadou Intune SDK nakonfigurovat jednotné přihlašování. Nejprve budete muset nakonfigurovat knihovnu ADAL/MSAL tak, aby se tokeny ukládaly ve stejné přístupové skupině řetězce klíčů, kterou používají xamarinové vazby pro iOS (com.microsoft.adalcache). Pro knihovny ADAL, Uděláte to tak [nastavení vlastnosti iOSKeychainSecurityGroup objektu kontextu AuthenticationContext](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet/wiki/iOS-Keychain-Access). Pro MSAL, budete muset [nastavit vlastnost iOSKeychainSecurityGroup PublicClientApplication](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet/wiki/Xamarin-iOS-specifics#enable-keychain-access). Dále budete muset přepsat výchozí nastavení služby AAD používaná sadou Intune SDK těmi, která používá vaše aplikace. Můžete to udělat prostřednictvím slovníku IntuneMAMSettings v souboru Info.plist aplikace podle popisu v [příručce pro vývojáře k sadě Intune App SDK pro iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk) nebo můžete použít vlastnosti přepisu AAD v instanci IntuneMAMPolicyManager. Způsob se souborem Info.plist se doporučuje použít u aplikací se statickým nastavením ADAL. Vlastnosti přepisu se doporučují použít u aplikací, které tyto hodnoty zjišťují za běhu. Po konfiguraci všech nastavení jednotného přihlašování by vaše aplikace měla metodě RegisterAndEnrollAccount třídy IntuneMAMEnrollmentManager po úspěšném ověření poskytnout hlavní název uživatele (UPN):
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      Aplikace mohou určit výsledek pokusu o registraci implementací metody EnrollmentRequestWithStatus v podtřídě IntuneMAMEnrollmentDelegate a nastavením vlastnosti Delegate třídy IntuneMAMEnrollmentManager na instanci této třídy. Příklad najdete v naší [ukázkové aplikaci Xamarin.iOS](https://github.com/msintuneappsdk/sample-intune-xamarin-ios).

      Po úspěšné registraci mohou aplikace určit hlavní název uživatele zaregistrovaného účtu (pokud předtím nebyl známý) dotazem na následující vlastnost: 
      ```csharp
       string enrolledAccount = IntuneMAMEnrollmentManager.Instance.EnrolledAccount;
      ```      
> [!NOTE] 
> Pro iOS není k dispozici nástroj pro přemapování. Integrace do aplikace Xamarin.Forms by měla být stejná jako u normálního projektu Xamarin.iOS. 

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Povolení zásad Intune App Protection v mobilní aplikaci pro Android

1. Do svého projektu Xamarin.Android přidejte [balíček NuGet Microsoft.Intune.MAM.Xamarin.Android](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android).
    1. Pro aplikaci Xamarin.Forms, přidejte [balíčku Microsoft.Intune.mam.remapper.Tasks, kvůli NuGet](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) do projektu Xamarin.Android. 
2. Postupujte podle obecných kroků potřebných k [integraci sady Intune App SDK](app-sdk-android.md) do mobilní aplikace pro Android při odkazování na tento dokument pro další podrobnosti.

### <a name="xamarinandroid-integration"></a>Integrace Xamarin.Android

Úplný přehled pro integraci sady Intune App SDK najdete v [Microsoft Intune App SDK pro Android developer průvodce](app-sdk-android.md). Přečtěte si v příručce a integrace s aplikací Xamarin sady Intune App SDK v následujících částech jsou určeny zvýrazněte rozdíly mezi implementací pro nativní aplikace pro Android vyvinuté v jazyce Java a Xamarin aplikace vyvinuté v C#. Tyto části by se měla zpracovávat jako doplňkové a nemůže fungovat jako náhradu přečtete průvodce v celém rozsahu.

#### <a name="renamed-methodsapp-sdk-androidmdrenamed-methods"></a>[Přejmenované metody](app-sdk-android.md#renamed-methods)
V mnoha případech je metoda dostupná ve třídě Androidu označená v náhradní třídě MAM jako finální. Náhradní třída MAM pak poskytuje metodu s podobným názvem (s příponou `MAM`), kterou byste měli přepsat místo toho. Třeba při odvozování od třídy `MAMActivity` musí `Activity` místo přepsání `OnCreate()` a volání `base.OnCreate()` přepsat `OnMAMCreate()` a volat `base.OnMAMCreate()`.

#### <a name="mam-applicationapp-sdk-androidmdmamapplication"></a>[Aplikace MAM](app-sdk-android.md#mamapplication)
Musíte definovat aplikaci `Android.App.Application` třídu odvozenou od `MAMApplication`. Zkontrolujte, že podtřída je správně doplněna o atribut `[Application]` a že přepisuje konstruktor `(IntPtr, JniHandleOwnership)`.
```csharp
    [Application]
    class TaskrApp : MAMApplication
    {
    public TaskrApp(IntPtr handle, JniHandleOwnership transfer)
        : base(handle, transfer) { }
```
> [!NOTE]
> Problém s vazbami MAM Xamarin může způsobit, že aplikace k chybě při nasazení v režimu ladění. Jako alternativní řešení `Debuggable=false` atribut musí být přidané do `Application` třídy a `android:debuggable="true"` příznak je třeba odebrat z manifestu byl ručně nastavený.

#### <a name="enable-features-that-require-app-participationapp-sdk-androidmdenable-features-that-require-app-participation"></a>[Povolení funkcí, které vyžadují zapojení aplikace](app-sdk-android.md#enable-features-that-require-app-participation)
Příklad: Určení, zda je aplikace vyžaduje PIN kód
```csharp
MAMPolicyManager.GetPolicy(currentActivity).IsPinRequired;
```
Příklad: Určení primárního uživatele Intune
```csharp
IMAMUserInfo info = MAMComponents.Get<IMAMUserInfo>();
return info?.PrimaryUser;
```
Příklad: Určí, zda ukládání na zařízení nebo cloudové úložiště je povolený.
```csharp
MAMPolicyManager.GetPolicy(currentActivity).GetIsSaveToLocationAllowed(SaveLocation service, String username);
```

#### <a name="register-for-notifications-from-the-sdkapp-sdk-androidmdregister-for-notifications-from-the-sdk"></a>[Registrace k oznámením z SDK](app-sdk-android.md#register-for-notifications-from-the-sdk)
Vaše aplikace musí k oznámením z SDK registrovat vytvořením `MAMNotificationReceiver` a její registrací pomocí `MAMNotificationReceiverRegistry`. To se uvede příjemce a typ požadovaného v oznámení `App.OnMAMCreate`, jak ukazuje následující příklad:
```csharp
public override void OnMAMCreate()
{
    // Register the notification receivers
    IMAMNotificationReceiverRegistry registry = MAMComponents.Get<IMAMNotificationReceiverRegistry>();
    foreach (MAMNotificationType notification in MAMNotificationType.Values())
    {
        registry.RegisterReceiver(new ToastNotificationReceiver(this), notification);
    }
    ...
```

#### <a name="mam-enrollment-managerapp-sdk-androidmdmamenrollmentmanager"></a>[Správce registrace MAM](app-sdk-android.md#mamenrollmentmanager)
```csharp
IMAMEnrollmentManager mgr = MAMComponents.Get<IMAMEnrollmentManager>();
```

### <a name="xamarinforms-integration"></a>Integrace Xamarin.Forms

Pro `Xamarin.Forms` aplikace uvádíme `Microsoft.Intune.MAM.Remapper` balíček automaticky provádět náhradní třída MAM vložením `MAM` třídy do hierarchie tříd běžně používaných `Xamarin.Forms` třídy. 

> [!NOTE]
> Kromě toho provést integraci Xamarin.Android výše popsané je integrace Xamarin.Forms.

Jakmile Remapper se přidá do vašeho projektu je potřeba provést nahrazení ekvivalentem MAM. Například `FormsAppCompatActivity` a `FormsApplicationActivity` můžete nadále používat v aplikaci k dispozici přepsání `OnCreate` a `OnResume` jsou nahrazeny ekvivalenty MAM `OnMAMCreate` a `OnMAMResume` v uvedeném pořadí.

```csharp
    public class MainActivity : global::Xamarin.Forms.Platform.Android.FormsAppCompatActivity
    {
        protected override void OnMAMCreate(Bundle savedInstanceState)
        {
            base.OnMAMCreate(savedInstanceState);
            global::Xamarin.Forms.Forms.Init(this, savedInstanceState);
            LoadApplication(new App());
        }
```
Pokud nejsou provedeny nahrazení může až když provedete nahrazení dojít následující chyby kompilace:
* [CS0239 Chyba kompilátoru](https://docs.microsoft.com/dotnet/csharp/misc/cs0239). Tato chyba obvykle nastává v tomto formuláři ``'MainActivity.OnCreate(Bundle)': cannot override inherited member 'MAMAppCompatActivityBase.OnCreate(Bundle)' because it is sealed``.
To je očekáváno, protože když Remapper změní dědičnosti tříd Xamarin, některé funkce pak bude možné `sealed` a přepsat místo toho se přidá nová varianta MAM.
* [Chyba kompilátoru CS0507](https://docs.microsoft.com/dotnet/csharp/language-reference/compiler-messages/cs0507): Tato chyba obvykle nastává v tomto formuláři ``'MyActivity.OnRequestPermissionsResult()' cannot change access modifiers when overriding 'public' inherited member ...``. Dědičnost některé třídy Xamarin změně Remapper určitých členských funkcí se změní na `public`. Pokud některý z těchto funkcí přepíšete, budete muset změnit tyto modifikátory přístupu pro ty funkci přepsání hodnot a být `public` také.

> [!NOTE]
> Remapper přepíše závislost, kterou používá Visual Studio pro automatické dokončování IntelliSense. Proto budete muset znovu načíst a znovu sestavte projekt, když se přidá Remapper technologie IntelliSense správně rozpoznat změny.

## <a name="support"></a>Podpora
Pokud je vaše organizace stávajícím zákazníkem Intune, prosím práci s zástupce podpory Microsoftu vytvořit lístek podpory a vytvoření problému [stránce problémů na Githubu](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues) a pomůžeme nejdříve podíváme. 
