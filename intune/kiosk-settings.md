---
title: Nastavení veřejného terminálu pro Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Konfigurace zařízení s Windows 10 (a novější) jako veřejné terminály jedné aplikace a s více aplikacemi, přizpůsobení nabídky start, přidejte aplikace, zobrazit panel úkolů a nakonfigurovat webový prohlížeč. Jako veřejný terminál s více aplikacemi v Microsoft Intune nakonfigurujte také zařízení s Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.openlocfilehash: 353c18affa41e56501a76bf695f95cbe95796e99
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203463"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-dedicated-kiosk-using-intune"></a>Nastavení Windows 10 (nebo novějším) ke spuštění jako vyhrazené veřejný terminál, pomocí Intune

Na zařízení s Windows 10 pomocí Intune můžete spustit zařízení jako veřejný terminál, někdy označovanou jako vyhrazená zařízení. Zařízení v celoobrazovkovém režimu, můžete spustit jednu aplikaci nebo spustit velký počet aplikací. Můžete zobrazit a přizpůsobit nabídku start, přidat různé aplikace, včetně aplikací Win32, přidejte konkrétní domovskou stránku webového prohlížeče a další. 

Tento článek uvádí a popisuje různá nastavení, které můžete řídit na Windows 10 a novější zařízení. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete nakonfigurovat zařízení s Windows 10 spustit v celoobrazovkovém režimu.

Intune podporuje jeden profil beznabídkového režimu v jednom zařízení. Pokud potřebujete více profilů beznabídkového režimu, můžete použít [vlastní OMA-URI](custom-settings-windows-10.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](device-profile-create.md).

## <a name="kiosk-settings"></a>Nastavení veřejného terminálu

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:

   - **Název**: Zadejte popisný název pro nový profil.
   - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
   - **Platforma**: Vyberte **Windows 10 a novější**
   - **Typ profilu**: Vyberte **veřejného terminálu**

4. Vyberte **beznabídkový režim**. **Beznabídkový režim** určuje typ režimu veřejného terminálu podporovaného zásadami. Vaše možnosti jsou:

    - **Není nakonfigurováno** (výchozí): Zásady neumožňuje beznabídkový režim.
    - **Aplikace s jedním, celoobrazovkového**: Zařízení používá jako jeden uživatelský účet a uzamkne ji proti k jedné aplikaci Store. Když se uživatel přihlásí, spustí se daná aplikace. Tento režim zároveň brání uživateli v otevírání nových aplikací nebo změně spuštěné aplikace.
    - **Veřejný terminál s více aplikacemi**: Zařízení spustí Store více aplikací, aplikací Win32 nebo aplikací Windows doručené pošty s ID modelu uživatele aplikace (AUMID). Na zařízení jsou dostupné pouze aplikace, které přidáte.

        Veřejný terminál s více aplikacemi, neboli zařízení s pevně stanoveným účelem, umožňuje poskytovat přehledné prostředí uživatelům, protože jim povoluje přístup pouze k aplikacím, které potřebují. Nezobrazuje jim aplikace, které nepotřebují.

## <a name="single-full-screen-app-kiosks"></a>Veřejné terminály s jednou aplikací v režimu na celou obrazovku
Když zvolíte beznabídkový režim s jednou aplikací, zadejte následující nastavení:

