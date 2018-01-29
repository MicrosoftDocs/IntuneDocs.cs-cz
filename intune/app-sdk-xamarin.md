---
title: Komponenta Xamarin sady Microsoft Intune App SDK
description: 
keywords: SDK, Xamarin, Intune
author: erikre
manager: angrobe
ms.author: erikre
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 73caf124e94994acf816c98f0788efdabe024cc4
ms.sourcegitcommit: c3bd0d192d712fcfd52f64dd1377155796239fcb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/17/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Komponenta Xamarin sady Microsoft Intune App SDK

> [!NOTE]
> Možná si budete chtít nejdřív přečíst článek [Začínáme s Intune App SDK](app-sdk-get-started.md), který vysvětluje postup přípravy integrace na jednotlivých podporovaných platformách.



## <a name="overview"></a>Přehled
[Komponenta Xamarin sady Intune App SDK](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) umožňuje v aplikacích pro iOS a Android vytvořených pomocí Xamarinu povolit [zásady ochrany aplikací Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune). Komponenta umožňuje vývojářům snadno do aplikací založených na Xamarinu začlenit funkce ochrany aplikace Intune.

> [!NOTE]
> Podpora sady Intune SDK pro Xamarin je v současné době dostupná ve verzi Preview. 

Komponenta Xamarin sady Microsoft Intune App SDK umožňuje začlenit do vašich aplikací vyvíjených pomocí Xamarinu zásady ochrany aplikací Intune (označované také jako zásady APP nebo MAM). Aplikace s povolenou funkcí MAM je integrovaná se sadou Intune App SDK. Správci IT můžou zásady ochrany aplikací nasadit do vaší mobilní aplikace, když Intune tuto aplikaci aktivně spravuje.

## <a name="whats-supported"></a>Co se podporuje

### <a name="developer-machines"></a>Počítače pro vývojáře
* macOS


### <a name="mobile-app-platforms"></a>Platformy pro mobilní aplikace
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Scénáře Správy mobilních aplikací Intune

* Zařízení zaregistrovaná v Intune MDM
* Zařízení zaregistrovaná v EMM třetích stran
* Nespravovaná zařízení (nezaregistrovaná v žádném systému správy mobilních zařízení)

Aplikace Xamarinu vytvořené pomocí komponenty Xamarin sady Intune App SDK teď můžou přijímat zásady ochrany aplikací Intune na zařízeních zaregistrovaných ve správě mobilních zařízení (MDM) Intune i na nezaregistrovaných zařízeních.

## <a name="prerequisites"></a>Požadavky

* **[Jenom Android]** V zařízení musí být nainstalovaná nejnovější aplikace Portál společnosti Microsoft Intune.

## <a name="get-started"></a>Začínáme

