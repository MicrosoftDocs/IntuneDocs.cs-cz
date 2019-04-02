---
title: Řešení problémů s instalací aplikací
titleSuffix: Microsoft Intune
description: Pomocí podokna pro řešení potíží s Microsoft Intune můžete řešit potíže s instalací aplikací.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/19/2019
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 574f509383891ff3e8e0f4c1b04a19832a378829
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2019
ms.locfileid: "58799497"
---
# <a name="troubleshoot-app-installation-issues"></a>Řešení problémů s instalací aplikací

U zařízení spravovaných pomocí Microsoft Intune MDM může občas dojít k chybě instalace. Když k těmto chybám instalace dojde, může být obtížné pochopit, proč k nim došlo nebo je odstranit. Microsoft Intune poskytuje podrobnosti o chybách při instalaci aplikací, díky nimž si operátoři helpdesku a správci Intune poskytující pomoc uživatelům mohou zobrazit informace o aplikacích. Podokno pro řešení potíží v Intune poskytuje podrobnosti o chybě, včetně podrobností o spravovaných aplikacích na zařízení uživatele. V podokně **Spravované aplikace** jsou k dispozici podrobnosti o úplném životním cyklu aplikace pro jednotlivá zařízení. Můžete si zobrazit potíže s instalací, například to, kdy byla aplikace vytvořena, upravena, zacílena a dodána do zařízení. 

## <a name="app-troubleshooting-details"></a>Podrobnosti o řešení problémů s aplikací

Intune poskytuje podrobnosti o řešení potíží s aplikacemi nainstalovanými na konkrétním zařízení uživatele.

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
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

