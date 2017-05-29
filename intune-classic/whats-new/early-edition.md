---
title: "Časná edice | Dokumentace Microsoftu"
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 249a902e6e10f799dcff4e1c46da90cd62f2c125
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="the-early-edition-for-microsoft-intune---may-2017"></a>Časná edice Microsoft Intune – květen 2017

**Časná edice** poskytuje seznam funkcí, které se chystají v nadcházejících vydáních služby Microsoft Intune. Tyto informace jsou poskytovány na základě smlouvy o utajení (NDA) ve velmi omezené míře a můžou podléhat změnám. U některých funkcí, které jsou zde uvedeny, existuje riziko, že nebudou do konečného termínu dokončeny, a můžou se proto objevit až v budoucí verzi. Další funkce se testují v pilotní (testovací) verzi, aby bylo zajištěno, že je budou moct zákazníci bez problémů využívat. Pokud máte jakékoli dotazy nebo připomínky, obraťte se prosím na příslušný kontakt (Intune/PM).

Tato stránka se pravidelně aktualizuje. Přijďte se tedy znovu podívat, jestli nejsou k dispozici nové informace.

> [!Note]
> Následující změny v Intune jsou ve vývoji. Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nové funkce

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Podpora jednotného přihlášení z Portálu společnosti pro iOS do Outlooku pro iOS <!--834012-->

Uživatelé už se nemusí přihlašovat k aplikaci Outlook, pokud jsou na stejném zařízení pomocí stejného účtu přihlášení k aplikaci Portál společnosti pro iOS. Při spuštění aplikace Outlook budou uživatelé moct zvolit svůj účet a přihlásit se automaticky. Pracujeme také na tom, abychom tuto funkci přidali i pro další aplikace Microsoftu.

### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Vylepšené oznámení pro spouštěcí PIN kódy Samsungu KNOX <!--1087143-->

Když budou koncoví uživatelé potřebovat nastavit spouštěcí PIN kód na zařízeních Samsung KNOX, tak aby byla kompatibilní se šifrováním, zobrazené oznámení je po klepnutí na ně odkáže přímo na místo v aplikaci Nastavení.  Dříve oznámení odkázalo koncové uživatele na obrazovku pro změnu hesla.

### <a name="promoting-the-most-current-version-of-the-company-portal-for-android---1098661--"></a>Zvýšení úrovně nejaktuálnější verze Portálu společnosti pro Android <!--1098661-->

Po vydání nové doporučené verze Portálu společnosti pro Android se koncovým uživatelům zobrazí oznámení v aplikaci na obrazovce Oznámení. Toto oznámení uživatelům sdělí, že je k dispozici aktualizace Portálu společnosti. Po klepnutí na oznámení se otevře webová stránka se seznamem dostupných obchodů s aplikacemi, kde si aktualizovanou verzi můžete stáhnout. 

### <a name="improvements-to-app-syncing-with-windows-10-creators-update----676505---"></a>Vylepšení synchronizace aplikace s Windows 10 Creators Update <!-- 676505 -->

Portál společnosti pro Windows 10 automaticky zahájí synchronizaci pro požadavky na instalaci zařízení s Windows 10 Creators Update (1704). Omezí se tím potíže s pozastavením instalací aplikace ve stavu čekající synchronizace. Uživatelé navíc budou moct synchronizaci zahájit ručně uvnitř aplikace. 

Portál společnosti pro Windows 10 bude také zobrazovat tlačítko pro aktualizaci, které uživateli umožní aktualizovat obsah v aplikaci, kdykoli to bude potřebovat. 

## <a name="notices"></a>Sdělení

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple bude vyžadovat aktualizace ATS (Application Transport Security) <!--748318-->

