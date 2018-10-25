---
title: Zpráva a akce při nedodržení předpisů v Microsoft Intune – Azure | Microsoft Docs
description: Vytvořte e-mailové oznámení, které se odešle do zařízení nedodržujícího předpisy. Přidejte akce, které se provedou, když je zařízení označeno jako nedodržující předpisy. Můžete třeba přidat období odkladu, během kterého musí uživatel dodržení předpisů zajistit, nebo vytvořit plán k zablokování přístupu, dokud zařízení nebude předpisy dodržovat. Použijte k tomu Microsoft Intune v Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fae8faf54c7b41bb547912853285cf09ec9c46d5
ms.sourcegitcommit: d92caead1d96151fea529c155bdd7b554a2ca5ac
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2018
ms.locfileid: "48828104"
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices---intune"></a>Automatické e-maily a přidání akcí pro zařízení nedodržující předpisy – Intune

Existuje funkce **Akce při nedodržení předpisů**, pomocí které můžete nakonfigurovat sled akcí v časovém pořadí. Tyto akce se aplikují na zařízení, která nesplňují vaše zásady dodržování předpisů. 

## <a name="overview"></a>Přehled
Když Intune ve výchozím nastavení detekuje zařízení, které nedodržuje předpisy, okamžitě ho označí jako nedodržující předpisy. [Podmíněný přístup](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) Azure Active Directory (AD) pak zařízení zablokuje. Když zařízení nedodržuje předpisy, **akce při nedodržení předpisů** vám umožní flexibilně se rozhodnout, co udělat. Zařízení třeba nemusíte okamžitě zablokovat, ale můžete dát uživateli nějaký čas na to, aby dodržení předpisů zajistil.

Existuje několik typů akcí:

- **Odeslat e-mail koncovému uživateli**: přizpůsobte si e-mailové oznámení před odesláním koncovému uživateli. Můžete přizpůsobit příjemce, předmět, a text zprávy včetně loga společnosti a kontaktních údajů.

    Kromě toho Intune v e-mailovém oznámení uvede podrobnosti o zařízení nedodržujícím předpisy.

- **Vzdáleně uzamknout zařízení, které nedodržuje předpisy**: pro zařízení, která nedodržují předpisy, můžete vydat vzdálený zámek. Uživateli se zobrazí výzva k zadání PIN kódu nebo hesla k odemknutí zařízení. Další informace o funkci [vzdáleného uzamčení](device-remote-lock.md). 

- **Označit zařízení jako nedodržující předpisy**: nastavte, za kolik dní má být zařízení označeno jako nedodržující předpisy. Může to být okamžitě nebo můžete dát uživateli nějaký čas na to, aby dodržení předpisů zařízením zajistil.

V tomto článku se dozvíte, jak:

- Vytvořit šablonu zprávy s oznámením
- Vytvořit akci pro případ nedodržování předpisů, například odeslat e-mail nebo vzdáleně uzamknout zařízení


## <a name="before-you-begin"></a>Před zahájením

- Abyste mohli akce při nedodržení předpisů nastavit, musíte mít aspoň jednu zásadu dodržování předpisů zařízením. Podívejte se, jak vytvořit zásady dodržování předpisů zařízeními pro tyto platformy:

  - [Androidemem](compliance-policy-create-android.md)
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

4. Po přidání informací vyberte **Vytvořit**. Šablona zprávy s oznámením je připravená k použití.

> [!NOTE]
> Můžete také upravit dříve vytvořenou šablonu oznámení.

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

    - **Odeslat e-mail koncovému uživateli**: Pokud zařízení nedodržuje předpisy, vyberte možnost odeslání e-mailu uživateli. Také: 
    
         - Vyberte **Šablonu zprávy**, kterou jste dříve vytvořili.
         - Zadejte libovolné **Další příjemce** výběrem skupin.
    
    - **Vzdáleně uzamknout zařízení, které nedodržuje předpisy**: Pokud zařízení nedodržuje předpisy, uzamkněte ho. Aby mohl uživatel zařízení odemknout, musí zadat PIN kód nebo heslo. 
    
    - **Plán**: Zadejte počet dní (0 až 365) po nedodržení předpisů, kdy se má vyvolat akce na zařízeních uživatelů. Po skončení této poskytnuté lhůty můžete vynutit zásady podmíněného přístupu. Pokud jako počet dnů zadáte **0**, potom začne podmíněný přístup platit **okamžitě**. Pokud zařízení nedodržuje předpisy, můžete například okamžitě blokovat přístup k firemním prostředkům.

5. Po dokončení vyberte **Přidat** > **OK** k uložení změn.

## <a name="next-steps"></a>Další kroky
[Monitorování dodržování předpisů zařízením](device-compliance-monitor.md).
