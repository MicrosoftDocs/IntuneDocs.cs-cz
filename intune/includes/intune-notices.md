---
title: zahrnout soubor
description: zahrnout soubor
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: fab8f2be48a30f6ad058b3eeb6874a44ff04e6ac
ms.sourcegitcommit: 7ceae61e036ccf8b33704751b0b39fee81944072
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66744325"
---
Tato oznámení poskytují důležité informace, které vám pomohou připravit se na budoucí změny Intune a funkce. 

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Aktualizovat na nejnovější verzi aplikace portál společnosti pro Android <!--4536963-->
Intune pravidelně vydává aktualizace s Androidem aplikaci portál společnosti. V listopadu 2018 jsme vydali aktualizací aplikace portál společnosti, který součástí back-end přepínač přípravy na Googlu změnu z jejich stávajících oznámení platformy na Google Firebase Cloud Messaging (FCM). Když Google co vyřadí stávající oznámení platformy a přesune se do FCM, koncoví uživatelé budou muset aktualizovali svoje aplikace firemního portálu do alespoň z listopadu 2018 vydání pro pokračovat v komunikaci s obchodu Google play.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Naše telemetrie označuje, že máte zařízení s verzí starší než 5.0.4269.0 portál společnosti. Pokud tato verze nebo novější z aplikace portál společnosti není nainstalovaná, IT pro zařízení iniciované akce, jako je vymazání, resetovat heslo, dostupné a požadované aplikace se nainstaluje a zápis certifikátu nemusí fungovat podle očekávání. Pokud jsou vaše zařízení zaregistrovaná v Intune MDM, pak se zobrazí verze portálu společnosti a uživatele tak, že přejdete do klientské aplikace – zjištěné aplikace. Výběr starší verze aplikace portál společnosti vám umožní zobrazit, které koncoví uživatelé měli zařízení, která neprovedli aktualizaci portálu společnosti.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Zeptejte se, že koncoví uživatelé zařízení s Androidem, které neprovedli aktualizaci na aktualizovat portál společnosti přes Google play. Informujte pracovníky helpdesku, v případě, že uživatel není uchovávat automatické aktualizace aplikace portál společnosti. Podívejte se na odkaz Další informace pro platformu FCM další na Googlu a změnit.

#### <a name="additional-information"></a>Další informace
https://firebase.google.com/docs/cloud-messaging/


### <a name="new-fullscreen-experience-coming-to-intune---4593669--"></a>Nové prostředí na celou obrazovku – Intune <!--4593669-->
Zavádíme aktualizované vytvářet a upravovat uživatelská rozhraní do Intune na portálu Azure portal. Toto nové prostředí zjednoduší stávajících pracovních postupů s použitím formátu styl Průvodce zhušťovat v rámci o jedno okno. Tato aktualizace bude okamžitě provést pomocí "okno zvětšování" nebo libovolný vytvořit a upravit toky, které vyžadují, abyste k podrobnostem jízdy hloubkové okno. Vytvořit pracovní postupy také zaktualizuje a zahrnují přiřazení (s výjimkou přiřazení aplikace).

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Možnosti zobrazení na celé obrazovce se začne distribuovat do služby Intune i na adrese portal.azure.com a devicemanagement.microsoft.com průběhu několika následujících měsíců. Tato aktualizace v uživatelském rozhraní to neovlivní funkčnost vaší stávající zásady a profily, ale zobrazí se mírně upravenou pracovní postup. Když vytvoříte nové zásady, třeba bude možné nastavit některá přiřazení jako součást tohoto toku místo tím po vytvoření zásady. Najdete v blogovém příspěvku na další informace pro snímky obrazovky vypadat nové prostředí v konzole.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
Není potřeba provádět žádnou akci, ale můžete zvážit možnost se v případě potřeby aktualizují vaše pokyny pro IT. Naši dokumentaci aktualizujeme, jak toto prostředí vidíme na různé listy v Intune na portálu Azure portal.

#### <a name="additional-information"></a>Další informace 
https://aka.ms/intune_fullscreen