- **Typ přihlášení uživatele**: Aplikace, které přidáte účet Spustit jako uživatele, které zadáte. Možnosti:

  - **Automatické přihlašování (Windows 10 verze 1803 nebo novější)**: Pro veřejné terminály ve veřejných prostředích, které nevyžadují uživatel přihlásil, podobně jako pomocí účtu guest. Toto nastavení využívá [poskytovatele konfiguračních služeb AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Místní uživatelský účet**: Zadejte místní (pro zařízení) uživatelského účtu. Zadaný účet se používá pro přihlášení k veřejnému terminálu.

- **Typ aplikace**: Vyberte **Store app**.

- **Aplikace ale běží v beznabídkovém režimu**: Zvolte **přidání aplikace ze storu**a vyberte aplikaci ze seznamu.

    Nejsou v seznamu žádné aplikace? Přidejte aplikace pomocí postupu v části [Klientské aplikace](apps-add.md).

    Vyberte **OK** uložte provedené změny.

- **Veřejný terminál, nastavení prohlížeče**: Tato nastavení řídí aplikaci webového prohlížeče na veřejném terminálu. Ujistěte se, získáte [aplikace Kiosk browser](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) z Store, přidejte ho do Intune jako [klientskou aplikaci](apps-add.md)a pak přiřadíte tuto aplikaci do zařízení v celoobrazovkovém režimu.

  Zadejte následující nastavení:

  - **Výchozí adresa URL domovské stránky**: Zadejte výchozí adresa URL zobrazí při otevření prohlížeči kiosk nebo při restartování prohlížeče. Zadejte například `http://bing.com` nebo `http://www.contoso.com`.

  - **Tlačítko Domů**: **Zobrazit** nebo **skrýt** tlačítko Domů prohlížeče veřejného terminálu. Ve výchozím nastavení se tlačítko nezobrazuje.

  - **Navigační tlačítka**: **Zobrazit** nebo **skrýt** tlačítka vpřed a zpět. Ve výchozím nastavení se navigační tlačítka nezobrazují.

  - **Ukončení relace tlačítko**: **Zobrazit** nebo **skrýt** tlačítko end relace. Když je zobrazené a uživatel tlačítko vybere, dojde k výzvě pro ukončení relace. Po potvrzení prohlížeč vymaže všechny údaje o procházení (soubory cookie, mezipaměť atd.) a otevře výchozí adresu URL. Ve výchozím nastavení se tlačítko nezobrazuje.

  - **Aktualizujte prohlížeč po nečinnosti**: Zadejte dobu nečinnosti (1 až 1440 v minut) dokud prohlížeči kiosk restartování do původního stavu. Doba nečinnosti se udává v minutách a označuje dobu, která uplynula od poslední interakce uživatele. Ve výchozím nastavení je hodnota prázdná, což znamená, že neexistuje žádný časový limit nečinnosti.

  - **Povolené websites**: Pomocí tohoto nastavení můžete povolit určité weby na Otevřít. Jinými slovy, tuto funkci použijte k omezení nebo zabránění spouštění webů na zařízení. Můžete například povolit, aby se otevíraly všechny weby na `http://contoso.com*`. Ve výchozím nastavení jsou povolené všechny weby.
 
      Pokud chcete povolit konkrétní weby, nahrajte soubor, který obsahuje seznam povolených webů na samostatných řádcích. Pokud soubor nepřidáte, jsou povolené všechny weby. Intune podporuje hvězdičku (*) jako zástupný znak.

      Váš ukázkový soubor by se měl podobat následujícímu seznamu:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`  

  Vyberte **OK** uložte provedené změny.

## <a name="multi-app-kiosks"></a>Veřejné terminály s více aplikacemi

Aplikace v tomto režimu jsou k dispozici v nabídce Start. Tyto aplikace jsou jedinými aplikacemi, které může uživatel spustit.

Když zvolíte beznabídkový režim s více aplikacemi, zadejte následující nastavení:

- **Cíl v režimu zařízení S Windows 10**: Zvolte **Ano** pro povolení aplikací pro store a AUMID aplikace (kromě aplikací Win32) ve profil beznabídkového režimu. Možnost **Ne** zvolte, pokud chcete v profilu veřejného terminálu povolit aplikace pro Store, aplikace Win32 a aplikace AUMID. Když zvolíte **Ne**, profil veřejného terminálu se nenasadí na zařízení v režimu S.

- **Typ přihlášení uživatele**: Aplikace, které přidáte účet Spustit jako uživatele, které zadáte. Možnosti:

  - **Automatické přihlašování (Windows 10 verze 1803 nebo novější)**: Pro veřejné terminály ve veřejných prostředích, které nevyžadují uživatel přihlásil, podobně jako pomocí účtu guest. Toto nastavení využívá [poskytovatele konfiguračních služeb AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Místní uživatelský účet**: **Přidat** místním (zařízení) uživatelského účtu. Zadaný účet se používá pro přihlášení k veřejnému terminálu.
  - **Azure AD uživateli nebo skupině (Windows 10 verze 1803 nebo novější)**: Vyberte **Přidat** a zvolte uživatele nebo skupiny Azure AD ze seznamu. Můžete vybrat více uživatelů a skupin. Zvolením možnosti **Vybrat** uložte změny.
  - **Návštěvník HoloLens**: Návštěvník účet je účet guest, který nevyžaduje žádné přihlašovací údaje uživatele nebo ověřování, jak je popsáno v [sdílí koncepty režimu PC](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Aplikace**: Přidání aplikací pro spuštění na zařízení beznabídkového režimu. Nezapomeňte, že můžete přidat několik aplikací.

  - **Přidat aplikace pro store**: Přidáte aplikace z Microsoft Store pro firmy. Pokud nejsou zobrazené žádné aplikace, můžete je získat a [přidat do Intune](store-apps-windows.md). Můžete například přidat Kiosk Browser, Excel, OneNote a další.

  - **Přidat aplikaci Win32**: Aplikace Win32 je tradiční desktopové aplikace, jako je Visual Studio Code nebo Google Chrome. Zadejte tyto vlastnosti:

    - **Název aplikace**: Povinný parametr. Zadejte název aplikace.
    - **Místní cesta**: Povinný parametr. Zadejte cestu ke spustitelnému souboru, například `C:\Program Files (x86)\Microsoft VS Code\Code.exe` nebo `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
    - **Uživatelské ID modelu aplikace (AUMID)**: Zadejte ID modelu uživatele aplikace (AUMID) aplikace Win32. Toto nastavení určuje rozložení nabídky Start na dlaždici na ploše. Pokud chcete získat toto ID, přečtěte si článek o tom, [jak u nainstalované aplikace najít ID modelu uživatele aplikace](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps).
    - **Dlaždici velikost**: Povinný parametr. Zvolte velikost dlaždice aplikace – malá, střední, široká nebo velká.
  
  - **Přidejte podle AUMID**: Tuto možnost použijte k přidání aplikací pro Windows doručené pošty, jako je například Poznámkový blok nebo kalkulačku. Zadejte tyto vlastnosti: 

    - **Název aplikace**: Povinný parametr. Zadejte název aplikace.
    - **Uživatelské ID modelu aplikace (AUMID)**: Povinný parametr. Zadejte ID modelu uživatele aplikace (AUMID) aplikace pro Windows. Pokud chcete získat toto ID, přečtěte si článek o tom, [jak u nainstalované aplikace najít ID modelu uživatele aplikace](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Dlaždici velikost**: Povinný parametr. Zvolte velikost dlaždice aplikace – malá, střední, široká nebo velká.

  > [!TIP]
  > Po přidání všech aplikací můžete změnit pořadí zobrazování tak, že na aplikace v seznamu kliknete a pomocí myši je přetáhnete, kam potřebujete.  

  Vyberte **OK** uložte provedené změny.

- **Veřejný terminál, nastavení prohlížeče**: Tato nastavení řídí aplikaci webového prohlížeče na veřejném terminálu. K nasazení aplikace webového prohlížeče do zařízení s beznabídkovým režimem použijte [klientské aplikace](apps-add.md).

  Zadejte následující nastavení:

  - **Výchozí adresa URL domovské stránky**: Zadejte výchozí adresa URL zobrazí při otevření prohlížeči kiosk nebo při restartování prohlížeče. Zadejte například `http://bing.com` nebo `http://www.contoso.com`.

  - **Tlačítko Domů**: **Zobrazit** nebo **skrýt** tlačítko Domů prohlížeče veřejného terminálu. Ve výchozím nastavení se tlačítko nezobrazuje.

  - **Navigační tlačítka**: **Zobrazit** nebo **skrýt** tlačítka vpřed a zpět. Ve výchozím nastavení se navigační tlačítka nezobrazují.

  - **Ukončení relace tlačítko**: **Zobrazit** nebo **skrýt** tlačítko end relace. Když je zobrazené a uživatel tlačítko vybere, dojde k výzvě pro ukončení relace. Po potvrzení prohlížeč vymaže všechny údaje o procházení (soubory cookie, mezipaměť atd.) a otevře výchozí adresu URL. Ve výchozím nastavení se tlačítko nezobrazuje.

  - **Aktualizujte prohlížeč po nečinnosti**: Zadejte dobu nečinnosti (1 až 1440 v minut) dokud prohlížeči kiosk restartování do původního stavu. Doba nečinnosti se udává v minutách a označuje dobu, která uplynula od poslední interakce uživatele. Ve výchozím nastavení je hodnota prázdná, což znamená, že neexistuje žádný časový limit nečinnosti.

  - **Povolené websites**: Pomocí tohoto nastavení můžete povolit určité weby na Otevřít. Jinými slovy, tuto funkci použijte k omezení nebo zabránění spouštění webů na zařízení. Můžete například povolit, aby se otevíraly všechny weby na `contoso.com*`. Ve výchozím nastavení jsou povolené všechny weby.

    Pokud chcete povolit konkrétní weby, nahrajte soubor CSV, který obsahuje seznam povolených webů. Pokud soubor CSV nepřidáte, budou povolené všechny weby.

  Vyberte **OK** uložte provedené změny.

- **Použití alternativní rozložení nabídky Start**: Zvolte **Ano** zadejte soubor XML, který popisuje, jak se mají aplikace zobrazit v nabídce start, včetně pořadí aplikace. Tuto možnost použijte, pokud v nabídce Start potřebujete větší míru přizpůsobení. V článku [Přizpůsobení a export rozložení nabídky Start](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) najdete pokyny a ukázkový soubor XML.

- **Hlavním panelu Windows**: Zvolit **zobrazit** nebo **skrýt** na hlavním panelu. Ve výchozím nastavení se hlavní panel nezobrazuje.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Zařízení s Windows Holographic for Business můžete nakonfigurovat tak, aby se spouštěla v režimu veřejného terminálu s jednou aplikací, nebo v režimu veřejného terminálu s více aplikacemi. Některé funkce nejsou na zařízení s Windows Holographic for Business podporované.

#### <a name="single-full-screen-app-kiosks"></a>Veřejné terminály s jednou aplikací v režimu na celou obrazovku
Když zvolíte beznabídkový režim s jednou aplikací, zadejte následující nastavení:

- **Typ přihlášení uživatele**: Vyberte **místní uživatelský účet** zadat místní (pro zařízení) uživatelský účet nebo účet Microsoft (MSA) účet přidružený k aplikaci veřejného terminálu. Typy uživatelských účtů **Automatické přihlášení** nejsou na zařízení s Windows Holographic for Business podporované.

- **Typ aplikace**: Vyberte **Store app**.

- **Aplikace ale běží v beznabídkovém režimu**: Zvolte **přidání aplikace ze storu**a vyberte aplikaci ze seznamu.

    Nejsou v seznamu žádné aplikace? Přidejte aplikace pomocí postupu v části [Klientské aplikace](apps-add.md).

    Vyberte **OK** uložte provedené změny.

#### <a name="multi-app-kiosks"></a>Veřejné terminály s více aplikacemi
Aplikace v tomto režimu jsou k dispozici v nabídce Start. Tyto aplikace jsou jedinými aplikacemi, které může uživatel spustit. Když zvolíte beznabídkový režim s více aplikacemi, zadejte následující nastavení:

- **Cíl v režimu zařízení S Windows 10**: Zvolte **ne**. Režim S není podporován na Windows Holographic for Business.

- **Typ přihlášení uživatele**: Přidejte jeden nebo více uživatelských účtů, které můžou používat aplikace, které přidáte. Možnosti: 

  - **Automatické přihlašování**: Nepodporované na Windows Holographic for Business.
  - **Místní uživatelské účty**: **Přidat** místním (zařízení) uživatelského účtu. Zadaný účet se používá pro přihlášení k veřejnému terminálu.
  - **Azure AD uživateli nebo skupině (Windows 10 verze 1803 nebo novější)**: Vyžaduje přihlašovací údaje uživatele pro přihlášení k zařízení. Vyberte **Přidat** a zvolte uživatele nebo skupiny Azure AD ze seznamu. Můžete vybrat více uživatelů a skupin. Zvolením možnosti **Vybrat** uložte změny.
  - **Návštěvník HoloLens**: Návštěvník účet je účet guest, který nevyžaduje žádné přihlašovací údaje uživatele nebo ověřování, jak je popsáno v [sdílí koncepty režimu PC](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Aplikace**: Přidání aplikací pro spuštění na zařízení beznabídkového režimu. Nezapomeňte, že můžete přidat několik aplikací.

  - **Přidání aplikací pro Store**: Vybrat existující aplikaci jste přidali pomocí [klientské aplikace](apps-add.md). Pokud nejsou zobrazené žádné aplikace, můžete je získat a [přidat do Intune](store-apps-windows.md).
  - **Přidat aplikaci Win32**: Nepodporované na Windows Holographic for Business.
  - **Přidejte podle AUMID**: Tuto možnost použijte k přidání aplikací pro Windows doručené pošty. Zadejte tyto vlastnosti: 

    - **Název aplikace**: Povinný parametr. Zadejte název aplikace.
    - **Uživatelské ID modelu aplikace (AUMID)**: Povinný parametr. Zadejte ID modelu uživatele aplikace (AUMID) aplikace pro Windows. Pokud chcete získat toto ID, přečtěte si článek o tom, [jak u nainstalované aplikace najít ID modelu uživatele aplikace](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Dlaždici velikost**: Povinný parametr. Zvolte velikost dlaždice aplikace – malá, střední, široká nebo velká.

- **Veřejný terminál, nastavení prohlížeče**: Nepodporované na Windows Holographic for Business.

- **Použití alternativní rozložení nabídky Start**: Zvolte **Ano** zadejte soubor XML, který popisuje, jak se mají aplikace zobrazit v nabídce start, včetně pořadí aplikace. Tuto možnost použijte, pokud v nabídce Start potřebujete větší míru přizpůsobení. V článku o [přizpůsobení a exportu rozložení nabídky Start](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) najdete pokyny a ukázkový soubor XML pro zařízení s Windows Holographic for Business.

- **Hlavním panelu Windows**: Nepodporované na Windows Holographic for Business.

## <a name="next-steps"></a>Další postup
[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Můžete také vytvořit profily beznabídkového režimu pro [Android](device-restrictions-android.md#kiosk) a [Androidu Enterprise](device-restrictions-android-for-work.md#kiosk-settings) zařízení.
