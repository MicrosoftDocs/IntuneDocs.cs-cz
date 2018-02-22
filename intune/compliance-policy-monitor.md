---
title: "Monitorování zásad dodržování předpisů zařízením v Intune"
titlesuffix: Azure portal
description: "Zjistěte, jak monitorovat dodržování zásad v zařízeních."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 503d1dd2-a647-4aea-bf48-55319a3dd8a7
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f82293ee3803f189cbb67549b1a6cd653572eaaf
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2018
---
# <a name="monitor-intune-device-compliance-policies"></a>Monitorování zásad dodržování předpisů zařízením v Intune

Sestavy dodržování předpisů pomáhají správcům analyzovat stav dodržování předpisů zařízením v organizaci a rychle vyřešit potíže související s dodržováním předpisů, na které uživatelé v organizaci narazí. Můžete zobrazit informace o celkovém stavu dodržování předpisů zařízením, stavu dodržování předpisů pro jednotlivá nastavení a stavu dodržování předpisů pro jednotlivé zásady a také procházet podrobnosti o jednotlivých zařízeních, abyste zobrazili konkrétní nastavení a zásady, které mají na zařízení vliv.

## <a name="before-you-begin"></a>Před zahájením

Podle následujících pokynů na portálu Azure Portal najděte **řídicí panel Intune pro dodržování předpisů zařízením**:

