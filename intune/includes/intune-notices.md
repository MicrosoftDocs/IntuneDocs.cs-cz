---
title: zahrnout soubor
description: zahrnout soubor
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: d907c5256469e86410c9916d117d3e322d43cfc3
ms.sourcegitcommit: 2614d1b08b8a78cd792aebd2ca9848f391df8550
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67812538"
---
Tato oznámení obsahují důležité informace, které vám pomůžou připravit se na budoucí změny a funkce Intune. 

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
Od září 2019 se Intune přesune na podporu aplikací pro iOS pomocí sady Intune App SDK 8.1.1 a vyšší. Aplikace sestavené s verzemi sady SDK nižšími než 8.1.1 se už nebudou podporovat. Tato změna se projeví u vydání iOS 13 od společnosti Apple, které se očekává od září a také bylo oznámeno v MC181399.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Pomocí sady Intune App SDK nebo integrace se zabalením aplikací můžete chránit podniková data před neschválenými aplikacemi a uživateli prostřednictvím šifrování dat. Intune App SDK pro iOS ve výchozím nastavení použije 256 šifrovacích klíčů, pokud je šifrování povolené Intune App Protection zásady (aplikace). Po této změně nebudou moct aplikace pro iOS ve verzích SDK starších než 8.1.1, které používají 128 šifrovacích klíčů, dál sdílet data s aplikacemi integrovanými se sadou SDK 8.1.1 nebo s použitím 256 klíčů. Aby bylo možné chráněné sdílení dat, bude pro všechny aplikace pro iOS potřeba mít sadu SDK verze 8.1.1 nebo vyšší.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
Kontrolovat aplikace Microsoftu, třetích stran a obchodních aplikací (LOB). Měli byste zajistit, aby všechny vaše aplikace chráněné pomocí aplikace Intune používaly sadu SDK verze 8.1.1 nebo novější.

- Pro obchodní aplikace: Možná budete muset znovu publikovat aplikace integrované se sadou SDK verze 8.1.1 nebo novější. Doporučujeme nejnovější verzi sady SDK. Informace o tom, jak připravit obchodní aplikace pro zásady ochrany aplikací, najdete v tématu [Příprava obchodních aplikací na zásady ochrany aplikací](../apps-prepare-mobile-application-management.md).
- Pro aplikace Microsoftu a třetích stran: Ujistěte se, že nasazujete nejnovější verze těchto aplikací pro uživatele.

Měli byste také aktualizovat dokumentaci nebo pokyny pro vývojáře, pokud je to možné, a zahrnout tuto změnu do podpory pro sadu SDK.

#### <a name="additional-information"></a>Další informace
https://docs.microsoft.com/intune/apps-prepare-mobile-application-management

### <a name="plan-for-change-new-windows-updates-settings-in-intune----4464404---"></a>Plán změny: Nové nastavení aktualizací Windows v Intune <!-- 4464404 -->
Od verze Intune do služby Intune nebo 1908 přidáváme nová "nastavení termínů", která můžete nakonfigurovat, místo nastavení "Allow User to restart (v případě restartování)"). V uživatelském rozhraní v 1909 nebo září si plánujeme zakázat nastavení, které je potřeba restartovat, a pak je úplně odebrat z konzoly do konce října. 

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Pokud spravujete zařízení s Windows 10 ve vašem prostředí: 
- V případě aktualizace Intune nebo 1908 se v konzole zobrazí nové nastavení termínu, kromě starého nastavení, které je potřeba restartovat.
- Když jsou tato stará i nová nastavení nakonfigurovaná, hodnoty nastavení konečného termínu přepíšou hodnoty nastavení, které je potřeba restartovat.
- Nastavení konečného termínu v konzole nástroje v aktualizaci 1910 nahradí možnost "povolení uživatele k restartování (v tomto prostředí)".

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
Začněte používat nastavení konečného termínu v 1908, a to tak, že je nakonfigurujete s požadovanými hodnotami. Až to budete mít, můžete nastavit nastavení provedeného restartování na Nenakonfigurováno pro přípravu na odebrání z konzoly v říjnu.

V případě potřeby aktualizujte svou dokumentaci a skripty pro automatizaci. 

Než odebereme nastavení provedeného restartování, budeme vás udržovat do centra zpráv, abychom vám aktualizovali a vyúčtovali připomenutí.
