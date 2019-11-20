---
title: Use Microsoft Defender ATP in Microsoft Intune - Azure | Microsoft Docs
description: Use Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) with Intune, including setup and configuration, onboarding of your Intune devices with ATP, and then use a devices ATP risk assessment with your Intune device compliance and conditional access policies to protect network resources.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 889b0a7562f1a663556e955271681e0747aeb3c4
ms.sourcegitcommit: 01fb3d844958a0e66c7b87623160982868e675b0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199169"
---
# <a name="enforce-compliance-for-microsoft-defender-atp-with-conditional-access-in-intune"></a>Enforce compliance for Microsoft Defender ATP with Conditional Access in Intune

You can integrate Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) with Microsoft Intune as a Mobile Threat Defense solution. Integration can help you prevent security breaches and limit the impact of breaches within an organization. Microsoft Defender ATP works with devices that run Windows 10 or later.

To be successful, you use the following configurations in concert:

- **Establish a service-to-service connection between Intune and Microsoft Defender ATP**. This connection lets Microsoft Defender ATP collect data about machine risk from Windows 10 devices you manage with Intune.
- **Use a device configuration profile to onboard devices with Microsoft Defender ATP**. You onboard devices to configure them to communicate with Microsoft Defender ATP and to provide data that helps assess their risk level.
- **Use a device compliance policy to set the level of risk you want to allow**. Risk levels are reported by Microsoft Defender ATP. Devices that exceed the allowed risk level are identified as non-compliant.
- **Use a conditional access policy** to block users from accessing corporate resources from devices that are non-compliant.

When you integrate Intune with Microsoft Defender ATP, you can take advantage of ATPs Threat & Vulnerability Management (TVM) and [use Intune to remediate endpoint weakness identified by TVM](atp-manage-vulnerabilities.md).

## <a name="example-of-using-microsoft-defender-atp-with-intune"></a>Example of using Microsoft Defender ATP with Intune

The following example helps explain how these solutions work together to help protect your organization. For this example, Microsoft Defender ATP and Intune are already integrated.

Consider an event where someone sends a Word attachment with embedded malicious code to a user within your organization.

- Uživatel přílohu otevře a povolí obsah.
- Spustí se útok se zvýšenými oprávněními. Útočník ho provádí ze vzdáleného počítače na napadeném zařízení, ke kterému získal oprávnění správce.
- Z tohoto zařízení získá vzdálený přístup i k dalším zařízením uživatele. Toto porušení zabezpečení může mít dopad na celou organizaci.

Microsoft Defender ATP can help resolve security events like this scenario.

