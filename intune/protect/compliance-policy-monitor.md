---
title: Monitorování zásad dodržování předpisů u zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Na řídicím panelu pro dodržování předpisů zařízením můžete monitorovat celkový stav dodržování předpisů zařízením, zobrazit sestavy a dodržování předpisů zařízením podle jednotlivých zásad a nastavení.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 1/14/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 844e93f3a063ae43342d2967cbd544f3ec425c21
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74410152"
---
# <a name="monitor-intune-device-compliance-policies"></a>Monitorování zásad dodržování předpisů zařízením v Intune

Sestavy dodržování předpisů slouží ke kontrole dodržování předpisů zařízeními a řešení problémů souvisejících s dodržováním předpisů ve vaší organizaci. Pomocí těchto sestav můžete zobrazit následující informace:

- Celkový stav dodržování předpisů zařízeními
- Stav dodržování předpisů pro individuální nastavení
- Stav dodržování předpisů pro individuální zásadu
- Podrobnosti o jednotlivých zařízeních otevřené za účelem zobrazení konkrétních nastavení a zásad, které mají vliv na zařízení

## <a name="open-the-compliance-dashboard"></a>Otevření řídicího panelu pro dodržování předpisů

Otevřete **řídicí panel Intune pro dodržování předpisů zařízením**:

1. Sign in to [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Vyberte **Dodržování předpisů zařízením** > **Přehled**. Otevře se **řídicí panel Dodržování předpisů zařízením**.

> [!IMPORTANT]
> Aby mohla zařízení přijímat zásady dodržování předpisů, musejí být zaregistrovaná v Intune.

## <a name="dashboard-overview"></a>Přehled řídicího panelu

Po otevření řídicího panelu se zobrazí přehled se všemi sestavami dodržování předpisů. V těchto sestavách můžete kontrolovat:

- Celkové dodržování předpisů u zařízení
- Dodržování předpisů zařízením podle zásad
- Dodržování předpisů zařízením podle nastavení
- Stav agenta hrozeb
- Stav ochrany zařízení

![Obrázek řídicího panelu s řídicím panelem pro dodržování předpisů zařízením a různými sestavami](./media/compliance-policy-monitor/idc-1.png)

Když se do těchto sestav ponoříte, najdete také specifické zásady dodržování předpisů a nastavení pro konkrétní zařízení, včetně stavu dodržování předpisů pro každé nastavení.

### <a name="device-compliance-status"></a>Device compliance status

The **Device compliance status** chart shows the compliance states for all Intune enrolled devices. Stavy jsou uložené ve dvou různých databázích – Intune a Azure Active Directory.

> [!IMPORTANT]
> Intune follows the device check-in schedule for all compliance evaluations on the device. [Learn more about the device check-in schedule](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

Podrobnosti o různých stavech zásad dodržování předpisů zařízením jsou následující:

- **Vyhovující předpisům**: Zařízení úspěšně použilo jedno nebo více nastavení zásad dodržování předpisů zařízením.

- **V období odkladu**: Na zařízení je zacíleno jedno nebo více nastavení zásad dodržování předpisů zařízením. Koncový uživatel ale zásady ještě nepoužil. To znamená, že zařízení předpisy nedodržuje, ale je v období odkladu definovaném správcem.

  - Přečtěte si další informace o [akcích pro zařízení nedodržující předpisy](actions-for-noncompliance.md).

- **Nevyhodnoceno**: Počáteční stav všech nově zaregistrovaných zařízení. Other possible reasons for this state include:

  - Devices that aren't assigned a compliance policy and don't have a trigger to check for compliance
  - Devices that haven't checked in since the compliance policy was last updated
  - Devices not associated to a specific user, such as:
    - iOS devices purchased through Apple's Device Enrollment Program (DEP) that don't have user affinity
    - Android kiosk or Android Enterprise dedicated devices
  - Devices enrolled with a device enrollment manager (DEM) account

- **Nedodržující předpisy**: Zařízení se nepodařilo použít jedno nebo více nastavení zásad dodržování předpisů zařízením. Případně zásady nedodržel uživatel.

- **Zařízení není synchronizované**: Zařízení se nepodařilo oznámit svůj stav zásad dodržování předpisů zařízením z některého z následujících důvodů:

  - **Neznámý**: Zařízení je offline nebo se mu s Intune nebo Azure AD nepodařilo komunikovat z jiných důvodů.

  - **Chyba**: Zařízení se nepodařilo komunikovat s Intune a Azure AD a obdrželo chybovou zprávu s odůvodněním.

> [!IMPORTANT]
> Zařízení, která jsou zaregistrovaná v Intune, ale nejsou na ně zacílené žádné zásady dodržování předpisů zařízením, jsou v této sestavě uvedená jako **Vyhovující předpisům**.

#### <a name="drill-down-for-more-details"></a>Zobrazení podrobností

V grafu **Stav dodržování předpisů pro zařízení** vyberte některý stav. Můžete například vybrat **Nedodržující předpisy**:

![Výběr stavu dodržování předpisů](./media/compliance-policy-monitor/select-not-compliant-status.png)

That action opens the **Device compliance** window, and displays devices in a **Device status** chart. The chart shows you more details on the devices in that state, including operating system platform, last check-in date, and more. 

![Snímek řídicího panelu s podrobnostmi o zařízeních v příslušném stavu](./media/compliance-policy-monitor/drill-down-details.png)

Pokud chcete zobrazit všechna zařízení vlastněná konkrétním uživatelem, můžete sestavu grafu také filtrovat zadáním jeho e-mailové adresy.

#### <a name="filter-and-columns"></a>Filtrování a sloupce

![Výběr tlačítek Filtrovat a Sloupce pro změnu výsledků zobrazených v grafu](./media/compliance-policy-monitor/filter-columns.png)

When you select the **Filter** button, the filter fly-out opens with more options, including the **Compliance** state, **Jailbroken** devices, and more. Kliknutím na **Použít** výsledky aktualizujete.

Pomocí vlastnosti **Sloupce** můžete ve výstupním grafu přidávat nebo odebírat sloupce. Například sloupec **Hlavní název uživatele** může zobrazovat e-mailovou adresu zaregistrovanou na zařízení. Kliknutím na **Použít** výsledky aktualizujete.

#### <a name="device-details"></a>Podrobnosti o zařízení

In the **Device details** chart, select a specific device, and then select **Device compliance**:

![Výběr zařízení a možnosti Dodržování předpisů zařízením pro zobrazení použitých zásad dodržování předpisů](./media/compliance-policy-monitor/see-policies-applied-specific-device.png)

Intune displays more details on the device compliance policy settings applied on that device. Když některou ze zásad vyberete, zobrazí se všechna její nastavení.

### <a name="devices-without-compliance"></a>Devices without compliance

On the *Compliance status* page, next to the *Policy compliance* chart, you can select the **Devices without compliance policy** tile to view information about devices that don't have any compliance policies assigned:

![Zobrazení zařízení bez zásad dodržování předpisů](./media/compliance-policy-monitor/devices-without-policies.png)

Když tuto dlaždici vyberete, zobrazí se všechna zařízení bez zásad dodržování předpisů. Kromě toho jsou zde uvedeny informace o uživateli zařízení, stavu nasazení zásady a modelu zařízení.

#### <a name="what-you-need-to-know"></a>Co je potřeba vědět

- U nastavení zabezpečení **Označit zařízení, která nemají přiřazené žádné zásady dodržování předpisů, jako** je důležité určit zařízení bez zásad dodržování předpisů. Potom jim můžete přiřadit aspoň jednu zásadu dodržování předpisů.

  Nastavení zabezpečení můžete konfigurovat na portálu Intune. To to **Devices** > **Compliance policies** > **Compliance policy settings**. Potom nastavte možnost **Označit zařízení, která nemají přiřazené žádné zásady dodržování předpisů, jako** na **Vyhovující předpisům**, nebo **Nevyhovující předpisům**. 

  Další informace najdete v článku o [vylepšeních zabezpečení ve službě Intune](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/).

- Uživatelé, kteří mají přiřazen kterýkoli typ zásady dodržování předpisů, se v sestavě nezobrazí (bez ohledu na platformu zařízení). Pokud jste například uživateli se zařízením s Androidem přiřadili zásadu dodržování předpisů pro Windows, jeho zařízení se v sestavě nezobrazí. Intune ale toto zařízení s Androidem vyhodnotí jako nevyhovující. Pokud se chcete podobným problémům vyhnout, doporučujeme vytvářet zásady pro každou platformu zařízení zvlášť a nasazovat je u všech uživatelů.

### <a name="per-policy-device-compliance"></a>Dodržování předpisů zařízením podle zásad

The **Policy compliance** chart shows you the policies, and how many devices are compliant and noncompliant. 

![Snímek seznamu zásad s počtem zařízení, které je splňují a nesplňují](./media/compliance-policy-monitor/idc-8.png)

### <a name="setting-compliance"></a>Dodržování nastavení

The **Setting compliance** chart shows you all device compliance policy settings from all compliance policies, the platforms the policy settings are applied, and the number of noncompliant devices.

![Snímek seznamu všech nastavení v různých zásadách](./media/compliance-policy-monitor/idc-10.png)

> [!NOTE]
> A policy can be assigned to a device, and a user on that same device. In some scenarios, a device may sync before the user signs in, such as when the device reboots. Compliance may evaluate this user, and show the device as non compliant. This behavior may also show the System Account as a non-compliant user.
>
> This is a known issue with multi-user Windows 10 devices. Any changes or updates on this behavior are announced in [in development](../fundamentals/in-development.md) and/or [what's new](../fundamentals/whats-new.md).

## <a name="view-compliance-reports"></a>View compliance reports

In addition to using the charts on *Compliance status*, you can view compliance reports from the *Monitor* page of the Admin Center.

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Devices** > **Monitor**, and then from below **Compliance** select the report you want to view. Some of the available compliance reports include:

   - Dodržování předpisů zařízení
   - Noncompliant devices
   - Zařízení bez zásad dodržování předpisů
   - Dodržování nastavení
   - Policy compliance
   - Windows health attestation report
   - Stav agenta hrozeb

For more information about reports, see [Intune reports](../fundamentals/reports.md)

## <a name="view-status-of-device-policies"></a>Zobrazení stavu zásad zařízení

Různé stavy zásad můžete zkontrolovat podle platformy. Máte například zásady dodržování předpisů v macOS. Chcete zobrazit zařízení, které jsou těmito zásadami ovlivněné, a zjistit, jestli se vyskytly konflikty nebo chyby.

Tato funkce je zahrnutá v sestavách stavu zařízení:

1. Select **Devices** > **Compliance policies** > **Policies**. Zobrazí se seznam zásad včetně platformy, pokud je příslušná zásada přiřazená, a další podrobnosti.
2. Vyberte zásadu > **Přehled**. Přiřazení zásad v tomto zobrazení zahrnuje následující stavy:

    - **Succeeded**: Policy is applied
    - **Error**: The policy failed to apply. Tato zpráva se obvykle zobrazí s chybovým kódem, který odkazuje na vysvětlení. 
    - **Conflict**: Two settings are applied to the same device, and Intune can't sort out the conflict. Správce by měl provést kontrolu.
    - **Pending**: The device hasn’t checked in with Intune to receive the policy yet. 
    - **Not applicable**: The device can't receive the policy. Zásada například aktualizuje nastavení pro iOS 11.1, ale zařízení používá iOS 10. 

3. Pokud chcete zobrazit podrobnosti o zařízeních používajících tyto zásady, vyberte některý stav. Vyberte například **Úspěšné**. V dalším okně se zobrazí podrobnosti o konkrétním zařízení včetně jeho názvu a stavu nasazení.

## <a name="how-intune-resolves-policy-conflicts"></a>Způsob řešení konfliktů zásad v Intune
Konflikty zásad můžou vzniknout, když se na zařízení použije více zásad Intune. Pokud se nastavení zásad překrývají, vyřeší Intune všechny konflikty s použitím následujících pravidel:

- Pokud konfliktní nastavení pocházejí ze zásad konfigurace a dodržování předpisů služby Intune, bude mít nastavení v zásadách dodržování předpisů přednost před nastavením v zásadách konfigurace. Platí to i v situaci, kdy je nastavení v zásadách konfigurace bezpečnější.

- Pokud jste nasadili více zásad dodržování předpisů, použije Intune ty nejbezpečnější z nich.
