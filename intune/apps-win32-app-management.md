---
title: Přidání a přiřazení aplikací Win32 do Microsoft Intune
titleSuffix: ''
description: Zjistěte, jak přidávat, přiřazovat a spravovat aplikace Win32 v Microsoft Intune. Toto téma poskytuje přehled funkcí pro poskytování a správu aplikací Win32 přes Intune a informace o řešení potíží s těmito aplikacemi.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/15/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8c2cac99ba45ccd91629e6db32d91735d90d706e
ms.sourcegitcommit: 6d6f43d69462f7f8fadc421c4ba566dc6ec20c36
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62426149"
---
# <a name="intune-standalone---win32-app-management"></a>Samostatnou službu Intune – Správa aplikací Win32

[Samostatnou službu Intune](mdm-authority-set.md) teď umožňuje větší aplikace Win32 možnosti správy. Přestože zákazníci připojení ke cloudu mohou pro správu aplikací Win32 používat nástroj Configuration Manager, zákazníci, kteří používají pouze Intune, mají širší možnosti správy svých obchodních aplikací Win32. Toto téma poskytuje přehled funkce správy aplikací Win32 v Intune a informace o řešení potíží.

> [!NOTE]
> Tato funkce správy aplikací podporuje obě architektury 32bitová verze a 64bitová verze operačního systému pro aplikace Windows.

## <a name="prerequisites"></a>Požadavky

Pokud chcete použít správu aplikací Win32, ujistěte se, že splňujete následující kritéria:

- Windows 10 verze 1607 nebo novější (Enterprise, Pro a vzdělávání verze)
- Klient Windows 10 musí splňovat tyto předpoklady: 
    - Zařízení musí být připojená k Azure AD a automatické zaregistrovaná. Rozšíření správy Intune podporuje Azure AD připojí, hybridní připojených k doméně, se podporují zařízení zaregistrovaná zásad skupiny. 
    > [!NOTE]
    > Pro zásady skupiny zaregistrovaná scénář – koncový uživatel používá místní uživatelský účet aad připojte se k jejich zařízení s Windows 10. Uživatel musí přihlásit pomocí svého účtu AAD uživatele zařízení a registrace v Intune. Intune se nainstalovat rozšíření správy Intune na zařízení, pokud Powershellový skript nebo aplikace Win32 je zacílený na uživatele nebo zařízení.
- Velikost aplikace Windows je omezené na 8 GB na aplikaci.

## <a name="prepare-the-win32-app-content-for-upload"></a>Příprava obsahu aplikace Win32 pro nahrání

