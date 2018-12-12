---
title: Řešení problémů s instalací aplikací
titlesuffix: Microsoft Intune
description: Pomocí podokna pro řešení potíží s Microsoft Intune můžete řešit potíže s instalací aplikací.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: cd43bfda69b42fb81a72d520d169fe1785161f65
ms.sourcegitcommit: 0f19bc5c76b7c0835bfd180459f2bbd128eec1c2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/11/2018
ms.locfileid: "53267001"
---
# <a name="troubleshoot-app-installation-issues"></a>Řešení problémů s instalací aplikací

U zařízení spravovaných pomocí Microsoft Intune MDM může občas dojít k chybě instalace. Když k těmto chybám instalace dojde, může být obtížné pochopit, proč k nim došlo nebo je odstranit. Microsoft Intune poskytuje podrobnosti o chybách při instalaci aplikací, díky nimž si operátoři helpdesku a správci Intune poskytující pomoc uživatelům mohou zobrazit informace o aplikacích. Podokno pro řešení potíží v Intune poskytuje podrobnosti o chybě, včetně podrobností o spravovaných aplikacích na zařízení uživatele. V podokně **Spravované aplikace** jsou k dispozici podrobnosti o úplném životním cyklu aplikace pro jednotlivá zařízení. Můžete si zobrazit potíže s instalací, například to, kdy byla aplikace vytvořena, upravena, zacílena a dodána do zařízení. 

## <a name="to-review-app-troubleshooting-details"></a>Kontrola podrobností o řešení potíží s aplikacemi

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

## <a name="app-installation-errors"></a>Chyby instalace aplikací

V následující tabulce jsou uvedeny chybové zprávy s popisem podrobností o chybách instalace v Androidu i iOSu. 

### <a name="android-errors"></a>Chyby v Androidu

|    Chybová zpráva/kód    |    Popis    |
|----------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Aplikaci se nepodařilo nainstalovat. (0xC7D14FB5)    |    Tato chybová zpráva se zobrazí, když Intune nemůže určit hlavní příčinu chyby instalace aplikace pro Android. Android o chybě neposkytl žádné informace.       Tato chyba se vrátí, když se soubor APK úspěšně stáhne, ale při instalaci aplikace dojde k chybě. K této chybě často dochází kvůli chybnému souboru APK, který nelze na zařízení nainstalovat. Možnou příčinou může být skutečnost, že Google Play Protect blokuje instalaci aplikace z důvodů zabezpečení. Další možnou příčinou této chyby může být skutečnost, že zařízení nepodporuje danou aplikaci. Aplikace například vyžaduje rozhraní API verze 21+ a zařízení aktuálně má rozhraní API verze 19.         Intune vrátí tuto chybu pro zařízení DA i KNOX, a i když se může zobrazit oznámení, že uživatelé můžou kliknutím akci zopakovat, v případě problému se souborem APK se akce s chybou už neprovede. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.        |
|    Instalace aplikace se zrušila, protože instalační soubor (APK) se po stažení, ale ještě před instalací, odstranil. (0xC7D14FBA)    |    Soubor APK se úspěšně stáhl, ale byl odebrán ze zařízení ještě předtím, než uživatel nainstaloval aplikaci. K tomu může dojít, když mezi stažením a instalací je velký časový rozdíl. Uživatel například zrušil původní instalaci, počkal a pak klikl na oznámení a akci zopakoval.         Tato chybová zpráva se vrací jenom ve scénářích DA. Ve scénářích KNOX je možné postupovat bez zobrazení oznámení. Zobrazí se oznámení s možností zopakování akce, takže místo zrušení může uživatel akci potvrdit. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.    |
|    Instalace aplikace se zrušila, protože během instalace se proces restartoval. (0xC7D14FBB)    |    Během procesu instalace souboru APK se zařízení restartovalo, takže došlo ke zrušení instalace.        Tato chybová zpráva se vrátí pro zařízení DA i KNOX. Intune zobrazí oznámení, že uživatelé můžou kliknutím akci zopakovat. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.    |
|    Aplikaci se nepovedlo detekovat, i když se její instalace úspěšně dokončila. (0x87D1041C)    |    Uživatel aplikaci explicitně odinstaloval. Tuto chybu nevrací klient. Jedná se o chybu, ke které dojde, pokud se aplikace na jednom místě nainstalovala, ale uživatel ji pak odinstaloval. K této chybě by mělo docházet jenom u požadovaných aplikací. Uživatelé můžou odinstalovat aplikace, které nejsou požadované. K této chybě může dojít jenom v DA. KNOX blokuje odinstalaci spravovaných aplikací.       Při příští synchronizaci se na zařízení znovu zobrazí oznámení s výzvou, aby uživatel provedl instalaci.   Uživatel může toto oznámení ignorovat. Tato chyba se bude dále zobrazovat, dokud uživatel aplikaci nenainstaluje.    |
|    Stažení se nezdařilo z důvodu neznámé chyby. (0xC7D14FB2)    |    Tato chyba se zobrazí, když se stažení nezdaří. K této chybě může běžně docházet při problémech s Wi-Fi nebo při pomalém připojení.       Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení. Intune zobrazí oznámení, že uživatelé můžou kliknutím akci zopakovat. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.    |
|    Stažení se nezdařilo z důvodu neznámé chyby. Při příští synchronizaci zařízení se zásady zkusí uplatnit znovu. (0xC7D15078)    |    Tato chyba se zobrazí, když se stažení nezdaří. K této chybě může běžně docházet při problémech s Wi-Fi nebo při pomalém připojení.       Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení.    |
|    Koncový uživatel zrušil instalaci aplikace. (0xC7D14FB1)    |    Uživatel aplikaci explicitně odinstaloval. Tato chyba se vrátí po zrušení instalační aktivity operačního systému Android uživatelem. Uživatel po zobrazení výzvy operačního systému k instalaci stiskl tlačítko Zrušit nebo klikl mimo zobrazenou výzvu.        Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení. Intune zobrazí oznámení, že uživatelé můžou kliknutím akci zopakovat. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.    |
|    Proces stahování souboru se neočekávaně zastavil. (0xC7D15015)    |    Operační systém zastavil proces stahování před jeho dokončením. K této chybě může dojít při nízkém stavu baterie v zařízení nebo když stahování trvá moc dlouho.       Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení. Intune zobrazí oznámení, že uživatelé můžou kliknutím akci zopakovat. Pokud se jedná o dostupnou aplikaci, je možné oznámení zavřít. Pokud je ale aplikace požadovaná, oznámení nelze zavřít.    |
|    Služba stažení souboru se neočekávaně zastavila. Při příští synchronizaci zařízení se zásady zkusí uplatnit znovu. (0xC7D1507C)    |    Operační systém zastavil proces stahování před jeho dokončením. K této chybě může dojít při nízkém stavu baterie v zařízení nebo když stahování trvá moc dlouho.       Tato chyba se vrací jenom ve scénářích DA. Ve scénářích KNOX se uživateli nezobrazuje výzva k instalaci a je možné postupovat bez zobrazení oznámení.    |

