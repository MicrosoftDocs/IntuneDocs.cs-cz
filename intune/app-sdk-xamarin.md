---
title: Komponenta Xamarin sady Microsoft Intune App SDK
description: 
keywords: SDK, Xamarin, Intune
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a684f7ab5841513e8e72a5e6c0af99f52e5fd207
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/25/2017
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Komponenta Xamarin sady Microsoft Intune App SDK

> [!NOTE]
> Možná si budete chtít nejdřív přečíst článek [Začínáme s Intune App SDK](app-sdk-get-started.md), který vysvětluje postup přípravy integrace na jednotlivých podporovaných platformách.



## <a name="overview"></a>Přehled
[Komponenta Xamarin sady Intune App SDK](https://components.xamarin.com/view/microsoft.intune.mam) umožňuje v aplikacích pro iOS a Android vytvořených pomocí Xamarinu povolit [zásady ochrany aplikací Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune). Komponenta umožňuje vývojářům snadno do aplikací založených na Xamarinu začlenit funkce ochrany aplikace Intune.

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

3.  Stáhněte složku komponenty Xamarin sady Intune App SDK z [GitHubu](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) nebo [Xamarinu](https://components.xamarin.com/license/microsoft.intune.mam) a extrahujte ji. Oba soubory stažené v kroku 1 a 3 musí být na úrovni stejného adresáře.

4.  Na příkazovém řádku jako správce spusťte `Xamarin.Component.exe install <.xam> file`.

5.  Ve Visual Studiu klikněte pravým tlačítkem na **komponenty** ve dříve vytvořeném projektu Xamarinu.

6.  Vyberte **Upravit komponenty** a přidejte komponentu Intune App SDK, kterou jste stáhli do počítače.



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Povolení zásad ochrany aplikací Intune v mobilní aplikaci pro iOS
1.  Abyste inicializovali sadu Intune App SDK, budete muset provést volání libovolného API ve třídě `AppDelegate.cs`. Například:

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  Když je teď komponenta přidaná a inicializovaná, můžete postupovat podle obecných kroků potřebných k začlenění App SDK do mobilní aplikace pro iOS. Kompletní dokumentaci k povolení nativních aplikací iOS najdete v tématu [Intune APP SDK pro iOS – Příručka vývojáře](app-sdk-ios.md).
3. **Důležité**: Existuje několik modifikací, které jsou specifické pro aplikace iOS založené na Xamarinu. Abyste například zahrnuli ukázkovou aplikaci Xamarinu, kterou jsme zahrnuli do komponenty, je nutné při povolování skupin řetězců klíčů přidat následující kód. Tady je příklad skupin, které byste potřebovali mít ve skupinách přístupu řetězce klíčů:

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
      <plist version="1.0">
            <dict>
                  <key>keychain-access-groups</key>
                  <array>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample</string>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample.intunemam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.intune.mam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.adalcache</string>
                  </array>
            </dict>
      </plist>
      ```

Dokončili jste kroky potřebné k začlenění komponenty do aplikace iOS založené na Xamarinu. Pokud k vytvoření projektu využíváte Xcode, můžete použít `Intune App SDK Settings.bundle`. To vám při tvorbě projektu umožní zapínat a vypínat nastavení zásad Intune kvůli testování a ladění. Pokud chcete využít výhod této sady, postupujte podle kroků v tématu [Intune App SDK pro iOS – Příručka vývojáře](app-sdk-ios.md) a přečtěte si část o [ladění v Xcodu](app-sdk-ios.md#status-result-and-debug-notifications).

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