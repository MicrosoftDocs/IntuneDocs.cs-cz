---
title: Profily zásad a pracovní ochrany aplikací v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Při rozhodování o použití zásad ochrany aplikací nebo pracovní profily pro osobní nebo BYOD podnikových zařízení s Androidem v Microsoft Intune, najdete v článku rozdíly a výhody a nevýhody. Porovnat rozdíly a funkce získáte pomocí zásad ochrany aplikací bez registrace (APP-jsme) a pracovní profily Androidu Enterprise.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/13/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 307e3ce1b1973897a08159bdcf91e0117d58bfe8
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57392664"
---
# <a name="application-protection-policies-and-work-profiles-on-android-enterprise-devices-in-intune"></a>Profily zásad a pracovní ochrany aplikací na zařízeních s Androidem Enterprise v Intune

V mnoha organizacích jsou postiženy omezeními správcům chránit prostředky a data na různých zařízeních. Problémy může vyvolávat chrání prostředky pro uživatele s osobní podnikových zařízení s Androidem, označované také jako bring-your-own-device (BYOD). Microsoft Intune podporuje dva scénáře nasazení Androidu pro používání your-own-device (BYOD):

- Zásady ochrany aplikací bez registrace (APP-jsme)
- Pracovní profily androidu Enterprise

Aplikace – jsme a scénáře s pracovním profilu nasazení zahrnovat následující klíčové funkce důležité pro model BYOD prostředí:

1. **Ochrana a oddělení data organizace spravovaná**: Obě řešení chránit data organizace tím, že vynucuje ovládací prvky ochrany před únikem informací (DLP) ke ztrátě dat v organizaci spravovaná data. Tyto ochrany zabránit náhodnému úniku informací z chráněných dat, jako je koncový uživatel náhodnému sdílení osobní aplikace nebo účtu. Slouží také k zajištění, že je v pořádku a není ohrožené zařízení přistupuje k datům.

2. **Ochrana osobních údajů koncového uživatele**: Aplikace – jsme pracovní profily Androidu Enterprise oddělení obsahu koncovým uživatelům na zařízení a data spravovaná službou Správa mobilních zařízení (MDM) správce. V obou případech správce IT vynutit zásady, jako je například ověřování pouze na úrovni kódu PIN v organizaci spravovaná aplikace nebo identity. Správci IT nebudou moct číst, přístup k nebo vymazat data, která má vlastní nebo řídit koncovými uživateli.

Určuje, zda zvolíte aplikace-jsme nebo pracovní profily Androidu Enterprise pro vaše nasazení modelu BYOD závisí na vašich požadavcích a obchodní potřeby. Cílem tohoto článku je poskytnout pokyny, které vám pomohou rozhodnout.

## <a name="about-intune-app-protection-policies"></a>O zásadách ochrany aplikací Intune

Zásady ochrany aplikací Intune (aplikace) jsou zásady ochrany dat zacílený na uživatele. Použít zásady ochrany před ztrátou dat na úrovni aplikace. Aplikace Intune vyžaduje, že vývojáři aplikací povolit funkce aplikací pro aplikace, který vytvoří.

Jednotlivé aplikace pro Android jsou povolené pro aplikaci několika způsoby:

1. **Nativně integrováno do aplikace Microsoft první strany**: Aplikace Microsoft Office pro Android a různé další aplikace od Microsoftu, jsou dostupné integrované aplikace v Intune. Tyto aplikace Office, jako je Word, OneDrive, Outlook a tak dále, není třeba žádné další přizpůsobení k uplatnění zásad. Tyto aplikace můžete instalovat koncoví uživatelé přímo z Google Play Store.

2. **Integrovaná aplikace sestavení podle vývojáře, kteří používají sadu Intune SDK**: Vývojáři aplikací můžete integrovat sadu Intune SDK jejich zdrojový kód a znovu zkompilovat svoje aplikace k podpoře funkce zásady aplikací Intune.

3. **Zabalený pomocí nástroje Intune app wrapping**: Někteří zákazníci kompilovat aplikace pro Android (. Soubor APK) bez přístupu ke zdrojovému kódu. Bez zdrojového kódu vývojář nelze integrovat sadu Intune SDK. Bez sady SDK nelze umožňují své aplikace pro zásady aplikací. Vývojář musí změnit nebo recode aplikaci podporují zásady aplikací.

    Abychom pomohli, Intune zahrnuje **nástroj App wrapping Tool** nástroje pro existující aplikace pro Android (soubory Apk) a vytvoří aplikaci, která rozpozná zásady aplikací.

    Další informace o tomto nástroji najdete v tématu [repare – obchodní aplikace pro zásady ochrany aplikací](apps-prepare-mobile-application-management.md).

