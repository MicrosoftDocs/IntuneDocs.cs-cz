---
title: Zpráva a akce při nedodržení předpisů v Microsoft Intune – Azure | Microsoft Docs
description: Vytvořte e-mailové oznámení, které se odešle do zařízení nedodržujícího předpisy. Přidejte akce, které se provedou, když je zařízení označeno jako nedodržující předpisy. Můžete třeba přidat období odkladu, během kterého musí uživatel dodržení předpisů zajistit, nebo vytvořit plán k zablokování přístupu, dokud zařízení nebude předpisy dodržovat. Použijte k tomu Microsoft Intune v Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8e8603ca59b46937b1529e710a8bc83aec5dd4d6
ms.sourcegitcommit: 4c18352d5b3b30080f7c7257fa63d852b1894850
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2018
ms.locfileid: "32017953"
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices---intune"></a>Automatické e-maily a přidání akcí pro zařízení nedodržující předpisy – Intune

Existuje funkce **Akce při nedodržení předpisů**, pomocí které můžete nakonfigurovat sled akcí v časovém pořadí. Tyto akce se aplikují na zařízení, která nesplňují vaše zásady dodržování předpisů. 

## <a name="overview"></a>Přehled
Když Intune ve výchozím nastavení detekuje zařízení, které nedodržuje předpisy, okamžitě ho označí jako nedodržující předpisy. [Podmíněný přístup](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) Azure Active Directory (AD) pak zařízení zablokuje. Když zařízení nedodržuje předpisy, **akce při nedodržení předpisů** vám umožní flexibilně se rozhodnout, co udělat. Zařízení třeba nemusíte okamžitě zablokovat, ale můžete dát uživateli nějaký čas na to, aby dodržení předpisů zajistil.

Existují dva typy akcí:

- **Upozornění koncových uživatelů prostřednictvím e-mailu**: přizpůsobte si e-mailové oznámení před odesláním koncovému uživateli. Můžete přizpůsobit příjemce, předmět, a text zprávy včetně loga společnosti a kontaktních údajů.

    Kromě toho Intune v e-mailovém oznámení uvede podrobnosti o zařízení nedodržujícím předpisy.

- **Označit zařízení jako nedodržující předpisy**: nastavte, za kolik dní má být zařízení označeno jako nedodržující předpisy. Může to být okamžitě nebo můžete dát uživateli nějaký čas na to, aby dodržení předpisů zařízením zajistil.

## <a name="before-you-begin"></a>Před zahájením

- Abyste mohli akce při nedodržení předpisů nastavit, musíte mít aspoň jednu zásadu dodržování předpisů zařízením. Podívejte se, jak vytvořit zásady dodržování předpisů zařízeními pro tyto platformy:

  - [Androidemem](compliance-policy-create-android.md)
  - [Android for Work](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Když používáte zásady dodržování předpisů zařízením k zablokování přístupu zařízení k podnikovým prostředkům, musíte mít nastavený podmíněný přístup Azure AD. Postup najdete v článku [Podmíněný přístup v Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

- Musí být vytvořená šablona zprávy s oznámením. Abyste odeslali e-mail uživatelům, tato šablona slouží k vytvoření akcí při nedodržení předpisů.

## <a name="create-a-notification-message-template"></a>Vytvoření šablony zprávy s oznámením

1. Přihlaste se na portálu [Azure Portal](https://portal.azure.com) pomocí svých přihlašovacích údajů k Intune. 
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Dodržování předpisů zařízením** a pak **Oznámení**. 
4. Vyberte **Vytvořit oznámení** a zadejte tyto informace:

   - Název
   - Předmět
   - Zpráva
   - Záhlaví e-mailu – připojte logo společnosti
   - Zápatí e-mailu – uveďte název společnosti
   - Zápatí e-mailu – uveďte kontaktní údaje

   ![Příklad oznámení o dodržování předpisů v Intune](./media/actionsfornoncompliance-1.PNG)

Po přidání informací vyberte **Vytvořit**. Šablona zprávy s oznámením je připravená k použití.

> [!NOTE]
> Můžete také upravit dříve vytvořenou šablonu oznámení.

## <a name="add-actions-for-noncompliance"></a>Přidání akcí při nedodržení předpisů

Ve výchozím nastavení Intune automaticky vytvoří akci, která se použije při nedodržení předpisů. Pokud zařízení nesplňuje vaše zásady dodržování předpisů, tato akce zařízení označí jako nedodržující předpisy. Můžete přizpůsobit, jak dlouho bude zařízení takto označené. Tuto akci není možné odebrat.

Akci můžete přidat při vytváření nových zásad dodržování předpisů nebo při aktualizaci existujících zásad. 

1. Na portálu [Azure Portal](https://portal.azure.com) otevřete **Microsoft Intune** a vyberte **Dodržování předpisů zařízením**.
2. Vyberte **Zásady**, vyberte jednu ze zásad a pak vyberte **Vlastnosti**. 

  Ještě zásadu nemáte? Vytvořte zásadu pro [Android](compliance-policy-create-android.md), [iOS](compliance-policy-create-ios.md), [Windows](compliance-policy-create-windows.md) nebo jinou platformu.
  
  > [!NOTE]
  > Zařízení JAMF a zařízení nastavená pomocí skupin zařízení nemohou v současnosti přijímat akce dodržování předpisů.

3. Vyberte **Akce při nedodržení předpisů** a pak pomocí **Přidat** zadejte parametry akce. Můžete vybrat dřív vytvořenou šablonu zprávy, přidat další příjemce a aktualizovat období odkladu. V období můžete zadat počet dní (0 až 365), po kterém můžete vynutit zásady podmíněného přístupu. Pokud zadáte **0** dní, pak podmíněný přístup **okamžitě** zablokuje přístup k podnikovým prostředkům.

4. Po dokončení vyberte **Přidat** > **OK** k uložení změn.

## <a name="next-steps"></a>Další kroky
Sledujte aktivitu dodržování předpisů zařízením pomocí sestav. Pokyny najdete v tématu [Monitorování dodržování předpisů zařízením v Intune](device-compliance-monitor.md).
