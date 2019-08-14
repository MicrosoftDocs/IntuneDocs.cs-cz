---
title: Řešení problémů s instalací aplikací
titleSuffix: Microsoft Intune
description: Pomocí podokna pro řešení potíží s Microsoft Intune můžete řešit potíže s instalací aplikací.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/25/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b93fc8bc1bddbae8b1b0bde4f8b8815e8052fb51
ms.sourcegitcommit: 2fa20338bd0236884e1f3fde624cf70da89fd254
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/26/2019
ms.locfileid: "68507697"
---
# <a name="troubleshoot-app-installation-issues"></a>Řešení problémů s instalací aplikací

U zařízení spravovaných pomocí Microsoft Intune MDM může občas dojít k chybě instalace. Když k těmto chybám instalace dojde, může být obtížné pochopit, proč k nim došlo nebo je odstranit. Microsoft Intune poskytuje podrobnosti o chybách při instalaci aplikací, díky nimž si operátoři helpdesku a správci Intune poskytující pomoc uživatelům mohou zobrazit informace o aplikacích. Podokno pro řešení potíží v Intune poskytuje podrobnosti o chybě, včetně podrobností o spravovaných aplikacích na zařízení uživatele. V podokně **Spravované aplikace** jsou k dispozici podrobnosti o úplném životním cyklu aplikace pro jednotlivá zařízení. Můžete si zobrazit potíže s instalací, například to, kdy byla aplikace vytvořena, upravena, zacílena a dodána do zařízení. 

## <a name="app-troubleshooting-details"></a>Podrobnosti o řešení potíží s aplikací

Intune poskytuje podrobnosti o řešení potíží s aplikacemi nainstalovanými na konkrétním zařízení uživatele.

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** zvolte **Řešení potíží**.
4. Klikněte na **Vybrat uživatele** a vyberte uživatele, pro kterého chcete řešit potíže. Zobrazí se podokno **Vybrat uživatele**.
5. Vyberte uživatele zadáním jména nebo e-mailové adresy. V dolní části podokna klikněte na **Vybrat**. V podokně **Řešení potíží** se zobrazí informace o řešení potíží pro daného uživatele. 
6. V seznamu **Zařízení** vyberte zařízení, u kterého chcete řešit potíže.
    ![Podokno Řešení potíží služby Intune](media/troubleshoot-app-install-01.png)
7. V podokně vybraného zařízení vyberte **Spravované aplikace**. Zobrazí se seznam spravovaných aplikací.
    ![Podrobnosti o konkrétním zařízení spravovaném pomocí Intune](media/troubleshoot-app-install-02.png)
