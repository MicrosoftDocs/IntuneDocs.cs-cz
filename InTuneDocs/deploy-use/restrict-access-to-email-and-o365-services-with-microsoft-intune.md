---
title: "Omezení přístupu k e-mailu a službám Office 365 | Microsoft Intune"
description: "Toto téma popisuje, jak můžete pomocí podmíněného přístupu povolit přístup k podnikovému e-mailu, podnikovým datům na SharePointu Online a k dalším službám jenom kompatibilním zařízením."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 3a58e075813fac6a37ec8f82a39e44a856ef1cce


---

# <a name="restrict-access-to-email-office-365-and-other-services-with-microsoft-intune"></a>Omezení přístupu k e-mailu, Office 365 a dalším službám pomocí Microsoft Intune
Pomocí podmíněného přístupu v Intune můžete omezit přístup k podnikovému e-mailu, k Office 365 a k dalším službám. Funkce podmíněného přístupu v Intune umožňuje zajistit, aby byl přístup k podnikovému e-mailu a službám Office 365 omezen na zařízení, která vyhovují nastaveným pravidlům.
## <a name="how-does-conditional-access-work"></a>Jak podmíněný přístup funguje?
K vyhodnocení, jestli zařízení vyhovuje, můžete použít nastavení zásady dodržování předpisů. Zásada podmíněného přístupu používá vyhodnocení k omezení nebo povolení přístupu ke konkrétní službě. Pokud zásadu podmíněného přístupu použijete v kombinaci se zásadou dodržování předpisů, budou mít přístup ke službě povolen jenom ta zařízení, která vyhovují. Zásada dodržování předpisů a zásada podmíněného přístupu se nasadí pro uživatele. Jakékoli zařízení, které uživatel používá pro přístup ke službám, se kontroluje na dodržování předpisů se zásadami.

Nezapomeňte, že uživatel, který zařízení používá, musí mít nasazenou zásadu dodržování předpisů, aby se vyhodnocovalo, jestli zařízení vyhovuje.
Pokud nejsou pro uživatele nasazené žádné zásady dodržování předpisů, pak se zařízení považuje za vyhovující a žádná omezení přístupu se neuplatní.

Pokud zařízení nesplňuje podmínky nastavené v zásadách, je koncový uživatel proveden procesem registrace zařízení a opravy problému, který tomuto zařízení brání v dodržení předpisů.

Obvyklý průběh podmíněného přístupu:

![Diagram znázorňující rozhodovací body, které určují, jestli má mít zařízení přístup ke službě povolený, nebo blokovaný](../media/ConditionalAccess4.png)

## <a name="how-to-configure-conditional-access"></a>Postup konfigurace podmíněného přístupu
Pro správu přístupu k **místnímu systému Microsoft Exchange**, **Exchange Online**, **Exchange Online Dedicated**, **SharePointu Online** a **Online Skypu pro firmy** použijte podmíněný přístup.

Pokud chcete nastavit podmíněný přístup, nakonfigurujte pro zařízení zásadu dodržování předpisů a zásadu podmíněného přístupu.

Zásada dodržování předpisů zahrnuje nastavení, jako je heslo, šifrování a to, jestli má zařízení jailbreak. Zařízení musí tyto pravidla splňovat, aby mohlo být považované za vyhovující.

Můžete nastavit zásadu podmíněného přístupu, abyste omezili přístup, na základě těchto položek:
- Stav dodržování předpisů pro zařízení
- Platforma spuštěná v zařízení
- Typ aplikací, které přistupují ke službám

Na rozdíl od jiných zásad služby Intune se zásady podmíněného přístupu nenasazují. Po nakonfigurování zásady a výběru uživatelů, kteří by měli mít tuto zásadu nastavenou, se zásada použije pro všechny cílové uživatele. Pokud je uživatel cílem zásady, musí každé jím používané zařízení vyhovovat, aby měl přístup k prostředkům.


## <a name="next-steps"></a>Další kroky
1. [Přečtěte si další informace o zásadě dodržování předpisů pro zařízení a její funkci](introduction-to-device-compliance-policies-in-microsoft-intune.md).

2. [Vytvořte zásadu dodržování předpisů](create-a-device-compliance-policy-in-microsoft-intune.md).

2.  Vytvořte zásadu podmíněného přístupu pro jednu z následujících možností:
> [!div class="op_single_selector"]
  - [Vytvoření zásady podmíněného přístupu pro Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro místní Exchange](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro novou verzi Exchange Online Dedicated](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro starší verzi Exchange Online Dedicated](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro Online Skype pro firmy](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro Dynamic CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Nov16_HO4-->