1.  Přejděte na portál [Azure Portal](https://portal.azure.com) a přihlaste se pomocí svých přihlašovacích údajů k Intune.

2.  V nabídce vlevo zvolte **Další služby** a do filtru textového pole pak zadejte **Intune**.

3.  Zvolte **Intune** &gt; **Dodržování předpisů zařízením** &gt; **Přehled** a pak se otevře **řídicí panel pro dodržování předpisů zařízením**.

> [!IMPORTANT] 
> Aby mohla zařízení přijímat zásady dodržování předpisů, musejí být zaregistrovaná v Intune.

## <a name="device-compliance-dashboard"></a>Řídicí panel pro dodržování předpisů zařízením

V **řídicím panelu pro dodržování předpisů zařízením** můžete monitorovat stavy zásad dodržování předpisů zařízením. Získáte tak různé sestavy v rámci různých dlaždic, které vám poskytnou stav dodržování předpisů zařízením ve vaší organizaci. Můžete zobrazit tyto sestavy:

-   Celkový souhrn dodržování předpisů zařízením

-   Dodržování předpisů zařízením podle zásad

-   Dodržování předpisů zařízením podle nastavení

![Řídicí panel pro dodržování předpisů zařízením](./media/idc-1.png)

Můžete také zobrazit konkrétní zásady a nastavení dodržování předpisů, které platí pro jednotlivá zařízení, a konečný stav dodržování předpisů pro každé z těchto nastavení na zařízení.

### <a name="overall-device-compliance-aggregate-report"></a>Sestava celkového souhrnu dodržování předpisů zařízením

Jde o prstencový graf zobrazující souhrnný stav dodržování předpisů pro všechna zařízení zaregistrovaná v Intune. Stavy dodržování předpisů zařízením jsou uložené ve dvou různých databázích, Intune a Azure Active Directory. Tady jsou další podrobnosti o stavech zásad dodržování předpisů zařízením:

-   **Vyhovující předpisům**: Zařízení úspěšně použilo jedno nebo více nastavení zásad dodržování předpisů zařízením zacílených správcem.

-   **Nedodržující předpisy:** Zařízení se nepodařilo použít jedno nebo více nastavení zásad dodržování předpisů zařízením zacílených správcem nebo uživatel nedodržel zásady zacílené správcem.

-   **V období odkladu:** Správce na zařízení zacílil jedno nebo více nastavení zásad dodržování předpisů zařízením, ale uživatel zatím zásady nepoužil. To znamená, že zařízení předpisy nedodržuje, ale je v období odkladu definovaném správcem.

    -   Přečtěte si další informace o akcích pro zařízení nedodržující předpisy.

-   **Zařízení není synchronizované:** Zařízení se nepodařilo oznámit svůj stav zásad dodržování předpisů zařízením kvůli některé z těchto příčin:

    -   **Neznámý**: Zařízení je offline nebo se mu s Intune nebo Azure AD nepodařilo komunikovat z jiných důvodů.

    -   **Chyba**: Zařízení se nepodařilo komunikovat s Intune a Azure AD a obdrželo chybovou zprávu s odůvodněním.

> [!IMPORTANT] 
> Zařízení, která jsou zaregistrovaná v Intune, ale nejsou na ně zacílené žádné zásady dodržování předpisů zařízením, budou v této sestavě obsažená jako **Vyhovující předpisům**.

#### <a name="drill-down-option"></a>Možnost přechodu k podrobnostem

Když v **řídicím panelu pro dodržování předpisů zařízením** kliknete na dlaždici dodržování předpisů zařízením, můžete přejít ke konkrétnímu **stavu dodržování předpisů**, **e-mailovému aliasu uživatele**, **modelu zařízení** a **umístění** pro každé zařízení, na které cílily zásady dodržování předpisů zařízením.

![Podrobnosti na řídicím panelu pro dodržování předpisů zařízením](./media/idc-2.png)

Pokud potřebujete další podrobnosti týkající se konkrétního uživatele, můžete sestavu grafu dodržování předpisů zařízením filtrovat zadáním e-mailového aliasu uživatele.

![Konkrétní uživatel na řídicím panelu pro dodržování předpisů zařízením](./media/idc-3.png)

Můžete také kliknout na různé stavy dodržování předpisů v grafu dodržování předpisů zařízením. Tím zobrazíte další podrobnosti o stavech zásad dodržování předpisů zařízeními uživatele.

![Různé stavy na řídicím panelu pro dodržování zásad zařízením](./media/idc-4.png)

#### <a name="filter"></a>Filtr

Pokud kliknete na **tlačítko Filtr**, otevře se nabídka s těmito možnostmi:

-   Model

    -   Textové pole, kam můžete zadat libovolný hledaný řetězec
<br></br>
-   Platforma

    -   Android

    -   iOS

    -   Mac OS

    -   Windows

    -   Windows Phone

-   Stav

    -   Vyhovuje

    -   Nedodržující předpisy

    -   V období odkladu

    -   Neznámé

    -   Chyba

Pokud kliknete na **tlačítko Aktualizovat**, nabídka by se měla zavřít a výsledky by se měly aktualizovat podle zvolených kritérií filtrování.

##### <a name="device-details"></a>Podrobnosti o zařízení

Kliknutím na zařízení se otevře **okno zařízení** s vybraným zařízením. Nabízí další podrobnosti o nastavení zásad dodržování předpisů zařízením, které je na toto zařízení použité.

![Řídicí panel pro dodržování předpisů zařízením](./media/idc-6.png)

Když kliknete na samotné nastavení zásad zařízení, uvidíte název zásady dodržování předpisů zařízením, ze které nastavení dodržování předpisů zařízení cílené správcem pochází.

![Název nastavení dodržování předpisů zařízením](./media/idc-7.png)

### <a name="per-policy-device-compliance-report"></a>Sestava dodržování předpisů zařízením podle zásad

Tato sestava poskytuje zobrazení podle zásad dodržování předpisů a celkový počet zařízení v jednotlivých stavech dodržování předpisů. Dlaždice **Dodržování zásad** je k dispozici na **řídicím panelu pro dodržování předpisů zařízením** a zobrazuje všechny zásady v minulosti vytvořené správcem, platformy, pro které zásady platí, počet zařízení dodržujících předpisy a počet zařízení nedodržujících předpisy.

![Sestava dodržování předpisů zařízením podle zásad](./media/idc-8.png)

Když kliknete na dlaždici Dodržování zásad a pak na některou ze zásad dodržování předpisů zařízením, uvidíte **stav dodržování předpisů**, **e-mailový alias uživatele**, **model zařízení** a **umístění** pro každé zařízení, na které zásady dodržování předpisů zařízením cílí.

![Dlaždice Dodržování zásad](./media/idc-9.png)

### <a name="per-setting-device-compliance-report"></a>Sestava dodržování předpisů zařízením podle nastavení

Tato sestava umožňuje zobrazit celkový počet zařízení v jednotlivých stavech dodržování předpisů podle nastavení dodržování předpisů. Dlaždice **Nastavení dodržování předpisů** je k dispozici na **řídicím panelu pro dodržování předpisů zařízením** a zobrazuje všechna nastavení zásad dodržování předpisů zařízením ze všech zásad dodržování předpisů zařízením vytvořených správcem, platformy, pro které nastavení zásad platí, a počet zařízení nedodržujících předpisy.

![Sestava dodržování předpisů zařízením podle nastavení](./media/idc-10.png)

Když kliknete na dlaždici Nastavení dodržování předpisů a pak na některé z nastavení zásad dodržování předpisů zařízením, uvidíte **stav dodržování předpisů**, **e-mailový alias uživatele**, **model zařízení** a **umístění** pro každé zařízení, na které nastavení zásad dodržování předpisů zařízením cílí.

![Dlaždice Nastavení dodržování předpisů](./media/idc-11.png)
