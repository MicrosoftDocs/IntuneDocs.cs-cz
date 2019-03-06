---
title: Začínáme s Microsoft Intune App SDK
description: Umožní vám rychle povolit u vaší mobilní aplikace správu mobilních aplikací (MAM) pomocí Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/24/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5ae6e8aec0fb2aa3e563e28f3846eaddea06380c
ms.sourcegitcommit: fb2ca28ab0cf89202c935da3f9d98adcea20566d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57461460"
---
# <a name="get-started-with-the-microsoft-intune-app-sdk"></a>Začínáme s Microsoft Intune App SDK

Tento průvodce vám pomůže rychle povolit mobilní aplikaci pro podporu zásad ochrany aplikací pomocí Microsoft Intune. Může být vhodné se nejdříve seznámit s výhodami sady Intune App SDK, které jsou vysvětlené v [Přehledu sady Intune App SDK](app-sdk.md).

Intune App SDK podporuje podobné scénáře v systémech iOS a Android a je určená k vytvoření konzistentního prostředí pro správce IT pracující na různých platformách. Ale vzhledem k platformě rozdíly a omezení existují v podpoře některých funkcí malé rozdíly.

## <a name="register-your-store-app-with-microsoft"></a>Registrace aplikace ze Storu s Microsoftem

### <a name="if-your-app-is-internal-to-your-organization-and-will-not-be-publicly-available"></a>Pokud aplikaci používáte v organizaci interně a nebude veřejně dostupná:

