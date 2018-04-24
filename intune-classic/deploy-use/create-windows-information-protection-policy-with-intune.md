---
title: Vytvoření a nasazení zásady ochrany aplikací WIP (Windows Information Protection) u Intune
description: Vytvoření a nasazení zásady ochrany aplikací WIP u Intune
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 9/13/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 51e53e28-5c34-4d0f-a4b1-6390a337514c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fec1d11320e47c3c0678f96bf6c2ffa6c4b18fec
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Vytvoření a nasazení zásady ochrany aplikací WIP (Windows Information Protection) u Intune

[!INCLUDE [note for both-portals](../includes/note-for-both-portals.md)]

Počínaje verzí Intune 1704 můžete používat zásady ochrany aplikací u Windows 10 ve správě mobilních aplikací (MAM) bez scénáře registrace.

## <a name="before-you-begin"></a>Před zahájením

Povězme si o několika konceptech při přidání zásady WIP.

### <a name="list-of-allowed-and-exempt-apps"></a>Seznamy Povolené aplikace a Aplikace s výjimkou

-   **Povolené aplikace:** Tyto aplikace musí tuto zásadu dodržovat.

-   **Aplikace s výjimkou:** Tyto aplikace mají z této zásady výjimku a můžou k podnikovým datům přistupovat bez omezení.

### <a name="types-of-apps"></a>Typy aplikací

-   **Doporučené aplikace:** Předem naplněný seznam aplikací (většinou Microsoft Office), které správcům umožňují snadný import do zásady.

-   **Aplikace pro Store:** Správce může do zásady přidat libovolnou aplikaci z Windows Storu.

-   **Desktopové aplikace Windows:** Správce může do zásady přidat libovolné tradiční desktopové aplikace Windows (např. soubory typu exe, dll atd.)

## <a name="pre-requisites"></a>Požadavky

Abyste mohli vytvořit zásadu ochrany aplikací WIP, musíte nejdříve nakonfigurovat poskytovatele MAM.

-   Přečtěte si další informace o tom, [jak nakonfigurovat poskytovatele MAM u Intune](/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10).

Navíc musíte mít toto:

-   Licence [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)
-   [Windows Creators Update](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> WIP nepodporuje víc identit. Vždy může existovat jenom jedna spravovaná identita.

## <a name="to-add-a-wip-policy"></a>Přidání zásady WIP

Pokud už máte v organizaci nastavenou službu Intune, můžete přes portál [Azure Portal](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies) vytvořit zásadu specifickou pro WIP.

1.  Přejděte na **řídicí panel Správa mobilních aplikací Intune**, zvolte **Všechna nastavení** a potom zvolte **Zásada aplikace**.

2.  V okně **Zásada aplikace** zvolte **Přidat zásadu** a pak zadejte následující hodnoty:

    a.  **Název:** Zadejte název nové zásady (povinné).

    b.  **Popis:** Zadejte volitelný popis.

    c.  **Platforma:** Jako podporovanou platformu pro vaši zásadu ochrany aplikací zvolte **Windows 10**.

    d.  **Stav registrace:** Jako stav registrace pro vaši zásadu zvolte **Bez registrace**.

3.  Zvolte **Vytvořit**. Zásada se vytvoří a objeví se v tabulce v okně **Zásada aplikace**.

## <a name="to-add-recommended-apps-to-your-allowed-apps-list"></a>Přidání doporučených aplikací do seznamu Povolené aplikace

1.  V okně **Zásada aplikace** zvolte název zásady a potom v okně **Přidat zásadu** zvolte možnost **Povolené aplikace**. Otevře se okno **Povolené aplikace** a zobrazí se v něm všechny aplikace, které už jsou obsažené v seznamu pro tuto zásadu ochrany aplikací.

2.  V okně **Povolené aplikace** zvolte **Přidat aplikace**. Otevře se okno **Přidat aplikace** a zobrazí se v něm všechny aplikace, které jsou součástí tohoto seznamu.

3.  Otevřete každou aplikaci, která má mít přístup k podnikovým datům, a zvolte **OK**. Okno **Povolené aplikace** se aktualizuje a zobrazí se v něm všechny vaše vybrané aplikace.

## <a name="add-a-store-app-to-your-allowed-apps-list"></a>Přidání aplikace ze Storu do seznamu Povolené aplikace

**Přidání aplikace ze Storu**

1.  V okně **Zásada aplikace** zvolte název zásady. Objeví se nabídka ukazující všechny aplikace, které už jsou obsažené v seznamu pro tuto zásadu ochrany aplikací. V této nabídce zvolte **Povolené aplikace**.

2.  V okně **Povolené aplikace** zvolte **Přidat aplikace**.

3.  V okně **Přidat aplikace** zvolte v rozevíracím seznamu možnost **Aplikace pro Store**. Okno se změní a objeví se v něm pole pro přidání **vydavatele** a **názvu aplikace**.

4.  Zadejte název aplikace a jejího vydavatele a zvolte **OK**.

    > [!TIP]
    > Tady je příklad aplikace, u které **vydavatel** je *CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US* a **název** produktu je *Microsoft.MicrosoftAppForWindows*.

5.  Až zadáte do polí příslušné informace, zvolte **OK** a přidejte tak aplikaci do seznamu **Povolené aplikace**.

> [!NOTE]
> Pokud chcete přidat najednou více aplikací ze Storu, můžete na konci řádku aplikace kliknout na nabídku **(…)** a pokračovat v přidávání dalších aplikací. Až budete hotovi, zvolte **OK**.

## <a name="add-a-desktop-app-to-your-allowed-apps-list"></a>Přidání desktopové aplikace do seznamu Povolené aplikace

**Přidání desktopové aplikace**

1.  V okně **Zásada aplikace** zvolte název zásady a potom zvolte **Povolené aplikace**. Otevře se okno **Povolené aplikace** a zobrazí se v něm všechny aplikace, které už jsou obsažené v seznamu pro tuto zásadu ochrany aplikací.

2.  V okně **Povolené aplikace** zvolte **Přidat aplikace**.

3.  V okně **Přidat aplikace** zvolte v rozevíracím seznamu možnost **Desktopové aplikace**.

4.  Až zadáte do polí příslušné informace, zvolte **OK** a přidejte tak aplikaci do seznamu **Povolené aplikace**.

> [!NOTE]
> Pokud chcete přidat najednou víc **desktopových aplikací**, můžete na konci řádku aplikace kliknout na nabídku **(…)** a pokračovat přidáváním dalších aplikací. Až budete hotovi, zvolte **OK**.

## <a name="windows-information-protection-wip-learning"></a>Kurzy k WIP (Windows Information Protection)

Po přidání aplikací, které chcete chránit pomocí WIP, je potřeba použít režim ochrany prostřednictvím **Kurzů k WIP**.

### <a name="before-you-begin"></a>Před zahájením

Kurzy k WIP (Windows Information Protection) je sestava, která správcům umožňuje monitorovat aplikace pro WIP neznámé. Neznámé aplikace jsou aplikace, které nenasadilo IT oddělení vaší organizace. Správce může tyto aplikace ze sestavy exportovat a přidat je do zásad WIP. Zabrání tak přerušení produktivity po dobu, než vynutí WIP v režimu Skrýt potlačení.

Doporučujeme začít s režimem **Tiché** nebo **Povolit potlačení** a u malé skupiny ověřit, jestli máte v seznamu povolených aplikací správné aplikace. Až budete hotovi, můžete režim změnit na konečnou zásadu vynucení **Skrýt potlačení**.

#### <a name="what-the-protection-modes-are"></a>Jaké jsou režimy ochrany?

- **Skrýt potlačení:**
    - WIP hledá nepatřičné postupy sdílení dat a zabrání uživateli dokončit akci.
    - K takovým postupům může patřit sdílení mezi podnikově nechráněnými aplikacemi a sdílení podnikových dat mezi dalšími lidmi a zařízeními mimo vaši organizaci.
<br></br>

- **Povolit potlačení:**
    - WIP hledá nepatřičné sdílení dat, a pokud uživatelé udělají něco potenciálně nebezpečného, upozorní je na to.
    - Uživatel ale může v tomto režimu zásady potlačit a data sdílet. Akce se v takovém případě zaznamená do protokolu auditu.
<br></br>
- **Tiché:**
    - WIP běží tiše s protokolováním nepatřičného sdílení dat. Neblokuje nic, co by v režimu Povolit potlačení vyžadovalo interakci uživatele.
    - Nepovolené akce, jako jsou nepatřičné pokusy aplikací o přístup k síťovému prostředku nebo k datům chráněným pomocí WIP, budou ale zastaveny.
<br></br>
- **Vypnuto (nedoporučuje se):**
    - WIP je vypnuté a nepomáhá chránit nebo auditovat data.
    - Když WIP vypnete, proběhne pokus o dešifrování všech souborů označených přes WIP na místně připojených jednotkách. Dejte pozor: Po opětovném zapnutí WIP se vaše předchozí šifrování a informace zásady znovu automaticky nepoužijí.

### <a name="to-add-a-protection-mode"></a>Přidání režimu ochrany

1.  V okně **Zásada aplikace**  zvolte název zásady a potom v okně **Přidat zásadu** klikněte na **Požadovaná nastavení**.

    ![Snímek obrazovky s režimem Kurzy](../media/AppManagement/learning-mode-sc1.png)

1.  Zvolte **Uložit**.

### <a name="to-use-wip-learning"></a>Použití Kurzů k WIP

1. Přejděte na řídicí panel Azure.

2. V nabídce vlevo zvolte **Další služby** a do filtru textového pole pak zadejte **Intune**.

3. Zvolte **Intune**. Na **řídicím panelu Intune**, který se otevře, zvolte **Mobilní aplikace**.

4. V části **Monitorování** zvolte **Kurzy k WIP**. Uvidíte neznámé aplikace protokolované prostřednictvím Kurzů k WIP.

> [!IMPORTANT]
> Když se tyto aplikace objeví v sestavě protokolování Kurzy k WIP, můžete je přidat do zásad ochrany aplikací.

## <a name="to-deploy-your-wip-app-protection-policy"></a>Nasazení zásady ochrany aplikací WIP

> [!IMPORTANT]
> Toto platí pro WIP se správou mobilních aplikací (MAM) bez scénáře registrace.

Když jste vytvořili zásadu ochrany aplikací WIP, potřebujete ji nasadit ve vaší organizaci s použitím MAM.

1.  V okně **Zásada aplikace** zvolte vaši nově vytvořenou zásadu pro ochranu aplikací, zvolte **Skupiny uživatelů** a potom zvolte **Přidat skupinu uživatelů**.

    V okně **Přidat skupinu uživatelů** se otevře seznam skupin uživatelů, který obsahuje všechny skupiny zabezpečení v Azure Active Directory.

1.  Zvolte skupinu, u které chcete zásadu použít, a kliknutím na **Vybrat** zásadu nasaďte.
