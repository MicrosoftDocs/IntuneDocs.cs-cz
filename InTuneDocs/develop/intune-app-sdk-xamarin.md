---
title: Komponenta Xamarin sady Microsoft Intune App SDK | Dokumentace Microsoftu
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
translationtype: Human Translation
ms.sourcegitcommit: c59707ba2967b069dc30aee71d2642e91d71b23b
ms.openlocfilehash: 74607fc704234e6ac85eae3bf55c186000c6e68a


---

# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Komponenta Xamarin sady Microsoft Intune App SDK

> [!NOTE]
> Možná si budete chtít nejdřív přečíst článek [Začínáme s Intune App SDK](intune-app-sdk-get-started.md), který vysvětluje postup přípravy integrace na jednotlivých podporovaných platformách.



## <a name="overview"></a>Přehled
[Komponenta Xamarin sady Intune App SDK](https://components.xamarin.com/view/microsoft.intune.mam) umožňuje v mobilních aplikacích pro iOS a Android vytvořených pomocí Xamarinu povolit [funkce správy mobilních aplikací Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune). Komponenta umožňuje vývojářům snadno do aplikací založených na Xamarinu začlenit funkce ochrany aplikace Intune.

Funkce SDK můžete povolit beze změny chování aplikace. Po začlenění této komponenty do mobilní aplikace pro iOS nebo Android bude moct správce IT přes Správu mobilních aplikací Microsoft Intune (MAM) nasadit zásady podporující celou řadu funkcí ochrany dat.

## <a name="whats-supported"></a>Co se podporuje

### <a name="developer-machines"></a>Počítače pro vývojáře
* Windows


### <a name="mobile-app-platforms"></a>Platformy pro mobilní aplikace
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Scénáře Správy mobilních aplikací Intune

* Zařízení zaregistrovaná v Intune MDM
* Zařízení zaregistrovaná v EMM třetích stran
* Nespravovaná zařízení (nezaregistrovaná v žádném systému správy mobilních zařízení)

Aplikace Xamarin vytvořené pomocí komponenty Xamarin sady Intune App SDK teď můžou přijímat zásady správy mobilních aplikací (MAM) Intune na zařízeních zaregistrovaných ve správě mobilních zařízení (MDM) Intune i na nezaregistrovaných zařízeních.

## <a name="prerequisites"></a>Požadavky

* **[Jenom Android]** V zařízení musí být vždy nainstalovaná nejnovější aplikace Portál společnosti Microsoft Intune.

## <a name="get-started"></a>Začínáme

1.  [Zde](https://components.xamarin.com/submit/xpkg) stáhněte soubor **Xamarin component.exe** a extrahujte ho.

2. Přečtěte si [licenční podmínky](https://components.xamarin.com/license/microsoft.intune.mam) pro komponentu Microsoft Intune MAM Xamarin.

3.  Stáhněte složku komponenty Xamarin sady Intune App SDK z [GitHubu](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) nebo [Xamarinu](https://components.xamarin.com/license/microsoft.intune.mam) a extrahujte ji. Oba soubory stažené v kroku 1 a 2 musí být na úrovni stejného adresáře.

4.  Na příkazovém řádku jako správce spusťte `Xamain.Component.exe install <.xam> file`.

5.  Ve Visual Studiu klikněte pravým tlačítkem na **komponenty** ve dříve vytvořeném projektu Xamarin.

6.  Vyberte **Upravit komponenty** a přidejte komponentu Intune App SDK, kterou jste stáhli do počítače.



## <a name="enabling-intune-mam-in-your-ios-mobile-app"></a>Povolení Intune MAM v mobilní aplikaci pro iOS
1.  Abyste inicializovali Intune App SDK, budete muset provést volání libovolného API ve třídě `AppDelegate.cs`. Například:

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  Když je teď komponenta přidaná a inicializovaná, můžete postupovat podle obecných kroků potřebných k začlenění App SDK do mobilní aplikace pro iOS. Kompletní dokumentaci k povolení nativních aplikací iOS najdete v tématu [Intune APP SDK pro iOS – Příručka vývojáře](intune-app-sdk-ios.md).
3. **Důležité**: Existuje několik modifikací, které jsou specifické pro aplikace iOS založené na Xamarinu. Například při povolování skupin řetězců klíčů budete muset přidat následující, abyste zahrnuli ukázkovou aplikaci Xamarin, kterou jsme zahrnuli do komponenty. Tady je příklad skupin, které byste potřebovali mít ve skupinách přístupu řetězce klíčů:

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

Dokončili jste kroky potřebné k začlenění komponenty do aplikace iOS založené na Xamarinu. Pokud k vytvoření projektu využíváte Xcode, můžete použít `Intune App SDK Settings.bundle`. To vám umožní při tvorbě projektu nastavení zásad Intune zapínat a vypínat kvůli testování a ladění. Pokud chcete využít výhod této sady, postupujte podle kroků v tématu [Intune App SDK pro iOS – Příručka vývojáře](intune-app-sdk-ios.md) a přečtěte si část o [ladění v Xcodu](intune-app-sdk-ios.md#status-result-and-debug-notifications).

## <a name="enabling-mam-in-your-android-mobile-app"></a>Povolení MAM v mobilní aplikaci pro Android
Pro aplikace Androidu založené na Xamarinu, které nepoužívají architekturu uživatelského rozhraní, si budete muset přečíst téma [Intune APP SDK pro Android – Příručka vývojáře] a postupovat podle něho. Pro aplikaci Androidu založenou na Xamarinu budete muset nahradit třídy, metody a aktivity jejich ekvivalentem MAM podle [tabulky](intune-app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent-required), kterou v průvodci najdete. Pokud vaše aplikace nedefinuje třídu `android.app.Application`, budete ji muset vytvořit a zajistit, abyste dědili z `MAMApplication`.

Pro Xamarin Forms a další architektury uživatelského rozhraní nabízíme nástroj, který se jmenuje `MAM.Remapper`. Nástroj provede nahrazení třídy za vás. Budete ale muset provést tyto kroky:

1.  Přidejte odkaz na balíček nuget ` Microsoft.Intune.MAM.Remapper.Tasks` verze 0.1.0.0 nebo vyšší.

2.  Přidejte následující řádek do souboru csproj Androidu:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Nastavte akci tvoření přidaného souboru `remapping-config.json` na **RemappingConfigFile**. Obsažený soubor `remapping-config.json` funguje jenom s Xamarin.Forms. Pro jiné architektury uživatelského rozhraní si přečtěte soubor Readme, který je součástí balíčku nuget Remapper.

## <a name="test-your-app"></a>Otestování aplikace

Dokončili jste základní kroky pro začlenění komponenty do aplikace. Teď můžete postupovat podle kroků, které jsou součástí ukázkové aplikace Xamarin pro Android. Nabízíme dvě ukázky, jednu pro Xamarin.Forms a druhou pro Android.



<!--HONumber=Dec16_HO2-->


