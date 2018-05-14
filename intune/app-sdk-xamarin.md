---
title: Xamarinové vazby sady Microsoft Intune App SDK
description: Xamarinové vazby sady Intune App SDK umožňují v aplikacích pro iOS a Android vytvořených v Xamarinu povolit zásady ochrany aplikací Intune.
keywords: SDK, Xamarin, Intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5c9f81761e7e24393471f44da4cf619f017e9bbd
ms.sourcegitcommit: 4c06fa8e9932575e546ef2e880d96e96a0618673
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Xamarinové vazby sady Microsoft Intune App SDK

> [!NOTE]
> Možná si budete chtít nejdřív přečíst článek [Začínáme s Intune App SDK](app-sdk-get-started.md), který vysvětluje postup přípravy integrace na jednotlivých podporovaných platformách.

## <a name="overview"></a>Přehled
[Xamarinové vazby sady Intune App SDK](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) umožňují v aplikacích pro iOS a Android vytvořených v Xamarinu povolit [zásady ochrany aplikací Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune). Tyto vazby umožňují vývojářům jednoduše do aplikací založených na Xamarinu začlenit funkce ochrany aplikace Intune.

Xamarinové vazby sady Microsoft Intune App SDK umožňují začlenit do vašich aplikací vyvíjených v Xamarinu zásady ochrany aplikací Intune (také označované jako zásady APP nebo MAM). Aplikace s povolenou funkcí MAM je integrovaná se sadou Intune App SDK. Správci IT můžou zásady ochrany aplikací nasadit do vaší mobilní aplikace, když Intune tuto aplikaci aktivně spravuje.

## <a name="whats-supported"></a>Co se podporuje

### <a name="developer-machines"></a>Počítače pro vývojáře
* Windows
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

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Povolení zásad ochrany aplikací Intune v mobilní aplikaci pro iOS
1. Do svého projektu Xamarin.iOS přidejte [balíček NuGet Microsoft.Intune.MAM.Xamarin.iOS](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS).
2.  Při integraci sady Intune App SDK do mobilní aplikace pro iOS dodržujte obecné pokyny. Začněte od 3. kroku popsaného v [příručce pro vývojáře k sadě Intune App SDK pro iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). Poslední krok v této části spuštění nástroje IntuneMAMConfigurator můžete přeskočit, protože tento nástroj je součástí balíčku Microsoft.Intune.MAM.Xamarin.iOS a spustí se automaticky při sestavení.
    **Důležité:** Povolení sdílení klíčenky aplikace je v sadě Visual Studio trochu jiné než v Xcode. Otevřete soubor Entitlements.plist aplikace a zkontrolujte, že je povolená možnost „Enable Keychain“ (Povolit klíčenku) a že jsou do oddílu přidané odpovídající skupiny pro sdílení klíčenky. Zkontrolujte, že je v poli „Custom Entitlements“ (Vlastní oprávnění) v možnostech podepsání sady prostředků aplikace pro iOS zadaný soubor Entitlements.plist, a to pro všechny kombinace konfigurace a platformy, které připadají v úvahu.
3.  Jakmile přidáte vazby a aplikaci správně nakonfigurujete, může aplikace začít používat rozhraní API sady Intune SDK. Aby to bylo možné, musíte přidat následující obor názvů:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. Aby aplikace mohly začít přijímat zásady ochrany, musíte je zaregistrovat do služby Intune MAM. Pokud aplikace k ověřování uživatelů používá knihovnu Azure Active Directory Authentication Library (ADAL), měla by aplikace po úspěšném ověření předat hlavní název uživatele (UPN) metodě registerAndEnrollAccount instance IntuneMAMEnrollmentManager:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **Důležité:** Nezapomeňte přepsat výchozí nastavení knihovny ADAL sady Intune App SDK nastavením vaší aplikace. Můžete to udělat prostřednictvím slovníku IntuneMAMSettings v souboru Info.plist aplikace podle popisu v [příručce pro vývojáře k sadě Intune App SDK pro iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk) nebo můžete použít vlastnosti přepisu AAD v instanci IntuneMAMPolicyManager. Způsob se souborem Info.plist se doporučuje použít u aplikací se statickým nastavením ADAL. Vlastnosti přepisu se doporučují použít u aplikací, které tyto hodnoty zjišťují za běhu. 
      
      Pokud aplikace knihovnu ADAL nepoužívá a chcete, aby ověřování prováděla sada Intune SDK, musí aplikace volat metodu loginAndEnrollAccount instance IntuneMAMEnrollmentManager.
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Povolení zásad Intune App Protection v mobilní aplikaci pro Android

