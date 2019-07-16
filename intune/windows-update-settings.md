---
title: Nastavení aktualizace Windows pro firmy pro Microsoft Intune – Azure | Microsoft Docs
description: Nastavení WUfB pro zařízení s Windows 10, která můžete nasadit pomocí Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9e9baf3593883cf2fa2402a0b4daec638a336366
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "67884201"
---
# <a name="windows-update-settings-for-intune"></a>Nastavení služby Windows Update pro Intune  

Prohlédněte si nastavení aktualizace Windows 10, která můžete [Konfigurovat a spravovat](windows-update-for-business-configure.md) pomocí Microsoft Intune.  

Když konfigurujete nastavení pro aktualizační kanály Windows 10 v Intune, konfigurujete nastavení web Windows Update. Pokud má nastavení Windows Update závislost na verzi Windows 10, zaznamená se závislost na verzi v podrobnostech nastavení.  

## <a name="update-settings"></a>Aktualizovat nastavení  

Nastavení aktualizace řídí, co se bude stahovat a kdy se zařízení stáhne. Další informace o chování jednotlivých nastaveních najdete v referenční dokumentaci k systému Windows.  

### <a name="servicing-channel"></a>Kanál pro údržbu  

- **Výchozí**: Půlroční kanál (cílený)  
- **Referenční dokumentace systému Windows**: [Update/BranchReadinessLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-branchreadinesslevel)  
Nastavte kanál (větev), ze kterého zařízení přijímá aktualizace systému Windows. Různé kanály můžou před doručením aktualizací používat odlišná období odložení.  

Například *půlroční kanál* má odložení po dobu šesti měsíců. Pokud použijete tento kanál bez dalších odložení z tohoto základního nastavení, zařízení nainstaluje aktualizaci po dobu šesti měsíců po jejím vydání.  

Podporované kanály pro aktualizace:  

- Půlroční kanál  
- Půlroční kanál (cílený)  
- Windows Insider – rychlá  
- Windows Insider – pomalé  
- Windows Insider – Release  

Když vyberete kanál Insider, Intune automaticky nakonfiguruje nastavení služby Windows Update [Update/ManagePreviewBuilds](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-managepreviewbuilds) , aby se Build Insider mohl pracovat.  


> [!IMPORTANT]  
> Počínaje systémem Windows verze 1903 je použití *pololetního kanálu (cílené)* (SAC-T) vyřazeno. Při této změně se SAC – T sloučí s půlročním *kanálem*. Pokud chcete získat další informace o této změně a o tom, jak má vliv na web Windows Update pro firmy, přečtěte si Blogový příspěvek ve Windows pro IT specialisty [web Windows Update pro firmy a vyřazení konzoly SAC – T](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-Update-for-Business-and-the-retirement-of-SAC-T/ba-p/339523).
 


### <a name="microsoft-product-updates"></a>Aktualizace produktů společnosti Microsoft  

- **Výchozí**:  Allow
- **Referenční dokumentace systému Windows**: [Update/AllowMUUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowmuupdateservice)

Vyberte možnost *umožňuje* vyhledávat aktualizace aplikací z Microsoft Update.    

### <a name="windows-drivers"></a>Ovladače Windows  

- **Výchozí**:  Allow
- **Referenční dokumentace systému Windows**: [Aktualizovat/ExcludeWUDriversInQualityUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-excludewudriversinqualityupdate)

V případě aktualizací vyberte možnost *Allow* include web Windows Update Drivers.

### <a name="quality-update-deferral-period-days"></a>Doba odložení aktualizace kvality (ve dnech)  

- **Výchozí**: 0  
- **Referenční dokumentace systému Windows**: [Aktualizovat/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays)  

Zadejte počet dní od 0 do 30, pro které se odložit aktualizace kvality. Toto období je kromě všech období odložení, které je součástí zvoleného kanálu služby. Doba odložení začíná, když zařízení obdrží zásady.  

Aktualizace kvality jsou obvykle opravy a vylepšení stávajících funkcí systému Windows.  

### <a name="feature-update-deferral-period-days"></a>Doba odložení aktualizace funkcí (ve dnech)  

- **Výchozí**: 0  
- **Referenční dokumentace systému Windows**: [Update/PauseFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays)  

Zadejte počet dní, po které se mají odložit aktualizace funkcí. Toto období je kromě všech období odložení, které je součástí zvoleného kanálu služby. Doba odložení začíná, když zařízení obdrží zásady.  
Podporované období odložení:  

- *Windows verze 1709 nebo novější*: 0 až 365 dní  
- *Windows verze 1703*:  0 až 180 dní  

