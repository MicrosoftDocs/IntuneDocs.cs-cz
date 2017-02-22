---
title: "Dodržování předpisů zařízením | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: V tomto tématu se dozvíte o dodržování předpisů zařízením v Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7693d49e2f0fa6e4aa40b6bb71433a7eaab8dd15
ms.openlocfilehash: a4254503e4e6b86079f862966dee2727934f1ee6


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Co je dodržování předpisů zařízením v Intune Azure Preview?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Pokud chcete chránit firemní data, budete muset zkontrolovat, jestli jsou zařízení určená pro přístup k podnikovým aplikacím a datům v souladu s určitými pravidly. Mezi tyto pravidla může patřit používání kódu PIN pro přístup k zařízením a šifrování dat uložených na zařízeních. Sada těchto pravidel se označuje jako **zásady dodržování předpisů**.

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Jak mám použít zásady dodržování předpisů zařízením?
Zásady dodržování předpisů spolu s podmíněným přístupem umožňují povolit přístup k e-mailu a dalším službám jenom zařízením, která jsou v souladu s pravidly zásad dodržování předpisů.

Zásady dodržování předpisů se můžou používat také nezávisle na podmíněném přístupu.
Při nezávislém použití zásad dodržování předpisů se cílová zařízení vyhodnotí a nahlásí se jejich stav dodržování předpisů. Můžete si například nechat nahlásit, kolik zařízení není šifrovaných nebo která zařízení mají jailbreak nebo root. Pokud ale tyto zásady použijete nezávisle, nefunguje žádné omezení přístupu k prostředkům společnosti.

Zásady dodržování předpisů se nasazují uživatelům. Po nasazení zásady dodržování předpisů uživateli se u jeho zařízení kontroluje dodržování předpisů. Další informace o tom, jak dlouho trvá, než mobilní zařízení načte zásady po jejich nasazení, najdete v článku Správa nastavení a funkcí na vašich zařízeních.

##  <a name="concepts"></a>Koncepty
V další části jsou některé pojmy a koncepty, které vám pomůžou pochopit, jak se zásady dodržování předpisů používají.

### <a name="compliance-requirements"></a>Požadavky na dodržování předpisů
Požadavky na dodržování předpisů jsou v podstatě pravidla, například vyžadování PIN kódu zařízení nebo šifrování, která můžete v zásadách dodržování předpisů určit jako povinná nebo nepovinná.

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

##  <a name="differences-between-the-classic-intune-admin-console-and-intune-in-the-azure-portal"></a>Rozdíly mezi konzolou pro správu Intune Classic a službou Intune na portálu Azure Portal


Pokud jste dříve používali konzolu pro správu Intune Classic, je dobré vědět o následujících rozdílech. Pomůže vám to při přechodu na nový pracovní postup dodržování předpisů zařízením na portálu Azure Portal:


-   Zásady dodržování předpisů se na portálu Azure Portal vytvářejí zvlášť pro každou podporovanou platformu. V konzole pro správu služby Intune byla jedna zásada dodržování předpisů společná všem podporovaným platformám.


<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="next-steps"></a>Další kroky

[Začínáme se zásadami dodržování předpisů](get-started-with-device-compliance.md)


<!---### See also

Conditional access--->



<!--HONumber=Feb17_HO1-->