8. V seznamu vyberte aplikaci, u které sloupec **Stav instalace** označuje chybu.
    ![Vybraná aplikace, u které jsou zobrazeny podrobnosti o chybě instalace.](media/troubleshoot-app-install-03.png)

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
  1. Přejděte na [Azure Active Directory nastavení zařízení](https://portal.azure.com/#blade/Microsoft_AAD_IAM/DevicesMenuBlade/DeviceSettings/menuId).
  2. Poznamenejte si hodnotu nastavenou pro **maximální počet zařízení na uživatele**.
  3. Přejděte na [Azure Active Directory uživatelé](https://portal.azure.com/#blade/Microsoft_AAD_IAM/UsersManagementMenuBlade/AllUsers).
  4. Vyberte ovlivněného uživatele a klikněte na **zařízení**.
  5. Pokud uživatel překročí nastavený limit, pak odstraňte všechny zastaralé záznamy, které už nepotřebujete.
- V případě zařízení se systémem iOS DEP se ujistěte, že je uživatel v okně Přehled zařízení Intune uveden jako **zaregistrovaný uživatelem** . Pokud se zobrazuje NA, pak Nasaďte zásadu konfigurace pro Portál společnosti Intune. Další informace najdete v tématu [Konfigurace aplikace Portál společnosti](https://docs.microsoft.com/intune/app-configuration-policies-use-ios#configure-the-company-portal-app-to-support-ios-dep-devices).

## <a name="win32-app-installation-troubleshooting"></a>Řešení potíží s instalací aplikace Win32

Vyberte aplikaci Win32 nasazenou pomocí rozšíření pro správu Intune. Při neúspěšné instalaci aplikace Win32 můžete vybrat možnost **shromáždit protokoly** . 

> [!IMPORTANT]
> Možnost **shromáždit protokoly** nebude povolena, pokud byla aplikace Win32 úspěšně nainstalována do zařízení.<p>Předtím, než budete moct shromažďovat informace protokolu aplikace Win32, je nutné nainstalovat rozšíření správy Intune na klienta Windows. Rozšíření pro správu Intune se nainstaluje při nasazení skriptu PowerShellu nebo aplikace Win32 do skupiny zabezpečení uživatele nebo zařízení. Další informace najdete v tématu [rozšíření pro správu Intune – předpoklady](intune-management-extension.md#prerequisites).

### <a name="collect-log-file"></a>Shromáždit soubor protokolu

Pokud chcete shromáždit protokoly instalace aplikace Win32, postupujte podle kroků uvedených v části [Podrobnosti o odstraňování potíží s aplikací](troubleshoot-app-install.md#app-troubleshooting-details). Pak pokračujte následujícími kroky:

1. Klikněte na možnost **shromáždit protokoly** v okně **Podrobnosti o instalaci** .

    <image alt="Win32 app installation details - Collect log option" src="media/troubleshoot-app-install-04.png" width="500" />

2. Zadáním cest k souborům s názvy souborů protokolu zahajte proces shromažďování souborů protokolu a klikněte na tlačítko **OK**.
    
    > [!NOTE]
    > Shromažďování protokolů bude trvat méně než dvě hodiny. Podporované typy souborů: *. log,. txt,. dmp,. cab,. zip,. XML,. evtx a. evtl*. Povoluje se maximálně 25 cest k souborům.

3. Po shromáždění souborů protokolu můžete vybrat odkaz **protokoly** ke stažení souborů protokolu.

    <image alt="Win32 app log details - Download logs" src="media/troubleshoot-app-install-05.png" width="500" />

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
- Uložené protokoly jsou zašifrované, aby chránily jakékoli informace PII obsažené v protokolech.
- Při otevírání lístků podpory pro chyby aplikací Win32 připojte související protokoly selhání pomocí výše uvedených kroků.

## <a name="app-installation-errors"></a>Chyby instalace aplikací

V následující tabulce jsou uvedeny chybové zprávy s popisem podrobností o chybách instalace v Androidu i iOSu. 

### <a name="android-errors"></a>Chyby v Androidu

|    Chybová zpráva/kód    |    Popis    |
|----------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Aplikaci se nepodařilo nainstalovat. (0xC7D14FB5)    |    Tato chybová zpráva se zobrazí, když Intune nemůže určit hlavní příčinu chyby instalace aplikace pro Android. Android o chybě neposkytl žádné informace.       Tato chyba se vrátí, když se soubor APK úspěšně stáhne, ale při instalaci aplikace dojde k chybě. K této chybě často dochází kvůli chybnému souboru APK, který nelze na zařízení nainstalovat. Možnou příčinou může být skutečnost, že Google Play Protect blokuje instalaci aplikace z důvodů zabezpečení. Další možnou příčinou této chyby může být skutečnost, že zařízení nepodporuje danou aplikaci. Aplikace například vyžaduje rozhraní API verze 21+ a zařízení aktuálně má rozhraní API verze 19.         Intune vrátí tuto chybu pro zařízení DA i KNOX, a i když se může zobrazit oznámení, že uživatelé můžou kliknutím akci zopakovat, v případě problému se souborem APK se akce s chybou už neprovede. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.        |
|    Instalace aplikace se zrušila, protože instalační soubor (APK) se po stažení, ale před instalací, odstranil. (0xC7D14FBA)    |    Soubor APK se úspěšně stáhl, ale byl odebrán ze zařízení ještě předtím, než uživatel nainstaloval aplikaci. K tomu může dojít, když mezi stažením a instalací je velký časový rozdíl. Například uživatel zrušil původní instalaci, čekal a pak kliknul na oznámení a zkusí to znovu.         Tato chybová zpráva se vrací jenom ve scénářích DA. Ve scénářích KNOX je možné postupovat bez zobrazení oznámení. Zobrazí se oznámení s možností zopakování akce, takže místo zrušení může uživatel akci potvrdit. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.    |
|    Instalace aplikace se zrušila, protože během instalace se proces restartoval. (0xC7D14FBB)    |    Zařízení se restartovalo během procesu instalace APK, což vedlo k zrušené instalaci.        Tato chybová zpráva se vrátí pro zařízení DA i KNOX. Intune zobrazí oznámení, že uživatelé můžou kliknutím akci zopakovat. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.    |
|    Aplikaci se nepovedlo detekovat, i když se její instalace úspěšně dokončila. (0x87D1041C)    |    Uživatel aplikaci explicitně odinstaloval. Tuto chybu nevrací klient. Jedná se o chybu, ke které dojde, pokud se aplikace na jednom místě nainstalovala, ale uživatel ji pak odinstaloval. K této chybě by mělo docházet jenom u požadovaných aplikací. Uživatelé můžou odinstalovat aplikace, které nejsou požadované. K této chybě může dojít jenom v DA. KNOX blokuje odinstalaci spravovaných aplikací.       Při příští synchronizaci se na zařízení znovu zobrazí oznámení s výzvou, aby uživatel provedl instalaci.   Uživatel může toto oznámení ignorovat. Tato chyba se bude dále zobrazovat, dokud uživatel aplikaci nenainstaluje.    |
|    Stažení se nezdařilo z důvodu neznámé chyby. (0xC7D14FB2)    |    Tato chyba se zobrazí, když se stažení nezdaří. K této chybě může běžně docházet při problémech s Wi-Fi nebo při pomalém připojení.       Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení. Intune zobrazí oznámení, že uživatelé můžou kliknutím akci zopakovat. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.    |
|    Stažení se nezdařilo z důvodu neznámé chyby. Při příští synchronizaci zařízení se zásady zkusí uplatnit znovu. (0xC7D15078)    |    Tato chyba se zobrazí, když se stažení nezdaří. K této chybě může běžně docházet při problémech s Wi-Fi nebo při pomalém připojení.       Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení.    |
|    Koncový uživatel zrušil instalaci aplikace. (0xC7D14FB1)    |    Uživatel aplikaci explicitně odinstaloval. Tato chyba se vrátí, když uživatel zruší aktivitu instalace operačního systému Android. Uživatel po zobrazení výzvy operačního systému k instalaci stiskl tlačítko Zrušit nebo klikl mimo zobrazenou výzvu.        Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení. Intune zobrazí oznámení, že uživatelé můžou kliknutím akci zopakovat. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.    |
|    Proces stahování souboru se neočekávaně zastavil. (0xC7D15015)    |    Operační systém zastavil proces stahování před jeho dokončením. K této chybě může dojít při nízkém stavu baterie v zařízení nebo když stahování trvá moc dlouho.       Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení. Intune zobrazí oznámení, že uživatelé můžou kliknutím akci zopakovat. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.    |
|    Služba stažení souboru se neočekávaně zastavila. Při příští synchronizaci zařízení se zásady zkusí uplatnit znovu. (0xC7D1507C)    |    Operační systém zastavil proces stahování před jeho dokončením. K této chybě může dojít při nízkém stavu baterie v zařízení nebo když stahování trvá moc dlouho.       Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení.    |

### <a name="ios-errors"></a>Chyby v iOSu

| Chybová zpráva/kód | Popis a tipy pro řešení potíží |
|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| (0x87D12906) | Agent Apple MDM vrátil selhání instalačního příkazu. |
| (0x87D1313C) | Během odesílání aktualizované adresy URL služby Stažení na zařízení došlo ke ztrátě síťového připojení. Konkrétně se nepodařilo najít server se zadaným názvem hostitele. |
| zařízení s iOS je momentálně zaneprázdněné. (0x87D11388) | Zařízení s iOS bylo zaneprázdněné, což vedlo k chybě. |
| Instalace aplikace se nezdařila. (0x87D13B64) | Došlo k chybě instalace aplikace. K odstranění této chyby jsou potřeba protokoly XCODE. |
| Aplikace je spravovaná, ale její platnost vypršela nebo odebrala uživatel. (0x87D13B66) | Uživatel explicitně odinstaloval aplikaci. Anebo platnost aplikace vypršela, ale nepovedlo se ji stáhnout, nebo detekce aplikace se neshoduje s odpovědí ze zařízení.   Kromě toho mohlo k této chybě dojít kvůli chybě platformy iOS 9.2.2. |
| Aplikace má naplánovanou instalaci, ale k dokončení transakce potřebuje kód pro uplatnění. (0x87D13B60) | K této chybě obvykle dochází u aplikací pro iOS Store, které jsou placené aplikace. |
| Aplikace nebyla po úspěšném dokončení instalace zjištěna.   (0x87D1041C) | Proces detekce aplikace se neshoduje s odpovědí ze zařízení. |
| Uživatel odmítl nabídku na instalaci aplikace. (0x87D13B62) | Při počáteční instalaci aplikace uživatel kliknul na zrušit. |
| Uživatel odmítl nabídku na aktualizaci aplikace. (0x87D13B63) | Koncový uživatel kliknul na zrušit během procesu aktualizace. |
| Neznámá chyba (0x87D103E8) | Došlo k neznámé chybě instalace aplikace. Toto je výsledná chyba v případě, že nedošlo k jiným chybám. |
| Aplikace VPP se dají instalovat jenom na sdíleném iPadu (-2016330861). | Aplikace se musí získat pomocí Apple Volume Purchase Program k instalaci na sdíleném iPadu. |
| Nejde nainstalovat aplikace, když je zakázané App Store (-2016330860).  | Aby uživatel mohl nainstalovat aplikaci, musí být povolený obchod s aplikacemi. |
| Nejde najít licenci VPP pro aplikaci (-2016330859).  | Zkuste odvolat a znovu přiřadit licenci aplikace. |
| Nejde nainstalovat systémové aplikace se zprostředkovatelem MDM (-2016330858). | Instalace aplikací, které jsou předem nainstalované operačním systémem iOS, není podporovaným scénářem. |
| Nejde nainstalovat aplikace, když je zařízení v režimu ztráty (-2016330857). | Veškeré použití zařízení je v režimu ztráty blokované.   Pokud chcete nainstalovat aplikace, zakažte režim ztráty. |
| Nejde nainstalovat aplikace, když je zařízení v celoobrazovkovém režimu (-2016330856). | Pokud chcete nainstalovat aplikace, zkuste toto zařízení přidat do skupiny vyloučení pro zásady konfigurace celoobrazovkového režimu. |
| Na tomto zařízení se nedají nainstalovat 32-bitové aplikace (-2016330852). | Zařízení nepodporuje instalaci 32 aplikací. Zkuste nasadit 64 verzi aplikace. |
| Uživatel se musí přihlásit k obchodu s aplikacemi (-2016330855). | Aby bylo možné aplikaci nainstalovat, musí se uživatel přihlásit do App Storu. |
| Neznámý problém. Zkuste to prosím znovu (-2016330854). | Instalace aplikace se nezdařila z neznámého důvodu.   Opakujte akci později. |
| Instalace aplikace se nezdařila. Intune se to pokusí znovu při příští synchronizaci zařízení (-2016330853). | Při instalaci aplikace došlo k chybě zařízení. Synchronizujte zařízení a zkuste aplikaci znovu nainstalovat. |

### <a name="other-installation-errors"></a>Další chyby instalace

|    Chybová zpráva/kód    |    Popis    |
|-----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    0x80073CFF, 0x80CF201C (Chyba klienta)    |    Pro instalaci této aplikace musíte mít systém s podporou instalace aplikací bokem. Ujistěte se, že je balíček aplikace podepsaný důvěryhodným podpisem a nainstalovaný na zařízení připojeném k doméně, které má povolenou zásadu **AllowAllTrustedApps** , nebo zařízení, které má licenci pro zkušební načtení systému Windows se zásadami **AllowAllTrustedApps** . umožněn. Další informace najdete v tématu [řešení potíží s balíčkem, nasazením a dotazy aplikací pro Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).     |
|    0x80073CF0    |    Balíček se nepodařilo otevřít. Možné příčiny:<ul><li> Balíček je nepodepsaný.</li><li> Název vydavatele neodpovídá subjektu podpisového certifikátu.</li></ul> Informace najdete v protokolu událostí **AppxPackagingOM** . Další informace najdete v tématu [řešení potíží s balíčkem, nasazením a dotazy aplikací pro Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x80073CF3    |    Ověření aktualizace, závislostí nebo konfliktů balíčku se nezdařilo. Možné příčiny:<ul><li> Příchozí balíček je v konfliktu s nainstalovaným balíčkem.</li><li> Zadaná závislost balíčku nebyla nalezena.</li><li> Balíček nepodporuje správnou architekturu procesoru.</li></ul> Informace najdete v protokolu událostí **AppXDeployment-Server** . Další informace najdete v tématu [řešení potíží s balíčkem, nasazením a dotazy aplikací pro Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x80073CFB    |    Zadaný balíček je už nainstalovaný a přeinstalace balíčku je zablokovaná. Tato chyba se může zobrazit při instalaci balíčku, který není totožný s balíčkem, který už je nainstalovaný. Potvrďte, že součástí balíčku je i digitální podpis. Pokud se balíček znovu vytvoří nebo znovu podepíše, nebude už tento balíček při bitovém porovnání totožný s dříve nainstalovaným balíčkem. Tuto chybu můžete odstranit jedním ze dvou způsobů:<ul><li> Zvyšte číslo verze aplikace a pak znovu sestavte a znovu podepište balíček.</li><li> Před instalací nového balíčku Odeberte starý balíček pro každého uživatele v systému.</li></ul> Další informace najdete v tématu [řešení potíží s balíčkem, nasazením a dotazy aplikací pro Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x87D1041C    |    Instalace aplikace úspěšně proběhla, ale není zjištěna aplikace. Aplikace byla úspěšně nasazena službou Intune a následně odinstalována. Mezi důvody pro odinstalování aplikace patří:<ul><li> Koncový uživatel tuto aplikaci neodinstaluje.</li><li> Informace o identitě v balíčku se neshodují se zprávami o zařízení pro špatné aplikace.</li><li>V případě automatických aktualizací MSIs verze produktu neodpovídá informacím aplikace po aktualizaci mimo Intune.</li></ul> Dejte uživateli pokyn, aby aplikaci znovu nainstaloval z portálu společnosti. Všimněte si, že požadované aplikace se znovu nainstalují automaticky při příštím ověření zařízení.    |
|    0x8000FFFF    |    Během instalace došlo k neočekávané chybě. Další informace najdete v protokolech instalace.    |

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Řešení problémů s aplikacemi z Microsoft Storu

Informace v tématu [Řešení problémů s vytvářením balíčků, nasazením a dotazy aplikací pro Microsoft Store](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) vám pomůžou s řešením běžných problémů, na které můžete narazit při instalaci aplikací z Microsoft Storu, ať už k ní využíváte službu Intune, nebo jiný nástroj.

## <a name="app-troubleshoooting-resources"></a>Prostředky troubleshoooting App
- [Nasazení aplikací Visio a Project jako součást nasazení sady Office pro plus](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Deploying-Visio-and-Project-as-part-of-your-Office/ba-p/701795)
- [Proveďte kroky k zajištění, aby se aplikace MSfB nasazené prostřednictvím Intune nainstalovaly ve Windows 10 1903.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Take-Action-to-Ensure-MSfB-Apps-deployed-through/ba-p/658864)
- [Řešení potíží s nasazením aplikací MSI v Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-MSI-App-deployments-in-Microsoft/ba-p/359125)
- [Osvědčené postupy pro distribuci softwaru do Intune Classic Windows PC Agent](https://support.microsoft.com/en-us/help/2583929/best-practices-for-intune-software-distribution-to-windows-pc)

## <a name="next-steps"></a>Další postup

- Další informace o řešení potíží s Intune najdete v článku [Použití portálu pro řešení potíží k poskytování pomoci uživatelům ve vaší společnosti](help-desk-operators.md). 
- Zjistěte další informace o známých problémech v Microsoft Intune. Další informace najdete v tématu [úspěšnost zákazníka](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)v Intune.
- Potřebujete další pomoc? Přečtěte si téma [Jak získat podporu pro Microsoft Intune](get-support.md).
