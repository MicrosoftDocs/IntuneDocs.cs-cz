---
title: Řešení problémů s instalací aplikací
titleSuffix: Microsoft Intune
description: Pomocí podokna pro řešení potíží s Microsoft Intune můžete řešit potíže s instalací aplikací.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4783d24e3fc25583a61f88c2e7375d4eed673186
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563488"
---
# <a name="troubleshoot-app-installation-issues"></a>Řešení problémů s instalací aplikací

U zařízení spravovaných pomocí Microsoft Intune MDM může občas dojít k chybě instalace. Když k těmto chybám instalace dojde, může být obtížné pochopit, proč k nim došlo nebo je odstranit. Microsoft Intune poskytuje podrobnosti o chybách při instalaci aplikací, díky nimž si operátoři helpdesku a správci Intune poskytující pomoc uživatelům mohou zobrazit informace o aplikacích. Podokno pro řešení potíží v Intune poskytuje podrobnosti o chybě, včetně podrobností o spravovaných aplikacích na zařízení uživatele. V podokně **Spravované aplikace** jsou k dispozici podrobnosti o úplném životním cyklu aplikace pro jednotlivá zařízení. Můžete si zobrazit potíže s instalací, například to, kdy byla aplikace vytvořena, upravena, zacílena a dodána do zařízení. 

## <a name="app-troubleshooting-details"></a>Podrobnosti o řešení potíží s aplikací

Intune poskytuje podrobnosti o řešení potíží s aplikacemi nainstalovanými na konkrétním zařízení uživatele.

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Vyberte **řešení potíží + podpora**.
4. Klikněte na **Vybrat uživatele** a vyberte uživatele, pro kterého chcete řešit potíže. Zobrazí se podokno **Vybrat uživatele**.
5. Vyberte uživatele zadáním jména nebo e-mailové adresy. V dolní části podokna klikněte na **Vybrat**. V podokně **Řešení potíží** se zobrazí informace o řešení potíží pro daného uživatele. 
6. V seznamu **Zařízení** vyberte zařízení, u kterého chcete řešit potíže.
    ![Podokno Řešení potíží služby Intune](./media/troubleshoot-app-install/troubleshoot-app-install-01.png)
7. V podokně vybraného zařízení vyberte **Spravované aplikace**. Zobrazí se seznam spravovaných aplikací.
    ![Podrobnosti o konkrétním zařízení spravovaném pomocí Intune](./media/troubleshoot-app-install/troubleshoot-app-install-02.png)
