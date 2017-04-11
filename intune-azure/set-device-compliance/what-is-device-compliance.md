---
title: "Dodržování předpisů zařízení"
titleSuffix: Intune Azure preview
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
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: f316b332c3f1b80b9d6af488943298fcfea13741
ms.openlocfilehash: 8cc5e12308871a3b023bed49e9647b888971f849
ms.lasthandoff: 03/30/2017


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Co je dodržování předpisů zařízením v Intune Azure Preview?

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Zásady dodržování předpisů pro zařízení v Intune určují nastavení a pravidla, která musí zařízení dodržovat, aby se dalo považovat za zařízení, které dodržuje zásady podmíněného přístupu Intune a EMS. Zásady dodržování předpisů pro zařízení můžete používat i k monitorování a řešení problémů s dodržováním předpisů u zařízení. 

Mezi tyto pravidla patří:

- Používání hesla pro přístup k zařízení
- Šifrování
- Jestli je zařízení s jailbreakem nebo rootem
- Požadavek na minimální verzi operačního systému
- Maximální povolená verze operačního systému
- Požadavek, aby zařízení bylo na určité úrovni Mobile Threat Defense nebo pod ní

<!---##  Concepts
Following are some terms and concepts that are useful to understanding how to use compliance policies.

### Device compliance requirements
Compliance requirements are essentially rules like requiring a device PIN or encryption that you can specify as required or not required for a compliance policy.

### Actions for noncompliance

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

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Jak mám použít zásady dodržování předpisů zařízením?

### <a name="using-ems-conditional-access"></a>Použití podmíněného přístupu EMS
Zásady dodržování předpisů spolu s podmíněným přístupem EMS umožňují povolit přístup k e-mailu a dalším firemním prostředkům jenom zařízením, která jsou v souladu s jedním nebo více pravidly zásad dodržování předpisů.

### <a name="not-using-ems-conditional-access"></a>Bez použití podmíněného přístupu EMS
Zásady dodržování předpisů pro zařízení se dají používat nezávisle na podmíněném přístupu EMS.
Při nezávislém použití zásad dodržování předpisů se cílová zařízení vyhodnotí a nahlásí se jejich stav dodržování předpisů. Můžete si například nechat nahlásit, kolik zařízení není šifrovaných nebo která zařízení mají jailbreak nebo root. Pokud ale tyto zásady použijete nezávisle, nefunguje žádné omezení přístupu k prostředkům společnosti.

Zásady dodržování předpisů se nasazují uživatelům. Po nasazení zásady dodržování předpisů uživateli se u jeho zařízení kontroluje dodržování předpisů. Další informace o tom, jak dlouho trvá, než mobilní zařízení načte zásady po jejich nasazení, najdete v článku Správa nastavení a funkcí na vašich zařízeních.

##  <a name="intune-classic-admin-console-vs-intune-azure-preview-portal"></a>Klasická konzola pro správu Intune a portál Intune Azure Preview – rozdíly

Pokud používáte klasickou konzolu pro správu Intune, je dobré vědět o následujících rozdílech. Pomůže vám to při přechodu na nový pracovní postup zásad dodržování předpisů pro zařízení na portálu Azure Portal:

-   Zásady dodržování předpisů se na portálu Azure Portal vytvářejí zvlášť pro každou podporovanou platformu. V konzole pro správu služby Intune byla jedna zásada dodržování předpisů společná všem podporovaným platformám.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migration-from-intune-classic-console-to-intune-azure-preview-portal"></a>Migrace z klasické konzoly Intune na portál Intune Azure Preview

Zásady dodržování předpisů pro zařízení vytvořené v [klasické konzole Intune](https://manage.microsoft.com) se nezobrazí na novém [portálu Azure Portal pro Intune](https://portal.azure.com). Budou ale nadále účinné pro uživatele a bude je možné spravovat prostřednictvím klasické konzoly Intune.

Pokud chcete využívat nové funkce související s dodržováním předpisů pro zařízení na portálu Azure Portal pro Intune, musíte vytvořit nové zásady dodržování předpisů pro zařízení přímo na portálu Azure Portal pro Intune. Pokud přiřadíte nové zásady dodržování předpisů pro zařízení na portálu Azure Portal pro Intune uživateli, kterému byly přiřazeny zásady dodržování předpisů pro zařízení také na klasickém portálu Intune, pak budou mít zásady na portálu Azure Portal pro Intune přednost před těmi, které byly vytvořeny v klasické konzole Intune.

##  <a name="next-steps"></a>Další kroky

[Začínáme se zásadami dodržování předpisů pro zařízení](get-started-with-device-compliance.md)


<!---### See also

Conditional access--->