1.  [Zde](https://components.xamarin.com/submit/xpkg) stáhněte soubor **Xamarin component.exe** a extrahujte ho.

2. Přečtěte si [licenční podmínky](https://components.xamarin.com/license/microsoft.intune.mam) pro komponentu Microsoft Intune MAM Xamarin.

3.  Stáhněte složku komponenty Xamarin sady Intune App SDK z [GitHubu](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) nebo [Nuget.org](https://www.nuget.org/profiles/msintuneappsdk) a extrahujte ji. Oba soubory stažené v kroku 1 a 3 musí být na úrovni stejného adresáře.

4.  Na příkazovém řádku jako správce spusťte `Xamarin.Component.exe install <.xam> file`.

5.  Ve Visual Studiu klikněte pravým tlačítkem na **komponenty** ve dříve vytvořeném projektu Xamarinu.

6.  Vyberte **Upravit komponenty** a přidejte komponentu Intune App SDK, kterou jste stáhli do počítače.



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Povolení zásad ochrany aplikací Intune v mobilní aplikaci pro iOS
1.  Při integraci sady Intune App SDK do mobilní aplikace pro iOS dodržujte obecné pokyny. Začněte od 3. kroku popsaného v [příručce pro vývojáře k sadě Intune App SDK pro iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app).
    **Důležité:** Povolení sdílení klíčenky aplikace je v sadě Visual Studio trochu jiné než v Xcode. Otevřete soubor Entitlements.plist aplikace a zkontrolujte, že je povolená možnost „Enable Keychain“ (Povolit klíčenku) a že jsou do oddílu přidané odpovídající skupiny pro sdílení klíčenky. Zkontrolujte, že je v poli „Custom Entitlements“ (Vlastní oprávnění) v možnostech podepsání sady prostředků aplikace pro iOS zadaný soubor Entitlements.plist, a to pro všechny kombinace konfigurace a platformy, které připadají v úvahu.
2.  Jakmile součást přidáte a aplikaci správně nakonfigurujete, může aplikace začít používat rozhraní API sady Intune SDK. Aby to bylo možné, musíte přidat následující obor názvů:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
3.    Aby aplikace mohly začít přijímat zásady ochrany, musíte je zaregistrovat do služby Intune MAM. Pokud aplikace k ověřování uživatelů používá knihovnu Azure Active Directory Authentication Library (ADAL), měla by aplikace po úspěšném ověření předat hlavní název uživatele (UPN) metodě registerAndEnrollAccount instance IntuneMAMEnrollmentManager:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **Důležité:** Nezapomeňte přepsat výchozí nastavení knihovny ADAL sady Intune App SDK nastavením vaší aplikace. Můžete to udělat prostřednictvím slovníku IntuneMAMSettings v souboru Info.plist aplikace podle popisu v [příručce pro vývojáře k sadě Intune App SDK pro iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk) nebo můžete použít vlastnosti přepisu AAD v instanci IntuneMAMPolicyManager. Způsob se souborem Info.plist se doporučuje použít u aplikací se statickým nastavením ADAL. Vlastnosti přepisu se doporučují použít u aplikací, které tyto hodnoty zjišťují za běhu. 
      
      Pokud aplikace knihovnu ADAL nepoužívá a chcete, aby ověřování prováděla sada Intune SDK, musí aplikace volat metodu loginAndEnrollAccount instance IntuneMAMEnrollmentManager.
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Povolení zásad ochrany aplikací v mobilní aplikaci pro Android
U aplikací pro Android založených na Xamarinu, které nevyužívají architekturu uživatelského rozhraní, si přečtěte téma [Intune APP SDK pro Android – Příručka vývojáře](app-sdk-android.md) a postupujte podle něj. V aplikaci pro Android založené na Xamarinu je potřeba nahradit třídu, metody a aktivity jejich ekvivalentem MAM podle [tabulky](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent), kterou v průvodci najdete. Pokud vaše aplikace nedefinuje třídu `android.app.Application`, budete ji muset vytvořit a zajistit, abyste dědili z `MAMApplication`.

Pro Xamarin Forms a další architektury uživatelského rozhraní nabízíme nástroj, který se jmenuje `MAM.Remapper`. Nástroj provede nahrazení třídy za vás. Bude ale potřeba provést tyto kroky:

1.  Přidejte odkaz na balíček NuGet `Microsoft.Intune.MAM.Remapper.Tasks` verze 0.1.0.0 nebo vyšší.

2.  Přidejte následující řádek do souboru csproj Androidu:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Nastavte akci tvoření přidaného souboru `remapping-config.json` na **RemappingConfigFile**. Obsažený soubor `remapping-config.json` funguje jenom s Xamarin.Forms. V případě jiných architektur uživatelského rozhraní si přečtěte soubor Readme, který je součástí balíčku NuGet Remapper.

## <a name="next-steps"></a>Další kroky

Dokončili jste základní kroky pro začlenění komponenty do aplikace. Teď můžete postupovat podle kroků, které jsou součástí ukázkové aplikace Xamarin pro Android. Nabízíme dvě ukázky, jednu pro Xamarin.Forms a druhou pro Android.
