---
title: "Vytvoření zásad dodržování předpisů pro ochranu před mobilními hrozbami Skycure"
description: "Zásady dodržování předpisů pro ochranu před mobilními hrozbami Skycure se vytvářejí na klasickém portálu Intune."
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
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ea45ac89064756f4b8ebd8ca9d163a151b6e6cc2
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2018
---
# <a name="create-skycure-mobile-threat-defense-compliance-policy"></a>Vytvoření zásad dodržování předpisů pro ochranu před mobilními hrozbami Skycure

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Služba Intune s ochranou před mobilními hrozbami Skycure umožňuje zjišťovat hrozby a posuzovat rizika na mobilních zařízeních. Můžete vytvořit pravidlo zásad dodržování předpisů služby Intune, které posuzuje rizika a zjišťuje, jestli je zařízení v souladu s nimi. Pomocí zásad podmíněného přístupu pak můžete zablokovat přístup ke službám podle toho, jestli zařízení dodržuje předpisy.

## <a name="before-you-begin"></a>Před zahájením

Požadavky na zásady dodržování předpisů u ochrany zařízení před hrozbami Skycure:

-   [Nastavení integrace služby Skycure se službou Intune](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

-   [Povolení připojení služby Skycure ve službě Intune](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

V rámci nastavení ochrany před mobilními hrozbami Skycure jste v konzole Skycure vytvořili zásadu, která klasifikuje různé hrozby jako vysoké, střední nebo nízké. V zásadách dodržování předpisů služby Intune je teď potřeba nastavit maximální povolenou úroveň hrozby.

## <a name="to-create-skycure-compliance-policy"></a>Postup vytvoření zásad dodržování předpisů služby Skycure

1.  Přejděte na [klasický portál Intune](https://manage.microsoft.com/) a zadejte své přihlašovací údaje.

2.  Zvolte **Předpisy** &gt; **Zásady dodržování předpisů**. Můžete použít stávající zásady dodržování předpisů, nebo vytvořit nové.

3.  Zvolte **Přidat** &gt; **Stav zařízení** a potom povolte možnost **Ochrana zařízení před hrozbami**.

4.  Vyberte **maximální povolenou úroveň ohrožení:**

    a.  **Žádná (zabezpečeno):** Toto je nejbezpečnější úroveň. Zařízení nemůže přistupovat k prostředkům společnosti, pokud je vystavené nějakým hrozbám. Pokud se najde jakákoli hrozba, zařízení se vyhodnotí jako nevyhovující.

    b.  **Nízká:** Zařízení se vyhodnotí jako vyhovující i v případě, že se v něm nachází jenom hrozby nízké úrovně. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.

    c.  **Střední:** Zařízení vyhovuje, pokud se v něm přítomné hrozby pohybují na střední nebo nízké úrovni. Pokud se v zařízení zjistí hrozby vysoké úrovně, vyhodnotí se jako nevyhovující.

    d.  **Vysoká**: Jedná se o nejméně bezpečnou možnost. Tato možnost povoluje všechny úrovně hrozeb a používá ochranu před mobilními hrozbami Skycure jenom pro účely generování sestav.

> [!IMPORTANT]
> Pokud vytvoříte zásady podmíněného přístupu pro Office 365 nebo jiné služby, posoudí se toto vyhodnocení dodržování předpisů. Nevyhovujícím zařízením se zablokuje přístup k prostředkům společnosti, dokud se hrozby nevyřeší.

## <a name="span-idmonitor-device-threats-classanchorspan-idnext-steps-classanchorspan-idtoc477360344-classanchorspanspanspannext-steps"></a><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>Další kroky

-   Vytvoření zásad podmíněného přístupu pro:

    -   [Exchange Online](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
    -   [Místní Exchange](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
    -   [SharePoint Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)
    -   [Online Skype pro firmy](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)
    -   [Dynamics CRM](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)
