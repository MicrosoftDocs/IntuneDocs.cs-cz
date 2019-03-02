---
title: Zpráva a akce při nedodržení předpisů v Microsoft Intune – Azure | Microsoft Docs
description: Vytvořte e-mailové oznámení, které se odešle do zařízení nedodržujícího předpisy. Přidejte akce, které se provedou, když je zařízení označeno jako nedodržující předpisy. Můžete třeba přidat období odkladu, během kterého musí uživatel dodržení předpisů zajistit, nebo vytvořit plán k zablokování přístupu, dokud zařízení nebude předpisy dodržovat. Použijte k tomu Microsoft Intune v Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/01/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 67d34d3c5ee6f964caeecf9e657563c421054971
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2019
ms.locfileid: "57231090"
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices-in-intune"></a>Automatické e-maily a přidání akcí pro zařízení nedodržující předpisy v Intune

Pro zařízení, která nesplňují zásady dodržování předpisů nebo pravidla, můžete přidat **akce při nedodržení**. Tato funkce nakonfiguruje časově řazenou posloupnost akcí, jako je například e-mailem žádají koncového uživatele a další.

## <a name="overview"></a>Přehled

Když Intune ve výchozím nastavení detekuje zařízení, které nedodržuje předpisy, okamžitě ho označí jako nedodržující předpisy. [Podmíněný přístup](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) Azure Active Directory (AD) pak zařízení zablokuje. Pokud zařízení nedodržuje předpisy, **akce při nedodržení** vám umožní flexibilně se rozhodnout, jak postupovat. Zařízení třeba nemusíte okamžitě zablokovat, ale můžete dát uživateli nějaký čas na to, aby dodržení předpisů zajistil.

Existuje několik typů akcí:

- **Odeslat e-mail koncovému uživateli**: E-mailové oznámení před odesláním koncovému uživateli přizpůsobte. Můžete přizpůsobit příjemce, předmět, a text zprávy včetně loga společnosti a kontaktních údajů.

    Kromě toho Intune v e-mailovém oznámení uvede podrobnosti o zařízení nedodržujícím předpisy.

- **Vzdálené uzamčení zařízení nedodržujícím předpisy**: Pro zařízení, která nejsou kompatibilní můžete vydat vzdálený zámek. Uživateli se zobrazí výzva k zadání PIN kódu nebo hesla k odemknutí zařízení. Další informace o funkci [vzdáleného uzamčení](device-remote-lock.md). 

- **Označit zařízení jako nevyhovující**: Vytvoření plánu (ve dnech) po zařízení označeno jako nedodržující předpisy. Může to být okamžitě nebo můžete dát uživateli nějaký čas na to, aby dodržení předpisů zařízením zajistil.

V tomto článku se dozvíte, jak:

- Vytvořit šablonu zprávy s oznámením
- Vytvořit akci pro případ nedodržování předpisů, například odeslat e-mail nebo vzdáleně uzamknout zařízení


## <a name="before-you-begin"></a>Před zahájením

- Abyste mohli akce při nedodržení předpisů nastavit, musíte mít aspoň jednu zásadu dodržování předpisů zařízením. Podívejte se, jak vytvořit zásady dodržování předpisů zařízeními pro tyto platformy:

  - [Android](compliance-policy-create-android.md)
  - [Pracovní profily Androidu](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Když používáte zásady dodržování předpisů zařízením k zablokování přístupu zařízení k podnikovým prostředkům, musíte mít nastavený podmíněný přístup Azure AD. Pokyny najdete v tématu o [podmíněném přístupu v Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) nebo o [běžných způsobech použití podmíněného přístupu s Intune](conditional-access-intune-common-ways-use.md).

## <a name="create-a-notification-message-template"></a>Vytvoření šablony zprávy s oznámením

Pokud chcete svým uživatelům odeslat e-mail, vytvořte šablonu zprávy s oznámením. Pokud zařízení nedodržuje předpisy, musíte do šablony zadat podrobnosti, které se zobrazují v e-mailu odeslaném vašim uživatelům.

1. Na [portálu Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **Dodržování předpisů zařízením** > **Oznámení**.
3. Vyberte **Vytvořit oznámení**. Zadejte následující informace:

   - **Název**
   - **Předmět**
   - **Zpráva**
   - **Záhlaví e-mailu – Připojte logo společnosti**
   - **Zápatí e-mailu – Uveďte název společnosti**
   - **Zápatí e-mailu – Uveďte kontaktní údaje**

   ![Příklad oznámení o dodržování předpisů v Intune](./media/actionsfornoncompliance-1.PNG)

4. Po přidání informací vyberte **Vytvořit**. Šablona zprávy s oznámením je připravená k použití. Logo, které budou nahrány jako součást značky portálu společnosti se používá pro e-mailové šablony. Další informace o značce Portálu společnosti najdete v tématu o [přizpůsobení brandingu firemní identity](company-portal-app.md#company-identity-branding-customization).

> [!NOTE]
> Můžete také změnit nebo aktualizovat stávající šablonu oznámení, který jste předtím vytvořili.

## <a name="add-actions-for-noncompliance"></a>Přidání akcí při nedodržení předpisů

Když vytvoříte zásady dodržování předpisů pro zařízení, Intune automaticky vytvoří akci pro případ nedodržování těchto předpisů. Pokud zařízení nesplňuje vaše zásady dodržování předpisů, tato akce zařízení označí jako nedodržující předpisy. Můžete přizpůsobit, jak dlouho bude zařízení takto označené. Tuto akci není možné odebrat.

Další akci můžete přidat při vytváření zásad dodržování předpisů nebo při aktualizaci existujících zásad. 

1. Na portálu [Azure Portal](https://portal.azure.com) otevřete **Microsoft Intune** > **Dodržování předpisů zařízením**.
2. Vyberte **Zásady**, vyberte jednu ze zásad a pak vyberte **Vlastnosti**. 

    Ještě zásadu nemáte? Vytvořte zásadu pro [Android](compliance-policy-create-android.md), [iOS](compliance-policy-create-ios.md), [Windows](compliance-policy-create-windows.md) nebo jinou platformu.
  
    > [!NOTE]
    > Zařízení JAMF a zařízení nastavená pomocí skupin zařízení nemohou v současnosti přijímat akce dodržování předpisů.

3. Vyberte **Akce při nedodržení předpisů** > **Přidat**.
4. Vyberte vaši **Akci**: 

    - **Odeslání e-mailu pro koncové uživatele**: Pokud zařízení nedodržuje předpisy, zvolte k e-mailu uživatele. Také: 
    
         - Vyberte **Šablonu zprávy**, kterou jste dříve vytvořili.
         - Zadejte libovolné **Další příjemce** výběrem skupin.
    
    - **Vzdálené uzamčení zařízení nedodržujícím předpisy**: Pokud zařízení nedodržuje předpisy, uzamčení zařízení. Tato akce vynutí, aby uživatel zadal kód PIN nebo hesla k odemknutí zařízení. 
    
    - **Plán**: Zadejte počet dní (0 až 365) po nedodržení předpisů k aktivaci akce na zařízeních uživatelů. Po skončení této poskytnuté lhůty můžete vynutit zásady podmíněného přístupu. Pokud zadáte **0** (nula) počet dnů, pak podmíněný přístup se projeví **okamžitě**. Pokud zařízení nedodržuje předpisy, můžete například okamžitě blokovat přístup k firemním prostředkům.

5. Po dokončení vyberte **Přidat** > **OK** k uložení změn.

## <a name="next-steps"></a>Další postup

[Monitorovat zásady](compliance-policy-monitor.md).
