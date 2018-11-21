---
title: Nastavení veřejného terminálu pro Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Nakonfigurujte svá zařízení s Windows 10 (a novější verzí) jako veřejný terminál s jednou nebo více aplikacemi, včetně přizpůsobení nabídky Start, přidání aplikací a hlavního panelu a konfigurace webového prohlížeče. Jako veřejný terminál s více aplikacemi v Microsoft Intune nakonfigurujte také zařízení s Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 7552c9c1fa8e94560505a8971143886160cff6ce
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185947"
---
# <a name="kiosk-settings-for-windows-10-and-later-in-intune"></a>Nastavení veřejného terminálu pro Windows 10 a novější v Intune

Zařízení s Windows 10 můžete pomocí Intune spouštět jako veřejný terminál. Veřejný terminál může spouštět jednu nebo mnoho aplikací. Můžete také zobrazit a přizpůsobit nabídku Start, přidat různé aplikace, včetně aplikací Win32, přidat konkrétní domovskou stránku do webového prohlížeče a další. 

Pomocí postupu v tomto článku vytvořte v Intune veřejný terminál s jednou aplikací nebo veřejný terminál s více aplikacemi.

Intune podporuje jeden profil beznabídkového režimu v jednom zařízení. Pokud potřebujete více profilů beznabídkového režimu, můžete použít [vlastní OMA-URI](custom-settings-windows-10.md).

## <a name="kiosk-settings"></a>Nastavení veřejného terminálu

