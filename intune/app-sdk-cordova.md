---
title: Modul plug-in Cordova sady Intune App SDK
description: Modul plug-in Cordova sady Intune App SDK umožňuje vývojářům integrovat do své aplikace založené na Cordově funkce Intune pro ochranu aplikací a dat.
keywords: SDK, Cordova, Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 84ff217361108ac3518567f31af8943d0b3032fe
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/16/2018
---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a>Modul plug-in Cordova sady Intune App SDK

> [!IMPORTANT]
> Intune ukončuje od 1. května 2018 podporu modulu plug-in Cordova sady Microsoft Intune App SDK. Doporučujeme, abyste místo něj používali nástroj Intune App Wrapping Tool. Další informace o nástroji App Wrapping Tool najdete v tématech [Nástroj App Wrapping Tool pro iOS](app-wrapper-prepare-ios.md) a [Nástroj App Wrapping Tool pro Android](app-wrapper-prepare-android.md). Další informace o této změně najdete v části [Sdělení](whats-new.md#notices) v tématu [Co je nového v Microsoft Intune](whats-new.md).

## <a name="overview"></a>Přehled

[Modul plug-in Cordova sady Intune App SDK](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) v aplikacích pro iOS a Android sestavené pomocí Cordovy Modul plug-in umožňuje vývojářům integrovat do své aplikace založené na Cordově funkce Intune pro ochranu aplikací a dat.

> [!NOTE]
> Možná si budete chtít nejdřív přečíst článek [Začínáme s Intune App SDK](app-sdk-get-started.md), který vysvětluje postup přípravy integrace na jednotlivých podporovaných platformách.

Funkce SDK můžete povolit beze změny chování aplikace. Po integraci modulu plug-in do aplikace pro iOS nebo Android bude moct správce Microsoft Intune nasadit zásady ochrany aplikací Intune, které se skládají z různých funkcí pro ochranu dat. Modul plug-in je vytvořený tak, aby se většina kroků prováděla automaticky v procesu sestavování Cordovy. Díky tomu byste měli být schopní v aplikaci rychle povolit ochranu aplikací Intune. Začněte následujícím postupem podle toho, kterou platformu máte.

## <a name="supported-platforms"></a>Podporované platformy

* Modul plug-in funguje v systému Windows, Mac a Linux OS.
* Modul plug-in funguje s aplikacemi pro Android s `minSdkVersion` >= 14 a `targetSdkVersion` <= 24.
* Modul plug-in funguje s aplikacemi pro iOS určenými pro verze iOS 9.0 a vyšší.

## <a name="intune-mobile-application-management-scenarios"></a>Scénáře Správy mobilních aplikací Intune

* Zařízení zaregistrovaná v Intune MDM
* Zařízení zaregistrovaná v EMM třetích stran
* Nespravovaná zařízení (nezaregistrovaná v žádném systému správy mobilních zařízení)

Aplikace Cordova vytvořené pomocí modulu plug-in Cordova sady Intune App SDK teď můžou přijímat zásady ochrany aplikací Intune na zařízeních zaregistrovaných ve správě mobilních zařízení (MDM) Intune i na nezaregistrovaných zařízeních.

## <a name="prerequisites"></a>Požadavky

### <a name="android"></a>Android

* V zařízení musí být vždy nainstalovaná nejnovější aplikace Portál společnosti Microsoft Intune.
* Na cestě, kde se bude při používání modulu spouštět sestavení Cordovy, musí být minimálně Java 7.

### <a name="ios"></a>iOS

* V zařízení musí být pro funkce MDM nainstalovaná nejnovější aplikace Portál společnosti Microsoft Intune. *Není* nutná pro zásady ochrany aplikací Intune bez funkcí pro registraci zařízení.

### <a name="both-platforms"></a>Obě platformy

* Je vyžadována verze 0.8.0+ [modulu plug-in Azure Active Directory Authentication Libraries (ADAL) pro Cordovu](https://github.com/AzureAD/azure-activedirectory-library-for-cordova).

> [!NOTE]
> Aplikace, které už mají závislost modulu plug-in, neupgradují modul plug-in automaticky na požadovanou verzi kvůli chybě Apache Cordovy popsané [tady](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22).



## <a name="quickstart"></a>Rychlý start

1. Aktualizujte si verzi ADAL:

  ```shell
  cordova plugin remove cordova-plugin-ms-adal
  cordova plugin add cordova-plugin-ms-adal@0.8.x
  ```

2. Přidejte modul plug-in Cordova sady Intune App SDK:

  ```shell
  cordova plugin add cordova-plugin-ms-intune-mam
  ```

## <a name="build-the-plugin-into-your-ios-app"></a>Integrujte modul plug-in do aplikace pro iOS

Budete muset provést některé kroky, aby byly v aplikaci povolené zásady ochrany aplikací Intune. Aby to bylo jednodušší, provedou se tyto kroky automaticky v procesu sestavení Cordovy jako zachycení volání a přesměrování funkce (hook) před sestavením. V důsledku toho automatizované kroky upraví vaše soubory `*.pbxproj`, `*-Info.plist` a `*.entitlements`, které jsou spojené s konfigurací projektu. Pokud projekt neobsahuje soubor nároků, modul plug-in ho automaticky vytvoří.

Tato instalace podporuje jenom jediný cíl, a pokud jich existuje více, provede konfiguraci na prvním nalezeném cíli. Pokud se proces nezdaří, zkontrolujte, jestli:

1. Projekt Xcode vaší aplikace je `[name].xcodeproj`, kde `[name]` je hodnota definovaná v `config.xml`.
2. Váš projekt používá [standardní adresářovou strukturu aplikací v Cordově](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).

## <a name="build-the-plugin-into-your-android-app"></a>Integrujte modul plug-in do aplikace pro Android

1. Importujte tento modul plug-in pomocí nejnovějších nástrojů Cordova. Modul plug-in bude automaticky vyvolán jako krok `after_compile`.

2. Modul plug-in na konci procesu sestavování vytvoří verzi sestaveného apk (Android API 14+) s povoleným Intune. Výstup sestavení bude obsahovat `[Project]-intunewrapped-[Build_Configuration].apk` (například `helloWorld-intunewrapped-debug.apk`).

> [!NOTE]
> Modul plug-in podporuje jenom sestavení gradle.

Kvůli chybě Cordovy popsané [zde](https://issues.apache.org/jira/browse/CB-9434), která způsobuje ignorování některých zachycení volání a přesměrování funkce (hook) Cordovy při použití `cordova run`, musíte ke spuštění zabalené aplikace z příkazového řádku provést toto:

```shell
$ cordova build
$ cordova run --nobuild
```

## <a name="sign-your-android-app"></a>Podepište si aplikaci pro Android

Modul plug-in automaticky rozpozná podpisové informace, které jste poskytli Cordově, v následujících umístěních:

* platforms/android/debug-signing.properties
* platforms/android/release-signing.properties
* res/native/android/ant.properties

Další informace o očekávaném formátu najdete v tématu o [podpisových informacích v nástroji Gradle Cordovy](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle).

Intune aktuálně nepodporuje schopnost poskytovat podpisové informace v souboru `build.json` nebo libovolných umístěních poskytnutých do sestavení Cordovy prostřednictvím parametrů.

## <a name="debugging-from-visual-studio"></a>Ladění z Visual Studia

Po prvním spuštění aplikace by se mělo zobrazit dialogové okno oznamující, že je aplikace spravovaná pomocí Intune. Zvolte „Znovu nezobrazovat“ a znovu klikněte na tlačítko ladění/spuštění z VS, aby se našly zarážky.

## <a name="known-limitations"></a>Známá omezení

### <a name="android"></a>Android

* Podpora MultiDex je nekompletní.
* Aplikace musí mít `minSdkVersion` verze 14 a `targetSdkVersion` verze 24 nebo nižší. Intune aktuálně nepodporuje aplikace určené pro rozhraní API 25.
* Aplikace, které jsou podepsané pomocí schématu podpisu V2, Intune nemůže znovu podepsat. Když se aplikace podepsané přes V2 zabalí pomocí modulu plug-in, bude výsledný soubor .apk nepodepsaný.
*
  * Výchozí podepisování Cordovy přes V2 můžete zakázat přidáním následujícího kódu do vašeho souboru `build-extras.gradle`:

  ```gradle
  android {
      signingConfigs {
          release {
              v2SigningEnabled false
          }
          debug {
              v2SigningEnabled false
          }
      }
      buildTypes {
          release {
              signingConfig signingConfigs.release
          }
          debug {
              signingConfig signingConfigs.debug
          }
      }
  }
  ```

### <a name="ios"></a>iOS

* Kdykoli upravíte seznam UTI pod uzlem **CFBundleDocumentTypes** souboru **Info.plist**, musíte před dalším sestavením vymazat UTI Intune v části importovaných UTI stejného souboru plist (uzel **UTImportedTypeDeclarations**). Všechny UTI Intune budou začínat předponou `com.microsoft.intune.mam`.

* Pokud chcete odebrat modul plug-in Intune App ADK pro Cordovu z projektu Cordova, musíte také odebrat platformu iOS a znovu ji přidat, abyste vrátili zpět některé konfigurace Intune v souborech .xcodeproj a .plist.
