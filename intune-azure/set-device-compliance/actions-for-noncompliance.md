---
title: "Akce při nedodržení předpisů"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si, jak vytvořit akce při nedodržení předpisů zařízeními"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: deea78dcea9ade031441bf12b388a862235a8e9c
ms.openlocfilehash: 16da087e741e335144266c838c0a91050bd7d520
ms.lasthandoff: 03/15/2017


---

# <a name="create-actions-for-non-compliance"></a>Vytvoření akcí při nedodržení předpisů

**Akce při nedodržení předpisů** umožňují konfigurovat časově seřazenou posloupnost akcí, které se použijí na zařízení, u kterého nebudou dodrženy předpisy. Můžete třeba uživatele zařízení nedodržujících předpisy upozornit prostřednictvím e-mailu nebo těmto zařízením zablokovat přístup k podnikovým prostředkům prostřednictvím podmíněného přístupu.

## <a name="use-case-scenario"></a>Scénář použití

Ve výchozím nastavení platí, že jakmile zásady dodržování předpisů Intune nahlásí, že zařízení předpisy nedodržuje, podmíněný přístup zařízení okamžitě zablokuje a uživatel dostane e-mail s pokyny, jak dodržení předpisů zajistit. Díky **akcím při nedodržení předpisů** získáte větší flexibilitu v rozhodování, co dělat, když zařízení předpisy nedodržuje. Můžete třeba rozhodnout, že se zařízení okamžitě nezablokuje a uživatel dostane nějaký čas na to, aby dodržení předpisů zajistil.

Existují dva typy akcí:

-   Upozornění uživatele prostřednictvím e-mailu

-   Zablokování přístupu k podnikovým prostředkům prostřednictvím podmíněného přístupu

## <a name="notify-the-user-via-email"></a>Upozornění uživatele prostřednictvím e-mailu

Můžete vybrat z předem vytvořené výchozí e-mailové šablony nebo vytvořit plně přizpůsobené e-mailové oznámení. Umožňujeme přizpůsobit si předmět a text zprávy a také přidat logo společnosti, kontaktní údaje a další příjemce.

## <a name="block-corporate-resource-access-through-conditional-access"></a>Zablokování přístupu k podnikovým prostředkům prostřednictvím podmíněného přístupu

Můžete určit, kolik dní má mít zařízení zablokovaný přístup k podnikovým prostředkům. K zablokování může dojít okamžitě, nebo můžete uživateli dát nějaký čas na to, aby dodržení předpisů zařízením zajistil.

## <a name="before-you-begin"></a>Před zahájením

Abyste mohli akce při nedodržení předpisů nastavit, musíte mít vytvořenou aspoň jednu zásadu dodržování předpisů zařízením.

-   Zjistěte, jak vytvořit zásady dodržování předpisů zařízením pro:

    -   [Android](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android)

    -   [Android for Work](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android-for-work)

    -   [iOS](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-ios)

    -   [Windows](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-windows)

Pokud plánujete použít zásady dodržování předpisů zařízením k zablokování přístupu zařízení k podnikovým prostředkům, musíte mít nastavený podmíněný přístup EMS.

