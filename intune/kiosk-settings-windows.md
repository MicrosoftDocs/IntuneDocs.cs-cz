---
title: Nastavení veřejného terminálu pro Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Nakonfigurujte zařízení s Windows 10 (a novějšími) jako veřejné terminály s jednou aplikací a více aplikacemi, přizpůsobte nabídku Start, přidejte aplikace, zobrazte panel úloh a nakonfigurujte webový prohlížeč v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/15/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6fb1111a7f660e8c59f45fb1893364dcadd34dca
ms.sourcegitcommit: 6a8de7bb4870ea19aa08db1f188ea7b5e8a387dd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/15/2019
ms.locfileid: "69487756"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-kiosk-in-intune"></a>Nastavení zařízení s Windows 10 a novějším, která se mají spustit jako veřejný terminál v Intune

V zařízeních se systémem Windows 10 nebo novějším můžete tato zařízení nakonfigurovat tak, aby běžela v celoobrazovkovém režimu jedné aplikace nebo celoobrazovkovém režimu s více aplikacemi.

Tento článek obsahuje seznam a popis různých nastavení, která můžete řídit na zařízeních s Windows 10 a novějších. Jako součást řešení správy mobilních zařízení (MDM) pomocí těchto nastavení můžete nakonfigurovat zařízení s Windows 10 a novějším tak, aby běžela v celoobrazovkovém režimu.

Jako správce Intune můžete vytvořit a přiřadit tato nastavení k vašim zařízením.

Další informace o funkci veřejného terminálu Windows v Intune najdete v tématu [Konfigurace nastavení veřejného terminálu](kiosk-settings.md).

## <a name="before-you-begin"></a>Před zahájením

