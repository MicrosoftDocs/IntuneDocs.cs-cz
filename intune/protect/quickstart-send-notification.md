---
title: Rychlý start – odeslání oznámení zařízením nedodržujícím předpisy
titleSuffix: Microsoft Intune
description: V tomto rychlém startu použijete Microsoft Intune k odeslání e-mailových oznámení zařízením nedodržujícím předpisy.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/24/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1b89f2d-7937-46bb-926b-b05f6fa9c749
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5fe05152b2221f17df4497d30e6a028523b878fd
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729518"
---
# <a name="quickstart-send-notifications-to-noncompliant-devices"></a>Rychlý start: Odeslání oznámení zařízením nedodržujícím předpisy

V tomto rychlém startu použijete Microsoft Intune k odeslání e-mailových oznámení zaměstnancům, kteří používají zařízení nedodržující předpisy.

Když Intune ve výchozím nastavení detekuje zařízení, které nedodržuje předpisy, okamžitě ho označí jako nedodržující předpisy. [Podmíněný přístup k](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) Azure Active Directory (AAD) pak zařízení zablokuje. Když zařízení nedodržuje předpisy, umožňuje Intune přidat akce při nedodržení předpisů, což vám umožní se flexibilně rozhodnout, jak postupovat. Uživatelům můžete dát například určitou dobu odkladu, během které musí zajistit dodržování předpisů, než tato zařízení zablokujete.

