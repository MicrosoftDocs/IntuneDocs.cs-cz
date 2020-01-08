---
title: Přidání a přiřazení aplikací Win32 k Microsoft Intune
titleSuffix: ''
description: Naučte se, jak přidávat, přiřazovat a spravovat aplikace Win32 pomocí Microsoft Intune. Toto téma poskytuje přehled funkcí pro poskytování a správu aplikací Win32 přes Intune a informace o řešení potíží s těmito aplikacemi.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 371800b39e04695eadc906465fdb013488836df9
ms.sourcegitcommit: 3189c3a82cfd1ff3a58153dfec2e12fae7b9bdc7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/03/2020
ms.locfileid: "75622522"
---
# <a name="intune-standalone---win32-app-management"></a>Samostatná verze Intune – Správa aplikací Win32

[Intune Standalone](../fundamentals/mdm-authority-set.md) teď umožňuje větší možnosti správy aplikací Win32. Přestože zákazníci připojení ke cloudu mohou pro správu aplikací Win32 používat nástroj Configuration Manager, zákazníci, kteří používají pouze Intune, mají širší možnosti správy svých obchodních aplikací Win32. Toto téma poskytuje přehled funkce správy aplikací Win32 v Intune a informace o řešení potíží.

> [!NOTE]
> Tato funkce správy aplikací podporuje jak 32, tak 64 architekturu operačního systému pro aplikace Windows.

> [!IMPORTANT]
> Při nasazování aplikací Win32 zvažte použití [rozšíření pro správu Intune](../apps/intune-management-extension.md) , zejména pokud máte k dispozici instalační program aplikace pro více souborů Win32. Pokud během registrace automatického pilotního nasazení kombinujete instalaci aplikací Win32 a obchodních aplikací, může instalace aplikace selhat.  

## <a name="prerequisites"></a>Požadované součásti

Pokud chcete používat správu aplikací Win32, ujistěte se, že splňujete následující kritéria:

- Windows 10 verze 1607 nebo novější (verze Enterprise, pro a školství)
- Klient Windows 10 musí splňovat tyto předpoklady: 
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
|    `-s <setup_file>`     |    Instalační soubor (například *setup.exe* nebo *setup.msi*)    |
|    `-o <output_folder>`     |    Výstupní složka pro vygenerovaný soubor *.intunewin*    |
|    `-q`       |    Tichý režim    |

### <a name="example-commands"></a>Příklady příkazů

|    **Příklad příkazu**    |    **Popis**    |
|:-----------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    `IntuneWinAppUtil -h`    |    Tento příkaz zobrazí informace o využití nástroje.    |
|    `IntuneWinAppUtil -c c:\testapp\v1.0 -s c:\testapp\v1.0\setup.exe -o c:\testappoutput\v1.0 -q`    |    Tento příkaz vygeneruje soubor `.intunewin` ze zadané zdrojové složky a instalačního souboru. U instalačního souboru MSI tento nástroj načte požadované informace pro Intune. Pokud zadáte parametr `-q`, příkaz se spustí v tichém režimu a pokud už výstupní soubor existuje, přepíše se. Pokud výstupní složka ještě neexistuje, automaticky se vytvoří.    |

Při generování souboru *. intunewin* uložte všechny soubory, které potřebujete odkazovat do podsložky složky nastavení. Pak použijte relativní cestu k odkazování na konkrétní soubor, který potřebujete. Příklad:

**Zdrojová složka instalačního programu:** *c:\testapp\v1.0*<br>
**License file:** *c:\testapp\v1.0\licenses\license.txt*

Informace o souboru *License. txt* najdete pomocí relativní cesty *licenses\license.txt*.

## <a name="create-assign-and-monitor-a-win32-app"></a>Vytvoření, přiřazení a monitorování aplikace Win32

Stejně jako obchodní aplikaci můžete do Microsoft Intune přidat také aplikaci Win32. Tento typ aplikace obvykle vytváří místní vývojáři nebo třetí strana. 

### <a name="process-flow-to-add-a-win32-app-to-intune"></a>Tok procesu pro přidání aplikace Win32 do Intune

<img alt="Process flow to add a Win32 app to Intune" src="./media/apps-win32-app-management/add-win32-app.svg" width="500">

### <a name="add-a-win32-app-to-intune"></a>Přidání aplikace Win32 do Intune

Následující kroky obsahují pokyny k přidání aplikace pro Windows do Intune.

