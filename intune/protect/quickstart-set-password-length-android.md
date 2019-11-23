---
title: Quickstart - Password compliance policy for Android devices
titleSuffix: Microsoft Intune
description: In this quickstart, you will use Microsoft Intune to set the length of the password required for Android devices.
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
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 61fdf91d57ce5d187a0c43153f317b0b42c6b46c
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74409784"
---
# <a name="quickstart-create-a-password-compliance-policy-for-android-devices"></a>Rychlý start: Vytvoření zásady dodržování předpisů pro hesla pro zařízení s Androidem

In this quickstart, you'll use Microsoft Intune to require your workforce's Android users to enter a password of a specific length before access is granted to information on their Android devices.

Zásada dodržování předpisů Intune pro zařízení určuje pravidla a nastavení, která zařízení musí splňovat, aby bylo považováno za dodržující předpisy. You can use compliance policies with Conditional Access to allow or block access to company resources. Můžete také získat sestavy zařízení a provádět akce v případě nedodržování předpisů.

> [!IMPORTANT]
> Kromě nastavení hesla byste také měli zvážit další nastavení zabezpečení systému pro ochranu pracovníků. Další informace najdete v tématu [Systémové nastavení zabezpečení](compliance-policy-create-android-for-work.md).

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](../fundamentals/free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) as a [Global administrator](../fundamentals/users-add.md#types-of-administrators) or an Intune [Service administrator](../fundamentals/users-add.md#types-of-administrators).

## <a name="create-a-device-compliance-policy"></a>Vytváření zásad dodržování předpisů pro zařízení

Create a device compliance policy to require your workforce's Android users to enter a password of a specific length before access is granted to information on their Android devices.

1. In Intune, select **Devices** > **Compliance Policies** > **Create Policy**.

2. Jako **Název** přidejte **Dodržování předpisů v Androidu**. Přidejte také **Popis**.

3. For **Platform**, select **Android Enterprise**.

4. For **Profile type**, select **Work profile**.

5. Vyberte **Nastavení** > **Zabezpečení systému** a zobrazte okno **Zabezpečení systému** Androidu.

6. U možnosti **Vyžadovat heslo k odemknutí mobilních zařízení** vyberte **Vyžadovat**.

7. For **Required password type**, select **At least numeric**.

8. For **Minimum password length**, enter **6**.

    ![Snímek obrazovky s vytvořením skupiny v Microsoft Intune](./media/quickstart-set-password-length-android/quickstart-set-password-length-android-01.png)

9. When done, select **OK** > **OK** > **Create** to create the policy.

When you've successfully created the policy, it appears in your list of device complice policies.

## <a name="clean-up-resources"></a>Vyčištění prostředků

Až tuto zásadu nebudete potřebovat, odstraňte ji. Uděláte to tak, že tuto zásadu dodržování předpisů vyberete a kliknete na **Odstranit**.

## <a name="next-steps"></a>Další kroky

V tomto rychlém startu jste v Intune vytvořili zásadu dodržování předpisů pro firemní zařízení s Androidem, která vyžaduje zadání hesla o minimální délce šesti znaků. Další informace o vytváření zásad dodržování předpisů najdete v článku [Začínáme se zásadami dodržování předpisů zařízeními v Intune](device-compliance-get-started.md).

Pokud chcete postupovat podle této série rychlých startů Intune, pokračujte k dalšímu rychlému startu.

> [!div class="nextstepaction"]
> [Rychlý start: Odeslání oznámení zařízením nedodržujícím předpisy](../quickstart-send-notification.md)
