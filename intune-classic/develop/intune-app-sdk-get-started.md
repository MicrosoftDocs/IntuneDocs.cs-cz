---
title: "Začínáme s Microsoft Intune App SDK | Dokumentace Microsoftu"
description: "Umožní vám rychle povolit u vaší mobilní aplikace správu mobilních aplikací (MAM) pomocí Microsoft Intune."
keywords: 
author: mtillman
manager: angrobe
ms.author: oydang
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 95c12111693e00fb6f67d20464dd159aeb4bb609
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="get-started-with-the-microsoft-intune-app-sdk"></a>Začínáme s Microsoft Intune App SDK

Tato příručka vám pomůže rychle povolit u vaší mobilní aplikace zásady ochrany aplikací pomocí Microsoft Intune. Může být vhodné se nejdříve seznámit s výhodami sady Intune App SDK, které jsou vysvětlené v [Přehledu sady Intune App SDK](intune-app-sdk.md).

Intune App SDK podporuje podobné scénáře v systémech iOS a Android a je určená k vytvoření konzistentního prostředí pro správce IT pracující na různých platformách. Vzhledem k omezením platforem ale existují v podpoře některých funkcí malé rozdíly.

## <a name="register-your-store-app-with-microsoft"></a>Registrace aplikace ze Storu s Microsoftem

### <a name="if-your-app-is-internal-to-your-organization-and-will-not-be-publicly-available"></a>Pokud aplikaci používáte v organizaci interně a nebude veřejně dostupná:

