---
title: Přidání aplikací Win32 do Microsoft Intune
titlesuffix: ''
description: Přečtěte si, jak přidat aplikace Win32 do Microsoft Intune a jak je v této službě spravovat.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c2774a8172eb389742a3fdbf805717b6bc134b43
ms.sourcegitcommit: ca132d509e3c978d18e50eac89e1a1ed7ddb25c1
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/08/2018
ms.locfileid: "48866367"
---
# <a name="intune-standalone---win32-app-management-public-preview"></a>Samostatné využití Intune – správa aplikací Win32 (veřejná verze Preview)

Samostatné využití Intune vám poskytuje širší možnosti správy aplikací Win32. Přestože zákazníci připojení ke cloudu mohou pro správu aplikací Win32 používat nástroj Configuration Manager, zákazníci, kteří používají pouze Intune, mají širší možnosti správy svých obchodních aplikací Win32. Tento dokument poskytuje přehled funkce správy aplikací Win32 a informace o řešení potíží.

## <a name="prerequisites-for-public-preview"></a>Předpoklady pro veřejnou verzi Preview

- Windows 10 verze 1607 nebo novější (Enterprise)
- Klient Windows 10 musí splňovat tyto předpoklady: 
    - musí být připojen ke službě Azure Active Directory (AAD) nebo hybridní službě Azure Active Directory, a
    - musí být zaregistrován v Intune (spravovaný přes MDM).
- Ve veřejné verzi Preview je velikost aplikace Windows omezená na 8 GB na jednu aplikaci. 

> [!NOTE]
> Momentálně testujeme edice Pro a Education verze 1607 systému Windows 10 a budeme rádi, když nám napíšete svůj názor.


## <a name="prepare-the-win32-app-content-for-upload"></a>Příprava obsahu aplikace Win32 pro nahrání

