---
title: Řešení potíží s profily zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Common questions and answers with device policies and profiles, including profile changes not applied to users or devices, how long it takes for new policies to be pushed to devices, which settings are applied when there are multiple policies, what happens when a profile is deleted or removed, and more with Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/15/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4a1177a37ddbfa7f760339c4ad0cd7773d670540
ms.sourcegitcommit: 01fb3d844958a0e66c7b87623160982868e675b0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199193"
---
# <a name="common-questions-issues-and-resolutions-with-device-policies-and-profiles-in-microsoft-intune"></a>Common questions, issues, and resolutions with device policies and profiles in Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Get answers to common questions when working with device profiles and policies in Intune. This article also lists the check-in time intervals, provides more detains on conflicts, and more.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Proč uživatel nezíská nový profil, když změníte heslo u existujícího profilu Wi-Fi?

Vytvoříte profil podnikové sítě Wi-Fi, nasadíte profil u skupiny, změníte heslo a profil uložíte. Když se profil změní, nemusí někteří uživatelé nový profil obdržet.

Abyste zmírnili následky tohoto problému, nastavte Wi-Fi pro hosty. Když selže podniková síť Wi-Fi, můžou se uživatelé připojit k Wi-Fi pro hosty. Je nutné povolit veškerá nastavení automatického připojení. Nasaďte profil sítě Wi-Fi pro hosty všem uživatelům.

Další doporučení:  

- If the Wi-Fi network you're connecting to uses a password or passphrase, make sure you can connect to the Wi-Fi router directly. Můžete to vyzkoušet na zařízení s iOSem.
- Až se úspěšně připojíte ke koncovému bodu sítě Wi-Fi (směrovači sítě Wi-Fi), zapište si identifikátor SSID a použité přihlašovací údaje (heslo).
- Zadejte identifikátor SSID a přihlašovací údaje (heslo) do pole Předsdílený klíč. 
- Nasaďte profil u testovací skupiny, která má omezený počet uživatelů, nejlépe jenom u IT týmu. 
- Synchronizujte vaše zařízení s iOSem do Intune. Zaregistrujte se (pokud jste to ještě neudělali). 
- Vyzkoušejte připojení ke stejnému koncovému bodu sítě Wi-Fi (jak je uvedeno v prvním kroku).
- Zaveďte profil u větších skupin a nakonec u všech předpokládaných uživatelů ve vaší organizaci. 

## <a name="how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned"></a>How long does it take for devices to get a policy, profile, or app after they are assigned?

Intune notifies the device to check in with the Intune service. The notification times vary, including immediately up to a few hours. These notification times also vary between platforms.

If a device doesn't check in to get the policy or profile after the first notification, Intune makes three more attempts. An offline device, such as turned off, or not connected to a network, may not receive the notifications. In this case, the device gets the policy or profile on its next scheduled check-in with the Intune service, which is **estimated** at:

| Platforma | Refresh cycle|
| --- | --- |
| iOS | About every 8 hours |
| macOS | About every 8 hours |
| Android | About every 8 hours |
| Počítače s Windows 10 zaregistrované jako zařízení | About every 8 hours |
| Windows Phone | About every 8 hours |
| Windows 8.1 | About every 8 hours |

If the device recently enrolled, the compliance and configuration check-in runs more frequently, which is **estimated** at:

| Platforma | Četnost |
| --- | --- |
| iOS | Every 15 minutes for 1 hour, and then around every 8 hours |  
| macOS | Every 15 minutes for 1 hour, and then around every 8 hours | 
| Android | Every 3 minutes for 15 minutes, then every 15 minutes for 2 hours, and then around every 8 hours | 
| Počítače s Windows 10 zaregistrované jako zařízení | Every 3 minutes for 15 minutes, then every 15 minutes for 2 hours, and then around every 8 hours | 
| Windows Phone | Every 5 minutes for 15 minutes, then every 15 minutes for 2 hours, and then around every 8 hours | 
| Windows 8.1 | Every 5 minutes for 15 minutes, then every 15 minutes for 2 hours, and then around every 8 hours | 

At any time, users can open the Company Portal app, **Settings** > **Sync** to immediately check for policy or profile updates.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Které akce způsobí, že Intune hned pošle oznámení do zařízení?

There are different actions that trigger a notification, such as when a policy, profile, or app is assigned (or unassigned), updated, deleted, and so on. These action times vary between platforms.

Devices check in with Intune when they receive a notification to check in, or during the scheduled check-in. When you target a device or user with an action, such as lock, passcode reset, app, profile or policy assignment, then Intune immediately notifies the device to check in to receive these updates.

Other changes, such as revising the contact information in the Company Portal app, don't cause an immediate notification to devices.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Pokud se stejnému zařízení nebo uživateli přiřadí několik zásad, jak poznám, které nastavení se použije?

When two or more policies are assigned to the same user or device, then the setting that applies happens at the individual setting level:

- Compliance policy settings always have precedence over configuration profile settings.

- If a compliance policy evaluates against the same setting in another compliance policy, then the most restrictive compliance policy setting applies.