Můžete _**není nutné**_ registrace vaší aplikace. Pro interní [-obchodní (LOB) aplikace](apps-add.md#app-types-in-microsoft-intune) , které byly vytvořeny podle nebo vaší společnosti, správce IT interně nasadí aplikaci. Intune rozpozná, že aplikace byla vytvořena pomocí sady SDK a umožní správci IT, aby u ní použil zásady ochrany aplikací. Můžete přeskočit k části [Povolení zásad ochrany aplikací v aplikaci pro iOS nebo Android](#enable-your-iOS-or-Android-app-for-app-protection-policy).

### <a name="if-your-app-will-be-released-to-a-public-app-store-like-the-apple-app-store-or-google-play"></a>Pokud bude vaše aplikace vydána ve veřejném obchodě s aplikacemi, například Apple App Storu nebo Google Play:

_**Musíte**_ aplikaci nejdřív zaregistrovat ve službě Microsoft Intune a odsouhlasit podmínky registrace. Správci IT lze následně použít zásady ochrany aplikací na aplikaci spravovanou, což bude potom uvedeno jako [partnerské aplikace s ochranou Intune](apps-supported-intune-apps.md#partner-apps).

Do té doby, než bude registrace dokončena a potvrzena týmem Microsoft Intune, nebudou mít správci Intune možnost použít zásady ochrany aplikací na přímý odkaz na vaši aplikaci. Microsoft vaši aplikací přidá také na [stránku partnerů Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps). Tady se zobrazí ikona aplikace označující, že aplikace podporuje zásady ochrany aplikací Intune.

### <a name="the-registration-process"></a>Proces registrace
Pokud chcete zahájit registraci, i když zatím s nikým z Microsoftu nespolupracujete, vyplňte [dotazník partnera s aplikací pro Microsoft Intune](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR80SNPjnVA1KsGiZ89UxSdVUMEpZNUFEUzdENENOVEdRMjM5UEpWWjJFVi4u).

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

Pokud je vaše aplikace vytvořená v Xamarinu, použijte tuto variantu sady SDK:

* [Xamarinové vazby sady Intune App SDK](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)

Doporučujeme, abyste si zaregistrovali na GitHubu účet, který je možné použít k operacím fork a pull v našich úložištích. GitHub vývojářům umožňuje komunikovat s naším produktovým týmem, hlásit problémy a dostávat rychlé odpovědi, zobrazit poznámky k verzi a posílat připomínky do Microsoftu. S dotazy ke GitHubu pro Intune App SDK se obraťte na msintuneappsdk@microsoft.com.

## <a name="enable-your-ios-or-android-app-for-app-protection-policy"></a>Povolení zásad ochrany aplikací v aplikaci pro iOS nebo Android

Budete potřebovat jednu z následujících příruček pro vývojáře, která vám pomůže integrovat Intune App SDK do vaší aplikace:

* **[Intune App SDK pro iOS – Příručka vývojáře](app-sdk-ios.md)**: Tento dokument se vás detailně provede procesem povolování vaší nativní aplikace pro iOS pomocí sady Intune App SDK.

* **[Intune App SDK pro Android Developer Příručka](app-sdk-android.md)**: Tento dokument se vás detailně provede procesem povolování vaší nativní aplikace pro Android s Intune App SDK.

* **[Xamarinové vazby sady Intune App SDK průvodce](app-sdk-xamarin.md)**: Tento dokument vám pomůže vytvářet zařízení s iOS a aplikace pro Android pomocí Xamarinu zásady ochrany aplikací Intune.



## <a name="enable-your-ios-or-android-app-for-app-based-conditional-access"></a>Povolení podmíněného přístupu na základě aplikace v aplikaci pro iOS nebo Android
 
 Aby aplikace správně fungovala s podmíněným přístupem na základě aplikace Azure Active Directory (AAD), musí být kromě povolení zásad ochrany aplikací v aplikaci splněny tyto podmínky:
 
 * Aplikace je vytvořená pomocí [Azure Active Directory Authentication Library](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) a má povolené ověřování zprostředkovatele AAD.
 
 * [ID klienta AAD](https://docs.microsoft.com/azure/app-service/app-service-mobile-how-to-configure-active-directory-authentication#configure-a-native-client-application) pro vaši aplikaci musí být v rámci platforem Android a iOS jedinečné.
 
## <a name="configure-telemetry-for-your-app"></a>Konfigurace telemetrie pro vaši aplikaci

Microsoft Intune shromažďuje data statistik využití vaši aplikace.

* **Intune App SDK pro iOS**: Sada SDK ve výchozím nastavení protokoluje telemetrická data SDK o událostech využití. Tato data se odešlou do Microsoft Intune.

    * Pokud se rozhodnete neodesílat telemetrická data sady SDK z aplikace do Microsoft Intune, musíte ve slovníku IntuneMAMSettings zakázat přenos telemetrie nastavením vlastnosti `MAMTelemetryDisabled` na hodnotu YES.

* **Intune App SDK pro Android**: Sada Intune App SDK pro Android neřídí shromažďování dat z vaší aplikace. Aplikace Portál společnosti ve výchozím nastavení protokoluje telemetrická data. Tato data se odešlou do Microsoft Intune. V souladu se zásadami Microsoftu neshromažďujeme žádné identifikovatelné osobní údaje. 

    * Pokud se koncoví uživatelé rozhodnou tato data neodesílat, musí v nastavení aplikace Portál společnosti vypnout telemetrii. Další informace najdete v článku [Vypnutí shromažďování dat Microsoftu o využití](https://docs.microsoft.com/intune-user-help/turn-off-microsoft-usage-data-collection-android). 

## <a name="line-of-business-app-version-numbers"></a>Čísla verzí obchodních aplikací

Obchodní aplikace v Intune teď zobrazují číslo verze aplikací pro iOS a Android. Číslo se zobrazuje na portálu Azure Portal v seznamu aplikací a v okně přehledu aplikace. Koncoví uživatelé uvidí číslo aplikace v aplikaci Portál společnosti a na webovém portálu.

### <a name="full-version-number"></a>Celé číslo verze

Celé číslo verze identifikuje konkrétní vydanou verzi aplikace. Číslo se zobrazí jako _Verze_(_build_). Například 2.2(2.2.17560800). 

Celé číslo verze tvoří dvě části:

 - **Verze**  
   Číslo verze je čitelné číslo vydané verze aplikace. Koncovým uživatelům slouží k identifikaci různých vydaných verzí aplikace.

 - **Číslo buildu**  
    Číslo buildu je interní číslo, které může sloužit k rozpoznání aplikace a její programové správě. Číslo buildu se vztahuje k iteraci aplikace, která odkazuje na změny v kódu.

### <a name="version-and-build-number-in-android-and-ios"></a>Číslo verze a buildu v Androidu a iOSu

Android i iOS používají pro aplikace jak čísla verzí, tak buildů. V obou operačních systémech mají ale svůj konkrétní význam. Následující tabulka vysvětluje, jak spolu tyto termíny souvisí.

Když vyvíjíte obchodní aplikaci pro použití v Intune, nezapomeňte použít jak číslo verze, tak i číslo buildu. Funkce správy aplikací Intune vyžadují smysluplné číslo **CFBundleVersion** (iOS) a **PackageVersionCode** (Android). Tato čísla jsou součástí manifestu aplikace. 

Intune|iOS|Android|Popis|
|---|---|---|---|
Číslo verze|CFBundleShortVersionString|PackageVersionName |Toto číslo označuje konkrétní vydanou verzi aplikace pro koncové uživatele.|
Číslo sestavení|CFBundleVersion|PackageVersionCode |Toto číslo slouží k označení iterace v kódu aplikace.|

#### <a name="ios"></a>iOS

- **CFBundleShortVersionString**  
    Určuje číslo vydané verze sady. Toto číslo označuje vydanou verzi aplikace. Používají ho koncoví uživatelé, když odkazují na aplikaci.
- **CFBundleVersion**  
    Verze buildu sady, která označuje iteraci sady. Číslo může označovat vydanou verzi nebo nevydanou sadu. Slouží ke zjištění aplikace.

#### <a name="android"></a>Android

 - **PackageVersionName**  
    Číslo verze, které se zobrazuje uživatelům. Tento atribut je možné nastavit jako nezpracovaný řetězec nebo jako odkaz na prostředek řetězce. Řetězec nemá žádný jiný účel než ten, že se zobrazuje uživatelům.
 - **PackageVersionCode**  
    Interní číslo verze. Toto číslo slouží jenom k určení aktuálnosti verze, přičemž vyšší čísla označují novější verze. Nejedná se o verzi. 

## <a name="next-steps-after-integration"></a>Další postup po integraci

### <a name="test-your-app"></a>Testování aplikace
Po dokončení nezbytných kroků k integraci vaší aplikace pro iOS nebo Android se sadou Intune App SDK se musíte ujistit, že mají uživatelé a správci IT povolené a funkční všechny zásady ochrany aplikací. K testování integrované aplikace budete potřebovat následující:

* **Testovací účet Microsoft Intune**: K testování vašich aplikací spravovaných v Intune s funkcemi ochrany aplikací Intune, budete potřebovat účet Microsoft Intune.

    * Pokud jste nezávislý dodavatel softwaru a povolujete zásady ochrany aplikací v Intune pro aplikace ze Storu pro iOS nebo Android, dostanete po dokončení registrace v Microsoft Intune propagační kód (jak je uvedeno během registrace). Tento propagační kód vám umožní zaregistrovat si Microsoft Intune po zkušební verzi na další rok používání.

    * Pokud vyvíjíte podnikovou aplikaci, kterou nebudete odesílat do Storu, předpokládá se, že máte přístup k Microsoft Intune prostřednictvím své organizace. Můžete si také v [Microsoft Intune](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) zaregistrovat zkušební verzi na měsíc zdarma.
    
    * Pokud testujete aplikaci na mobilním zařízení pomocí účtu koncového uživatele, ujistěte se, že jste udělili tento účet licenci Intune na webu Microsoft 365 admin center po přihlášení pomocí účtu správce, naleznete v tématu [licence přiřadit Microsoft Intune ](https://docs.microsoft.com/en-ca/intune/licenses-assign).

* **Zásady ochrany aplikací Intune**: Chcete-li otestovat aplikaci se všechny zásady Intune app protection, byste měli vědět, jaké chování je očekávané pro každé nastavení zásad. Více najdete v popisech [zásad ochrany aplikací pro iOS](app-protection-policy-settings-ios.md) a [zásad ochrany aplikací pro Android](app-protection-policy-settings-android.md).

* **Řešení potíží s**: Pokud narazíte na nějaké problémy při ručním testování vaší aplikace instalace uživatelské prostředí, přečtěte si téma [řešit problémy při instalaci aplikace](troubleshoot-app-install.md). 

### <a name="give-your-app-access-to-the-intune-app-protection-service-optional"></a>Vaši aplikaci dáte přístup ke službě Intune app protection (nepovinné)

Pokud vaše aplikace používá k ověřování vlastní vlastní nastavení Azure Active Directory (AAD), by měl následující kroky prováděné na jak veřejnými aplikacemi z obchodu, tak i interních obchodních aplikacích. Kroky **není nutné mají být provedeny, pokud vaše aplikace používá ID klienta výchozí sadu Intune SDK**. 

Jakmile jste zaregistrovali aplikaci v rámci tenanta služby Azure a se objeví pod **všechny aplikace**, musíte poskytnout přístup k vaší aplikaci ke službě Intune app protection (dříve označovanou jako služba MAM). Na webu Azure Portal:

1.  Přejděte do okna **Azure Active Directory**.
2.  Vyberte pro danou aplikaci možnost **Registrace aplikace**.
3.  V části **Nastavení** pod záhlavím **Přístup přes rozhraní API** vyberte **Požadovaná oprávnění**. 
4.  Klikněte na **+ Přidat**.
5.  Klikněte na **Vyberte rozhraní API**. 
6.  Do vyhledávacího pole zadejte **Microsoft Mobile Application Management** (Správa mobilních aplikací Microsoftu).
7.  V seznamu rozhraní API vyberte **Microsoft Mobile Application Management** (Správa mobilních aplikací Microsoftu) a kliknutím proveďte výběr.
8.  Vyberte **Read and Write the User’s App Management Data** (Čtení a zápis dat správy uživatelských aplikací).
9.  Klikněte na **Done** (Hotovo).
10. Klikněte na **Udělit oprávnění** a potom na **Ano**. 

### <a name="badge-your-app-optional"></a>Označte si aplikaci (volitelné)

Po ověření, že zásady ochrany aplikací Intune ve vaší aplikaci fungují, můžete označit ikonu aplikace logem ochrany aplikací Intune.

Tento znak říká správcům IT, koncovým uživatelům a potenciálním zákazníkům Intune, že vaše aplikace funguje se zásadami ochrany aplikací Intune. Podporuje to využívání a přijetí vaší aplikace u zákazníků Intune.

Jde o ikonu aktovky a můžete si ji prohlédnout níže:

![Zásady ochrany aplikací Intune – příklad znaku 1](./media/badge-example-1.png) ![Zásady ochrany aplikací Intune – příklad znaku 2](./media/badge-example-2.png)

**Co budete potřebovat k označení aplikace**:

* Aplikaci pro zpracování obrázků, která umí přečíst soubory **.eps**, nebo aplikaci Adobe, která umí přečíst soubory **.ai**.

* Na Githubu pro Microsoft Intune najdete [prostředky a pokyny pro označení aplikace pro Intune](https://github.com/msintuneappsdk/intune-app-partner-badge).
