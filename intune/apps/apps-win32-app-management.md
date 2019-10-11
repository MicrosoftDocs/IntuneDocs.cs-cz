---
title: Přidání a přiřazení aplikací Win32 k Microsoft Intune
titleSuffix: ''
description: Naučte se, jak přidávat, přiřazovat a spravovat aplikace Win32 pomocí Microsoft Intune. Toto téma poskytuje přehled funkcí pro doručování a správu aplikací Intune Win32 a také informace o řešení potíží s aplikací Win32.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 21192d259de0711ad38fa35b294ea82c7d913292
ms.sourcegitcommit: fca2670142c083d7562c0a36547a6a451863e315
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/08/2019
ms.locfileid: "72036492"
---
# <a name="intune-standalone---win32-app-management"></a>Samostatná verze Intune – Správa aplikací Win32

[Intune Standalone](../fundamentals/mdm-authority-set.md) teď umožňuje větší možnosti správy aplikací Win32. I když je možné, aby zákazníci s připojením k síti používali Configuration Manager pro správu aplikací Win32, budou mít zákazníci s Intune větší možnosti správy pro své obchodní aplikace (LOB) pro Win32. Toto téma poskytuje přehled funkce správy aplikací Win32 Intune a informace o odstraňování potíží.

> [!NOTE]
> Tato funkce správy aplikací podporuje jak 32, tak 64 architekturu operačního systému pro aplikace Windows.

> [!IMPORTANT]
> Při nasazování aplikací Win32 zvažte použití [rozšíření pro správu Intune](../apps/intune-management-extension.md) , zejména pokud máte k dispozici instalační program aplikace pro více souborů Win32. Pokud během registrace automatického pilotního nasazení kombinujete instalaci aplikací Win32 a obchodních aplikací, může instalace aplikace selhat.  

## <a name="prerequisites"></a>Předpoklady

Pokud chcete používat správu aplikací Win32, ujistěte se, že splňujete následující kritéria:

- Windows 10 verze 1607 nebo novější (verze Enterprise, pro a školství)
- Klient Windows 10 musí být: 
  - Zařízení musí být připojená k Azure AD a automaticky zaregistrovaná. Rozšíření pro správu Intune podporuje připojení ke službě Azure AD, která je připojená k hybridní doméně, a jsou podporovaná zařízení zaregistrovaná v zásadách skupiny. 
  > [!NOTE]
  > V případě zaregistrovaného scénáře zásad skupiny koncový uživatel použije místní uživatelský účet k AAD připojit své zařízení s Windows 10. Uživatel se musí do zařízení přihlásit pomocí svého uživatelského účtu AAD a zaregistrovat se do Intune. Intune nainstaluje na zařízení rozšíření pro správu Intune, pokud je skript PowerShellu nebo aplikace Win32 cílené na uživatele nebo zařízení.
- Velikost aplikace systému Windows je omezené na 8 GB na aplikaci.

## <a name="prepare-the-win32-app-content-for-upload"></a>Příprava obsahu aplikace Win32 pro nahrání