- Přečtěte si, [jak nastavit podmíněný přístup EMS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

Navíc musíte mít vytvořenou šablonu zpráv s oznámením. Šablona zpráv s oznámením se použije v pozdější fázi procesu vytváření akcí při nedodržení předpisů k odesílání e-mailů uživatelům.

### <a name="to-add-a-notification-message-template"></a>Přidání šablony zprávy s oznámením

V okně **Zásady dodržování předpisů zařízením**:

1.  V části **Spravovat** zvolte **Oznámení**, čímž se otevře okno šablony zprávy s oznámením.

    ![Přidání šablony oznámení](../media/afnc-1.png)

2.  Zvolte **Přidat** a pak musíte definovat následující:

    a.  Popis

    b.  Z

    c.  Předmět

    d.  Zpráva

    e.  Záhlaví e-mailu – Připojte logo společnosti.

    f.  Zápatí e-mailu – Uveďte název společnosti.

    g.  Zápatí e-mailu – Uveďte kontaktní údaje.

     ![Šablona zprávy s oznámením](../media/afnc-2.png)

Po dokončení přidávání informací můžete kliknout na **Vytvořit**. Šablona zprávy s oznámením je pak k dispozici.

> [!NOTE] 
> Můžete také upravit dříve vytvořenou šablonu oznámení.

## <a name="to-create-actions-for-non-compliance"></a>Vytvoření akcí při nedodržení předpisů

Akci můžete přidat při vytváření nových zásad dodržování předpisů zařízením nebo upravením už existujících zásad.

1.  V okně **Zásady dodržování předpisů zařízením** pod možností **Spravovat** vyberte **Zásady**.

2.  Kliknutím zvolte zásadu dodržování předpisů zařízením.

    ![Zásady dodržování předpisů](../media/afnc-3.png)

3.  Otevře se okno s **vlastnostmi zásad dodržování předpisů zařízením**, ve kterém zvolte **Akce při nedodržení předpisů**.

4.  Otevře se okno Akce při nedodržení předpisů, ve kterém zvolte **Přidat** a určete parametry akce.

    ![Okno Akce při nedodržení předpisů](../media/afnc-4.png)

Akce při nedodržení předpisů jsou tyto:

-   **Označit jako nedodržující předpisy**

-   **Odeslat e-mail koncovému uživateli**

### <a name="enforce-conditional-access-policy"></a>Označit jako nedodržující předpisy

Pokud chcete přidat tuto akci při nedodržení předpisů:

1.  V okně **Akce při nedodržení předpisů** vyberte **Přidat**.

2.  V okně **Parametry akce** vyberte z rozevíracího seznamu akce možnost **Označit jako nedodržující předpisy**.

3.  V **Plánu** můžete zadat počet dní (0 až 255) k vynucení zásad podmíněného přístupu. Pokud zadáte počet dní **0**, znamená to, že podmíněný přístup musí **okamžitě** zablokovat přístup k podnikovým prostředkům, jakmile zařízení přestanou dodržovat předpisy.

    ![Naplánování akcí při nedodržení předpisů](../media/afnc-5.png)

4.  Zvolte **Přidat** a pak v okně **Akce** zvolte **OK**.

5.  V okně s **vlastnostmi zásad dodržování předpisů zařízením** zvolte **Uložit**.

### <a name="send-e-mail-to-end-user"></a>Odeslat e-mail koncovému uživateli

Můžete použít e-mailovou šablonu, která se má odeslat uživatelům nedodržujícím předpisy. Tyto e-maily pomáhají udržovat dodržování předpisů zařízeními v celé organizaci.

Pokud chcete přidat tuto akci při nedodržení předpisů:

1.  V okně **Akce při nedodržení předpisů** vyberte **Přidat**.

2.  V okně **Parametry akce** vyberte z rozevíracího seznamu akce možnost **Odeslat e-mail koncovému uživateli**.

3.  Kliknutím na **Šablona zprávy** zvolte dříve vytvořenou šablonu zprávy. Můžete si zobrazit obsah šablony zprávy. Pak zvolte **Vybrat**.

    ![Šablona zprávy](../media/afnc-6.png)

> [!NOTE] 
> Šablonu zprávy můžete zobrazit, ale nemůžete ji upravovat. Pokud chcete šablonu zprávy upravit, musíte se vrátit do okna **Oznámení**.

1.  V **Plánu** zadejte, po kolika dnech nedodržení předpisů se má e-mail uživatelům odeslat. Pokud zadáte počet dní **0**, znamená to, že se e-mail odešle **okamžitě**.

2.  Zvolte **Přidat** a pak v okně **Akce** zvolte **OK**.

3.  V okně s **vlastnostmi zásad dodržování předpisů zařízením** zvolte **Uložit**.

