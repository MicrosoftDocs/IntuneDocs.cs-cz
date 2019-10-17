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
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e53f50c42e768eeb652a8602bea49c04d29364c7
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504426"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Povolení konektoru Mobile Threat Defense v Intune

> [!NOTE] 
> Toto téma se týká všech partnerů ochrany před mobilními hrozbami.

Při nastavení Mobile Threat Defense (MTD) jste v konzole partnera MTD nakonfigurovali zásadu pro klasifikaci hrozeb a vytvořili jste zásadu dodržování předpisů zařízením v Intune. Pokud jste už konektor Intune nakonfigurovali v konzole pro partnery MTD, můžete teď povolit připojení MTD pro partnerské aplikace MTD.

Když integrujete novou aplikaci do ochrany před mobilními hrozbami Intune a povolíte připojení k Intune, vytvoří Intune v Azure Active Directory zásady klasického podmíněného přístupu. Každá aplikace MTD, kterou integrujete, včetně [ATP ATP](advanced-threat-protection.md) nebo kteréhokoli z našich dalších [partnerů MTD](mobile-threat-defense.md#mobile-threat-defense-partners), vytvoří nové zásady podmíněného přístupu v klasickém rozhraní. Tyto zásady je možné ignorovat, ale neměly by být upravované, odstraňující ani zakázané.

Klasické zásady podmíněného přístupu pro aplikace MTD: 

- Používají Intune MTD k tomu, aby vyžadovaly, aby byla zařízení zaregistrovaná ve službě Azure AD, aby měla ID zařízení před komunikací s partnery MTD. IDENTIFIKÁTOR je povinný, aby zařízení a mohl úspěšně ohlásit svůj stav do Intune.  
- Nemusíte mít žádný vliv na žádné jiné cloudové aplikace ani prostředky.  
- Liší se od zásad podmíněného přístupu, které byste mohli vytvořit, abyste mohli lépe spravovat MTD.
- Ve výchozím nastavení nekomunikujete s dalšími zásadami podmíněného přístupu, které používáte pro vyhodnocení.  

Pokud chcete zobrazit klasické zásady podmíněného přístupu, přejděte v [Azure](https://portal.azure.com/#home)na **Azure Active Directory** > **podmíněný přístup** > **Classic**.


## <a name="to-enable-the-mtd-connector"></a>Povolení konektoru MTD

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

4. Na **řídicím panelu Intune** zvolte **Dodržování předpisů zařízením** a potom v části **Nastavení** zvolte **Mobile Threat Defense**.

5. V podokně **Mobile Threat Defense** zvolte **Přidat**.

6. V rozevíracím seznamu **Vyberte konektor Mobile Threat Defense, který chcete nastavit** vyberte své řešení MTD.

    ![Nastavení konektoru MTD v Intune na portálu Azure Portal](./media/mtd-connector-enable/enable-mtd-connector-1.png)

7. Povolte možnosti přepínání podle požadavků vaší organizace. Viditelnost možností přepínání se bude lišit v závislosti na partnerovi MTD.

## <a name="mtd-toggle-options"></a>Možnosti přepínání MTD

Podle požadavků organizace se můžete rozhodnout, jaké možnosti přepínání konektoru MTD potřebujete povolit. Tady jsou další podrobnosti:

- **Připojit zařízení s Androidem 4.1+ k [název partnera MTD] for Work MTD**: Když tuto možnost povolíte, mohou zařízení se systémem Android verze 4.1 a vyšší hlásit bezpečnostní riziko zpět Intune.
  - **Při nepřijetí dat označit jako nedodržující předpisy**: Pokud Intune na této platformě nedostane od partnera MTD údaje o zařízení, můžete zařízení považovat za nevyhovující.
<br></br>
- **Připojit zařízení s iOSem 8.0+ k [název partnera MTD] for Work MTD**: Když tuto možnost povolíte, mohou zařízení se systémem iOS verze 8.0 a vyšší hlásit bezpečnostní riziko zpět Intune.
  - **Při nepřijetí dat označit jako nedodržující předpisy**: Pokud Intune na této platformě nedostane od partnera MTD údaje o zařízení, můžete zařízení považovat za nevyhovující.
<br></br>
- **Povolit synchronizaci aplikací pro zařízení iOS**: Povolí tomuto partnerovi Ochrany před mobilními hrozbami žádat o metadata aplikací pro iOS z Intune, která se použijí pro účely analýzy hrozeb.

- **Blokovat nepodporované verze operačního systému**: Blokovat zařízení, pokud je na něm spuštěn operační systém nižší verze, než je minimálně podporovaná.

- **Počet dnů, než partner přestane reagovat**: Počet dnů nečinnosti, než bude Intune kvůli ztrátě připojení považovat partnera za nereagujícího. U nereagujících partnerů MTD Intune ignoruje stav dodržování předpisů.

> [!IMPORTANT] 
> Pokud je to možné, doporučujeme přidat a přiřadit aplikace MTD ještě před tím, než vytvoříte dodržování předpisů zařízením a pravidla zásad podmíněného přístupu. To pomáhá zajistit, aby byla aplikace MTD připravená a dostupná pro koncové uživatele, aby mohli získat přístup k e-mailu nebo jiným firemním prostředkům.

> [!TIP]
> Z podokna Mobile Threat Defense se můžete podívat na **Stav připojení** a čas **poslední synchronizace** mezi Intune a partnerem MTD.