- In our example, Microsoft Defender ATP detects that the device executed abnormal code, experienced a process privilege escalation, injected malicious code, and issued a suspicious remote shell.
- Based on these actions from the device, Microsoft Defender ATP [classifies the device as high-risk](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue#severity) and includes a detailed report of suspicious activity in the Microsoft Defender Security Center portal.

Because you have an Intune device compliance policy to classify devices with a *Medium* or *High* level of risk as non-compliant, the compromised device is classified as non-compliant. This classification allows your conditional access policy to kick in and block access from that device to your corporate resources.

## <a name="prerequisites"></a>Požadované součásti

To use Microsoft Defender ATP with Intune, be sure you have the following configured, and ready for use:

- Tenant s licencí pro Enterprise Mobility + Security E3 a Windows E5 (nebo Microsoft 365 Enterprise E5)
- Prostředí Microsoft Intune se zařízeními s Windows 10 [spravovanými v Intune](../enrollment/windows-enroll.md), která jsou zároveň připojená k Azure AD
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and access to the Microsoft Defender Security Center (ATP portal)

> [!NOTE]
> Microsoft Defender ATP is not supported with iOS and Android Intune app protection policies.

## <a name="enable-microsoft-defender-atp-in-intune"></a>Enable Microsoft Defender ATP in Intune

The first step you take is to set up the service-to-service connection between Intune and Microsoft Defender ATP. This requires administrative access to both the Microsoft Defender Security Center, and to Intune.

### <a name="to-enable-defender-atp"></a>To enable Defender ATP

You only need to enable Defender ATP a single time per tenant.

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Endpoint security** > **Microsoft Defender ATP**, and then select **Open the Microsoft Defender Security Center**.

   ![Select to open the Microsoft Defender Security Center](./media/advanced-threat-protection/atp-device-compliance-open-microsoft-defender.png)

4. In **Microsoft Defender Security Center**:
    1. Zvolte **Nastavení** > **Pokročilé funkce**.
    2. Přepínač pro **připojení Microsoft Intune** přepněte do polohy **Zapnuto**:

        ![Povolení připojení k Intune](./media/advanced-threat-protection/atp-security-center-intune-toggle.png)

    3. Vyberte **Uložit předvolby**.

4. Return to **Microsoft Defender ATP** in the Microsoft Endpoint Manager Admin Center. Under **MDM Compliance Policy Settings**, set **Connect Windows devices version 10.0.15063 and above to Microsoft Defender ATP** to **On**.

5. Vyberte **Uložit**.

> [!TIP]
> When you integrate a new application to Intune Mobile Threat Defense and enable the connection to Intune, Intune creates a classic conditional access policy in Azure Active Directory. Each MTD app you integrate, including [Defender ATP](advanced-threat-protection.md) or any of our additional [MTD partners](mobile-threat-defense.md#mobile-threat-defense-partners), creates a new classic conditional access policy. These policies can be ignored, but should not be edited, deleted, or disabled.
>
> If the classic policy is deleted, you will need to delete the connection to Intune that was responsible for its creation, and then set it up again. This recreates the classic policy. Its not supported to migrate classic policies for MTD apps to the new policy type for conditional access.
>
> Classic conditional access policies for MTD apps:
>
> - Are used by Intune MTD to require that devices are registered in Azure AD so that they have a device ID before communicating to MTD partners. The ID is required so that devices and can successfully report their status to Intune.
> - Have no effect on any other Cloud apps or Resources.
> - Are distinct from conditional access policies you might create to help manage MTD.
> - By default, don’t interact with other conditional access policies you use for evaluation.
>
> To view classic conditional access policies, in [Azure](https://portal.azure.com/#home), go to **Azure Active Directory** > **Conditional Access** > **Classic policies**.

## <a name="onboard-devices-by-using-a-configuration-profile"></a>Onboard devices by using a configuration profile

After you establish the service-to-service connection between Intune and Microsoft Defender ATP, you onboard your Intune managed devices to ATP so that data about their risk level can be collected and used. To onboard devices, you use a device configuration profile for Microsoft Defender ATP.

When you established the connection to Microsoft Defender ATP, Intune received a Microsoft Defender ATP onboarding configuration package from Microsoft Defender ATP. This package is deployed to devices with the device configuration profile. The configuration package configures devices to communicate with [Microsoft Defender ATP services](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan files, detect threats, and report the risk to Microsoft Defender ATP.

After you onboard a device using configuration package, you don't need to do it again. Zařízení můžete připojit také pomocí [skupiny zásad nebo System Center Configuration Manageru (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="create-the-device-configuration-profile"></a>Create the device configuration profile

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Select **Devices** > **Configuration profiles** > **Create profile**.
3. Zadejte **Název** a **Popis**.
4. V části **Platforma** vyberte **Windows 10 a novější**.
5. For **Profile type**, select **Microsoft Defender ATP (Windows 10 Desktop)** .
6. Nakonfigurujte nastavení:

   - **Microsoft Defender ATP client configuration package type**: Select **Onboard** to add the configuration package to the profile. Výběrem možnosti **Zrušit zprovoznění** konfigurační balíček odeberete.
  
     > [!NOTE]
     > If you've properly established a connection with Microsoft Defender ATP, Intune will automatically **Onboard** the configuration profile for you, and the **Microsoft Defender ATP client configuration package type** setting will not be available.
  
   - **Sample sharing for all files**: **Enable** allows samples to be collected, and shared with Microsoft Defender ATP. For example, if you see a suspicious file, you can submit it to Microsoft Defender ATP for deep analysis. **Not configured** doesn't share any samples to Microsoft Defender ATP.
   - **Expedite telemetry reporting frequency**: For devices that are at high risk, **Enable** this setting so it reports telemetry to the Microsoft Defender ATP service more frequently.

     [Onboard Windows 10 machines using System Center Configuration Manager](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-sccm) has more details on these Microsoft Defender ATP settings.

7. Zvolte **OK** a pak **Vytvořit**. Tím uložíte změny a vytvoříte profil.
8. [Assign the device configuration profile](../configuration/device-profile-assign.md) to devices you want to assess with Microsoft Defender ATP.

## <a name="create-and-assign-the-compliance-policy"></a>Create and assign the compliance policy

The compliance policy determines the level of risk that you consider as acceptable for a device.

### <a name="create-the-compliance-policy"></a>Vytvoření zásady dodržování předpisů

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Select **Devices** > **Compliance policies** > **Create policy**.
3. Zadejte **Název** a **Popis**.
4. V části **Platforma** vyberte **Windows 10 a novější**.
5. Under **Settings**, select **Microsoft Defender ATP**.
6. Set **Require the device to be at or under the machine risk score** to your preferred level.

   Threat level classifications are [determined by Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue).

   - **Vymazat:** Tato úroveň poskytuje nejvyšší zabezpečení. The device can't have any existing threats and still access company resources. Pokud se najde jakákoli hrozba, zařízení se vyhodnotí jako nevyhovující. (Microsoft Defender ATP users the value *Secure*.)
   - **Nízká:** Zařízení se vyhodnotí jako vyhovující, pokud se v něm nacházejí jenom hrozby nízké úrovně. Devices with medium or high threat levels aren't compliant.
   - **Střední:** Zařízení vyhovuje, pokud se v něm vyskytují hrozby na střední nebo nízké úrovni. Pokud se v zařízení zjistí hrozby vysoké úrovně, vyhodnotí se jako nevyhovující.
   - **High**: This level is the least secure and allows all threat levels. So devices that with high, medium, or low threat levels are considered compliant.

7. Zvolte **OK** a pak **Vytvořit**. Tím uložíte změny a vytvoříte zásadu.
8. [Assign the device compliance policy](create-compliance-policy.md#assign-the-policy) to applicable groups.

## <a name="create-a-conditional-access-policy"></a>Create a Conditional Access policy

The Conditional Access policy blocks access to resources for devices that exceed the threat level you set in your compliance policy. You can block access from the device to corporate resources, such as SharePoint or Exchange Online.

> [!TIP]
> Podmíněný přístup je technologie Azure Active Directory (Azure AD). The Conditional Access node accessed from the Microsoft Endpoint Manager Admin Center is the same node as accessed from *Azure AD*.

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Endpoint security** > **Conditional Access** > **New policy**.

3. Zadejte **Název** zásady a zvolte **Uživatelé a skupiny**. Pomocí možností Zahrnout a Vyloučit vyberte požadované skupiny pro nasazení zásady a zvolte **Hotovo**.

4. Zvolte **Cloudové aplikace** a vyberte aplikace, které chcete chránit. Zvolte například **Vybrat aplikace** a pak vyberte **Office 365 SharePoint Online** a **Office 365 Exchange Online**.

   Zvolením možnosti **Hotovo** uložte změny.

5. Když zvolíte **Podmínky** > **Klientské aplikace**, zásady se použijí pro aplikace a prohlížeče. Zvolte například **Ano** a pak povolte **Prohlížeč** a **Mobilní aplikace a desktopoví klienti**.

   Zvolením možnosti **Hotovo** uložte změny.

6. Select **Grant** to apply Conditional Access based on device compliance. Zvolte například **Udělit přístup** > **Vyžadovat, aby zařízení bylo označené jako vyhovující**.

    Zvolením možnosti **Vybrat** uložte změny.

7. Zvolte **Povolit zásadu** a potom **Vytvořit**. Tím uložíte provedené změny.

## <a name="monitor-device-compliance"></a>Monitorování dodržování předpisů zařízením

Next, monitor the state of devices that have the Microsoft Defender ATP compliance policy.

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Devices** > **Monitor** > **Policy compliance**.

3. Find your Microsoft Defender ATP policy in the list, and see which devices are compliant or noncompliant.

## <a name="view-onboarding-status"></a>View onboarding status

To view the onboarding status of all Intune-managed Windows 10 devices, you can go to **Device compliance** > **Microsoft Defender ATP**. From this page, you can also initiate the creation of a device configuration profile for onboarding more devices to Microsoft Defender ATP.

## <a name="next-steps"></a>Další kroky

[Microsoft Defender ATP Conditional Access](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/conditional-access)

[Microsoft Defender ATP risk dashboard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)

[Use security tasks with ATPs Vulnerability Management to remediate issues on devices](atp-manage-vulnerabilities.md).

[Začínáme se zásadami dodržování předpisů zařízeními](device-compliance-get-started.md)