Aplikaci *nemusíte* registrovat. Interní obchodní aplikace nasazuje správce IT interně. Intune rozpozná, že je aplikace vytvořená pomocí sady SDK, a umožní správci IT, aby u ní použil zásady ochrany aplikací. Můžete přeskočit k části [Povolení zásad ochrany aplikací v aplikaci pro iOS nebo Android](#enable-your-iOS-or-Android-app-for-app-protection-policy).

### <a name="if-your-app-will-be-released-to-a-public-app-store-like-the-apple-app-store-or-google-play"></a>Pokud bude vaše aplikace vydána ve veřejném obchodě s aplikacemi, například Apple App Storu nebo Google Play:

_**Musíte**_ aplikaci nejdřív zaregistrovat ve službě Microsoft Intune a odsouhlasit podmínky registrace. Správci IT potom můžou u podporované aplikace použít zásady ochrany aplikací. Ta pak bude uvedená jako partnerská aplikace Intune.

Do té doby, než bude registrace dokončena a potvrzena týmem Microsoft Intune, nebudou mít správci Intune možnost použít zásady ochrany aplikací na přímý odkaz na vaši aplikaci. Microsoft vaši aplikací přidá také na [stránku partnerů Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps). Tady se zobrazí ikona aplikace označující, že aplikace podporuje zásady ochrany aplikací Intune.

Pokud chcete zahájit registraci, vyplňte [dotazník pro partnery s aplikací pro Microsoft Intune](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u).

E-mailové adresy, které uvedete ve svých odpovědích v dotazníku, použijeme k tomu, abychom se s vámi mohli spojit a pokračovat v registraci. Registrační e-mailová adresa slouží také k tomu, abychom vás mohli kontaktovat v případě jakýchkoliv nejasností.

> [!NOTE]
> Všechny informace shromážděné prostřednictvím dotazníku a e-mailové korespondence s týmem Microsoft Intune používáme v souladu s [Prohlášením o zásadách ochrany osobních údajů společnosti Microsoft](https://www.microsoft.com/privacystatement/default.aspx).

**Jak probíhá registrace**:

1. Po odeslání dotazníku vás budeme kontaktovat na e-mailové adrese použité k registraci a potvrdíme úspěšný příjem, případně vás požádáme o další informace potřebné k dokončení registrace.

2. Jakmile od vás získáme všechny potřebné informace, pošleme vám k podpisu smlouvu pro partnery s aplikací pro Microsoft Intune. Tato smlouva popisuje podmínky, které vaše společnost musí splnit, aby se mohla stát partnerem pro aplikace Microsoft Intune.

3. Jakmile bude aplikace úspěšně zaregistrovaná ve službě Microsoft Intune a uvedená na webu pro [partnery služby Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps), dostanete o tom zprávu.

4. Nakonec přidáme přímý odkaz na vaši aplikaci do další měsíční aktualizace služby Intune. Pokud se například proces registrace dokončí v červenci, bude se přímý odkaz podporovat v polovině srpna.

Pokud se v budoucnosti přímý odkaz na aplikaci změní, budete ji muset znovu zaregistrovat.

> [!NOTE]
> Informujte nás prosím v případě, že aktualizujete aplikaci novou verzí sady Intune App SDK.



## <a name="download-the-sdk-files"></a>Stažení souborů sady SDK

Sady Intune App SDK pro nativní systémy iOS a Android jsou hostované v účtu služby Microsoft GitHub. Tato veřejná úložiště obsahují soubory sady SDK pro nativní iOS a Android:

* [Intune App SDK pro iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Intune App SDK pro Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

Pokud je vaše aplikace vytvořená v Xamarinu nebo Cordově, použijte prosím následující varianty sady SDK:

* [Komponenta Xamarin sady Intune App SDK](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Modul plug-in Cordova sady Intune App SDK](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Doporučujeme, abyste si zaregistrovali na GitHubu účet, který je možné použít k operacím fork a pull v našich úložištích. GitHub vývojářům umožňuje komunikovat s naším produktovým týmem, hlásit problémy a dostávat rychlé odpovědi, zobrazit poznámky k verzi a posílat připomínky do Microsoftu. S dotazy ke GitHubu pro Intune App SDK se obraťte na msintuneappsdk@microsoft.com.





## <a name="enable-your-ios-or-android-app-for-app-protection-policy"></a>Povolení zásad ochrany aplikací v aplikaci pro iOS nebo Android

Budete potřebovat jednu z následujících příruček pro vývojáře, která vám pomůže integrovat Intune App SDK do vaší aplikace:

* **[Příručka pro vývojáře sady Intune App SDK pro iOS](intune-app-sdk-ios.md)**: Tento dokument vás detailně provede procesem povolování vaší nativní aplikace pro iOS pomocí Intune App SDK.

* **[Příručka pro vývojáře sady Intune App SDK pro Android](intune-app-sdk-android.md)**: Tento dokument vás detailně provede procesem povolování vaší nativní aplikace pro Android pomocí Intune App SDK.

* **[Příručka k modulu plug-in Cordova sady Intune App SDK](intune-app-sdk-cordova.md)**: Tento dokument vám pomůže vytvářet aplikace pro iOS a Android pomocí zásad ochrany aplikací Cordova for Intune.

* **[Příručka ke komponentě Xamarin sady Intune App SDK](intune-app-sdk-xamarin.md)**: Tento dokument vám pomůže vytvářet aplikace pro iOS a Android pomocí zásad ochrany aplikací Cordova for Intune.




## <a name="configure-telemetry-for-your-app"></a>Konfigurace telemetrie pro vaši aplikaci

Microsoft Intune shromažďuje data statistik využití vaši aplikace.

* **Intune App SDK pro iOS**: SDK ve výchozím nastavení protokoluje telemetrická data SDK o událostech využití. Tato data se odešlou do Microsoft Intune.

    * Pokud se rozhodnete neodesílat telemetrická data sady SDK z aplikace do Microsoft Intune, musíte ve slovníku IntuneMAMSettings zakázat přenos telemetrie nastavením vlastnosti `MAMTelemetryDisabled` na hodnotu YES.


* **Intune App SDK pro Android**: Telemetrické údaje se neprotokolují pomocí sady SDK.

## <a name="next-steps-after-integration"></a>Další postup po integraci

### <a name="test-your-app"></a>Otestování aplikace
Po dokončení nezbytných kroků k integraci vaší aplikace pro iOS nebo Android se sadou Intune App SDK se musíte ujistit, že mají uživatelé a správci IT povolené a funkční všechny zásady ochrany aplikací. K testování integrované aplikace budete potřebovat následující:

* **Testovací účet Microsoft Intune**: Jestli chcete otestovat aplikaci podporující Intune s funkcemi ochrany aplikací Intune, budete potřebovat účet Microsoft Intune.

    * Pokud jste nezávislý dodavatel softwaru a povolujete zásady ochrany aplikací v Intune pro aplikace ze Storu pro iOS nebo Android, dostanete po dokončení registrace v Microsoft Intune propagační kód (jak je uvedeno během registrace). Tento propagační kód vám umožní zaregistrovat si Microsoft Intune po zkušební verzi na další rok používání.

    * Pokud vyvíjíte podnikovou aplikaci, kterou nebudete odesílat do Storu, předpokládá se, že máte přístup k Microsoft Intune prostřednictvím své organizace. Můžete si také v [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) zaregistrovat zkušební verzi na měsíc zdarma.

* **Zásady ochrany aplikací Intune**: Pokud chcete otestovat aplikaci se všemi zásadami ochrany aplikací Intune, měli byste vědět, jaké chování je očekávané pro každé nastavení zásad. Více najdete v popisech [zásad ochrany aplikací pro iOS](../deploy-use/ios-mam-policy-settings.md) a [zásad ochrany aplikací pro Android](../deploy-use/android-mam-policy-settings.md).

* **Řešení potíží**: Pokud narazíte na problémy při ručním testování uživatelského prostředí vaší aplikace, podívejte se na [Řešení potíží se správou mobilních aplikací](../troubleshoot/troubleshoot-mam.md). Tento článek poskytuje nápovědu pro běžné problémy, dialogová okna a chybové zprávy, s kterými se můžete setkat v aplikacích podporujících Intune. 

### <a name="badge-your-app-optional"></a>Označte si aplikaci (volitelné)

Po ověření, že zásady ochrany aplikací Intune ve vaší aplikaci fungují, můžete označit ikonu aplikace logem ochrany aplikací Intune.

Tento znak říká správcům IT, koncovým uživatelům a potenciálním zákazníkům Intune, že vaše aplikace funguje se zásadami ochrany aplikací Intune. Podporuje to využívání a přijetí vaší aplikace u zákazníků Intune.

Jde o ikonu aktovky a můžete si ji prohlédnout níže:

![Příklad znaku 1](../media/intune-app-badge/example-1.png) ![Příklad znaku 2](../media/intune-app-badge/example-2.png)

**Co budete potřebovat k označení aplikace**:

* Aplikaci pro zpracování obrázků, která umí přečíst soubory **.eps**, nebo aplikaci Adobe, která umí přečíst soubory **.ai**.

* Na Githubu pro Microsoft Intune najdete [prostředky a pokyny pro označení aplikace pro Intune](https://github.com/msintuneappsdk/intune-app-partner-badge).

