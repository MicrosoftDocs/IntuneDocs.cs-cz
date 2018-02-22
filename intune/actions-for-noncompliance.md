---
title: "Akce při nedodržení předpisů pomocí Intune"
titleSuffix: Intune on Azure
description: "Přečtěte si, jak vytvořit akce při nedodržení předpisů pomocí Intune."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 01/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 573a8b000e63576f3dd3bae1b6e8e8c47733f6bf
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/03/2018
---
# <a name="automate-actions-for-noncompliance"></a>Automatizace akcí při nedodržení předpisů

**Akce při nedodržení předpisů** umožňují konfigurovat časově řazenou posloupnost akcí, které se použijí na zařízeních, která nevyhovují kritériím zásad dodržování předpisů. Když se ve výchozím nastavení zjistí, že zařízení nesplňuje kritéria zásad dodržování předpisů, Intune ho okamžitě označí jako nevyhovující a podmíněný přístup Azure AD pak zařízení zablokuje. Díky **akcím při nedodržení předpisů** získáte větší flexibilitu při rozhodování o postupu v případě, že zařízení nevyhovuje předpisům. Můžete třeba rozhodnout, že se zařízení okamžitě nezablokuje a uživatel dostane nějaký čas na to, aby dodržení předpisů zajistil.

Existují dva typy akcí:

-   **Upozornění koncových uživatelů prostřednictvím e-mailu**: E-mailové oznámení můžete před odesláním koncovému uživateli přizpůsobit. Intune umožňuje přizpůsobit příjemce, předmět, text zprávy a také logo společnosti a kontaktní údaje.

    Kromě toho Intune uvede v e-mailovém oznámení podrobnosti o nevyhovujícím zařízení.

-   **Označit zařízení jako nevyhovující**: Můžete určit, za kolik dní má být zařízení označeno jako nevyhovující. Může to být okamžitě nebo můžete dát uživateli nějaký čas na to, aby dodržení předpisů zařízením zajistil.

## <a name="before-you-begin"></a>Před zahájením

Abyste mohli akce při nedodržení předpisů nastavit, musíte mít vytvořenou aspoň jednu zásadu dodržování předpisů zařízením. 

- Přečtěte si, jak vytvořit zásady dodržování předpisů zařízením pro následující platformy:

    -   [Android](compliance-policy-create-android.md)
    -   [Android for Work](compliance-policy-create-android-for-work.md)
    -   [iOS](compliance-policy-create-ios.md)
    -   [macOS](compliance-policy-create-mac-os.md)
    -   [Windows](compliance-policy-create-windows.md)

Pokud plánujete použít zásady dodržování předpisů zařízením k zablokování přístupu zařízení k podnikovým prostředkům, musíte mít nastavený podmíněný přístup Azure AD. 

- Přečtěte si, [jak nastavit podmíněný přístup EMS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

Navíc musíte mít vytvořenou šablonu zpráv s oznámením. Šablona zpráv s oznámením se použije k odesílání e-mailů uživatelům v pozdější fázi procesu vytváření akcí při nedodržení předpisů.

### <a name="to-create-a-notification-message-template"></a>Vytvoření šablony zprávy s oznámením

1. Přejděte do [Intune na portálu Azure Portal](https://portal.azure.com) a přihlaste se pomocí svých přihlašovacích údajů k Intune.
2. V nabídce vlevo zvolte **Další služby** a do filtru textového pole pak zadejte **Intune**.
3. Zvolte **Intune**.
4. Vyberte **Dodržování předpisů zařízením** a pak vyberte **Oznámení** v sekci **Spravovat**.
5. Zvolte **Vytvořit oznámení** a zadejte tyto informace:
    - Název
    - Předmět
    - Zpráva
    - Záhlaví e-mailu – Připojte logo společnosti.
    - Zápatí e-mailu – Uveďte název společnosti.
    - Zápatí e-mailu – Uveďte kontaktní údaje.

5. Zvolte **Vytvořit oznámení** a zadejte tyto informace:

    a. Název

    b. Předmět

    c.  Zpráva

    d. Záhlaví e-mailu – připojte logo společnosti

    e. Zápatí e-mailu – uveďte název společnosti

    f. Zápatí e-mailu – uveďte kontaktní údaje

![příklad šablony zprávy s oznámením](./media/actionsfornoncompliance-1.PNG)

Po přidání informací vyberte **Vytvořit**. Šablona zprávy s oznámením je pak k dispozici.

> [!NOTE]
> Můžete také upravit dříve vytvořenou šablonu oznámení.

## <a name="to-create-actions-for-noncompliance"></a>Vytvoření akcí při nedodržení předpisů

> [!TIP]
> Ve výchozím nastavení Intune poskytuje jednu akci předem definovanou v sekci akcí při nedodržení předpisů. Tato akce označuje zařízení jako nevyhovující předpisům po zjištění, že zařízení nesplňuje kritéria zásad dodržování předpisů. Můžete přizpůsobit, za jak dlouho po zjištění bude zařízení označeno jako nevyhovující. Tuto akci nejde odebrat.

Akci můžete přidat při vytváření nových zásad dodržování předpisů zařízením nebo při úpravách už existujících zásad.

1.  V úloze Intune v okně **Zásady dodržování předpisů zařízením** vyberte **Zásady** v sekci **Spravovat**.

2.  Kliknutím vyberte zásadu dodržování předpisů zařízením a pak vyberte **Vlastnosti** v sekci **Spravovat**.

3.  Otevře se okno s **vlastnostmi zásad dodržování předpisů zařízením**, ve kterém zvolte **Akce při nedodržení předpisů**.

4.  Otevře se okno **Akce při nedodržení předpisů**, ve kterém zvolte **Přidat** a určete parametry akce. Můžete vybrat dřív vytvořenou šablonu zprávy, další příjemce a období odkladu. V období můžete zadat počet dní (0 až 365), po kterém můžete vynutit zásady podmíněného přístupu. Pokud zadáte počet dní **0**, znamená to, že podmíněný přístup musí **okamžitě** zablokovat přístup k podnikovým prostředkům, jakmile zařízení přestanou dodržovat předpisy.

5.  Po přidání informací vyberte **Přidat** a pak **OK**.

## <a name="next-steps"></a>Další kroky
Aktivitu dodržování předpisů zařízením můžete monitorovat spuštěním sestav, které jsou k dispozici v okně dodržování předpisů zařízením. Podrobnosti najdete v tématu o tom, [jak monitorovat dodržování zásad zařízením v Intune](device-compliance-monitor.md).
