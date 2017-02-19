---
title: "Povolení pravidla ochrany zařízení | Dokumentace Microsoftu"
description: "Povolení pravidla ochrany před mobilními hrozbami v zásadách dodržování předpisů zařízení."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 9f05e516723976dcf6862475dbb78f9dce2913be
ms.openlocfilehash: 08edca426901eda3017bf17dda3b330dd186ce58


---

# <a name="enable-device-threat-protection-rule-in-the-compliance-policy"></a>Povolení pravidla ochrany zařízení před internetovými útoky v zásadách dodržování předpisů

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune s Lookout Mobile Threat Protection umožňuje zjišťovat hrozby a posuzovat rizika na mobilních zařízeních. Můžete vytvořit pravidlo zásad dodržování předpisů, které posuzuje rizika a zjišťuje, jestli je zařízení v souladu s nimi. Pomocí zásad podmíněného přístupu pak můžete zablokovat přístup ke službám podle toho, jestli zařízení dodržuje předpisy.

Požadavky na zásady dodržování předpisů s ochranou zařízení před internetovými útoky Lookout:

- [Nastavení předplatného ochrany zařízení před internetovými útoky ve službě Lookout](set-up-your-subscription-with-lookout-mtp.md)
- [Povolení připojení Lookout v Intune](enable-lookout-mtp-connection-in-intune.md)
- [Konfigurace aplikace Lookout for Work](configure-and-deploy-lookout-for-work-apps.md)

V rámci nastavení ochrany zařízení před internetovými útoky Lookout v [konzole Lookout](https://aad.lookout.com) jste vytvořili zásadu, která klasifikuje různé hrozby jako vysoké, střední nebo nízké. V zásadách dodržování předpisů Intune nastavujete maximální povolené úrovně hrozby.

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



<!--HONumber=Jan17_HO4-->