Aktualizace funkcí jsou zpravidla nové funkce pro Windows.  

### <a name="set-feature-update-uninstall-period-2--60-days"></a>Nastavit období odinstalace aktualizací funkcí (2 – 60 dní)  

- **Výchozí**: 10  
- **Referenční dokumentace systému Windows**:  [Aktualizovat/ConfigureFeatureUpdateUninstallPeriod](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configurefeatureupdateuninstallperiod)  

Nakonfigurujte čas, po kterém se aktualizace funkcí nedají odinstalovat.  

Po uplynutí této doby se ze zařízení odeberou předchozí aktualizace a nebude už možné ji odinstalovat na předchozí verzi aktualizace.  

Představte si například aktualizační kanál s dobou odinstalace aktualizace funkcí o 20 dní. Po 25 dnech se rozhodnete vrátit nejnovější aktualizaci funkcí a použít možnost odinstalace.  Zařízení, na která se nainstalovala aktualizace funkcí víc než 20 dní, ji nemůžou odinstalovat, protože v rámci údržby odebrala potřebné bity. Zařízení, u kterých se tato funkce nainstalovala jenom do 19 dnů, ale můžou aktualizaci odinstalovat, jenom když se úspěšně zaregistrují, aby se před tím, než je doba odinstalace odinstalovala.  


## <a name="user-experience-settings"></a>Nastavení uživatelského prostředí  

Nastavení uživatelského prostředí řídí činnost koncového uživatele při restartu a připomenutích zařízení. Další informace o chování jednotlivých nastaveních najdete v referenční dokumentaci k systému Windows.  

### <a name="automatic-update-behavior"></a>Chování Automatické aktualizace  