K předběžnému zpracování aplikací pro Windows Classic (Win32) použijte [Nástroj pro přípravu obsahu Win32 od Microsoftu](https://go.microsoft.com/fwlink/?linkid=2065730) . Nástroj převede instalační soubory aplikace do formátu *. intunewin* . Nástroj také detekuje některé atributy, které Intune vyžaduje k určení stavu instalace aplikace. Po použití tohoto nástroje ve složce instalačního programu aplikace budete moct vytvořit aplikaci Win32 v konzole Intune.

> [!IMPORTANT]
> [Nástroj pro přípravu obsahu Microsoft Win32](https://go.microsoft.com/fwlink/?linkid=2065730) zips všechny soubory a podsložky při vytváření souboru *. intunewin* . Ujistěte se, že nástroj pro přípravu obsahu Microsoft Win32 je oddělený od instalačních souborů a složek, takže nezahrnete do souboru *. intunewin* nástroj ani jiné nepotřebné soubory a složky.

[Nástroj pro přípravu obsahu Microsoft Win32](https://go.microsoft.com/fwlink/?linkid=2065730) si můžete stáhnout z GitHubu jako soubor zip. Soubor zip obsahuje složku s názvem **Microsoft-Win32-Content-PREP-Tool-Master**. Složka obsahuje nástroj pro přípravu, licenci, soubor Readme a poznámky k verzi. 

### <a name="process-flow-to-create-intunewin-file"></a>Tok procesu pro vytvoření souboru. intunewin

   ![Tok procesu pro vytvoření souboru. intunewin](./media/apps-win32-app-management/prepare-win32-app.svg)

### <a name="run-the-microsoft-win32-content-prep-tool"></a>Spuštění nástroje pro přípravu obsahu Microsoft Win32

Pokud spustíte `IntuneWinAppUtil.exe` z příkazového okna bez parametrů, nástroj vás provede zadáním podrobných parametrů. Nebo můžete přidat parametry do příkazu na základě následujících dostupných parametrů příkazového řádku.

### <a name="available-command-line-parameters"></a>Dostupné parametry příkazového řádku 

|    **Parametr příkazového řádku**    |    **Popis**    |
|:------------------------------:|:----------------------------------------------------------:|
|    `-h`     |    Nápověda    |
|    `-c <setup_folder>`     |    Složka pro všechny instalační soubory. Všechny soubory v této složce budou zkomprimovány do souboru *. intunewin* .    |
|    `-s <setup_file>`     |    Instalační soubor (například *Setup. exe* nebo *Setup. msi*).    |
|    `-o <output_folder>`     |    Výstupní složka pro vygenerovaný soubor *. intunewin*    |
|    `-q`       |    Tichý režim    |

### <a name="example-commands"></a>Příklady příkazů

|    **Příklad příkazu**    |    **Popis**    |
|:-----------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    `IntuneWinAppUtil -h`    |    Tento příkaz zobrazí informace o použití nástroje.    |
|    `IntuneWinAppUtil -c c:\testapp\v1.0 -s c:\testapp\v1.0\setup.exe -o c:\testappoutput\v1.0 -q`    |    Tento příkaz vytvoří soubor `.intunewin` ze zadané zdrojové složky a instalačního souboru. Pro instalační soubor MSI tento nástroj načte požadované informace pro Intune. Je-li zadán parametr `-q`, příkaz se spustí v tichém režimu a pokud výstupní soubor již existuje, bude přepsán. Také pokud výstupní složka neexistuje, vytvoří se automaticky.    |

Při generování souboru *. intunewin* uložte všechny soubory, které potřebujete odkazovat do podsložky složky nastavení. Pak použijte relativní cestu k odkazování na konkrétní soubor, který potřebujete. Například:

**Zdrojová složka instalačního programu:** *c:\testapp\v1.0*<br>
**Soubor s licencí:** *c:\testapp\v1.0\licenses\license.txt*

Informace o souboru *License. txt* najdete pomocí relativní cesty *licenses\license.txt*.

## <a name="create-assign-and-monitor-a-win32-app"></a>Vytvoření, přiřazení a monitorování aplikace Win32

Podobně jako obchodní aplikace (LOB) můžete přidat aplikaci Win32 do Microsoft Intune. Tento typ aplikace se obvykle napíše interně nebo třetí stranou. 

### <a name="process-flow-to-add-a-win32-app-to-intune"></a>Tok procesu pro přidání aplikace Win32 do Intune

<img alt="Process flow to add a Win32 app to Intune" src="./media/apps-win32-app-management/add-win32-app.svg" width="500">

### <a name="add-a-win32-app-to-intune"></a>Přidání aplikace Win32 do Intune

Následující kroky poskytují pokyny, které vám pomůžou přidat aplikaci pro Windows do Intune.

### <a name="step-1-specify-the-software-setup-file"></a>Krok 1: určení instalačního souboru softwaru

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** vyberte **klientské aplikace** > **aplikace** > **Přidat**.
4. V podokně **Přidat** aplikaci vyberte v zobrazeném rozevíracím seznamu možnost **aplikace pro Windows (Win32)** .

    ![Snímek obrazovky okna Přidat aplikaci – přidat typ rozevíracího seznamu](./media/apps-win32-app-management/apps-win32-app-01.png)

### <a name="step-2-upload-the-app-package-file"></a>Krok 2: nahrání souboru balíčku aplikace

1. V podokně **Přidat aplikaci** vyberte **soubor balíčku aplikace** a vyberte soubor. Zobrazí se podokno souborů balíčku aplikace.

    ![Snímek obrazovky okna souboru balíčku aplikace](./media/apps-win32-app-management/apps-win32-app-02.png)

2. V podokně **soubor balíčku aplikace** klikněte na tlačítko Procházet. Pak vyberte instalační soubor Windows s příponou *. intunewin*.

    > [!IMPORTANT]
    > Nezapomeňte použít nejnovější verzi nástroje pro přípravu obsahu Microsoft Win32. Pokud nepoužíváte nejnovější verzi, zobrazí se upozornění s oznámením, že aplikace byla zabalená pomocí starší verze nástroje pro přípravu obsahu Microsoft Win32. 

3. Až budete hotovi, vyberte **OK**.

### <a name="step-3-configure-app-information"></a>Krok 3: Konfigurace informací o aplikaci

1. V podokně **Přidat aplikaci** vyberte **informace o aplikaci** a nakonfigurujte aplikaci.
2. V podokně **informace o aplikaci** nakonfigurujte následující informace. Některé hodnoty v tomto podokně mohou být automaticky vyplněny.
    - **Název**: zadejte název aplikace, který se zobrazí na portálu společnosti. Pokud stejný název aplikace existuje dvakrát, každá aplikace se zobrazí na portálu společnosti.
    - **Popis**: zadejte popis aplikace. Popis se zobrazí na portálu společnosti.
    - **Publikování**r: zadejte název vydavatele aplikace.
    - **Kategorie**: vyberte jednu nebo více předdefinovaných kategorií aplikací nebo vyberte kategorii, kterou jste vytvořili. Kategorie usnadňují uživatelům vyhledání aplikace při procházení portálu společnosti.
    - **Zobrazit jako doporučenou aplikaci v portál společnosti**: aplikace bude na hlavní stránce portálu společnosti výrazně zobrazovat, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Adresa URL ochrany osobních údajů**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o ochraně osobních údajů pro aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Vývojář**: Volitelně můžete zadat název vývojáře aplikace.
    - **Vlastník**: Volitelně zadejte jméno vlastníka této aplikace. Příkladem je **personální oddělení**.
    - **Poznámky**: Zadejte jakékoli poznámky, které chcete přidružit k této aplikaci.
    - **Logo**: Nahrajte ikonu, která je přidružená k aplikaci. Ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
3. Až budete hotovi, vyberte **OK**.

### <a name="step-4-configure-app-installation-details"></a>Krok 4: Konfigurace podrobností instalace aplikace
1. V podokně **Přidat aplikaci** vyberte **program** , abyste nakonfigurovali příkazy pro instalaci a odebrání aplikace v aplikaci.
2. Přidejte k instalaci aplikace úplný příkazový řádek instalace. 

    Například pokud je název vaší aplikace **MyApp123**, přidejte následující:<br>
    `msiexec /p “MyApp123.msp”`<p>
    A pokud je aplikace `ApplicationName.exe`, příkaz by představoval název aplikace následovaný argumenty příkazu (přepínači) podporovanými balíčkem. <br>Například:<br>
    `ApplicationName.exe /quiet`<br>
    V příkazu výše podporuje balíček `ApplicationName.exe` argument příkazu `/quiet`.<p> 
    Pro konkrétní argumenty podporované balíčkem aplikace se obraťte na dodavatele aplikace.

3. Přidáním úplného příkazového řádku pro odinstalaci odinstalujte aplikaci na základě identifikátoru GUID aplikace. 

    Například: `msiexec /x “{12345A67-89B0-1234-5678-000001000000}”`

    > [!NOTE]
    > Aplikaci Win32 můžete nakonfigurovat tak, aby se nainstalovala v **uživatelském** nebo **systémovém** kontextu. Kontext **uživatele** se vztahuje pouze na daného uživatele. **Systémový** kontext odkazuje na všechny uživatele zařízení s Windows 10.
    >
    > Pro instalaci aplikací Win32 není nutné, aby se na zařízení přihlásili koncoví uživatelé.
    > 
    > Instalace a odinstalace aplikace Win32 se spustí v části oprávnění správce (ve výchozím nastavení), když je aplikace nastavená tak, aby se nainstalovala v uživatelském kontextu, a koncový uživatel na zařízení má oprávnění správce.

4. Až budete hotovi, vyberte **OK**.

### <a name="step-5-configure-app-requirements"></a>Krok 5: Konfigurace požadavků aplikace

1. V podokně **Přidat aplikaci** vyberte **požadavky** , abyste nakonfigurovali požadavky, které zařízení musí splnit, než se aplikace nainstaluje.
2. V podokně **Přidat pravidlo požadavku** nakonfigurujte následující informace. Některé hodnoty v tomto podokně mohou být automaticky vyplněny.
    - **Architektura operačního systému**: vyberte architektury, které musí aplikace nainstalovat.
    - **Minimální operační systém**: vyberte minimální operační systém potřebný k instalaci aplikace.
    - **Požadované místo na disku (MB)** : Volitelně můžete k instalaci aplikace přidat volné místo na disku potřebné na systémové jednotce.
    - **Požadovaná fyzická paměť (MB)** : Volitelně můžete přidat fyzickou paměť (RAM) nutnou k instalaci aplikace.
    - **Minimální požadovaný počet logických procesorů**: Volitelně můžete přidat minimální počet logických procesorů potřebných k instalaci aplikace.
    - **Minimální požadovaná rychlost procesoru (MHz)** : Volitelně můžete přidat minimální rychlost procesoru potřebnou k instalaci aplikace.

3. Kliknutím na **Přidat** zobrazíte okno **Přidat pravidlo požadavku** a nakonfigurujete další pravidla požadavků. Vyberte **typ požadavku** a zvolte typ pravidla, který budete používat k určení způsobu ověření požadavku. Pravidla požadavků můžou být založená na informacích o systému souborů, hodnotách registru nebo skriptech PowerShellu. 
    - **Soubor**: když jako **typ požadavku**zvolíte **soubor** , pravidlo požadavku musí detekovat soubor nebo složku, datum, verzi nebo velikost. 
        - **Cesta** – úplná cesta ke složce obsahující soubor nebo složku, která se má zjistit
        - **Soubor nebo složka** – soubor nebo složka, které se mají zjistit.
        - **Vlastnost** – vyberte typ pravidla, které se použije k ověření přítomnosti aplikace.
        - **Přidružená k 32 aplikaci na 64 klientech** – výběrem **Ano** rozbalíte všechny proměnné prostředí PATH v kontextu 32-bit v 64 systémech 16bitového klienta. Pokud chcete rozšířit všechny proměnné cest v 64 kontextu na 64 klientech, vyberte **ne** (výchozí). 32-bitoví klienti budou vždy používat 32 bitovou kontext.
    - **Registr**: když jako **typ požadavku**zvolíte **registr** , pravidlo požadavku musí zjistit nastavení registru na základě hodnoty, řetězce, celého čísla nebo verze.
        - **Cesta ke klíči** – úplná cesta k položce registru obsahující hodnotu, která se má zjistit.
        - **Název hodnoty** – název hodnoty registru, která se má zjistit. Pokud je tato hodnota prázdná, k detekci dojde v klíči. Hodnota (výchozí) klíč se použije jako hodnota detekce, pokud je metoda zjišťování jiná než existence souboru nebo složky.
        - **Požadavek na klíč registru** – vyberte typ porovnání klíče registru používaného k určení způsobu ověření pravidla požadavku.
        - **Přidružená k 32 aplikaci na 64 klientech** – vyberte **Ano** , pokud chcete hledat v 64 počítačích s 64bitovým systémem na 32. Vyberte **ne** (výchozí) vyhledejte 64 registr na 64 klientech. 32-bitové klienty budou vždy Hledat v registru 32.
    - **Skript**: Pokud nemůžete vytvořit pravidlo požadavku založené na souboru, registru nebo jiné metodě, kterou máte k dispozici v konzole Intune, vyberte **skript** jako **typ požadavku**.
        - **Soubor skriptu** – pro pravidlo požadavku na základě skriptu prostředí PowerShell, pokud existuje kód 0, zjistíme, že stdout bude více zjišťovat podrobněji. Můžete například detekovat STDOUT jako celé číslo s hodnotou 1.
        - **Spustit skript jako 32ový proces na 64 klientech** – vyberte **Ano** , pokud chcete skript spustit 32 v 16bitovém procesu 64 na 64bitových klientech. Pokud chcete spustit skript v 64 procesech na 64 klientech, vyberte **ne** (výchozí). 32-bitoví klienti spouštějí skript v procesu 32.
        - **Spusťte tento skript pomocí přihlašovacích údajů přihlášeného**: vyberte **Ano** , pokud chcete skript spustit pomocí přihlašovacích údajů přihlášeného zařízení * *.
        - **Vynutilo kontrolu podpisu skriptu** – vyberte **Ano** , pokud chcete ověřit, že je skript podepsaný důvěryhodným vydavatelem. tím se umožní, aby se skript spouštěl bez upozornění nebo zobrazování výzev. Skript se spustí odblokované. Pokud chcete spustit skript s potvrzením koncových uživatelů bez ověření podpisu, vyberte **ne** (výchozí).
        - **Vyberte typ výstupních dat**: vyberte datový typ, který se použije při určování shody pravidla požadavku.
4. Až budete hotovi, vyberte **OK**.

### <a name="step-6-configure-app-detection-rules"></a>Krok 6: Konfigurace pravidel detekce aplikací

1. V podokně **Přidat aplikaci** vyberte **pravidla detekce** , abyste mohli nakonfigurovat pravidla pro detekci přítomnosti aplikace.
2. V poli **Formát pravidel** vyberte, jak se bude detekovat přítomnost aplikace. Můžete zvolit buď ruční konfiguraci pravidel detekce, nebo použít vlastní skript k detekci přítomnosti aplikace. Musíte zvolit aspoň jedno pravidlo zjišťování. 

    > [!NOTE]
    > V podokně **pravidla detekce** se můžete rozhodnout přidat několik pravidel. Pro detekci aplikace musí být splněné podmínky pro **všechna** pravidla.
    >
    > Pokud Intune zjistí, že se aplikace v zařízení nenachází, Intune tuto aplikaci nabídne znovu za 24 hodin. Tato akce nastane jenom u aplikací, které cílí na povinný záměr.

    - **Ruční konfigurace pravidel detekce** – můžete vybrat jeden z následujících typů pravidel:
        1. **MSI** – ověřte na základě kontroly verze MSI. Tuto možnost lze přidat pouze jednou. Když vyberete tento typ pravidla, máte dvě nastavení:
            - **Kód produktu MSI** – přidejte do aplikace platný kód produktu MSI.
            - **Kontrola verze produktu MSI** – vyberte **Ano** , pokud chcete kromě kódu produktu MSI ověřit i verzi produktu MSI.
        2. **Soubor** – ověřte na základě zjištění souboru nebo složky, data, verze nebo velikosti.
            - **Cesta** – úplná cesta ke složce obsahující soubor nebo složku, která se má zjistit
            - **Soubor nebo složka** – soubor nebo složka, které se mají zjistit.
            - **Metoda detekce** – vyberte typ metody detekce, který se používá k ověření přítomnosti aplikace.
            - **Přidružená k 32 aplikaci na 64 klientech** – výběrem **Ano** rozbalíte všechny proměnné prostředí PATH v kontextu 32-bit v 64 systémech 16bitového klienta. Pokud chcete rozšířit všechny proměnné cest v 64 kontextu na 64 klientech, vyberte **ne** (výchozí). 32-bitoví klienti budou vždy používat 32 bitovou kontext.
            
            **Příklady detekce na základě souborů**
            1. Kontrolovat existenci souboru.
         
                ![Snímek obrazovky s podoknem pravidel detekce – existence souboru](./media/apps-win32-app-management/apps-win32-app-03.png)
        
            2. Kontrolovat existenci složky.
         
                ![Snímek obrazovky s podoknem pravidel detekce – existence složky](./media/apps-win32-app-management/apps-win32-app-04.png)
        
        3. **Registr** – ověřte na základě hodnoty, řetězce, celého čísla nebo verze.
            - **Cesta ke klíči** – úplná cesta k položce registru obsahující hodnotu, která se má zjistit.
            - **Název hodnoty** – název hodnoty registru, která se má zjistit. Pokud je tato hodnota prázdná, k detekci dojde v klíči. Hodnota (výchozí) klíč se použije jako hodnota detekce, pokud je metoda zjišťování jiná než existence souboru nebo složky.
            - **Metoda detekce** – vyberte typ metody detekce, který se používá k ověření přítomnosti aplikace.
            - **Přidružená k 32 aplikaci na 64 klientech** – vyberte **Ano** , pokud chcete hledat v 64 počítačích s 64bitovým systémem na 32. Vyberte **ne** (výchozí) vyhledejte 64 registr na 64 klientech. 32-bitové klienty budou vždy Hledat v registru 32.
            
            **Příklady pro detekci založenou na registru**
            1. Klíč registru, který se má vyhledat, existuje.
            
                ![Snímek obrazovky s podoknem pravidel detekce – klíč registru existuje](./media/apps-win32-app-management/apps-win32-app-05.png)    
            
            2. Zkontroluje, jestli hodnota registru existuje.
        
                ![Snímek obrazovky s podoknem pravidel detekce – hodnota registru existuje](./media/apps-win32-app-management/apps-win32-app-06.png)    
        
            3. Podívejte se, jestli se řetězec hodnoty registru rovná.
        
                ![Snímek obrazovky s podoknem pravidla detekce – řetězec hodnoty registru se rovná](./media/apps-win32-app-management/apps-win32-app-07.png)    
     
    - **Použijte vlastní skript detekce** – zadejte powershellový skript, který se použije k detekci této aplikace. 
    
        1. **Soubor skriptu** – vyberte powershellový skript, který zjistí přítomnost aplikace na klientovi. Aplikace bude detekována, když skript vrátí ukončovací kód 0 a zapíše hodnotu řetězce do STDOUT.

        2. **Spustit skript jako 32ový proces na 64 klientech** – vyberte **Ano** , pokud chcete skript spustit 32 v 16bitovém procesu 64 na 64bitových klientech. Pokud chcete spustit skript v 64 procesech na 64 klientech, vyberte **ne** (výchozí). 32-bitoví klienti spouštějí skript v procesu 32.

        3. **Vynutilo kontrolu podpisu skriptu** – vyberte **Ano** , pokud chcete ověřit, že je skript podepsaný důvěryhodným vydavatelem. tím se umožní, aby se skript spouštěl bez upozornění nebo zobrazování výzev. Skript se spustí odblokované. Pokud chcete spustit skript s potvrzením koncových uživatelů bez ověření podpisu, vyberte **ne** (výchozí).
    
            Agent Intune kontroluje výsledky ze skriptu. Přečte hodnoty zapsané skriptem do standardního výstupního (STDOUT) streamu, standardního chyby (STDERR) a ukončovacího kódu. Pokud se skript ukončí s nenulovou hodnotou, skript se nezdařil a stav detekce aplikace není nainstalován. Pokud je ukončovací kód nula a STDOUT obsahuje data, je stav detekce aplikace nainstalován. 

            > [!NOTE]
            > Microsoft doporučuje kódování skriptu jako UTF-8. Když se skript ukončí s hodnotou 0, spuštění skriptu bylo úspěšné. Druhý výstupní kanál indikuje zjištěnou aplikaci – data STDOUT označují, že se aplikace našla na klientovi. Nehledáme konkrétní řetězec z STDOUT.

        4. Jakmile přidáte pravidla, vyberte **přidat** > **OK**.

### <a name="step-7-configure-app-return-codes"></a>Krok 7: Konfigurace návratových kódů aplikace

1. V podokně **Přidat aplikaci** vyberte **návratové** kódy pro přidání návratových kódů, které slouží k určení chování při instalaci aplikace nebo chování po instalaci. Ve výchozím nastavení se během vytváření aplikace přidávají položky návratového kódu. Můžete však přidat další návratové kódy nebo změnit existující návratové kódy. 
2. V podokně **návratové kódy** přidejte další návratové kódy nebo upravte existující návratové kódy.
    - **Selhalo** – vrácená hodnota, která indikuje selhání instalace aplikace.
    - **Pevný restart** – návratový kód při pevném restartování nepovoluje instalaci dalších aplikací Win32 do klienta bez restartování. 
    - **Rychlé restartování** – návratový kód pro rychlé restartování umožňuje instalaci další aplikace Win32 bez nutnosti restartování klienta. Restart je nutný k dokončení instalace aktuální aplikace.
    - **Opakovat** – agent návratového kódu opakování se pokusí aplikaci nainstalovat třikrát. Mezi jednotlivými pokusy bude čekat 5 minut. 
    - **Úspěch** – vrácená hodnota, která indikuje, že aplikace byla úspěšně nainstalována.
3. Po přidání nebo úpravě seznamu návratových kódů vyberte **OK** .

### <a name="step-8-add-the-app"></a>Krok 8: Přidání aplikace

1. V podokně **Přidat aplikaci** ověřte, jestli jste správně nakonfigurovali informace o aplikaci.
2. Vyberte **Přidat** a nahrajte aplikaci do Intune.

### <a name="step-9-assign-the-app"></a>Krok 9: přiřazení aplikace

1. V podokně aplikace vyberte **přiřazení**.
2. Výběrem možnosti **Přidat skupinu** otevřete podokno **Přidat skupinu** , které souvisí s aplikací.
3. V případě konkrétní aplikace vyberte **Typ přiřazení**:
    - **K dispozici pro zaregistrovaná zařízení**: uživatelé aplikaci nainstalují z aplikace Portál společnosti nebo portál společnosti webu.
    - **Požadováno**: aplikace je nainstalovaná na zařízeních ve vybraných skupinách.
    - **Odinstalace**: aplikace se odinstaluje ze zařízení ve vybraných skupinách.
4. Vyberte **zahrnuté skupiny** a přiřaďte skupiny, které budou používat tuto aplikaci.
5. V podokně **přiřadit** vyberte **OK** a dokončete výběr zahrnutých skupin.
6. Pokud chcete vyloučit skupiny uživatelů, na které se toto přiřazení aplikace dotýká, vyberte **vyloučit skupiny**.
7. V podokně **Přidat skupinu** vyberte **OK**.
8. V podokně **přiřazení** aplikace vyberte **Uložit**.

V tuto chvíli jste dokončili kroky pro přidání aplikace Win32 do Intune. Informace o přiřazování a monitorování aplikací najdete v článku [přiřazení aplikací do skupin pomocí Microsoft Intune](apps-deploy.md) a [monitorování informací a přiřazení aplikace pomocí Microsoft Intune](apps-monitor.md).

## <a name="app-dependencies"></a>Závislosti aplikací

Závislosti aplikací jsou aplikace, které je třeba nainstalovat, než bude možné nainstalovat aplikaci Win32. Můžete vyžadovat, aby byly další aplikace nainstalovány jako závislosti. Konkrétně musí zařízení před instalací aplikace Win32 nainstalovat závislé aplikace. Existuje maximálně 100 závislostí, které zahrnují závislosti všech zahrnutých závislostí a také samotnou aplikaci. Závislosti aplikace Win32 můžete přidat až po přidání a nahrání aplikace Win32 do Intune. Po přidání aplikace Win32 se v okně pro aplikaci Win32 zobrazí možnost **závislosti** . 

Jakákoli závislost aplikace Win32 musí být také aplikací Win32. Nepodporuje se v závislosti na jiných typech aplikací, například na samostatných aplikacích MSI LOB nebo v aplikacích pro Store.

Při přidávání závislosti aplikace můžete vyhledávat podle názvu aplikace a vydavatele. Přidané závislosti můžete seřadit také na základě názvu a vydavatele aplikace. Dříve přidané závislosti aplikací nelze vybrat v seznamu závislostí přidaných aplikací. 

Můžete zvolit, jestli se mají automaticky instalovat jednotlivé závislé aplikace. Ve výchozím nastavení je možnost **automaticky instalovat** nastavená na **hodnotu Ano** pro každou závislost. Při automatické instalaci závislé aplikace, i když není závislá aplikace cílena na uživatele nebo zařízení, Intune nainstaluje aplikaci na zařízení, aby před instalací aplikace Win32 splňovala závislost. Je důležité si uvědomit, že závislost může mít rekurzivní závislosti a každá podřízená závislost bude nainstalována před instalací hlavní závislosti. Kromě toho instalace závislostí nedodržuje pořadí instalace na dané úrovni závislostí.

Chcete-li přidat závislost aplikace do aplikace Win32, použijte následující postup:

1. V Intune vyberte **klientské aplikace** > **aplikace** . zobrazí se seznam přidaných klientských aplikací. 
2. Vyberte přidanou aplikaci pro **Windows (Win32)** . 
3. Vyberte **závislosti** a přidejte tam závislé aplikace, které musí být nainstalované, než bude možné nainstalovat aplikaci Win32. 
4. Kliknutím na **Přidat** přidejte závislost aplikace.
5. Po přidání závislých aplikací klikněte na **Vybrat**.
6. Zvolte, jestli se má automaticky nainstalovat závislá aplikace, a to tak, že v části **automaticky nainstalovat**vyberete **Ano** nebo **ne** .
7. Klikněte na **Uložit**.

Koncovému uživateli se zobrazí informační zpráva systému Windows s oznámením, že se stahují a instalují závislé aplikace jako součást procesu instalace aplikace Win32. Kromě toho, když není nainstalovaná závislá aplikace, bude koncový uživatel obvykle zobrazovat jedno z následujících oznámení:
- jednu nebo víc závislých aplikací se nepovedlo nainstalovat.
- 1 nebo více požadavků závislých aplikací nebylo splněno.
- jedna nebo více závislých aplikací čeká na restartování zařízení.

Pokud se rozhodnete, že nechcete **automatickou instalaci** závislosti, nebude proveden pokus o instalaci aplikace Win32. Kromě toho se v hlášení aplikace zobrazí, že závislost byla označena jako `failed` a také může mít důvod selhání. Selhání instalace závislosti můžete zobrazit kliknutím na chybu (nebo upozornění), která je k dispozici v [podrobnostech o instalaci](troubleshoot-app-install.md#win32-app-installation-troubleshooting)aplikace Win 32. 

Každá závislost bude odpovídat logice opakování aplikace Intune Win32 (zkuste nainstalovat třikrát po uplynutí 5 minut) a globální plán opakovaného vyhodnocení. Závislosti se taky použijí jenom v době instalace aplikace Win32 do zařízení. Závislosti nejsou k dispozici pro odinstalaci aplikace Win32. Pokud chcete závislost odstranit, musíte kliknout na elipsy (tři tečky) nalevo od závislé aplikace umístěné na konci řádku seznamu závislostí. 

## <a name="delivery-optimization"></a>Optimalizace doručení

Windows 10 1709 a novější klienti stáhnou obsah aplikace Intune Win32 pomocí součásti optimalizace doručování v klientovi s Windows 10. Optimalizace doručení poskytuje funkce peer-to-peer, které jsou ve výchozím nastavení zapnuté. Optimalizace doručení se dá nakonfigurovat pomocí zásad skupiny a pomocí konfigurace zařízení v Intune. Další informace najdete v tématu [optimalizace doručování pro Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization). 

## <a name="install-required-and-available-apps-on-devices"></a>Instalace požadovaných a dostupných aplikací na zařízeních

Koncový uživatel uvidí informační zprávy systému Windows pro požadované a dostupné instalace aplikací. Následující obrázek ukazuje příklad informačního oznámení, kde se instalace aplikace nedokončila, dokud se zařízení nerestartuje. 

![Snímek obrazovky s oznámeními informačních zpráv systému Windows pro instalaci aplikace](./media/apps-win32-app-management/apps-win32-app-08.png)    

Následující obrázek upozorní koncového uživatele, že se na zařízení provádí změny aplikace.

![Snímek obrazovky oznamující uživateli, že probíhají změny aplikace](./media/apps-win32-app-management/apps-win32-app-09.png)    

## <a name="toast-notifications-for-win32-apps"></a>Oznámení informačních zpráv pro aplikace Win32 
V případě potřeby můžete potlačit zobrazování oznámení informační zprávy koncového uživatele na přiřazení aplikace. V Intune vyberte **klientské aplikace**@no__t **-1 > vyberte aplikace >** **přiřazení** **skupiny zahrnutí** > . 

> [!NOTE]
> Rozšíření pro správu Intune nainstalované aplikace Win32 se odinstalují na nezaregistrovaných zařízeních. Správci můžou využít vyloučení přiřazení, aby nenabízeli aplikacím Win32 možnost BYOD zařízení.

## <a name="troubleshoot-win32-app-issues"></a>Řešení problémů s aplikacemi Win32
Protokoly agenta v klientském počítači jsou běžně v `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs`. K zobrazení těchto souborů protokolu můžete využít `CMTrace.exe`. *CMTrace. exe* lze stáhnout z [Configuration Manager klientských nástrojů](https://docs.microsoft.com/sccm/core/support/tools). 

![Snímek obrazovky protokolů agenta v klientském počítači](./media/apps-win32-app-management/apps-win32-app-10.png)    

> [!IMPORTANT]
> Aby bylo možné správně nainstalovat a spustit aplikace pro obchodní prostředí Win32, nastavení antimalwarového programu by mělo vyloučit následující adresáře, aby byly prohledávány:<p>
> **Na klientských počítačích x64**:<br>
> *C:\Program Files (x86) \Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*
>  
> **Na klientských počítačích x86**:<br>
> *C:\Program Files\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*

### <a name="detecting-the-win32-app-file-version-using-powershell"></a>Zjištění verze souboru aplikace Win32 pomocí prostředí PowerShell

Pokud máte potíže s detekcí verze souboru aplikace Win32, zvažte použití nebo úpravy následujícího příkazu prostředí PowerShell:

``` PowerShell

$FileVersion = [System.Diagnostics.FileVersionInfo]::GetVersionInfo("<path to binary file>").FileVersion
#The below line trims the spaces before and after the version name
$FileVersion = $FileVersion.Trim();
if ("<file version of successfully detected file>" -eq $FileVersion)
{
#Write the version to STDOUT by default
$FileVersion
exit 0
}
else
{
#Exit with non-zero failure code
exit 1
}
```

Ve výše uvedeném příkazu PowerShellu nahraďte řetězec `<path to binary file>` cestou k souboru aplikace Win32. Příklad cesty by byl podobný následujícímu:<br>
`C:\Program Files (x86)\Microsoft SQL Server Management Studio 18\Common7\IDE\ssms.exe`

Také nahraďte řetězec `<file version of successfully detected file>` verzí souboru, který je třeba zjistit. Příklad řetězce verze souboru by byl podobný následujícímu:<br>
`2019.0150.18118.00 ((SSMS_Rel).190420-0019)`

Pokud potřebujete získat informace o verzi vaší aplikace Win32, můžete použít následující příkaz prostředí PowerShell:

``` PowerShell

[System.Diagnostics.FileVersionInfo]::GetVersionInfo("<path to binary file>").FileVersion

```

Ve výše uvedeném příkazu prostředí PowerShell nahraďte `<path to binary file>` cestou k souboru.

### <a name="additional-troubleshooting-areas-to-consider"></a>Další oblasti řešení potíží, které je potřeba zvážit
- Zkontrolujte cíle a zajistěte, aby byl agent nainstalovaný v aplikaci systému Win32, která je určená pro skupinu nebo skript prostředí PowerShell, který cílí na skupinu, a vytvoří zásady pro instalaci agenta pro skupinu zabezpečení.
- Podívejte se na verzi operačního systému – Windows 10 1607 a novější.  
- Podívejte se na Windows 10 SKU – Windows 10 S nebo verze Windows běžící s povoleným režimem S. nepodporují instalaci MSI.

Další informace o řešení potíží s aplikacemi Win32 najdete v tématu [řešení potíží s instalací aplikací Win32](troubleshoot-app-install.md#win32-app-installation-troubleshooting).

## <a name="next-steps"></a>Další kroky

- Další informace o přidávání aplikací do Intune najdete v tématu [Přidání aplikací do Microsoft Intune](apps-add.md).
