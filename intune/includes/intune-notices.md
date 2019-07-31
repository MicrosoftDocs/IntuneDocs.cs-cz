---
title: zahrnout soubor
description: zahrnout soubor
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 4423e731bc1538cd2454de32f0d50f2d08eedc69
ms.sourcegitcommit: 99b74d7849fbfc8f5cf99cba33e858eeb9f537aa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/31/2019
ms.locfileid: "68670928"
---
Tato oznámení obsahují důležité informace, které vám pomůžou připravit se na budoucí změny a funkce Intune. 


### <a name="decreasing-support-for-android-device-administrator"></a>Snížení podpory pro správce zařízení s Androidem 
Správce zařízení s Androidem (někdy označovaný jako "starší verze" správy Androidu a vydaný s Androidem 2,2) je způsob, jak spravovat zařízení s Androidem. Vylepšené funkce správy jsou teď ale k dispozici v [Androidu Enterprise]( https://docs.microsoft.com/intune/connect-intune-android-enterprise) (vydané s androidem 5,0). V úsilí o přechod na moderní, bohatou a bezpečnější správu zařízení bude Google v nových verzích Androidu snížit podporu Správce zařízení.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Vzhledem k těmto změnám od společnosti Google budou mít uživatelé Intune tyto možnosti: 
- Intune bude moct poskytovat podporu jenom pro zařízení s Androidem spravovaná pomocí Správce zařízení s Androidem 10 nebo novějším (označovanou taky jako Android Q) až do letního 2020. Toto datum se očekává, že se má vydávat další hlavní verze Androidu.  
- Zařízení spravovaná správcem zařízení se systémem Android 10 nebo novějším po léto 2020 již nebudou moci být zcela spravována.    
- Zařízení s Androidem spravovaná správcem zařízení, která zůstávají ve verzích Androidu pod Androidem 10, nebudou ovlivněná a můžou se dál spravovat pomocí Správce zařízení.  
- Pro všechna zařízení s Androidem 10 a novějším společnost Google omezila možnost pro agenty správy zařízení, jako je Portál společnosti k přístupu k informacím o identifikátoru zařízení. To má vliv na následující funkce Intune po aktualizaci zařízení na Android 10 nebo novější: 
    - Řízení přístupu k síti pro VPN už nebude fungovat.  
    - Identifikaci zařízení jako vlastněných společností pomocí IMEI nebo sériového čísla nebudou zařízení automaticky označovat jako ve vlastnictví firmy. 
    - IMEI a sériové číslo se už v Intune nebudou zobrazovat správcům IT. 
        > [!Note]
        > To má vliv jenom na zařízení spravovaná správcem zařízení s Androidem 10 a novějším, která neovlivňují zařízení spravovaná jako Android Enterprise. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Aby se zabránilo snížení funkčnosti, které přichází v létě 2020, doporučujeme následující:
- Nepřidávejte nová zařízení do správy Správce zařízení.
- Pokud se očekává, že zařízení obdrží aktualizaci pro Android 10, migruje ji ze správy správců zařízení na zásady pro Android Enterprise Management a/nebo ochranu aplikací.

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Aktualizace aplikace pro Android Portál společnosti na nejnovější verzi <!--4536963-->
Intune pravidelně uvolňuje aktualizace aplikace Portál společnosti pro Android. V listopadu 2018 jsme vydali aktualizaci portálu společnosti, která obsahovala back-end přepínač, který vám umožní připravit se na změny Google od stávající platformy oznámení až po Firebase Cloud Messaging (FCM) od společnosti Google. Když Google pustí svou stávající platformu pro oznámení a přesune se do FCM, budou muset koncoví uživatelé aktualizovat aplikaci Portál společnosti aspoň na 2018. listopadu, aby mohli pokračovat v komunikaci s obchodem Google Play.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Naše telemetrie znamená, že máte zařízení s Portál společnosti verzí starší než 5.0.4269.0. Pokud není nainstalovaná Tato verze nebo novější aplikace Portál společnosti, spustí se akce zařízení, jako je vymazání, resetování hesla, dostupná a požadovaná instalace aplikací, a zápis certifikátu nemusí fungovat podle očekávání. Pokud jsou vaše zařízení zaregistrovaná v MDM v Intune, můžete zobrazit verze a uživatele portálu společnosti v klientských aplikacích – zjištěné aplikace. Výběr dřívějších verzí Portál společnosti vám umožní zjistit, co mají koncoví uživatelé zařízení, která neaktualizovala firemní portál.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Zeptejte se koncových uživatelů zařízení s Androidem, která se neaktualizovala tak, aby aktualizovala portál společnosti prostřednictvím obchodu Google Play. Informujte pracovníky helpdesku o případ, že uživatel nedrží automatickou aktualizaci aplikace Portál společnosti. Podívejte se na odkaz v části Další informace, kde najdete další informace o FCM platformě Google a změně.

#### <a name="additional-information"></a>Další informace
https://firebase.google.com/docs/cloud-messaging/


### <a name="new-fullscreen-experience-coming-to-intune---4593669--"></a>Nové prostředí pro celou obrazovku přicházející do Intune <!--4593669-->
Zavádíme aktualizované prostředí pro vytváření a úpravu uživatelského rozhraní pro Intune v Azure Portal. Toto nové prostředí zjednoduší stávající pracovní postupy pomocí formátu stylu, který je v jednom okně zhuštěný. Tato aktualizace prochází s "oknem neustálému zvětšování" nebo libovolnými toky vytváření a úprav, které vyžadují přechod k podrobnostem hloubkové jízdy. Pracovní postupy vytváření se také aktualizují tak, aby zahrnovaly přiřazení (s výjimkou přiřazení aplikace).

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Prostředí na celé obrazovce se bude zavádět do Intune jak v portal.azure.com, tak v devicemanagement.microsoft.com během několika dalších měsíců. Tato aktualizace uživatelského rozhraní nebude mít vliv na funkčnost stávajících zásad a profilů, ale zobrazí se mírně upravený pracovní postup. Když vytvoříte nové zásady, budete moct nastavit některá přiřazení jako součást tohoto toku, a to tak, abyste je po vytvoření zásady nemuseli vytvářet. V příspěvku na blogu najdete další informace o snímcích obrazovky, které nové prostředí bude vypadat v konzole.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
Nemusíte provádět žádnou akci, ale v případě potřeby můžete zvážit aktualizaci pokynů pro IT specialisty. Naši dokumentaci aktualizujeme, protože toto prostředí se zavede na různá okna v Intune na Azure Portal.

#### <a name="additional-information"></a>Další informace 
https://aka.ms/intune_fullscreen

### <a name="plan-for-change-intune-moving-to-support-ios-11-and-higher-in-september----4665342--"></a>Plán změny: Intune se přesouvá na podporu iOS 11 a vyšší v září. <!-- 4665342-->
V září očekáváme, že iOS 13 vydává společnost Apple. Registrace do Intune, Portál společnosti a Managed Browser se po vydání verze iOS 13 přesune na podporu iOS 11 a novějších.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Za předpokladu, že jsou mobilní aplikace O365 podporované v iOS 11,0 a vyšších, to vás nemusí ovlivnit. je možné, že jste už provedli upgrade operačního systému nebo zařízení. Pokud ale máte některá z níže uvedených zařízení nebo se rozhodnete zaregistrovat některá z níže uvedených zařízení, zjistěte, že níže uvedená zařízení nepodporují operační systém větší než iOS 10. Tato zařízení bude potřeba upgradovat na zařízení, které podporuje iOS 11 nebo vyšší:

- iPhone 5
- iPhone 5c
- iPad (4. generace)

Od července se zařízení zaregistrovaná v MDM s iOS 10 a Portál společnosti zobrazí výzva k upgradu operačního systému nebo zařízení. Pokud používáte zásady ochrany aplikací (aplikace), můžete také nastavit přístup nastavení "vyžadovat minimální operační systém iOS" (pouze upozornění).

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Podívejte se do sestavy Intune, kde vidíte, která zařízení nebo uživatelé můžou být ovlivnění. Přejít na **zařízení** > **všechna zařízení** a filtrovat podle operačního systému. Můžete přidat další sloupce, které vám pomůžou určit, kdo ve vaší organizaci má zařízení se systémem iOS 10. Zajistěte, aby vaši koncoví uživatelé před září upgradovali svoje zařízení na podporovanou verzi operačního systému.

### <a name="plan-for-change-support-for-version-811-and-higher-of-intune-app-sdk-for-ios----3586942--"></a>Plán změny: Podpora verze 8.1.1 a vyšší sady Intune App SDK pro iOS <!-- 3586942-->
Od září 2019 se Intune přesune na podporu aplikací pro iOS pomocí sady Intune App SDK 8.1.1 a vyšší. Aplikace sestavené s verzemi sady SDK nižšími než 8.1.1 se už nebudou podporovat. Tato změna se projeví u verze iOS 13 od společnosti Apple, která se očekává od září a bude také oznámena v MC181399.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Pomocí sady Intune App SDK nebo integrace se zabalením aplikací můžete chránit podniková data před neschválenými aplikacemi a uživateli prostřednictvím šifrování dat. Intune App SDK pro iOS ve výchozím nastavení použije 256 šifrovacích klíčů, pokud je šifrování povolené Intune App Protection zásady (aplikace). Po této změně nebudou moct aplikace pro iOS ve verzích SDK starších než 8.1.1, které používají 128 šifrovacích klíčů, dál sdílet data s aplikacemi integrovanými se sadou SDK 8.1.1 nebo s použitím 256 klíčů. Aby bylo možné chráněné sdílení dat, bude pro všechny aplikace pro iOS potřeba mít sadu SDK verze 8.1.1 nebo vyšší.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
Kontrolovat aplikace Microsoftu, třetích stran a obchodních aplikací (LOB). Zajistěte, aby všechny vaše aplikace chráněné pomocí aplikace Intune používaly sadu SDK verze 8.1.1 nebo novější.

- Pro obchodní aplikace: Možná budete muset znovu publikovat aplikace integrované se sadou SDK verze 8.1.1 nebo novější. Doporučujeme nejnovější verzi sady SDK. Informace o tom, jak připravit obchodní aplikace pro zásady ochrany aplikací, najdete v tématu [Příprava obchodních aplikací na zásady ochrany aplikací](../apps-prepare-mobile-application-management.md).
- Pro aplikace Microsoftu a třetích stran: Ujistěte se, že nasazujete nejnovější verze těchto aplikací pro uživatele.

Měli byste také aktualizovat dokumentaci nebo pokyny pro vývojáře, pokud je to možné, a zahrnout tuto změnu do podpory pro sadu SDK.

#### <a name="additional-information"></a>Další informace
https://docs.microsoft.com/intune/apps-prepare-mobile-application-management

### <a name="plan-for-change-new-windows-updates-settings-in-intune----4464404---"></a>Plán změny: Nové nastavení aktualizací Windows v Intune <!-- 4464404 -->
Od verze Intune do Intune nebo 1908 přidáváme nové "nastavení termínu", které můžete nakonfigurovat místo nastavení "Umožněte uživateli, aby se restartoval". V uživatelském rozhraní v 1909 nebo září si plánujeme zakázat nastavení, které je potřeba restartovat, a pak je úplně odebrat z konzoly do konce října. 

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Pokud spravujete zařízení s Windows 10 ve vašem prostředí: 
- V případě aktualizace Intune nebo 1908 se v konzole zobrazí nové nastavení termínu, kromě starého nastavení, které je potřeba restartovat.
- Když jsou tato stará i nová nastavení nakonfigurovaná, hodnoty nastavení konečného termínu přepíšou hodnoty nastavení, které je potřeba restartovat.
- Nastavení konečného termínu v konzole nástroje v aktualizaci 1910 nahradí možnost "povolení uživatele k restartování (v tomto prostředí)".

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
Začněte používat nastavení konečného termínu v 1908, a to tak, že je nakonfigurujete s požadovanými hodnotami. Jakmile to budete mít, můžete nastavit nastavení provedeného restartování na Nenakonfigurováno pro přípravu na odebrání těchto nastavení z konzoly v říjnu.

V případě potřeby aktualizujte svou dokumentaci a skripty pro automatizaci. 

Než odebereme nastavení provedeného restartování, budeme vás udržovat do centra zpráv, abychom vám aktualizovali a vyúčtovali připomenutí.

### <a name="plan-for-change-intune-app-sdk-and-app-protection-policies-for-android-moving-to-support-android-50-and-higher-in-october---4911065---"></a>Plán změny: Sada Intune App SDK a zásady ochrany aplikací pro Android, které se přesunou na podporu Android 5,0 a novějších v říjnu <!--4911065 -->
Intune se v říjnu přesune na podporu Androidu 5. x (Lupa) a vyšší. Aktualizujte všechny zabalené aplikace pomocí nejnovější sady Intune App SDK a aktualizujte svá zařízení.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Pokud nepoužíváte nebo plánujete použít sadu SDK nebo aplikaci pro Android, tato změna vás nijak neovlivní. Pokud používáte sadu Intune App SDK, nezapomeňte aktualizovat na nejnovější verzi a také aktualizovat zařízení na Android 5. x a vyšší. Pokud aktualizace neaktualizujete, nebudou aplikace dostávat aktualizace a kvalita jejich prostředí se v průběhu času sníží. 

Níže najdete seznam běžných zařízení zaregistrovaných v Intune, na kterých běží Android verze 4. x. Pokud máte jedno z těchto zařízení, proveďte příslušné kroky, abyste se ujistili, že toto zařízení bude podporovat Android verze 5,0 nebo vyšší nebo že bude nahrazeno zařízením, které podporuje Android verze 5,0 nebo novější. Tento seznam není vyčerpávající pro všechna zařízení, která může být potřeba vyhodnotit:
- Samsung SM – T561  
- Samsung SM – T365 
- Samsung GT – I9195 
- Samsung SM – G800F
- Samsung SM – G357FZ
- Společnost Motorola XT1080
- Samsung GT – I9305
- Samsung SM – T231

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Zabalte své aplikace pomocí nejnovější sady Intune App SDK. Můžete také nastavit podmíněné nastavení "vyžadovat minimální verzi operačního systému (pouze upozornění)", které upozorní koncové uživatele na osobní zařízení k upgradu.