Podrobnosti o chybě při instalaci aplikace označí problém. Tyto podrobnosti můžete použít k určení nejvhodnějších kroků pro vyřešení problému. Další informace o řešení potíží s instalací aplikací najdete v článku popisujícím [chybové kódy pro řešení potíží s instalací aplikací](https://blogs.technet.microsoft.com/intunesupport/2018/05/15/error-codes-for-troubleshooting-app-installation-issues).

> [!Note]  
> Do podokna **řešení potíží** se dostanete také tak, že v prohlížeči přejdete na adresu: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="win32-app-installation-troubleshooting"></a>Řešení potíží instalace aplikace Win32

Vyberte aplikaci Win32, který je nasazený pomocí rozšíření správy Intune. Můžete vybrat **shromažďování protokolů** možnost, pokud se nezdaří instalace aplikace Win32. 

> [!IMPORTANT]
> **Shromažďování protokolů** nebude při aplikaci Win32 byla úspěšně nainstalována na zařízení povolená možnost.<p>Předtím, než může shromažďovat informace o protokolu aplikací Win32, musí na klientovi Windows nainstalované rozšíření správy Intune. Rozšíření správy Intune se nainstaluje při skript prostředí PowerShell nebo aplikace Win32 je nasazená na uživatele nebo skupiny zabezpečení zařízení. Další informace najdete v tématu [rozšíření správy Intune – požadavky](intune-management-extension.md#prerequisites).

### <a name="collect-log-file"></a>Shromažďovat soubory protokolu

Shromažďovat protokoly instalace aplikace Win32, nejdřív postupujte podle kroků uvedených v části [aplikace podrobnosti o řešení problémů](troubleshoot-app-install.md#app-troubleshooting-details). Potom pokračujte následujícími kroky:

1. Klikněte na tlačítko **shromažďování protokolů** možnost **podrobné informace o instalaci** okno.

    <image alt="Win32 app installation details - Collect log option" src="media/troubleshoot-app-install-04.png" width="500" />

2. Zadejte cesty k souborům protokolu názvy souborů k zahájení procesu shromažďování souborů protokolu a klikněte na tlačítko **OK**.
    
    > [!NOTE]
    > Shromažďování protokolů bude trvat méně než dvě hodiny. Podporované typy souborů: *.log, txt, dmp, CAB, ZIP, XML, / v. číslo a .evtl*. Jsou povoleny maximálně 25 cesty k souborům.

3. Až se shromáždí soubory protokolů, můžete vybrat **protokoly** odkaz ke stažení souborů protokolu.

    <image alt="Win32 app log details - Download logs" src="media/troubleshoot-app-install-05.png" width="500" />

    > [!NOTE]
    > Oznámení se zobrazí, která signalizuje úspěch shromažďování protokolů aplikace.

#### <a name="win32-log-collection-requirements"></a>Požadavky na kolekce protokolu Win32

Existují zvláštní požadavky, které musí být následován shromažďovat soubory protokolu:

- Je nutné zadat souborovou cestu úplný protokol. 
- Můžete zadat proměnné prostředí pro shromažďování protokolů, jako je následující:<br>
  *% PROGRAMFILES %, % PROGRAMDATA % VEŘEJNÉ %, % WINDIR %, % TEMP %, % TMP %*
- Pouze přípony souborů jsou povoleny, jako například:<br>
  *.log, txt, dmp, CAB, ZIP, .xml*
- Maximální souboru protokolu určeného k nahrání je 60 MB nebo 25 souborů, podle toho, co nastane dříve. 
- Je povoleno shromažďování protokolů instalace aplikace Win32 pro aplikace, které splňují požadováno, k dispozici a odinstalujte záměr přiřazení aplikace.
- Uložené protokoly se zašifrují do chránit všechny identifikovatelné osobní údaje informace obsažené v protokolech.
- Při otevírání podporu lístky pro chyby aplikace Win32, připojte protokoly související chyby pomocí kroků uvedených výše.

## <a name="app-installation-errors"></a>Chyby instalace aplikací

V následující tabulce jsou uvedeny chybové zprávy s popisem podrobností o chybách instalace v Androidu i iOSu. 

### <a name="android-errors"></a>Chyby v Androidu

|    Chybová zpráva/kód    |    Popis    |
|----------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Aplikaci se nepodařilo nainstalovat. (0xC7D14FB5)    |    Tato chybová zpráva se zobrazí, když Intune nemůže určit hlavní příčinu chyby instalace aplikace pro Android. Android o chybě neposkytl žádné informace.       Tato chyba se vrátí, když se soubor APK úspěšně stáhne, ale při instalaci aplikace dojde k chybě. K této chybě často dochází kvůli chybnému souboru APK, který nelze na zařízení nainstalovat. Možnou příčinou může být skutečnost, že Google Play Protect blokuje instalaci aplikace z důvodů zabezpečení. Další možnou příčinou této chyby může být skutečnost, že zařízení nepodporuje danou aplikaci. Aplikace například vyžaduje rozhraní API verze 21+ a zařízení aktuálně má rozhraní API verze 19.         Intune vrátí tuto chybu pro zařízení DA i KNOX, a i když se může zobrazit oznámení, že uživatelé můžou kliknutím akci zopakovat, v případě problému se souborem APK se akce s chybou už neprovede. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.        |
|    Instalace aplikace byla zrušena, protože instalační soubor (APK) byl odstraněn po stažení, ale ještě před instalací. (0xC7D14FBA)    |    Soubor APK se úspěšně stáhl, ale byl odebrán ze zařízení ještě předtím, než uživatel nainstaloval aplikaci. K tomu může dojít, když mezi stažením a instalací je velký časový rozdíl. Například uživatelem zrušeno původní instalaci, čekalo se a pak jste klikli na oznámení a akci opakujte.         Tato chybová zpráva se vrací jenom ve scénářích DA. Ve scénářích KNOX je možné postupovat bez zobrazení oznámení. Zobrazí se oznámení s možností zopakování akce, takže místo zrušení může uživatel akci potvrdit. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.    |
|    Instalace aplikace byla zrušena, protože během instalace se proces restartoval. (0xC7D14FBB)    |    Zařízení byl restartován během procesu instalace APK, výsledkem je zrušená instalace.        Tato chybová zpráva se vrátí pro zařízení DA i KNOX. Intune zobrazí oznámení, že uživatelé můžou kliknutím akci zopakovat. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.    |
|    Aplikaci se nepovedlo detekovat, i když se její instalace úspěšně dokončila. (0x87D1041C)    |    Uživatel aplikaci explicitně odinstaloval. Tuto chybu nevrací klient. Jedná se o chybu, ke které dojde, pokud se aplikace na jednom místě nainstalovala, ale uživatel ji pak odinstaloval. K této chybě by mělo docházet jenom u požadovaných aplikací. Uživatelé můžou odinstalovat aplikace, které nejsou požadované. K této chybě může dojít jenom v DA. KNOX blokuje odinstalaci spravovaných aplikací.       Při příští synchronizaci se na zařízení znovu zobrazí oznámení s výzvou, aby uživatel provedl instalaci.   Uživatel může toto oznámení ignorovat. Tato chyba se bude dále zobrazovat, dokud uživatel aplikaci nenainstaluje.    |
|    Stažení se nezdařilo z důvodu neznámé chyby. (0xC7D14FB2)    |    Tato chyba se zobrazí, když se stažení nezdaří. K této chybě může běžně docházet při problémech s Wi-Fi nebo při pomalém připojení.       Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení. Intune zobrazí oznámení, že uživatelé můžou kliknutím akci zopakovat. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.    |
|    Stažení se nezdařilo z důvodu neznámé chyby. Při příští synchronizaci zařízení se zásady zkusí uplatnit znovu. (0xC7D15078)    |    Tato chyba se zobrazí, když se stažení nezdaří. K této chybě může běžně docházet při problémech s Wi-Fi nebo při pomalém připojení.       Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení.    |
|    Koncový uživatel zrušil instalaci aplikace. (0xC7D14FB1)    |    Uživatel aplikaci explicitně odinstaloval. Tato chyba je vrácena při instalaci operačního systému Android, že aktivita byla zrušena uživatelem. Uživatel po zobrazení výzvy operačního systému k instalaci stiskl tlačítko Zrušit nebo klikl mimo zobrazenou výzvu.        Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení. Intune zobrazí oznámení, že uživatelé můžou kliknutím akci zopakovat. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.    |
|    Proces stahování souboru se neočekávaně zastavil. (0xC7D15015)    |    Operační systém zastavil proces stahování před jeho dokončením. K této chybě může dojít při nízkém stavu baterie v zařízení nebo když stahování trvá moc dlouho.       Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení. Intune zobrazí oznámení, že uživatelé můžou kliknutím akci zopakovat. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.    |
|    Služba stažení souboru se neočekávaně zastavila. Při příští synchronizaci zařízení se zásady zkusí uplatnit znovu. (0xC7D1507C)    |    Operační systém zastavil proces stahování před jeho dokončením. K této chybě může dojít při nízkém stavu baterie v zařízení nebo když stahování trvá moc dlouho.       Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení.    |

### <a name="ios-errors"></a>Chyby v iOSu

| Chybová zpráva/kód | Popis a řešení potíží se tipy |
|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| (0x87D12906) | Apple MDM agenta vrátila, že instalace příkaz se nezdařil. |
| (0x87D1313C) | Když adresa URL pro stahování aktualizované služby se neodesílají do zařízení se ztratilo připojení k síti. Konkrétně serveru se zadaným názvem hostitele se nenašel. |
| zařízení se systémem iOS je momentálně zaneprázdněn. (0x87D11388) | Zařízení s Iosem byl zaneprázdněn, což vedlo k chybě. |
| Instalace aplikace se nezdařilo. (0x87D13B64) | Došlo k chybě instalace aplikace. K odstranění této chyby jsou potřeba protokoly XCODE. |
| Aplikace je spravovaná, ale vypršela nebo byl odebrán uživatel. (0x87D13B66) | Uživatel explicitně odinstalaci aplikace. Anebo platnost aplikace vypršela, ale nepovedlo se ji stáhnout, nebo detekce aplikace se neshoduje s odpovědí ze zařízení.   Kromě toho mohlo k této chybě dojít kvůli chybě platformy iOS 9.2.2. |
| Aplikace je naplánovaná instalace, ale potřebuje uplatnění kódu k dokončení transakce. (0x87D13B60) | K této chybě obvykle dochází u aplikací iOS Store, které jsou placené aplikace. |
| Aplikace nebyla detekována. Po úspěšném dokončení instalace.   (0x87D1041C) | Proces zjišťování aplikací se neshodují s odpovědí ze zařízení. |
| Uživatel odmítl nabídku na instalaci aplikace. (0x87D13B62) | Během instalace počáteční aplikace uživatele ke kliknutí na zrušit. |
| Uživatel odmítl nabídku na aktualizaci aplikace. (0x87D13B63) | Koncový uživatel ke kliknutí na zrušit během procesu aktualizace. |
| Neznámá chyba (0x87D103E8) | Došlo k chybě instalace neznámých aplikací. Toto je výsledná chyba, kdy ještě jiné chyby došlo k chybě. |
| Aplikace VPP můžete nainstalovat pouze na sdílený iPad (-2016330861). | Aplikace musí získat pomocí programu Apple Volume Purchase Program pro instalaci na sdílený iPad. |
| Nelze instalovat aplikace, pokud je zakázán App Store (-2016330860).  | Pro uživatele k instalaci aplikace musí být povoleno App Store. |
| Nelze najít licence VPP pro aplikaci (-2016330859).  | Zkuste odvolání a opětovné přiřazení licence aplikace. |
| Nelze nainstalovat aplikace pro systém u svého poskytovatele MDM (-2016330858). | Instalace aplikací, které jsou předinstalované v operačním systému iOS není podporovaný scénář. |
| Nelze instalovat aplikace, když je zařízení v režimu ztráty (-2016330857). | Veškeré možnosti použití zařízení je blokováno v režimu ztráty.   Zakážete režim ztráty instalovat aplikace. |
| Nelze instalovat aplikace, když je zařízení v celoobrazovkovém režimu (-2016330856). | Zkuste zařízení přidat do skupiny vyloučení pro zásady Konfigurace celoobrazovkového režimu pro instalaci aplikace. |
| Nelze nainstalovat 32bitové aplikace na tomto zařízení (-2016330852). | Zařízení nepodporuje instalaci 32bitové aplikace. Vyzkoušejte si nasazení 64bitovou verzi aplikace. |
| Uživatel musí přihlásit k aplikaci Store (-2016330855). | Uživatel musí přihlásit k aplikaci Store před instalací aplikace. |
| Neznámý problém. Pokuste se znovu (-2016330854). | Instalace aplikace se nezdařila z neznámého důvodu.   Opakujte akci později. |
| Instalace aplikace se nezdařilo. Intune se pokusí znovu při příštím synchronizuje zařízení (-2016330853). | Instalace aplikace došlo k chybě zařízení. Synchronizace zařízení a zkuste nainstalovat aplikace znovu. |

### <a name="other-installation-errors"></a>Další chyby při instalaci

|    Chybová zpráva/kód    |    Popis    |
|-----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    0x80073CFF, 0x80CF201C (Chyba klienta)    |    Pro instalaci této aplikace musíte mít systém s podporou instalace aplikací bokem. Ujistěte se, že je balíček aplikace podepsaný důvěryhodným podpisem a nainstalovaný na zařízení připojeném k doméně, která má **AllowAllTrustedApps** zásadu nebo zařízení, které má licenci pro zkušební načtení Windows se  **AllowAllTrustedApps** povolenou zásadou. Další informace najdete v tématu [řešení potíží s balení, nasazování a dotazování aplikací pro Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).     |
|    0x80073CF0    |    Balíček se nepodařilo otevřít. Možné příčiny:<ul><li> Balíček není podepsaný.</li><li> Název vydavatele neodpovídá subjektu podpisového certifikátu.</li></ul> Zkontrolujte, **AppxPackagingOM** informace v protokolu událostí. Další informace najdete v tématu [řešení potíží s balení, nasazování a dotazování aplikací pro Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x80073CF3    |    Balíčku se nezdařilo. aktualizace, závislostí nebo konfliktů ověření. Možné příčiny:<ul><li> Příchozí balíček je v konfliktu s nainstalovaným balíčkem.</li><li> Nebyla nalezena zadaná závislost balíčku.</li><li> Balíček nepodporuje správnou architekturu procesoru.</li></ul> Zkontrolujte, **AppXDeployment-Server** informace v protokolu událostí. Další informace najdete v tématu [řešení potíží s balení, nasazování a dotazování aplikací pro Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x80073CFB    |    Zadaný balíček je už nainstalovaný a přeinstalace balíčku je blokován. Tato chyba může zobrazit při instalaci balíčku, který není totožný s balíčkem, který je už nainstalovaný. Potvrďte, že součástí balíčku je i digitální podpis. Pokud se balíček znovu vytvoří nebo znovu podepíše, nebude už tento balíček při bitovém porovnání totožný s dříve nainstalovaným balíčkem. Tuto chybu můžete odstranit jedním ze dvou způsobů:<ul><li> Zvýšit číslo verze aplikace a pak znovu sestavit a znovu podepsat balíček.</li><li> Než budete instalovat nový balíček, odeberte starý balíček pro každého uživatele v systému.</li></ul> Další informace najdete v tématu [řešení potíží s balení, nasazování a dotazování aplikací pro Windows Store](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x87D1041C    |    Instalace aplikace úspěšně proběhla, ale není zjištěna aplikace. Aplikace byla úspěšně nasazena službou Intune a potom byla odinstalována. Mezi důvody pro aplikaci odinstalují patří:<ul><li> Koncový uživatel odinstaluje aplikaci.</li><li> Informace o identitě v balíčku se neshoduje, jaké zařízení hlásí pro chybný aplikace.</li><li>Pro automatických aktualizací souborů MSI verzi produktu se neshoduje s informací o aplikaci po aktualizaci mimo Intune.</li></ul> Dejte uživateli pokyn, aby aplikaci znovu nainstaloval z portálu společnosti. Všimněte si, že požadované aplikace budou automaticky znovu nainstalovány, když zařízení příště připojí.    |

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Řešení problémů s aplikacemi z Microsoft Storu

Informace v tématu [Řešení problémů s vytvářením balíčků, nasazením a dotazy aplikací pro Microsoft Store](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) vám pomůžou s řešením běžných problémů, na které můžete narazit při instalaci aplikací z Microsoft Storu, ať už k ní využíváte službu Intune, nebo jiný nástroj.

## <a name="next-steps"></a>Další postup

- Další informace o řešení potíží s Intune najdete v článku [Použití portálu pro řešení potíží k poskytování pomoci uživatelům ve vaší společnosti](help-desk-operators.md). 
- Zjistěte další informace o známých problémech v Microsoft Intune. Ty najdete v článku [Známé problémy v Microsoft Intune](known-issues.md).
- Potřebujete další pomoc? Přečtěte si téma [Jak získat podporu pro Microsoft Intune](get-support.md).
