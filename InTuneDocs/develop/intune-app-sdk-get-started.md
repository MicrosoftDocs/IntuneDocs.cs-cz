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
ms.sourcegitcommit: ed1008c786285821c608a8404805c6615c60507f
ms.openlocfilehash: c80868fdee79df62aae0aa64e378be5dcc9664ae


---

# Začínáme s Microsoft Intune App SDK

Tato úvodní příručka vám pomůže rychle povolit mobilní aplikace pro správu mobilních aplikací pomocí Microsoft Intune. Možná bude vhodné, když nejdřív pochopíte výhody sady Intune App SDK, které jsou uvedené v [Přehledu sady Intune App SDK](intune-app-sdk.md).

Tento průvodce vás provede důležitými kroky potřebnými k povolení správy mobilních aplikací ve vaší aplikaci pomocí Microsoft Intune. Sada Intune App SDK podporuje podobné scénáře napříč platformami a je určená k vytvoření konzistentního prostředí pro správce IT napříč platformami. Vzhledem k omezením platforem ale existují v podpoře některých funkcí malé rozdíly.

# Getting Started (Začínáme)

## Registrace aplikace ze Storu s Microsoftem

**Pokud je vaše aplikace interní a nebude dostupná pro veřejné obchody s aplikacemi**:

Aplikaci **nemusíte** registrovat. Interní obchodní aplikace nasazuje správce IT interně. Intune rozpozná, že aplikace byla vytvořena pomocí SDK, a umožní správci IT, aby u ní použil nastavení zásad MAM. Můžete přeskočit k části [Povolení mobilní aplikace pro iOS nebo Android pro MAM s SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk).

**Pokud vaše aplikace bude vydána do veřejného obchodu s aplikacemi, například Apple App Storu nebo Google Play**: 

**Musíte** aplikaci nejdřív zaregistrovat ve službě Microsoft Intune a odsouhlasit podmínky registrace. Po registraci můžou správci IT na podporované aplikace použít nastavení zásad MAM v Intune, což bude potom uvedeno jako partner aplikace Intune. Do té doby, než bude registrace dokončena a potvrzena týmem Microsoft Intune, nebudou mít správci Intune možnost použít zásady MAM na přímý odkaz na vaši aplikaci. Microsoft aplikaci přidá také na [stránku partnerů Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps), kde se zobrazí ikona aplikace, která znázorňuje podporu zásad MAM pro Microsoft Intune.

Pokud chcete zahájit registraci, vyplňte **[dotazník pro partnery s aplikací pro Microsoft Intune](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u)**. 

Microsoft použije e-mailové adresy, které uvedete ve svých odpovědích v dotazníku, a obrátí se na vás, aby pokračoval v registraci. Navíc použijeme e-mailovou adresu použitou při registraci, abychom vás v případě nejasností kontaktovali.