1. Na webu [Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:

   - **Název**: Zadejte popisný název nového profilu.
   - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
   - **Platforma**: Vyberte **Windows 10 a novější**.
   - **Typ profilu**: Vyberte **Beznabídkový režim (Preview)**.

4. Vyberte **beznabídkový režim**. **Beznabídkový režim** určuje typ režimu veřejného terminálu podporovaného zásadami. Vaše možnosti jsou:

    - **Není konfigurováno** (výchozí): Zásady nepovolují režim veřejného terminálu.
    - **Beznabídkový režim na celou obrazovku s jednou aplikací**: Zařízení se spustí jako účet jednoho uživatele a uzamkne ho pro jednu aplikaci pro Store. Když se uživatel přihlásí, spustí se daná aplikace. Tento režim zároveň brání uživateli v otevírání nových aplikací nebo změně spuštěné aplikace.
    - **Veřejný terminál s více aplikacemi**: Zařízení spustí více aplikací pro Store, aplikací Win32 nebo vnitřních aplikací pro Windows pomocí ID uživatele aplikace (AUMID). Na zařízení jsou dostupné pouze aplikace, které přidáte.

        Veřejný terminál s více aplikacemi, neboli zařízení s pevně stanoveným účelem, umožňuje poskytovat přehledné prostředí uživatelům, protože jim povoluje přístup pouze k aplikacím, které potřebují. Nezobrazuje jim aplikace, které nepotřebují.

## <a name="single-full-screen-app-kiosks"></a>Veřejné terminály s jednou aplikací v režimu na celou obrazovku
Když zvolíte beznabídkový režim s jednou aplikací, zadejte následující nastavení:

- **Typ přihlášení uživatele**: Aplikace, které přidáte, se spustí jako zadaný uživatelský účet. Možnosti:

  - **Automatické přihlášení (Windows 10 verze 1803+)**: Používá se u veřejných terminálů ve veřejných prostředích, které nevyžadují přihlášení uživatele; jedná se o obdobu účtu hosta. Toto nastavení využívá [poskytovatele konfiguračních služeb AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Účet místního uživatele**: Zadejte účet místního uživatele (v zařízení). Zadaný účet se používá pro přihlášení k veřejnému terminálu.

- **Typ aplikace**: Vyberte **aplikaci pro Store**.

- **Aplikace, která se spustí v beznabídkovém režimu**: Zvolte **Přidat aplikaci pro Store** a vyberte aplikaci ze seznamu.

    Nejsou v seznamu žádné aplikace? Přidejte aplikace pomocí postupu v části [Klientské aplikace](apps-add.md).

    Výběrem **OK** uložte změny.

- **Nastavení Kiosk Browseru**: Tato nastavení řídí aplikaci webového prohlížeče na veřejném terminálu. Nezapomeňte získat [aplikaci Kiosk Browseru](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) ze Storu, přidat ji do Intune jako [klientskou aplikaci](apps-add.md) a potom ji přiřadit k zařízením s beznabídkovým režimem.

  Zadejte následující nastavení:

  - **Výchozí adresa URL domovské stránky**: Zadejte výchozí adresu URL, která se otevře, když se otevře Kiosk Browser nebo restartuje prohlížeč. Zadejte například `http://bing.com` nebo `http://www.contoso.com`.

  - **Tlačítko Domů**: **Zobrazí**  nebo **skryje** tlačítko Domů Kiosk Browseru. Ve výchozím nastavení se tlačítko nezobrazuje.

  - **Navigační tlačítka**: **Zobrazí** nebo **skryje** tlačítka pro přechod vpřed nebo vzad. Ve výchozím nastavení se navigační tlačítka nezobrazují.

  - **Tlačítko pro ukončení relace**: **Zobrazí** nebo **skryje** tlačítko pro ukončení relace. Když je zobrazené a uživatel tlačítko vybere, dojde k výzvě pro ukončení relace. Po potvrzení prohlížeč vymaže všechny údaje o procházení (soubory cookie, mezipaměť atd.) a otevře výchozí adresu URL. Ve výchozím nastavení se tlačítko nezobrazuje.

  - **Aktualizovat prohlížeč po určité době nečinnosti**: Zadejte dobu nečinnosti (1 až 1 440 minut), než se Kiosk Browser restartuje a obnoví. Doba nečinnosti se udává v minutách a označuje dobu, která uplynula od poslední interakce uživatele. Ve výchozím nastavení je hodnota prázdná, což znamená, že neexistuje žádný časový limit nečinnosti.

  - **Povolené weby**: Toto nastavení použijte, pokud chcete povolit otevírání konkrétních webů. Jinými slovy, tuto funkci použijte k omezení nebo zabránění spouštění webů na zařízení. Můžete například povolit, aby se otevíraly všechny weby na `http://contoso.com*`. Ve výchozím nastavení jsou povolené všechny weby.
 
      Pokud chcete povolit konkrétní weby, nahrajte soubor, který obsahuje seznam povolených webů na samostatných řádcích. Pokud soubor nepřidáte, jsou povolené všechny weby. Intune podporuje hvězdičku (*) jako zástupný znak.

      Váš ukázkový soubor by se měl podobat následujícímu seznamu:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`  

  Výběrem **OK** uložte změny.

## <a name="multi-app-kiosks"></a>Veřejné terminály s více aplikacemi

Aplikace v tomto režimu jsou k dispozici v nabídce Start. Tyto aplikace jsou jedinými aplikacemi, které může uživatel spustit.

Když zvolíte beznabídkový režim s více aplikacemi, zadejte následující nastavení:

- **Cílit na zařízení s Windows 10 v režimu S**: Zvolte **Ano**, pokud v profilu veřejného terminálu chcete povolit aplikace pro Store a aplikace AUMID (kromě aplikací Win32). Možnost **Ne** zvolte, pokud chcete v profilu veřejného terminálu povolit aplikace pro Store, aplikace Win32 a aplikace AUMID. Když zvolíte **Ne**, profil veřejného terminálu se nenasadí na zařízení v režimu S.

- **Typ přihlášení uživatele**: Aplikace, které přidáte, se spustí jako zadaný uživatelský účet. Možnosti:

  - **Automatické přihlášení (Windows 10 verze 1803+)**: Používá se u veřejných terminálů ve veřejných prostředích, které nevyžadují přihlášení uživatele; jedná se o obdobu účtu hosta. Toto nastavení využívá [poskytovatele konfiguračních služeb AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Účet místního uživatele**: **Přidejte** účet místního uživatele (v zařízení). Zadaný účet se používá pro přihlášení k veřejnému terminálu.
  - **Uživatel nebo skupina Azure AD (Windows 10, verze 1803+)**: Vyberte **Přidat** a ze seznamu vyberte uživatele nebo skupiny Azure AD. Můžete vybrat více uživatelů a skupin. Zvolením možnosti **Vybrat** uložte změny.
  - **Návštěvník HoloLens**: Účet návštěvníka je účtem hosta, který nevyžaduje žádné přihlašovací údaje uživatele ani ověřování, viz článek o [konceptech režimu sdíleného počítače](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Aplikace**: Přidejte aplikace, které se budou spouštět zařízení s beznabídkovým režimem. Nezapomeňte, že můžete přidat několik aplikací.

  - **Přidat aplikaci pro Store**: Přidejte aplikaci z Microsoft Storu pro firmy. Pokud nejsou zobrazené žádné aplikace, můžete je získat a [přidat do Intune](store-apps-windows.md). Můžete například přidat Kiosk Browser, Excel, OneNote a další.

  - **Přidat aplikaci Win32**: Aplikace Win32 je tradiční desktopová aplikace, jako je například Visual Studio Code nebo Google Chrome. Zadejte tyto vlastnosti:

    - **Název aplikace**: Povinné. Zadejte název aplikace.
    - **Místní cesta**: Povinné. Zadejte cestu ke spustitelnému souboru, například `C:\Program Files (x86)\Microsoft VS Code\Code.exe` nebo `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
    - **ID modelu uživatele aplikace (AUMID)**: Zadejte ID modelu uživatele aplikace (AUMID) aplikace Win32. Toto nastavení určuje rozložení nabídky Start na dlaždici na ploše. Pokud chcete získat toto ID, přečtěte si článek o tom, [jak u nainstalované aplikace najít ID modelu uživatele aplikace](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps).
    - **Velikost dlaždice**: Povinné. Zvolte velikost dlaždice aplikace – malá, střední, široká nebo velká.
  
  - **Přidat podle AUMID**: Tuto možnost použijte pro přidání aplikací pro Windows, například Poznámkového bloku nebo Kalkulačky. Zadejte tyto vlastnosti: 

    - **Název aplikace**: Povinné. Zadejte název aplikace.
    - **ID modelu uživatele aplikace (AUMID)**: Povinné. Zadejte ID modelu uživatele aplikace (AUMID) aplikace pro Windows. Pokud chcete získat toto ID, přečtěte si článek o tom, [jak u nainstalované aplikace najít ID modelu uživatele aplikace](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Velikost dlaždice**: Povinné. Zvolte velikost dlaždice aplikace – malá, střední, široká nebo velká.

  > [!TIP]
  > Po přidání všech aplikací můžete změnit pořadí zobrazování tak, že na aplikace v seznamu kliknete a pomocí myši je přetáhnete, kam potřebujete.  

  Výběrem **OK** uložte změny.

- **Nastavení Kiosk Browseru**: Tato nastavení řídí aplikaci webového prohlížeče na veřejném terminálu. K nasazení aplikace webového prohlížeče do zařízení s beznabídkovým režimem použijte [klientské aplikace](apps-add.md).

  Zadejte následující nastavení:

  - **Výchozí adresa URL domovské stránky**: Zadejte výchozí adresu URL, která se otevře, když se otevře Kiosk Browser nebo restartuje prohlížeč. Zadejte například `http://bing.com` nebo `http://www.contoso.com`.

  - **Tlačítko Domů**: **Zobrazí**  nebo **skryje** tlačítko Domů Kiosk Browseru. Ve výchozím nastavení se tlačítko nezobrazuje.

  - **Navigační tlačítka**: **Zobrazí** nebo **skryje** tlačítka pro přechod vpřed nebo vzad. Ve výchozím nastavení se navigační tlačítka nezobrazují.

  - **Tlačítko pro ukončení relace**: **Zobrazí** nebo **skryje** tlačítko pro ukončení relace. Když je zobrazené a uživatel tlačítko vybere, dojde k výzvě pro ukončení relace. Po potvrzení prohlížeč vymaže všechny údaje o procházení (soubory cookie, mezipaměť atd.) a otevře výchozí adresu URL. Ve výchozím nastavení se tlačítko nezobrazuje.

  - **Aktualizovat prohlížeč po určité době nečinnosti**: Zadejte dobu nečinnosti (1 až 1 440 minut), než se Kiosk Browser restartuje a obnoví. Doba nečinnosti se udává v minutách a označuje dobu, která uplynula od poslední interakce uživatele. Ve výchozím nastavení je hodnota prázdná, což znamená, že neexistuje žádný časový limit nečinnosti.

  - **Povolené weby**: Toto nastavení použijte, pokud chcete povolit otevírání konkrétních webů. Jinými slovy, tuto funkci použijte k omezení nebo zabránění spouštění webů na zařízení. Můžete například povolit, aby se otevíraly všechny weby na `contoso.com*`. Ve výchozím nastavení jsou povolené všechny weby.

    Pokud chcete povolit konkrétní weby, nahrajte soubor CSV, který obsahuje seznam povolených webů. Pokud soubor CSV nepřidáte, budou povolené všechny weby.

  Výběrem **OK** uložte změny.

- **Použít alternativní rozložení nabídky Start**: Zvolte **Ano**, pokud chcete zadat soubor XML, který popisuje, jak se aplikace zobrazují v nabídce Start (včetně jejich pořadí). Tuto možnost použijte, pokud v nabídce Start potřebujete větší míru přizpůsobení. V článku [Přizpůsobení a export rozložení nabídky Start](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) najdete pokyny a ukázkový soubor XML.

- **Hlavní panel Windows**: U hlavního panelu si můžete vybrat, zda se má **zobrazit** nebo **skrýt**. Ve výchozím nastavení se hlavní panel nezobrazuje.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Zařízení s Windows Holographic for Business můžete nakonfigurovat tak, aby se spouštěla v režimu veřejného terminálu s jednou aplikací, nebo v režimu veřejného terminálu s více aplikacemi. Některé funkce nejsou na zařízení s Windows Holographic for Business podporované.

#### <a name="single-full-screen-app-kiosks"></a>Veřejné terminály s jednou aplikací v režimu na celou obrazovku
Když zvolíte beznabídkový režim s jednou aplikací, zadejte následující nastavení:

- **Typ přihlášení uživatele**: Vyberte **Účet místního uživatele** a zadejte účet místního uživatele (v zařízení) nebo účet Microsoft (MSA) přidružený k aplikaci veřejného terminálu. Typy uživatelských účtů **Automatické přihlášení** nejsou na zařízení s Windows Holographic for Business podporované.

- **Typ aplikace**: Vyberte **aplikaci pro Store**.

- **Aplikace, která se spustí v beznabídkovém režimu**: Zvolte **Přidat aplikaci pro Store** a vyberte aplikaci ze seznamu.

    Nejsou v seznamu žádné aplikace? Přidejte aplikace pomocí postupu v části [Klientské aplikace](apps-add.md).

    Výběrem **OK** uložte změny.

#### <a name="multi-app-kiosks"></a>Veřejné terminály s více aplikacemi
Aplikace v tomto režimu jsou k dispozici v nabídce Start. Tyto aplikace jsou jedinými aplikacemi, které může uživatel spustit. Když zvolíte beznabídkový režim s více aplikacemi, zadejte následující nastavení:

- **Cílit na zařízení s Windows 10 v režimu S**: Zvolte **Ne**. Režim S není na zařízení s Windows Holographic for Business podporovaný.

- **Typ přihlášení uživatele**: Přidejte jeden nebo více uživatelských účtů, které mohou přidané aplikace používat. Možnosti: 

  - **Automatické přihlášení**: Na zařízeních s Windows Holographic for Business se nepodporuje.
  - **Účet místního uživatele**: **Přidejte** účet místního uživatele (v zařízení). Zadaný účet se používá pro přihlášení k veřejnému terminálu.
  - **Uživatel nebo skupina Azure AD (Windows 10, verze 1803+)**: Vyžaduje zadání přihlašovacích údajů, aby se uživatel mohl k zařízení přihlásit. Vyberte **Přidat** a zvolte uživatele nebo skupiny Azure AD ze seznamu. Můžete vybrat více uživatelů a skupin. Zvolením možnosti **Vybrat** uložte změny.
  - **Návštěvník HoloLens**: Účet návštěvníka je účtem hosta, který nevyžaduje žádné přihlašovací údaje uživatele ani ověřování, viz článek o [konceptech režimu sdíleného počítače](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Aplikace**: Přidejte aplikace, které se budou spouštět zařízení s beznabídkovým režimem. Nezapomeňte, že můžete přidat několik aplikací.

  - **Přidat aplikaci pro Store**: Vyberte stávající aplikaci, kterou jste přidali do [klientských aplikací](apps-add.md). Pokud nejsou zobrazené žádné aplikace, můžete je získat a [přidat do Intune](store-apps-windows.md).
  - **Přidat aplikaci Win32**: Na zařízeních s Windows Holographic for Business se nepodporuje.
  - **Přidat podle AUMID**: Tuto možnost použijte pro přidání vnitřních aplikací pro Windows. Zadejte tyto vlastnosti: 

    - **Název aplikace**: Povinné. Zadejte název aplikace.
    - **ID modelu uživatele aplikace (AUMID)**: Povinné. Zadejte ID modelu uživatele aplikace (AUMID) aplikace pro Windows. Pokud chcete získat toto ID, přečtěte si článek o tom, [jak u nainstalované aplikace najít ID modelu uživatele aplikace](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Velikost dlaždice**: Povinné. Zvolte velikost dlaždice aplikace – malá, střední, široká nebo velká.

- **Nastavení Kiosk Browseru**: Na zařízeních s Windows Holographic for Business se nepodporuje.

- **Použít alternativní rozložení nabídky Start**: Zvolte **Ano**, pokud chcete zadat soubor XML, který popisuje, jak se aplikace zobrazují v nabídce Start (včetně jejich pořadí). Tuto možnost použijte, pokud v nabídce Start potřebujete větší míru přizpůsobení. V článku o [přizpůsobení a exportu rozložení nabídky Start](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) najdete pokyny a ukázkový soubor XML pro zařízení s Windows Holographic for Business.

- **Hlavní panel Windows**: Na zařízeních s Windows Holographic for Business se nepodporuje.



## <a name="next-steps"></a>Další postup
[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
