---
title: Modul plug-in Cordova sady Microsoft Intune App SDK | Microsoft Intune
description: 
keywords: SDK, Cordova, Intune
author: oydang
manager: angrobe
ms.author: oydang
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: karthikaraman
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: af7df3fcf50c3508d495522341bb287c638f40a3
ms.openlocfilehash: 2af369cc44c710789ab65eb25f10602882772019


---
# ﻿<a name="microsoft-intune-app-sdk-cordova-plugin"></a>Modul plug-in Cordova sady Intune App SDK

> [!NOTE]
> Možná si budete chtít nejdřív přečíst článek [Začínáme s Intune App SDK](intune-app-sdk-get-started.md), který vysvětluje postup přípravy integrace na jednotlivých podporovaných platformách.


## <a name="overview"></a>Přehled

[Modul plug-in Cordova sady Intune App SDK](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam) umožňuje v mobilních aplikacích pro iOS a Android vytvořených pomocí Cordovy povolit [funkce správy mobilních aplikací Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune). Modul plug-in umožňuje vývojářům integrovat do své aplikace založené na Cordově funkce Intune pro ochranu aplikací a dat.

Funkce SDK můžete povolit beze změny chování aplikace. Po začlenění modulu plug-in do mobilní aplikace pro iOS nebo Android bude moct správce IT přes Správu mobilních aplikací Microsoft Intune (MAM) nasadit zásady podporující celou řadu funkcí ochrany dat. Modul plug-in jsme vyvinuli tak, aby se většina kroků prováděla automaticky v procesu sestavování Cordovy. Díky tomu byste měli být schopní rychle dosáhnout povolení aplikace pro správu. Začněte podle následujících kroků na základě vaší cílové platformy.




## <a name="whats-supported"></a>Co se podporuje

### <a name="developer-machines"></a>Počítače pro vývojáře
* Windows
* Mac OS


### <a name="mobile-app-platforms"></a>Platformy pro mobilní aplikace
* Android 4.0+
* iOS

### <a name="intune-mobile-application-management-scenarios"></a>Scénáře Správy mobilních aplikací Intune

* Zařízení zaregistrovaná v Intune MDM
* Zařízení zaregistrovaná v EMM třetích stran
* Nespravovaná zařízení (nezaregistrovaná v žádném systému správy mobilních zařízení)

Aplikace Cordova vytvořené pomocí modulu plug-in Cordova sady Intune App SDK teď můžou přijímat zásady správy mobilních aplikací (MAM) Intune na zařízeních zaregistrovaných ve správě mobilních zařízení (MDM) Intune i na nezaregistrovaných zařízeních.



## <a name="prerequisites"></a>Požadavky

### <a name="technical-prerequisites"></a>Technické požadavky

* **[Jenom Android]** V zařízení musí být vždy nainstalovaná nejnovější aplikace Portál společnosti Microsoft Intune.


