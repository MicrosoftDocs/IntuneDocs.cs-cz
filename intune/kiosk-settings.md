---
title: Nastavení veřejného terminálu pro Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Přečtěte si o nastaveních Microsoft Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s Windows 10.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 897ff48253961d6e1aa83bf36113c362d4548fbf
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745122"
---
# <a name="kiosk-settings-for-windows-10-and-later-in-intune"></a>Nastavení veřejného terminálu pro Windows 10 a novější v Intune

Profily veřejného terminálu můžete použít ke konfiguraci zařízení s Windows 10 pro spuštění jedné aplikace nebo několika aplikací. Když konfigurujete profil veřejného terminálu, vybíráte také, jestli se má zobrazit nabídka Start, jestli se instaluje webový prohlížeč a další možnosti.

## <a name="kiosk-settings"></a>Nastavení veřejného terminálu

1. Výběrem možnosti **Přidat** vytvořte prostředí veřejného terminálu.
2. Zadejte **Název konfigurace veřejného terminálu** pro váš veřejný terminál. Tento název identifikuje skupinu aplikací, rozložení těchto aplikací v nabídce Start a uživatele, kteří jsou této konfiguraci veřejného terminálu přiřazení.
3. Vyberte **Beznabídkový režim**. **Beznabídkový režim**: Určuje typ režimu veřejného terminálu podporovaného zásadami. Vaše možnosti jsou:

  - **Není konfigurováno** (výchozí): Zásady nepovolují režim veřejného terminálu.
  - **Veřejný terminál s jednou aplikací v režimu na celou obrazovku**: Profil umožňuje, aby se zařízení spustilo jako účet jednoho uživatele, a uzamkne ho pro jednu aplikaci pro Univerzální platformu Windows (UPW). Když se uživatel přihlásí, spustí se daná aplikace. Tento režim zároveň brání uživateli v otevírání nových aplikací nebo změně spuštěné aplikace.
  - **Beznabídkový režim s více aplikacemi**: Profil umožňuje, aby zařízení spustilo více aplikací pro UPW (Univerzální platformu Windows) nebo aplikací Win32. Můžete také přiřadit různé aplikace různým uživatelským účtům. Uživatelé mají k dispozici pouze aplikace, které přidáte. Veřejný terminál s více aplikacemi, neboli zařízení s pevně stanoveným účelem, umožňuje poskytovat přehledné prostředí uživatelům, protože jim povoluje přístup pouze k aplikacím, které potřebují. Nezobrazuje jim aplikace, které nepotřebují.

#### <a name="single-full-screen-app-kiosks"></a>Veřejné terminály s jednou aplikací v režimu na celou obrazovku
Zadejte následující nastavení:

