---
title: Tutorial - Protect Exchange Online email on managed devices
titleSuffix: Microsoft Intune
description: Learn to secure Exchange Online with iOS Intune compliance policies and Azure AD Conditional Access to require managed devices and the Outlook app.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/21/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9deee0dca675d7fd95445131ed98ea195972c6ac
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74409856"
---
# <a name="tutorial-protect-exchange-online-email-on-managed-devices"></a>Kurz: Ochrana e-mailu Exchange Online na spravovaných zařízeních

Learn about using device compliance policies with Conditional Access to make sure that iOS devices can access Exchange Online email only if they're managed by Intune and using an approved email app.

V tomto kurzu se naučíte:

> [!div class="checklist"]
> * Vytvořit zásadu dodržování předpisů zařízením s iOSem v Intune. Tato zásada nastaví podmínky, které zařízení musí splnit, než bude považováno za vyhovující.
> * Create an Azure Active Directory (Azure AD) Conditional Access policy that requires iOS devices to enroll in Intune, comply with Intune policies, and use the approved Outlook mobile app to access Exchange Online email.

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Požadované součásti

Pro účely tohoto kurzu budete potřebovat testovacího tenanta s následujícími předplatnými:

- Azure Active Directory Premium ([bezplatná zkušební verze](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))

- Předplatné Office 365 Business, které zahrnuje Exchange ([bezplatná zkušební verze](https://go.microsoft.com/fwlink/p/?LinkID=510938))

Než začnete, vytvořte si testovací profil pro zařízení s iOSem podle postupu uvedeného v článku [Rychlý start: Vytvoření e-mailového profilu zařízení pro iOS](../configuration/quickstart-email-profile.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) as a [Global administrator](../fundamentals/users-add.md#types-of-administrators) or an Intune [Service administrator](../fundamentals/users-add.md#types-of-administrators). Pokud jste vytvořili zkušební předplatné Intune, účet, z něhož jste toto předplatné vytvořili, je globálním správcem.

## <a name="create-the-ios-device-compliance-policy"></a>Vytvoření zásady dodržování předpisů zařízením s iOSem

Nastavte zásadu dodržování předpisů zařízením s iOSem v Intune a nastavte podmínky, které zařízení musí splnit, než bude považováno za vyhovující. Pro účely tohoto kurzu vytvoříme zásadu dodržování předpisů pro zařízení s iOSem. Zásady dodržování předpisů jsou pro jednotlivé platformy specifické, a proto potřebujete samostatnou zásadu dodržování předpisů pro každou platformu zařízení, kterou chcete vyhodnotit.

1. In Intune, select **Devices** > **Compliance policies** > **Create policy**.

2. For **Name**, enter **iOS compliance policy test**.

3. For **Description**, enter **iOS compliance policy test**.

4. For **Platform**, select **iOS/iPadOS**.

5. Vyberte **Nastavení** > **E-mail**.

   1. Vedle možnosti **Vyžadovat, aby mobilní zařízení měla spravovaný e-mailový profil** vyberte **Vyžadovat**.

   2. Vyberte **OK**.

   ![Nastavení zásad dodržování předpisů e-mailem, které vyžadují spravovaný e-mailový profil](./media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-email.png)

6. Vyberte **Stav zařízení**. Vedle možnosti **Zařízení s jailbreakem** vyberte **Blokovat** a potom vyberte **OK**.

7. Vyberte **Zabezpečení systému** a zadejte nastavení **hesla**. Pro účely tohoto kurzu vyberte následující doporučená nastavení:

   - U možnosti **Vyžadovat heslo k odemknutí mobilních zařízení** vyberte **Vyžadovat**.

   - U možnosti **Jednoduchá hesla** vyberte **Blokovat**.

   - U možnosti **Minimální délka hesla** zadejte **4**.

     > [!TIP]
     > Default values that are grayed out and italicized are only recommendations. You must replace values that are recommendations to configure a setting.

   - Jako **Požadovaný typ hesla** zvolte **Alfanumerické**.

   - U možnosti **Maximální počet minut po uzamčení obrazovky, po kterém bude nutné zadat heslo**, zvolte **Okamžitě**.

   - U možnosti **Konec platnosti hesla (dny)** zadejte **41**.

   - U možnosti **Počet předchozích hesel, která se nesmí použít znovu** zadejte **5**.
 
   ![Nastavení hesla pro zásady dodržování předpisů e-mailem](./media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-system-security.png)

8. Vyberte **OK** a potom znovu vyberte **OK**.

9. Vyberte **Vytvořit**.

## <a name="create-the-conditional-access-policy"></a>Create the Conditional Access policy

Now we’ll create a Conditional Access policy that requires all device platforms to enroll in Intune and comply with our Intune compliance policy before they can access Exchange Online. Pro přístup k e-mailu budeme také vyžadovat aplikaci Outlook. Conditional Access policies are configurable in either the Azure AD portal or the Intune portal. Vzhledem k tomu, že se už nacházíme na portálu Intune, vytvoříme zásadu zde.

1. In Intune, select **Endpoint security** > **Conditional Access** > **New policy**.

2. For **Name**, enter **Test policy for Office 365 email**.

3. V části **Přiřazení** vyberte **Uživatelé a skupiny**. Na kartě **Zahrnout** vyberte **Všichni uživatelé** a vyberte **Hotovo**.

4. Under **Assignments**, select **Cloud apps or actions**. Protože chceme chránit e-mail Office 365 se službou Exchange Online, vybereme ho následujícím postupem:

   1. Na kartě **Zahrnout** zvolte **Vybrat aplikace**.

   2. Zvolte **Vybrat**. 

   3. V seznamu aplikací vyberte **Office 365 se službou Exchange Online** a potom zvolte **Vybrat**. 

   4. Vyberte **Hotovo**.
  
   ![Výběr aplikace Office 365 se službou Exchange Online](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-apps.png)

5. V části **Přiřazení** vyberte **Podmínky** > **Platformy zařízení**.

   1. V části **Konfigurovat** vyberte **Ano**.

   2. On the **Include** tab, select **Any device**, and then select **Done**. 

   3. Znovu vyberte **Hotovo**.

   ![Include any device](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-device-platforms.png)

6. V části **Přiřazení** vyberte **Podmínky** > **Klientské aplikace**.

   1. V části **Konfigurovat** vyberte **Ano**.

   2. Pro účely tohoto kurzu vyberte **Mobilní aplikace a desktopoví klienti** a **Klienti moderního ověřování** (týká se aplikací, jako jsou Outlook pro iOS a Outlook pro Android). Zaškrtnutí všech ostatních políček zrušte.

   3. Vyberte **Hotovo** a potom znovu vyberte **Hotovo**.

   ![Select apps and clients](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-client-apps.png)

7. V části **Ovládací prvky přístupu** zvolte **Udělení**.

   1. V podokně **Udělení** vyberte **Udělit přístup**.

   2. Vyberte **Vyžadovat, aby zařízení bylo označené jako vyhovující**.

   3. Vyberte **Vyžaduje se klientem schválená aplikace**.

   4. V části **Pro více ovládacích prvků** vyberte **Vyžadovat všechny vybrané ovládací prvky**. Toto nastavení zajistí, že se při přístupu zařízení k e-mailu oba vybrané požadavky vynutí.

   5. Zvolte **Vybrat**.

   ![Select conrols](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-grant-access.png)

8. V části **Povolit zásadu** vyberte **Zapnuto**.

   ![Enable policy](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-enable-policy.png)

9. Vyberte **Vytvořit**.

## <a name="try-it-out"></a>Vyzkoušejte si to

S vytvořenými zásadami se budou všechna zařízení s iOSem, která se pokusí o přihlášení k e-mailu Office 365, muset zaregistrovat v Intune a používat mobilní aplikaci Outlook pro iOS. Pokud chcete tento scénář otestovat na zařízení s iOSem, zkuste se přihlásit k Exchangi Online pomocí přihlašovacích údajů uživatele v testovacím tenantovi. Zobrazí se výzva k registraci zařízení a k instalaci mobilní aplikace Outlook.

1. Pokud si chcete zásady otestovat na iPhonu, přejděte na **Nastavení** > **Hesla a účty** > **Přidat účet** > **Exchange**.

2. Zadejte e-mailovou adresu uživatele v testovacím tenantovi a stiskněte **Další**.

3. Stiskněte **Přihlásit se**.

4. Zadejte heslo testovacího uživatele a stiskněte **Přihlásit se**.

5. Zobrazí se zpráva, že zařízení musí být spravováno, aby mohlo prostředek použít, spolu s možností registrace.

## <a name="clean-up-resources"></a>Vyčištění prostředků

Pokud už testovací zásady nepotřebujete, můžete je odebrat.
1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) as a Global Administrator or an Intune Service Administrator.

2. Select **Devices** > **Compliance policies**.

3. V seznamu **Název zásady** vyberte u testovací zásady místní nabídku ( **...** ) a potom vyberte **Odstranit**. Vyberte **OK**. Tím akci potvrdíte.

4. Select **Endpoint security** > **Conditional access**.

5. V seznamu **Název zásady** vyberte u testovací zásady místní nabídku ( **...** ) a potom vyberte **Odstranit**. Select **Yes** to confirm.

## <a name="next-steps"></a>Další kroky

V tomto kurzu jste vytvořili zásady, které vyžadují, aby se zařízení s iOSem zaregistrovala v Intune a používala aplikaci Outlook pro přístupu k e-mailu Exchange Online. To learn about using Intune with Conditional Access to protect other apps and services, including Exchange ActiveSync clients for Office 365 Exchange Online, see [Set up Conditional Access](conditional-access.md).
