---
title: Povolení konektoru Mobile Threat Defense v Microsoft Intune
titleSuffix: Microsoft Intune
description: Povolte konektor mezi vaším partnerem Mobile Threat Defense (MTD) a Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4dd77be45c21db53dd82322049d377ced247c4c7
ms.sourcegitcommit: 614c4c36cfe544569db998e17e29feeaefbb7a2e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2019
ms.locfileid: "68427347"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Povolení konektoru Mobile Threat Defense v Intune

> [!NOTE] 
> Toto téma se týká všech partnerů ochrany před mobilními hrozbami.

Při nastavení Mobile Threat Defense (MTD) jste v konzole partnera MTD nakonfigurovali zásadu pro klasifikaci hrozeb a vytvořili jste zásadu dodržování předpisů zařízením v Intune. Pokud jste už konektor Intune nakonfigurovali v konzole pro partnery MTD, můžete teď povolit připojení MTD pro partnerské aplikace MTD.

Když integrujete novou aplikaci do ochrany před mobilními hrozbami Intune a povolíte připojení, Intune vytvoří v Azure Active Directory zásady klasického podmíněného přístupu. Každá aplikace MTD, kterou integrujete, jako je [Defender ATP](advanced-threat-protection.md) nebo některé z našich dalších [MTDch partnerů](mobile-threat-defense.md#mobile-threat-defense-partners), vytvoří nové zásady podmíněného přístupu v klasickém rozhraní.  Tyto zásady je možné ignorovat, ale neměly by být upravované, odstraňující ani zakázané.

Klasické zásady podmíněného přístupu pro aplikace MTD: 

- Používá Intune MTD k tomu, aby vyžadovala, aby byla zařízení zaregistrovaná ve službě Azure AD, aby měla ID zařízení. IDENTIFIKÁTOR je povinný, aby zařízení a mohl úspěšně ohlásit svůj stav do Intune.  
- Liší se od zásad podmíněného přístupu, které byste mohli vytvořit, abyste mohli lépe spravovat MTD.
- Ve výchozím nastavení nekomunikujete s dalšími zásadami podmíněného přístupu, které používáte pro vyhodnocení.  

Pokud chcete zobrazit klasické zásady podmíněného přístupu, přejděte v [Azure](https://portal.azure.com/#home)na **Azure Active Directory** > **klasické zásady** **podmíněného přístupu** > .


## <a name="to-enable-the-mtd-connector"></a>Povolení konektoru MTD

1. Přihlaste [](https://go.microsoft.com/fwlink/?linkid=2090973)se k Intune.

4. Na **řídicím panelu Intune** zvolte **Dodržování předpisů zařízením** a potom v části **Nastavení** zvolte **Mobile Threat Defense**.

5. V podokně **Mobile Threat Defense** zvolte **Přidat**.

6. V rozevíracím seznamu **Vyberte konektor Mobile Threat Defense, který chcete nastavit** vyberte své řešení MTD.

    ![Nastavení konektoru MTD v Intune na portálu Azure Portal](./media/enable-mtd-connector-1.png)

7. Povolte možnosti přepínání podle požadavků vaší organizace. Viditelnost možností přepínání se bude lišit v závislosti na partnerovi MTD.

## <a name="mtd-toggle-options"></a>Možnosti přepínání MTD

Podle požadavků organizace se můžete rozhodnout, jaké možnosti přepínání konektoru MTD potřebujete povolit. Tady jsou další podrobnosti:

- **Připojit zařízení s Androidem 4.1 + k [název partnera MTD] for Work MTD**: Pokud povolíte tuto možnost, můžete nechat zařízení se systémem Android 4.1 +, která hlásí bezpečnostní riziko zpět Intune.
  - **Označit jako nedodržující předpisy, pokud nejsou přijata žádná data**: Pokud Intune neobdrží data o zařízení na této platformě od partnera MTD, zvažte, jestli zařízení nedodržuje předpisy.
<br></br>
- **Připojit zařízení s iOS 8.0 + k [název partnera MTD] for Work MTD**: Pokud povolíte tuto možnost, můžete mít zařízení s iOS 8.0 +, která hlásí bezpečnostní riziko zpátky do Intune.
  - **Označit jako nedodržující předpisy, pokud nejsou přijata žádná data**: Pokud Intune neobdrží data o zařízení na této platformě od partnera MTD, zvažte, jestli zařízení nedodržuje předpisy.
<br></br>
- **Povolit synchronizaci aplikací pro zařízení s iOS**: Umožňuje tomuto partnerovi ochrany před mobilními hrozbami žádat o metadata aplikací iOS z Intune, aby je bylo možné použít pro účely analýzy hrozeb.

- **Zablokovat nepodporované verze operačního systému**: Zablokuje, jestli je na zařízení spuštěný operační systém nižší než minimální podporovaná verze.

- **Počet dní, než partner přestane reagovat**: Počet dnů nečinnosti, než Intune považuje za nereagující partnera, protože došlo ke ztrátě připojení. U nereagujících partnerů MTD Intune ignoruje stav dodržování předpisů.

> [!IMPORTANT] 
> Pokud je to možné, doporučujeme přidat a přiřadit aplikace MTD ještě před tím, než vytvoříte dodržování předpisů zařízením a pravidla zásad podmíněného přístupu. To pomáhá zajistit, aby byla aplikace MTD připravená a dostupná pro koncové uživatele, aby mohli získat přístup k e-mailu nebo jiným firemním prostředkům.

> [!TIP]
> Z podokna Mobile Threat Defense se můžete podívat na **Stav připojení** a čas **poslední synchronizace** mezi Intune a partnerem MTD.
