---
title: "Příprava aplikací pro správu mobilních aplikací | Microsoft Intune"
description: "Informace v tomto tématu vám pomůžou rozhodnout, kdy byste měli použít nástroj App Wrapping a sadu App SDK, aby vaše vlastní obchodní aplikace mohly používat zásady správy mobilních aplikací."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ee7e0491c0635c45cbc0377a5de01d5eba851132
ms.openlocfilehash: 3d7b60862942742d663ff23c7b5f3fd135c72640


---

# <a name="decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune"></a>Rozhodování o způsobu přípravy aplikací na správu mobilních aplikací v Microsoft Intune
Svým aplikacím můžete umožnit použití zásad správy mobilních aplikací (MAM) buď prostřednictvím nástroje Intune App Wrapping, nebo pomocí sady Intune App SDK. V tomto tématu se dozvíte, co tyto dvě metody obnáší a kdy je použít.

## <a name="intune-app-wrapping-tool"></a>Nástroj Intune App Wrapping
Nástroj App Wrapping se používá hlavně pro interní obchodní aplikace. Je to aplikace příkazového řádku, která vytvoří kolem aplikace obálku, a ta potom umožní správu aplikace pomocí zásad MAM v Intune.

K použití nástroje nepotřebujete zdrojový kód, ale potřebujete přihlašovací údaje k podepisování.  Další informace o přihlašovacích údajích k podepisování najdete v [blogu o Intune](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Dokumentaci k nástroji App Wrapping najdete v tématech [Nástroj App Wrapping pro Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) a [Nástroj App Wrapping pro iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

Nástroj App Wrapping **nepodporuje** aplikace v Apple App Storu nebo obchodu Google Play. Nepodporuje ani některé funkce, které vyžadují vývojářskou integraci (viz následující tabulka s porovnáním funkcí).


Další informace o nástroji App Wrapping pro MAM na zařízeních, která nejsou registrovaná do Intune, najdete v článku [Ochrana obchodních aplikací a dat na zařízeních neregistrovaných do Microsoft Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

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

Další informace o sadě SDK najdete v tématu [Přehled](/intune/develop/intune-app-sdk). Pokud chcete začít používat sadu SDK, přečtěte si téma [Začínáme s Microsoft Intune App SDK](/intune/develop/intune-app-sdk-get-started).

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
|**iOS**|Ano – Použijte [komponentu Xamarin sady Intune App SDK](/../develop/intune-app-sdk-xamarin).|Ano – Použijte [modul plug-in Cordova sady Intune App SDK](/../develop/intune-app-sdk-cordova).|
|**Android**| Ano – Použijte [komponentu Xamarin sady Intune App SDK](/../develop/intune-app-sdk-xamarin).|Ano – Použijte [modul plug-in Cordova sady Intune App SDK](/../develop/intune-app-sdk-cordova).|

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
|Úplné vymazání|X|X|
|Selektivní vymazání <br></br>**Poznámka:** V iOS platí, že při odebrání profilu pro správu se odebere taky příslušná aplikace.|X||
|Zabránit možnosti Uložit jako |X||
|Podpora víc identit|X||
|Podpora MAM bez registrace zařízení|X|X|
|Přizpůsobitelný styl |X|||
### <a name="see-also"></a>Související témata

[Nástroj App Wrapping Tool a aplikace pro Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Nástroj App Wrapping Tool a aplikace pro iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Použití sady SDK k povolení správy mobilních aplikací pro aplikace](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Dec16_HO2-->


