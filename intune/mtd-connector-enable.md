---
title: "Povolení konektoru Mobile Threat Defense s Intune"
titleSuffix: Intune on Azure
description: "Povolení konektoru Mobile Threat Defense v Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a5dfef35c9f2d2fa543d8b19c2566b25d47b8f72
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/10/2017
---
# <a name="enable-mobile-threat-defense-in-intune"></a>Povolení služby Mobile Threat Defense v Intune

> [!NOTE] 
> Toto téma se týká všech partnerů ochrany před mobilními hrozbami.

Pokud chcete v Intune povolit připojení ochrany před mobilními hrozbami (MTD), měli byste nakonfigurovat konektor Intune v konzole řešení MTD.

## <a name="to-enable-the-mtd-connector"></a>Povolení konektoru MTD

1. Přejděte na portál [Azure Portal](https://portal.azure.com) a přihlaste se pomocí svých přihlašovacích údajů k Intune. Po úspěšném přihlášení se zobrazí **řídicí panel Azure**.

2. Na **řídicím panelu Azure** zvolte v nabídce vlevo **Další služby** a do filtru textového pole zadejte **Intune**.

3. Zvolte **Intune** a zobrazí se **řídicí panel Intune**.

4. Na **řídicím panelu Intune** zvolte **Dodržování předpisů zařízením** a potom v části **Nastavení** zvolte **Mobile Threat Defense**.

5. V okně **Mobile Threat Defense** zvolte **Přidat**.

6. V rozevíracím seznamu **Vyberte konektor Mobile Threat Defense, který chcete nastavit** vyberte své řešení MTD.

    ![Nastavení konektoru MTD v Intune na portálu Azure Portal](./media/enable-mtd-connector-1.png)

7. Povolte možnosti přepínání podle požadavků vaší organizace.

## <a name="mtd-toggle-options"></a>Možnosti přepínání MTD

Podle požadavků organizace se můžete rozhodnout, jaké možnosti přepínání konektoru MTD potřebujete povolit. Tady jsou další podrobnosti:

- **Připojit zařízení s Androidem 4.1+ k [název partnera MTD] for Work MTD**: Když tuto možnost povolíte, mohou zařízení se systémem Android verze 4.1 a vyšší hlásit bezpečnostní riziko zpět Intune.
    - **Při nepřijetí dat označit jako nedodržující předpisy**: Pokud Intune na této platformě nedostane od partnera MTD údaje o zařízení, můžete zařízení považovat za nevyhovující.
<br></br>
- **Připojit zařízení s iOS 8.0+ k [název partnera MTD] for Work MTD**: Když tuto možnost povolíte, mohou zařízení se systémem iOS verze 8.0 a vyšší hlásit bezpečnostní riziko zpět Intune.
    - **Při nepřijetí dat označit jako nedodržující předpisy**: Pokud Intune na této platformě nedostane od partnera MTD údaje o zařízení, můžete zařízení považovat za nevyhovující.
<br></br>
- **Blokovat nepodporované verze operačního systému**: Blokovat zařízení, pokud je na něm spuštěn operační systém nižší verze, než je minimálně podporovaná.

- **Počet dnů, než partner přestane reagovat**: Počet dnů nečinnosti, než bude Intune kvůli ztrátě připojení považovat partnera za nereagujícího. U nereagujících partnerů MTD Intune ignoruje stav dodržování předpisů.

> [!IMPORTANT] 
> Před vytvořením pravidel zásad dodržování předpisů zařízení a podmíněného přístupu musíte přidat a přiřadit aplikace MTD. Tím zajistíte, že aplikace MTD bude připravena a koncoví uživatelé ji budou moci nainstalovat a získat tak přístup k e-mailu a dalším firemním prostředkům.

> [!TIP]
> Z okna Mobile Threat Defense se můžete podívat na **Stav připojení** a čas **poslední synchronizace** mezi Intune a partnerem MTD.

## <a name="next-steps"></a>Další kroky

[Vytvoření zásad dodržování předpisů pro ochranu zařízení před mobilními hrozbami v Intune](mtd-device-compliance-policy-create.md)
