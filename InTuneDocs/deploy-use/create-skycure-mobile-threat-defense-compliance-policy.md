---
title: "Vytvoření zásad dodržování předpisů pro ochranu před mobilními hrozbami Skycure | Dokumentace Microsoftu"
description: "Vytvořte zásady dodržování předpisů pro ochranu před mobilními hrozbami Skycure v klasické konzole služby Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 56ff1728-1119-4e8a-aae6-ed5c7fafa052
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: c28ba63136c1037c8c8191e9a7f46fa9a4823b4e
ms.lasthandoff: 04/25/2017


---

# <a name="create-skycure-mobile-threat-defense-compliance-policy"></a>Vytvoření zásad dodržování předpisů pro ochranu před mobilními hrozbami Skycure

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Služba Intune s ochranou před mobilními hrozbami Skycure umožňuje zjišťovat hrozby a posuzovat rizika na mobilních zařízeních. Můžete vytvořit pravidlo zásad dodržování předpisů služby Intune, které posuzuje rizika a zjišťuje, jestli je zařízení v souladu s nimi. Pomocí zásad podmíněného přístupu pak můžete zablokovat přístup ke službám podle toho, jestli zařízení dodržuje předpisy.

## <a name="before-you-begin"></a>Před zahájením

Požadavky na zásady dodržování předpisů u ochrany zařízení před hrozbami Skycure:

-   [Nastavení integrace služby Skycure se službou Intune](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune)

-   [Povolení připojení služby Skycure ve službě Intune](https://docs.microsoft.com/intune/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

V rámci nastavení ochrany před mobilními hrozbami Skycure jste v konzole Skycure vytvořili zásadu, která klasifikuje různé hrozby jako vysoké, střední nebo nízké. V zásadách dodržování předpisů služby Intune je teď potřeba nastavit maximální povolenou úroveň hrozby.

## <a name="to-create-skycure-compliance-policy"></a>Postup vytvoření zásad dodržování předpisů služby Skycure

1.  Přejděte na stránku [klasické konzoly Intune](https://manage.microsoft.com/) a zadejte své přihlašovací údaje.

2.  Zvolte **Předpisy** &gt; **Zásady dodržování předpisů**. Můžete použít stávající zásady dodržování předpisů, nebo vytvořit nové.

3.  Zvolte **Přidat** &gt; **Stav zařízení** a potom povolte možnost **Ochrana zařízení před hrozbami**.

4.  Vyberte **maximální povolenou úroveň ohrožení:**

    a.  **Žádná (zabezpečeno):** Toto je nejbezpečnější úroveň. Zařízení nemůže přistupovat k prostředkům společnosti, pokud je vystavené nějakým hrozbám. Pokud se najde jakákoli hrozba, zařízení se vyhodnotí jako nevyhovující.

    b.  **Nízká:** Zařízení se vyhodnotí jako vyhovující i v případě, že se v něm nachází jenom hrozby nízké úrovně. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.

    c.  **Střední:** Zařízení vyhovuje, pokud se v něm přítomné hrozby pohybují na střední nebo nízké úrovni. Pokud budou v zařízení zjištěny hrozby vysoké úrovně, bude vyhodnoceno jako nevyhovující.

    d.  **Vysoká**: Jedná se o nejméně bezpečnou možnost. Tato možnost povoluje všechny úrovně hrozeb a používá ochranu před mobilními hrozbami Skycure jenom pro účely generování sestav.

> [!IMPORTANT]
> Pokud vytvoříte zásady podmíněného přístupu pro Office 365 nebo jiné služby, posoudí se toto vyhodnocení dodržování předpisů. Nevyhovujícím zařízením se zablokuje přístup k prostředkům společnosti, dokud se hrozby nevyřeší.

## <a name="span-idmonitor-device-threats-classanchorspan-idnext-steps-classanchorspan-idtoc477360344-classanchorspanspanspannext-steps"></a><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>Další kroky

-   Vytvoření zásad podmíněného přístupu pro:

    -   [Exchange Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
    -   [Místní Exchange](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
    -   [SharePoint Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)
    -   [Online Skype pro firmy](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)
    -   [Dynamics CRM](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

