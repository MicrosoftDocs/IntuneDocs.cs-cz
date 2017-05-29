---
title: Ochrana e-mailu a Office 365 | Dokumentace Microsoftu
description: "Toto téma popisuje, jak můžete pomocí podmíněného přístupu povolit přístup k podnikovému e-mailu, podnikovým datům na SharePointu Online a k dalším službám jenom kompatibilním zařízením."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: fc89c1b5b502f00bab5ed02f6e7df6422241aeb1
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="protect-access-to-email-office-365-and-other-services-with-microsoft-intune"></a>Ochrana přístupu k e-mailu, Office 365 a dalším službám pomocí Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pomocí řešení pro podmíněný přístup Enterprise Mobility + Security (EMS) můžete chránit přístup k podnikovému e-mailu, službám Office 365, jako jsou **místní Exchange**, **Exchange Online**, **Exchange Online Dedicated**, **SharePoint Online** nebo **Online Skype pro firmy**, a k dalším službám. Tato funkce umožňuje zajistit, aby se přístup k podnikovému e-mailu a službám Office 365 omezil na zařízení vyhovující pravidlům podmíněného přístupu, která jste nastavili v konzole správce služby Intune nebo na portálu Azure Classic.
## <a name="how-does-conditional-access-work"></a>Jak podmíněný přístup funguje?
K vyhodnocení, jestli zařízení vyhovuje, můžete použít nastavení zásady dodržování předpisů. Zásada podmíněného přístupu používá vyhodnocení k omezení nebo povolení přístupu ke konkrétní službě. Když zásady podmíněného přístupu použijete v kombinaci se zásadami dodržování předpisů pro zařízení, povolí se přístup ke službě jenom vyhovujícím zařízením. Zásada dodržování předpisů a zásada podmíněného přístupu se nasadí pro uživatele. Jakékoli zařízení, které uživatel používá pro přístup ke službám, se kontroluje na dodržování předpisů se zásadami.

> [!IMPORTANT]
> Nezapomeňte, že uživatel, který zařízení používá, musí mít nasazenou zásadu dodržování předpisů, aby se vyhodnocovalo, jestli zařízení vyhovuje.
> Pokud nejsou pro uživatele nasazené žádné zásady dodržování předpisů, pak se zařízení považuje za vyhovující a žádná omezení přístupu se neuplatní.

Pokud zařízení nesplňuje podmínky nastavené v zásadách, je koncový uživatel proveden procesem registrace zařízení a opravy problému, který tomuto zařízení brání v dodržení předpisů.

Obvyklý průběh podmíněného přístupu:

![Diagram znázorňující rozhodovací body, které určují, jestli má mít zařízení přístup ke službě povolený, nebo blokovaný](../media/ConditionalAccess4.png)

## <a name="setup-considerations"></a>Co je třeba zvážit při nastavení

### <a name="licensing"></a>Správa licencí

Microsoft Intune a Azure Active Directory (Azure AD) Premium hladce spolupracují a poskytují několik úrovní kontroly prostřednictvím podmíněného přístupu EMS. Pokud chcete nasadit zásady podmíněného přístupu v Intune, je nutné mít licenci pro oba produkty.

**Licence Azure AD Premium** lze zakoupit jako samostatnou službu nebo (společně s Intune) v rámci smlouvy na řešení Enterprise. Pokud jste nasadili zásady podmíněného přístupu v Intune, ujistěte se, jestli máte správné **licence pro EMS** nebo Azure AD Premium.

- Další informace najdete na [stránce s cenami služby Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) nebo na [stránce s cenami služby Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

Dále ověřte, jestli uživatelé, kteří mají zásady podmíněného přístupu používat, mají [přiřazené licence Azure AD Premium nebo EMS](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4.md).

### <a name="device-compliance-settings"></a>Nastavení dodržování předpisů pro zařízení

Pokud chcete nastavit podmíněný přístup, nakonfigurujte pro zařízení zásadu dodržování předpisů a zásadu podmíněného přístupu. Zásada dodržování předpisů zahrnuje nastavení, jako je heslo, šifrování a to, jestli má zařízení jailbreak. Zařízení musí tyto pravidla splňovat, aby mohlo být považované za vyhovující.

- Přečtěte si další informace o [zásadách dodržování předpisů pro zařízení a jejich funkci](introduction-to-device-compliance-policies-in-microsoft-intune.md).

### <a name="conditional-access-policy"></a>Zásady podmíněného přístupu

Můžete nastavit zásadu podmíněného přístupu, abyste chránili přístup, na základě těchto položek:
- Stav dodržování předpisů pro zařízení
- Platforma spuštěná v zařízení
- Typ aplikací, které přistupují ke službám

Na rozdíl od jiných zásad služby Intune se zásady podmíněného přístupu nenasazují. Po nakonfigurování zásady a výběru uživatelů, kteří by měli mít tuto zásadu nastavenou, se zásada použije pro všechny cílové uživatele. Pokud je uživatel cílem zásady, musí každé jím používané zařízení vyhovovat, aby měl přístup k prostředkům.


## <a name="next-steps"></a>Další kroky


2. [Vytvořte zásady dodržování předpisů pro zařízení](create-a-device-compliance-policy-in-microsoft-intune.md).

2.  Vytvořte zásady podmíněného přístupu pro jednu z následujících cloudových služeb nebo produktů Microsoftu:

  - [Vytvoření zásady podmíněného přístupu pro Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro místní Exchange](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro novou verzi Exchange Online Dedicated](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro starší verzi Exchange Online Dedicated](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro Online Skype pro firmy](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [Vytvoření zásady podmíněného přístupu pro Dynamic CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)