- **Identifikátor aplikace pro Univerzální platformu Windows (UPW)**: Zadejte **ID modelu uživatele aplikace (AUMID)** aplikace veřejného terminálu. Nebo vyberte existující spravovanou aplikaci, kterou jste přidali pomocí [Mobile Apps](apps-add.md).

    Přečtěte si článek věnovaný [vyhledání ID modelu uživatele aplikace (AUMID) nainstalované aplikace](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

- **Typ uživatelského účtu**: Toto jsou vaše možnosti:

  - **Automatické přihlášení**: U terminálů určených veřejnosti s povoleným automatickým přihlašováním je vhodné použít uživatele s nejnižšími oprávněními (například místní standardní uživatelský účet). Ke konfiguraci účtu Azure Active Directory (AD) pro beznabídkový režim veřejného terminálu použijte formát `AzureAD\user@contoso.com`.
  - **Účet místního uživatele**: Zadejte účet místního uživatele (v zařízení) nebo přihlášení k účtu Azure AD přidružené k aplikaci veřejného terminálu. U účtů připojených k doménám Azure AD zadejte účet ve tvaru `domain\username@tenant.org`.

#### <a name="multi-app-kiosks"></a>Veřejné terminály s více aplikacemi
Aplikace v tomto režimu jsou k dispozici v nabídce Start. Tyto aplikace jsou jedinými aplikacemi, které může uživatel spustit. 

[Veřejné terminály s více aplikacemi](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune) používají konfiguraci veřejného terminálu, která zobrazuje povolené aplikace, a další nastavení.

Zadejte následující nastavení:

- **Přidat aplikaci Win32**: Aplikace Win32 je tradiční desktopová aplikace. Zadejte **Název aplikace** a **Identifikátor**. **Identifikátor** je plně kvalifikovaná cesta ke spustitelnému souboru, s ohledem na zařízení.
- **Přidat spravované aplikace**: Vyberte existující spravovanou aplikaci, kterou jste přidali pomocí [Mobile Apps v Intune](apps-add.md).
- **Přidat aplikaci podle AUMID**: Zadejte [AUMID aplikace](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (aplikace pro UPW).
- **Hlavní panel**: Zvolte buď **Povolit**, aby se hlavní panel zobrazoval, nebo ho ponechejte **nenakonfigurovaný** (skrytý) na veřejném terminálu.
- **Rozložení nabídky Start**: Zadejte soubor XML, který popisuje, jak se mají aplikace zobrazit v nabídce Start, včetně pořadí aplikací. V článku [Přizpůsobení a export rozložení nabídky Start](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) najdete pokyny a ukázkový soubor XML.

  Článek [Vytvoření veřejného terminálu s Windows 10 umožňujícího použití více aplikací](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) poskytuje podrobnější informace o používání a vytváření souborů XML.

- **Typ uživatelského účtu**: Přidejte jeden či více uživatelských účtů, které mohou přidané aplikace používat. Přihlášenému účtu jsou k dispozici pouze aplikace definované v konfiguraci. Účet může být místní v zařízení nebo přihlášení k účtu Azure AD přidružené k aplikaci veřejného terminálu.

    U terminálů určených veřejnosti s povoleným automatickým přihlašováním je vhodné použít typ uživatele s nejnižšími oprávněními (například místní standardní uživatelský účet). Ke konfiguraci účtu Azure Active Directory (AD) pro beznabídkový režim veřejného terminálu použijte formát `domain\user@tenant.com`.

## <a name="kiosk-web-browser-settings"></a>Nastavení webového prohlížeče Kiosk

Tato nastavení řídí aplikaci webového prohlížeče na veřejném terminálu. Aplikaci webového prohlížeče nasaďte do zařízení veřejného terminálu pomocí [Mobile Apps](apps-add.md).

1. Zadejte následující nastavení:

  - **Výchozí adresa URL domovské stránky**: Zadejte výchozí adresu URL, kterou prohlížeč Kiosk otevře při svém spuštění nebo restartování.

  - **Zobrazit tlačítko Domů**: Zobrazte (**Vyžadovat**) nebo skryjte (**Není konfigurováno**) tlačítko Domů prohlížeče Kiosk. Ve výchozím nastavení tlačítko není nakonfigurováno.

  - **Zobrazit navigační tlačítka**: Zobrazte (**Vyžadovat**) nebo skryjte (**Není konfigurováno**) tlačítka Vpřed a Zpět. Ve výchozím nastavení nejsou navigační tlačítka nakonfigurovaná.

  - **Když uživatel překročí časový limit nečinnosti, aktualizovat prohlížeč**: Zadejte dobu nečinnosti relace v minutách, než se prohlížeč Kiosk restartuje a obnoví. Hodnota může být v intervalu 1 až 1 440 minut. Ve výchozím nastavení je hodnota prázdná, což znamená, že neexistuje žádný časový limit nečinnosti.

  - **Blokované weby**: Seznam adres URL blokovaných webů (podporuje zástupné znaky). Pomocí tohoto nastavení můžete prohlížeči zabránit v otevření konkrétních webů. Můžete také **Importovat** soubor .csv, který seznam obsahuje. Nebo můžete (**Exportovat**) vámi vytvořený soubor .csv, který obsahuje vámi přidané weby.

  - **Výjimky webů**: Seznam výjimek z adres URL blokovaných webů (podporuje zástupné znaky). Pomocí tohoto nastavení můžete prohlížeči povolit, aby otevřel konkrétní weby. Tyto výjimky jsou podmnožinou blokovaných adres URL. Pokud je adresa URL jak na seznamu blokovaných webů, tak i na seznamu výjimek, platí seznam výjimek.

    Můžete také **Importovat** soubor .csv, který seznam obsahuje. Nebo můžete (**Exportovat**) vámi vytvořený soubor .csv, který obsahuje vámi přidané weby.

2. Výběrem **OK** uložte změny.

## <a name="next-steps"></a>Další kroky
[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).