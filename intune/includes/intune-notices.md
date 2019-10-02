---
title: zahrnout soubor
description: zahrnout soubor
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: fa251a0edd943d566849b138af5cbab0be248a53
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71731758"
---
Tato oznámení obsahují důležité informace, které vám pomůžou připravit se na budoucí změny a funkce Intune. 


### <a name="decreasing-support-for-android-device-administrator"></a>Snížení podpory pro správce zařízení s Androidem 
Správce zařízení s Androidem (někdy označovaný jako "starší verze" správy Androidu a vydaný s Androidem 2,2) je způsob, jak spravovat zařízení s Androidem. Vylepšené funkce správy jsou teď ale k dispozici v [Androidu Enterprise](../enrollment/connect-intune-android-enterprise.md) (vydané s androidem 5,0). V úsilí o přechod na moderní, bohatou a bezpečnější správu zařízení bude Google v nových verzích Androidu snížit podporu Správce zařízení.

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

#### <a name="additional-information"></a>Další informace
- [Pokyny pro migraci ze strany správce zařízení na Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Dokumentace ke službě Google v plánu pro zařazování rozhraní API pro správce zařízení](https://developers.google.com/android/work/device-admin-deprecation)

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

### <a name="plan-for-change-new-windows-updates-settings-in-intune----4464404---"></a>Plánování změn: nové nastavení aktualizací Windows v Intune <!-- 4464404 -->
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

### <a name="plan-for-change-intune-app-sdk-and-app-protection-policies-for-android-moving-to-support-android-50-and-higher-in-october---4911065---"></a>Plánování změn: sada Intune App SDK a zásady ochrany aplikací pro Android, které se přesunou na podporu Android 5,0 a novějších v říjnu <!--4911065 -->
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

### <a name="intune-plan-for-change-nearing-end-of-support-for-windows-7----3042987---"></a>Plán změny v Intune: blíží se konec podpory pro Windows 7. <!-- 3042987 -->
Protože jsme se poslali v MC148476, který byl vydán posledních září 2018, a znovu v MC176794 zpátky v březnu 2019, Windows 7 dosáhne konce rozšířené podpory 14. ledna 2020. V tuto chvíli Intune vyřadí podporu pro zařízení s Windows 7, takže můžeme zaměřit naši investici na podporu novějších technologií a zajistit Skvělé nové prostředí koncových uživatelů. Po tomto datu se v Intune už nebude k dispozici technická pomoc a automatické aktualizace, které vám pomůžou chránit počítač s Windows 7. Microsoft důrazně doporučuje přejít na Windows 10 před lednem 2020, aby nedocházelo k situaci, kdy potřebujete službu nebo podporu, která už není dostupná. Další informace o životním cyklu podpory pro Windows [najdete tady](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Tuto zprávu dostáváte, protože aktuálně spravujete počítač se systémem Windows 7 pomocí starší verze softwarového agenta Intune pro počítače. Po kratší dobu než na konci rozšířené podpory Windows 7 doporučujeme vaší organizaci co nejdříve začít s upgradem na Windows 10. Možnosti správy počítačů se vytvářejí přímo v operačním systému Windows 10 a už nemusíte instalovat klientského agenta, jako je softwarový klient Intune pro Windows 7. Od Windows 8.1 používá společnost Microsoft architekturu správy mobilních zařízení (MDM) ke zřízení, konfiguraci, aktualizaci a správě počítačů s Windows. Jakmile nastavíte Intune, můžete zjednodušit registraci zařízení s Windows 10 tak, že [do Intune zaregistrujete počítače s Windows 10](..\windows-enroll.md) prostřednictvím kanálu MDM. Pro správu počítače s Windows 10 doporučujeme použít toto "bez agenta správy MDM".

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Doporučujeme, aby vaše organizace okamžitě zvážila tento akční plán:

- Naplánujte a upgradujte loďstev Windows 7 na Windows 10 do 14. ledna 2020.
- Pokud chcete získat další informace o tom, jak upgradovat stávající loďstvo počítače se systémem Windows 7 na Windows 10, prozkoumejte [podporu nasazení Windows 10](https://docs.microsoft.com/windows/deployment/) .
- Seznamte se s tím, jak [aplikace pro stolní počítače](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure?rtc=1) nabízí rychlou stopu, která vám pomůže s příslibem kompatibility aplikací Microsoftu.
- Převeďte stávající starší verze spravovaných softwarových klientů Intune do řešení doporučených pro společnost Microsoft pro správu Windows 10 pomocí správy mobilních zařízení (MDM). Zaregistrujte všechny nové počítače s Windows 10, které používají správu MDM pro Intune v Azure Portal.
- Další informace najdete v [blogu publikovaném tady](https://aka.ms/Windows7_Intune) .
