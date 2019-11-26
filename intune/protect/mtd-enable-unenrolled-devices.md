---
title: Enable the Mobile Threat Defense connector for unenrolled devices
titleSuffix: Microsoft Intune
description: Enable the Mobile Threat Defense connector in Microsoft Intune for unenrolled devices.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 84f82cf2fde7d400e5531bac219b6cbb4877032f
ms.sourcegitcommit: 960ffb2214c35d75ad219fa2571a999529a0abd4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2019
ms.locfileid: "74478925"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune-for-unenrolled-devices"></a>Enable the Mobile Threat Defense connector in Intune for unenrolled devices

During Mobile Threat Defense (MTD) setup, you've configured a policy for classifying threats in your Mobile Threat Defense partner console and you've created the app protection policy in Intune. If you've already configured the Intune connector in the MTD partner console, you can now enable the MTD connection for MTD partner applications.

> [!NOTE]
> This article applies to all Mobile Threat Defense partners that support app protection policies: Better Mobile (Android), Zimperium (iOS), Lookout for Work (Android/iOS).

## <a name="classic-conditional-access-policies-for-mtd-apps"></a>Classic conditional access policies for MTD apps

When you integrate a new application to Intune Mobile Threat Defense and enable the connection to Intune, Intune creates a classic conditional access policy in Azure Active Directory. Each MTD app you integrate, including [Defender ATP](advanced-threat-protection.md) or any of our additional [MTD partners](mobile-threat-defense.md#mobile-threat-defense-partners), creates a new classic conditional access policy. These policies can be ignored, but shouldn't be edited, deleted, or disabled.

If the classic policy is deleted, you'll need to delete the connection to Intune that was responsible for its creation, and then set it up again. This process recreates the classic policy. It's not supported to migrate classic policies for MTD apps to the new policy type for conditional access.

Classic conditional access policies for MTD apps:

- Are used by Intune MTD to require that devices are registered in Azure AD so that they have a device ID before communicating to MTD partners. The ID is required so that devices and can successfully report their status to Intune.

- Have no effect on any other Cloud apps or Resources.

- Are distinct from conditional access policies you might create to help manage MTD.

- By default, don’t interact with other conditional access policies you use for evaluation.

To view classic conditional access policies, in [Azure](https://portal.azure.com/#home), go to **Azure Active Directory** > **Conditional Access** > **Classic policies**.

## <a name="to-enable-the-mtd-connector"></a>Povolení konektoru MTD

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Tenant administration** > **Connectors and tokens** > **Mobile Threat Defense**.

3. V podokně **Mobile Threat Defense** zvolte **Přidat**.

4. V rozevíracím seznamu **Vyberte konektor Mobile Threat Defense, který chcete nastavit** vyberte své řešení MTD.

    <!-- ![MTD setup in Intune](PLACEHOLDER, need a new screenshot of this page) -->

5. Povolte možnosti přepínání podle požadavků vaší organizace. Viditelnost možností přepínání se bude lišit v závislosti na partnerovi MTD.

## <a name="mobile-threat-defense-toggle-options"></a>Mobile Threat Defense toggle options

Podle požadavků organizace se můžete rozhodnout, jaké možnosti přepínání konektoru MTD potřebujete povolit. Tady jsou další podrobnosti:

**App Protection Policy Settings**

- **Connect Android devices of version 4.4 and above to *\<MTD partner name>* for app protection policy evaluation**: When you enable this option, app protection policies using the Device Threat Level rule will evaluate devices including data from this connector.

- **Connect iOS devices version 11 and above to *\<MTD partner name>* for app protection policy evaluation**: When you enable this option, app protection policies using the Device Threat Level rule will evaluate devices including data from this connector.

**Common Shared Settings**

- **Počet dnů, než partner přestane reagovat**: Počet dnů nečinnosti, než bude Intune kvůli ztrátě připojení považovat partnera za nereagujícího. U nereagujících partnerů MTD Intune ignoruje stav dodržování předpisů.

> [!TIP]
> Z podokna Mobile Threat Defense se můžete podívat na **Stav připojení** a čas **poslední synchronizace** mezi Intune a partnerem MTD.

## <a name="next-steps"></a>Další kroky

- [Create Mobile Threat Defense (MTD) app protection policy with Intune](~/protect/mtd-app-protection-policy.md).