Jednou z akcí, které můžete udělat, když zařízení nedodržují předpisy, je odeslání e-mailu jejich koncovým uživatelům. E-mailové oznámení můžete před odesláním koncovým uživatelům přizpůsobit. Konkrétně můžete přizpůsobit příjemce, předmět a text zprávy včetně firemního loga a kontaktních údajů. Intune do tohoto e-mailového oznámení zároveň zahrne podrobnosti o zařízení nedodržujícím předpisy.

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Požadované součásti
- Pokud používáte zásady dodržování předpisů zařízením k blokování zařízení z firemních prostředků, musíte nastavit podmíněný přístup AAD. Pokud jste dokončili rychlý start věnovaný [vytvoření zásady dodržování předpisů pro zařízení](quickstart-set-password-length-android.md), službu Azure Active Directory používáte. Další informace o AAD najdete v tématu [podmíněný přístup v Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) a [běžné způsoby použití podmíněného přístupu s Intune](../protect/conditional-access-intune-common-ways-use.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k portálu [Intune](https://aka.ms/intuneportal) jako [globální správce](../fundamentals/users-add.md#types-of-administrators) nebo jako [správce služby](../fundamentals/users-add.md#types-of-administrators) Intune. Pokud jste vytvořili zkušební předplatné Intune, účet, z něhož jste toto předplatné vytvořili, je globálním správcem.

## <a name="create-a-notification-message-template"></a>Vytvoření šablony zprávy s oznámením

Pokud chcete svým uživatelům odeslat e-mail, vytvořte šablonu zprávy s oznámením. Pokud zařízení nedodržuje předpisy, musíte do šablony zadat podrobnosti, které se zobrazují v e-mailu odeslaném vašim uživatelům.

1. V Intune vyberte **Dodržování předpisů zařízením** > **Oznámení** > **Vytvořit oznámení**. 
2. Zadejte následující informace:

   - **Jméno:** *Správce Contoso*
   - **Předmět:** *Dodržování předpisů zařízením*
   - **Zpráva**: *vaše zařízení aktuálně nesplňuje požadavky naší organizace na dodržování předpisů.*
   - **Záhlaví e-mailu – Připojte logo společnosti:** Pokud chcete zobrazit logo organizace, nastavte na **Povoleno**.
   - **Zápatí e-mailu – Uveďte název společnosti:** Pokud chcete zobrazit název organizace, nastavte na **Povoleno**.
   - **Zápatí e-mailu – Uveďte kontaktní údaje:** Pokud chcete zobrazit kontaktní údaje organizace, nastavte na **Povoleno**.

   ![Příklad oznámení o dodržování předpisů v Intune](./media/quickstart-send-notification/quickstart-send-notification-01.png)

3. Po přidání informací vyberte **Vytvořit**. Šablona zprávy s oznámením je připravená k použití.

    > [!NOTE]
    > Můžete také upravit některou dříve vytvořenou šablonu oznámení.

Podrobnosti o nastavení názvu, kontaktních údajů a loga firmy najdete v článku [Informace o společnosti a prohlášení o zásadách ochrany osobních údajů](../apps/company-portal-app.md#company-information-and-privacy-statement), [Informace o podpoře](../apps/company-portal-app.md#support-information) a [Přizpůsobení brandingu firemní identity](../apps/company-portal-app.md#company-identity-branding-customization). 

## <a name="add-a-noncompliance-policy"></a>Přidání zásady při nedodržování předpisů

Když vytvoříte zásady dodržování předpisů pro zařízení, Intune automaticky vytvoří akci pro případ nedodržování těchto předpisů. Pokud zařízení nesplňuje zásadu dodržování předpisů, označí Intune toto zařízení automaticky jako nedodržující předpisy. Můžete přizpůsobit, jak dlouho bude zařízení takto označené. Při vytváření zásady dodržování předpisů nebo aktualizaci existující zásady dodržování předpisů můžete také přidat další akci. 

Následující postup vytvoří zásadu dodržování předpisů pro zařízení s Windows 10.

1. V Intune vyberte **Dodržování předpisů zařízením**.
2. Vyberte **Zásady** > **Vytvořit zásadu**.
3. Zadejte následující informace:

   - **Název:** *Dodržování předpisů pro Windows 10*
   - **Popis:** *Zásada dodržování předpisů pro Windows 10*
   - **Platforma:** Windows 10 a novější

4. Výběrem možnosti **Nastavení** > **Zabezpečení systému** zobrazte nastavení související se zabezpečením zařízení.
5. Možnost **Vyžadovat heslo k odemknutí mobilních zařízení** nastavte na **Vyžadovat**. Toto nastavení určuje, jestli se má po uživatelích vyžadovat zadání hesla, než bude udělen přístup k informacím uloženým v jejich mobilních zařízeních. 
6. Volbu **Minimální délka hesla** nastavte na **6**. Toto nastavení určuje minimální počet číslic nebo znaků v hesle.

    <img alt="System Security settings for a new compliance policy" src="./media/quickstart-send-notification/quickstart-send-notification-01.png" width="600">

7. Vyberte **ok** > **OK** > **vytvořit** a vytvořte tak zásady dodržování předpisů.
8. Vyberte **Vlastnosti** > **Akce při nedodržení předpisů** > **Přidat**.
9. V rozevíracím seznamu **Akce** potvrďte, že je vybraná možnost **Odeslat e-mail koncovému uživateli**.
10. Výběrem možnosti **Šablona zprávy** > **Správce Contoso** > **Vybrat** vyberte šablonu zprávy, kterou jste vytvořili dříve v tomto tématu.
11. Vyberte **přidat** > **OK** > **Uložit** , aby se změny uložily.

## <a name="assign-the-policy"></a>Přiřazení zásady

Zásadu dodržování předpisů můžete přiřadit určité skupině uživatelů nebo všem uživatelům. Když Intune rozpozná, že zařízení nedodržuje předpisy, bude uživateli oznámeno, že zařízení musí aktualizovat tak, aby splňovalo tuto zásadu dodržování předpisů. K přiřazení zásady použijte následující postup.

1. Vyberte zásadu **Dodržování předpisů pro Windows 10**, kterou jste vytvořili dříve.
2. Zvolte **Přiřazení**.
3. V rozevíracím seznamu **Přiřadit k** vyberte **Všichni uživatelé**. Tím vyberete všechny uživatele. Každý uživatel se zařízením s **Windows 10 a novější verzí**, které nesplňuje tuto zásadu dodržování předpisů, dostane oznámení.

    > [!NOTE]
    > Při přiřazování zásad dodržování předpisů můžete zahrnout a vyloučit skupiny.

4. Klikněte na **Uložit**.

Pokud se vám podařilo zásadu vytvořit a uložit, zobrazí se v seznamu **Dodržování předpisů zařízením – Zásady**. V tomto seznamu si můžete všimnout, že **Přiřazeno** je nastavené na **Ano**.

## <a name="next-steps"></a>Další kroky

V tomto rychlém startu jste Intune použili k vytvoření a přiřazení zásady dodržování předpisů pro firemní zařízení s Windows 10, která vyžaduje zadání hesla o minimální délce šesti znaků. Další informace o vytváření zásad dodržování předpisů pro zařízení s Windows najdete v článku [Přidání zásad dodržování předpisů pro zařízení s Windows v Intune](compliance-policy-create-windows.md).

Pokud chcete postupovat podle této série rychlých startů Intune, pokračujte k dalšímu rychlému startu.

> [!div class="nextstepaction"]
> [Rychlý start: Přidání a přiřazení klientské aplikace](../apps/quickstart-add-assign-app.md)