Použití [Microsoft Win32 obsahu Prep Tool](https://go.microsoft.com/fwlink/?linkid=2065730) předběžně zpracovat klasické Windows (Win32) aplikace. Tento nástroj převede instalačních souborů aplikace do *.intunewin* formátu. Nástroj zjistí také některé atributy, které vyžaduje služba Intune k určení stavu instalace aplikace. Po použití tohoto nástroje ve složce instalační program aplikace, bude možné k vytvoření aplikace Win32 v konzole Intune.

> [!IMPORTANT]
> [Microsoft Win32 obsahu Prep Tool](https://go.microsoft.com/fwlink/?linkid=2065730) zips všechny soubory a podsložky, když vytváří *.intunewin* souboru. Rozhodně buďte Microsoft Win32 obsahu Prep Tool nezávisle na instalační soubory a složky, tak, aby nezadáte, nástroj nebo jiné nepotřebné soubory a složky ve vaší *.intunewin* souboru.

Můžete stáhnout [Microsoft Win32 obsahu Prep Tool](https://go.microsoft.com/fwlink/?linkid=2065730) z Githubu jako soubor zip. Soubor ZIP obsahuje složku s názvem **Microsoft-Win32-Content-Prep-Tool-master**. Složka obsahuje nástroj pro přípravu, licence, souboru readme a poznámky k verzi. 

### <a name="process-flow-to-create-intunewin-file"></a>Tok procesu pro vytvoření souboru .intunewin

   ![Tok procesu pro vytvoření souboru .intunewin](./media/prepare-win32-app.svg)

### <a name="run-the-microsoft-win32-content-prep-tool"></a>Spusťte nástroj Microsoft Win32 obsahu přípravu

Pokud spustíte `IntuneWinAppUtil.exe` z příkazového okna bez parametrů, vás provedou nástroje vám umožní zadat požadované parametry krok za krokem. Nebo můžete přidat parametry do příkazu založené na následující parametry příkazového řádku k dispozici.

### <a name="available-command-line-parameters"></a>Dostupné parametry příkazového řádku 

|    **Parametr příkazového řádku**    |    **Popis**    |
|:------------------------------:|:----------------------------------------------------------:|
|    `-h`     |    Help    |
|    `-c <setup_folder>`     |    Složka pro všechny instalační soubory. Všechny soubory v této složce se zkomprimují do *.intunewin* souboru.    |
|   ` -s <setup_file>`     |    Instalační soubor (například *setup.exe* nebo *setup.msi*)    |
|    `-o <output_folder>`     |    Výstupní složka pro vygenerovaný soubor *.intunewin*    |
|    `-q`       |    Tichý režim    |

### <a name="example-commands"></a>Příklady příkazů

|    **Příklad příkazu**    |    **Popis**    |
|:-----------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    `IntuneWinAppUtil -h`    |    Tento příkaz zobrazí informace o využití nástroje.    |
|    `IntuneWinAppUtil -c c:\testapp\v1.0 -s c:\testapp\v1.0\setup.exe -o c:\testappoutput\v1.0 -q`    |    Tento příkaz vygeneruje soubor `.intunewin` ze zadané zdrojové složky a instalačního souboru. U instalačního souboru MSI tento nástroj načte požadované informace pro Intune. Pokud zadáte parametr `-q`, příkaz se spustí v tichém režimu a pokud už výstupní soubor existuje, přepíše se. Pokud výstupní složka ještě neexistuje, automaticky se vytvoří.    |

Při generování *.intunewin* souboru, umístěte všechny soubory, budete muset odkaz do podsložky složky instalace. Potom použijte relativní cesty tak, aby odkazovaly na konkrétní soubor, který potřebujete. Příklad:

**Složky zdroje instalace:** *c:\testapp\v1.0*<br>
**License file:** *c:\testapp\v1.0\licenses\license.txt*

Odkazovat *license.txt* soubor pomocí relativní cesty *licenses\license.txt*.

## <a name="create-assign-and-monitor-a-win32-app"></a>Vytvoření, přiřazení a monitorování aplikace Win32

Stejně jako obchodní aplikaci můžete do Microsoft Intune přidat také aplikaci Win32. Tento typ aplikace obvykle vytváří místní vývojáři nebo třetí strana. 

### <a name="process-flow-to-add-a-win32-app-to-intune"></a>Tok procesu do Intune přidat aplikace Win32

   ![Tok procesu do Intune přidat aplikace Win32](./media/add-win32-app.svg)

### <a name="add-a-win32-app-to-intune"></a>Přidat aplikaci Win32 do Intune

Následující kroky obsahují pokyny k přidání aplikace pro Windows do Intune.

### <a name="step-1-specify-the-software-setup-file"></a>Krok 1: Určení instalačního souboru softwaru

1.  Přihlaste se k webu [Azure Portal](https://portal.azure.com/).
2.  Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3.  V podokně **Intune** vyberte **Klientské aplikace** > **Aplikace** > **Přidat**.
4.  V **přidat** podokno aplikace, vyberte **aplikace Windows (Win32)** ze zadané rozevíracího seznamu.

    ![Snímek obrazovky okna Přidat aplikaci – přidat typ rozevírací seznam pole](./media/apps-win32-app-01.png)

### <a name="step-2-upload-the-app-package-file"></a>Krok 2: Nahrát soubor balíčku aplikace

1.  V podokně **Přidat aplikaci** zvolte **Soubor balíčku aplikace** a vyberte soubor. Zobrazí se podokno Soubor balíčku aplikace.

    ![Snímek obrazovky okna soubor balíčku aplikace](./media/apps-win32-app-02.png)

2.  V podokně **Soubor balíčku aplikace** vyberte tlačítko Procházet. Potom vyberte instalační soubor Windows s příponou *.intunewin*.

    > [!IMPORTANT]
    > Nezapomeňte použít nejnovější verzi nástroje Microsoft Win32 obsahu Prep Tool. Pokud nepoužíváte nejnovější verzi, zobrazí se upozornění, že se aplikace zabalila ve starší verzi nástroje Příprava obsahu pro Microsoft Win32. 

3.  Až to budete mít, vyberte **OK**.

### <a name="step-3-configure-app-information"></a>Krok 3: Konfigurace informací o aplikaci

1.  V podokně **Přidat aplikaci** zvolte **Informace o aplikaci** a nakonfigurujte aplikaci.
2.  V podokně **Informace o aplikaci** nakonfigurujte následující údaje. Některé hodnoty v tomto podokně mohou být vyplněné automaticky.
    - **Název**: Zadejte název aplikace, zobrazí se v aplikaci portál společnosti. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti všechny aplikace.
    - **Popis**: Zadejte popis aplikace. Popis se zobrazí na portálu společnosti.
    - **Publikování**r: Zadejte název vydavatele aplikace.
    - **Kategorie**: Vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste vytvořili. Díky kategoriím uživatelé aplikaci při procházení portálu společnosti snadněji najdou.
    - **Zobrazit tuto aplikaci jako doporučenou aplikaci portálu společnosti**: Když uživatelé hledají aplikace, zobrazí se aplikace výrazně na hlavní stránce portálu společnosti.
    - **Adresa URL informací**: Volitelně zadejte adresu URL webu, který obsahuje informace o aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Soukromá adresa URL**: Volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů pro aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Pro vývojáře**: Volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník**: Volitelně zadejte jméno vlastníka této aplikace. Zadat můžete například **Personální oddělení**.
    - **Poznámky k**: Zadejte jakékoli poznámky, které chcete přidružit k této aplikaci.
    - **Logo**: Nahrajte ikonu, která je spojená s aplikací. Ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
3.  Až to budete mít, vyberte **OK**.

### <a name="step-4-configure-app-installation-details"></a>Krok 4: Nakonfigurujte podrobnosti instalace aplikace
1.  V podokně **Přidat aplikaci** vyberte **Program** a nakonfigurujte příkazy pro instalaci a odebrání aplikace.
2.  Přidejte příkazový řádek pro dokončení aplikace, abyste mohli nainstalovat aplikaci. 

    Například, pokud je vaše aplikace filename **MyApp123**, přidejte následující:<br>
    `msiexec /p “MyApp123.msp”`<p>
    A pokud je aplikace `ApplicationName.exe`, příkaz bude název aplikace, za nímž následuje argumenty příkazu (přepínače) podporované tímto balíčkem. <br>Příklad:<br>
    `ApplicationName.exe /quite`<br>
    Ve výše uvedeném příkazu `ApplicaitonName.exe` balíček podporuje `/quite` příkaz argument.<p> Pro konkrétní argumentů podporovaných balíčku aplikace obraťte se na dodavatele aplikace.

3.  Přidejte příkazový řádek pro dokončení odinstalace, abyste mohli aplikaci odinstalovat na základě identifikátoru GUID aplikace. 

    Příklad: `msiexec /x “{12345A67-89B0-1234-5678-000001000000}”`

    > [!NOTE]
    > Aplikaci Win32 můžete nakonfigurovat tak, aby se nainstalovala v kontextu **uživatele** nebo **systému**. Kontext **Uživatel** se vztahuje pouze k danému uživateli. Kontext **Systém** se vztahuje ke všem uživatelům zařízení s Windows 10.
    >
    > Koncoví uživatelé nemusí být kvůli instalaci aplikací Win32 přihlášení k zařízení.

4.  Až to budete mít, vyberte **OK**.

### <a name="step-5-configure-app-requirements"></a>Krok 5: Konfigurace požadavků na aplikaci

1.  V podokně **Přidat aplikaci** vyberte **Požadavky** a nakonfigurujte požadavky, které zařízení musí splnit, aby bylo možné aplikaci nainstalovat.
2.  V **přidat pravidlo požadavku** podokno, nakonfigurujte následující údaje. Některé hodnoty v tomto podokně mohou být vyplněné automaticky.
    - **Architektura operačního systému**: Zvolte, že architektury potřebujete k instalaci aplikace.
    - **Minimální verzi operačního systému**: Vyberte minimální verzi operačního systému, které jsou potřebné k instalaci aplikace.
    - **Místo na disku vyžadované (MB)**: Volitelně můžete přidáte volné místo na disku potřebné k instalaci aplikace na systémovou jednotku.
    - **Vyžaduje fyzické paměti (MB)**: Volitelně můžete přidáte fyzické paměti (RAM) požadovaná k instalaci aplikace.
    - **Minimální počet logických procesorů potřebný**: Volitelně můžete přidáte minimální počet logických procesorů potřebný k instalaci aplikace.
    - **Minimální rychlost procesoru požadované (MHz)**: Volitelně můžete přidáte minimální rychlost procesoru, které jsou potřebné k instalaci aplikace.

3. Klikněte na tlačítko **přidat** zobrazíte **přidat pravidlo požadavku** okno Konfigurace pravidel další požadavek. Vyberte **typ požadavku** zvolit typ pravidlo, které budete používat k určení, jak je požadavek ověřen. Pravidla požadavků můžete podle informací o systému souboru, hodnoty registru nebo skripty prostředí PowerShell. 
    - **Soubor**: Při výběru **souboru** jako **typ požadavku**, pravidlo požadavku musí odhalit souboru nebo složky, datum, verze nebo velikosti. 
        - **Cesta**: Úplná cesta ke složce obsahující soubor nebo složku, které se mají zjistit.
        - **Soubor nebo složka**: Soubor nebo složka, které se mají zjistit.
        - **Vlastnost** – vyberte typ pravidla použitá k ověření přítomnosti aplikace.
        - **Přidruženo k 32bitové aplikaci na 64bitových klientech**: Vyberte **Ano**, pokud chcete rozbalit všechny proměnné prostředí cesty ve 32bitovém kontextu na 64bitových klientech. Výchozí možnost **Ne** vyberte, pokud chcete rozbalit všechny proměnné cesty ve 64bitovém kontextu na 64bitových klientech. 32bitoví klienti budou vždy používat 32bitový kontext.
    - **Registru**: Pokud zvolíte **registru** jako **typ požadavku**, pravidlo požadavku musí odhalit nastavení registru na základě hodnoty, řetězec, celé číslo nebo verze.
        - **Cesta ke klíči**: Úplná cesta k položce registru obsahující hodnotu, která se má zjistit.
        - **Název hodnoty**: Název hodnoty registru, která se má zjistit. Pokud je tato hodnota prázdná, provede se zjišťování u klíče. Hodnota klíče (výchozí) se použije jako hodnota zjišťování v případě, že se metoda zjišťování liší od metody zjišťování existence souboru nebo složky.
        - **Klíčovým požadavkem registru** – vyberte typ porovnání, klíčů registru použít k určení, jak se ověřit pravidlo požadavku.
        - **Přidruženo k 32bitové aplikaci na 64bitových klientech**: Vyberte **Ano**, pokud chcete vyhledat 32bitový registr na 64bitových klientech. Výchozí možnost **Ne** vyberte, pokud chcete vyhledat 64bitový registr na 64bitových klientech. 32bitoví klienti budou vždy vyhledávat 32bitový registr.
    - **skript**: Zvolte **skript** jako **typ požadavku**, když nebude možné vytvořit pravidlo požadavku na základě souborů, registru nebo jakékoliv jiné metody, které jsou k dispozici v konzole Intune.
        - **Soubor skriptu** – pro Powershellový skript na základě pravidlo požadavku, pokud existuje kód je 0, zjistíme standardního výstupu skriptu podrobněji. Například abychom mohli detekovat STDOUT jako celé číslo, které má hodnotu 1.
        - **Spusťte skript jako 32bitový proces v 64bitových klientech** – vyberte **Ano** pro spuštění skriptu v procesu 32-bit v 64bitových klientech. Vyberte **ne** (výchozí) pro spuštění skriptu v procesu 64-bit v 64bitových klientech. 32bitové klienty, spusťte skript 32bitový proces.
        - **Spusťte tento skript pomocí pověření přihlášeného**: Vyberte **Ano** ke spuštění skriptu s použitím podepsané v přihlašovací údaje zařízení **.
        - **Vynutit kontrolu podpisu skriptu**: Vyberte **Ano**, pokud chcete ověřit, že skript je podepsán důvěryhodným vydavatelem. To skriptu umožní spouštět se bez zobrazení upozornění nebo výzev. Skript se bude spouštět odblokovaný. Výchozí možnost **Ne** vyberte, pokud chcete skript spouštět na základě potvrzení koncového uživatele bez ověření podpisu.
        - **Vybrat výstupní datový typ**: Vyberte typ dat, které se používají při zjišťování shody pravidlo požadavku.
4.  Až to budete mít, vyberte **OK**.

### <a name="step-6-configure-app-detection-rules"></a>Krok 6: Konfigurace pravidel detekce aplikace

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
            
            2.  Zkontrolujte, zda hodnota registru existuje.
        
                ![Snímek obrazovky s podoknem pravidla detekce – existence hodnoty registru](./media/apps-win32-app-06.png)    
        
            3.  Zkontrolujte, zda se řetězec hodnoty registru rovná.
        
                ![Snímek obrazovky s podoknem pravidla detekce – řetězec hodnoty registru se rovná](./media/apps-win32-app-07.png)    
     
    - **Použít vlastní skript zjišťování**: Zadejte powershellový skript, který se použije ke zjištění této aplikace. 
    
        1.  **Soubor skriptu**: Vyberte powershellový skript, který zjistí přítomnost aplikace v klientovi. Aplikace se bude považovat za zjištěnou, když skript vrátí ukončovací kód s hodnotou 0 a zapíše řetězcovou hodnotu do výstupu STDOUT.

        2.  **Spusťte skript jako 32bitový proces v 64bitových klientech** – vyberte **Ano** pro spuštění skriptu v procesu 32-bit v 64bitových klientech. Vyberte **ne** (výchozí) pro spuštění skriptu v procesu 64-bit v 64bitových klientech. 32bitové klienty, spusťte skript 32bitový proces.

        3.  **Vynutit kontrolu podpisu skriptu**: Vyberte **Ano**, pokud chcete ověřit, že skript je podepsán důvěryhodným vydavatelem. To skriptu umožní spouštět se bez zobrazení upozornění nebo výzev. Skript se bude spouštět odblokovaný. Výchozí možnost **Ne** vyberte, pokud chcete skript spouštět na základě potvrzení koncového uživatele bez ověření podpisu.
    
            Agenta Intune kontroluje výsledky ze skriptu. Přečte hodnoty, které skript zapsal do standardního streamu výstupu (STDOUT), standardního streamu chyb (STDERR) a do ukončovacího kódu. Pokud kód končí nenulovou hodnotu, skript selže a stav zjišťování aplikace je Nenainstalováno. Pokud ukončovací kód obsahuje nulovou hodnotu a výstup STDOUT obsahuje data, byl stav zjišťování aplikace je Nainstalováno. 

            > [!NOTE]
            > Pokud se skript ukončí s hodnotou 0, bylo spuštění skriptu úspěšné. Sekundární výstupní kanál označuje, že aplikace byla zjištěna – data STDOUT označují, že aplikace se v klientovi našla. Konkrétnímu řetězci z výstupu STDOUT se nevěnujeme.

        4.  Po přidání pravidel vyberte **Přidat** > **OK**.

### <a name="step-7-configure-app-return-codes"></a>Krok 7: Konfigurace aplikace návratové kódy

1.  V podokně **Přidat aplikaci** vyberte **Návratové kódy** a přidejte návratové kódy, které se mají použít buď pro přidání chování při opakování instalace aplikace, nebo pro přidání chování po instalaci. Položky návratových kódů se standardně přidají při vytváření aplikace. Můžete ale přidat další nebo změnit existující návratové kódy. 
2.  V podokně **Návratové kódy** přidejte další návratové kódy nebo změňte existující návratové kódy.
    - **Nepovedlo** – návratovou hodnotu, která označuje k selhání instalace aplikace.
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
    - **K dispozici zaregistrovaným zařízením**: Uživatelé nainstalovat aplikaci z aplikace portál společnosti nebo webu portál společnosti.
    - **Vyžaduje**: Aplikace se nainstaluje na zařízení ve vybraných skupinách.
    - **Odinstalujte**: Aplikace se odinstaluje ze zařízení ve vybraných skupinách.
4.  Vyberte **Zahrnuté skupiny** a přiřaďte skupiny, které budou tuto aplikaci používat.
5.  V podokně **Přiřadit** vyberte **OK**. Tím výběr zahrnutých skupin dokončíte.
6.  Pokud se rozhodnete některé skupiny uživatelů vyloučit, aby nebyly přiřazením aplikace ovlivněné, klikněte na **Vyloučit skupiny**.
7.  V podokně **Přidat skupinu** vyberte **OK**.
8.  V podokně **Přiřazení** aplikace vyberte **Uložit**.

V tomto okamžiku jste dokončili postup do Intune přidat aplikace Win32. Informace o přiřazení a monitorování aplikace najdete v článku [Přiřazení aplikací do skupin pomocí Microsoft Intune](https://docs.microsoft.com/intune/apps-deploy) a [Monitorování informací a přiřazení aplikace pomocí Microsoft Intune](https://docs.microsoft.com/intune/apps-monitor).

## <a name="app-dependencies"></a>Závislosti aplikace

Závislosti aplikace jsou aplikace, které musí být nainstalovaný před instalací aplikace Win32. Můžete vyžadovat, aby ostatní aplikace se instalují jako závislosti. Konkrétně zařízení musíte nainstalovat závislé aplikace, před instalací aplikace Win32. Je maximálně 100 závislosti, obsahující závislosti žádné zahrnuté závislosti, stejně jako vlastní aplikaci. Závislosti aplikace systému Win32 můžete přidat až po aplikace Win32 byl přidán a nahrát do Intune. Po přidání aplikace Win32, zobrazí se vám **závislosti** možnost v okně pro vaši aplikaci Win32. 

> [!NOTE]
> Funkce závislostí aplikace bude k dispozici pouze po 1904 verzi (větší než 1.18.120.0), což může trvat jednu nebo dvě další týdny poté, co jsme upgradovat službu na 1904 byl upgradován agent pro správu Intune.

Při přidání závislosti aplikaci, můžete hledat podle názvu aplikace a vydavatele. Kromě toho můžete seřadit přidání závislostí podle názvu aplikace a vydavatele. Dříve závislosti přidání aplikace se nedá vybrat v seznamu závislostí přidaných aplikací. 

Můžete rozhodnout, zda se mají instalovat automaticky každé závislé aplikace. Ve výchozím nastavení **automaticky instalovat** je možnost nastavená na **Ano** každý závislosti. Po instalaci automaticky závislé aplikace, i v případě, že závislé aplikace neodkazuje na uživatele nebo zařízení, Intune nainstaluje aplikaci na zařízení, které splňuje závislost před instalací aplikace Win32. Je důležité si uvědomit, že závislosti může mít dílčí závislosti rekurzivní a každý dílčí závislostí se dá nainstalovat před instalací hlavní závislostí. Kromě toho instalace závislostí nedodržuje pořadí instalace na úrovni dané závislosti.

Chcete-li přidat závislost aplikace do vaší aplikace Win32, postupujte následovně:

1. V Intune, vyberte **klientské aplikace** > **aplikace** zobrazíte seznam přidali klientské aplikace. 
2. Vyberte přidání **aplikace Windows (Win32)** aplikace. 
3. Vyberte **závislosti** přidat závislé aplikace, které musí být nainstalovaný před instalací aplikace Win32. 
4. Klikněte na tlačítko **přidat** Přidat závislost aplikace.
5. Po přidání závislé aplikace, klikněte na tlačítko **vyberte**.
6. Zvolte, zda chcete automaticky nainstalovat závislé aplikace tak, že vyberete **Ano** nebo **ne** pod **automaticky instalovat**.
7. Klikněte na **Uložit**.

Koncovému uživateli se zobrazí informační zprávy Windows označující, že závislé aplikace se stahují a instalují jako součást procesu instalace aplikace Win32. Kromě toho při závislé aplikace není nainstalovaná, koncový uživatel se běžně zobrazí následující oznámení:
- 1 nebo více závislých aplikací, které se nepodařilo nainstalovat
- 1 nebo více závislých aplikací požadavky nesplněny
- 1 nebo více závislých aplikací se čeká na restartování zařízení

Pokud se rozhodnete **automaticky instalovat** závislost, Win32, nebude pokus o instalaci aplikace. Kromě toho vytváření sestav aplikace se zobrazí, že závislost byla označena jako `failed` a také zadat příslušný důvod selhání. Selhání instalace závislostí můžete zobrazit kliknutím na selhání (nebo upozornění) součástí aplikace Win 32 [podrobné informace o instalaci](troubleshoot-app-install.md#win32-app-installation-troubleshooting). 

Každá závislost bude dodržovat logika opakovaných pokusů aplikace Intune Win32 (pokus o instalaci 3krát za čekání po dobu 5 minut) a plán globální opakovaného vyhodnocení. Navíc závislosti platí pouze v době instalace aplikace Win32 v zařízení. Závislosti se nedají použít pro odinstalaci aplikace Win32. Pokud chcete odstranit závislost, musí klikněte na výpustky (tři tečky) nalevo od závislé aplikace umístěné na konci řádku v seznamu závislostí. 

## <a name="delivery-optimization"></a>Optimalizace doručení

Windows 10 1709 a vyšší než klienti budou stahovat obsah aplikace Intune Win32 pomocí komponenty optimalizace doručování na klientovi Windows 10. Optimalizace doručení poskytuje peer-to-peer funkce, které je ve výchozím nastavení zapnutá. Optimalizace doručení je možné nakonfigurovat prostřednictvím zásad skupiny a prostřednictvím konfigurace zařízení v Intune. Další informace najdete v tématu [optimalizace doručení pro Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization). 

## <a name="install-required-and-available-apps-on-devices"></a>Instalace požadovaných a dostupných aplikací na zařízení

Koncovému uživateli se zobrazí informační zprávy Windows pro instalace aplikací povinné a k dispozici. Na následujícím obrázku je znázorněna ukázková informační zpráva, že instalace aplikace se nedokončí, dokud se zařízení nerestartuje. 

![Snímek obrazovky Windows informační zprávy pro instalaci aplikace](./media/apps-win32-app-08.png)    

Na následujícím obrázku upozorní koncového uživatele, že jsou prováděny změny aplikace do zařízení.

![Snímek obrazovky upozornění uživatele, které se provádějí změny aplikace](./media/apps-win32-app-09.png)    

## <a name="toast-notifications-for-win32-apps"></a>Informační zprávy pro aplikace Win32 
V případě potřeby můžete potlačit oznámení informační zprávy zobrazující koncový uživatel za přiřazení aplikace. V Intune, vyberte **klientské aplikace** > **aplikace** > vyberte aplikaci > **přiřazení** > **zahrnout skupiny**. 

> [!NOTE]
> Rozšíření správy Intune nainstalovat Win32 neodinstaluje aplikací na nezaregistrovaných zařízeních. Správci můžou využívat vyloučení přiřazení není nabízet aplikace Win32 vlastních zařízení uživatelů.

## <a name="troubleshoot-win32-app-issues"></a>Řešení potíží s aplikacemi Win32
Protokoly agenta na klientském počítači se obvykle nachází ve složce `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs`. K zobrazení těchto protokolů můžete využít nástroj `CMTrace.exe`. *CMTrace.exe* si můžete stáhnout z [klienta nástroje Configuration Manager](https://docs.microsoft.com/sccm/core/support/tools). 

![Snímek obrazovky se Agent přihlásí v klientském počítači.](./media/apps-win32-app-10.png)    

> [!IMPORTANT]
> Povolit správné instalace a spuštění aplikace LOB Win32, by měl nastavení anti-malware vyloučení se má zkontrolovat následující adresáře:<p>
> **Na X64 klientské počítače**:<br>
> *C:\Program Files (x86)\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*
>  
> **Na X86 klientské počítače**:<br>
> *C:\Program Files\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*

Další informace o řešení potíží s aplikací Win32, naleznete v tématu [Win32 aplikace řešení potíží s instalací](troubleshoot-app-install.md#win32-app-installation-troubleshooting).

### <a name="troubleshooting-areas-to-consider"></a>Oblasti řešení potíží, na které je třeba se zaměřit
- Zkontroluje cílení, abyste měli jistotu, že je agent nainstalovaný na zařízení – aplikace Win32 zacílená na skupinu nebo powershellový skript zacílený na skupinu vytvoří zásady instalace agenta pro skupinu zabezpečení.
- Zkontrolujte verzi operačního systému – Windows 10 1607 a novější.  
- Zkontrolujte skladovou položku Windows 10 – Windows 10 S nebo verze Windows s povoleným režimem S nepodporují instalaci pomocí instalační služby MSI.

## <a name="next-steps"></a>Další postup

- Další informace o přidávání aplikací do Intune najdete v článku [Přidání aplikací do Microsoft Intune](apps-add.md).
