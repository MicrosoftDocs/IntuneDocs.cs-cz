---
title: "Zásady dodržování předpisů zařízeními v Intune"
titleSuffix: Azure portal
description: "V tomto tématu se dozvíte o dodržování předpisů zařízením v Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1e6d758d10a3527e0dc350115f2f8f10e2c62322
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="get-started-with-intune-device-compliance-policies"></a>Začínáme se zásadami dodržování předpisů zařízeními v Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="what-is-device-compliance-in-intune"></a>Co je dodržování předpisů zařízením v Intune?

Zásady dodržování předpisů zařízeními v Intune definují pravidla a nastavení, která jsou pro zařízení povinná, pokud má toto zařízení vyhovět zásadám Intune.

Mezi tyto pravidla patří:

- Používání hesla pro přístup k zařízení

- Šifrování

- Jestli je zařízení s jailbreakem nebo rootem

- Požadavek na minimální verzi operačního systému

- Maximální povolená verze operačního systému

- Požadavek, aby zařízení bylo na určité úrovni Mobile Threat Defense nebo pod ní

Zásady dodržování předpisů zařízeními můžete používat i k monitorování stavu dodržování předpisů u vašich zařízení.

### <a name="device-compliance-requirements"></a>Požadavky na dodržování předpisů zařízení

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

##  <a name="pre-requisites"></a>Požadavky

Pokud chcete používat zásady dodržování předpisů zařízeními s Intune, potřebujete následující předplatná:

- Intune EMS

- Azure AD Premium

###  <a name="supported-platforms"></a>Podporované platformy:

-   Android

-   iOS

-   macOS (preview)

-   Windows 8.1

-   Windows Phone 8.1

-   Windows 10

> [!IMPORTANT]
> Aby mohla zařízení oznamovat stavy dodržování předpisů, musejí být zaregistrovaná v Intune.

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>Jak fungují zásady dodržování předpisů zařízeními v Intune s Azure AD

Pokud je zařízení zaregistrované v Intune, proběhne proces registrace Azure AD, který aktualizuje v Azure AD informace týkající se atributů zařízení. Jednou z klíčových informací je stav dodržování předpisů zařízením, který používají zásady podmíněného přístupu k blokování nebo povolení přístupu k e-mailu a dalším podnikovým prostředkům.

- Přečtěte si další informace o [procesu registrace Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-device-registration-overview).

##  <a name="ways-to-use-device-compliance-policies"></a>Způsoby používání zásad dodržování předpisů zařízeními

### <a name="with-conditional-access"></a>S podmíněným přístupem
Zásady dodržování předpisů spolu s podmíněným přístupem umožňují povolit přístup k e-mailu a dalším podnikovým prostředkům jenom zařízením, která vyhovují jednomu nebo více pravidlům zásad dodržování předpisů zařízeními.

### <a name="without-conditional-access"></a>Bez podmíněného přístupu
Zásady dodržování předpisů zařízeními se dají používat nezávisle na podmíněném přístupu. Při nezávislém použití zásad dodržování předpisů se cílová zařízení vyhodnotí a nahlásí se jejich stav dodržování předpisů. Můžete si například nechat nahlásit, kolik zařízení není šifrovaných nebo která zařízení mají jailbreak nebo root. Pokud ale tyto zásady použijete nezávisle, nefunguje žádné omezení přístupu k prostředkům společnosti.

Zásady dodržování předpisů se nasazují uživatelům. Po nasazení zásady dodržování předpisů uživateli se u jeho zařízení kontroluje dodržování předpisů. Další informace o tom, jak dlouho trvá, než mobilní zařízení načte zásady po jejich nasazení, najdete v článku Správa nastavení a funkcí na vašich zařízeních.

##  <a name="using-device-compliance-policies-in-the-intune-classic-portal-vs-azure-portal"></a>Použití zásad dodržování předpisů zařízeními na klasickém portálu Intune a na portálu Azure Portal

Abychom vám pomohli při přechodu na nový pracovní postup pro dodržování zásad zařízeními na portálu Azure Portal, chtěli bychom vás upozornit na hlavní rozdíly.

- Zásady dodržování předpisů se na portálu Azure Portal vytvářejí zvlášť pro každou podporovanou platformu.
- Na klasickém portálu Intune měly všechny podporované platformy společnou jednu zásadu dodržování předpisů zařízeními.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migrate-device-compliance-policies-from-the-intune-classic-portal-to-the-azure-portal"></a>Migrace zásad dodržování předpisů zařízeními z klasického portálu Intune na portál Azure Portal

Zásady dodržování předpisů zařízeními vytvořené na [klasickém portálu Intune](https://manage.microsoft.com) se na novém portálu [Azure Portal v Intune](https://portal.azure.com) nezobrazí. Pro uživatele ale nadále platí a dají se spravovat prostřednictvím klasického portálu Intune.

Pokud chcete využívat nové funkce související s dodržováním předpisů zařízeními na portálu Azure Portal, musíte vytvořit nové zásady dodržování předpisů zařízeními přímo na portálu Azure Portal. Pokud přiřadíte nové zásady dodržování předpisů zařízeními na portálu Azure Portal uživateli, kterému byly přiřazeny zásady dodržování předpisů zařízeními také na klasickém portálu Intune, budou mít zásady na portálu Azure Portal přednost před těmi, které byly vytvořeny na klasickém portálu Intune.

##  <a name="next-steps"></a>Další kroky

Vytvoření zásad dodržování předpisů zařízeními pro následující platformy:

- [Androidemem](compliance-policy-create-android.md)
- [Android for work](compliance-policy-create-android-for-work.md)
- [iOS](compliance-policy-create-ios.md)
- [macOS](compliance-policy-create-mac-os.md)
- [Windows](compliance-policy-create-windows.md)