8. V seznamu vyberte aplikaci, u které sloupec **Stav instalace** označuje chybu.
    ![Vybraná aplikace, u které jsou zobrazeny podrobnosti o chybě instalace.](./media/troubleshoot-app-install/troubleshoot-app-install-03.png)

    > [!Note]  
    > Stejná aplikace může být přiřazena k více skupinám, ale s různými zamýšlenými akcemi (záměry) pro aplikaci. Zjištěný záměr pro aplikaci bude například zobrazovat **vyloučeno**, pokud byla aplikace vyloučena pro uživatele během přiřazování aplikace. Další informace najdete v tématu [Řešení konfliktů mezi záměry aplikace](apps-deploy.md#how-conflicts-between-app-intents-are-resolved).<br><br>
    > Pokud dojde k chybě instalace požadované aplikace, vy nebo váš tým technické podpory bude moci synchronizovat zařízení a zopakovat pokus o instalaci.

Podrobnosti o chybě při instalaci aplikace označí problém. Tyto podrobnosti můžete použít k určení nejvhodnějších kroků pro vyřešení problému. Další informace o řešení potíží s instalací aplikací najdete v tématu [chyby při instalaci aplikací](troubleshoot-app-install.md#app-installation-errors).

> [!Note]  
> Do podokna **řešení potíží** se dostanete také tak, že v prohlížeči přejdete na adresu: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="user-group-targeted-app-installation-does-not-reach-device"></a>Instalace cílené aplikace skupiny uživatelů nedosahuje zařízení.
Pokud máte problémy s instalací aplikací, je třeba vzít v úvahu následující akce:
- Pokud se aplikace v Portál společnosti nezobrazí, ujistěte se, že je aplikace nasazená s **dostupným** záměrem a že uživatel přistupuje k Portál společnosti s typem zařízení, který aplikace podporuje.
- Pro zařízení s Windows BYOD musí uživatel do zařízení přidat pracovní účet.
- Ověřte, jestli uživatel překračuje limit zařízení AAD:
  1. Přejděte na [Azure Active Directory nastavení zařízení](https://portal.azure.com/#pane/Microsoft_AAD_IAM/DevicesMenupane/DeviceSettings/menuId).
  2. Poznamenejte si hodnotu nastavenou pro **maximální počet zařízení na uživatele**.
  3. Přejděte na [Azure Active Directory uživatelé](https://portal.azure.com/#pane/Microsoft_AAD_IAM/UsersManagementMenupane/AllUsers).
  4. Vyberte ovlivněného uživatele a klikněte na **zařízení**.
  5. Pokud uživatel překročí nastavený limit, pak odstraňte všechny zastaralé záznamy, které už nepotřebujete.
- V případě zařízení se systémem iOS DEP se ujistěte, že je uživatel v podokně Přehled zařízení Intune uveden jako **zapsaný uživatelem** . Pokud se zobrazuje NA, pak Nasaďte zásadu konfigurace pro Portál společnosti Intune. Další informace najdete v tématu [Konfigurace aplikace Portál společnosti](app-configuration-policies-use-ios.md#configure-the-company-portal-app-to-support-ios-dep-devices).

## <a name="win32-app-installation-troubleshooting"></a>Řešení potíží s instalací aplikace Win32

Vyberte aplikaci Win32 nasazenou pomocí rozšíření pro správu Intune. Při neúspěšné instalaci aplikace Win32 můžete vybrat možnost **shromáždit protokoly** . 

> [!IMPORTANT]
> Možnost **shromáždit protokoly** nebude povolena, pokud byla aplikace Win32 úspěšně nainstalována do zařízení.<p>Předtím, než budete moct shromažďovat informace protokolu aplikace Win32, je nutné nainstalovat rozšíření správy Intune na klienta Windows. Rozšíření pro správu Intune se nainstaluje při nasazení skriptu PowerShellu nebo aplikace Win32 do skupiny zabezpečení uživatele nebo zařízení. Další informace najdete v tématu [rozšíření pro správu Intune – předpoklady](intune-management-extension.md#prerequisites).

### <a name="collect-log-file"></a>Shromáždit soubor protokolu

Pokud chcete shromáždit protokoly instalace aplikace Win32, postupujte podle kroků uvedených v části [Podrobnosti o odstraňování potíží s aplikací](troubleshoot-app-install.md#app-troubleshooting-details). Pak pokračujte následujícími kroky:

1. Klikněte na možnost **shromáždit protokoly** v podokně **Podrobnosti o instalaci** .

    <image alt="Win32 app installation details - Collect log option" src="./media/troubleshoot-app-install/troubleshoot-app-install-04.png" width="500" />

2. Zadáním cest k souborům s názvy souborů protokolu zahajte proces shromažďování souborů protokolu a klikněte na tlačítko **OK**.

    > [!NOTE]
    > Shromažďování protokolů bude trvat méně než dvě hodiny. Podporované typy souborů: *. log,. txt,. dmp,. cab,. zip,. XML,. evtx a. evtl*. Povoluje se maximálně 25 cest k souborům.

3. Po shromáždění souborů protokolu můžete vybrat odkaz **protokoly** ke stažení souborů protokolu.

    <image alt="Win32 app log details - Download logs" src="./media/troubleshoot-app-install/troubleshoot-app-install-05.png" width="500" />

    > [!NOTE]
    > Zobrazí se oznámení o úspěchu shromažďování protokolu aplikace.

#### <a name="win32-log-collection-requirements"></a>Požadavky na shromažďování protokolů Win32

Existují specifické požadavky, které je nutné dodržovat ke shromáždění souborů protokolu:

- Je nutné zadat úplnou cestu k souboru protokolu. 
- Pro shromažďování protokolů můžete zadat proměnné prostředí, například následující:<br>
  *% PROGRAMFILES%,% SLOŽKA PROGRAMDATA%% PUBLIC%,% WINDIR%,% TEMP%,% TMP%*
- Jsou povoleny pouze přesné přípony souborů, například:<br>
  *. log,. txt,. dmp,. cab,. zip,. XML*
- Maximální soubor protokolu k nahrání je 60 MB nebo 25 souborů, podle toho, co nastane dřív. 
- Pro aplikace, které splňují požadovaný, dostupný a odinstalační záměr přiřazení aplikace, je povolená kolekce protokolů instalace aplikace Win32.
- Uložené protokoly jsou zašifrované, aby chránily jakékoli osobní identifikovatelné informace obsažené v protokolech.
- Při otevírání lístků podpory pro chyby aplikací Win32 připojte související protokoly selhání pomocí výše uvedených kroků.

## <a name="app-installation-errors"></a>Chyby instalace aplikací

V následující tabulce jsou uvedeny chybové zprávy s popisem podrobností o chybách instalace v Androidu i iOSu. 

### <a name="android-errors"></a>Chyby v Androidu

V této části se zmiňují Správce zařízení (DA) i registrace Samsung KNOX. Další informace najdete v tématu [registrace Správce zařízení s Androidem](../enrollment/android-enroll-device-administrator.md) a [Automatická registrace zařízení s Androidem pomocí zápisu mobilních zařízení Samsung pro Samsung](../enrollment/android-samsung-knox-mobile-enroll.md). 

| Chybová zpráva/kód | Description |
|---------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Aplikaci se nepovedlo nainstalovat. (0xC7D14FB5) | Tato chybová zpráva se zobrazí, když Intune nemůže určit hlavní příčinu chyby instalace aplikace pro Android. Android o chybě neposkytl žádné informace. Tato chyba se vrátí po úspěšném stažení APK, ale instalace aplikace se nezdařila. K této chybě může často docházet z důvodu chybného souboru APK, který nelze do zařízení nainstalovat. Možnou příčinou může být to, že když Google Play chránit, zablokuje instalaci aplikace kvůli bezpečnostním obavám. Další možnou příčinou této chyby je, když zařízení aplikaci nepodporuje. Například pokud aplikace vyžaduje rozhraní API verze 21 + a zařízení aktuálně má rozhraní API verze 19. Intune vrátí tuto chybu pro zařízení DIRECTACCESS i KNOX, i když se může jednat o oznámení, že uživatelé můžou kliknout a zkusit to znovu, pokud dojde k nějakému problému s APK, nebude se nikdy dál zdařit. Pokud je aplikace dostupnou aplikací, oznámení může být zavřeno. Pokud je ale aplikace požadovaná, oznámení nelze zavřít. |
| Instalace aplikace se zrušila, protože instalační soubor (APK) se po stažení, ale před instalací, odstranil. (0xC7D14FBA) | Stažení APK bylo úspěšné, ale před tím, než uživatel aplikaci nainstaloval, byl soubor odebrán ze zařízení. K tomu může dojít, pokud došlo k velkému rozdílu mezi stažením a instalací. Například uživatel zrušil původní instalaci, čekal a pak kliknul na oznámení a zkusí to znovu. Tato chybová zpráva se vrátí jenom pro scénáře DA. Scénáře KNOX se dají dělat Tichě. Připravujeme oznámení, aby se mohl uživatel přijmout, místo aby mohl operaci zrušit. Pokud je aplikace dostupnou aplikací, oznámení může být zavřeno. Pokud je ale aplikace požadovaná, oznámení nelze zavřít. |
| Instalace aplikace se zrušila, protože během instalace se proces restartoval. (0xC7D14FBB) | Zařízení se restartovalo během procesu instalace APK, což vedlo k zrušené instalaci. Tato chybová zpráva se vrátí pro zařízení DIRECTACCESS i KNOX. Intune prezentuje oznámení, že uživatelé můžou kliknout a zkusit to znovu. Pokud je aplikace dostupnou aplikací, oznámení může být zavřeno. Pokud je ale aplikace požadovaná, oznámení nelze zavřít. |
| Aplikace nebyla po úspěšném dokončení instalace zjištěna. (0x87D1041C) | Uživatel explicitně odinstaloval aplikaci. Tato chyba se nevrací z klienta. Jedná se o chybu vytvořenou při instalaci aplikace na jednom místě, ale uživatel ji odinstaloval. Tato chyba by se měla vyskytovat jenom u požadovaných aplikací. Uživatelé můžou odinstalovat aplikace, které nejsou požadované. K této chybě může dojít pouze v případě DA. KNOX blokuje odinstalaci spravovaných aplikací. Další synchronizace znovu odešle oznámení na zařízení, aby ho uživatel mohl nainstalovat. Uživatel může toto oznámení ignorovat. Tato chyba bude nadále hlášena, dokud uživatel nenainstaluje aplikaci. |
| Stažení se nezdařilo z důvodu neznámé chyby. (0xC7D14FB2) | K této chybě dojde, pokud se stahování nepovede. K této chybě obvykle dochází z důvodu problémů s Wi-Fi nebo pomalým připojením. Tato chyba se vrátí jenom pro scénáře DA. V případě scénářů KNOX není uživatel vyzván k instalaci, a to lze provést v tichém režimu. Intune prezentuje oznámení, že uživatelé můžou kliknout a zkusit to znovu. Pokud je aplikace dostupnou aplikací, oznámení může být zavřeno. Pokud je ale aplikace požadovaná, oznámení nelze zavřít. |
| Stažení se nezdařilo z důvodu neznámé chyby. Při příští synchronizaci zařízení se zásady zopakují. (0xC7D15078) | K této chybě dojde, pokud se stahování nepovede. K této chybě obvykle dochází z důvodu problémů s Wi-Fi nebo pomalým připojením. Tato chyba se vrátí jenom pro scénáře DA. V případě scénářů KNOX není uživatel vyzván k instalaci, a to lze provést v tichém režimu. |
| Koncový uživatel zrušil instalaci aplikace. (0xC7D14FB1) | Uživatel explicitně odinstaloval aplikaci. Tato chyba se vrátí, když uživatel zruší aktivitu instalace operačního systému Android. Uživatel stiskne tlačítko zrušit, když se zobrazí výzva k instalaci operačního systému nebo když se na něj klikne hned. Tato chyba se vrátí jenom pro scénáře DA. V případě scénářů KNOX není uživatel vyzván k instalaci, a to lze provést v tichém režimu. Intune prezentuje oznámení, že uživatelé můžou kliknout a zkusit to znovu. Pokud je aplikace dostupnou aplikací, oznámení může být zavřeno. Pokud je ale aplikace požadovaná, oznámení nelze zavřít. Požádejte uživatele, aby instalaci nezrušil. |
| Proces stahování souboru se neočekávaně zastavil. (0xC7D15015) | Operační systém zastavil proces stahování předtím, než byl dokončen. K této chybě může dojít v případě, že zařízení má nízký stav baterie nebo stahování trvá příliš dlouho. Tato chyba se vrátí jenom pro scénáře DA. V případě scénářů KNOX není uživatel vyzván k instalaci, a to lze provést v tichém režimu. Intune prezentuje oznámení, že uživatelé můžou kliknout a zkusit to znovu. Pokud je aplikace dostupnou aplikací, oznámení může být zavřeno. Pokud je ale aplikace požadovaná, oznámení nelze zavřít. Ujistěte se, že zařízení má spolehlivé síťové připojení.  |
| Služba Stažení souboru se neočekávaně zastavila. Při příští synchronizaci zařízení se zásady zopakují. (0xC7D1507C) | Operační systém ukončil proces stahování před jeho dokončením. K této chybě může dojít v případě, že zařízení má nízký stav baterie nebo stahování trvá příliš dlouho. Tato chyba se vrátí jenom pro scénáře DA. V případě scénářů KNOX není uživatel vyzván k instalaci, a to lze provést v tichém režimu. Ručně synchronizujte zařízení nebo počkejte 24 hodin a ověřte stav. |
| Aplikaci se nepovedlo odinstalovat. (0xc7d14fb8) | Tato chyba je obecná chyba při odinstalaci. Operační systém neurčil, proč se aplikaci nepovedlo odinstalovat. Některé aplikace pro správu nejdou jednoduše odinstalovat. Zkontrolujte, jestli je možné aplikaci odinstalovat ručně a shromažďovat protokoly Portál společnosti, pokud se odinstalace nepovede. |
| Instalační soubor APK aplikace, který se používá pro upgrade, se neshoduje s podpisem aktuální aplikace v zařízení. (0xc7d14fb7) | Operační systém Android má omezení, které vyžaduje, aby podpisový certifikát pro verzi upgradu byl přesně stejný jako certifikát použitý k podepsání stávající verze. Pokud vývojář nemůže použít stejný certifikát k podepsání nové verze, bude nutné odinstalovat existující aplikaci a znovu nasadit novou aplikaci místo upgradu stávající aplikace. |
| Koncový uživatel zrušil instalaci aplikace. (0xc7d14fb9) | Informujte uživatele o přijetí aplikace nasazené v Intune a po zobrazení výzvy aplikaci nainstalujte. |
| Odinstalace aplikace se zrušila, protože během instalace se proces restartoval. (0xc7d14fbc) | Proces instalace aplikace byl ukončen operačním systémem nebo se zařízení restartovalo. Pokud k této chybě dojde znovu, zkuste nainstalovat a shromažďovat protokoly Portál společnosti. |
| Instalační soubor aplikace APK nejde nainstalovat, protože nebyl podepsaný. (0xc7d14fb6) | Android OS standardně vyžaduje, aby byly aplikace podepsané. Před nasazením zajistěte, aby byla aplikace podepsaná. |

### <a name="ios-errors"></a>Chyby v iOSu

| Chybová zpráva/kód | Popis a tipy pro řešení potíží |
|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| (0x87D12906) | Agent Apple MDM vrátil selhání instalačního příkazu. |
| (0x87D1313C) | Během odesílání aktualizované adresy URL služby Stažení na zařízení došlo ke ztrátě síťového připojení. Konkrétně se nepodařilo najít server se zadaným názvem hostitele. |
| zařízení s iOS je momentálně zaneprázdněné. (0x87D11388) | Zařízení s iOS bylo zaneprázdněné, což vedlo k chybě. Zařízení bylo uzamčené. Uživatel musí zařízení odemknout, aby se nainstalovala aplikace. |
| Instalace aplikace se nezdařila. (0x87D13B64) | Došlo k chybě instalace aplikace. k odstranění této chyby je potřeba protokol konzoly iOS. |
| Aplikace je spravovaná, ale její platnost vypršela nebo odebrala uživatel. (0x87D13B66) | Buď uživatel explicitně odinstaloval aplikaci, nebo vypršela platnost aplikace, ale stahování se nepovedlo, nebo se detekce aplikace neshoduje s odpovědí ze zařízení. Kromě toho mohlo k této chybě dojít kvůli chybě platformy iOS 9.2.2. |
| Aplikace má naplánovanou instalaci, ale k dokončení transakce potřebuje kód pro uplatnění. (0x87D13B60) | K této chybě obvykle dochází u aplikací pro iOS Store, které jsou placené aplikace. |
| Aplikace nebyla po úspěšném dokončení instalace zjištěna. (0x87D1041C) | Proces detekce aplikace se neshoduje s odpovědí ze zařízení. |
| Uživatel odmítl nabídku na instalaci aplikace. (0x87D13B62) | Při počáteční instalaci aplikace uživatel kliknul na zrušit. Požádejte uživatele, aby požadavek na instalaci přijal příště. |
| Uživatel odmítl nabídku na aktualizaci aplikace. (0x87D13B63) | Koncový uživatel kliknul na zrušit během procesu aktualizace. Nasaďte podle potřeby nebo dodáte uživateli souhlas s výzvou k upgradu. |
| Neznámá chyba (0x87D103E8) | Došlo k neznámé chybě instalace aplikace. Toto je výsledná chyba v případě, že nedošlo k jiným chybám. |
| Aplikace VPP se dají instalovat jenom na sdíleném iPadu (-2016330861). | Aplikace se musí získat pomocí Apple Volume Purchase Program k instalaci na sdíleném iPadu. |
| Nejde nainstalovat aplikace, když je zakázané App Store (-2016330860). | Aby uživatel mohl nainstalovat aplikaci, musí být povolený obchod s aplikacemi. |
| Nejde najít licenci VPP pro aplikaci (-2016330859). | Zkuste odvolat a znovu přiřadit licenci aplikace. |
| Nejde nainstalovat systémové aplikace se zprostředkovatelem MDM (-2016330858). | Instalace aplikací, které jsou předem nainstalované operačním systémem iOS, není podporovaným scénářem. |
| Nejde nainstalovat aplikace, když je zařízení v režimu ztráty (-2016330857). | Veškeré použití zařízení je v režimu ztráty blokované. Pokud chcete nainstalovat aplikace, zakažte režim ztráty. |
| Nejde nainstalovat aplikace, když je zařízení v celoobrazovkovém režimu (-2016330856). | Pokud chcete nainstalovat aplikace, zkuste toto zařízení přidat do skupiny vyloučení pro zásady konfigurace celoobrazovkového režimu. |
| Na tomto zařízení se nedají nainstalovat 32-bitové aplikace (-2016330852). | Zařízení nepodporuje instalaci 32 aplikací. Zkuste nasadit 64 verzi aplikace. |
| Uživatel se musí přihlásit k obchodu s aplikacemi (-2016330855). | Aby bylo možné aplikaci nainstalovat, musí se uživatel přihlásit do App Storu. |
| Neznámý problém. Zkuste to prosím znovu (-2016330854). | Instalace aplikace se nezdařila z neznámého důvodu. Opakujte akci později. |
| Instalace aplikace se nezdařila. Intune se to pokusí znovu při příští synchronizaci zařízení (-2016330853). | Při instalaci aplikace došlo k chybě zařízení. Synchronizujte zařízení a zkuste aplikaci znovu nainstalovat. |
| Přiřazení licence se nezdařilo. Chyba Apple: nejsou zbývající licence VPP (0x87d13b7e) | Toto chování je záměrné. Pokud to chcete vyřešit, Zakupte další licence VPP nebo licence od uživatelů, které už nejsou cílené. |
| Chyba instalace aplikace 12024: Neznámá příčina (0x87d13b6e) | Společnost Apple ještě nedali dostatek informací, abychom zjistili, proč se instalace nezdařila. Nic k sestavování. |
| Nejsou k dispozici požadované zásady konfigurace aplikace, zajistěte, aby byly zásady cílené na stejné skupiny. (0x87d13b7f) | Aplikace vyžaduje konfiguraci aplikace, ale necílí na žádnou konfiguraci aplikace. Správce by měl mít jistotu, že skupiny, na které je aplikace cílena, má taky požadovanou konfiguraci aplikace, na kterou se cílí do skupin. |
| Licencování VPP zařízení se dá použít jenom pro zařízení se systémem iOS 9.0 +. (0x87d13b69) | Upgradovat ovlivněná zařízení se systémem iOS na iOS 9.0 +. |
| Aplikace je nainstalována na zařízení, ale není spravována. (0x87d13b8f) | K této chybě dochází pouze v obchodních aplikacích. Aplikace se nainstalovala mimo Intune. Pokud chcete tuto chybu vyřešit, odinstalujte aplikaci ze zařízení. Až dojde k dalšímu synchronizaci zařízení, zařízení by mělo aplikaci nainstalovat z Intune. |
| Uživatel odmítl správu aplikací (0x87d13b68). | Požádejte uživatele, aby přijal správu aplikací. |
| Neznámá chyba. (0x87d1279d) | K této chybě dochází v aplikacích pro iOS Store, ale scénář chyby je neznámý. |
| Poslední verzi aplikace se nepovedlo aktualizovat ze starší verze. (0x87D13B9D) | Tato chybová zpráva se zobrazí, pokud je aplikace nainstalovaná a spravovaná, ale má na zařízení nesprávnou verzi. Tato situace zahrnuje situaci, kdy zařízení obdrželo příkaz k aktualizaci aplikace, ale nová verze ještě není nainstalovaná a nahlášená zpět. Tato chyba bude hlášena při prvním vrácení se změnami zařízení po nasazení upgradu a provede se, dokud zařízení neoznámí, že je nainstalována nová verze, nebo dojde k chybě z důvodu jiné chyby.  |


### <a name="other-installation-errors"></a>Další chyby instalace

|  Chybová zpráva/kód  |  Description  |
|-----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  0x80073CFF, 0x80CF201C (Chyba klienta)  |  Pro instalaci této aplikace musíte mít systém s podporou instalace aplikací bokem. Ujistěte se, že je balíček aplikace podepsaný důvěryhodným podpisem a nainstalovaný na zařízení připojeném k doméně, které má povolenou zásadu **AllowAllTrustedApps** , nebo zařízení, které má licenci pro zkušební načtení systému Windows s povolenou zásadou **AllowAllTrustedApps** . Další informace najdete v tématu [řešení potíží s balíčkem, nasazením a dotazy aplikací pro Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).   |
|  0x80073CF0  |  Balíček se nepodařilo otevřít. Možné příčiny:<ul><li> Balíček je nepodepsaný.</li><li> Název vydavatele neodpovídá subjektu podpisového certifikátu.</li></ul> Informace najdete v protokolu událostí **AppxPackagingOM** . Další informace najdete v tématu [řešení potíží s balíčkem, nasazením a dotazy aplikací pro Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).  |
|  0x80073CF3  |  Ověření aktualizace, závislostí nebo konfliktů balíčku se nezdařilo. Možné příčiny:<ul><li> Příchozí balíček je v konfliktu s nainstalovaným balíčkem.</li><li> Zadaná závislost balíčku nebyla nalezena.</li><li> Balíček nepodporuje správnou architekturu procesoru.</li></ul> Informace najdete v protokolu událostí **AppXDeployment-Server** . Další informace najdete v tématu [řešení potíží s balíčkem, nasazením a dotazy aplikací pro Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).  |
|  0x80073CFB  |  Zadaný balíček je už nainstalovaný a přeinstalace balíčku je zablokovaná. Tato chyba se může zobrazit při instalaci balíčku, který není totožný s balíčkem, který už je nainstalovaný. Potvrďte, že součástí balíčku je i digitální podpis. Pokud se balíček znovu vytvoří nebo znovu podepíše, nebude už tento balíček při bitovém porovnání totožný s dříve nainstalovaným balíčkem. Tuto chybu můžete odstranit jedním ze dvou způsobů:<ul><li> Zvyšte číslo verze aplikace a pak znovu sestavte a znovu podepište balíček.</li><li> Před instalací nového balíčku Odeberte starý balíček pro každého uživatele v systému.</li></ul> Další informace najdete v tématu [řešení potíží s balíčkem, nasazením a dotazy aplikací pro Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).  |
|  0x87D1041C  |  Instalace aplikace úspěšně proběhla, ale není zjištěna aplikace. Aplikace byla úspěšně nasazena službou Intune a následně odinstalována. Mezi důvody pro odinstalování aplikace patří:<ul><li> Koncový uživatel tuto aplikaci neodinstaluje.</li><li> Informace o identitě v balíčku se neshodují se zprávami o zařízení pro špatné aplikace.</li><li>V případě automatických aktualizací MSIs verze produktu neodpovídá informacím aplikace po aktualizaci mimo Intune.</li></ul> Dejte uživateli pokyn, aby aplikaci znovu nainstaloval z portálu společnosti. Všimněte si, že požadované aplikace se znovu nainstalují automaticky při příštím ověření zařízení.  |
|  0x8000FFFF  |  Během instalace došlo k neočekávané chybě. Další informace najdete v protokolech instalace.  |

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Řešení problémů s aplikacemi z Microsoft Storu

Informace v tématu [Řešení problémů s vytvářením balíčků, nasazením a dotazy aplikací pro Microsoft Store](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) vám pomůžou s řešením běžných problémů, na které můžete narazit při instalaci aplikací z Microsoft Storu, ať už k ní využíváte službu Intune, nebo jiný nástroj.

## <a name="app-troubleshooting-resources"></a>Prostředky pro řešení potíží s aplikací
- [Nasazení aplikací Visio a Project jako součást nasazení sady Office pro plus](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Deploying-Visio-and-Project-as-part-of-your-Office/ba-p/701795)
- [Proveďte kroky k zajištění, aby se aplikace MSfB nasazené prostřednictvím Intune nainstalovaly ve Windows 10 1903.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Take-Action-to-Ensure-MSfB-Apps-deployed-through/ba-p/658864)
- [Řešení potíží s nasazením aplikací MSI v Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-MSI-App-deployments-in-Microsoft/ba-p/359125)
- [Osvědčené postupy pro distribuci softwaru do Intune Classic Windows PC Agent](https://support.microsoft.com/en-us/help/2583929/best-practices-for-intune-software-distribution-to-windows-pc)

## <a name="next-steps"></a>Další kroky

- Další informace o řešení potíží s Intune najdete v článku [Použití portálu pro řešení potíží k poskytování pomoci uživatelům ve vaší společnosti](../fundamentals/help-desk-operators.md). 
- Zjistěte další informace o známých problémech v Microsoft Intune. Další informace najdete v tématu [úspěšnost zákazníka v Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess).
- Potřebujete další pomoc? Přečtěte si téma [Jak získat podporu pro Microsoft Intune](../fundamentals/get-support.md).