- **Výchozí**: Automaticky nainstalovat a restartovat v naplánovaném čase  
- **Referenční dokumentace systému Windows**: [Aktualizovat/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

Vyberte, jak se mají instalovat automatické aktualizace, a pokud je to nutné, když zařízení restartujete.  

Kompletní informace o následujících podporovaných možnostech najdete v referenční dokumentaci Windows:  

- **Odeslat zprávu pro stažení** – před stažením aktualizace upozorněte uživatele. Uživatelé si můžou stáhnout a nainstalovat aktualizace.  

- **Automaticky nainstalovat v době údržby** – aktualizace se automaticky stahují a pak se během automatické údržby nainstalují, když se zařízení nepoužívá nebo neběží při napájení z baterie. Po restartování počítače se uživatelům zobrazí výzva k restartování po dobu až sedmi dnů a pak se restartování vynutí.  

  Tato možnost po instalaci aktualizace může zařízení restartovat automaticky. Pomocí nastavení **aktivní hodiny** můžete definovat období, během kterého jsou automatické restartování blokované:  

  - **Začátek aktivních hodin**: Zadejte počáteční čas pro potlačení restartování z důvodu instalace aktualizací.  
    **Referenční dokumentace systému Windows**:  [Aktualizovat/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Výchozí**: 8 DOP.  
  
  - **Konec aktivní hodiny**: Zadejte čas ukončení pro potlačení restartování z důvodu instalace aktualizací.  
    **Referenční dokumentace systému Windows**:  [Aktualizovat/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Výchozí**: 5 ODP.  

- Automaticky **nainstalovat a restartovat v době údržby** – aktualizace se automaticky stahují a pak se nainstalují během automatické údržby, když se zařízení nepoužívá nebo se spouští při napájení z baterie. Pokud je vyžadováno restartování, zařízení se restartuje, když se nepoužívá. (Toto je výchozí nastavení pro nespravovaná zařízení.)  

  Tato možnost po instalaci aktualizace může zařízení restartovat automaticky. Použití nastavení **aktivní hodiny** není popsané v nastavení web Windows Update, ale používá se v Intune k definování období, během kterého se zablokuje automatické restartování:  

  - **Začátek aktivních hodin**: Zadejte počáteční čas pro potlačení restartování z důvodu instalace aktualizací.  
    **Referenční dokumentace systému Windows**:  [Aktualizovat/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Výchozí**: 8 DOP.  

  - **Konec aktivní hodiny**: Zadejte čas ukončení pro potlačení restartování z důvodu instalace aktualizací.  
    **Referenční dokumentace systému Windows**:  [Aktualizovat/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Výchozí**: 5 ODP.  

- **Automaticky nainstalovat a restartovat v naplánovaném čase** – zadejte den a čas instalace. Je-li tento parametr zadán, bude instalace spuštěna 3. den a následuje 15 minut odpočítávání za účelem restartu. Přihlášené používání může zpozdit odpočítávání a restartování.  
  
  Tato možnost podporuje další nastavení.  
  **Referenční dokumentace systému Windows**:  [Aktualizovat/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

  - **Frekvence automatického chování**: Pomocí něj můžete naplánovat, kdy se aktualizace nainstalují (můžete určit týden, den a čas).  
    **Výchozí**: Každý týden

  - **Den plánované instalace**:  Určete, ke kterému dni v týdnu chcete nainstalovat aktualizace.  
    **Výchozí**: Každý den  

  - **Čas plánované instalace**:  Zadejte denní dobu, kdy chcete nainstalovat aktualizace.  
    **Výchozí**: 3 DOP.  

- Automaticky **nainstalovat a restartovat bez ovládacího prvku pro koncové uživatele** – aktualizace se automaticky stahují a pak se během automatické údržby nainstalují, když se zařízení nepoužívá nebo neběží při napájení z baterie. Pokud je vyžadováno restartování, zařízení se restartuje, když se nepoužívá. Tato možnost nastaví podokno ovládacího prvku koncoví uživatelé na jen pro čtení.  

- **Obnovit výchozí** – obnoví původní nastavení automatické aktualizace na počítačích s Windows 10, na kterých běží aktualizace z října 2018 nebo novější.  


### <a name="restart-checks"></a>Restartovat kontroly  

- **Výchozí**: Allow  
- **Referenční dokumentace systému Windows**: [Aktualizovat/SetEDURestart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setedurestart)  

Toto nastavení má různé výsledky v závislosti na verzi Windows pro zařízení:  

- Windows verze 1703 a starší: Po restartu zařízení se provádí některé kontroly, například zjišťování aktivních uživatelů, stavu baterie, spuštěných her a další. Pokud tyto kontroly chcete přeskočit, zvolte **Přeskočit**.  
- Počínaje systémem Windows verze 1709: Během aktivní hodiny se pro aktualizace nespouštějí následující procesy: kontrola, stažení, instalace a restartování. Po aktivní hodině se procesy aktualizace spouštějí a můžou zařízení probudit z režimu spánku, prohledávat, stahovat, instalovat a restartovat zařízení, pokud se kontrolují baterie a kontrolují napájení. Další informace najdete v tématu [Update/SetEDURestart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setedurestart).  

### <a name="block-user-from-pausing-windows-updates"></a>Zablokovat uživateli pozastavit aktualizace Windows  

- **Výchozí**: Allow  
- **Referenční dokumentace systému Windows**: [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)  

Povolí nebo zablokuje uživateli zařízení, aby pozastavil instalaci aktualizace. 

### <a name="block-user-from-scanning-for-windows-updates"></a>Zablokovat uživateli kontrolu aktualizací Windows  
- **Výchozí**: Allow
- **Referenční dokumentace systému Windows**: [Update/SetDisableUXWUAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisableuxwuaccess) 

Určuje, jestli se má pro kontrolu web Windows Update pro uživatele zakázat nebo blokovat přístup. Pokud například nakonfigurujete *blok*, uživatelé nebudou mít přístup k funkcím pro kontrolu web Windows Update, stahování a instalaci.  

### <a name="require-users-approval-to-restart-outside-of-work-hours"></a>Vyžadovat schválení uživatele pro restartování mimo pracovní dobu  

- **Výchozí**: Není nakonfigurováno  
- **Referenční dokumentace systému Windows**: [Aktualizovat/AutoRestartRequiredNotificationDismissal](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
  
Vyberte možnost *požadováno* , pokud požadujete, aby uživatel schválil restart zařízení mimo pracovní dobu.  
   
### <a name="remind-user-prior-to-required-auto-restart-with-dismissible-reminder-hours"></a>Připomenout uživatele před vyžadováním automatického restartování s připomenutím přeskočit (hodiny)  

- **Výchozí**: *Toto nastavení není ve výchozím nastavení nakonfigurované a uživatelům se nezobrazí žádné připomenutí*.  
- **Referenční dokumentace systému Windows**: [Aktualizovat/ScheduleRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)  

Určete, jak dlouho předem má automatické restartování zobrazovat oznámení přeskočit uživateli zařízení o tomto restartování. Jsou podporovány hodnoty **2**, **4**, **8**, **12**a **24** hodin.  

### <a name="remind-user-prior-to-required-auto-restart-with-permanent-reminder-minutes"></a>Připomenout uživatele před vyžadováním automatického restartování s trvalým připomenutím (minuty)  

- **Výchozí**: *Toto nastavení není ve výchozím nastavení nakonfigurované a uživatelům se nezobrazí žádné připomenutí*.  
- **Referenční dokumentace systému Windows**: [Update/ScheduleImminentRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning) 

Zadejte, jak dlouho předem bude automatické restartování pro uživatele zařízení o tomto restartování zobrazovat upozornění bez přeskočit. Jsou podporovány hodnoty **15**, **30** a **60** minut.  

### <a name="windows-update-notification-level"></a>Web Windows Update úroveň oznámení  
- **Výchozí**: Použít výchozí oznámení web Windows Update 
- **Referenční dokumentace systému Windows**: [Aktualizovat/UpdateNotificationLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

Určete, jakou úroveň oznámení web Windows Update uživatelé uvidí. Toto nastavení neurčuje, jak a kdy se aktualizace stahují a instalují.

### <a name="allow-user-to-restart-engaged-restart"></a>Povolení restartování uživatelem (při restartování)  

- **Výchozí**: Není nakonfigurováno  
- **Referenční dokumentace systému Windows**: *Nelze použít*  
- **Verze systému Windows**: Podporováno pro Windows 10 verze 1803 a novější  

  > [!NOTE]  
  > Windows 10 verze 1809 zavádí další nastavení, které je potřeba restartovat, které umožňuje použít pro aktualizace funkcí a kvality samostatné nastavení. Nastavení spravovaná přes Intune ale neplatí samostatně pro různé typy aktualizací. Místo toho Intune aplikuje stejné hodnoty na aktualizace funkcí i kvality.  

Pokud je nastavené na **požadováno**, povolíte použití možností změny pro Windows 10. Pomocí těchto možností můžete uživatele zařízení pořídit, kdy po instalaci aktualizace, která vyžaduje restart, restartovat zařízení.  

Další informace o této možnosti najdete v tématu věnovaném [restartování](https://docs.microsoft.com/windows/deployment/update/waas-restart#engaged-restart) v dokumentaci k Windows 10 pro nasazení aktualizací.  

Následující nastavení se používají k určení, kdy dojde k akcím v restartu.  

- **Převod uživatelů na restartování po automatickém restartování (dny)**  
  - **Výchozí**:  Ve výchozím nastavení to není nakonfigurované, ale podporuje hodnotu od **2** do **30**.  
  - **Referenční dokumentace systému Windows**: [Update/EngagedRestartTransitionSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestarttransitionschedule)  
  Určete, jak dlouho se aktualizace po instalaci nainstaluje, dokud zařízení nevstoupí do činnosti. Po nakonfigurovaném počtu dnů se uživatelům zobrazí výzva k restartování zařízení.  

- **Odložit připomenutí s přijatým restartováním (dny)**  
  - **Výchozí**:  Ve výchozím nastavení není toto nastavení nakonfigurované, ale podporuje hodnotu od **1** do **3**.  
  - **Referenční dokumentace systému Windows**: [Update/EngagedRestartSnoozeSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartsnoozeschedule)  
  Určete, jak dlouho se výzva k restartování dá odložit.  Po uplynutí doby odložení se znovu nabídne výzva k restartování. Uživatel může pokračovat v odložení připomenutí, dokud nebude dosaženo konečného termínu instalace.  

- **Nastavit konečný termín pro čekání na restartování (dny)**  
  - **Výchozí**:  Ve výchozím nastavení není toto nastavení nakonfigurované, ale podporuje hodnotu od **2** do **30**.  
  - **Referenční dokumentace systému Windows**: [Aktualizovat/EngagedRestartDeadline](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartdeadline)  
  Zadejte maximální počet dní, po který se má počkat, než se zahájí chování při restartování, než zařízení vynutilo vyžadované restartování. Tento restart vyzve uživatele, aby uložil svou práci.

### <a name="delivery-optimization-download-mode"></a>Režim stažení Optimalizace doručení  

Optimalizace doručení již není konfigurována jako součást aktualizačního kanálu Windows 10 v části aktualizace softwaru. Optimalizace doručování se teď nastavuje prostřednictvím konfigurace zařízení. Předchozí konfigurace ale zůstanou v konzole k dispozici. Tyto předchozí konfigurace můžete odebrat tak, že je upravíte, aby *nebyly nakonfigurované*, ale nelze je jinak upravovat. 

Aby nedocházelo ke konfliktům mezi novou a starou zásadou, přečtěte si téma [Přesun z existujících aktualizačních kanálů na optimalizaci doručování](delivery-optimization-windows.md#move-existing-update-rings-to-delivery-optimization) a přesunutí nastavení do profilu Optimalizace doručení.
