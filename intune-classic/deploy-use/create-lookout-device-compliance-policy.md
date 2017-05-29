---
title: "Povolení pravidla ochrany zařízení | Dokumentace Microsoftu"
description: "Povolení pravidla ochrany před mobilními hrozbami v zásadách dodržování předpisů zařízení."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 67913bfcbca3cef52e309ad86bfe722db6e16895
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="create-lookout-device-compliance-policy-in-intune"></a>Vytváření zásad dodržování předpisů zařízení pro Lookout ve službě Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Služba Intune s ochranou před mobilními hrozbami Lookout umožňuje zjišťovat hrozby a posuzovat rizika na mobilních zařízeních. Můžete vytvořit pravidlo zásad dodržování předpisů, které posuzuje rizika a zjišťuje, jestli je zařízení v souladu s nimi. Pomocí zásad podmíněného přístupu pak můžete zablokovat přístup ke službám podle toho, jestli zařízení dodržuje předpisy.

Požadavky na zásady dodržování předpisů s ochranou zařízení před mobilními hrozbami Lookout:

- [Nastavení předplatného ochrany před mobilními hrozbami Lookout](setup-your-lookout-mtd-subscription.md)
- [Povolení připojení Lookout v Intune](enable-lookout-mtd-connection.md)
- [Konfigurace a nasazení aplikace Lookout for Work](configure-deploy-lookout-for-work-app.md)

V rámci nastavení ochrany před mobilními hrozbami Lookout jste v [konzole Lookout](https://aad.lookout.com) vytvořili zásadu, která klasifikuje různé hrozby jako vysoké, střední nebo nízké. V zásadách dodržování předpisů Intune nastavujete maximální povolené úrovně hrozby.

1. V [konzole správce Intune](https://manage.microsoft.com) přejděte na stránku **Zásady dodržování předpisů**. Můžete použít stávající zásady dodržování předpisů, nebo vytvořit nové. Přejděte na **Stav zařízení** a povolte možnost **Ochrana zařízení před internetovými útoky**.
  ![snímek obrazovky zobrazující nastavení pravidla ochrany zařízení před hrozbami](../media/mtp/mtp-compliance-policy-rule.png)

2. Vyberte **maximální povolenou úroveň ohrožení:**
  * **Žádná (zabezpečeno):** Toto je nejbezpečnější úroveň.  Zařízení nemůže přistupovat k prostředkům společnosti, pokud je vystavené nějakým hrozbám.  Pokud se najde jakákoli hrozba, zařízení se vyhodnotí jako nevyhovující.  
  * **Nízká:** Zařízení se vyhodnotí jako vyhovující i v případě, že se v něm nachází jenom hrozby nízké úrovně. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  * **Střední:** Zařízení vyhovuje, pokud se v něm přítomné hrozby pohybují na střední nebo nízké úrovni. Pokud budou v zařízení zjištěny hrozby vysoké úrovně, bude vyhodnoceno jako nevyhovující.
  * **Vysoká**: Jedná se o nejméně bezpečnou možnost. Tato možnost povoluje všechny úrovně hrozeb a používá Lookout Mobile Threat Protection jenom pro účely generování sestav.

![snímek obrazovky zobrazující možnost úrovně hrozeb pro nastavení pravidla ochrany zařízení před internetovými útoky](../media/mtp/mtp-compliance-policy-setting.png)

Pokud vytvoříte zásady podmíněného přístupu pro Office 365 nebo jiné služby, posoudí se toto vyhodnocení dodržování předpisů. Nevyhovujícím zařízením se zablokuje přístup k prostředkům společnosti, dokud se hrozby nevyřeší.

## <a name="monitor-device-threats"></a>Monitorování hrozeb zařízení
Pokud si chcete zobrazit stav dodržování předpisů zařízení, přejděte na [konzolu správce Intune](https://manage.microsoft.com) a zobrazte si **Všechna zařízení**.

![snímek stránky zařízení v konzole pro správu Intune zobrazující stav dodržování předpisů zařízení](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a>Další kroky
* Vytvoření zásad podmíněného přístupu
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Místní Exchange](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Online Skype pro firmy](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)