* Je vyžadována verze 0.8.0+ [modulu plug-in Azure Active Directory Authentication Libraries (ADAL) pro Cordovu](https://github.com/AzureAD/azure-activedirectory-library-for-cordova).
  * **Důležité:** Aplikace, které už mají závislost modulu plug-in, neprovedou automatické upgradování modulu plug-in na požadovanou verzi kvůli chybě Apache Cordovy popsané [zde](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22).


### <a name="before-you-install-and-use-microsoft-intune-app-sdk-cordova-plugin-you-must"></a>Před instalací a používáním modulu plug-in Cordova sady Microsoft Intune App SDK **musíte**:

* Přečíst si [licenční podmínky modulu plug-in Cordova sady Intune App SDK](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam/blob/master/Intune_App_SDK_Cordova_plugin_RTM_license.pdf)

* Vytisknout a uchovat pro své záznamy kopii licenčních podmínek. Stažením a použitím modulu plug-in Cordova sady Intune App SDK s licenčními podmínkami souhlasíte.  Pokud je nepřijímáte, software nepoužívejte.


## <a name="quick-start"></a>Rychlý start

1. Aktualizujte si verzi ADAL:

    ```
    cordova plugin remove cordova-plugin-ms-adal
    cordova plugin add cordova-plugin-ms-adal@0.8.x
    ```

2. Přidejte modul plug-in Cordova sady Intune App SDK:

    ```
    cordova plugin add cordova-plugin-ms-intune-mam
    ```

## <a name="how-to-build-the-plugin-into-your-ios-app"></a>Jak modul plug-in začlenit do aplikace pro iOS

Budete muset provést některé kroky, aby byla aplikace povolená pro Intune MAM. Aby to bylo jednodušší, provedou se tyto kroky automaticky v procesu sestavení Cordovy jako zachycení volání a přesměrování funkce (hook) před sestavením. V důsledku toho automatizované kroky upraví vaše soubory `*.pbxproj`, `*-Info.plist` a `*.entitlements`, které jsou spojené s konfigurací projektu. Pokud projekt neobsahuje soubor nároků, modul plug-in ho automaticky vytvoří.

Tato instalace podporuje jenom jediný cíl, a pokud jich existuje více, provede konfiguraci na prvním nalezeném cíli. Pokud se proces nezdaří, zkontrolujte, jestli:

1. Projekt Xcode vaší aplikace je `[name].xcodeproj`, kde `[name]` je hodnota definovaná v `config.xml`.
2. Váš projekt používá [standardní adresářovou strukturu aplikací v Cordově](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).

## <a name="how-to-build-the-plugin-into-your-android-app"></a>Jak modul plug-in začlenit do aplikace pro Android

1. Importujte tento modul plug-in pomocí nejnovějších nástrojů Cordova. Modul plug-in bude automaticky vyvolán jako krok `after_compile`.

2. Modul plug-in na konci procesu sestavování vytvoří verzi sestaveného apk (Android API 14+) s povoleným MAM. Výstup sestavení bude obsahovat `[Project]-intunewrapped-[Build_Configuration].apk` (například `helloWorld-intunewrapped-debug.apk`).

Modul plug-in podporuje jenom sestavení gradle.

Kvůli chybě Cordovy popsané [zde](https://issues.apache.org/jira/browse/CB-9434), která způsobuje ignorování některých zachycení volání a přesměrování funkce (hook) Cordovy při použití `cordova run`, musíte ke spuštění zabalené aplikace z příkazového řádku provést toto:

```
$ cordova build
$ cordova run --nobuild
```


### <a name="signing-your-android-app"></a>Podepsání aplikace pro Android
Pokud chcete do zabaleného souboru apk přidat podpisové informace, upravte `build.json` běžným způsobem pro přidání podpisových informací. Například:
```json
{
  "android": {
    "release": {
      "keystore": "your.keystore",
      "storePassword": "yourpassword",
      "alias": "youralias",
      "password" : "yourpassword",
      "keystoreType": ""
    }
  }
}
```

### <a name="build-for-android-test-only"></a>Sestavení jenom pro test v Androidu

1. Přidejte `android:testOnly="true"` do uzlu aplikace v souboru `AndroidManifest.xml`.


2. **Cordova 6.x.x:** V `[PROJECT_ROOT]/platforms/android/cordova/lib/Adb.js` změňte řádek 60 z

    ```javascript
    var args = ['-s', target, 'install'];
    ```
    na
    ```javascript
    var args = ['-s', target, 'install', '-t'];
    ```

Účelem je spustit `adb install` s příznakem „-t“, protože aplikace `testOnly` bez něho nejde instalovat.

### <a name="debugging-from-visual-studio"></a>Ladění z Visual Studia
Po prvním spuštění aplikace by se mělo zobrazit dialogové okno oznamující, že je aplikace spravovaná pomocí Intune. Zvolte „Znovu nezobrazovat“ a znovu klikněte na tlačítko ladění/spuštění z VS, aby se našly zarážky.

## <a name="known-limitations"></a>Známá omezení
### <a name="android"></a>Android
* Podpora MultiDex je nekompletní.
* Aplikace musí být pro cílový Android 4.0 (Android API 14) nebo vyšší.

### <a name="ios"></a>iOS
* Kdykoli upravíte seznam UTI pod uzlem **CFBundleDocumentTypes** souboru **Info.plist**, musíte před dalším sestavením vymazat UTI Intune v části importovaných UTI stejného souboru plist (uzel **UTImportedTypeDeclarations**). Všechny UTI Intune budou začínat předponou `com.microsoft.intune.mam`.

* Pokud chcete modul plug-in Intune z projektu Cordova odebrat, musíte také odebrat platformu iOS a znovu ji přidat, abyste vrátili zpět některé konfigurace Intune v souborech .xcodeproj a .plist.



<!--HONumber=Nov16_HO4-->