- [Vytvořte profil](kiosk-settings.md#create-the-profile).

- Tento profil veřejného terminálu přímo souvisí s profilem omezení zařízení, které vytvoříte pomocí [nastavení Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser)na veřejném terminálu. Sumarizace:

  1. Vytvořte tento profil veřejného terminálu pro spuštění zařízení v celoobrazovkovém režimu.
  2. Umožňuje vytvořit [profil omezení zařízení](device-restrictions-windows-10.md#microsoft-edge-browser)a nakonfigurovat konkrétní funkce a nastavení povolená v Microsoft Edge.

> [!IMPORTANT] 
> Ujistěte se, že tento profil pro terminál přiřadíte ke stejným zařízením jako váš [profil Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser).

## <a name="single-full-screen-app-kiosks"></a>Veřejné terminály s jednou aplikací v režimu na celou obrazovku

Spustí na zařízení jenom jednu aplikaci.

- **Vyberte celoobrazovkový režim**: Vyberte možnost **jediná aplikace, celoobrazovkový terminál**.

- **Typ přihlášení uživatele**: Aplikace, které přidáte, se spustí jako uživatelský účet, který zadáte. Možnosti:

  - **Automatické přihlašování (Windows 10 verze 1803 a novější)** : Používejte na terminálech ve veřejných prostředích, která nevyžadují, aby se uživatel přihlásil, podobně jako účet Guest. Toto nastavení využívá [poskytovatele konfiguračních služeb AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Místní uživatelský účet**: Zadejte místní uživatelský účet (zařízení). Účet, který zadáte, se přihlaste k veřejnému terminálu.

- **Typ aplikace**: Vyberte typ aplikace. Možnosti:

  - **Přidat prohlížeč Microsoft Edge**: Vyberte **prohlížeč Microsoft Edge**a zvolte **Typ režimu celoobrazovkového**na okraji:

    - **Digitální a interaktivní podpis**: Otevře adresu URL na celé obrazovce a zobrazí jenom obsah na tomto webu. [Nastavení digitální znaménka](https://docs.microsoft.com/windows/configuration/setup-digital-signage) poskytuje další informace o této funkci.
    - **Veřejné procházení (InPrivate)** : Spouští omezené víceúrovňové verze Microsoft Edge. Uživatelé můžou procházet veřejně nebo ukončit jejich relaci procházení.

    Další informace o těchto možnostech najdete v tématu [nasazení celoobrazovkového režimu Microsoft Edge](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

    > [!NOTE]
    > Toto nastavení povolí prohlížeči Microsoft Edge na zařízení. Pokud chcete nakonfigurovat nastavení specifické pro Microsoft Edge, vytvořte profil konfigurace zařízení (**Konfigurace** > zařízení**profily** > **vytvořit profil** > **Windows 10** pro platformu >Omezení >  zařízení**prohlížeč Microsoft Edge**. Seznam dostupných nastavení najdete v [prohlížeči Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser) .

  - **Přidat webový prohlížeč**na veřejném terminálu: Vyberte **nastavení prohlížeče veřejného terminálu**. Tato nastavení řídí aplikaci webového prohlížeče na veřejném terminálu. Ujistěte se, že jste si z obchodu získali [aplikaci celoobrazovkového prohlížeče](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) , přidejte ji do Intune jako [klientskou aplikaci](apps-add.md). Pak aplikaci přiřaďte k veřejnému zařízení.

    Zadejte následující nastavení:

    - **Adresa URL výchozí domovské stránky**: Zadejte výchozí adresu URL, která se zobrazí, když se otevře prohlížeč veřejného terminálu nebo když se prohlížeč restartuje. Zadejte například `http://bing.com` nebo `http://www.contoso.com`.

    - **Tlačítko domů**: **Umožňuje zobrazit** nebo **Skrýt** tlačítko domů v prohlížeči veřejného terminálu. Ve výchozím nastavení se tlačítko nezobrazuje.

    - **Navigační tlačítka**: **Zobrazí** nebo **skryje** tlačítka pro přeposílání a zpět. Ve výchozím nastavení se navigační tlačítka nezobrazují.

    - **Tlačítko ukončit relaci**: **Zobrazí** nebo **skryje** tlačítko ukončit relaci. Když je zobrazené a uživatel tlačítko vybere, dojde k výzvě pro ukončení relace. Po potvrzení prohlížeč vymaže všechny údaje o procházení (soubory cookie, mezipaměť atd.) a otevře výchozí adresu URL. Ve výchozím nastavení se tlačítko nezobrazuje.

    - **Aktualizovat prohlížeč po době nečinnosti**: Zadejte dobu nečinnosti (1-1440 minut), dokud se prohlížeč veřejného terminálu nerestartuje v neaktivním stavu. Doba nečinnosti se udává v minutách a označuje dobu, která uplynula od poslední interakce uživatele. Ve výchozím nastavení je hodnota prázdná, což znamená, že neexistuje žádný časový limit nečinnosti.

    - **Povolené weby**: Pomocí tohoto nastavení můžete uživatelům dovolit, aby otevřeli jednotlivé weby. Jinými slovy, tuto funkci použijte k omezení nebo zabránění spouštění webů na zařízení. Můžete například povolit, aby se otevíraly všechny weby na `http://contoso.com*`. Ve výchozím nastavení jsou povolené všechny weby.

      Pokud chcete povolit konkrétní weby, nahrajte soubor, který obsahuje seznam povolených webů na samostatných řádcích. Pokud soubor nepřidáte, jsou povolené všechny weby. Intune podporuje `*` (hvězdičku) jako zástupnou kartu.

      Váš ukázkový soubor by se měl podobat následujícímu seznamu:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`

    > [!NOTE]
    > Veřejné terminály s Windows 10 s povoleným přihlašováním pomocí prohlížeče veřejného terminálu Microsoftu musí používat licenci offline od Microsoft Store pro firmy. Důvodem je to, že automatické přihlašování používá místní uživatelský účet bez přihlašovacích údajů Azure Active Directory (AD). Licence Online proto nejde vyhodnotit. Další informace najdete v tématu [distribuce offline aplikací](https://docs.microsoft.com/microsoft-store/distribute-offline-apps).

  - **Přidat aplikaci ze Storu**: Vyberte **Přidat aplikaci ze Storu**a zvolte aplikaci ze seznamu.

    Nejsou v seznamu žádné aplikace? Přidejte aplikace pomocí postupu v části [Klientské aplikace](apps-add.md).

## <a name="multi-app-kiosks"></a>Veřejné terminály s více aplikacemi

Aplikace v tomto režimu jsou k dispozici v nabídce Start. Tyto aplikace jsou jedinými aplikacemi, které může uživatel spustit. Pokud má aplikace závislost na jiné aplikaci, musí být v seznamu povolené aplikace zahrnutá obě. Například v aplikaci Internet Explorer 64-bit je závislá na aplikaci Internet Explorer 32-bit, takže je třeba umožnit možnost "C:\Program Files\internet Explorer\iexplore.exe" a "C:\Program Files (x86) \Internet Explorer\iexplore.exe". 

- **Vyberte celoobrazovkový režim**: Vyberte veřejný **terminál s více aplikacemi**.

- **Cílová zařízení s Windows 10 v režimu S**:
  - **Ano**: Povoluje aplikace pro Store a aplikace AUMID (nezahrnuje aplikace Win32) v profilu veřejného terminálu.
  - **Ne**: Umožňuje aplikace pro Store, aplikace Win32 a aplikace AUMID v profilu veřejného terminálu. Tento profil veřejného terminálu není nasazený do zařízení S režimem S.

- **Typ přihlášení uživatele**: Aplikace, které přidáte, se spustí jako uživatelský účet, který zadáte. Možnosti:

  - **Automatické přihlašování (Windows 10 verze 1803 a novější)** : Používejte na terminálech ve veřejných prostředích, která nevyžadují, aby se uživatel přihlásil, podobně jako účet Guest. Toto nastavení využívá [poskytovatele konfiguračních služeb AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Místní uživatelský účet**: **Přidejte** místní uživatelský účet (do zařízení). Účet, který zadáte, se přihlaste k veřejnému terminálu.
  - **Uživatel nebo skupina Azure AD (Windows 10 verze 1803 a novější)** : Vyberte **Přidat**a v seznamu zvolte uživatelé nebo skupiny Azure AD. Můžete vybrat více uživatelů a skupin. Zvolením možnosti **Vybrat** uložte změny.
  - **Návštěvník HoloLens**: Účet návštěvníka je účet hosta, který nevyžaduje žádné přihlašovací údaje ani ověřování uživatele, jak je popsáno v tématu [Koncepty v režimu sdílené počítače](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Prohlížeč a aplikace**: Přidejte aplikace, které se mají spustit na veřejném zařízení. Nezapomeňte, že můžete přidat několik aplikací.

  - **Nimi**

    - **Přidat Microsoft Edge**: Microsoft Edge se přidá do mřížky aplikace a všechny aplikace můžou běžet na tomto veřejném terminálu. Vyberte **typ beznabídkového režimu Microsoft Edge**:

      - **Normální režim (plná verze Microsoft Edge)** : Spustí plnou verzi Microsoft Edge se všemi funkcemi pro procházení. Data a stav uživatele jsou ukládána mezi relacemi.
      - **Veřejné procházení (InPrivate)** : Spustí na více kartách verzi Microsoft Edge InPrivate s přizpůsobeným prostředím pro veřejné terminály, které běží v režimu celé obrazovky.

      Další informace o těchto možnostech najdete v tématu [nasazení celoobrazovkového režimu Microsoft Edge](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

      > [!NOTE]
      > Toto nastavení povolí prohlížeči Microsoft Edge na zařízení. Pokud chcete nakonfigurovat nastavení specifické pro Microsoft Edge, vytvořte profil konfigurace zařízení (**Konfigurace** > zařízení**profily** > **vytvořit profil** > **Windows 10** pro platformu >Omezení >  zařízení**prohlížeč Microsoft Edge**. Seznam dostupných nastavení najdete v [prohlížeči Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser) .

    - **Přidat webový prohlížeč**na veřejném terminálu: Tato nastavení řídí aplikaci webového prohlížeče na veřejném terminálu. K nasazení aplikace webového prohlížeče do zařízení s beznabídkovým režimem použijte [klientské aplikace](apps-add.md).

      Zadejte následující nastavení:

      - **Adresa URL výchozí domovské stránky**: Zadejte výchozí adresu URL, která se zobrazí, když se otevře prohlížeč veřejného terminálu nebo když se prohlížeč restartuje. Zadejte například `http://bing.com` nebo `http://www.contoso.com`.

      - **Tlačítko domů**: **Umožňuje zobrazit** nebo **Skrýt** tlačítko domů v prohlížeči veřejného terminálu. Ve výchozím nastavení se tlačítko nezobrazuje.

      - **Navigační tlačítka**: **Zobrazí** nebo **skryje** tlačítka pro přeposílání a zpět. Ve výchozím nastavení se navigační tlačítka nezobrazují.

      - **Tlačítko ukončit relaci**: **Zobrazí** nebo **skryje** tlačítko ukončit relaci. Když je zobrazené a uživatel tlačítko vybere, dojde k výzvě pro ukončení relace. Po potvrzení prohlížeč vymaže všechny údaje o procházení (soubory cookie, mezipaměť atd.) a otevře výchozí adresu URL. Ve výchozím nastavení se tlačítko nezobrazuje.

      - **Aktualizovat prohlížeč po době nečinnosti**: Zadejte dobu nečinnosti (1-1440 minut), dokud se prohlížeč veřejného terminálu nerestartuje v neaktivním stavu. Doba nečinnosti se udává v minutách a označuje dobu, která uplynula od poslední interakce uživatele. Ve výchozím nastavení je hodnota prázdná, což znamená, že neexistuje žádný časový limit nečinnosti.

      - **Povolené weby**: Pomocí tohoto nastavení můžete uživatelům dovolit, aby otevřeli jednotlivé weby. Jinými slovy, tuto funkci použijte k omezení nebo zabránění spouštění webů na zařízení. Můžete například povolit, aby se otevíraly všechny weby na `contoso.com*`. Ve výchozím nastavení jsou povolené všechny weby.

        Pokud chcete povolit konkrétní weby, nahrajte soubor CSV, který obsahuje seznam povolených webů. Pokud soubor CSV nepřidáte, budou povolené všechny weby.

      > [!NOTE]
      > Veřejné terminály s Windows 10 s povoleným přihlašováním pomocí prohlížeče veřejného terminálu Microsoftu musí používat licenci offline od Microsoft Store pro firmy. Důvodem je to, že automatické přihlašování používá místní uživatelský účet bez přihlašovacích údajů Azure Active Directory (AD). Licence Online proto nejde vyhodnotit. Další informace najdete v tématu [distribuce offline aplikací](https://docs.microsoft.com/microsoft-store/distribute-offline-apps).

  - **Vyrovnání**

    - **Přidat aplikaci ze Storu**: Přidejte aplikaci z Microsoft Store pro firmy. Pokud nejsou zobrazené žádné aplikace, můžete je získat a [přidat do Intune](store-apps-windows.md). Můžete například přidat Kiosk Browser, Excel, OneNote a další.

    - **Přidat aplikaci Win32**: Aplikace Win32 je tradiční desktopová aplikace, například Visual Studio Code nebo Google Chrome. Zadejte tyto vlastnosti:

      - **Název aplikace**: Povinný parametr. Zadejte název aplikace.
      - **Místní cesta**: Povinný parametr. Zadejte cestu ke spustitelnému souboru, například `C:\Program Files (x86)\Microsoft VS Code\Code.exe` nebo `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
      - **ID modelu uživatele aplikace (AUMID)** : Zadejte ID modelu uživatele aplikace (AUMID) aplikace Win32. Toto nastavení určuje rozložení nabídky Start na dlaždici na ploše. Pokud chcete získat toto ID, přečtěte si téma [Get-StartApps](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps).

    - **Přidat podle AUMID**: Tuto možnost použijte, pokud chcete přidat aplikace pro Windows doručené pošty, například Poznámkový blok nebo Kalkulačka. Zadejte tyto vlastnosti:

      - **Název aplikace**: Povinný parametr. Zadejte název aplikace.
      - **ID modelu uživatele aplikace (AUMID)** : Povinný parametr. Zadejte ID modelu uživatele aplikace (AUMID) aplikace pro Windows. Pokud chcete získat toto ID, přečtěte si článek o tom, [jak u nainstalované aplikace najít ID modelu uživatele aplikace](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

    - **Spustit**znovu: Volitelný parametr. Vyberte aplikaci, která se má spustit, když se uživatel přihlásí. Spustit se dá jenom jedna aplikace.
    - **Velikost dlaždice**: Povinný parametr. Zvolte velikost dlaždice aplikace – malá, střední, široká nebo velká.

  > [!TIP]
  > Po přidání všech aplikací můžete změnit pořadí zobrazování tak, že na aplikace v seznamu kliknete a pomocí myši je přetáhnete, kam potřebujete.  

- **Použít alternativní počáteční rozložení**: Vyberte **Ano** , pokud chcete zadat soubor XML, který popisuje, jak se aplikace objeví v nabídce Start, včetně pořadí aplikací. Tuto možnost použijte, pokud v nabídce Start potřebujete větší míru přizpůsobení. V článku [Přizpůsobení a export rozložení nabídky Start](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) najdete pokyny a ukázkový soubor XML.

- **Hlavní panel Windows**: Vyberte, chcete-li **Zobrazit** nebo **Skrýt** hlavní panel. Ve výchozím nastavení se hlavní panel nezobrazuje. Ikony, jako je ikona sítě Wi-Fi, se zobrazí, ale koncoví uživatelé je nemůžou změnit.

- **Povolení přístupu ke složce stažené soubory**: Vyberte **Ano** , pokud chcete, aby uživatelé měli přístup ke složce stažené soubory v Průzkumníkovi Windows. Ve výchozím nastavení je přístup ke složce stažené soubory zakázán. Tato funkce se běžně používá pro koncové uživatele k přístupu k položkám staženým z prohlížeče.

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Můžete také vytvořit profily celoobrazovkového pro zařízení [](device-restrictions-android.md#kiosk)s Androidem, [Androidem Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings)a [Windows holografickým pro firmy](kiosk-settings-holographic.md) .
