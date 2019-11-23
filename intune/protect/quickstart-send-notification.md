---
title: Rychlý start – odeslání oznámení zařízením nedodržujícím předpisy
titleSuffix: Microsoft Intune
description: In this quickstart, you use Microsoft Intune to send email notifications to noncompliant devices.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/21/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1b89f2d-7937-46bb-926b-b05f6fa9c749
ms.reviewer: jinyoon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6d89cfcafd5452b990509e0fa6fd431a614ee5c1
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74410267"
---
# <a name="quickstart-send-notifications-to-noncompliant-devices"></a>Rychlý start: Odeslání oznámení zařízením nedodržujícím předpisy

In this quickstart, you'll use Microsoft Intune to send an email notification to the members of your workforce that have noncompliant devices.

Když Intune ve výchozím nastavení detekuje zařízení, které nedodržuje předpisy, okamžitě ho označí jako nedodržující předpisy. Azure Active Directory (Azure AD) [Conditional Access](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) then blocks the device. When a device isn't compliant, Intune allows you to add actions for noncompliance, which gives you flexibility to decide what to do. Uživatelům můžete dát například určitou dobu odkladu, během které musí zajistit dodržování předpisů, než tato zařízení zablokujete.

One action to take when a device doesn't meet compliance is to send email to the devices user. You can also customize an email notification before sending it. Konkrétně můžete přizpůsobit příjemce, předmět a text zprávy včetně firemního loga a kontaktních údajů. Intune also includes details about the noncompliant device in the email notification.

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Požadované součásti