### <a name="ios-errors"></a>Chyby v iOSu

|    Chybová zpráva/kód    |    Popis    |
|:----------------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    (0x87D12906)    |    Agent Apple MDM vrátil oznámení, že instalační příkaz selhal.        |
|    (0x87D1313C)    |    Při odesílání aktualizované adresy URL služby stažení do zařízení došlo ke ztrátě síťového připojení. Konkrétně se nepodařilo najít server s určeným názvem hostitele.    |
|    Zařízení s iOSem je momentálně zaneprázdněné. (0x87D11388)    |    Zařízení s iOSem bylo zaneprázdněné, což způsobilo chybu.    |
|    Aplikaci se nepovedlo nainstalovat. (0x87D13B64)    |    Došlo k chybě instalace aplikace. K odstranění této chyby jsou potřeba protokoly XCODE.    |
|    Aplikace je spravovaná, ale její platnost vypršela, nebo ji odebral uživatel. (0x87D13B66)    |    Uživatel aplikaci explicitně odinstaloval. Anebo platnost aplikace vypršela, ale nepovedlo se ji stáhnout, nebo detekce aplikace se neshoduje s odpovědí ze zařízení.   Kromě toho mohlo k této chybě dojít kvůli chybě platformy iOS 9.2.2.    |
|    Aplikace má naplánovanou instalaci, ale k dokončení transakce potřebuje kód pro uplatnění.   (0x87D13B60)    |    K této chybě obvykle dochází u aplikací pro iOS Store, které jsou placené.     |
|    Aplikaci se nepovedlo detekovat, i když se její instalace úspěšně dokončila. (0x87D1041C)    |    Proces detekce aplikace se neshodoval s odpovědí ze zařízení.    |
|    Uživatel odmítl nabídku na instalaci aplikace. (0x87D13B62)    |    Uživatel během úvodní instalace aplikace klikl na tlačítko Zrušit.    |
|    Uživatel odmítl nabídku na aktualizaci aplikace. (0x87D13B63)    |    Koncový uživatel během procesu aktualizace klikl na tlačítko Zrušit.     |
|    Neznámá chyba (0x87D103E8)    |    Došlo k neznámé chybě instalace aplikace. Tato výsledná chyba se zobrazí, pokud nedošlo k jiným uvedeným chybám.    |

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