Apple oznámil, že od jara 2017 začne vynucovat specifické požadavky na ATS (Application Transport Security). ATS se používá k vynucení vyššího zabezpečení veškeré komunikace aplikací přes protokol HTTPS. Tato změna ovlivní zákazníky Intune, kteří používají aplikace Portál společnosti pro iOS. Další podrobnosti najdete v [blogu podpory služby Intune](https://aka.ms/compportalats).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Přímý přístup ke scénářům registrace Apple <!--951869-->

U účtů Intune vytvořených po lednu 2017 umožňuje Intune přímý přístup ke scénářům registrace Apple pomocí úlohy Registrovat zařízení na portálu Azure Preview. Náhled na registraci Apple byl předtím přístupný přes odkazy na portálu klasické služby Intune. Zpřístupnění těchto funkcí v Azure bude u účtů Intune vytvořených před lednem 2017 vyžadovat jednorázovou migraci. Plán této migrace zatím nebyl oznámen, podrobnosti ale budou zpřístupněny co nejdříve. Pokud váš existující účet nemá k tomuto náhledu přístup, k otestování tohoto nového prostředí důrazně doporučujeme vytvořit zkušební účet.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Co se chystá pro Appx v Intune na Azure <!-- 1000270 -->

V rámci migrace do Intune na Azure provádíme tři změny appx:

1. Přidání nového typu aplikace appx v klasické konzole Intune, který se dá nasadit jenom na zařízení zaregistrovaná v MDM
2. Změna účelu stávajícího typu aplikace appx, aby byl zacílený jenom na počítače PC spravované pomocí agenta Intune pro počítače PC
3. Převedení všech stávajících appx na appx MDM v rámci migrace

Nebude to mít vliv na žádné z vašich stávajících nasazení do zařízení spravovaných pomocí agenta Intune pro počítače PC. Po migraci ale nebudete moct tyto migrované appx nasadit do žádných nových zařízení spravovaných pomocí agenta Intune pro počítače PC, pokud na ně předtím nebylo zacíleno.

Pokud budete chtít provést nová nasazení do počítačů PC, budete muset po migraci znovu nahrát appx jako appx pro počítače PC. Další informace najdete v článku o [změnách appx v Intune na Azure](https://aka.ms/appxchange) na blogu týmu podpory Intune.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Veřejná verze Preview nového prostředí pro správu Intune v Azure <!--736542-->

Na začátku kalendářního roku 2017 provedeme migraci celého našeho prostředí pro správu do Azure, což umožní výkonnou a integrovanou správu základních pracovních postupů EMS na moderní platformě pro služby, která je rozšiřitelná pomocí rozhraní Graph API.

Noví zkušební tenanti se začnou objevovat ve veřejné verzi Preview nového prostředí pro správu na webu Azure Portal tento měsíc. Funkce a parita se stávající konzolou Intune se ve verzi Preview budou zavádět postupně.

Prostředí pro správu na webu Azure Portal bude využívat nové funkce seskupování a cílení, které už byly oznámeny. Při migraci vašeho stávajícího tenanta do nového prostředí seskupování se provede také vaše migrace do verze Preview nového prostředí pro správu vašeho tenanta. Pokud si chcete otestovat nebo prohlédnout některé nové funkce ještě před migrací vašeho tenanta, zaregistrujte si nový zkušební účet Intune nebo se podívejte na [novou dokumentaci](https://docs.microsoft.com/intune/what-is-intune).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Podpora možností spravované konfigurace pro aplikace Android <!-- 621621 -->

V obchodu Play budete moct konfigurovat aplikace Android podporující možnosti spravované konfigurace.  Tato funkce umožňuje zobrazit seznam hodnot konfigurace podporovaných aplikací a poskytuje prvotřídní uživatelské rozhraní s asistencí, které umožňuje tyto hodnoty konfigurovat.

### <a name="remote-assistance-for-android-devices----675418---"></a>Vzdálená pomoc pro zařízení s Androidem <!-- 675418 -->

Microsoft Intune vám pomocí softwaru [TeamViewer](https://www.teamviewer.com), který se kupuje zvlášť, umožní poskytovat vzdálenou pomoc uživatelům, kteří používají zařízení s Androidem.

### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Konfigurace oprávnění zařízení pro aplikace Android for Work <!-- 621614 -->

U aplikací nasazených do pracovních profilů zařízení Android for Work budete moct nakonfigurovat stav oprávnění pro jednotlivé aplikace. Aplikace pro Android, které vyžadují oprávnění zařízení, jako je například přístup k umístění nebo fotoaparátu zařízení, ve výchozím nastavení vyzvou uživatele, aby oprávnění přijali nebo odmítli.  Pokud například aplikace používá mikrofon zařízení, potom bude koncový uživatel vyzván, aby aplikaci udělil oprávnění používat mikrofon. Tato funkce vám umožní definovat oprávnění jménem koncového uživatele.  Správce může konfigurovat oprávnění, aby

- Došlo k automatickému zamítnutí bez upozornění uživatele
- Došlo k automatickému schválení bez upozornění uživatele
- Vyzval uživatele ke schválení nebo zamítnutí

### <a name="define-app-specific-pin-for-android-for-work-devices---728976--"></a>Definice PIN kódu aplikace pro zařízení s Androidem for Work <!--728976-->

Pro zařízení s Androidem 7.0 a vyšším spravovaná jako zařízení s Androidem for Work budete moct definovat zásady hesla, které se vztahují pouze na aplikace v pracovním profilu.  Vaše možnosti jsou:

- Definovat pouze zásady hesla pro celé zařízení – jedná se o heslo, které musí koncový uživatel používat k odemknutí celého zařízení.
- Definovat pouze zásady hesla pracovního profilu – koncoví uživatelé budou vyzváni k zadání hesla při každém otevření jakékoli aplikaci v pracovním profilu.
- Definovat zásady hesla pro zařízení i pro pracovní profil – IT má možnost definovat zásady hesla zařízení a pracovního profilu o různé síle (např. 4místný PIN kód pro odemknutí zařízení a 6místný PIN kód pro otevření libovolné pracovní aplikace).

>[!NOTE]
> Tyto možnosti budou k dispozici pouze u Androidu 7.0 a vyššího.  Ve výchozím nastavení bude mít koncový uživatel možnost použít dva samostatně definované PIN kódy, nebo se může rozhodnout zkombinovat tyto dva nadefinované PIN kódy do silnějšího z nich.

### <a name="manage-password-and-other-android-for-work-settings---1102534--"></a>Správa hesla a dalších nastavení Androidu for Work<!--1102534-->

Přidáváme novou zásadu omezení pro zařízení s Androidem for Work, která vám umožní spravovat nastavení hesla a pracovního profilu na zařízeních s Androidem for Work.

###  <a name="new-web-content-filter-policy-for-ios-devices----723832---"></a>Nové zásady filtru webového obsahu pro zařízení s iOSem <!-- 723832 -->

Budete moct řídit, které webové stránky můžou uživatelé zařízení s iOSem navštívit, a to pomocí jedné z těchto dvou metod:

  - Přidejte povolené a blokované adresy URL pomocí integrovaného filtru webového obsahu od společnosti Apple.
  - Povolte přístup z prohlížeče Safari jenom k určeným webovým stránkám. V prohlížeči Safari se vytvoří záložky pro weby, které určíte.

### <a name="apple-school-manager-asm-support---748864--"></a>Podpora Apple School Manageru (ASM) <!--748864-->

Pro první registraci zařízení s iOSem bude Intune místo programu Apple Device Enrollment Program podporovat použití Apple School Manageru (ASM). K použití aplikace Classroom pro sdílené iPady a k povolení synchronizace dat z ASM do Azure Active Directory prostřednictvím služby Synchronizace školních dat Microsoftu se vyžaduje zprovoznění ASM.  

### <a name="shared-ipad-support---770395-1044681---"></a>Podpora sdílených iPadů <!--770395, 1044681 -->

V profilu registrace pro program Apple Device Enrollment Program nebo Apple School Manager bude Intune podporovat konfiguraci režimu sdíleného iPadu. Toto nastavení umožňuje, aby se ke stejnému zařízení mohlo přihlásit více spravovaných Apple ID.

Rozšiřujeme také podporu správy aplikace Classroom pro iOS tak, aby zahrnovala studenty, kteří se přihlásí do sdílených iPadů pomocí svých spravovaných Apple ID.

### <a name="new-windows-device-restriction-settings---978585--"></a>Nová nastavení omezení pro zařízení s Windows <!--978585-->

Do profilu omezení zařízení s Windows přidáváme nastavení, která řídí funkce, jako jsou bezdrátové displeje, zjišťování zařízení, přepínání úloh a chybové zprávy SIM karet.

### <a name="office-365-proplus-app-available-for-windows-10-devices---1121362--"></a>Aplikace Office 365 ProPlus dostupná pro zařízení s Windows 10 <!--1121362-->

Přidáváme nový typ aplikace Office 365 ProPlus, který usnadňuje přiřazení aplikací Office 365 ProPlus zařízením s Windows 10. Pokud vlastníte příslušné licence, budete také moct nainstalovat Microsoft Project a Microsoft Visio. Požadované aplikace budou spojeny a v seznamu aplikací v konzole Intune se budou zobrazovat jako jedna aplikace.

### <a name="new-allowblock-list-for-the-managed-browser---682960--"></a>Nový seznam povolených/blokovaných adres pro Managed Browser <!--682960-->

Seznam povolených/blokovaných domén a adres URL pro Managed Browser budete moct konfigurovat pomocí nastavení konfigurace aplikace Intune na portálu Azure. Pro Managed Browser to jde nakonfigurovat bez ohledu na to, jestli se používá na spravovaném nebo nespravovaném zařízení.

### <a name="new-app-configuration-capabilities----677969---"></a>Nové možnosti konfigurace aplikace <!-- 677969 -->

Tato funkce bude odpovídat konfiguraci aplikace správy mobilního zařízení. Umožní správcům použít více hodnot konfigurace aplikace, než jsou jen hodnoty konfigurace aplikace dostupné prostřednictvím zásad ochrany aplikace v MAM bez kanálu registrace.

### <a name="new-app-protection-policies-conditions-for-mam---679864--"></a>Nové podmínky zásad ochrany aplikace pro MAM <!--679864-->

Budete moct nastavit požadavek pro MAM bez uživatelů registrace prostřednictvím konzole pro správu vynucující:

- Minimální verzi aplikací
- Minimální verzi operačního systému
- Minimální verzi Intune APP SDK cílové aplikace (pouze iOS)

Tato funkce bude k dispozici pro Android i iOS. Intune podporuje vynucení minimální verze pro verze platformy OS, verze aplikací a Intune APP SDK. V iOSu můžou aplikace s integrovanou sadou SDK také nastavit vynucení minimální veze na úrovni SDK.

Pokud nebudou splněny minimální požadavky prostřednictvím zásad ochrany aplikace na 3 různých úrovních uvedených výše, uživatel nebude moct k cílové aplikaci přistupovat. Uživatel teď může odebrat svůj účet (pro aplikace s více identitami), zavřít aplikaci a/nebo aktualizovat operační systém nebo verzi aplikace tak, aby odpovídaly požadavku.

Dále budete moct nakonfigurovat další nastavení prostřednictvím konzoly správce, abyste zajistili neblokující oznámení, které bude doporučovat upgrade operačního systému nebo aplikace. Toto oznámení se dá zavřít a aplikace se dá používat jako obvykle.

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Změna autority pro správu mobilních zařízení bez zrušení registrace spravovaných zařízení <!--1103950-->

Autoritu pro správu mobilních zařízení budete moct změnit, aniž byste museli kontaktovat podporu Microsoftu, museli zrušit registraci a provést novou registraci existujících spravovaných zařízení. V konzole nástroje Configuration Manager můžete změnit autoritu pro správu mobilních zařízení z Nastavit na nástroj Configuration Manager (hybridní) na Microsoft Intune (samostatné) a naopak.


### <a name="see-also"></a>Viz taky
Podrobnosti o posledním vývoji najdete v tématu [Co je nového v Microsoft Intune](whats-new-in-microsoft-intune.md).

