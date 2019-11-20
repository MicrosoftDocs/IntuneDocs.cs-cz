---
title: Create device compliance policies in Microsoft Intune - Azure | Microsoft Docs
description: Create device compliance policies, overview of status and severity levels, using the InGracePeriod status, working with Conditional Access, handling devices without an assigned policy, and the differences in compliance in the Azure portal and classic portal in Microsoft Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
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
ms.openlocfilehash: c8452f9b56032864380ec703bfd444dc85ef129b
ms.sourcegitcommit: 13fa1a4a478cb0e03c7f751958bc17d9dc70010d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188266"
---
# <a name="create-a-compliance-policy-in-microsoft-intune"></a>Create a compliance policy in Microsoft Intune

Zásady dodržování předpisů pro zařízení jsou klíčovou funkcí Intune, která umožňuje chránit prostředky organizace. In Intune, you can create rules and settings that devices must meet to be considered compliant, such as a minimum OS version. If the device isn't compliant, you can then block access to data and resources using [Conditional Access](conditional-access.md).

You can also take actions for non-compliance, such as sending a notification email to the user. For an overview of what compliance policies do, and how they're used, see [get started with device compliance](device-compliance-get-started.md).

V tomto článku najdete:

- Lists the prerequisites and steps to create a compliancy policy.
- Shows you how to assign the policy to your user and device groups.
- Describes additional features, including scope tags to "filter" your policies, and steps you can take on devices that aren't compliant.
- Lists the check-in refresh cycle times when devices receive policy updates.

## <a name="before-you-begin"></a>Před zahájením

To use device compliance policies, be sure you:

- Použití následujících předplatných:

  - Intune
  - If you use Conditional Access, then you need Azure Active Directory (AD) Premium edition. [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/) lists what you get with the different editions. Intune compliance doesn't require Azure AD.

- Použití podporované platformy:

  - Android device administrator
  - Android Enterprise
  - iOS
  - macOS
  - Windows 10
  - Windows 8.1
  - Wvdows Phone 8.1

- Enroll devices in Intune (required to see the compliance status)

- Enroll devices to one user, or enroll without a primary user. Devices enrolled to multiple users aren't supported.

## <a name="create-the-policy"></a>Create the policy

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Devices** > **Compliance policies** > **Create Policy**.

3. Specify the following properties:

   - **Name**: Enter a descriptive name for the policy. Name your policies so you can easily identify them later. For example, a good policy name is **Mark iOS jailbroken devices as not compliant**.

   - **Description**: Enter a description for the policy. Toto nastavení není povinné, ale doporučujeme ho zadat.

   - **Platform**: Choose the platform of your devices. Možnosti:
     - **Android device administrator**
     - **Android Enterprise**
     - **iOS/iPadOS**
     - **macOS**
     - **Windows Phone 8.1**
     - **Windows 8.1 a novější**
     - **Windows 10 a novější**

     For *Android Enterprise*, you must then select a **Profile type**:
     - **Device owner**
     - **Work Profile**

   - **Settings**: The following articles list and describe the settings for each platform:
     - [Android device administrator](compliance-policy-create-android.md)
     - [Android Enterprise](compliance-policy-create-android-for-work.md)
     - [iOS/iPadOS](compliance-policy-create-ios.md)
     - [macOS](compliance-policy-create-mac-os.md)
     - [Windows Phone 8.1, Windows 8.1 and later](compliance-policy-create-windows-8-1.md)
     - [Windows 10 a novější](compliance-policy-create-windows.md)  

   - **Locations** *(Android device administrator)* : In your policy, you can force compliance by the location of the device. Choose from existing locations. Žádné umístění ještě nemáte? [Use Locations (network fence)](use-network-locations.md) in Intune provides some guidance.  

   - **Actions for noncompliance**: For devices that don't meet your compliance policies, you can add a sequence of actions to apply automatically. Pokud je zařízení označené jako nevyhovující, můžete plán třeba další den změnit. Můžete také nakonfigurovat druhou akci, která uživateli nevyhovujícího zařízení pošle e-mail.

     Další informace, včetně návodu na vytvoření e-mailu s oznámením pro uživatele, najdete v článku o [přidání akcí pro nevyhovující zařízení](actions-for-noncompliance.md).

     Pokud například používáte funkci Umístění, přidáte do zásady dodržování předpisů nějaké umístění a vyberete aspoň jedno umístění, použije se pro nevyhovující zařízení výchozí akce. Pokud zařízení není připojené k vybraným umístěním, považuje se hned za nevyhovující. Uživatelům můžete dát určitou lhůtu, třeba jeden den.

   - **Scope (Tags)** : Scope tags are a great way to assign and filter policies to specific groups, such as Sales, HR, All US-NC employees, and so on. After you add the settings, you can also add a scope tag to your compliance policies. [Use scope tags to filter policies](../fundamentals/scope-tags.md) is a good resource.

