---
title: "Omezení přístupu k e-mailu a službám O365 | Microsoft Intune"
description: "Toto téma popisuje, jak lze pomocí podmíněného přístupu povolit přístup k firemnímu e-mailu a firemním datům v SharePoint Online a dalších službách jenom kompatibilním zařízením."
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 06/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c72c8e1a764af73ba4d421ca6637ee91ab7bca0a
ms.openlocfilehash: df430a31e13027c7a342beb90b78d48c74bce9e6


---

# Omezení přístupu k e-mailu, O365 a dalším službám pomocí Microsoft Intune
Pomocí podmíněného přístupu Intune můžete omezit přístup k e-mailu a službám O365. Funkce podmíněného přístupu Intune umožňuje zajistit, aby přístup k e-mailu a službám O365 společnosti byl omezen na zařízení, která vyhovují nastaveným pravidlům.
## Jak podmíněný přístup funguje?
K vyhodnocení stavu kompatibility zařízení se používají nastavení zásad dodržování předpisů. Zásada podmíněného přístupu používá vyhodnocení k omezení nebo povolení přístupu ke konkrétní službě. Pokud se zásada podmíněného přístupu použije v kombinaci se zásadou dodržování předpisů, budou mít přístup povolený jenom zařízení, která vyhovují. Zásada dodržování předpisů a zásada podmíněného přístupu se nasadí pro uživatele. Jakékoli zařízení, které uživatel používá pro přístup ke službám, se kontroluje na dodržování předpisů se zásadami.

Mějte na paměti, že uživatel, který zařízení používá, musí mít nasazenou zásadu dodržování předpisů, aby se u zařízení vyhodnocovala shoda.
Pokud na uživatele nejsou nasazené žádné zásady dodržování předpisů, pak se zařízení považuje za vyhovující a žádná omezení přístupu se neuplatní.

Pokud zařízení nesplňuje podmínky nakonfigurované v zásadách, koncový uživatel je proveden procesem jeho registrace a opravy problému, který tomuto zařízení brání v dodržení předpisů.

Obvyklý průběh podmíněného přístupu:

![Diagram zobrazuje rozhodovací body používané k určení, jestli má zařízení přístup ke službě povolený, nebo blokovaný.](../media/ConditionalAccess4.png)

## Postup konfigurace podmíněného přístupu
Pro správu přístupu k **místnímu systému Microsoft Exchange**, **systému Exchange Online**, **systému Exchange Online Dedicated**, **SharePointu Online** a **Online Skypu pro firmy** použijte podmíněný přístup.

Abyste mohli nastavit podmíněný přístup, nakonfigurujte pro zařízení zásadu dodržování předpisů a zásadu podmíněného přístupu.

Zásada dodržování předpisů zahrnuje nastavení, jako je heslo, šifrování a to, jestli má zařízení jailbreak. Zařízení musí tyto pravidla splňovat, aby mohlo být považované za vyhovující.

Můžete nastavit zásadu podmíněného přístupu, abyste omezili přístup, na základě těchto položek:
- Stav dodržování předpisů pro zařízení
- Platforma spuštěná v zařízení
- Typ aplikace použitý pro přístup ke službám

Na rozdíl od jiných zásad služby Intune zásady podmíněného přístupu nenasazujete. Po nakonfigurování zásady a výběru uživatelů, kteří by měli mít zásadu, se zásada použije na všechny cílové uživatele. Pokud je uživatel cílem zásady, musí každé jím používané zařízení splňovat zásady, aby měl přístup k prostředkům.


## Další kroky
1. [Další informace o zásadě dodržování předpisů pro zařízení a její funkci ](introduction-to-device-compliance-policies-in-microsoft-intune.md)

2. [Tvorba zásady dodržování předpisů](create-a-device-compliance-policy-in-microsoft-intune.md)

2.  Vytvořte zásadu podmíněného přístupu pro jednu z následujících možností:
> [!div class="op_single_selector"]
  - [Vytvoření zásady podmíněného přístupu pro Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro místní Exchange](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro novou verzi Exchange Online Dedicated](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro starší verzi Exchange Online Dedicated](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro Online Skype pro firmy](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [Vytvoření zásad podmíněného přístupu pro Dynamic CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


