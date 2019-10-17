---
title: zahrnout soubor
description: zahrnout soubor
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 9e18182ff8cbddff1ae41298120928f2e2cb948a
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502756"
---
Tato oznámení obsahují důležité informace, které vám pomůžou připravit se na budoucí změny a funkce Intune.

### <a name="end-of-support-for-legacy-pc-management"></a>Konec podpory pro správu starších počítačů

Podpora starší verze správy počítačů od 15. října 2020. Upgradujte zařízení na Windows 10 a znovu je zaregistrujte jako zařízení MDM, abyste je mohli spravovat přes Intune.

[Další informace](https://go.microsoft.com/fwlink/?linkid=2107122)

### <a name="decreasing-support-for-android-device-administrator"></a>Snížení podpory pro správce zařízení s Androidem 
Správce zařízení s Androidem (někdy označovaný jako "starší verze" správy Androidu a vydaný s Androidem 2,2) je způsob, jak spravovat zařízení s Androidem. Vylepšené funkce správy jsou teď ale k dispozici v [Androidu Enterprise](../enrollment/connect-intune-android-enterprise.md) (vydané s androidem 5,0). V úsilí o přechod na moderní, bohatou a bezpečnější správu zařízení bude Google v nových verzích Androidu snížit podporu Správce zařízení.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Vzhledem k těmto změnám od společnosti Google budou mít uživatelé Intune tyto možnosti:  
- Intune bude moct poskytovat podporu jenom pro zařízení s Androidem spravovaná pomocí Správce zařízení s Androidem 10 nebo novějším (označovanou taky jako Android Q) až do letního 2020. Toto datum se očekává, že se má uvolnit další hlavní verze Androidu.   
- Zařízení spravovaná správcem zařízení se systémem Android 10 nebo novějším po léto 2020 již nebudou moci být zcela spravována.       
- Zařízení s Androidem spravovaná správcem zařízení, která zůstávají ve verzích Androidu pod Androidem 10, nebudou ovlivněná a můžou se dál spravovat pomocí Správce zařízení.    
- Pro všechna zařízení s Androidem 10 nebo novějším má Google možnost agentů správy zařízení, jako je Portál společnosti získat přístup k informacím o identifikátoru zařízení. To má vliv na následující funkce Intune po aktualizaci zařízení na Android 10 nebo novější:  
    - Řízení přístupu k síti pro VPN už nebude fungovat.   
    - Identifikaci zařízení jako vlastněných společností pomocí IMEI nebo sériového čísla nebudou zařízení automaticky označovat jako ve vlastnictví firmy.  
    - IMEI a sériové číslo se už nebudou zobrazovat správcům IT v Intune. 
        > [!NOTE]
        > To má vliv jenom na zařízení spravovaná správcem zařízení s Androidem 10 a novějším a nemá vliv na zařízení spravovaná jako Android Enterprise. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Abyste se vyhnuli snížení funkčnosti, které přichází v létě 2020, doporučujeme následující:
- Nepřidávejte nová zařízení do správy Správce zařízení.
- Pokud se očekává, že zařízení obdrží aktualizaci pro Android 10, migruje ji ze správy správců zařízení na zásady pro Android Enterprise Management a/nebo ochranu aplikací.

#### <a name="additional-information"></a>Další informace
- [Pokyny pro migraci ze strany správce zařízení na Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Dokumentace ke službě Google v plánu pro zařazování rozhraní API pro správce zařízení](https://developers.google.com/android/work/device-admin-deprecation)

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Aktualizace aplikace pro Android Portál společnosti na nejnovější verzi <!--4536963-->
Intune pravidelně uvolňuje aktualizace aplikace Portál společnosti pro Android. V listopadu 2018 jsme vydali aktualizaci portálu společnosti, která obsahovala back-end přepínač, který vám umožní připravit se na změny Google od stávající platformy oznámení až po Firebase Cloud Messaging (FCM) od společnosti Google. Když Google vyřazuje svou stávající platformu oznámení a přesune se na FCM, bude muset koncoví uživatelé aktualizovat Portál společnosti aplikaci na verzi alespoň 2018. listopadu, aby mohli pokračovat v komunikaci s úložištěm Google Play.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Naše telemetrie znamená, že máte zařízení s Portál společnosti verzí starší než 5.0.4269.0. Pokud tato verze nebo novější aplikace Portál společnosti není nainstalovaná, akce zařízení inicializované pro IT, jako je vymazání, resetování hesla, dostupná a požadovaná instalace aplikací, nemusí fungovat podle očekávání. Pokud jsou vaše zařízení zaregistrovaná v MDM v Intune, můžete pomocí klientských aplikací – zjištěné aplikace zobrazit Portál společnosti verze a uživatele. Výběr dřívějších verzí aplikace Portál společnosti vám umožní zjistit, které koncové uživatele mají zařízení, která aplikaci Portál společnosti neaktualizovala.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Zeptejte se koncových uživatelů zařízení s Androidem, která se neaktualizovala tak, aby se aktualizovaly aplikace Portál společnosti přes Google Play. Informujte pracovníky helpdesku o případ, že uživatel nedrží automatickou aktualizaci aplikace Portál společnosti. Podívejte se na odkaz v části *Další informace* , kde najdete další informace o FCM platformě Google a změně.

#### <a name="additional-information"></a>Další informace
https://firebase.google.com/docs/cloud-messaging/


### <a name="new-full-screen-experience-coming-to-intune---4593669--"></a>Nové prostředí pro celou obrazovku přicházející do Intune <!--4593669-->
Zavádíme aktualizované prostředí pro vytváření a úpravu uživatelského rozhraní pro Intune v Azure Portal. Toto nové prostředí zjednoduší stávající pracovní postupy pomocí formátu stylu, který je v jednom okně zhuštěný. Tato aktualizace prochází s "oknem neustálému zvětšování" nebo libovolnými toky vytváření a úprav, které vyžadují přechod k podrobnostem hloubkové jízdy. Pracovní postupy vytváření se také aktualizují tak, aby zahrnovaly přiřazení (s výjimkou přiřazení aplikace).

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Prostředí pro celou obrazovku se bude zavádět do Intune jak v portal.azure.com, tak v devicemanagement.microsoft.com během několika dalších měsíců. Tato aktualizace uživatelského rozhraní nebude mít vliv na funkčnost stávajících zásad a profilů, ale zobrazí se mírně upravený pracovní postup. Když vytvoříte nové zásady, budete moct nastavit některá přiřazení jako součást tohoto toku, a to tak, abyste je po vytvoření zásady nemuseli vytvářet. V příspěvku na blogu najdete *Další informace* o snímcích obrazovky, které nové prostředí bude vypadat v konzole.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
Nemusíte provádět žádnou akci, ale v případě potřeby můžete zvážit aktualizaci pokynů pro IT specialisty. Naši dokumentaci aktualizujeme, protože toto prostředí se zavede na různá okna v Intune na Azure Portal.

#### <a name="additional-information"></a>Další informace 
https://aka.ms/intune_fullscreen

### <a name="plan-for-change-new-windows-updates-settings-in-intune----4464404---"></a>Plánování změn: nové nastavení aktualizací Windows v Intune <!-- 4464404 -->
Od verze Intune do služby Intune nebo 1908 přidáváme nové "nastavení termínu", které můžete nakonfigurovat místo nastavení "umožní uživateli restartovat počítač". V uživatelském rozhraní v 1909 nebo září plánujeme zakázat nastavení, které je potřeba znovu spustit, a pak je úplně odebrat z konzoly do konce října.

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Pokud spravujete zařízení s Windows 10 ve vašem prostředí:

- V případě aktualizace Intune nebo 1908 se v konzole zobrazí nové nastavení termínu, kromě starého nastavení, které je potřeba znovu spustit.
- Když jsou tato stará i nová nastavení nakonfigurovaná, hodnoty nastavení konečného termínu přepíšou hodnoty nastavení po restartování.
- Nastavení konečného termínu nahradí v konzole v rámci aktualizace 1910 možnost "povolení uživatele k restartování (v tomto případě)".

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Jak se můžu na tyto změny připravit?
Začněte používat nastavení konečného termínu v 1908, a to tak, že je nakonfigurujete s požadovanými hodnotami. Jakmile to budete mít, můžete nastavit, aby se nastavení při spuštění z konzoly v říjnu nastavilo na Nenakonfigurováno.

V případě potřeby aktualizujte svou dokumentaci a skripty pro automatizaci.

Před odebráním nastavení možnosti aktualizace jsme si musíme v centru zpráv aktualizovat a vystavit připomenutí.

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
Stejně jako v MC148476, který jsme odeslali v, od poslední září 2018 a znovu v MC176794 zpátky v březnu 2019, Windows 7 dosáhne konce rozšířené podpory 14. ledna 2020. V tuto chvíli Intune vyřadí podporu pro zařízení s Windows 7, takže můžeme soustředit na naši investici do podpory novějších technologií a zajistit Skvělé nové prostředí pro koncové uživatele. Po tomto datu se v Intune už nebude k dispozici technická pomoc a automatické aktualizace, které vám pomůžou chránit počítač s Windows 7. Společnost Microsoft důrazně doporučuje přejít na Windows 10 před lednem 2020, aby nedocházelo k situaci, kdy potřebujete službu nebo podporu, která už není dostupná. Další informace o životním cyklu podpory pro Windows [najdete tady](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

#### <a name="how-does-this-affect-me"></a>Co to pro mě znamená?
Tuto zprávu dostáváte, protože aktuálně spravujete počítače se systémem Windows 7 pomocí starší verze softwarového agenta Intune pro počítače. Vzhledem k tomu, že zbývá méně než rok, než je prodloužená podpora Windows 7, důrazně doporučujeme vaší organizaci začít upgradovat na Windows 10, jakmile to bude možné.  

Možnosti správy počítačů se vytvářejí přímo v operačním systému Windows 10 a už nemusíte instalovat klientského agenta, jako je softwarový klient Intune pro Windows 7. Od Windows 8.1 používá společnost Microsoft architekturu správy mobilních zařízení (MDM) ke zřízení, konfiguraci, aktualizaci a správě počítačů s Windows. Když nastavíte Intune, můžete zjednodušit registraci zařízení s Windows 10 tak, že [do Intune zaregistrujete počítače s Windows 10](..\windows-enroll.md) prostřednictvím kanálu MDM. Pro správu počítačů s Windows 10 doporučujeme použít toto řešení správy MDM bez agenta.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Jak se mám na tuto změnu připravit?
Doporučujeme, aby vaše organizace okamžitě zvážila tento akční plán:

- Naplánujte a upgradujte loďstev Windows 7 na Windows 10 do 14. ledna 2020.
- V článku [Podpora nasazení Windows 10](https://docs.microsoft.com/windows/deployment/) najdete další informace o tom, jak upgradovat stávající loďstvo počítačů s Windows 7 na Windows 10.
- Seznamte se s tím, jak [desktopová aplikace](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure?rtc=1) nabízí nabídku inFastTrack, která vám pomůže s příslibem kompatibility aplikací Microsoftu.
- Převeďte stávající starší verze spravovaných softwarových klientů Intune do řešení doporučeného společností Microsoft pro správu Windows 10 pomocí správy MDM. Zaregistrujte všechny nové počítače s Windows 10 pomocí správy MDM pro Intune v Azure Portal.

Další informace najdete v tomto [blogovém příspěvku](https://aka.ms/Windows7_Intune) .