When using device compliance policies to block devices from corporate resources, Azure AD Conditional Access must be set up. If you've completed the [Create a device compliance policy](quickstart-set-password-length-android.md) quickstart, you're using Azure Active Directory. For more information about Azure AD, see [Conditional Access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) and [common ways to use Conditional Access with Intune](../protect/conditional-access-intune-common-ways-use.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) as a [Global administrator](../fundamentals/users-add.md#types-of-administrators) or an Intune [Service administrator](../fundamentals/users-add.md#types-of-administrators). If you've created an Intune Trial subscription, the account you created the subscription with is the Global administrator.

## <a name="create-a-notification-message-template"></a>Vytvoření šablony zprávy s oznámením

Pokud chcete svým uživatelům odeslat e-mail, vytvořte šablonu zprávy s oznámením. Pokud zařízení nedodržuje předpisy, musíte do šablony zadat podrobnosti, které se zobrazují v e-mailu odeslaném vašim uživatelům.

1. In Intune, select **Devices** > **Compliance policies** > **Notifications** > **Create notification**.
2. Zadejte následující informace:

   - **Jméno:** *Správce Contoso*
   - **Předmět:** *Dodržování předpisů zařízením*
   - **Message**: *Your device is currently not meeting our organization's compliance requirements.*
   - **Záhlaví e-mailu – Připojte logo společnosti:** Pokud chcete zobrazit logo organizace, nastavte na **Povoleno**.
   - **Zápatí e-mailu – Uveďte název společnosti:** Pokud chcete zobrazit název organizace, nastavte na **Povoleno**.
   - **Zápatí e-mailu – Uveďte kontaktní údaje:** Pokud chcete zobrazit kontaktní údaje organizace, nastavte na **Povoleno**.

   ![Příklad oznámení o dodržování předpisů v Intune](./media/quickstart-send-notification/quickstart-send-notification-01.png)

3. Select **Next** and review your notification. Select **Create** and the notification message template is ready to use.

   > [!NOTE]
   > Můžete také upravit některou dříve vytvořenou šablonu oznámení.

For details about setting your company name, company contact information, and company logo, see the following articles:

- [Company information and privacy statement](../apps/company-portal-app.md#company-information-and-privacy-statement)
- [Support information](../apps/company-portal-app.md#support-information)
- [Company identity branding customization](../apps/company-portal-app.md#company-identity-branding-customization).

## <a name="add-a-noncompliance-policy"></a>Přidání zásady při nedodržování předpisů

Když vytvoříte zásady dodržování předpisů pro zařízení, Intune automaticky vytvoří akci pro případ nedodržování těchto předpisů. Intune then marks devices as noncompliant when they fail to meet your compliance policy. Můžete přizpůsobit, jak dlouho bude zařízení takto označené. Při vytváření zásady dodržování předpisů nebo aktualizaci existující zásady dodržování předpisů můžete také přidat další akci.

Následující postup vytvoří zásadu dodržování předpisů pro zařízení s Windows 10.

1. In Intune, select **Devices** > **Compliance Policies** > **Create Policy**.

2. Zadejte následující informace:

   - **Název:** *Dodržování předpisů pro Windows 10*
   - **Popis:** *Zásada dodržování předpisů pro Windows 10*
   - **Platforma:** Windows 10 a novější

3. Výběrem možnosti **Nastavení** > **Zabezpečení systému** zobrazte nastavení související se zabezpečením zařízení.

4. Configure the following options:

   - Možnost **Vyžadovat heslo k odemknutí mobilních zařízení** nastavte na **Vyžadovat**. Toto nastavení určuje, jestli se má po uživatelích vyžadovat zadání hesla, než bude udělen přístup k informacím uloženým v jejich mobilních zařízeních.

   - Volbu **Minimální délka hesla** nastavte na **6**. Toto nastavení určuje minimální počet číslic nebo znaků v hesle.

   ![Nastavení Zabezpečení systému pro novou zásadu dodržování předpisů](./media/quickstart-send-notification/system-security-settings-01.png)

5. Select **OK** > **OK** > **Create** to create your compliance policy.

6. Vyberte **Vlastnosti** > **Akce při nedodržení předpisů** > **Přidat**.

7. V rozevíracím seznamu **Akce** potvrďte, že je vybraná možnost **Odeslat e-mail koncovému uživateli**.

8. Select **Message template**,  the template you created earlier in this article, and then **Select** to select the message template.

9. Select **ADD** > **OK** > **Save** to save your changes.

## <a name="assign-the-policy"></a>Přiřazení zásady

Zásadu dodržování předpisů můžete přiřadit určité skupině uživatelů nebo všem uživatelům. When Intune recognizes that a device is noncompliant, the user is notified that they must update their device to meet the compliance policy. Use the following steps to assign the policy.

1. In Intune go to **Devices** > **Compliance Policies** and select the **Windows 10 compliance** policy that you created earlier.

2. Zvolte **Přiřazení**.

3. V rozevíracím seznamu **Přiřadit k** vyberte **Všichni uživatelé**. Tím vyberete všechny uživatele. Každý uživatel se zařízením s **Windows 10 a novější verzí**, které nesplňuje tuto zásadu dodržování předpisů, dostane oznámení.

    > [!NOTE]
    > Při přiřazování zásad dodržování předpisů můžete zahrnout a vyloučit skupiny.

4. Klikněte na **Uložit**.

When you've successfully created and saved the policy, it will appear in the list of **Compliance policies - Policies**. V tomto seznamu si můžete všimnout, že **Přiřazeno** je nastavené na **Ano**.

## <a name="next-steps"></a>Další kroky

V tomto rychlém startu jste Intune použili k vytvoření a přiřazení zásady dodržování předpisů pro firemní zařízení s Windows 10, která vyžaduje zadání hesla o minimální délce šesti znaků. Další informace o vytváření zásad dodržování předpisů pro zařízení s Windows najdete v článku [Přidání zásad dodržování předpisů pro zařízení s Windows v Intune](compliance-policy-create-windows.md).

Pokud chcete postupovat podle této série rychlých startů Intune, pokračujte k dalšímu rychlému startu.

> [!div class="nextstepaction"]
> [Rychlý start: Přidání a přiřazení klientské aplikace](../apps/quickstart-add-assign-app.md)
