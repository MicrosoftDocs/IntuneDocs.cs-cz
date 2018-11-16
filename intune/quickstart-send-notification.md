---
title: Rychlý start – odeslání oznámení zařízením nedodržujícím předpisy
titlesuffix: Microsoft Intune
description: V tomto rychlém startu použijete Microsoft Intune k odeslání e-mailových oznámení zařízením nedodržujícím předpisy.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/09/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1b89f2d-7937-46bb-926b-b05f6fa9c749
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e76e173bef7a370f89f60f6c9eb4588bb63aefdc
ms.sourcegitcommit: 4c4e87cb0d8906085fcb7cdd170bd6b0cfeb23ff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/10/2018
ms.locfileid: "51510903"
---
# <a name="quickstart-send-notifications-to-noncompliant-devices"></a>Rychlý start: Odeslání oznámení zařízením nedodržujícím předpisy

V tomto rychlém startu použijete Microsoft Intune k odeslání e-mailových oznámení zaměstnancům, kteří používají zařízení nedodržující předpisy.

Když Intune ve výchozím nastavení detekuje zařízení, které nedodržuje předpisy, okamžitě ho označí jako nedodržující předpisy. [Podmíněný přístup](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) služby Azure Active Directory (AAD) pak takové zařízení zablokuje. Když zařízení nedodržuje předpisy, umožňuje Intune přidat akce při nedodržení předpisů, což vám umožní se flexibilně rozhodnout, jak postupovat. Uživatelům můžete dát například určitou dobu odkladu, během které musí zajistit dodržování předpisů, než tato zařízení zablokujete.

Jednou z akcí, které můžete udělat, když zařízení nedodržují předpisy, je odeslání e-mailu jejich koncovým uživatelům. E-mailové oznámení můžete před odesláním koncovým uživatelům přizpůsobit. Konkrétně můžete přizpůsobit příjemce, předmět a text zprávy včetně firemního loga a kontaktních údajů. Intune do tohoto e-mailového oznámení zároveň zahrne podrobnosti o zařízení nedodržujícím předpisy.

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

## <a name="prerequisites"></a>Požadavky
- Při použití zásad dodržování předpisů zařízením k blokování přístupu zařízení k podnikovým prostředkům musí být nastavený podmíněný přístup služby AAD. Pokud jste dokončili rychlý start věnovaný [vytvoření zásady dodržování předpisů pro zařízení](quickstart-set-password-length-android.md), službu Azure Active Directory používáte. Další informace o službě AAD najdete v článku [Podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) a [Běžné způsoby používání podmíněného přístupu s Intune](conditional-access-intune-common-ways-use.md).

## <a name="sign-in-to-intune"></a>Přihlášení k Intune

Přihlaste se k portálu [Intune](https://aka.ms/intuneportal) jako [globální správce](users-add.md#types-of-administrators) nebo jako [správce služby](users-add.md#types-of-administrators) Intune. 

## <a name="create-a-notification-message-template"></a>Vytvoření šablony zprávy s oznámením

Pokud chcete svým uživatelům odeslat e-mail, vytvořte šablonu zprávy s oznámením. Pokud zařízení nedodržuje předpisy, musíte do šablony zadat podrobnosti, které se zobrazují v e-mailu odeslaném vašim uživatelům.

1. V Intune vyberte **Dodržování předpisů zařízením** > **Oznámení** > **Vytvořit oznámení**. 
2. Zadejte následující informace:

   - **Jméno:** *Správce Contoso*
   - **Předmět:** *Dodržování předpisů zařízením*
   - **Zpráva:** *Vaše zařízení momentálně nesplňuje požadavky na dodržování předpisů naší organizace.*
   - **Záhlaví e-mailu – Připojte logo společnosti:** Pokud chcete zobrazit logo organizace, nastavte na **Povoleno**.
   - **Zápatí e-mailu – Uveďte název společnosti:** Pokud chcete zobrazit název organizace, nastavte na **Povoleno**.
   - **Zápatí e-mailu – Uveďte kontaktní údaje:** Pokud chcete zobrazit kontaktní údaje organizace, nastavte na **Povoleno**.

   ![Příklad oznámení o dodržování předpisů v Intune](./media/quickstart-send-notification-01.png)

3. Po přidání informací vyberte **Vytvořit**. Šablona zprávy s oznámením je připravená k použití.

    > [!NOTE]
    > Můžete také upravit některou dříve vytvořenou šablonu oznámení.

Podrobnosti o nastavení názvu, kontaktních údajů a loga firmy najdete v článku [Informace o společnosti a prohlášení o zásadách ochrany osobních údajů](company-portal-app.md#company-information-and-privacy-statement), [Informace o podpoře](company-portal-app.md#support-information) a [Přizpůsobení brandingu firemní identity](company-portal-app.md#company-identity-branding-customization). 

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

    ![Nastavení Zabezpečení systému pro novou zásadu dodržování předpisů](./media/quickstart-send-notification-02.png) 

7. Kliknutím na **OK**, **OK** a **Vytvořit** tuto zásadu dodržování předpisů vytvořte.
8. Vyberte název nové zásady: **Dodržování předpisů pro Windows 10**.
9. Vyberte **Vlastnosti** > **Akce při nedodržení předpisů** > **Přidat**.
10. V rozevíracím seznamu **Akce** potvrďte, že je vybraná možnost **Odeslat e-mail koncovému uživateli**.
11. Výběrem možnosti **Šablona zprávy** > **Správce Contoso** > **Vybrat** vyberte šablonu zprávy, kterou jste vytvořili dříve v tomto tématu.
12. Výběrem **OK** > **OK** > **Uložit** uložte provedené změny.

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
> [Rychlý start: Přidání a přiřazení klientské aplikace](quickstart-add-assign-app.md)
