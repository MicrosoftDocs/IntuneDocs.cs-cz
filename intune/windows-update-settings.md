---
title: Windows Update pro firmy nastavení pro Microsoft Intune – Azure | Dokumentace Microsoftu
description: WUfB nastavení pro zařízení s Windows 10, které můžete nasadit pomocí Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/04/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1797db030bd2716fd12a4f8c064a51b89b7964f8
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57397453"
---
# <a name="windows-update-settings-for-intune"></a>Windows aktualizovat nastavení pro Intune  

Zobrazit nastavení aktualizace Windows 10 můžete [konfigurovat a spravovat](windows-update-for-business-configure.md) pomocí Microsoft Intune.  

Při konfiguraci nastavení pro aktualizační okruhy Windows 10 v Intune, konfiguraci nastavení aktualizace Windows.  Při aktualizaci Windows nastavení má závislost na verzi Windows 10, verze závislosti je podrobně popsané nastavení.  

## <a name="update-settings"></a>Aktualizovat nastavení  

Aktualizovat správu nastavení bits, jaké budou zařízení stahovat, a kdy. Naleznete v dokumentaci Windows odkaz Další informace o chování jednotlivých nastavení.  

### <a name="servicing-channel"></a>Kanál pro údržbu  

- **Výchozí**: Půlroční kanál (cílený)  
- **Referenční dokumentace ke službě Windows**: [Update/BranchReadinessLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-branchreadinesslevel)  
Nastavte kanál (větve), ze kterého má zařízení přijímat aktualizace Windows. Různé kanály můžete použít různé odložení období před aktualizace jsou doručovány.  

Například *prostřednictvím půlročního kanálu* má šest měsíců odložení. To znamená, že pokud použijete tento kanál a žádné další odložení z této části nastavení, zařízení nainstaluje aktualizace šest měsíců po jeho uvolnění.  

Podporované aktualizace kanály:  

- Půlroční kanál  
- Půlroční kanál (cílený)  
- Windows Insider – Fast  
- Windows Insider – pomalý  
- Windows Insider – Release  

Pokud vyberete kanál Insider, Intune automaticky nakonfiguruje nastavení aktualizace Windows [aktualizace/ManagePreviewBuilds](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-managepreviewbuilds) tak, aby pracovaly se sestavení insider.  


> [!IMPORTANT]  
> Od systému Windows verze 1903, použití *půlroční kanál (cílený)* (SAC-T), byl vyřazen z provozu. Díky této změně SAC-T sloučí s *prostřednictvím půlročního kanálu*. Další informace o této změně a o jejím dopadu na Windows Update for Business, najdete v příspěvku blogu IT Pro Windows [Windows Update pro firmy a vyřazení SAC-T](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-Update-for-Business-and-the-retirement-of-SAC-T/ba-p/339523).
 


### <a name="microsoft-product-updates"></a>Aktualizace produktů Microsoftu  

- **Výchozí**:  Povolit
- **Referenční dokumentace ke službě Windows**: [Update/AllowMUUpdateService](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-allowmuupdateservice)

Zvolte *povolit* kontrolu aktualizace aplikací z webu Microsoft Update.    

### <a name="windows-drivers"></a>Ovladače Windows  

- **Výchozí**:  Povolit
- **Referenční dokumentace ke službě Windows**: [Update/ExcludeWUDriversInQualityUpdate](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-excludewudriversinqualityupdate)

Zvolte *povolit* zahrnout ovladače Windows Update během aktualizací

### <a name="quality-update-deferral-period-days"></a>Odložení aktualizace kvality (dny)  

- **Výchozí**: 0  
- **Referenční dokumentace ke službě Windows**: [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays)  

Zadejte počet dnů od 0 do 30, pro kterou budou aktualizace kvality odložené. Toto období se kromě období odkladu, který je součástí služby kanál, který jste vybrali. Doba odkladu začíná, když je zařízení přijímat zásady.  

Aktualizace kvality jsou obecně opravy a vylepšení stávajících funkcí Windows.  

### <a name="feature-update-deferral-period-days"></a>Odložení aktualizace funkcí (ve dnech)  

- **Výchozí**: 0  
- **Referenční dokumentace ke službě Windows**: [Update/PauseFeatureUpdatesPeriodInDays](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays)  

Zadejte počet dní, pro které budou aktualizace funkcí odložené. Toto období se kromě období odkladu, který je součástí služby kanál, který jste vybrali. Doba odkladu začíná, když je zařízení přijímat zásady.  
Doba odkladu podporované:  