4. When finished, select **OK** > **Create** to save your changes. The policy is created, and shown in the list. Next, assign the policy to your groups.

## <a name="assign-the-policy"></a>Přiřazení zásady

Once a policy is created, the next step is to assign the policy to your groups:

1. Choose a policy you created. Existing policies are in **Devices** > **Compliance policies** > **Policies**.

2. Select the *policy* > **Assignments**. Můžete zahrnout nebo vyloučit skupiny zabezpečení služby Azure Active Directory (AD).

3. Vyberte **Vybrané skupiny** a zobrazte skupiny zabezpečení Azure AD. Select the groups you want this policy to apply > Choose **Save** to deploy the policy.

The users or devices targeted by your policy are evaluated for compliance when they check-in with Intune.

### <a name="evaluate-how-many-users-are-targeted"></a>Evaluate how many users are targeted

When you assign the policy, you can also **Evaluate** how many users are affected. This feature calculates users; it doesn't calculate devices.

1. In Intune, select **Devices** > **Compliance policies** > **Policies**.

2. Select a *policy* > **Assignments** > **Evaluate**. A message shows you how many users are targeted by this policy.

If the **Evaluate** button is grayed out, make sure the policy is assigned to one or more groups.

<!-- ## Actions for noncompliance

For devices that don't meet your compliance policies, you can add a sequence of actions to apply automatically. You can change the schedule when the device is marked non-compliant, such as after one day. You can also configure a second action that sends an email to the user when the device isn't compliant.

[Add actions for noncompliant devices](actions-for-noncompliance.md) provides more information, including creating a notification email to your users.

For example, you're using the Locations feature, and add a location in a compliance policy. The default action for noncompliance applies when you select at least one location. If the device isn't connected to the selected locations, it's immediately considered not compliant. You can give your users a grace period, such as one day.

## Scope tags

Scope tags are a great way to assign and filter policies to specific groups, such as Sales, HR, All US-NC employees, and so on. After you add the settings, you can also add a scope tag to your compliance policies. [Use scope tags to filter policies](../fundamentals/scope-tags.md) is a good resource.
-->

## <a name="refresh-cycle-times"></a>Refresh cycle times

Intune uses different refresh cycles to check for updates to compliance policies. If the device recently enrolled, the check-in runs more frequently. [Policy and profile refresh cycles](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) lists the estimated refresh times.

At any time, users can open the Company Portal app, and sync the device to immediately check for policy updates.

### <a name="assign-an-ingraceperiod-status"></a>Přiřazení stavu V období odkladu

Stav V období odkladu u zásad dodržování předpisů představuje hodnotu. Tuto hodnotu určuje kombinace období odkladu a skutečný stav daných zásad dodržování předpisů u zařízení.

Konkrétně, pokud má zařízení pro přiřazené zásady dodržování předpisů stav Nevyhovující předpisům a:

- The device has no grace period assigned to it, then the assigned value for the compliance policy is NonCompliant
- The device has a grace period that's expired, then the assigned value for the compliance policy is NonCompliant
- The device has a grace period that's in the future, then the assigned value for the compliance policy is InGracePeriod

V následující tabulce najdete souhrnný přehled těchto bodů:

|Skutečný stav dodržování předpisů|Hodnota přiřazeného období odkladu|Účinný stav dodržování předpisů|
|---------|---------|---------|
|Nevyhovující předpisům |Bez přiřazeného období odkladu |Nevyhovující předpisům |
|Nevyhovující předpisům |Včerejší datum|Nevyhovující předpisům|
|Nevyhovující předpisům |Zítřejší datum|V období odkladu|

Další informace o monitorování zásad dodržování předpisů zařízením najdete v článku [Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md).

### <a name="assign-a-resulting-compliance-policy-status"></a>Přiřazení výsledného stavu zásad dodržování předpisů

Pokud má nějaké zařízení několik zásad dodržování předpisů a pro dvě nebo více z nich má různé stavy dodržování předpisů, přiřadí se mu jediný výsledný stav dodržování předpisů. Toto přiřazení vychází z koncepční úrovně závažnosti přiřazené jednotlivých stavům dodržování předpisů. Jednotlivé stavy dodržování předpisů mají následující úroveň závažnosti:

|Stav  |Závažnost  |
|---------|---------|
|Neznámé     |1|
|Neužívá se     |2|
|Vyhovuje|3|
|V období odkladu|4|
|Nevyhovující předpisům|5|
|Chyba|6|

Pokud má zařízení více zásad dodržování předpisů, přiřadí se mu nejvyšší úroveň závažnosti ze všech zásad.

For example, a device has three compliance policies assigned to it: one Unknown status (severity = 1), one Compliant status (severity = 3), and one InGracePeriod status (severity = 4). The InGracePeriod status has the highest severity level. So, all three policies have the InGracePeriod compliance status.

## <a name="next-steps"></a>Další kroky

[Monitor your policies](compliance-policy-monitor.md).