- If a configuration policy setting conflicts with a setting in another configuration policy, this conflict is shown in Intune. Konflikty vyřešte ručně.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>Co se stane, když zásady ochrany aplikací navzájem kolidují? Která se použije pro příslušnou aplikaci?

Conflict values are the most restrictive settings available in an app protection policy *except* for the number entry fields, such as PIN attempts before reset. The number entry fields are set the same as the values, as if you created a MAM policy using the recommended settings option.

Conflicts happen when two profile settings are the same. Představte si třeba, že jste nakonfigurovali dvě zásady MAM, které jsou stejné až na nastavení kopírování/vkládání. V tomto scénáři se nastavení kopírování/vkládání nastaví na nejvíce omezující hodnotu, ale ostatní nastavení se použijí tak, jak se nakonfigurovala.

A policy is deployed to the app and takes effect. A second policy is deployed. In this scenario, the first policy takes precedence, and stays applied. The second policy shows a conflict. If both are applied at the same time, meaning that there isn't preceding policy, then both are in conflict. Všechna konfliktní nastavení se nastaví na nejvíce omezující hodnoty.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>Co se stane při konfliktu vlastních zásad iOS?

Intune nevyhodnocuje datovou část konfiguračních souborů Apple nebo vlastní zásady OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Slouží jenom jako mechanismus doručování.

When you assign a custom policy, confirm that the configured settings don't conflict with compliance, configuration, or other custom policies. If a custom policy and its settings conflict, then the settings are applied randomly.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Co se stane, když se profil odstraní nebo už není použitelný?

When you delete a profile, or you remove a device from a group that has the profile, then the profile and settings are removed from the device as described:

- Profily sítě Wi-Fi, VPN, certifikátu a e-mailu: Tyto profily se odeberou ze všech podporovaných registrovaných zařízení.
- Všechny ostatní typy profilů:  

  - **Windows and Android devices**: Settings aren't removed from the device
  - **Zařízení Windows Phone 8.1**: Odeberou se tato nastavení:  
  
    - Vyžadovat heslo k odemknutí mobilních zařízení
    - Povolit jednoduchá hesla
    - Minimální délka hesla
    - Vyžadovaný typ hesla
    - Vypršení platnosti hesla (dny)
    - Pamatovat si historii hesel
    - Počet povolených opakovaných neúspěšných přihlášení, než bude zařízení vymazáno
    - Počet minut nečinnosti před vyžadováním hesla
    - Typ požadovaného hesla – minimální počet znaků
    - Povolit fotoaparát
    - Vyžadovat šifrování u mobilního zařízení
    - Povolit vyměnitelné úložiště
    - Povolit webový prohlížeč
    - Povolit obchod s aplikacemi
    - Povolit snímek obrazovky
    - Povolit zeměpisnou polohu
    - Povolit účet Microsoft
    - Povolit kopírování a vkládání
    - Povolit sdílení internetového připojení přes Wi-Fi
    - Povolit automatické připojení k bezplatným Wi-Fi hotspotům
    - Povolit oznamování Wi-Fi hotspotů
    - Povolit vymazání
    - Povolit Bluetooth
    - Povolit komunikaci NFC
    - Povolit Wi-Fi

  - **iOS**: Odeberou se všechna nastavení s těmito výjimkami:
  
    - Povolit hlasový roaming
    - Povolit datový roaming
    - Povolit automatickou synchronizaci při roamingu

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Změnil(a) jsem profil omezení zařízení, ale tyto změny se neprojevily

Once set, Windows Phone devices don't allow security policies set using MDM or EAS to be reduced in security. For example, you set a **Minimum number of character password** to 8. You try to reduce it to 4. The more restrictive profile is already applied to the device.

To change the profile to a less secure value, then reset security policies. For example, in Windows 8.1, on the desktop, swipe in from right > select **Settings** > **Control Panel**. Vyberte aplet **Uživatelské účty** . In the left-hand navigation menu, there's a **Reset Security Policies** link (toward the bottom). Vyberte ho a potom zvolte **Resetovat zásady**.

Other MDM devices, such as Android, Windows Phone 8.1 and later, iOS, and Windows 10 may need to be retired, and re-enrolled in to Intune to apply a less restrictive profile.

## <a name="some-settings-in-a-windows-10-profile-return-not-applicable"></a>Some settings in a Windows 10 profile return "Not Applicable"

Some settings on Windows 10 devices may show as "Not Applicable". When this happens, that specific setting isn't supported on the version or edition of Windows running on the device. This message can occur for the following reasons:

- The setting is only available for newer versions of Windows, and not the current operating system (OS) version on the device.
- The setting is only available for specific Windows editions or specific SKUs, such as Home, Professional, Enterprise, and Education.

To learn more about the version and SKU requirements for the different settings, see the [Configuration Service Provider (CSP) reference](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).

## <a name="next-steps"></a>Další kroky

Potřebujete další pomoc? Přečtěte si téma [Jak získat podporu pro Microsoft Intune](../fundamentals/get-support.md).