- *Windows verze 1709 nebo novější*: 0 až 365 dnů  
- *Windows verze 1703*:  0 až 180 dní  

Aktualizace funkcí jsou zpravidla nové funkce pro Windows.  

### <a name="set-feature-update-uninstall-period-2--60-days"></a>Odinstalace aktualizací funkcí sady období (2 – 60 dní)  

- **Výchozí**: 10  
- **Referenční dokumentace ke službě Windows**:  [Update/ConfigureFeatureUpdateUninstallPeriod](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-configurefeatureupdateuninstallperiod)  

Nakonfigurujte čas, po aktualizace funkcí, které není možné odinstalovat.  

Po vypršení tohoto limitu, předchozí bity aktualizace se odebere ze zařízení a nebudou moci odinstalujte předchozí verzi aktualizace.  

Představte si třeba aktualizační kanál s funkcí aktualizace odinstalovat 20 dnů. Za 25 dnů rozhodnete vrátit nejnovější aktualizace funkcí a použijte možnost odinstalovat.  Zařízení s nainstalovanou aktualizací funkcí před více než 20 dny ji nelze odinstalovat, protože se odebraly nezbytné bity jako součást jejich údržbu. Zařízení, která instaluje aktualizace funkcí do 19 dny však můžete aktualizaci odinstalovat, pokud se úspěšně vrácení se změnami do zobrazí příkaz odinstalovat před překročení doby 20 dnů odinstalovat.  


## <a name="user-experience-settings"></a>Nastavení činnosti koncového uživatele  

Nastavení činnosti koncového uživatele řídit činnost koncového uživatele při restartování zařízení a připomenutí. Naleznete v dokumentaci Windows odkaz Další informace o chování jednotlivých nastavení.  

### <a name="automatic-update-behavior"></a>Chování automatické aktualizace  

