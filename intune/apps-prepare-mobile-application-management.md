---
title: "Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune"
description: "Informace v tomto tématu vám pomůžou rozhodnout, kdy byste měli použít nástroj App Wrapping a sadu App SDK, aby vaše vlastní obchodní aplikace mohly používat zásady správy mobilních aplikací."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e8b218ce38a7e76135a62b1155dbf9060ba511cc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="prepare-line-of-business-apps-for-mam"></a>Příprava obchodních aplikací pro MAM

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Svým aplikacím můžete umožnit použití zásad správy mobilních aplikací (MAM) buď prostřednictvím nástroje Intune App Wrapping, nebo pomocí sady Intune App SDK. V tomto tématu se dozvíte, co tyto dvě metody obnáší a kdy je použít.

## <a name="intune-app-wrapping-tool"></a>Nástroj Intune App Wrapping
Nástroj App Wrapping se používá hlavně pro interní obchodní aplikace. Je to aplikace příkazového řádku, která vytvoří kolem aplikace obálku, a ta potom umožní správu aplikace pomocí zásad MAM v Intune.

K použití nástroje nepotřebujete zdrojový kód, ale potřebujete přihlašovací údaje k podepisování.  Další informace o přihlašovacích údajích k podepisování najdete v [blogu o Intune](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Dokumentaci k nástroji App Wrapping najdete v tématech [Nástroj App Wrapping pro Android](app-wrapper-prepare-android.md) a [Nástroj App Wrapping pro iOS](app-wrapper-prepare-ios.md).

Nástroj App Wrapping **nepodporuje** aplikace v Apple App Storu nebo obchodu Google Play. Nepodporuje ani některé funkce, které vyžadují vývojářskou integraci (viz následující tabulka s porovnáním funkcí).


Další informace o nástroji App Wrapping pro MAM na zařízeních, která nejsou registrovaná do Intune, najdete v článku [Ochrana obchodních aplikací a dat na zařízeních neregistrovaných do Microsoft Intune](/intune-classic/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune).

### <a name="reasons-to-use-the-app-wrapping-tool"></a>Důvody pro použití nástroje App Wrapping:
* Aplikace nemá předdefinované funkce ochrany dat.
* Aplikace je jednoduchá.
* Aplikace je nasazená interně.
* Nemáte přístup ke zdrojovému kódu aplikace.
* Aplikaci jste nevyvinuli.
* Aplikace zahrnuje minimální funkce ověřování uživatelů.


### <a name="supported-app-development-platforms"></a>Podporované platformy vývoje aplikací

|**Nástroj App Wrapping** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Ano|Ano|
|**Androidemem**| Ne |Ano|

## <a name="intune-app-sdk"></a>Sada Intune App SDK
Sada App SDK je určená hlavně zákazníkům, kteří mají aplikace v App Storu nebo obchodu Google Play a chtějí mít možnost spravovat je pomocí Intune. Nicméně využít integraci sady SDK může jakákoli aplikace, i obchodní aplikace.

Další informace o sadě SDK najdete v tématu [Přehled](app-sdk.md). Pokud chcete začít používat sadu SDK, přečtěte si téma [Začínáme s Microsoft Intune App SDK](app-sdk-get-started.md).

### <a name="reasons-to-use-the-sdk"></a>Důvody pro použití sady SDK
* Aplikace nemá předdefinované funkce ochrany dat.
* Aplikace je komplexní a obsahuje mnoho funkcí.
* Aplikace je nasazena prostřednictvím veřejného obchodu s aplikacemi, jako je Google Play nebo App Store společnosti Apple.
* Jste vývojář aplikací a máte technické znalosti potřebné k použití sady SDK.
* Aplikace zahrnuje další integrace pomocí sady SDK.
* Aplikace je často aktualizována.

### <a name="supported-app-development-platforms"></a>Podporované platformy vývoje aplikací

|**Intune App SDK** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Ano – Použijte [komponentu Xamarin sady Intune App SDK](app-sdk-xamarin.md).|Ano – Použijte [modul plug-in Cordova sady Intune App SDK](app-sdk-cordova.md).|
|**Android**| Ano – Použijte [komponentu Xamarin sady Intune App SDK](app-sdk-xamarin.md).|Ano – Použijte [modul plug-in Cordova sady Intune App SDK](app-sdk-cordova.md).|

## <a name="feature-comparison"></a>Porovnání funkcí
Tato tabulka obsahuje seznam nastavení, která můžete použít v sadě SDK a nástroji App Wrapping.

> [!NOTE]
> Nástroj App Wrapping Tool se dá použít se samostatnou službu Intune nebo Intune s Configuration Managerem.

|Funkce|Sada App SDK|Nástroj App Wrapping|
|-----------|---------------------|-----------|
|Omezit zobrazování obsahu webu jenom na podnikový spravovaný prohlížeč|X|X|
|Zabránit zálohování Androidu, iTunes a iCloudu|X|X|
|Povolit aplikaci přenos dat do ostatních aplikací|X|X|
|Povolit aplikaci, aby přijímala data z jiných aplikací|X|X|
|Omezit vyjmutí, kopírování a vkládání v ostatních aplikacích|X|X|
|Požadovat jednoduchý kód PIN pro přístup|X|X|
|Nahradit integrovaný PIN kód aplikace PIN kódem Intune|X||
|Určit počet pokusů o zadání PIN kódu před jeho obnovením|X|X|
|Povolit otisk prstu místo PIN kódu |X|X|
|Vyžadovat podnikové přihlašovací údaje pro přístup|X|X|
|Blokovat spuštění spravovaných aplikací v zařízení s jailbreakem nebo rootem|X|X|
|Zašifrovat data aplikací|X|X|
|Znovu zkontrolovat požadavky na přístup po zadaném počtu minut|X|X|
|Zadat období odkladu pro offline režim|X|X|
|Blokovat snímek obrazovky (jenom Android)|X|X|
|Podpora MAM bez registrace zařízení|X|X|
|Úplné vymazání|X|X|
|Selektivní vymazání <br></br>**Poznámka:** V iOSu platí, že při odebrání profilu pro správu se odebere taky příslušná aplikace.|X||
|Zabránit možnosti Uložit jako |X||
|Konfigurace cílové aplikace |X||
|Podpora víc identit|X||
|Přizpůsobitelný styl |X|||
### <a name="see-also"></a>Související témata

[Nástroj App Wrapping Tool a aplikace pro Android](app-wrapper-prepare-android.md)</br>
[Nástroj App Wrapping Tool a aplikace pro iOS](app-wrapper-prepare-ios.md)</br>
[Použití sady SDK k povolení správy mobilních aplikací pro aplikace](/intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management)