> [!NOTE]
> Se všemi informacemi shromážděnými prostřednictvím dotazníku a e-mailové korespondence s týmem Microsoft Intune se nakládá v souladu s [Prohlášením o zásadách ochrany osobních údajů společnosti Microsoft](https://www.microsoft.com/en-us/privacystatement/default.aspx).

**V procesu registrace se setkáte s následujícími akcemi**: 

1. Po odeslání dotazníku vás bude Microsoft kontaktovat na e-mailovou adresu použitou k registraci, aby buď potvrdil úspěšný příjem, nebo požádal o další informace potřebné k dokončení registrace. 
2. Jakmile od vás získáme všechny potřebné informace, pošleme vám k podpisu smlouvu pro partnery s aplikací pro Microsoft Intune. Tato smlouva popisuje podmínky, které vaše společnost musí splnit, než se stane partnerem pro aplikace Microsoft Intune. 
3. Jakmile bude aplikace úspěšně zaregistrovaná ve službě Microsoft Intune a uvedená na webu pro [partnery služby Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps), dostanete o tom zprávu. 
4. Nakonec bude do další měsíční aktualizace služby Intune přidán přímý odkaz na vaši aplikaci. Pokud se například proces registrace dokončí v červenci, přímý odkaz na aplikaci bude podporovaný v polovině srpna. 

Pokud se v budoucnosti přímý odkaz na aplikaci ve Storu změní, budete ji muset znovu zaregistrovat. Také nás prosím informujte, pokud k aktualizaci aplikace použijete novou verzi sady Intune App SDK.



## Stažení souborů sady SDK

Sady Intune App SDK pro nativní systémy iOS a Android jsou hostované v účtu služby Microsoft GitHub. Níže uvedená veřejná úložiště obsahují soubory sady SDK pro iOS a Android:

* [Intune App SDK pro iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Intune App SDK pro Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

**Pokud je vaše aplikace vytvořená v Xamarinu nebo Cordově, použijte prosím následující vývojářské nástroje:**

* [Komponenta Xamarin sady Intune App SDK](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Plugin Cordova sady Intune App SDK](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Doporučujeme, abyste si zaregistrovali účet na GitHubu, který můžete použít k rozvětvení a přebírání z našich úložišť. GitHub vývojářům umožňuje komunikovat s naším produktovým týmem, hlásit problémy a dostávat rychlé odpovědi, zobrazit poznámky k verzi a zasílat připomínky do Microsoftu. V případě dotazů k účtu a úložištím na GitHubu se obraťte na adresu msintuneappsdk@microsoft.com.





## Povolení mobilní aplikace systému iOS nebo Android pro MAM s SDK

K integraci sady Intune App SDK do nativní aplikace pro iOS budete potřebovat následující příručku: 

* **[Příručka pro vývojáře sady Intune App SDK pro iOS](intune-app-sdk-ios.md)**: Tento dokument vás detailně provede procesem povolování mobilních aplikací s iOS pomocí sady Intune App SDK. 


K integraci sady Intune App SDK do nativní aplikace pro Android budete potřebovat následující příručku:

* **[Příručka pro vývojáře sady Intune App SDK pro Android](intune-app-sdk-android.md)**: Tento dokument vás detailně provede procesem povolování mobilních aplikací s Androidem pomocí sady Intune App SDK. 

Dokumentaci ke komponentě Xamarin sady Intune App SDK a k pluginu Cordova sady Intune App SDK najdete v příslušných úložištích GitHubu. 


## Konfigurace telemetrie pro aplikaci

Microsoft Intune shromažďuje data statistik využití vaši aplikace.

* **Intune App SDK pro iOS**: SDK ve výchozím nastavení protokoluje telemetrická data SDK o událostech využití. Tato data se odešlou do Microsoft Intune.

    * Pokud se rozhodnete neodesílat telemetrická data sady SDK z aplikace do Microsoft Intune, musíte ve slovníku IntuneMAMSettings zakázat přenos telemetrie nastavením vlastnosti `MAMTelemetryDisabled` na hodnotu YES.

* **Intune App SDK pro Android**: Telemetrické údaje se neprotokolují pomocí sady SDK.

## Testování aplikace s povoleným MAM s Microsoft Intune

Po dokončení nezbytných kroků k integraci vaší aplikace pro iOS nebo Android se sadou Intune App SDK se musíte ujistit, že všechny zásady správy aplikací jsou pro koncové uživatele a správce IT povolené a funkční. K testování integrované aplikace budete potřebovat následující:

<!--TODO-->

* **Testování aplikace s povoleným MAM s Microsoft Intune**: Tento dokument vás podrobně provede postupem testování aplikací s podporou MAM pro iOS nebo Android s Microsoft Intune. Tento dokument najdete v úložištích GitHub sad SDK.

* **Účet Microsoft Intune**: K testování aplikace s povoleným MAM pomocí Microsoft Intune budete potřebovat účet Microsoft Intune. 
    * Pokud jste nezávislý dodavatel softwaru a povolujete Intune MAM pro aplikace ze Storu pro iOS nebo Android, obdržíte po dokončení registrace do Microsoft Intune propagační kód (jak je uvedeno v kroku registrace). Tento propagační kód vám umožní zaregistrovat zkušební verzi Microsoft Intune na rok rozšířeného používání. 
    * Pokud vyvíjíte podnikovou aplikaci, která nebude odeslaná do Storu, předpokládá se, že máte přístup k Microsoft Intune prostřednictvím vaší organizace. Můžete si taky zaregistrovat k měsíční zkušební verzi zdarma s [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).




<!--HONumber=Nov16_HO1-->


