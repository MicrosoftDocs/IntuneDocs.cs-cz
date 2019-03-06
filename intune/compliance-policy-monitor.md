---
title: Monitorování zásad dodržování předpisů u zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Na řídicím panelu pro dodržování předpisů zařízením můžete monitorovat celkový stav dodržování předpisů zařízením, zobrazit sestavy a dodržování předpisů zařízením podle jednotlivých zásad a nastavení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 654d5b86a8a2df8eaddc8ea626b55390d2d32920
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57389195"
---
# <a name="monitor-intune-device-compliance-policies"></a>Monitorování zásad dodržování předpisů zařízením v Intune

Sestavy dodržování předpisů slouží ke kontrole dodržování předpisů zařízeními a řešení problémů souvisejících s dodržováním předpisů ve vaší organizaci. Pomocí těchto sestav můžete zobrazit následující informace:

- Celkový stav dodržování předpisů zařízeními
- Stav dodržování předpisů pro individuální nastavení
- Stav dodržování předpisů pro individuální zásadu
- Podrobnosti o jednotlivých zařízeních otevřené za účelem zobrazení konkrétních nastavení a zásad, které mají vliv na zařízení

## <a name="open-the-compliance-dashboard"></a>Otevření řídicího panelu pro dodržování předpisů

Otevřete **řídicí panel Intune pro dodržování předpisů zařízením**:

1. Na [portálu Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.

2. Vyberte **Dodržování předpisů zařízením** > **Přehled**. Otevře se **řídicí panel Dodržování předpisů zařízením**.

> [!IMPORTANT]
> Aby mohla zařízení přijímat zásady dodržování předpisů, musejí být zaregistrovaná v Intune.

## <a name="dashboard-overview"></a>Přehled řídicího panelu

Po otevření řídicího panelu se zobrazí přehled se všemi sestavami dodržování předpisů. V těchto sestavách můžete kontrolovat:

- Celkové dodržování předpisů u zařízení
- Dodržování předpisů zařízením podle zásad
- Dodržování předpisů zařízením podle nastavení
- Stav ochrany zařízení
- Stav agenta hrozeb

![Obrázek řídicího panelu s řídicím panelem pro dodržování předpisů zařízením a různými sestavami](./media/compliance-policy-monitor/idc-1.png)

Když se do těchto sestav ponoříte, najdete také specifické zásady dodržování předpisů a nastavení pro konkrétní zařízení, včetně stavu dodržování předpisů pro každé nastavení.

### <a name="device-compliance-status-report"></a>Stav dodržování předpisů pro zařízení

Tento graf zobrazuje stav dodržování předpisů pro všechna zařízení zaregistrovaná v Intune. Stavy dodržování předpisů zařízením jsou uloženy ve dvou různých databázích: Intune a Azure Active Directory. 

> [!IMPORTANT]
> Intune se řídí zařízení vrácení se změnami plán pro všechna hodnocení dodržování předpisů na zařízení. [Další informace o zařízení vrácení se změnami plánu](https://docs.microsoft.com/intune/device-profile-troubleshoot#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

Podrobnosti o různých stavech zásad dodržování předpisů zařízením jsou následující:

- **Kompatibilní**: Zařízení úspěšně použilo jedno nebo více nastavení zásad dodržování předpisů zařízení.

- **V období odkladu:** Zařízení je cílem jednoho nebo více nastavení zásad dodržování předpisů zařízením. Koncový uživatel ale zásady ještě nepoužil. To znamená, že zařízení předpisy nedodržuje, ale je v období odkladu definovaném správcem.

  - Přečtěte si další informace o [akcích pro zařízení nedodržující předpisy](actions-for-noncompliance.md).

- **Nevyhodnoceno**: Počáteční stav pro nově registrovaná zařízení. Další možné příčiny tohoto stavu stavu:

  - Zařízení, které nejsou přiřazené zásady dodržování předpisů a nemáte aktivační události ke kontrole dodržování předpisů
  - Zařízení, která nebyla vrácena se změnami od poslední aktualizace zásad dodržování předpisů
  - Zařízení není přidružen k specifické pro uživatele
  - Zařízení zaregistrovaná pomocí účtu správce registrace zařízení

- **Nedodržující předpisy:** Zařízení se nepodařilo použít jednu nebo více nastavení zásad dodržování předpisů zařízením. Případně zásady nedodržel uživatel.

- **Zařízení není synchronizované:** Zařízení se nepodařilo oznámit svůj stav zásad dodržování předpisů zařízení, protože jeden z následujících důvodů:

  - **Neznámý**: Zařízení je offline nebo se nepodařilo komunikovat s Intune nebo Azure AD z jiných důvodů.

  - **Chyba**: Zařízení se nepodařilo komunikovat s Intune a Azure AD a obdrželo chybovou zprávu s odůvodněním.

> [!IMPORTANT]
> Zařízení, která jsou zaregistrovaná v Intune, ale nejsou na ně zacílené žádné zásady dodržování předpisů zařízením, jsou v této sestavě uvedená jako **Vyhovující předpisům**.

#### <a name="drill-down-for-more-details"></a>Zobrazení podrobností

V grafu **Stav dodržování předpisů pro zařízení** vyberte některý stav. Můžete například vybrat **Nedodržující předpisy**:

![Výběr stavu dodržování předpisů](./media/compliance-policy-monitor/select-not-compliant-status.png)

Zde vidíte podrobnosti o zařízeních ve zvoleném stavu včetně platformy operačního systému, data posledního ohlášení atd. 

![Snímek řídicího panelu s podrobnostmi o zařízeních v příslušném stavu](./media/compliance-policy-monitor/drill-down-details.png)

Pokud chcete zobrazit všechna zařízení vlastněná konkrétním uživatelem, můžete sestavu grafu také filtrovat zadáním jeho e-mailové adresy.

#### <a name="filter-and-columns"></a>Filtrování a sloupce

![Výběr tlačítek Filtrovat a Sloupce pro změnu výsledků zobrazených v grafu](./media/compliance-policy-monitor/filter-columns.png)

Při výběru tlačítka **Filtrovat** se otevře nabídka filtrů s dalšími možnostmi, jako je stav dodržování předpisů, zařízení s jailbreakem a další. Kliknutím na **Použít** výsledky aktualizujete.

Pomocí vlastnosti **Sloupce** můžete ve výstupním grafu přidávat nebo odebírat sloupce. Například sloupec **Hlavní název uživatele** může zobrazovat e-mailovou adresu zaregistrovanou na zařízení. Kliknutím na **Použít** výsledky aktualizujete.

#### <a name="device-details"></a>Podrobnosti o zařízení

V grafu vyberte požadované zařízení a potom vyberte **Dodržování předpisů zařízením**:

![Výběr zařízení a možnosti Dodržování předpisů zařízením pro zobrazení použitých zásad dodržování předpisů](./media/compliance-policy-monitor/see-policies-applied-specific-device.png)

Zde najdete podrobnější informace o zásadách dodržování předpisů nastavených pro dané zařízení. Když některou ze zásad vyberete, zobrazí se všechna její nastavení.

### <a name="devices-without-compliance-policy"></a>Zařízení bez zásad dodržování předpisů
V sestavě **Dodržování předpisů zařízením** > **Přehled** najdete zařízení, která nemají přiřazené žádné zásady dodržování předpisů.

![Zobrazení zařízení bez zásad dodržování předpisů](./media/compliance-policy-monitor/devices-without-policies.png)

Když tuto dlaždici vyberete, zobrazí se všechna zařízení bez zásad dodržování předpisů. Kromě toho jsou zde uvedeny informace o uživateli zařízení, stavu nasazení zásady a modelu zařízení.

#### <a name="what-you-need-to-know"></a>Co je potřeba vědět

- U nastavení zabezpečení **Označit zařízení, která nemají přiřazené žádné zásady dodržování předpisů, jako** je důležité určit zařízení bez zásad dodržování předpisů. Potom jim můžete přiřadit aspoň jednu zásadu dodržování předpisů.

  Nastavení zabezpečení můžete konfigurovat na portálu Intune. Vyberte **Dodržování předpisů zařízením** > **Nastavení zásad dodržování předpisů**. Potom nastavte možnost **Označit zařízení, která nemají přiřazené žádné zásady dodržování předpisů, jako** na **Vyhovující předpisům**, nebo **Nevyhovující předpisům**. 

  Další informace najdete v článku o [vylepšeních zabezpečení ve službě Intune](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/).

- Uživatelé, kteří mají přiřazen kterýkoli typ zásady dodržování předpisů, se v sestavě nezobrazí (bez ohledu na platformu zařízení). Pokud jste například uživateli se zařízením s Androidem přiřadili zásadu dodržování předpisů pro Windows, jeho zařízení se v sestavě nezobrazí. Intune ale toto zařízení s Androidem vyhodnotí jako nevyhovující. Pokud se chcete podobným problémům vyhnout, doporučujeme vytvářet zásady pro každou platformu zařízení zvlášť a nasazovat je u všech uživatelů.

### <a name="per-policy-device-compliance-report"></a>Sestava dodržování předpisů zařízením podle zásad

V sestavě **Dodržování předpisů zařízením** > **Dodržování zásad** se zobrazují zásady a počet zařízení, které předpisy dodržují, respektive nedodržují. 

![Snímek seznamu zásad s počtem zařízení, které je splňují a nesplňují](./media/compliance-policy-monitor/idc-8.png)

Když některou ze zásad dodržování předpisů vyberete, zobrazí se pro každé zařízení cílené touto zásadou **stav kompatibility**, **e-mailový alias uživatele**, **model zařízení** a **poloha**.

## <a name="setting-compliance-report"></a>Sestava Nastavení dodržování předpisů

Sestava **Dodržování předpisů zařízením** > **Nastavení dodržování předpisů** umožňuje zobrazit celkový počet zařízení v jednotlivých stavech dodržování předpisů podle nastavení dodržování předpisů. Najdete v ní všechna nastavení zásad dodržování předpisů pro zařízení ze všech zásad dodržování předpisů, platformy, na kterých se nastavení zásad používají, a počet zařízení nedodržujících předpisy.

![Snímek seznamu všech nastavení v různých zásadách](./media/compliance-policy-monitor/idc-10.png)

Když některé nastavení vyberete, zobrazí se pro každé zařízení cílené tímto nastavením **stav kompatibility**, **e-mailový alias uživatele**, **model zařízení** a **poloha**.

> [!NOTE]
> Na zařízeních s Windows 10 nepřipojených ke službě Azure AD se systémový účet může zobrazit jako uživatel nevyhovující předpisům. Jedná se o očekávané chování, které neovlivňuje celkový stav dodržování předpisů zařízením. 

## <a name="view-status-of-device-policies"></a>Zobrazení stavu zásad zařízení

Různé stavy zásad můžete zkontrolovat podle platformy. Máte například zásady dodržování předpisů v macOS. Chcete zobrazit zařízení, které jsou těmito zásadami ovlivněné, a zjistit, jestli se vyskytly konflikty nebo chyby.

Tato funkce je zahrnutá v sestavách stavu zařízení:

1. Vyberte **Dodržování předpisů zařízením** > **Zásady**. Zobrazí se seznam zásad včetně platformy, pokud je příslušná zásada přiřazená, a další podrobnosti.
2. Vyberte zásadu > **Přehled**. Přiřazení zásad v tomto zobrazení zahrnuje následující stavy:

    - Úspěšné: Zásady platí
    - Chyba: Použití zásad se nezdařilo. Tato zpráva se obvykle zobrazí s chybovým kódem, který odkazuje na vysvětlení. 
    - Konflikt: Dvě nastavení se použijí pro stejné zařízení a Intune nemůže zařadit konflikt. Správce by měl provést kontrolu.
    - Čekající na vyřízení: Intune přijímat zásady ještě nějakou dobu nepřipojilo k zařízení. 
    - Není k dispozici: Zařízení nejde získat zásady. Zásada například aktualizuje nastavení pro iOS 11.1, ale zařízení používá iOS 10. 

3. Pokud chcete zobrazit podrobnosti o zařízeních používajících tyto zásady, vyberte některý stav. Vyberte například **Úspěšné**. V dalším okně se zobrazí podrobnosti o konkrétním zařízení včetně jeho názvu a stavu nasazení.

## <a name="how-intune-resolves-policy-conflicts"></a>Způsob řešení konfliktů zásad v Intune
Konflikty zásad můžou vzniknout, když se na zařízení použije více zásad Intune. Pokud se nastavení zásad překrývají, vyřeší Intune všechny konflikty s použitím následujících pravidel:

- Pokud konfliktní nastavení pocházejí ze zásad konfigurace a dodržování předpisů služby Intune, bude mít nastavení v zásadách dodržování předpisů přednost před nastavením v zásadách konfigurace. Platí to i v situaci, kdy je nastavení v zásadách konfigurace bezpečnější.

- Pokud jste nasadili více zásad dodržování předpisů, použije Intune ty nejbezpečnější z nich.
