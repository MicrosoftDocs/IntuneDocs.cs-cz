---
title: Povolení konektoru Mobile Threat Defense v Microsoft Intune
titleSuffix: ''
description: Povolte konektor mezi vaším partnerem Mobile Threat Defense (MTD) a Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e2172c1cd066e99f3634dd856538671207cf1ed0
ms.sourcegitcommit: fffa64f28278573dc83a846b647315def2108781
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2018
ms.locfileid: "48232235"
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
> Před vytvořením pravidel zásad dodržování předpisů zařízení a podmíněného přístupu musíte přidat a přiřadit aplikace MTD. Tím zajistíte, že aplikace MTD bude připravena a koncoví uživatelé ji budou moci nainstalovat a získat tak přístup k e-mailu a dalším firemním prostředkům.

> [!TIP]
> Z podokna Mobile Threat Defense se můžete podívat na **Stav připojení** a čas **poslední synchronizace** mezi Intune a partnerem MTD.