- **Výchozí**: Automaticky nainstalovat a restartovat v naplánovaném čase  
- **Referenční dokumentace ke službě Windows**: [Update/AllowAutoUpdate](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

Zvolte způsob, jakým automatické aktualizace jsou nainstalovány a v případě potřeby, kdy se má zařízení restartovat.  

Získáte v dokumentaci Windows plně zveřejnit z těchto podporovaných možností:  

- **Oznámit stažení** – upozornit uživatele, než si stáhnete aktualizaci. Uživatelům se rozhodli stáhnout a nainstalovat aktualizace.  

- **Automaticky nainstalovat v době údržby** – stahování aktualizací automaticky a potom nainstalovat během automatické údržby, pokud zařízení není používán nebo funguje na baterii. Když se vyžaduje restartování, uživatelům se výzva k restartování po dobu až sedmi dnů a potom vynucené restartování.  

  Tuto možnost můžete restartovat zařízení automaticky po instalaci aktualizace. Použití **aktivní doby** nastavení můžete určit dobu, během které jsou blokovány, automatické restartování:  

  - **Začátek aktivní doby**: Zadejte čas zahájení pro potlačení restartu kvůli instalaci aktualizací.  
    **Referenční dokumentace ke službě Windows**:  [Update/ActiveHoursStart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Výchozí**: 8 AM  
  
  - **Konec aktivní doby**: Zadejte čas ukončení pro potlačení restartování kvůli instalaci aktualizací.  
    **Referenční dokumentace ke službě Windows**:  [Aktualizace/ActiveHoursEnd](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Výchozí**: 17: 00  

- **Automaticky nainstalovat a restartovat v době údržby** – stahování aktualizací automaticky a potom nainstalovat během automatické údržby, pokud zařízení není používán nebo funguje na baterii. Když se vyžaduje restartování, zařízení se restartuje, když se nevyužívají. (Toto je výchozí pro nespravovaná zařízení.)  

  Tuto možnost můžete restartovat zařízení automaticky po instalaci aktualizace. Použití **aktivní doby** nastavení nejsou popsané v nastavení služby Windows Update, ale používají Intune můžete určit dobu, během které jsou blokovány, automatické restartování:  

  - **Začátek aktivní doby**: Zadejte čas zahájení pro potlačení restartu kvůli instalaci aktualizací.  
    **Referenční dokumentace ke službě Windows**:  [Update/ActiveHoursStart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Výchozí**: 8 AM  

  - **Konec aktivní doby**: Zadejte čas ukončení pro potlačení restartování kvůli instalaci aktualizací.  
    **Referenční dokumentace ke službě Windows**:  [Aktualizace/ActiveHoursEnd](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Výchozí**: 17: 00  

- **Automaticky nainstalovat a restartovat v naplánovaném čase** – zadejte instalace den a čas. Pokud tento parametr zadán, spuštěna instalace v 3 hodin denně, následované odpočítávání 15 minut na restartování. Přihlášený používá můžete odložit odpočítávání a restartovat.  
  
  Tato možnost podporuje další nastavení.  
  **Referenční dokumentace ke službě Windows**:  [Update/AllowAutoUpdate](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

  - **Frekvence automatického chování**: Pomocí něj můžete naplánovat, kdy se aktualizace nainstalují (můžete určit týden, den a čas).  
    **Výchozí**: Každý týden

  - **Den plánované instalace**:  Zadejte den v týdnu, kdy se mají aktualizace instalovat.  
    **Výchozí**: Libovolný den  

  - **Čas plánované instalace**:  Zadejte čas den, kdy se mají aktualizace instalovat.  
    **Výchozí**: 3 AM  

- **Automaticky nainstalovat a restartovat bez ovládání koncovým uživatelem** – stahování aktualizací automaticky a potom nainstalovat během automatické údržby, pokud zařízení není používán nebo funguje na baterii. Když se vyžaduje restartování, zařízení se restartuje, když se nevyužívají. Tato možnost nastaví jen pro čtení v podokně ovládacího prvku koncovým uživatelům.  

- **Obnovit výchozí** – obnovení původního nastavení automatických aktualizací na Windows 10 počítačů, které používají aktualizace z října 2018 nebo novější.  


### <a name="restart-checks"></a>Kontroly při restartu  

- **Výchozí**: Povolit  
- **Referenční dokumentace ke službě Windows**: [Update/SetEDURestart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-setedurestart)  

Toto nastavení má odlišné výsledky v závislosti na verzi Windows, která se týká zařízení:  

- 1703 a starší verze Windows: Po restartu zařízení se provádí některé kontroly, například zjišťování aktivních uživatelů, stavu baterie, spuštěných her a další. Pokud tyto kontroly chcete přeskočit, zvolte **Přeskočit**.  
- Od systému Windows verze 1709: Během aktivní doby následující procesy nelze spustit pro aktualizace: zkontrolovat, stáhnout, nainstalovat a restartovat. Po skenování aktivní doby aktualizace procesy spuštění a může probudit z režimu spánku, zařízení, stáhnout, nainstalovat a restartovat zařízení jako splněné kontroly baterie a napájení. Další informace najdete v tématu [aktualizace/SetEDURestart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-setedurestart).  

### <a name="block-user-from-pausing-windows-updates"></a>Brání uživateli ve pozastavení aktualizací Windows  

- **Výchozí**: Povolit  
- **Referenční dokumentace ke službě Windows**: [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)  

Povolit nebo blokovat zařízení uživatele z pozastavení instalace aktualizace.  

### <a name="require-users-approval-to-restart-outside-of-work-hours"></a>Vyžadovat schválení uživatele k restartování mimo pracovní dobu  

- **Výchozí**: Není nakonfigurováno  
- **Referenční dokumentace ke službě Windows**: [Update/AutoRestartRequiredNotificationDismissal](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
  
Vyberte *vyžaduje* tak, aby vyžadovala, že uživatel schválit restartovat zařízení mimo pracovní dobu.  
   
### <a name="remind-user-prior-to-required-auto-restart-with-dismissible-reminder-hours"></a>Připomenout uživateli před požadované automatické restartování v dialogových připomenutí (hodiny)  

- **Výchozí**: *To není ve výchozím nastavení nakonfigurované a uživatelé nepředkládá žádná připomenutí*.  
- **Referenční dokumentace ke službě Windows**: [Update/ScheduleRestartWarning](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)  

Určete, jak dlouho před automatické restartování zobrazit oznámení o který můžete přeskočit na zařízení uživatele o tomto restartování. Hodnoty **2**, **4**, **8**, **12**, nebo **24** hodiny jsou podporovány.  

### <a name="remind-user-prior-to-required-auto-restart-with-permanent-reminder-minutes"></a>Připomenout uživateli před požadované automatické restartování v trvalé připomenutí (minuty)  

- **Výchozí**: *To není ve výchozím nastavení nakonfigurované a uživatelé nepředkládá žádná připomenutí*.  
- **Referenční dokumentace ke službě Windows**: [Update/ScheduleImminentRestartWarning](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning) 

Určete, jak dlouho před automatické restartování zobrazíte-dialogových upozornění na zařízení uživatele o tomto restartování. Hodnoty **15**, **30** nebo **60** minut jsou podporovány.  
 
### <a name="allow-user-to-restart-engaged-restart"></a>Povolit uživatele k restartování (znamenají angažovaní restartování)  

- **Výchozí**: Není nakonfigurováno  
- **Referenční dokumentace ke službě Windows**: *Není k dispozici*  
- **Verze Windows**: Podporované pro Windows 10 verze 1803 nebo novější  

  > [!NOTE]  
  > Windows 10 verze 1809 zavádí další znamenají angažovaní restartování nastavení, umožňující samostatná nastavení pro aktualizace funkcí a kvality. Však spravuje Intune nebude platit nastavení samostatně na různé typy aktualizací. Místo toho Intune platí stejné hodnoty pro aktualizace funkcí a kvality.  

Pokud je nastavena na **vyžaduje**, povolit použití možnosti znamenají angažovaní restartování pro aktualizace Windows 10. Tyto možnosti zapojení uživatele zařízení ke správě při restartování zařízení po instalaci aktualizace, která vyžaduje restartování.  

Další informace o této možnosti najdete v tématu [zapojení restartování](https://docs.microsoft.com/en-us/windows/deployment/update/waas-restart#engaged-restart) v dokumentaci k Windows 10 pro nasazování aktualizací.  

Tato nastavení slouží k řízení, když dojde k akcím znamenají angažovaní restartování.  

- **Přechod uživatelům znamenají angažovaní restartování po automatické restartování (dny)**  
  - **Výchozí**:  Ve výchozím nastavení, to není nakonfigurovaná, ale podporuje hodnotu z **2** k **30**.  
  - **Referenční dokumentace ke službě Windows**: [Update/EngagedRestartTransitionSchedule](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-engagedrestarttransitionschedule)  
  Zadejte, jak dlouho po instalaci aktualizace, dokud se zařízení přejde do zájmu chování při restartu. Po uplynutí nakonfigurovaného počtu dnů uživatelé obdrží výzvu k restartování zařízení.  

- **Odložit restartování znamenají angažovaní připomenutí (dny)**  
  - **Výchozí**:  Ve výchozím nastavení, to není nakonfigurovaná, ale podporuje hodnotu z **1** k **3**.  
  - **Referenční dokumentace ke službě Windows**: [Update/EngagedRestartSnoozeSchedule](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-engagedrestartsnoozeschedule)  
  Zadejte, jak dlouho restartování může být připomenout znovu řádku.  Po skončení období opakovaného se výzva k restartování nabízí znovu. Uživatel může dál připomenout znovu připomenutí, dokud je dosaženo konečného termínu instalace.  

- **Sada konečný termín pro čekající restartování (dny)**  
  - **Výchozí**:  Ve výchozím nastavení, to není nakonfigurovaná, ale podporuje hodnotu z **2** k **30**.  
  - **Referenční dokumentace ke službě Windows**: [Update/EngagedRestartDeadline](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-engagedrestartdeadline)  
  Zadejte maximální počet dní čekání po zájmu chování při restartu začíná předtím, než se zařízení vynutí povinné restartování. Toto restartování nastavení vyzvou uživatele práci uložit

### <a name="delivery-optimization-download-mode"></a>Režim stahování pro optimalizaci doručení  

- **Výchozí**:  Nelze použít
- **Referenční dokumentace ke službě Windows**: *Není k dispozici*

Optimalizace doručení je už nakonfigurovaný jako součást aktualizační kanál Windows 10 v rámci aktualizace softwaru. Optimalizace doručení je nyní nastaveno prostřednictvím konfigurace zařízení. Ale předchozí konfigurace zůstanou dostupné i v konzole. Tyto předchozích konfigurací můžete odebrat úpravou jejich *Nenakonfigurováno*, ale jinak nedaly změnit. 

Aby nedocházelo ke konfliktům mezi původní a nové zásady, najdete v článku [přesouvat existující aktualizační okruhy optimalizace doručení](delivery-optimization-windows.md#move-existing-update-rings-to-delivery-optimization) a poté přesuňte nastavení do profilu optimalizace doručení.


