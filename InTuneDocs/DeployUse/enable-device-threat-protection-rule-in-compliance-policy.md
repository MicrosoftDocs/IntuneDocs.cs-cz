---
title: "Povolení pravidla ochrany zařízení v zásadách dodržování předpisů | Microsoft Intune"
description: "Povolení pravidla ochrany před mobilními hrozbami v zásadách dodržování předpisů zařízení."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fa05027e1785bb27a607aa9e31b685107a84f63f
ms.openlocfilehash: 3de68238515a2584b6f1a5785e13688097468415


---

# Povolení pravidla ochrany zařízení před internetovými útoky v zásadách dodržování předpisů
Intune vám s ochranou Lookout proti mobilním hrozbám umožňuje v zařízení detekovat mobilní hrozby a provádět posouzení rizik. Můžete vytvořit pravidla zásad dodržování předpisů a posouzením rizik zjistit, jestli je zařízení s nimi v souladu. Pomocí zásad podmíněného přístupu pak můžete povolit nebo blokovat přístup k Exchangi, SharePointu a dalším službám podle toho, nakolik zařízení zásady splňuje nebo nesplňuje.

Nastavení detekce hrozeb Lookout MTP, aby ovlivňovala zásady dodržování předpisů pro zařízení:

* V zásadách dodržování předpisů musí být povoleno pravidlo **Ochrana zařízení před internetovými útoky**.

* Na stránce **Stav Lookoutu** v **konzole správce Intune** se musí zobrazovat stav **Aktivní**. Další podrobnosti a pokyny k tomu, jak aktivovat integraci Lookout, naleznete v tématu [Povolení připojení Lookout MTP v Intune](enable-lookout-mtp-connection-in-intune.md).


Před vytvořením pravidla ochrany zařízení před internetovými útoky v zásadách dodržování předpisů doporučujeme [nastavit předplatné pro službu Lookout MTP](set-up-your-subscription-with-lookout-mtp.md), [povolit připojení Lookout v Intune](enable-lookout-mtp-connection-in-intune.md) a [nakonfigurovat aplikaci Lookout for Work](configure-and-deploy-lookout-for-work-apps.md). Pravidlo dodržování předpisů bude vynucováno až po dokončení nastavení.

Pokud chcete aktivovat pravidlo ochrany zařízení před internetovými útoky, můžete použít stávající zásady dodržování předpisů nebo vytvořit novou zásadu.

V rámci nastavení Lookout MTP v [konzole Lookout MTP](https://aad.lookout.com) jste vytvořili zásadu, která rozděluje různé hrozby na vysokou, střední a nízkou úroveň. V zásadách dodržování předpisů Intune využijete úroveň hrozby k nastavení maximální povolené úrovně hrozby.

Na stránce **zásad dodržování předpisů** v **konzole správce Intune** přejděte do části **Stav zařízení** a přepnutím tlačítka povolte pravidlo **Ochrana zařízení před internetovými útoky**. Potom vyberte maximální povolenou úroveň hrozeb, což je jedna z následujících:
* **Žádná (zabezpečeno)**: Toto je nejbezpečnější úroveň.  To znamená, že zařízení nesmí obsahovat žádné hrozby.  Pokud je nalezena jakákoli úroveň hrozeb, je zařízení vyhodnoceno jako nevyhovující.  
* **Nízká:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm nachází i jen nízká úroveň hrozeb. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
* **Střední:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm přítomné hrozby pohybují na střední nebo nízké úrovni. Pokud budou v zařízení zjištěny hrozby vysoké úrovně, bude vyhodnoceno jako nevyhovující.
* **Vysoká**: Jedná se o nejméně bezpečnou možnost. V podstatě povoluje všechny úrovně hrozeb. Toto řešení může být užitečné prakticky jen pro účely nahlašování.

![snímek obrazovky zobrazující nastavení pravidla ochrany zařízení před hrozbami ](../media/mtp/mtp-compliance-policy-rule.png)

![snímek obrazovky zobrazující možnost úrovně hrozeb pro nastavení pravidla ochrany zařízení před internetovými útoky](../media/mtp/mtp-compliance-policy-setting.png)

Pokud vytvoříte zásady podmíněného přístupu pro O365 a další služby, použije se výše uvedené vyhodnocení v souladu s těmito zásadami. Nevyhovujícím zařízením bude zablokován přístup k prostředkům společnosti, dokud se hrozby nevyřeší.

Stav dodržování předpisů zařízení naleznete na stránce**Všechna zařízení** v **konzole správce Intune**.

![snímek stránky zařízení v konzole pro správu Intune zobrazující stav dodržování předpisů zařízení](../media/mtp/mtp-device-status-intune-console.png)

## Další kroky
* Vytvoření zásad podmíněného přístupu
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [místnímu systému Microsoft Exchange](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Online Skype pro firmy](restrict-access-to-skype-for-business-online-with-microsoft-intune,md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Sep16_HO3-->


