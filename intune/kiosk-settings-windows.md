---
title: Nastavení veřejného terminálu pro Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Konfigurace zařízení s Windows 10 (a novější) jako veřejné terminály jedné aplikace a s více aplikacemi, přizpůsobení nabídky start, přidejte aplikace, zobrazit na hlavním panelu a konfigurace webového prohlížeče v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/13/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 78b47decc297c58feadb7cd507a3ff09070d46d4
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565736"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-kiosk-in-intune"></a>Windows 10 a novější zařízení nastavení pro spuštění jako veřejný terminál v Intune

V systému Windows 10 a novější zařízení můžete nakonfigurovat tato zařízení ke spuštění v režimu jedné aplikace veřejného terminálu, nebo režim veřejný terminál s více aplikacemi.

Tento článek uvádí a popisuje různá nastavení, které můžete řídit na Windows 10 a novější zařízení. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení konfigurace Windows 10 a novější zařízení v beznabídkovém režimu spouštět.

Jako správce Intune můžete vytvořit a přiřadit tato nastavení do zařízení.

Další informace o funkci Windows veřejného terminálu v Intune najdete v tématu [nakonfigurovat nastavení beznabídkového režimu](kiosk-settings.md).

## <a name="before-you-begin"></a>Před zahájením

- [Vytvoření profilu](kiosk-settings.md#create-the-profile).

- Tento profil beznabídkového režimu přímo souvisí s profil omezení zařízení můžete vytvořit pomocí [nastavení beznabídkového režimu Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser). Shrnutí:

  1. Vytvořte tento profil beznabídkového režimu pro zařízení v beznabídkovém režimu spouštět.
  2. Vytvořte [profil omezení zařízení](device-restrictions-windows-10.md#microsoft-edge-browser)a konfigurovat konkrétní funkce a nastavení povolená v Microsoft Edge.

> [!IMPORTANT] 
> Je potřeba přiřadit tento profil beznabídkového režimu pro stejné zařízení jako vaše [profil Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser).

## <a name="single-full-screen-app-kiosks"></a>Veřejné terminály s jednou aplikací v režimu na celou obrazovku

Na zařízení spustí jenom jedna aplikace.

- **Vyberte režim veřejného terminálu**: Zvolte **aplikace s jedním, celoobrazovkového**.

- **Typ přihlášení uživatele**: Aplikace, které přidáte účet Spustit jako uživatele, které zadáte. Možnosti:

  - **Automatické přihlašování (Windows 10 verze 1803 nebo novější)**: Použít na veřejné terminály ve veřejných prostředích, které nevyžadují uživatel přihlásil, podobně jako pomocí účtu guest. Toto nastavení využívá [poskytovatele konfiguračních služeb AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Místní uživatelský účet**: Zadejte místní (pro zařízení) uživatelského účtu. Účet, že zadejte přihlásí na veřejném terminálu.

- **Typ aplikace**: Vyberte typ aplikace. Možnosti:

  - **Přidejte prohlížeče Microsoft Edge**: Vyberte **prohlížeč Microsoft Edge**a zvolte **hraniční typ režimu veřejného terminálu**:

    - **Digitální/Interaktivní značky**: Otevře na celé obrazovce adresu URL a zobrazuje pouze obsah na daném webu. [Nastavit příznaky digitální](https://docs.microsoft.com/windows/configuration/setup-digital-signage) poskytuje další informace o této funkci.
    - **Veřejné procházení (InPrivate)**: Běží omezená více karet verze Microsoft Edge. Uživatelé mohou procházet veřejně nebo ukončení relace jejich procházení.

    Další informace o těchto možnostech najdete v tématu [celoobrazovkový režim nasazení Microsoft Edge](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

    > [!NOTE]
    > Toto nastavení umožňuje prohlížeč Microsoft Edge na zařízení. Ke konfiguraci nastavení specifické pro společnost Microsoft Edge, vytvořit profil konfigurace zařízení (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **Windows 10** pro platformu > **omezení zařízení** >  **prohlížeče Microsoft Edge**). [Prohlížeč Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser) uvádí a popisuje dostupná nastavení.

    Vyberte **OK** uložte provedené změny.

  - **Přidat prohlížeči Kiosk**: Vyberte **nastavení beznabídkového režimu prohlížeče**. Tato nastavení řídí aplikaci webového prohlížeče na veřejném terminálu. Ujistěte se, získáte [aplikace Kiosk browser](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) z Store, přidejte ho do Intune jako [klientskou aplikaci](apps-add.md)a pak přiřadíte tuto aplikaci do zařízení v celoobrazovkovém režimu.

    Zadejte následující nastavení:

    - **Výchozí adresa URL domovské stránky**: Zadejte výchozí adresa URL zobrazí při otevření prohlížeči kiosk nebo při restartování prohlížeče. Zadejte například `http://bing.com` nebo `http://www.contoso.com`.

    - **Tlačítko Domů**: **Zobrazit** nebo **skrýt** tlačítko Domů prohlížeče veřejného terminálu. Ve výchozím nastavení se tlačítko nezobrazuje.

    - **Navigační tlačítka**: **Zobrazit** nebo **skrýt** tlačítka vpřed a zpět. Ve výchozím nastavení se navigační tlačítka nezobrazují.

    - **Ukončení relace tlačítko**: **Zobrazit** nebo **skrýt** tlačítko end relace. Když je zobrazené a uživatel tlačítko vybere, dojde k výzvě pro ukončení relace. Po potvrzení prohlížeč vymaže všechny údaje o procházení (soubory cookie, mezipaměť atd.) a otevře výchozí adresu URL. Ve výchozím nastavení se tlačítko nezobrazuje.

    - **Aktualizujte prohlížeč po nečinnosti**: Zadejte dobu nečinnosti (1 až 1440 v minut) dokud prohlížeči kiosk restartování do původního stavu. Doba nečinnosti se udává v minutách a označuje dobu, která uplynula od poslední interakce uživatele. Ve výchozím nastavení je hodnota prázdná, což znamená, že neexistuje žádný časový limit nečinnosti.

    - **Povolené websites**: Pomocí tohoto nastavení můžete povolit určité weby na Otevřít. Jinými slovy, tuto funkci použijte k omezení nebo zabránění spouštění webů na zařízení. Můžete například povolit, aby se otevíraly všechny weby na `http://contoso.com*`. Ve výchozím nastavení jsou povolené všechny weby.

      Pokud chcete povolit konkrétní weby, nahrajte soubor, který obsahuje seznam povolených webů na samostatných řádcích. Pokud soubor nepřidáte, jsou povolené všechny weby. Intune podporuje `*` (hvězdička) jako zástupný znak.

      Váš ukázkový soubor by se měl podobat následujícímu seznamu:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`  

    Vyberte **OK** uložte provedené změny.

  - **Přidat aplikaci Store**: Vyberte **přidání aplikace ze storu**a vyberte aplikaci ze seznamu.

    Nejsou v seznamu žádné aplikace? Přidejte aplikace pomocí postupu v části [Klientské aplikace](apps-add.md).

  Vyberte **OK** uložte provedené změny.

## <a name="multi-app-kiosks"></a>Veřejné terminály s více aplikacemi

Aplikace v tomto režimu jsou k dispozici v nabídce Start. Tyto aplikace jsou jedinými aplikacemi, které může uživatel spustit. Pokud aplikace obsahuje závislost na jiné aplikace, obě musí být součástí seznamu povolených aplikací. Například Internet Explorer 64-bit závislý na Internet Explorer 32-bit, takže je potřeba povolit "C:\Program Files\internet explorer\iexplore.exe" a "C:\Program Files (x86) \Internet". 

- **Vyberte režim veřejného terminálu**: Zvolte **veřejný terminál s více aplikacemi**.

- **Cíl v režimu zařízení S Windows 10**:
  - **Ano**: Umožňuje profil beznabídkového režimu, aplikace pro store a AUMID aplikace (kromě aplikací Win32).
  - **Ne**: Umožňuje AUMID aplikace, aplikace pro store a aplikace Win32 v profil beznabídkového režimu. Tento profil beznabídkového režimu není nasazený do zařízení S režimu.

- **Typ přihlášení uživatele**: Aplikace, které přidáte účet Spustit jako uživatele, které zadáte. Možnosti:

  - **Automatické přihlašování (Windows 10 verze 1803 nebo novější)**: Použít na veřejné terminály ve veřejných prostředích, které nevyžadují uživatel přihlásil, podobně jako pomocí účtu guest. Toto nastavení využívá [poskytovatele konfiguračních služeb AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Místní uživatelský účet**: **Přidat** místním (zařízení) uživatelského účtu. Účet, že zadejte přihlásí na veřejném terminálu.
  - **Azure AD uživateli nebo skupině (Windows 10 verze 1803 nebo novější)**: Vyberte **přidat**a zvolte ze seznamu uživatelů Azure AD nebo skupinám. Můžete vybrat více uživatelů a skupin. Zvolením možnosti **Vybrat** uložte změny.
  - **Návštěvník HoloLens**: Návštěvník účet je účet guest, který nevyžaduje žádné přihlašovací údaje uživatele nebo ověřování, jak je popsáno v [sdílí koncepty režimu PC](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Prohlížeče a aplikace**: Přidání aplikací pro spuštění na zařízení beznabídkového režimu. Nezapomeňte, že můžete přidat několik aplikací.

  - **Prohlížeče**

    - **Přidat Microsoft Edge**: Microsoft Edge je přidané do mřížky aplikace a všechny aplikace se můžou spouštět na tomto veřejného terminálu. Zvolte **typ režimu veřejného terminálu Microsoft Edge**:

      - **Normální režim (úplnou verzi Microsoft Edge)**: Spouští se všemi funkcemi procházení plné verze Microsoft Edge. Uživatelská data a stát se uloží mezi relacemi.
      - **Veřejné procházení (InPrivate)**: Běží více karet verze InPrivate v Microsoft Edgi s přizpůsobené prostředí pro veřejné terminály, které běží v režimu celé obrazovky.

      Další informace o těchto možnostech najdete v tématu [celoobrazovkový režim nasazení Microsoft Edge](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

      > [!NOTE]
      > Toto nastavení umožňuje prohlížeč Microsoft Edge na zařízení. Ke konfiguraci nastavení specifické pro společnost Microsoft Edge, vytvořit profil konfigurace zařízení (**konfigurace zařízení** > **profily** > **vytvořit profil**  >  **Windows 10** pro platformu > **omezení zařízení** >  **prohlížeče Microsoft Edge**). [Prohlížeč Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser) uvádí a popisuje dostupná nastavení.

      Vyberte **OK** uložte provedené změny.

    - **Přidat prohlížeči Kiosk**: Tato nastavení řídí aplikaci webového prohlížeče na veřejném terminálu. K nasazení aplikace webového prohlížeče do zařízení s beznabídkovým režimem použijte [klientské aplikace](apps-add.md).

      Zadejte následující nastavení:

      - **Výchozí adresa URL domovské stránky**: Zadejte výchozí adresa URL zobrazí při otevření prohlížeči kiosk nebo při restartování prohlížeče. Zadejte například `http://bing.com` nebo `http://www.contoso.com`.

      - **Tlačítko Domů**: **Zobrazit** nebo **skrýt** tlačítko Domů prohlížeče veřejného terminálu. Ve výchozím nastavení se tlačítko nezobrazuje.

      - **Navigační tlačítka**: **Zobrazit** nebo **skrýt** tlačítka vpřed a zpět. Ve výchozím nastavení se navigační tlačítka nezobrazují.

      - **Ukončení relace tlačítko**: **Zobrazit** nebo **skrýt** tlačítko end relace. Když je zobrazené a uživatel tlačítko vybere, dojde k výzvě pro ukončení relace. Po potvrzení prohlížeč vymaže všechny údaje o procházení (soubory cookie, mezipaměť atd.) a otevře výchozí adresu URL. Ve výchozím nastavení se tlačítko nezobrazuje.

      - **Aktualizujte prohlížeč po nečinnosti**: Zadejte dobu nečinnosti (1 až 1440 v minut) dokud prohlížeči kiosk restartování do původního stavu. Doba nečinnosti se udává v minutách a označuje dobu, která uplynula od poslední interakce uživatele. Ve výchozím nastavení je hodnota prázdná, což znamená, že neexistuje žádný časový limit nečinnosti.

      - **Povolené websites**: Pomocí tohoto nastavení můžete povolit určité weby na Otevřít. Jinými slovy, tuto funkci použijte k omezení nebo zabránění spouštění webů na zařízení. Můžete například povolit, aby se otevíraly všechny weby na `contoso.com*`. Ve výchozím nastavení jsou povolené všechny weby.

        Pokud chcete povolit konkrétní weby, nahrajte soubor CSV, který obsahuje seznam povolených webů. Pokud soubor CSV nepřidáte, budou povolené všechny weby.

      Vyberte **OK** uložte provedené změny.

  - **Aplikace**

    - **Přidat aplikace pro store**: Přidáte aplikace z Microsoft Store pro firmy. Pokud nejsou zobrazené žádné aplikace, můžete je získat a [přidat do Intune](store-apps-windows.md). Můžete například přidat Kiosk Browser, Excel, OneNote a další.

      Vyberte **OK** uložte provedené změny.

    - **Přidat aplikaci Win32**: Aplikace Win32 je tradiční desktopové aplikace, jako je Visual Studio Code nebo Google Chrome. Zadejte tyto vlastnosti:

      - **Název aplikace**: Povinný parametr. Zadejte název aplikace.
      - **Místní cesta**: Povinný parametr. Zadejte cestu ke spustitelnému souboru, například `C:\Program Files (x86)\Microsoft VS Code\Code.exe` nebo `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
      - **Uživatelské ID modelu aplikace (AUMID)**: Zadejte ID modelu uživatele aplikace (AUMID) aplikace Win32. Toto nastavení určuje rozložení nabídky Start na dlaždici na ploše. Toto ID získáte [Get-StartApps](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps).

      Vyberte **OK** uložte provedené změny.

    - **Přidejte podle AUMID**: Tuto možnost použijte k přidání aplikací pro Windows doručené pošty, jako je například Poznámkový blok nebo kalkulačku. Zadejte tyto vlastnosti:

      - **Název aplikace**: Povinný parametr. Zadejte název aplikace.
      - **Uživatelské ID modelu aplikace (AUMID)**: Povinný parametr. Zadejte ID modelu uživatele aplikace (AUMID) aplikace pro Windows. Pokud chcete získat toto ID, přečtěte si článek o tom, [jak u nainstalované aplikace najít ID modelu uživatele aplikace](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

      Vyberte **OK** uložte provedené změny.

    - **Dlaždici velikost**: Povinný parametr. Zvolte velikost dlaždice aplikace – malá, střední, široká nebo velká.

  > [!TIP]
  > Po přidání všech aplikací můžete změnit pořadí zobrazování tak, že na aplikace v seznamu kliknete a pomocí myši je přetáhnete, kam potřebujete.  

- **Použití alternativní rozložení nabídky Start**: Zvolte **Ano** zadejte soubor XML, který popisuje, jak se mají aplikace zobrazit v nabídce start, včetně pořadí aplikace. Tuto možnost použijte, pokud v nabídce Start potřebujete větší míru přizpůsobení. V článku [Přizpůsobení a export rozložení nabídky Start](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) najdete pokyny a ukázkový soubor XML.

- **Hlavním panelu Windows**: Zvolit **zobrazit** nebo **skrýt** na hlavním panelu. Ve výchozím nastavení se hlavní panel nezobrazuje. Ikony, jako je například na ikonu sítě Wi-Fi se zobrazí, ale nastavení nelze změnit koncovými uživateli.

Vyberte **OK** uložte provedené změny.

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Můžete také vytvořit profily beznabídkového režimu pro [Android](device-restrictions-android.md#kiosk), [Androidu Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings), a [Windows Holographic for Business](kiosk-settings-holographic.md) zařízení.
