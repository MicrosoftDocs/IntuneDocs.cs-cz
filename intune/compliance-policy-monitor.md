---
title: Monitorování zásad dodržování předpisů u zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Na řídicím panelu pro dodržování předpisů zařízením můžete monitorovat celkový stav dodržování předpisů zařízením, zobrazit sestavy a dodržování předpisů zařízením podle jednotlivých zásad a nastavení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 33e42c821881a5cc7eb9e4be65f6f7e56263480e
ms.sourcegitcommit: ada99fefe9a612ed753420116f8c801ac4bf0934
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36232966"
---
# <a name="monitor-intune-device-compliance-policies"></a>Monitorování zásad dodržování předpisů zařízením v Intune

Sestavy dodržování předpisů pomáhají správcům analyzovat stav dodržování předpisů zařízeními v organizaci a rychle vyřešit potíže související s dodržováním předpisů, na které uživatelé v organizaci narazí. Můžete zobrazit informace o celkovém stavu dodržování předpisů zařízením, stavu dodržování předpisů pro jednotlivá nastavení a stavu dodržování předpisů pro jednotlivé zásady a také procházet podrobnosti o jednotlivých zařízeních, abyste zobrazili konkrétní nastavení a zásady, které mají na zařízení vliv.

## <a name="before-you-begin"></a>Před zahájením

Podle těchto pokynů vyhledejte na portálu Azure Portal **řídicí panel Intune pro dodržování předpisů zařízením**:

1. Na webu [Azure Portal](https://portal.azure.com) se přihlaste se svými přihlašovacími údaji k Intune.

2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.

3. Vyberte **Dodržování předpisů zařízením** > **Přehled**. Otevře se **řídicí panel Dodržování předpisů zařízením**.

> [!IMPORTANT]
> Aby mohla zařízení přijímat zásady dodržování předpisů, musejí být zaregistrovaná v Intune.

## <a name="device-compliance-dashboard"></a>Řídicí panel pro dodržování předpisů zařízením

V **řídicím panelu Dodržování předpisů zařízením** můžete monitorovat dodržování předpisů různými zařízeními, stav jejich ochrany a mnoho dalšího. Můžete zobrazit tyto sestavy:

- Celkový souhrn dodržování předpisů zařízením

- Dodržování předpisů zařízením podle zásad

- Dodržování předpisů zařízením podle nastavení

- Stav ochrany zařízení

- Stav agenta hrozeb

![Obrázek řídicího panelu pro dodržování předpisů zařízením](./media/idc-1.png)

Můžete také zobrazit konkrétní zásady a nastavení dodržování předpisů, které platí pro jednotlivá zařízení, a konečný stav dodržování předpisů pro každé z těchto nastavení na zařízení.

### <a name="overall-device-compliance-aggregate-report"></a>Sestava celkového souhrnu dodržování předpisů zařízením

Jde o prstencový graf zobrazující souhrnný stav dodržování předpisů pro všechna zařízení zaregistrovaná v Intune. Stavy dodržování předpisů zařízením jsou uložené ve dvou různých databázích, Intune a Azure Active Directory. Tady jsou další podrobnosti o stavech zásad dodržování předpisů zařízením:

- **Vyhovující předpisům**: Zařízení úspěšně použilo jedno nebo více nastavení zásad dodržování předpisů zařízením zacílených správcem.

- **Nedodržující předpisy:** Zařízení se nepodařilo použít jedno nebo více nastavení zásad dodržování předpisů zařízením zacílených správcem nebo uživatel nedodržel zásady zacílené správcem.

- **V období odkladu:** Správce na zařízení zacílil jedno nebo více nastavení zásad dodržování předpisů zařízením, ale uživatel zatím zásady nepoužil. To znamená, že zařízení předpisy nedodržuje, ale je v období odkladu definovaném správcem.

  - Přečtěte si další informace o akcích pro zařízení nedodržující předpisy.

- **Zařízení není synchronizované**: Zařízení se nepodařilo oznámit svůj stav zásad dodržování předpisů zařízením z některého z následujících důvodů:

  - **Neznámý**: Zařízení je offline nebo se mu s Intune nebo Azure AD nepodařilo komunikovat z jiných důvodů.

  - **Chyba**: Zařízení se nepodařilo komunikovat s Intune a Azure AD a obdrželo chybovou zprávu s odůvodněním.

> [!IMPORTANT]
> Zařízení, která jsou zaregistrovaná v Intune, ale nejsou na ně zacílené žádné zásady dodržování předpisů zařízením, jsou v této sestavě uvedená jako **Vyhovující předpisům**.

#### <a name="drill-down-option"></a>Možnost přechodu k podrobnostem

Když na **řídicím panelu Dodržování předpisů zařízením** vyberete dlaždici Dodržování předpisů zařízením, přejdete ke **stavu dodržování předpisů**, **e-mailovému aliasu uživatele**, **modelu zařízení** a **umístění** konkrétního zařízení, pro které tyto zásady platí.

![Obrázek podrobností na řídicím panelu pro dodržování předpisů zařízením](./media/idc-2.png)

Pokud potřebujete další podrobnosti týkající se konkrétního uživatele, můžete sestavu grafu dodržování předpisů zařízením filtrovat zadáním e-mailového aliasu uživatele.

![Obrázek znázorňující konkrétního uživatele na řídicím panelu pro dodržování předpisů zařízením](./media/idc-3.png)

Můžete také kliknout na různé stavy dodržování předpisů v grafu dodržování předpisů zařízením. Tím zobrazíte další podrobnosti o stavech zásad dodržování předpisů zařízeními uživatele.

![Obrázek různých stavů na řídicím panelu pro dodržování zásad zařízením](./media/idc-4.png)

#### <a name="filter"></a>Filtr

Když vyberete **tlačítko Filtr**, otevře se kontextová nabídka s následujícími možnostmi:

- Model

  - Textové pole, kam můžete zadat libovolný hledaný řetězec

- Platforma

  - Android

  - iOS

  - macOS

  - Windows

  - Windows Phone

- Stav

  - Vyhovuje

  - Nedodržující předpisy

  - V období odkladu

  - Neznámé

  - Chyba

Když vyberete **tlačítko Aktualizovat**, kontextová nabídka se zavře a výsledky se aktualizují podle vybraných filtrovacích kritérií.

##### <a name="device-details"></a>Podrobnosti o zařízení

Po výběru zařízení se otevře nabídka **Zařízení** s vybraným zařízením. Nabízí podrobnější informace o zásadách dodržování předpisů nastavených pro dané zařízení.

Když vyberete samotné nastavení zásad zařízení, můžete se podívat, z jaké zásady dodržování předpisů pro zařízení vychází nastavení dodržování předpisů daného zařízení, které provedl správce.

### <a name="devices-without-compliance-policy"></a>Zařízení bez zásad dodržování předpisů
Podle této sestavy zjistíte zařízení, která nemají přiřazené zásady dodržování předpisů. Pokud zavedete nastavení zabezpečení, které označí všechna zařízení bez zásad dodržování předpisů jako nevyhovující, je důležité, abyste dokázali tato zařízení identifikovat. Potom jim můžete přiřadit aspoň jednu zásadu dodržování předpisů.

> [!NOTE]
> Nové nastavení zabezpečení můžete konfigurovat na portálu Intune. Vyberte **Dodržování předpisů zařízením** a v části **Nastavení** zvolte **Nastavení zásad dodržování předpisů**. Pak přepínačem nastavte možnost **Označit zařízení, která nemají přiřazené žádné zásady dodržování předpisů, jako** na **Vyhovující předpisům** nebo **Nevyhovující předpisům**. Další informace najdete v článku o [vylepšeních zabezpečení ve službě Intune](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/).

![Obrázek sestavy Zařízení bez zásad dodržování předpisů](./media/idc-12.png)

Dlaždice **Zařízení bez zásad dodržování předpisů** je dostupná na panelu Dodržování předpisů zařízením. Tato sestava zobrazuje všechna zařízení bez zásad dodržování předpisů, uživatele zařízení, stav kompatibility a model zařízení.

> [!NOTE]
> Uživatelé, kteří mají přiřazen kterýkoli typ zásady dodržování předpisů, se v sestavě nezobrazí (bez ohledu na platformu zařízení). Když například uživateli se zařízením Android omylem přiřadíte zásadu dodržování předpisů pro Windows, jeho zařízení se v sestavě nezobrazí. Intune ale toto zařízení s Androidem vyhodnotí jako nevyhovující. Pokud se chcete podobným problémům vyhnout, doporučujeme vytvářet zásady pro každou platformu zařízení zvlášť a nasazovat je u všech uživatelů.

### <a name="per-policy-device-compliance-report"></a>Sestava dodržování předpisů zařízením podle zásad

Tato sestava poskytuje zobrazení podle zásad dodržování předpisů a celkový počet zařízení v jednotlivých stavech dodržování předpisů. Dlaždice **Dodržování zásad** je k dispozici na **řídicím panelu pro dodržování předpisů zařízením** a zobrazuje všechny zásady v minulosti vytvořené správcem, platformy, pro které zásady platí, počet zařízení dodržujících předpisy a počet zařízení nedodržujících předpisy.

![Obrázek sestavy dodržování předpisů zařízením podle zásad](./media/idc-8.png)

Když kliknete na dlaždici Dodržování zásad a pak na některou ze zásad dodržování předpisů zařízením, uvidíte **stav dodržování předpisů**, **e-mailový alias uživatele**, **model zařízení** a **umístění** pro každé zařízení, na které zásady dodržování předpisů zařízením cílí.

## <a name="setting-compliance-report"></a>Sestava Nastavení dodržování předpisů

Tato sestava umožňuje zobrazit celkový počet zařízení v jednotlivých stavech dodržování předpisů podle nastavení dodržování předpisů. Dlaždice **Nastavení dodržování předpisů** je k dispozici na **řídicím panelu pro dodržování předpisů zařízením** a zobrazuje všechna nastavení zásad dodržování předpisů zařízením ze všech zásad dodržování předpisů zařízením vytvořených správcem, platformy, pro které nastavení zásad platí, a počet zařízení nedodržujících předpisy.

![Obrázek sestavy dodržování předpisů zařízením podle nastavení](./media/idc-10.png)

Když kliknete na dlaždici Nastavení dodržování předpisů a pak na některé z nastavení zásad dodržování předpisů zařízením, uvidíte **stav dodržování předpisů**, **e-mailový alias uživatele**, **model zařízení** a **umístění** pro každé zařízení, na které nastavení zásad dodržování předpisů zařízením cílí.

## <a name="how-intune-resolves-policy-conflicts"></a>Způsob řešení konfliktů zásad v Intune
Konflikty zásad můžou vzniknout, když se na zařízení použije více zásad Intune. Pokud se nastavení zásad překrývají, vyřeší Intune všechny konflikty s použitím následujících pravidel:

- Pokud konfliktní nastavení pocházejí ze zásad konfigurace a dodržování předpisů služby Intune, bude mít nastavení v zásadách dodržování předpisů přednost před nastavením v zásadách konfigurace. Platí to i v situaci, kdy je nastavení v zásadách konfigurace bezpečnější.

- Pokud jste nasadili více zásad dodržování předpisů, použije Intune ty nejbezpečnější z nich.