### <a name="plan-for-change-intune-moving-to-support-ios-11-and-higher-in-september----4665342--"></a>Plánovaná změna: Intune přesunutí pro podporu iOS 11 a vyšší v září <!-- 4665342-->
V září Očekáváme, že 13 vydané společností Apple iOS. Registrace v Intune, portálu společnosti a v aplikaci Managed Browser se přesune na podporu iOS 11 a vyšší krátce po vydání iOS 13.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Za předpokladu, že mobilní aplikace O365 se podporují v Iosu 11.0 nebo novější, to nemusí mít vliv na vás. jste pravděpodobně již upgradovali operační systém nebo zařízení. Pokud mají některý z níže uvedených zařízení nebo rozhodnout registrovat zařízení uvedená níže, vědět však, že níže uvedená zařízení nepodporují operačního systému větší než iOS 10. Tato zařízení bude potřeba upgradovat na zařízení, která podporuje iOS 11 nebo vyšší:

- iPhone 5
- iPhone 5c
- iPad (4. generace)

Od července se MDM zaregistrovaná zařízení s iOS 10 a aplikace portál společnosti se zobrazí výzva k upgradu svých operační systém nebo zařízení. Pokud používáte zásady ochrany aplikací (aplikace) můžete také nastavit nastavení přístupu "Vyžadují minimální verze operačního systému (jenom upozornění)".

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Zkontrolujte Intune generování sestav zobrazit, jaké zařízení nebo uživatele, může být ovlivněn. Přejděte na **zařízení** > **všechna zařízení** a filtrovat podle operačního systému. Přidáte v dodatečné sloupce vám pomůže identifikovat, kdo ve vaší organizaci, kteří mají zařízení s Iosem 10. Požadavek, že vaši koncoví uživatelé svá zařízení před upgradovat na podporovanou verzi operačního systému. září.

### <a name="plan-for-change-support-for-version-811-and-higher-of-intune-app-sdk-for-ios----3586942--"></a>Plánovaná změna: Podpora pro verzi 8.1.1 a vyšší sady Intune App SDK pro iOS <!-- 3586942-->
Od září 2019, Intune přesune pro podporu aplikací pro iOS nástrojem Intune App SDK 8.1.1 a vyšší. Aplikace vytvořené pomocí sady SDK verze nižší než 8.1.1 budou již nejsou podporovány. Tato změna začnou platit od společnosti Apple verzi iOS 13, které se očekává kolem září a také budou oznámeny byla v MC181399.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Díky integraci sady Intune App SDK nebo pro zabalení aplikace můžete chránit podniková data z neschválených aplikací a uživatelů prostřednictvím šifrování dat. Sady Intune App SDK pro iOS ve výchozím nastavení použije 256bitových šifrovacích klíčů, když je povoleno šifrování pomocí Intune App Protection zásady (aplikace). Po této změně žádné aplikace pro iOS na verze sady SDK před 8.1.1, které používají 128bitové šifrování klíče, už nebude moci sdílet data s aplikacemi integrovaná se sadou SDK 8.1.1 nebo pomocí klíče 256 bitů. Všechny aplikace pro iOS bude muset mít sadu SDK verze 8.1.1 nebo vyšší umožňující chráněných dat pro sdílení obsahu.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
Zkontrolujte vaše aplikace Microsoftu, třetích stran a obchodní (LOB). Měli byste zajistit všechno, všechny svoje aplikace, které jsou chráněné pomocí Intune APP používáte sadu SDK verze 8.1.1 nebo novější.

- Pro obchodní aplikace: Budete muset znovu publikovat aplikace integrované s verzí sady SDK 8.1.1 nebo novější. Doporučujeme nejnovější verzi sady SDK. Infomration o tom, jak Příprava obchodních aplikací pro zásady ochrany aplikací, najdete v části [Příprava-obchodních aplikací pro zásady ochrany aplikací](../apps-prepare-mobile-application-management.md).
- Pro aplikace pro Microsoft nebo třetích stran: Ujistěte se, že se nasazení nejnovější verze těchto aplikací pro vaše uživatele.

Dokumentace nebo pro vývojáře pokyny by měl také aktualizovat, pokud je k dispozici podpora pro sadu SDK zahrnout tuto změnu.

#### <a name="additional-information"></a>Další informace
https://docs.microsoft.com/intune/apps-prepare-mobile-application-management