### <a name="step-1-specify-the-software-setup-file"></a>Krok 1: Určení instalačního souboru softwaru

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Vyberte **aplikace** > **všechny aplikace** > **Přidat**.
4. V podokně **Přidat** aplikaci vyberte v zobrazeném rozevíracím seznamu možnost **aplikace pro Windows (Win32)** .

    ![Snímek obrazovky podokna přidat aplikaci – rozevírací pole přidat typ](./media/apps-win32-app-management/apps-win32-app-01.png)

### <a name="step-2-upload-the-app-package-file"></a>Krok 2: Nahrání souboru balíčku aplikace

1. V podokně **Přidat aplikaci** zvolte **Soubor balíčku aplikace** a vyberte soubor. Zobrazí se podokno Soubor balíčku aplikace.

    ![Snímek obrazovky s podoknem souboru balíčku aplikace](./media/apps-win32-app-management/apps-win32-app-02.png)

2. V podokně **Soubor balíčku aplikace** vyberte tlačítko Procházet. Potom vyberte instalační soubor Windows s příponou *.intunewin*.

    > [!IMPORTANT]
    > Nezapomeňte použít nejnovější verzi nástroje pro přípravu obsahu Microsoft Win32. Pokud nepoužíváte nejnovější verzi, zobrazí se upozornění s oznámením, že aplikace byla zabalená pomocí starší verze nástroje pro přípravu obsahu Microsoft Win32. 

3. Až to budete mít, vyberte **OK**.

### <a name="step-3-configure-app-information"></a>Krok 3: Konfigurace informací o aplikaci

1. V podokně **Přidat aplikaci** zvolte **Informace o aplikaci** a nakonfigurujte aplikaci.
2. V podokně **Informace o aplikaci** nakonfigurujte následující údaje. Některé hodnoty v tomto podokně mohou být vyplněné automaticky.
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
3. Až to budete mít, vyberte **OK**.

### <a name="step-4-configure-app-installation-details"></a>Krok 4: Konfigurace podrobností instalace aplikace
1. V podokně **Přidat aplikaci** vyberte **Program** a nakonfigurujte příkazy pro instalaci a odebrání aplikace.
2. Pokud chcete nakonfigurovat **příkaz Install**, přidejte k instalaci aplikace úplný příkazový řádek instalace. 

    Například pokud je název vaší aplikace **MyApp123**, přidejte následující:<br>
    `msiexec /p “MyApp123.msp”`<p>
    A pokud je aplikace `ApplicationName.exe`, příkaz by představoval název aplikace následovaný argumenty příkazu (přepínači) podporovanými balíčkem. <br>Příklad:<br>
    `ApplicationName.exe /quiet`<br>
    Ve výše uvedeném příkazu balíček `ApplicationName.exe` podporuje argument příkazu `/quiet`.<p> 
    Pro konkrétní argumenty podporované balíčkem aplikace se obraťte na dodavatele aplikace.

3. Chcete-li provést konfiguraci **příkazu Uninstall**, přidejte k odinstalaci aplikace na základě identifikátoru GUID aplikace úplný příkazový řádek pro odinstalaci. 

    Například: `msiexec /x “{12345A67-89B0-1234-5678-000001000000}”`

4. Nastavte **chování pro instalaci** buď na **systém** , nebo na **uživatele**.

    > [!NOTE]
    > Aplikaci Win32 můžete nakonfigurovat tak, aby se nainstalovala v kontextu **uživatele** nebo **systému**. Kontext **Uživatel** se vztahuje pouze k danému uživateli. Kontext **Systém** se vztahuje ke všem uživatelům zařízení s Windows 10.
    >
    > Koncoví uživatelé nemusí být kvůli instalaci aplikací Win32 přihlášení k zařízení.
    > 
    > Instalace a odinstalace aplikace Win32 se spustí v části oprávnění správce (ve výchozím nastavení), když je aplikace nastavená tak, aby se nainstalovala v uživatelském kontextu, a koncový uživatel na zařízení má oprávnění správce.

