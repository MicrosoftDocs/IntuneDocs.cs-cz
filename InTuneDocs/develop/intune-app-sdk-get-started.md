---
title: "Začínáme s Microsoft Intune App SDK | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8bc2f6e8dcf9d0ac3e7fccec792c86ff1fd4131c
ms.openlocfilehash: 15be877edbdeb827a4318af226ea8cde8c8e46f4


---

# <a name="get-started-with-the-microsoft-intune-app-sdk"></a>Začínáme s Microsoft Intune App SDK

Tato příručka vám pomůže rychle povolit u vaší mobilní aplikace správu mobilních aplikací (MAM) pomocí Microsoft Intune. Může být vhodné se nejdříve seznámit s výhodami sady Intune App SDK, které jsou vysvětlené v [Přehledu sady Intune App SDK](intune-app-sdk.md).

Tato příručka vás provede hlavními kroky povolení správy mobilních aplikací ve vaší aplikaci pomocí Microsoft Intune. Sada Intune App SDK podporuje podobné scénáře napříč platformami a je určená k vytvoření konzistentního prostředí pro správce IT pracující na různých platformách. Vzhledem k omezením platforem ale existují v podpoře některých funkcí malé rozdíly.

## <a name="register-your-store-app-with-microsoft"></a>Registrace aplikace ze Storu s Microsoftem

**Pokud je vaše aplikace interní a nebude dostupná pro veřejné obchody s aplikacemi**:

Aplikaci *nemusíte* registrovat. Interní obchodní aplikace nasazuje správce IT interně. Intune rozpozná, že je aplikace vytvořená pomocí sady SDK, a umožní správci IT, aby u ní použil nastavení zásad MAM. Můžete přeskočit k části [Povolení mobilní aplikace pro iOS nebo Android pro MAM s SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk).

**Pokud bude vaše aplikace vydána ve veřejném obchodě s aplikacemi, například Apple App Storu nebo Google Play**:

*Musíte* aplikaci nejdřív zaregistrovat ve službě Microsoft Intune a odsouhlasit podmínky registrace. Správci IT potom můžou u podporovaných aplikací použít nastavení zásad MAM v Intune. Ty pak budou uvedené jako partnerské aplikace Intune. Než se registrace dokončí a tým Microsoft Intune ji potvrdí, nebudou mít správci Intune možnost použít u přímého odkazu na vaši aplikaci zásady MAM. Microsoft vaši aplikací přidá také na [stránku partnerů Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps). Tady se zobrazí ikona aplikace označující, že aplikace podporuje zásady MAM služby Microsoft Intune.

Pokud chcete zahájit registraci, vyplňte [dotazník pro partnery s aplikací pro Microsoft Intune](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u).

E-mailové adresy, které uvedete ve svých odpovědích v dotazníku, použijeme k tomu, abychom se s vámi mohli spojit a pokračovat v registraci. Registrační e-mailová adresa slouží také k tomu, abychom vás mohli kontaktovat v případě jakýchkoliv nejasností.