K předběžnému zpracování aplikací Win32 použijte [nástroj pro přípravu nahrání aplikace Win32 do Microsoft Intune](https://github.com/Microsoft/Intune-Win32-App-Packaging-Tool). Nástroj pro vytváření balíčků převede instalační soubory aplikace do formátu *.intunewin*. Nástroj také zjistí některé z atributů, které Intune vyžaduje pro určení stavu instalace aplikace. Po použití tohoto nástroje u složky instalačního programu aplikace budete moci v konzole Intune vytvořit aplikaci Win32.

[Nástroj pro přípravu nahrání aplikace Win32 do Microsoft Intune](https://github.com/Microsoft/Intune-Win32-App-Packaging-Tool) si můžete stáhnout z GitHubu.

### <a name="available-command-line-parameters"></a>Dostupné parametry příkazového řádku 

|    **Parametr příkazového řádku**    |    **Popis**    |
|:------------------------------:|:----------------------------------------------------------:|
|    `-h`     |    Nápověda    |
|    `-c <setup_folder>`     |    Instalační složka pro všechny instalační soubory    |
|   ` -s <setup_file>`     |    Instalační soubor (například *setup.exe* nebo *setup.msi*)    |
|    `-o <output_file>`     |    Výstupní složka pro vygenerovaný soubor *.intunewin*    |
|    `-q`       |    Tichý režim    |

### <a name="example-commands"></a>Příklady příkazů

|    **Příklad příkazu**    |    **Popis**    |
|:-----------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    `IntuneWinAppUtil -h`    |    Tento příkaz zobrazí informace o využití nástroje.    |
|    `IntuneWinAppUtil -c <setup_folder> -s <source_setup_file> -o <output_folder> <-q>`    |    Tento příkaz vygeneruje soubor `.intunewin` ze zadané zdrojové složky a instalačního souboru. U instalačního souboru MSI tento nástroj načte požadované informace pro Intune. Pokud zadáte parametr `-q`, příkaz se spustí v tichém režimu a pokud už výstupní soubor existuje, přepíše se. Pokud výstupní složka ještě neexistuje, automaticky se vytvoří.    |

## <a name="create-assign-and-monitor-a-win32-app"></a>Vytvoření, přiřazení a monitorování aplikace Win32

Stejně jako obchodní aplikaci můžete do Microsoft Intune přidat také aplikaci Win32. Tento typ aplikace obvykle vytváří místní vývojáři nebo třetí strana. Následující kroky obsahují pokyny k přidání aplikace pro Windows do Intune.

### <a name="step-1-specify-the-software-setup-file"></a>Krok 1: Určení instalačního souboru softwaru

1.  Přihlaste se k [portálu Azure Portal](https://portal.azure.com/).
2.  Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3.  V podokně **Intune** vyberte **Klientské aplikace** > **Aplikace** > **Přidat**.
4.  V podokně **Přidat aplikaci** vyberte **Aplikace pro Windows (Win32) – Preview** ze seznamu v rozevírací nabídce.

    ![Snímek obrazovky Přidat aplikaci – rozevírací nabídka typů pro přidání](./media/apps-win32-app-01.png)

### <a name="step-2-upload-the-app-package-file"></a>Krok 2: Nahrání souboru balíčku aplikace

1.  V podokně **Přidat aplikaci** zvolte **Soubor balíčku aplikace** a vyberte soubor. Zobrazí se podokno Soubor balíčku aplikace.

    ![Snímek obrazovky Soubor balíčku aplikace](./media/apps-win32-app-02.png)

2.  V podokně **Soubor balíčku aplikace** vyberte tlačítko Procházet. Potom vyberte instalační soubor Windows s příponou *.intunewin*.
3.  Až to budete mít, vyberte **OK**.

### <a name="step-3-configure-app-information"></a>Krok 3: Konfigurace informací o aplikaci

1.  V podokně **Přidat aplikaci** zvolte **Informace o aplikaci** a nakonfigurujte aplikaci.
2.  V podokně **Informace o aplikaci** nakonfigurujte následující údaje. Některé hodnoty v tomto podokně mohou být vyplněné automaticky.
    - **Název**: Zadejte název aplikace, který se zobrazí na portálu společnosti. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti všechny aplikace.
    - **Popis**: Zadejte popis aplikace. Popis se zobrazí na portálu společnosti.
    - **Vydavatel**: Zadejte název vydavatele aplikace.
    - **Kategorie**: Vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste si vytvořili sami. Díky kategoriím uživatelé aplikaci při procházení portálu společnosti snadněji najdou.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci**: Aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů**: Volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Vývojář**: Volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník**: Volitelně zadejte jméno vlastníka aplikace. Zadat můžete například **Personální oddělení**.
    - **Poznámky**: Zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    - **Logo**: Nahrajte ikonu, která se k aplikaci přidruží. Ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
3.  Až to budete mít, vyberte **OK**.

### <a name="step-4-configure-app-installation-details"></a>Krok 4: Konfigurace podrobností instalace aplikace
1.  V podokně **Přidat aplikaci** vyberte **Program** a nakonfigurujte příkazy pro instalaci a odebrání aplikace.
2.  Přidejte příkazový řádek pro dokončení aplikace, abyste mohli nainstalovat aplikaci. 

    Pokud je například název souboru aplikace **MyApp123**, přidejte toto: `msiexec /i “MyApp123.msi”`.

3.  Přidejte příkazový řádek pro dokončení odinstalace, abyste mohli aplikaci odinstalovat na základě identifikátoru GUID aplikace. 

    Příklad: `msiexec /x “{12345A67-89B0-1234-5678-000001000000}”`

4.  Až to budete mít, vyberte **OK**.

### <a name="step-5-configure-app-requirements"></a>Krok 5: Konfigurace požadavků aplikace

1.  V podokně **Přidat aplikaci** vyberte **Požadavky** a nakonfigurujte požadavky, které zařízení musí splnit, aby bylo možné aplikaci nainstalovat.
2.  V podokně **Požadavky** nakonfigurujte následující údaje. Některé hodnoty v tomto podokně mohou být vyplněné automaticky.
    - **Architektura operačního systému**: Zvolte architektury nutné k instalaci aplikace.
    - **Minimální operační systém**: Vyberte minimální operační systém potřebný k instalaci aplikace.
    - **Požadované místo na disku (MB)**: Volitelně přidejte volné místo na systémové jednotce pro instalaci aplikace.
    - **Požadovaná fyzická paměť (MB)**: Volitelně přidejte fyzickou paměť (RAM) nutnou pro instalaci aplikace.
    - **Minimální požadovaný počet logických procesorů**: Volitelně přidejte minimální počet logických procesorů požadovaných k instalaci aplikace.
    - **Minimální požadovaná rychlost CPU (MHz)**: Volitelně přidejte minimální rychlost procesoru, která se požaduje pro instalaci aplikace.
3.  Až to budete mít, vyberte **OK**.

### <a name="step-6-configure-app-detection-rules"></a>Krok 6: Konfigurace pravidel zjišťování aplikace

1.  V podokně **Přidat aplikaci** vyberte **Pravidla detekce** a nakonfigurujte pravidla pro zjištění přítomnosti aplikace.
2.  V poli **Formát pravidel** vyberte, jak se bude přítomnost aplikace zjišťovat. Pravidla detekce můžete nakonfigurovat ručně, ale můžete použít i vlastní skript, který zjistí přítomnost aplikace. Musíte zvolit alespoň jedno pravidlo detekce. 

    > [!NOTE]
    > V podokně **Pravidla detekce** můžete zvolit přidání více pravidel. Podmínky **všech** pravidel se musí splnit, aby bylo možné aplikaci zjistit.

    - **Ručně nakonfigurovat pravidla zjišťování**: Můžete vybrat jeden z následujících typů pravidel:
        1.  **Instalační služba MSI**: Umožňuje provést ověření na základě kontroly verze MSI. Tuto možnost je možné přidat pouze jednou. Když zvolíte tento typ pravidla, máte dvě nastavení:
            - **Kód produktu Instalační služby MSI**: Přidá platný kód produktu MSI pro aplikaci.
            - **Kontrola verze produktu Instalační služby MSI**: Vyberte **Ano**, pokud chcete kromě kódu produktu MSI ověřit i verzi produktu MSI.
        2.  **Soubor**: Umožňuje provést ověření na základě zjištění, data, verze nebo velikosti souboru nebo složky.
            - **Cesta**: Úplná cesta ke složce obsahující soubor nebo složku, které se mají zjistit.
            - **Soubor nebo složka**: Soubor nebo složka, které se mají zjistit.
            - **Metoda zjišťování**: Vyberte typ metody zjišťování použité k ověření přítomnosti aplikace.
            - **Přidruženo k 32bitové aplikaci na 64bitových klientech**: Vyberte **Ano**, pokud chcete rozbalit všechny proměnné prostředí cesty ve 32bitovém kontextu na 64bitových klientech. Výchozí možnost **Ne** vyberte, pokud chcete rozbalit všechny proměnné cesty ve 64bitovém kontextu na 64bitových klientech. 32bitoví klienti budou vždy používat 32bitový kontext.
            
            **Příklady zjišťování na základě souboru**
            1.  Zkontrolujte, zda soubor existuje.
         
                ![Snímek obrazovky s podoknem pravidla detekce – existence souboru](./media/apps-win32-app-03.png)
        
            2.  Zkontrolujte, zda složka existuje.
         
                ![Snímek obrazovky s podoknem pravidla detekce – existence složky](./media/apps-win32-app-04.png)
        
        3. **Registr**: Umožňuje provést ověření na základě verze, řetězce, celého čísla nebo verze.
            - **Cesta ke klíči**: Úplná cesta k položce registru obsahující hodnotu, která se má zjistit.
            - **Název hodnoty**: Název hodnoty registru, která se má zjistit. Pokud je tato hodnota prázdná, provede se zjišťování u klíče. Hodnota klíče (výchozí) se použije jako hodnota zjišťování v případě, že se metoda zjišťování liší od metody zjišťování existence souboru nebo složky.
            - **Metoda zjišťování**: Vyberte typ metody zjišťování použité k ověření přítomnosti aplikace.
            - **Přidruženo k 32bitové aplikaci na 64bitových klientech**: Vyberte **Ano**, pokud chcete vyhledat 32bitový registr na 64bitových klientech. Výchozí možnost **Ne** vyberte, pokud chcete vyhledat 64bitový registr na 64bitových klientech. 32bitoví klienti budou vždy vyhledávat 32bitový registr.
            
            **Příklady zjišťování na základě registru**
            1.  Zkontrolujte, zda existuje klíč registru.
            
                ![Snímek obrazovky s podoknem pravidla detekce – existence klíče registru](./media/apps-win32-app-05.png)    
            
            2.  Zkontrolujte, zda existuje hodnota registru (**není dostupné ve verzi Preview**).
        
                ![Snímek obrazovky s podoknem pravidla detekce – existence hodnoty registru](./media/apps-win32-app-06.png)    
        
            3.  Zkontrolujte, zda se řetězec hodnoty registru rovná.
        
                ![Snímek obrazovky s podoknem pravidla detekce – řetězec hodnoty registru se rovná](./media/apps-win32-app-07.png)    
     
    - **Použít vlastní skript zjišťování**: Zadejte powershellový skript, který se použije ke zjištění této aplikace. 
    
        1.  **Soubor skriptu**: Vyberte powershellový skript, který zjistí přítomnost aplikace v klientovi. Aplikace se bude považovat za zjištěnou, když skript vrátí ukončovací kód s hodnotou 0 a zapíše řetězcovou hodnotu do výstupu STDOUT.
        2.  **Na 64bitových klientech spouštět skript jako 32bitový proces**: Vyberte **Ano**, pokud chcete spouštět skript pomocí přihlašovacích údajů přihlášeného koncového uživatele. Výchozí možnost **Ne** vyberte, pokud chcete skript spouštět v kontextu systému.
        3.  **Vynutit kontrolu podpisu skriptu**: Vyberte **Ano**, pokud chcete ověřit, že skript je podepsán důvěryhodným vydavatelem. To skriptu umožní spouštět se bez zobrazení upozornění nebo výzev. Skript se bude spouštět odblokovaný. Výchozí možnost **Ne** vyberte, pokud chcete skript spouštět na základě potvrzení koncového uživatele bez ověření podpisu.
    
        Funkce Intune Sidecar zkontroluje výsledky skriptu. Přečte hodnoty, které skript zapsal do standardního streamu výstupu (STDOUT), standardního streamu chyb (STDERR) a do ukončovacího kódu. Pokud kód končí nenulovou hodnotu, skript selže a stav zjišťování aplikace je Nenainstalováno. Pokud ukončovací kód obsahuje nulovou hodnotu a výstup STDOUT obsahuje data, byl stav zjišťování aplikace je Nainstalováno. 
    
        > [!NOTE]
        > Pokud se skript ukončí s hodnotou 0, bylo spuštění skriptu úspěšné. Sekundární výstupní kanál označuje, že aplikace byla zjištěna – data STDOUT označují, že aplikace se v klientovi našla. Konkrétnímu řetězci z výstupu STDOUT se nevěnujeme.
    
3.  Po přidání pravidel vyberte **Přidat** > **OK**.

### <a name="step-7-configure-app-return-codes"></a>Krok 7: Konfigurace návratových kódů aplikace

1.  V podokně **Přidat aplikaci** vyberte **Návratové kódy** a přidejte návratové kódy, které se mají použít buď pro přidání chování při opakování instalace aplikace, nebo pro přidání chování po instalaci. Položky návratových kódů se standardně přidají při vytváření aplikace. Můžete ale přidat další nebo změnit existující návratové kódy. 
2.  V podokně **Návratové kódy** přidejte další návratové kódy nebo změňte existující návratové kódy.
    - **Chyba**: Tato návratová hodnota označuje, že se aplikaci nepodařilo nainstalovat.
    - **Úplné restartování**: Návratový kód pro úplné restartování nepovolí instalaci dalších aplikací Win32 do klienta bez úplného restartování. 
    - **Rychlé restartování**: Návratový kód pro rychlé restartování umožní instalaci další aplikace Win32 bez nutnosti restartovat klienta. Restartování je důležité pro instalaci aktuální aplikace.
    - **Opakovat**: Agent návratového kódu pro opakování se třikrát pokusí aplikaci nainstalovat. Mezi jednotlivými pokusy počká 5 minut. 
    - **Úspěch**: Toto je návratový kód, který označuje, že se aplikace úspěšně nainstalovala.
3.  Jakmile přidáte nebo změníte návratové kódy, vyberte **OK**.

### <a name="step-8-add-the-app"></a>Krok 8: Přidání aplikace

1.  V podokně **Přidat aplikaci** zkontrolujte správnost nakonfigurovaných informací o aplikaci.
2.  Pomocí možnosti **Přidat** nahrajte aplikaci do Intune.

### <a name="step-9-assign-the-app"></a>Krok 9: Přiřazení aplikace

1.  V podokně aplikace vyberte **Přiřazení**.
2.  Vyberte **Přidat skupinu**. Tím se otevře podokno **Přidat skupinu** týkající se aplikace.
3.  Pro konkrétní aplikaci vyberte **typ přiřazení**:
    - **K dispozici zaregistrovaným zařízením**: Uživatelé nainstalují aplikaci z aplikace Portál společnosti nebo z webu Portál společnosti.
    - **Povinné**: Aplikace se nainstaluje na zařízení ve vybraných skupinách.
    - **Odinstalovat**: Aplikace se odinstaluje ze zařízení ve vybraných skupinách.
4.  Vyberte **Zahrnuté skupiny** a přiřaďte skupiny, které budou tuto aplikaci používat.
5.  V podokně **Přiřadit** vyberte **OK**. Tím výběr zahrnutých skupin dokončíte.
6.  Pokud se rozhodnete některé skupiny uživatelů vyloučit, aby nebyly přiřazením aplikace ovlivněné, klikněte na **Vyloučit skupiny**.
7.  V podokně **Přidat skupinu** vyberte **OK**.
8.  V podokně **Přiřazení** aplikace vyberte **Uložit**.

V tomto okamžiku jste dokončili postup přidání aplikace Win32 do Intune. Informace o přiřazení a monitorování aplikace najdete v článku [Přiřazení aplikací do skupin pomocí Microsoft Intune](https://docs.microsoft.com/intune/apps-deploy) a [Monitorování informací a přiřazení aplikace pomocí Microsoft Intune](https://docs.microsoft.com/intune/apps-monitor).

## <a name="install-required-and-available-apps-on-devices"></a>Instalace požadovaných a dostupných aplikací na zařízení

Koncovému uživateli se pro instalaci požadovaných a dostupných aplikací zobrazí informační zprávy Windows. Na následujícím obrázku je znázorněna ukázková informační zpráva, že instalace aplikace se nedokončí, dokud se zařízení nerestartuje. 

![Snímek obrazovky s ukázkovými informačními zprávami Windows pro instalaci aplikace](./media/apps-win32-app-08.png)    

Následující obrázek oznamuje koncovému uživateli, že aplikace provádí změny zařízení.

![Snímek obrazovky s ukázkovým oznámením koncovému uživateli, že aplikace provádí změny zařízení](./media/apps-win32-app-09.png)    

## <a name="troubleshoot-win32-app-issues"></a>Řešení potíží s aplikacemi Win32
Protokoly agenta na klientském počítači se obvykle nachází ve složce `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs`. K zobrazení těchto protokolů můžete využít nástroj `CMTrace.exe`. Nástroj *CMTrace.exe* si můžete stáhnout z umístění uvedeném v článku o [klientských nástrojích SCCM](https://docs.microsoft.com/sccm/core/support/tools). 

![Snímek obrazovky s protokoly agenta](./media/apps-win32-app-10.png)    

### <a name="troubleshooting-areas-to-consider"></a>Oblasti řešení potíží, na které je třeba se zaměřit
- Zkontroluje cílení, abyste měli jistotu, že je agent nainstalovaný na zařízení – aplikace Win32 zacílená na skupinu nebo powershellový skript zacílený na skupinu vytvoří zásady instalace agenta pro skupinu zabezpečení.
- Zkontrolujte verzi operačního systému – Windows 10 1607 a novější.  
- Je uživatel AAD přihlášený ke klientskému počítači?
- Zkontrolujte skladovou položku Windows 10 – Windows 10 S nebo verze Windows s povoleným režimem S nepodporují instalaci pomocí instalační služby MSI.

## <a name="next-steps"></a>Další kroky

- Další informace o přidávání aplikací do Intune najdete v článku [Přidání aplikací do Microsoft Intune](apps-add.md).
