---
title: "Začínáme s Microsoft Intune App SDK | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b7f62c5ee18d8f69fa174f09a1c46b6925c7517c
ms.openlocfilehash: a042f0c6206e9aaf4ec0eb012a70930aa95ecc47


---

# Začínáme s Microsoft Intune App SDK

Tato úvodní příručka vám pomůže rychle povolit mobilní aplikace pro správu mobilních aplikací pomocí Microsoft Intune. Možná bude vhodné, když nejdřív pochopíte výhody sady Intune App SDK, které jsou uvedené v [Přehledu sady Intune App SDK](intune-app-sdk.md).

Tento průvodce vás provede důležitými kroky potřebnými k povolení správy mobilních aplikací ve vaší aplikaci pomocí Microsoft Intune. Sada Intune App SDK podporuje podobné scénáře napříč platformami a je určená k vytvoření konzistentního prostředí pro správce IT napříč platformami. Vzhledem k omezením platforem ale existují v podpoře některých funkcí malé rozdíly.

# Getting Started (Začínáme)

## Registrace pro Microsoft Connect

Sada Intune App SDK je aktuálně přístupná prostřednictvím webu Microsoft Connect a vyžaduje registraci. Zaregistrujte si proto pomocí svého podnikového e-mailu [účet Microsoft](https://connect.microsoft.com/ConfigurationManagervnext/InvitationUse.aspx?ProgramID=8967&InvitationID=8967-YJYJ-8G6X).

Registrace bude v nevyřízeném stavu, dokud tým Intune nezkontroluje vaši žádost. Obvyklá doba odezvy se pohybuje do 2 až 3 pracovních dnů. Po schválení obdržíte e-mailem oznámení s odkazy na stažení sady Intune App SDK pro vaše platformy a všechny příslušné průvodce. K těmto průvodcům můžete také přistupovat na webu MSDN.

## Registrace aplikace z App Storu s Microsoft Intune

**Pokud vaše povolená aplikace je interní a nebude zpřístupněna v App Storu Apple nebo Google**: Není nutné aplikaci registrovat. Tyto interní aplikace správce IT načte přímo do konzoly Microsoft Intune pro nasazení, Intune detekuje, že aplikace byla vytvořena pomocí sady SDK, a nabídne správci IT možnost použít na ni zásady MAM. Můžete přeskočit k části s názvem [Povolení mobilní aplikace systému iOS nebo Android pro MAM s SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk).

**Pokud jste nezávislý dodavatel softwaru vyvíjející aplikaci, která bude přístupná zákazníkům prostřednictvím App Storu Apple nebo Google**: Musíte nejprve registrovat aplikaci s Microsoft Intune a přijmout podmínky registrace. V tuto chvíli můžete poskytnout přímý odkaz na aplikaci. Potom může správce IT použít pro aplikaci zásady MAM Intune. Do té doby, než se registrace dokončí a potvrdí týmem Microsoft Intune, přímý odkaz na vaši aplikaci nebude mít možnost použít v konzole správce zásady MAM. Microsoft také udržuje web pro partnery Microsoft Intune, kde bude aplikace registrovaná, aby zákazníci věděli, že podporuje zásady MAM služby Microsoft Intune.

Pokud chcete zahájit proces registrace, **přečtěte si a podepište**[smlouvu pro partnery Microsoft Intune](https://connect.microsoft.com/ConfigurationManagervnext/Survey/Survey.aspx?SurveyID=17806). Tato smlouva popisuje podmínky, které vaše společnost musí splnit, než se stane partnerem pro aplikace Microsoft Intune. Před zobrazením tohoto dokumentu se musíte přihlásit. Smlouvu najdete na webu Microsoft Connect sady Intune App SDK na kartě Průzkumy nebo tady. Také vás požádáme o poskytnutí názvu aplikace, názvu vaší společnosti a přímý odkaz na aplikaci ve storu Google nebo iTunes.

![Microsoft Connect](../media/microsoft-connect.png)

K potvrzení a dokončení procesu registrace použijeme e-mailovou adresu použitou při registraci. Navíc použijeme e-mailovou adresu použitou při registraci, abychom vás v případě nejasností kontaktovali.

**Co očekávat při procesu registrace**: Po odeslání formuláře budete kontaktováni Microsoftem prostřednictvím e-mailové adresy použité při registraci, abyste potvrdili příjem nebo abychom si vyžádali dodatečné informace k dokončení registrace. Budete také kontaktováni, když bude aplikace úspěšně registrovaná s Microsoft Intune a když bude uvedena na partnerském webu Microsoft Intune. Po potvrzení přijetí informací se přímý odkaz na vaši aplikaci zahrne do aktualizace služby Intune pro příští měsíc. Pokud se například proces registrace dokončí v červenci, přímý odkaz na aplikaci bude podporovaný v polovině srpna. Pokud se v budoucnu přímý odkaz na vaši aplikaci ve Storu změní, budete aplikaci muset znovu zaregistrovat. Také nás informujte v případě, že aktualizujete aplikaci s novou verzí sady Intune App SDK.

**Poznámka**: Se všemi informacemi shromážděnými prostřednictvím výše uvedeného formuláře a prostřednictvím e-mailové korespondence s týmem Intune se nakládá v souladu s [Prohlášením o zásadách ochrany osobních údajů společnosti Microsoft](https://www.microsoft.com/en-us/privacystatement/default.aspx).

## Povolení mobilní aplikace systému iOS nebo Android pro MAM s SDK

Pokud chcete povolit mobilní aplikaci s iOS, musíte provést tyto kroky:

1. **[Příručka pro vývojáře sady Intune App SDK pro iOS](intune-app-sdk-ios.md)**: Tento dokument vás detailně provede procesem povolování mobilních aplikací s iOS pomocí sady Intune App SDK. Tento dokument najdete ve složce dokumentace, kterou jste si stáhli jako součást balíčku Intune App SDK.
2. **Intune App SDK pro systém iOS**: Jakou součást balíčku Intune App SDK staženého z Microsoft Intune najdete složku označenou Intune App SDK for iOS. Tato složka obsahuje celou sadu Intune App SDK pro systém iOS.

Pokud chcete povolit mobilní aplikaci s Androidem, musíte provést tyto kroky:

1. **[Příručka pro vývojáře sady Intune App SDK pro Android](intune-app-sdk-android.md)**: Tento dokument vás detailně provede procesem povolování mobilních aplikací s Androidem pomocí sady Intune App SDK. Tento dokument najdete ve složce dokumentace, kterou jste si stáhli jako součást balíčku Intune App SDK.
2. **Intune App SDK pro systém Android**: Jakou součást balíčku Intune App SDK staženého z Microsoft Intune najdete složku označenou Intune App SDK for Android. Tato složka obsahuje celou sadu Intune App SDK pro systém Android.

## Vypnutí telemetrie pro aplikaci

**Intune App SDK pro iOS**: SDK ve výchozím nastavení protokoluje telemetrická data SDK o událostech využití. Tato data se odešlou do Microsoft Intune.

Pokud se rozhodnete neodesílat telemetrická data sady SDK z vaší aplikace do Microsoft Intune, **musíte zakázat** přenos telemetrie sady SDK v `MAMTelemetryDisabled` nastavením vlastnosti `IntuneMAMSettings`.

**Intune App SDK pro Android**: Telemetrické údaje SDK se neprotokolují pomocí SDK.

## Testování aplikace s povoleným MAM s Microsoft Intune

Po dokončení nezbytných kroků k vylepšení (integraci sady Intune App SDK) vaší sady Intune App SDK pro systém iOS nebo Android se musíte ujistit, že všechny zásady správy aplikací jsou povolené a fungují pro koncové uživatele a správce IT. K testování vylepšené aplikace budete potřebovat:

1. **Testování aplikace s povoleným MAM s Microsoft Intune**: Tento průvodce vás detailně provede postupem testování vylepšených aplikací pro iOS s podporou MAM nebo Android s Microsoft Intune. Tento dokument najdete ve složce dokumentace, kterou jste si stáhli jako součást balíčku Intune App SDK.
2. **Účet Microsoft Intune**: K testování aplikace s povoleným MAM pomocí Microsoft Intune budete potřebovat účet Microsoft Intune. Pokud jste nezávislý dodavatel softwaru a povolujete MAM pro aplikace z App Storu pro iOS nebo Android, obdržíte po dokončení registrace pomocí Microsoft Intune podle pokynů k registraci propagační kód. Tento propagační kód vám umožní zaregistrovat zkušební verzi Microsoft Intune na rok rozšířeného používání. Pokud vyvíjíte podnikovou aplikaci, která nebude odeslaná do Storu, předpokládá se, že máte přístup k Microsoft Intune prostřednictvím vaší organizace. Můžete si taky zaregistrovat k měsíční zkušební verzi zdarma s [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).




<!--HONumber=Jul16_HO3-->


