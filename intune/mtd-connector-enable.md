---
title: Povolení konektoru Mobile Threat Defense v Microsoft Intune
titleSuffix: Microsoft Intune
description: Povolte konektor mezi vaším partnerem Mobile Threat Defense (MTD) a Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
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
ms.openlocfilehash: b7998eb82b27a7e70d5a77374950e544fd603f6d
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66046283"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Povolení konektoru Mobile Threat Defense v Intune

> [!NOTE] 
> Toto téma se týká všech partnerů ochrany před mobilními hrozbami.

Při nastavení Mobile Threat Defense (MTD) jste v konzole partnera MTD nakonfigurovali zásadu pro klasifikaci hrozeb a vytvořili jste zásadu dodržování předpisů zařízením v Intune. Pokud jste už nakonfigurovali konektor Intune v konzole partnera MTD, můžete teď v Intune povolit připojení MTD.

## <a name="to-enable-the-mtd-connector"></a>Povolení konektoru MTD

1. Přejděte na portál [Azure Portal](https://portal.azure.com) a přihlaste se pomocí svých přihlašovacích údajů k Intune. Po úspěšném přihlášení se zobrazí **řídicí panel Azure**.

2. Na **Řídicím panelu Azure** zvolte v nabídce vlevo **Všechny služby** a potom do filtru textového pole zadejte **Intune**.

3. Zvolte **Intune** a zobrazí se **Řídicí panel Intune**.

4. Na **řídicím panelu Intune** zvolte **Dodržování předpisů zařízením** a potom v části **Nastavení** zvolte **Mobile Threat Defense**.

5. V podokně **Mobile Threat Defense** zvolte **Přidat**.

6. V rozevíracím seznamu **Vyberte konektor Mobile Threat Defense, který chcete nastavit** vyberte své řešení MTD.

    ![Nastavení konektoru MTD v Intune na portálu Azure Portal](./media/enable-mtd-connector-1.png)

7. Povolte možnosti přepínání podle požadavků vaší organizace. Viditelnost možností přepínání se bude lišit v závislosti na partnerovi MTD.

## <a name="mtd-toggle-options"></a>Možnosti přepínání MTD

Podle požadavků organizace se můžete rozhodnout, jaké možnosti přepínání konektoru MTD potřebujete povolit. Tady jsou další podrobnosti:

- **Připojení s Androidem 4.1 + zařízení k [název partnera MTD] for Work MTD**: Když povolíte tuto možnost, můžete mít s Androidem 4.1 + zařízení hlásit bezpečnostní riziko zpět Intune.
    - **Označit jako nedodržující předpisy, pokud neobdrží žádná data**: Pokud Intune údaje o zařízení na této platformě nedostane od partnera MTD, můžete zařízení Považujte za nedodržující předpisy.
<br></br>
- **Připojit zařízení s iOS 8.0 + k [název partnera MTD] for Work MTD**: Když povolíte tuto možnost, můžete mít zařízení se systémem iOS 8.0 + hlásit bezpečnostní riziko zpět Intune.
    - **Označit jako nedodržující předpisy, pokud neobdrží žádná data**: Pokud Intune údaje o zařízení na této platformě nedostane od partnera MTD, můžete zařízení Považujte za nedodržující předpisy.
<br></br>
- **Povolit synchronizaci aplikací pro zařízení se systémem iOS**: Umožňuje tato partnerem Mobile Threat Defense žádat o metadata aplikací pro iOS v Intune používat pro účely analýzy hrozeb.

- **Blokovat nepodporované verze operačního systému**: Blokovat, pokud zařízení používá menší než minimální podporovaná verze operačního systému.

- **Počet dní, než partner přestane reagovat**: Počet dnů neaktivity, než začne Intune považovat partnera za nereagujícího kvůli dojde ke ztrátě připojení. U nereagujících partnerů MTD Intune ignoruje stav dodržování předpisů.

> [!IMPORTANT] 
> Pokud je to možné, doporučujeme přidat a přiřadit aplikace MTD před vytvořením pravidel zásad dodržování předpisů zařízením a podmíněného přístupu. Díky tomu se zajistí, že aplikace MTD bude připravena a koncoví uživatelé nainstalovat, než uživatelé získají přístup k e-mailu a dalším firemním prostředkům.

> [!TIP]
> Z podokna Mobile Threat Defense se můžete podívat na **Stav připojení** a čas **poslední synchronizace** mezi Intune a partnerem MTD.