5. Pokud chcete nakonfigurovat **chování při restartování zařízení**, vyberte jednu z následujících možností:
    - **Určete chování na základě návratových kódů**: tuto možnost vyberte, pokud chcete zařízení restartovat podle nastavení konfigurace [návratových kódů](~/apps/apps-win32-app-management.md#step-7-configure-app-return-codes) .
    - **Žádná konkrétní akce**: tuto možnost vyberte, pokud chcete potlačit restartování zařízení během instalace aplikace založené na MSI.
    - **Instalace aplikace může vynutit restartování zařízení**: tuto možnost vyberte, pokud chcete, aby se instalace aplikace mohla dokončit bez potlačení restartování.
    - **Intune vynutí povinné restartování zařízení**: tuto možnost vyberte, když chcete zařízení po úspěšné instalaci aplikace vždycky restartovat.

6. Až to budete mít, vyberte **OK**.

### <a name="step-5-configure-app-requirements"></a>Krok 5: Konfigurace požadavků aplikace

1. V podokně **Přidat aplikaci** vyberte **Požadavky** a nakonfigurujte požadavky, které zařízení musí splnit, aby bylo možné aplikaci nainstalovat.
2. V podokně **Přidat pravidlo požadavku** nakonfigurujte následující informace. Některé hodnoty v tomto podokně mohou být vyplněné automaticky.
    - **Architektura operačního systému**: Zvolte architektury nutné k instalaci aplikace.
    - **Minimální operační systém**: Vyberte minimální operační systém potřebný k instalaci aplikace.
    - **Požadované místo na disku (MB)** : Volitelně přidejte volné místo na systémové jednotce pro instalaci aplikace.
    - **Požadovaná fyzická paměť (MB)** : Volitelně přidejte fyzickou paměť (RAM) nutnou pro instalaci aplikace.
    - **Minimální požadovaný počet logických procesorů**: Volitelně přidejte minimální počet logických procesorů požadovaných k instalaci aplikace.
    - **Minimální požadovaná rychlost CPU (MHz)** : Volitelně přidejte minimální rychlost procesoru, která se požaduje pro instalaci aplikace.

3. Kliknutím na tlačítko **Přidat** zobrazíte podokno **Přidat pravidlo požadavku** a nakonfigurujete další pravidla požadavků. Vyberte **typ požadavku** a zvolte typ pravidla, který budete používat k určení způsobu ověření požadavku. Pravidla požadavků můžou být založená na informacích o systému souborů, hodnotách registru nebo skriptech PowerShellu. 
    - **Soubor**: když jako **typ požadavku**zvolíte **soubor** , pravidlo požadavku musí detekovat soubor nebo složku, datum, verzi nebo velikost. 
        - **Cesta**: Úplná cesta ke složce obsahující soubor nebo složku, které se mají zjistit.
        - **Soubor nebo složka**: Soubor nebo složka, které se mají zjistit.
        - **Vlastnost** – vyberte typ pravidla, které se použije k ověření přítomnosti aplikace.
        - **Přidruženo k 32bitové aplikaci na 64bitových klientech**: Vyberte **Ano**, pokud chcete rozbalit všechny proměnné prostředí cesty ve 32bitovém kontextu na 64bitových klientech. Výchozí možnost **Ne** vyberte, pokud chcete rozbalit všechny proměnné cesty ve 64bitovém kontextu na 64bitových klientech. 32bitoví klienti budou vždy používat 32bitový kontext.
    - **Registr**: když jako **typ požadavku**zvolíte **registr** , pravidlo požadavku musí zjistit nastavení registru na základě hodnoty, řetězce, celého čísla nebo verze.
        - **Cesta ke klíči**: Úplná cesta k položce registru obsahující hodnotu, která se má zjistit.
        - **Název hodnoty**: Název hodnoty registru, která se má zjistit. Pokud je tato hodnota prázdná, provede se zjišťování u klíče. Hodnota klíče (výchozí) se použije jako hodnota zjišťování v případě, že se metoda zjišťování liší od metody zjišťování existence souboru nebo složky.
        - **Požadavek na klíč registru** – vyberte typ porovnání klíče registru používaného k určení způsobu ověření pravidla požadavku.
        - **Přidruženo k 32bitové aplikaci na 64bitových klientech**: Vyberte **Ano**, pokud chcete vyhledat 32bitový registr na 64bitových klientech. Výchozí možnost **Ne** vyberte, pokud chcete vyhledat 64bitový registr na 64bitových klientech. 32bitoví klienti budou vždy vyhledávat 32bitový registr.
    - **Skript**: Pokud nemůžete vytvořit pravidlo požadavku založené na souboru, registru nebo jiné metodě, kterou máte k dispozici v konzole Intune, vyberte **skript** jako **typ požadavku**.
        - **Soubor skriptu** – pro pravidlo požadavku na základě skriptu prostředí PowerShell, pokud existuje kód 0, zjistíme, že stdout bude více zjišťovat podrobněji. Můžete například detekovat STDOUT jako celé číslo s hodnotou 1.
        - **Spustit skript jako 32ový proces na 64 klientech** – vyberte **Ano** , pokud chcete skript spustit 32 v 16bitovém procesu 64 na 64bitových klientech. Pokud chcete spustit skript v 64 procesech na 64 klientech, vyberte **ne** (výchozí). 32-bitoví klienti spouštějí skript v procesu 32.
        - **Spusťte tento skript pomocí přihlašovacích údajů přihlášeného**: vyberte **Ano** , pokud chcete skript spustit pomocí přihlašovacích údajů přihlášeného zařízení * *.
        - **Vynutit kontrolu podpisu skriptu**: Vyberte **Ano**, pokud chcete ověřit, že skript je podepsán důvěryhodným vydavatelem. To skriptu umožní spouštět se bez zobrazení upozornění nebo výzev. Skript se bude spouštět odblokovaný. Výchozí možnost **Ne** vyberte, pokud chcete skript spouštět na základě potvrzení koncového uživatele bez ověření podpisu.
        - **Vyberte typ výstupních dat**: vyberte datový typ, který se použije při určování shody pravidla požadavku.
4. Až to budete mít, vyberte **OK**.

### <a name="step-6-configure-app-detection-rules"></a>Krok 6: Konfigurace pravidel zjišťování aplikace

1. V podokně **Přidat aplikaci** vyberte **Pravidla detekce** a nakonfigurujte pravidla pro zjištění přítomnosti aplikace.
2. V poli **Formát pravidel** vyberte, jak se bude přítomnost aplikace zjišťovat. Pravidla detekce můžete nakonfigurovat ručně, ale můžete použít i vlastní skript, který zjistí přítomnost aplikace. Musíte zvolit alespoň jedno pravidlo detekce. 

    > [!NOTE]
    > V podokně **Pravidla detekce** můžete zvolit přidání více pravidel. Podmínky **všech** pravidel se musí splnit, aby bylo možné aplikaci zjistit.
    >
    > Pokud Intune zjistí, že se aplikace v zařízení nenachází, Intune tuto aplikaci nabídne znovu za 24 hodin. Tato akce nastane jenom u aplikací, které cílí na povinný záměr.

    - **Ručně nakonfigurovat pravidla zjišťování**: Můžete vybrat jeden z následujících typů pravidel:
        1. **Instalační služba MSI**: Umožňuje provést ověření na základě kontroly verze MSI. Tuto možnost je možné přidat pouze jednou. Když zvolíte tento typ pravidla, máte dvě nastavení:
            - **Kód produktu Instalační služby MSI**: Přidá platný kód produktu MSI pro aplikaci.
            - **Kontrola verze produktu Instalační služby MSI**: Vyberte **Ano**, pokud chcete kromě kódu produktu MSI ověřit i verzi produktu MSI.
        2. **Soubor**: Umožňuje provést ověření na základě zjištění, data, verze nebo velikosti souboru nebo složky.
            - **Cesta**: Úplná cesta ke složce obsahující soubor nebo složku, které se mají zjistit.
            - **Soubor nebo složka**: Soubor nebo složka, které se mají zjistit.
            - **Metoda zjišťování**: Vyberte typ metody zjišťování použité k ověření přítomnosti aplikace.
            - **Přidruženo k 32bitové aplikaci na 64bitových klientech**: Vyberte **Ano**, pokud chcete rozbalit všechny proměnné prostředí cesty ve 32bitovém kontextu na 64bitových klientech. Výchozí možnost **Ne** vyberte, pokud chcete rozbalit všechny proměnné cesty ve 64bitovém kontextu na 64bitových klientech. 32bitoví klienti budou vždy používat 32bitový kontext.
            
            **Příklady zjišťování na základě souboru**
            1. Zkontrolujte, zda soubor existuje.
         
                ![Snímek obrazovky s podoknem pravidla detekce – existence souboru](./media/apps-win32-app-management/apps-win32-app-03.png)
        
            2. Zkontrolujte, zda složka existuje.
         
                ![Snímek obrazovky s podoknem pravidla detekce – existence složky](./media/apps-win32-app-management/apps-win32-app-04.png)
        
        3. **Registr**: Umožňuje provést ověření na základě verze, řetězce, celého čísla nebo verze.
            - **Cesta ke klíči**: Úplná cesta k položce registru obsahující hodnotu, která se má zjistit.
            - **Název hodnoty**: Název hodnoty registru, která se má zjistit. Pokud je tato hodnota prázdná, provede se zjišťování u klíče. Hodnota klíče (výchozí) se použije jako hodnota zjišťování v případě, že se metoda zjišťování liší od metody zjišťování existence souboru nebo složky.
            - **Metoda zjišťování**: Vyberte typ metody zjišťování použité k ověření přítomnosti aplikace.
            - **Přidruženo k 32bitové aplikaci na 64bitových klientech**: Vyberte **Ano**, pokud chcete vyhledat 32bitový registr na 64bitových klientech. Výchozí možnost **Ne** vyberte, pokud chcete vyhledat 64bitový registr na 64bitových klientech. 32bitoví klienti budou vždy vyhledávat 32bitový registr.
            
            **Příklady zjišťování na základě registru**
            1. Zkontrolujte, zda existuje klíč registru.
            
                ![Snímek obrazovky s podoknem pravidla detekce – existence klíče registru](./media/apps-win32-app-management/apps-win32-app-05.png)    
            
            2. Zkontroluje, jestli hodnota registru existuje.
        
                ![Snímek obrazovky s podoknem pravidla detekce – existence hodnoty registru](./media/apps-win32-app-management/apps-win32-app-06.png)    
        
            3. Zkontrolujte, zda se řetězec hodnoty registru rovná.
        
                ![Snímek obrazovky s podoknem pravidla detekce – řetězec hodnoty registru se rovná](./media/apps-win32-app-management/apps-win32-app-07.png)    
     
    - **Použít vlastní skript zjišťování**: Zadejte powershellový skript, který se použije ke zjištění této aplikace. 
    
        1. **Soubor skriptu**: Vyberte powershellový skript, který zjistí přítomnost aplikace v klientovi. Aplikace se bude považovat za zjištěnou, když skript vrátí ukončovací kód s hodnotou 0 a zapíše řetězcovou hodnotu do výstupu STDOUT.

        2. **Spustit skript jako 32ový proces na 64 klientech** – vyberte **Ano** , pokud chcete skript spustit 32 v 16bitovém procesu 64 na 64bitových klientech. Pokud chcete spustit skript v 64 procesech na 64 klientech, vyberte **ne** (výchozí). 32-bitoví klienti spouštějí skript v procesu 32.

        3. **Vynutit kontrolu podpisu skriptu**: Vyberte **Ano**, pokud chcete ověřit, že skript je podepsán důvěryhodným vydavatelem. To skriptu umožní spouštět se bez zobrazení upozornění nebo výzev. Skript se bude spouštět odblokovaný. Výchozí možnost **Ne** vyberte, pokud chcete skript spouštět na základě potvrzení koncového uživatele bez ověření podpisu.
    
            Agent Intune kontroluje výsledky ze skriptu. Přečte hodnoty, které skript zapsal do standardního streamu výstupu (STDOUT), standardního streamu chyb (STDERR) a do ukončovacího kódu. Pokud kód končí nenulovou hodnotu, skript selže a stav zjišťování aplikace je Nenainstalováno. Pokud ukončovací kód obsahuje nulovou hodnotu a výstup STDOUT obsahuje data, byl stav zjišťování aplikace je Nainstalováno. 

            > [!NOTE]
            > Microsoft doporučuje kódování skriptu jako UTF-8. Pokud se skript ukončí s hodnotou 0, bylo spuštění skriptu úspěšné. Sekundární výstupní kanál označuje, že aplikace byla zjištěna – data STDOUT označují, že aplikace se v klientovi našla. Konkrétnímu řetězci z výstupu STDOUT se nevěnujeme.

        4. Po přidání pravidel vyberte **Přidat** > **OK**.

### <a name="step-7-configure-app-return-codes"></a>Krok 7: Konfigurace návratových kódů aplikace

1. V podokně **Přidat aplikaci** vyberte **Návratové kódy** a přidejte návratové kódy, které se mají použít buď pro přidání chování při opakování instalace aplikace, nebo pro přidání chování po instalaci. Položky návratových kódů se standardně přidají při vytváření aplikace. Můžete ale přidat další nebo změnit existující návratové kódy. 
2. V podokně **Návratové kódy** přidejte další návratové kódy nebo změňte existující návratové kódy.
    - **Selhalo** – vrácená hodnota, která indikuje selhání instalace aplikace.
    - **Úplné restartování**: Návratový kód pro úplné restartování nepovolí instalaci dalších aplikací Win32 do klienta bez úplného restartování. 
    - **Rychlé restartování**: Návratový kód pro rychlé restartování umožní instalaci další aplikace Win32 bez nutnosti restartovat klienta. Restartování je důležité pro instalaci aktuální aplikace.
    - **Opakovat**: Agent návratového kódu pro opakování se třikrát pokusí aplikaci nainstalovat. Mezi jednotlivými pokusy počká 5 minut. 
    - **Úspěch**: Toto je návratový kód, který označuje, že se aplikace úspěšně nainstalovala.
3. Jakmile přidáte nebo změníte návratové kódy, vyberte **OK**.

### <a name="step-8-add-the-app"></a>Krok 8: Přidání aplikace

1. V podokně **Přidat aplikaci** zkontrolujte správnost nakonfigurovaných informací o aplikaci.
2. Pomocí možnosti **Přidat** nahrajte aplikaci do Intune.

### <a name="step-9-assign-the-app"></a>Krok 9: Přiřazení aplikace

1. V podokně aplikace vyberte **Přiřazení**.
2. Vyberte **Přidat skupinu**. Tím se otevře podokno **Přidat skupinu** týkající se aplikace.
3. Pro konkrétní aplikaci vyberte **typ přiřazení**:
    - **K dispozici zaregistrovaným zařízením**: Uživatelé nainstalují aplikaci z aplikace Portál společnosti nebo z webu Portál společnosti.
    - **Povinné**: Aplikace se nainstaluje na zařízení ve vybraných skupinách.
    - **Odinstalovat**: Aplikace se odinstaluje ze zařízení ve vybraných skupinách.
4. Vyberte **Zahrnuté skupiny** a přiřaďte skupiny, které budou tuto aplikaci používat.
5. V podokně **přiřadit** vyberte možnost přiřazení na základě uživatelů nebo zařízení. Když zvolíte přiřazení, můžete také zvolit **činnost koncového uživatele**. **Prostředí koncového uživatele** umožňuje nastavit **oznámení koncovým uživatelům**, **dobu odkladu pro restartování**, **dostupnost**a **konečný termín instalace**. Další informace najdete v tématu **Nastavení dostupnosti a oznámení aplikace Win32**.
6. výběrem **OK** dokončete výběr zahrnutých skupin.
7. Pokud se rozhodnete některé skupiny uživatelů vyloučit, aby nebyly přiřazením aplikace ovlivněné, klikněte na **Vyloučit skupiny**.
8. V podokně **Přidat skupinu** vyberte **OK**.
9. V podokně **Přiřazení** aplikace vyberte **Uložit**.

V tuto chvíli jste dokončili kroky pro přidání aplikace Win32 do Intune. Informace o přiřazení a monitorování aplikace najdete v článku [Přiřazení aplikací do skupin pomocí Microsoft Intune](apps-deploy.md) a [Monitorování informací a přiřazení aplikace pomocí Microsoft Intune](apps-monitor.md).

## <a name="app-dependencies"></a>Závislosti aplikací

Závislosti aplikací jsou aplikace, které je třeba nainstalovat, než bude možné nainstalovat aplikaci Win32. Můžete vyžadovat, aby byly další aplikace nainstalovány jako závislosti. Konkrétně musí zařízení před instalací aplikace Win32 nainstalovat závislé aplikace. Existuje maximálně 100 závislostí, které zahrnují závislosti všech zahrnutých závislostí a také samotnou aplikaci. Závislosti aplikace Win32 můžete přidat až po přidání a nahrání aplikace Win32 do Intune. Po přidání aplikace Win32 se zobrazí možnost **závislosti** v podokně aplikace Win32. 

Jakákoli závislost aplikace Win32 musí být také aplikací Win32. Nepodporuje se v závislosti na jiných typech aplikací, například na samostatných aplikacích MSI LOB nebo v aplikacích pro Store.

Při přidávání závislosti aplikace můžete vyhledávat podle názvu aplikace a vydavatele. Přidané závislosti můžete seřadit také na základě názvu a vydavatele aplikace. Dříve přidané závislosti aplikací nelze vybrat v seznamu závislostí přidaných aplikací. 

Můžete zvolit, jestli se mají automaticky instalovat jednotlivé závislé aplikace. Ve výchozím nastavení je možnost **automaticky instalovat** nastavená na **hodnotu Ano** pro každou závislost. Při automatické instalaci závislé aplikace, i když není závislá aplikace cílena na uživatele nebo zařízení, Intune nainstaluje aplikaci na zařízení, aby před instalací aplikace Win32 splňovala závislost. Je důležité si uvědomit, že závislost může mít rekurzivní závislosti a každá podřízená závislost bude nainstalována před instalací hlavní závislosti. Kromě toho instalace závislostí nedodržuje pořadí instalace na dané úrovni závislostí.

Chcete-li přidat závislost aplikace do aplikace Win32, použijte následující postup:

1. V Intune vyberte **aplikace** > **všech aplikacích** , abyste zobrazili seznam přidaných klientských aplikací. 
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

Pokud se rozhodnete, že nechcete **automatickou instalaci** závislosti, nebude proveden pokus o instalaci aplikace Win32. Kromě toho se v hlášení aplikace zobrazí, že tato závislost byla označena jako `failed` a také poskytuje důvod selhání. Selhání instalace závislosti můžete zobrazit kliknutím na chybu (nebo upozornění), která je k dispozici v [podrobnostech o instalaci](troubleshoot-app-install.md#win32-app-installation-troubleshooting)aplikace Win 32. 

Každá závislost bude odpovídat logice opakování aplikace Intune Win32 (zkuste nainstalovat třikrát po uplynutí 5 minut) a globální plán opakovaného vyhodnocení. Závislosti se taky použijí jenom v době instalace aplikace Win32 do zařízení. Závislosti nejsou k dispozici pro odinstalaci aplikace Win32. Pokud chcete závislost odstranit, musíte kliknout na elipsy (tři tečky) nalevo od závislé aplikace umístěné na konci řádku seznamu závislostí. 

## <a name="delivery-optimization"></a>Optimalizace doručení

Windows 10 1709 a novější klienti stáhnou obsah aplikace Intune Win32 pomocí součásti optimalizace doručování v klientovi s Windows 10. Optimalizace doručení poskytuje funkce peer-to-peer, které jsou ve výchozím nastavení zapnuté. Optimalizace doručení se dá nakonfigurovat pomocí zásad skupiny a pomocí konfigurace zařízení v Intune. Další informace najdete v tématu [optimalizace doručování pro Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization). 

> [!NOTE]
> Můžete taky nainstalovat server s připojenou mezipamětí Microsoft do distribučních bodů Configuration Manager pro ukládání obsahu aplikace Win32 v Intune. Další informace najdete v tématu věnovaném [podpoře aplikací pro Intune Win32 v Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/microsoft-connected-cache#bkmk_intune).

## <a name="install-required-and-available-apps-on-devices"></a>Instalace požadovaných a dostupných aplikací na zařízení

Koncový uživatel uvidí informační zprávy systému Windows pro požadované a dostupné instalace aplikací. Na následujícím obrázku je znázorněna ukázková informační zpráva, že instalace aplikace se nedokončí, dokud se zařízení nerestartuje. 

![Snímek obrazovky s oznámeními informačních zpráv systému Windows pro instalaci aplikace](./media/apps-win32-app-management/apps-win32-app-08.png)    

Následující obrázek upozorní koncového uživatele, že se na zařízení provádí změny aplikace.

![Snímek obrazovky oznamující uživateli, že probíhají změny aplikace](./media/apps-win32-app-management/apps-win32-app-09.png)    

## <a name="set-win32-app-availability-and-notifications"></a>Nastavení dostupnosti a oznámení aplikace Win32
Můžete nakonfigurovat čas zahájení a konečný termín pro aplikaci Win32. V počátečním čase rozšíření pro správu Intune spustí stažení obsahu aplikace a uloží je do mezipaměti pro požadovaný záměr. Aplikace se nainstaluje v čase konečného termínu. V případě dostupných aplikací se čas spuštění určí při zobrazení aplikace v Portál společnosti a obsah se stáhne, když koncový uživatel požádá aplikaci z Portál společnosti. Navíc můžete povolit dobu odkladu pro restartování. 

Nastavte dostupnost aplikace na základě data a času požadované aplikace pomocí následujících kroků:

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vyberte **aplikace** > **všech aplikacích**.
3. Vyberte ze seznamu existující **aplikaci pro Windows (Win32)** . 
4. V podokně aplikace vyberte **přiřazení** > **Přidat skupinu**. 
5. **Typ přiřazení** nastavte na **Povinné**. Všimněte si, že dostupnost aplikace se dá nastavit na základě typu přiřazení. **Typ přiřazení** může být **povinný**, **dostupný pro zaregistrovaná zařízení**nebo **odinstalovat**.
6. Vyberte **zahrnuté skupiny** a určete, ke které skupině uživatelů se aplikace přiřadí. Zobrazí se podokno **přiřazení** .
7. Nastavte nastavit **tuto aplikaci jako povinnou pro všechny uživatele** na **Ano**.

    > [!NOTE]
    > Mezi možnosti **typu přiřazení** patří následující:<br>
    > - **Požadováno**: tuto aplikaci si můžete **nastavit jako povinnou pro všechny uživatele** nebo **nastavit tuto aplikaci jako povinnou na všech zařízeních**.<br>
    > - **K dispozici pro zaregistrovaná zařízení**: tuto aplikaci můžete nastavit tak, aby byla **dostupná pro všechny uživatele s registrovanými zařízeními**.<br>
    > - **Odinstalace**: můžete si vybrat možnost ***odinstalovat tuto aplikaci pro všechny uživatele** nebo **odinstalovat tuto aplikaci pro všechna zařízení**.

8. Chcete-li upravit možnosti **prostředí koncového uživatele** , vyberte možnost **Upravit**.
9. V podokně **Upravit přiřazení** nastavte **oznámení pro uživatele Ender** , aby se **zobrazila všechna informační oznámení**. Všimněte si, že můžete nastavit **oznámení koncových uživatelů** a **Zobrazit všechna informační oznámení**, **Zobrazit informační zprávy pro restartování počítače**nebo **Skrýt všechna informační oznámení**.
10. Nastavte **Dostupnost aplikace** na **konkrétní datum a čas** a vyberte datum a čas. Toto datum a čas určuje, kdy se aplikace stáhne do zařízení koncových uživatelů. 
11. Nastavte **konečný termín instalace aplikace** na **konkrétní datum a čas** a vyberte datum a čas. Toto datum a čas určuje, kdy se aplikace nainstaluje na koncové uživatele. Pokud se pro stejného uživatele nebo zařízení provede více než jedno přiřazení, bude čas konečného termínu instalace aplikace vyzvednut na základě nejdřívějšího možného času.
12. Klikněte na **povoleno** vedle **období odkladu pro restartování**. Doba odkladu restartování se spustí hned po dokončení instalace aplikace na zařízení. Když je tato možnost zakázaná, může se zařízení bez upozornění restartovat. <br>Můžete přizpůsobit následující možnosti:
    - **Doba odkladu pro restartování zařízení (minuty)** : výchozí hodnota je 1440 minut (24 hodin). Tato hodnota může být maximálně 2 týdny.
    - **Vyberte, kdy se má zobrazit dialogové okno odpočítávání před restartováním (minuty)** : výchozí hodnota je 15 minut.
    - **Dovolit uživateli odložit oznámení o restartování**: můžete vybrat **Ano** nebo **ne**.
        - **Vyberte dobu opakovaného přiložení (minuty)** : výchozí hodnota je 240 minut (4 hodiny). Hodnota pro odložení nemůže být delší než doba odkladu pro restartování.
13. Kliknutím na OK ** > ok** > **OK** > **Save (Uložit** ) přidejte přiřazení.

## <a name="toast-notifications-for-win32-apps"></a>Oznámení informačních zpráv pro aplikace Win32 
V případě potřeby můžete potlačit zobrazování oznámení informační zprávy koncového uživatele na přiřazení aplikace. V Intune vyberte **aplikace** > **všechny aplikace** > vyberte **přiřazení** > aplikací > **Zahrnout skupiny**. 

> [!NOTE]
> Rozšíření pro správu Intune nainstalované aplikace Win32 se odinstalují na nezaregistrovaných zařízeních. Správci můžou využít vyloučení přiřazení, aby nenabízeli aplikacím Win32 možnost BYOD zařízení.

## <a name="troubleshoot-win32-app-issues"></a>Řešení potíží s aplikacemi Win32
Protokoly agenta na klientském počítači se obvykle nachází ve složce `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs`. K zobrazení těchto protokolů můžete využít nástroj `CMTrace.exe`. Další informace najdete v tématu [CMTrace](https://docs.microsoft.com/configmgr/core/support/cmtrace).

![Snímek obrazovky protokolů agenta v klientském počítači](./media/apps-win32-app-management/apps-win32-app-10.png)    

> [!IMPORTANT]
> Aby bylo možné správně nainstalovat a spustit aplikace pro obchodní prostředí Win32, nastavení antimalwarového programu by mělo vyloučit následující adresáře, aby byly prohledávány:<p>
> **Na klientských počítačích x64**:<br>
> *C:\Program Files (x86)\Microsoft Intune Management Extension\Content*<br>
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

Ve výše uvedeném příkazu PowerShellu nahraďte `<path to binary file>` cestou k souboru.

### <a name="additional-troubleshooting-areas-to-consider"></a>Další oblasti řešení potíží, které je potřeba zvážit
- Zkontroluje cílení, abyste měli jistotu, že je agent nainstalovaný na zařízení – aplikace Win32 zacílená na skupinu nebo powershellový skript zacílený na skupinu vytvoří zásady instalace agenta pro skupinu zabezpečení.
- Zkontrolujte verzi operačního systému – Windows 10 1607 a novější.  
- Zkontrolujte skladovou položku Windows 10 – Windows 10 S nebo verze Windows s povoleným režimem S nepodporují instalaci pomocí instalační služby MSI.

Další informace o řešení potíží s aplikacemi Win32 najdete v tématu [řešení potíží s instalací aplikací Win32](troubleshoot-app-install.md#win32-app-installation-troubleshooting).

## <a name="next-steps"></a>Další kroky

- Další informace o přidávání aplikací do Intune najdete v článku [Přidání aplikací do Microsoft Intune](apps-add.md).
