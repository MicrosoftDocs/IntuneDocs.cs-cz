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
ms.sourcegitcommit: ba9ba203c9ec173dafd1d6f9e4828d4a8a51e1ef
ms.openlocfilehash: 136dd127c5e0f1784746b973ebc5594573f07925


---

# Začínáme s Microsoft Intune App SDK

Tato úvodní příručka vám pomůže rychle povolit mobilní aplikace pro správu mobilních aplikací pomocí Microsoft Intune. Možná bude vhodné, když nejdřív pochopíte výhody sady Intune App SDK, které jsou uvedené v [Přehledu sady Intune App SDK](intune-app-sdk.md).

Tento průvodce vás provede důležitými kroky potřebnými k povolení správy mobilních aplikací ve vaší aplikaci pomocí Microsoft Intune. Sada Intune App SDK podporuje podobné scénáře napříč platformami a je určená k vytvoření konzistentního prostředí pro správce IT napříč platformami. Vzhledem k omezením platforem ale existují v podpoře některých funkcí malé rozdíly.

# Getting Started (Začínáme)

## Registrace aplikace ze Storu s Microsoftem

**Pokud je vaše aplikace interní a nebude dostupná pro veřejné obchody s aplikacemi**:

Aplikaci **nemusíte** registrovat. V případě interních obchodních aplikací správce IT takové aplikace nasadí interně pomocí Microsoft Intune. Intune rozpozná, že aplikace je vytvořená pomocí sady SDK, a umožní správci IT, aby na aplikaci použil nastavení zásad MAM. Můžete přeskočit k části [Povolení mobilní aplikace pro iOS nebo Android pro MAM s SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk).

**Pokud vaše aplikace bude vydána do veřejného obchodu s aplikacemi, například Apple App Storu nebo Google Play**: 

**Musíte** aplikaci nejdřív zaregistrovat ve službě Microsoft Intune a odsouhlasit podmínky registrace. Po registraci můžou správci IT na podporované aplikace použít nastavení zásad MAM v Intune, což bude potom uvedeno jako partner aplikace Intune. Do té doby, než bude registrace dokončena a potvrzena týmem Microsoft Intune, nebudou mít správci Intune možnost použít zásady MAM na přímý odkaz na vaši aplikaci. Microsoft aplikaci přidá také na [stránku partnerů Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners), kde se zobrazí ikona aplikace, která znázorňuje podporu zásad MAM pro Microsoft Intune.

Pokud chcete zahájit proces registrace, **přečtěte si a podepište**[smlouvu pro partnery Microsoft Intune](https://connect.microsoft.com/ConfigurationManagervnext/Survey/Survey.aspx?SurveyID=17806). Tato smlouva popisuje podmínky, které vaše společnost musí splnit, než se stane partnerem pro aplikace Microsoft Intune. Před zobrazením tohoto dokumentu se musíte přihlásit. Smlouvu najdete na webu Microsoft Connect sady Intune App SDK na kartě Průzkumy nebo tady. Také vás požádáme o poskytnutí názvu aplikace, názvu vaší společnosti a přímý odkaz na aplikaci ve storu Google nebo iTunes.

![Microsoft Connect](../media/microsoft-connect.png)

K potvrzení a dokončení procesu registrace použijeme e-mailovou adresu použitou při registraci. Navíc použijeme e-mailovou adresu použitou při registraci, abychom vás v případě nejasností kontaktovali.

**V procesu registrace se setkáte s následujícími akcemi**: 

Po odeslání formuláře budete kontaktováni Microsoftem prostřednictvím e-mailové adresy použité při registraci, abyste potvrdili příjem, nebo abychom si vyžádali dodatečné informace k dokončení registrace. Budete také kontaktováni, když bude aplikace úspěšně registrovaná s Microsoft Intune a když bude uvedena na partnerském webu Microsoft Intune. Po potvrzení přijetí informací se přímý odkaz na vaši aplikaci zahrne do aktualizace služby Intune pro příští měsíc. Pokud se například proces registrace dokončí v červenci, přímý odkaz na aplikaci bude podporovaný v polovině srpna. Pokud se v budoucnu přímý odkaz na vaši aplikaci ve Storu změní, budete aplikaci muset znovu zaregistrovat. Také nás informujte v případě, že aktualizujete aplikaci s novou verzí sady Intune App SDK.

**Poznámka**: Se všemi informacemi shromážděnými prostřednictvím výše uvedeného formuláře a prostřednictvím e-mailové korespondence s týmem Intune se nakládá v souladu s [Prohlášením o zásadách ochrany osobních údajů společnosti Microsoft](https://www.microsoft.com/en-us/privacystatement/default.aspx).

## Stažení souborů sady SDK

Sady Intune App SDK pro iOS a Android jsou hostované na účtu GitHub Microsoftu. Níže uvedená veřejná úložiště obsahují soubory sady SDK pro iOS a Android:

* [Intune App SDK pro iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Intune App SDK pro Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

Doporučujeme, abyste si zaregistrovali účet na GitHubu, který můžete použít k rozvětvení a přebírání z našich úložišť. GitHub vývojářům umožňuje komunikovat s naším produktovým týmem, hlásit problémy a dostávat rychlé odpovědi, zobrazit poznámky k verzi a zasílat připomínky do Microsoftu. V případě dotazů k účtu a úložištím na GitHubu se obraťte na adresu msintuneappsdk@microsoft.com.

## Povolení mobilní aplikace systému iOS nebo Android pro MAM s SDK

K integraci sady Intune App SDK do aplikace pro iOS budete potřebovat následující: 

* **[Příručka pro vývojáře sady Intune App SDK pro iOS](intune-app-sdk-ios.md)**: Tento dokument vás detailně provede procesem povolování mobilních aplikací s iOS pomocí sady Intune App SDK. 


K integraci sady Intune App SDK do aplikace pro Android budete potřebovat následující:

* **[Příručka pro vývojáře sady Intune App SDK pro Android](intune-app-sdk-android.md)**: Tento dokument vás detailně provede procesem povolování mobilních aplikací s Androidem pomocí sady Intune App SDK. 



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




<!--HONumber=Sep16_HO4-->


