---
title: Xamarinové vazby sady Microsoft Intune App SDK
description: Xamarinové vazby sady Intune App SDK umožňují v aplikacích pro iOS a Android vytvořených v Xamarinu povolit zásady ochrany aplikací Intune.
keywords: SDK, Xamarin, Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c3ccd2db88df4e5b7a51e0aa2446a99f33256432
ms.sourcegitcommit: 378474debffbc85010c54e20151d81b59b7a7828
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2018
ms.locfileid: "47028711"
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Xamarinové vazby sady Microsoft Intune App SDK

> [!NOTE]
> Možná si budete chtít nejdřív přečíst článek [Začínáme s Intune App SDK](app-sdk-get-started.md), který vysvětluje postup přípravy integrace na jednotlivých podporovaných platformách.

## <a name="overview"></a>Přehled
[Xamarinové vazby sady Intune App SDK](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) umožňují v aplikacích pro iOS a Android vytvořených v Xamarinu povolit [zásady ochrany aplikací Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune). Tyto vazby umožňují vývojářům jednoduše do aplikací založených na Xamarinu začlenit funkce ochrany aplikace Intune.

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

Sada SDK spoléhá na [knihovnu ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) s jejími scénáři [ověření](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) a podmíněného spuštění, což vyžaduje, aby byly aplikace nakonfigurovány s [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). Hodnoty konfigurace se předávají sadě SDK prostřednictvím metadat AndroidManifest. Přečtěte si dokumentaci ke [konfiguraci knihovny ADAL pro vaši aplikaci](https://docs.microsoft.com/intune/app-sdk-android#configure-azure-active-directory-authentication-library-adal).

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
      
> [!NOTE] 
> Pro iOS není k dispozici nástroj pro přemapování. Integrace do aplikace Xamarin.Forms by měla být stejná jako u normálního projektu Xamarin.iOS. 

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Povolení zásad Intune App Protection v mobilní aplikaci pro Android

U aplikací pro Android založených na Xamarinu, které nevyužívají architekturu uživatelského rozhraní, si přečtěte téma [Intune APP SDK pro Android – Příručka vývojáře](app-sdk-android.md) a postupujte podle něj. V aplikaci pro Android založené na Xamarinu je potřeba nahradit třídu, metody a aktivity jejich ekvivalentem MAM podle [tabulky](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent), kterou v průvodci najdete. Pokud vaše aplikace nedefinuje třídu `android.app.Application`, budete ji muset vytvořit a zajistit, abyste dědili z `MAMApplication`.

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

Dokončili jste základní kroky pro začlenění komponenty do aplikace. Teď můžete postupovat podle kroků, které jsou součástí ukázkové aplikace Xamarin pro Android. Nabízíme dvě ukázky, jednu pro Xamarin.Forms a druhou pro Android.

## <a name="requiring-intune-app-protection-policies-in-order-to-use-your-xamarin-based-android-lob-app-optional"></a>Vyžadování zásad ochrany aplikací Intune k tomu, aby bylo možné použít obchodní aplikaci pro Android, která je založená na Xamarinu (volitelné) 

Následující část obsahuje postup, který zajistí, aby obchodní aplikace pro Android, které jsou založené na Xamarinu, mohli na svém zařízení používat jenom uživatelé s ochranou Intune. 

### <a name="general-requirements"></a>Obecné požadavky
* Proveďte registraci ID aplikace pro vaši aplikaci. Tento údaj najdete na portálu [Azure Portal](https://portal.azure.com/) v části **Všechny aplikace** ve sloupci **ID aplikace**. Na webu Azure Portal:
1.  Přejděte do okna **Azure Active Directory**.
2.  Vyberte pro danou aplikaci možnost **Registrace aplikace**.
3.  V části **Nastavení** pod záhlavím **Přístup přes rozhraní API** vyberte **Požadovaná oprávnění**. 
4.  Klikněte na **+ Přidat**.
5.  Klikněte na **Vyberte rozhraní API**. 
6.  Do vyhledávacího pole zadejte **Microsoft Mobile Application Management** (Správa mobilních aplikací Microsoftu).
7.  V seznamu rozhraní API vyberte **Microsoft Mobile Application Management** (Správa mobilních aplikací Microsoftu) a kliknutím proveďte výběr.
8.  Vyberte **Read and Write the User’s App Management Data** (Čtení a zápis dat správy uživatelských aplikací).
9.  Klikněte na **Hotovo**.
10. Klikněte na **Udělit oprávnění** a pak na **Ano**. 
    
### <a name="working-with-the-intune-sdk"></a>Práce se sadou Intune SDK
Tyto pokyny se týkají všech aplikací pro Android a Xamarin, u kterých chcete při použití na zařízení koncového uživatele vyžadovat zásady ochrany aplikací Intune.

1. Nakonfigurujte ADAL pomocí postupu, který je uvedený v [příručce Intune SDK pro Android](https://docs.microsoft.com/intune/app-sdk-android#configure-azure-active-directory-authentication-library-adal).
> [!NOTE] 
> Termín „ID klienta“ je shodný s termínem „ID aplikace“ z portálu Azure Portal, který se váže na vaši aplikaci. 
* Pokud chcete povolit jednotné přihlašování, použijte postup uvedený v části Obvyklé konfigurace ADAL v bodě 2.

2. Povolte výchozí registraci tak, že do manifestu vložíte následující hodnotu: ```xml <meta-data android:name="com.microsoft.intune.mam.DefaultMAMServiceEnrollment" android:value="true" />```
> [!NOTE] 
> Musí jít o jedinou integraci MAM-WE v dané aplikaci. Pokud existují další pokusy o volání rozhraní API instance MAMEnrollmentManager, může docházet ke konfliktům.

3. Povolte požadované zásady MAM tak, že do manifestu vložíte následující hodnotu: ```xml <meta-data android:name="com.microsoft.intune.mam.MAMPolicyRequired" android:value="true" />```
> [!NOTE] 
> Tím vynutíte, aby si aplikace na zařízení stáhly Portál společnosti a před použitím provedly postup výchozí registrace.

### <a name="working-with-adal"></a>Práce s ADAL
Tyto pokyny se týkají požadavku pro aplikace .NET/Xamarin, u kterých chcete při použití na zařízení koncového uživatele vyžadovat zásady ochrany aplikací Intune.

1. Proveďte všechny kroky, které jsou uvedené v dokumentaci pro ADAL v části o [zprostředkovaném ověřování pro Android](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet/tree/dev/adal#brokered-authentication-for-android).
> [!NOTE] 
> Očekává se, že další vydaná verze .NET ADAL (3.17.4) bude obsahovat opravu, která zajistí, že toto bude fungovat.

Pokud je vaše organizace stávajícím zákazníkem Intune, obraťte se na zástupce podpory Microsoft a požádejte ho o otevření lístku podpory a vytvoření problému na [stránce problémů s Githubem](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues), abychom vám mohli co nejrychleji pomoci. 