> [!NOTE]
> Všechny informace shromážděné prostřednictvím dotazníku a e-mailové korespondence s týmem Microsoft Intune používáme v souladu s [Prohlášením o zásadách ochrany osobních údajů společnosti Microsoft](https://www.microsoft.com/en-us/privacystatement/default.aspx).

**Jak probíhá registrace**:

1. Po odeslání dotazníku vás budeme kontaktovat na e-mailové adrese použité k registraci a potvrdíme úspěšný příjem, případně vás požádáme o další informace potřebné k dokončení registrace.
2. Jakmile od vás získáme všechny potřebné informace, pošleme vám k podpisu smlouvu pro partnery s aplikací pro Microsoft Intune. Tato smlouva popisuje podmínky, které vaše společnost musí splnit, aby se mohla stát partnerem pro aplikace Microsoft Intune.
3. Jakmile bude aplikace úspěšně zaregistrovaná ve službě Microsoft Intune a uvedená na webu pro [partnery služby Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps), dostanete o tom zprávu.
4. Nakonec přidáme přímý odkaz na vaši aplikaci do další měsíční aktualizace služby Intune. Pokud se například proces registrace dokončí v červenci, bude se přímý odkaz podporovat v polovině srpna.

Pokud se v budoucnosti přímý odkaz na aplikaci změní, budete ji muset znovu zaregistrovat. Také nás prosím informujte, pokud k aktualizaci aplikace použijete novou verzi sady Intune App SDK.



## <a name="download-the-sdk-files"></a>Stažení souborů sady SDK

Sady Intune App SDK pro nativní systémy iOS a Android jsou hostované v účtu služby Microsoft GitHub. Tato veřejná úložiště obsahují soubory sady SDK pro iOS a Android:

* [Intune App SDK pro iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Intune App SDK pro Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

Pokud je vaše aplikace vytvořená v Xamarinu nebo Cordově, použijte prosím následující vývojářské nástroje:

* [Komponenta Xamarin sady Intune App SDK](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Modul plug-in Cordova sady Intune App SDK](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Doporučujeme, abyste si zaregistrovali na GitHubu účet, který je možné použít k operacím fork a pull v našich úložištích. GitHub vývojářům umožňuje komunikovat s naším produktovým týmem, hlásit problémy a dostávat rychlé odpovědi, zobrazit poznámky k verzi a posílat připomínky do Microsoftu. V případě dotazů k účtu a úložištím na GitHubu se obraťte na adresu msintuneappsdk@microsoft.com.





## <a name="enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk"></a>Povolení mobilní aplikace systému iOS nebo Android pro MAM s SDK

K integraci sady Intune App SDK do nativní aplikace pro iOS budete potřebovat následující příručku:

* **[Příručka pro vývojáře sady Intune App SDK pro iOS](intune-app-sdk-ios.md)**: Tento dokument vás detailně provede procesem povolování mobilních aplikací s iOSem pomocí sady Intune App SDK.


K integraci sady Intune App SDK do nativní aplikace pro Android budete potřebovat následující příručku:

* **[Příručka pro vývojáře sady Intune App SDK pro Android](intune-app-sdk-android.md)**: Tento dokument vás detailně provede procesem povolování mobilních aplikací s Androidem pomocí sady Intune App SDK.

Dokumentaci ke komponentě Xamarin sady Intune App SDK a k pluginu Cordova sady Intune App SDK najdete v příslušných úložištích GitHubu.


## <a name="set-up-telemetry-for-your-app"></a>Nastavení telemetrie pro aplikaci

Microsoft Intune shromažďuje data statistik využití vaši aplikace.

* **Intune App SDK pro iOS**: SDK ve výchozím nastavení protokoluje telemetrická data SDK o událostech využití. Tato data se odešlou do Microsoft Intune.

    * Pokud se rozhodnete neodesílat telemetrická data sady SDK z aplikace do Microsoft Intune, musíte ve slovníku IntuneMAMSettings zakázat přenos telemetrie nastavením vlastnosti `MAMTelemetryDisabled` na hodnotu YES.

* **Intune App SDK pro Android**: Telemetrické údaje se neprotokolují pomocí sady SDK.

## <a name="test-your-mamenabled-app-with-microsoft-intune"></a>Testování aplikace s povolenou správou mobilních aplikací s Microsoft Intune

Po dokončení nezbytných kroků k integraci vaší aplikace pro iOS nebo Android se sadou Intune App SDK se musíte ujistit, že mají uživatelé a správci IT povolené a funkční všechny zásady správy aplikací. K testování integrované aplikace budete potřebovat následující:

<!--TODO-->

* **Testování aplikace s povolenou správou mobilních aplikací s Microsoft Intune**: Tento dokument vás podrobně provede postupem testování aplikací s podporou správy mobilních aplikací pro iOS nebo Android s Microsoft Intune. Tento dokument najdete v úložištích GitHub sad SDK.

* **Účet Microsoft Intune**: K testování aplikace s povolenou správou mobilních aplikací pomocí Microsoft Intune budete potřebovat účet Microsoft Intune.
    * Pokud jste nezávislý dodavatel softwaru a povolujete správu mobilních aplikací v Intune pro aplikace ze Storu pro iOS nebo Android, dostanete po dokončení registrace v Microsoft Intune propagační kód (jak je uvedeno během registrace). Tento propagační kód vám umožní zaregistrovat si Microsoft Intune po zkušební verzi na další rok používání.
    * Pokud vyvíjíte podnikovou aplikaci, kterou nebudete odesílat do Storu, předpokládá se, že máte přístup k Microsoft Intune prostřednictvím své organizace. Můžete si také v [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) zaregistrovat zkušební verzi na měsíc zdarma.



<!--HONumber=Nov16_HO3-->