Pokud chcete zobrazit seznam aplikací, které jsou povolené s aplikací, najdete v článku [spravované aplikace s bohatou sadou zásad ochrany mobilních aplikací](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

## <a name="deployment-scenarios"></a>Scénáře nasazení

Tato část popisuje důležité charakteristiky aplikace-jsme a Android Enterprise pracovní profil scénáře nasazení.

#### <a name="app-we"></a>APP-WE

Aplikace – nasazení jsme (zásady ochrany aplikací bez registrace) definuje zásady pro aplikace, nikoli zařízením. V tomto scénáři zařízení obvykle nejsou zaregistrovaná nebo spravovaná podle autority MDM, jako je například Intune. Ochrana aplikací a přístup k datům organizace, správci používat aplikaci spravovat aplikace a pro tyto aplikace použít zásady ochrany dat.

Tato funkce platí pro:

- Android 4.4 a novější

> [!TIP]
> Další informace najdete v tématu [co jsou zásady ochrany aplikací?](app-protection-policy.md).

Aplikace – jsme scénáře jsou pro koncové uživatele, kteří mají malé náklady organizace na svých zařízeních a nechcete, aby se zapsat do správy mobilních zařízení. Jako správce stále potřebují chránit vaše data. Tato zařízení nespravuje. Proto běžné úlohy MDM a funkce, jako je například Wi-Fi zařízení VPN a správa certifikátů, nejsou součástí tohoto scénáře nasazení.

#### <a name="android-enterprise-work-profiles"></a>Pracovní profily androidu Enterprise

Pracovní profily jsou základní scénář nasazení Androidu Enterprise a případy použití pouze scénář zaměřený na modelu BYOD. Pracovní profil je samostatný oddíl vytváří na úrovni operačního systému Android, která je možné spravovat pomocí Intune.

Tato funkce platí pro:

- Zařízení s androidem 5.0 a novější s Google Mobile Services

Pracovní profil obsahuje následující funkce:

- **Tradiční funkce MDM**: Možnosti správy mobilních zařízení klíče, jako je například Správa životního cyklu aplikací pomocí spravovaného obchodu Google Play, je k dispozici ve všech scénářích Androidu Enterprise. Spravovaný obchod Google Play poskytuje robustní možnosti instalovat a aktualizovat aplikace bez jakéhokoli zásahu uživatele. IT konfigurační nastavení aplikace můžete také odeslat do aplikace organizace. Nevyžaduje ani koncovým uživatelům povolit instalace z neznámých zdrojů. Další běžné činnosti MDM, jako je například nasazení certifikátů, konfiguraci připojení Wi-Fi/VPN a nastavení hesel zařízení jsou k dispozici s pracovními profily.

- **Ochrana před únikem informací na hranice pracovního profilu**: Jako jsou APP-WE, IT můžete vynutit zásady ochrany dat. S pracovním profilem zásady ochrany před únikem informací se vynucují na úrovni pracovní profil, ne na úrovni aplikace. Například kopírování a vkládání ochrana je vynucená v nastavení aplikace použít pro aplikaci nebo vynucuje pracovního profilu. Při nasazení aplikace do pracovního profilu, můžete správci pozastavit ochrany, kopírování a vkládání do pracovního profilu vypnutím tyto zásady na úrovni aplikace.

## <a name="tips-to-optimize-the-work-profile-experience"></a>Tipy pro optimalizaci pracovního profilu prostředí

### <a name="when-to-use-app-within-work-profiles"></a>Při používání aplikace v rámci pracovních profilů

Aplikace v Intune a pracovní profily jsou doplňkové technologie, které lze použít společně nebo samostatně. Obě řešení architektonicky, vynucování zásad v různých vrstvách – aplikace ve vrstvě jednotlivých aplikací a pracovního profilu na vrstvě profilu. Nasazení aplikací spravovaných pomocí zásad aplikace do aplikace v pracovním profilu je platný a podporované scénáře. Používání aplikace, pracovních profilů nebo ke kombinaci závisí na vašich požadavcích ochrany před únikem informací.

Pracovní profily a aplikace, nastavení vzájemně doplňují tím, že poskytuje další pokrytí, pokud se jeden profil nesplňuje požadavky na ochranu dat vaší organizace. Například pracovní profily nativně neposkytují ovládacích prvků pro aplikaci zabránit ukládání do umístění nedůvěryhodné cloudové úložiště. Aplikace obsahuje tuto funkci. Můžete rozhodnout, že ochrany před únikem informací, které jsou k dispozici pouze v pracovním profilu je dostačující a zvolit nepoužívání aplikací. Nebo můžou vyžadovat ochrany z kombinace dvou.

### <a name="suppress-app-policy-for-work-profiles"></a>Potlačit zásady aplikace pro pracovní profily

Budete muset podporují jednotlivé uživatele, kteří mají několik zařízení – nespravovaná zařízení v aplikaci pro – jsme scénář a spravovaných zařízeních s pracovními profily. 

Například vyžadovat zadání kódu PIN při otevírání pracovní aplikace koncovým uživatelům. V závislosti na zařízení jsou zpracovány funkce PIN kód aplikace nebo pracovního profilu. Aplikace pro – jsme zařízení, PIN kód pro spuštění chování je vynucena aplikací. Pro pracovní profil zařízení můžete použít zařízení nebo pracovní profil PIN vynucuje operačním systémem. Chcete-li provést tento scénář, konfigurace nastavení aplikace tak, že nemůžete použít *při* aplikace je nasazená do pracovního profilu. Pokud nenakonfigurujete se tímto způsobem, koncový uživatel získá výzva k zadání kódu PIN v zařízení a znovu ve vrstvě aplikací.

### <a name="control-multi-identity-behavior-in-work-profiles"></a>Řízení chování funkce více identit v pracovních profilech

Aplikace Office, jako je Outlook a OneDrive, mají "více identit" chování. V rámci jedné instance aplikace koncový uživatel můžete přidat připojení k několika účtům odlišné nebo cloudových umístění úložiště. V rámci aplikace může být data načtená z těchto míst samostatné nebo sloučení. A uživatele můžete přepínat kontext mezi osobní identity (user@outlook.com) a identity organizace (user@contoso.com).

Při používání pracovních profilů, můžete chtít zakázat toto chování více identit. Když ho zakážete, je označené jako instancí aplikace v pracovním profilu nakonfigurovat pouze s identitou organizace. Pomocí nastavení konfigurace aplikace, které povolené účty pro podporu aplikací pro Office Android.

Další informace najdete v tématu [nasadit Outlook pro iOS a nastavení konfigurace aplikace pro Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

## <a name="when-to-use-intune-app"></a>Kdy použít pro aplikace Intune

Existuje několik scénářů enterprise mobility, kdy použití aplikací Intune je nejvhodnější.

#### <a name="older-devices-running-android-44-51-are-being-used"></a>Používají se starší zařízení se systémem Android 4.4 5.1

Oficiálně, jakékoli zařízení s Androidem 5.0 nebo novější s Google Mobile Services podporuje pracovních profilů a smí být spravovány tímto způsobem. Ale některé s Androidem 5.0 a 5.1 zařízení z některých výrobci OEM nepodporují pracovních profilů.

Pokud používáte verze, které nepodporují pracovní profily, a k zajištění ochrany před únikem informací pro organizaci dat na zařízeních, je nutné použít funkce aplikace Intune.

#### <a name="no-mdm-no-enrollment-google-services-are-unavailable"></a>Bez správy MDM, bez registrace, Google services nejsou k dispozici

Zákazníci, kteří nemají žádný způsob správy zařízení, včetně správy pracovních profilů, různých důvodů:

- Právní informace a odpovědnost důvodů
- Konzistence činnost koncového uživatele
- Je vysoce heterogenní prostředí zařízení s Androidem
- Není k dispozici žádné připojení ke službám Google, který je potřebný pro pracovní profil správy.

Například zákazníků nebo uživatelů v Číně nelze použít správy zařízení s Androidem, protože jsou blokované aplikace služby Google. V takovém případě použijte aplikace Intune pro ochranu před únikem informací.

## <a name="summary"></a>Souhrn

Pomocí Intune, obě aplikace-jsme a pracovní profily Androidu Enterprise jsou k dispozici pro aplikace Android BYOD. Zvolit aplikaci-jsme nebo pracovních profilů závisí na požadavcích vaší firmy a využití. Stručně řečeno použijte pracovních profilů, pokud potřebujete MDM aktivity na spravovaných zařízeních, jako je například nasazení certifikátu, nabídky aplikace a tak dále. Použití aplikace-jsme Pokud nechcete, aby se nebo není možné spravovat zařízení a používají pouze pro aplikace Intune povolené aplikace.

## <a name="next-steps"></a>Další postup
[Začněte používat zásady ochrany aplikací](app-protection-policy.md), nebo [zaregistrovat svoje zařízení](android-enroll.md).
