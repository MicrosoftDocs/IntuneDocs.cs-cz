---
title: Povolení konektoru Mobile Threat Defense v Microsoft Intune | Microsoft Intune
description: Povolte konektor mezi vaším partnerem Mobile Threat Defense (MTD) a Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/27/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1f4e920719b26cf90292a927a129b4fae2b17b45
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57394021"
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
> Před vytvořením pravidel zásad dodržování předpisů zařízení a podmíněného přístupu musíte přidat a přiřadit aplikace MTD. Tím zajistíte, že aplikace MTD bude připravena a koncoví uživatelé ji budou moci nainstalovat a získat tak přístup k e-mailu a dalším firemním prostředkům.

> [!TIP]
> Z podokna Mobile Threat Defense se můžete podívat na **Stav připojení** a čas **poslední synchronizace** mezi Intune a partnerem MTD.