### <a name="xamarinandroid-integration"></a>Integrace Xamarin.Android

1. Do svého projektu Xamarin.Android přidejte nejnovější verzi [balíčku NuGet Microsoft.Intune.MAM.Xamarin.Android](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android). Ten vám poskytne potřebné odkazy, abyste mohli aplikaci v Intune povolit.

2. Přečtěte si celou [příručku pro vývojáře, kteří používají sadu Intune App SDK pro Android](app-sdk-android.md), a zvláštní pozornost věnujte těmto částem:
    1. [Celá část věnovaná nahrazením tříd a metod](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent). 
    2. [Část věnovaná MAMApplication](app-sdk-android.md#mamapplication). Zkontrolujte, že podtřída je správně doplněna o atribut `[Application]` a že přepisuje konstruktor `(IntPtr, JniHandleOwnership)`.
    3. [Část věnovaná integraci ADAL](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal), pokud se vaše aplikace ověřuje ve službě AAD.
    4. [Část věnovaná registraci MAM-WE](app-sdk-android.md#app-protection-policy-without-device-enrollment), pokud plánujete, že vaše aplikace bude získávat zásady ze služby MAM.

> [!NOTE]
> Když se ve vazbách `Microsoft.Intune.MAM.Xamarin.Android` pokoušíte najít odpovídající rozhraní API z [příručky pro vývojáře, kteří používají sadu Intune App SDK pro Android](app-sdk-android.md), nebo se z této příručky pokoušíte převést fragmenty kódu, mějte na paměti, že xamarinový generátor vazeb v rozhraní API Androidu podstatně mění následující položky:
> * Všechny identifikátory se převedou na formát PascalCase (com.foo.bar -> Com.Foo.Bar).
> * Všechny operace get/set se převedou na operace vlastností (např. Foo.getBar() -> Foo.Bar, Foo.setBar("zap") -> Foo.Bar = "zap").
> * Všechna rozhraní mají před názvem znak „I“ (FooInterface -> IFooInterface).

### <a name="xamarinforms-integration"></a>Integrace Xamarin.Forms

**Kromě provedení všech výše uvedených kroků** poskytujeme pro aplikace `Xamarin.Forms` balíček `Microsoft.Intune.MAM.Remapper`. Tento balíček za vás nahradí třídy a vloží třídy `MAM` do hierarchie běžně používaných tříd `Xamarin.Forms`, například `FormsAppCompatActivity` a `FormsApplicationActivity`, abyste tyto třídy mohli i nadále používat tak, že budete poskytovat přepsání ekvivalentních funkcí MAM, jako jsou `OnMAMCreate` a `OnMAMResume`. Pokud ho chcete použít, postupujte takto:

1.  Přidejte do svého projektu balíček NuGet [Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks). Tím se automaticky přidají xamarinové vazby sady Intune APP SDK, pokud jste je ještě nezahrnuli.

2.  Přidejte volání `Xamarin.Forms.Forms.Init(Context, Bundle)` ve funkci `OnMAMCreate` třídy `MAMApplication`, kterou jste vytvořili v kroku 2.2 výše. To je nutné, protože se správou přes Intune se aplikace může spustit i na pozadí.

> [!NOTE]
> Tato operace znovu zapíše závislost, kterou Visual Studio používá pro automatické dokončování Intellisense, a proto možná budete muset po prvním spuštění nástroje pro přemapování restartovat Visual Studio, aby funkce Intellisense správně rozpoznala změny. 

## <a name="support"></a>Support

Pokud je vaše organizace stávajícím zákazníkem Intune, obraťte se na zástupce podpory Microsoft a požádejte ho o otevření lístku podpory a vytvoření problému na [stránce problémů s Githubem](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues), abychom vám mohli co nejrychleji pomoci. 