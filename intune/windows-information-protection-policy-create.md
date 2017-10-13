---
title: "Vytvoření a nasazení zásady ochrany aplikací WIP (Windows Information Protection) u Intune"
titlesuffix: Azure portal
description: "Vytvoření a nasazení zásady ochrany aplikací WIP u Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4e3627bd-a9fd-49bc-b95e-9b7532f0ed55
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3cf11c53a5f1ce78dda9c703da32270b0b07874a
ms.sourcegitcommit: 001577b700f634da2fec0b44af2a378150d1f7ac
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2017
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Vytvoření a nasazení zásady ochrany aplikací WIP (Windows Information Protection) u Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Počínaje verzí Intune 1704 můžete používat zásady ochrany aplikací u Windows 10 k ochraně aplikací bez registrace zařízení.

## <a name="before-you-begin"></a>Před zahájením

Povězme si o několika konceptech při přidání zásady WIP.

### <a name="list-of-allowed-and-exempt-apps"></a>Seznamy povolených aplikací a aplikací s výjimkou

-   **Povolené aplikace:** Tyto aplikace musí tuto zásadu dodržovat.

-   **Aplikace s výjimkou:** Tyto aplikace mají z této zásady výjimku a můžou k podnikovým datům přistupovat bez omezení.

### <a name="types-of-apps"></a>Typy aplikací

-   **Doporučené aplikace:** Předvyplněný seznam aplikací (většinou Microsoft Office), které můžete snadno importovat do zásady. <!---I really don't know what you mean by "easily import into policy"--->

-   **Aplikace pro Store:** Do zásad můžete přidat libovolnou aplikaci z Microsoft Storu.

-   **Desktopové aplikace Windows:** Do zásad můžete přidat libovolné tradiční desktopové aplikace Windows (např. soubory typu exe nebo dll).

## <a name="pre-requisites"></a>Požadavky

Abyste mohli vytvořit zásadu ochrany aplikací WIP, musíte nejdříve nakonfigurovat poskytovatele MAM. Přečtěte si další informace o tom, [jak nakonfigurovat poskytovatele MAM u Intune](https://docs.microsoft.com/app-protection-policies-configure-windows-10.md).

Navíc musíte mít toto:

-   Licence [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)
-   [Windows Creators Update](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> WIP nepodporuje víc identit. Vždy může existovat jenom jedna spravovaná identita.
<!---Should you be linking to a topic that explains what multi-identity is?--->

## <a name="to-add-a-wip-policy"></a>Přidání zásady WIP

Pokud už máte v organizaci nastavenou službu Intune, můžete přes portál [Azure Portal](https://docs.microsoft.com/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies) vytvořit zásadu specifickou pro WIP. <!---Is there an azure topic you can use instead of a classic? if not, should this topic be moved into the azure docset?--->

1.  Přejděte na **řídicí panel Správa mobilních aplikací Intune** a zvolte **Všechna nastavení** > **Zásada aplikace**.

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

## <a name="wip-learning"></a>Kurzy k WIP
<!---You've already defined WIP earlier in the topic. You don't need to keep doing so. --->
Po přidání aplikací, které chcete chránit pomocí WIP, je potřeba použít režim ochrany prostřednictvím **Kurzů k WIP**.

### <a name="before-you-begin"></a>Před zahájením

Kurzy k WIP jsou sestava umožňující monitorovat neznámé aplikace v rámci WIP. Neznámé aplikace jsou aplikace, které nenasadilo IT oddělení vaší organizace. Můžete je ze sestavy exportovat a přidat do zásad WIP. Zabráníte tak přerušení produktivity po dobu, než vynutíte WIP v režimu Skrýt potlačení.

Doporučujeme začít s režimem **Tiché** nebo **Povolit potlačení** a u malé skupiny ověřit, jestli máte v seznamu povolených aplikací správné aplikace. Až budete hotovi, můžete režim změnit na konečnou zásadu vynucení **Skrýt potlačení**.

### <a name="what-are-the-protection-modes"></a>Co jsou režimy ochrany?

#### <a name="hide-overrides"></a>Skrýt potlačení
WIP hledá nepatřičné postupy sdílení dat a zabrání uživateli dokončit akci. K takovým postupům může patřit sdílení mezi podnikově nechráněnými aplikacemi a sdílení podnikových dat mezi dalšími lidmi a zařízeními mimo vaši organizaci.

#### <a name="allow-overrides"></a>Povolit potlačení
WIP hledá nepatřičné sdílení dat, a pokud uživatelé udělají něco potenciálně nebezpečného, upozorní je na to. Uživatel ale může v tomto režimu zásady potlačit a data sdílet. Akce se v takovém případě zaznamená do protokolu auditu.

#### <a name="silent"></a>Tiché
WIP běží bez upozorňování s protokolováním nepatřičného sdílení dat. Neblokuje nic, co by v režimu Povolit potlačení vyžadovalo interakci uživatele. Nepovolené akce, jako jsou nepatřičné pokusy aplikací o přístup k síťovému prostředku nebo k datům chráněným pomocí WIP, budou ale zastaveny.

#### <a name="off-not-recommended"></a>Vypnuto (nedoporučuje se)
WIP je vypnuté a nepomáhá chránit nebo auditovat data.

Když WIP vypnete, proběhne pokus o dešifrování všech souborů označených přes WIP na místně připojených jednotkách. Mějte na paměti, že po opětovném zapnutí WIP se předchozí šifrování a informace zásady znovu automaticky nepoužijí.

### <a name="add-a-protection-mode"></a>Přidání režimu ochrany

1.  V okně **Zásada aplikace** zvolte název zásady a potom zvolte **Povinná nastavení**.

    ![Snímek obrazovky s režimem Kurzy](./media/learning-mode-sc1.png)

1.  Vyberte **Uložit**.

### <a name="use-wip-learning"></a>Použití Kurzů k WIP

1. Otevřete portál Azure Portal. Zvolte **Další služby**. Do filtru textového pole zadejte **Intune**.

3. Zvolte **Intune** > **Mobilní aplikace**.

4. Zvolte **Stav ochrany aplikace** > **Sestavy** > **Kurz k Windows Information Protection**.  
 
    Jakmile se tyto aplikace objeví v sestavě protokolování Kurzy k WIP, můžete je přidat do zásad ochrany aplikací.

## <a name="deploy-your-wip-app-protection-policy"></a>Nasazení zásady ochrany aplikací WIP

> [!IMPORTANT]
> Následující informace platí pro zásady WIP bez registrace zařízení.

<!---not sure why you need the Important note. Isn't this what the topic is about? app protection w/o enrollment?--->

Když jste vytvořili zásadu ochrany aplikací WIP, potřebujete ji nasadit ve vaší organizaci s použitím MAM.

1.  V okně **Zásada aplikace** vyberte svoji nově vytvořenou zásadu pro ochranu aplikací a zvolte **Skupiny uživatelů** > **Přidat skupinu uživatelů**.

    V okně **Přidat skupinu uživatelů** se otevře seznam skupin uživatelů, který obsahuje všechny skupiny zabezpečení v Azure Active Directory.

1.  Zvolte skupinu, u které chcete zásadu použít, a kliknutím na **Vybrat** zásadu nasaďte.
