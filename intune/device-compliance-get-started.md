---
title: Zásady dodržování předpisů zařízeními v Microsoft Intune
titleSuffix: ''
description: Informace o zásadách dodržování předpisů zařízeními v Microsoft Intune
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fb3ec168844708d80c83909ab6c58a52ca62e53c
ms.sourcegitcommit: a22309174e617e59ab0cdd0a55abde38711a5f35
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/23/2018
---
# <a name="get-started-with-microsoft-intune-device-compliance-policies"></a>Začínáme se zásadami dodržování předpisů zařízeními v Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zásady dodržování předpisů zařízeními v Intune definují pravidla a nastavení, která jsou pro zařízení povinná, pokud má toto zařízení vyhovět zásadám Intune.

Mezi tyto pravidla patří:

- Používání hesla pro přístup k zařízení

- Šifrování

- Jestli je zařízení s jailbreakem nebo rootem

- Požadavek na minimální verzi operačního systému

- Maximální povolená verze operačního systému

- Požadavek, aby zařízení bylo na určité úrovni Mobile Threat Defense nebo pod ní

Zásady dodržování předpisů zařízeními můžete používat i k monitorování stavu dodržování předpisů u vašich zařízení.

## <a name="device-compliance-requirements"></a>Požadavky na dodržování předpisů zařízení

Požadavky na dodržování předpisů jsou v podstatě pravidla, například vyžadování PIN kódu zařízení nebo šifrování, která můžete v zásadách dodržování předpisů určit jako povinná nebo nepovinná.

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be noncompliant, an email with noncompliant notification is sent to the user.

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

- Intune

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

Když je zařízení zaregistrované v Intune, proběhne proces registrace služby Azure AD, který ve službě Azure AD aktualizuje atributy zařízení o další informace. Klíčovou informací je stav dodržování předpisů zařízením, který používají zásady podmíněného přístupu k blokování nebo povolení přístupu k e-mailu a dalším podnikovým prostředkům.

- Přečtěte si další informace o [procesu registrace Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction).

### <a name="assigning-a-resulting-device-configuration-profile-status"></a>Přiřazení výsledného stavu konfiguračního profilu zařízení

Pokud je k nějakému zařízení přiřazených několik konfiguračních profilů a toto zařízení má pro dva nebo více z nich různé stavy dodržování předpisů, musí se mu přiřadit jediný výsledný stav dodržování předpisů. Toto přiřazení vychází z koncepční úrovně závažnosti přiřazené jednotlivých stavům dodržování předpisů. Jednotlivé stavy dodržování předpisů mají následující úroveň závažnosti:


|Stav  |Závažnost  |
|---------|---------|
|Čeká     |1|
|Úspěšné     |2|
|Neúspěch     |3|
|Chyba     |4|

Výsledný stav dvou nebo více konfiguračních profilů se pak přiřadí tak, že se vybere nejvyšší úroveň závažnosti všech profilů přiřazených k zařízení.

Dejme tomu, že k zařízení jsou přiřazené tři profily: jeden má stav Čeká (závažnost 1), jeden má stav Úspěšné (závažnost 2) a jeden má stav Chyba (závažnost 4). Stav Chyba má nejvyšší úroveň závažnosti, takže se přiřadí jako výsledný stav dodržování předpisů všech tří profilů.

### <a name="assigning-an-ingraceperiod-status-for-an-assigned-compliance-policy"></a>Přiřazení stavu V období odkladu pro přiřazené zásady dodržování předpisů

Stav V období odkladu pro zásady dodržování předpisů je hodnota určená kombinací období odkladu zařízení a skutečného stavu zařízení s ohledem na přiřazené zásady dodržování předpisů. 

Konkrétně, pokud má zařízení pro přiřazené zásady dodržování předpisů stav Nevyhovující předpisům a:

- k zařízení není přiřazené žádné období odkladu, přiřadí se zásadám dodržování předpisů hodnota Nevyhovující předpisům.
- zařízení má období odkladu, které vypršelo, přiřadí se zásadám dodržování předpisů hodnota Nevyhovující předpisům.
- zařízení má období odkladu, které je v budoucnosti, přiřadí se zásadám dodržování předpisů hodnota V období odkladu.

Předchozí body jsou shrnuty v následující tabulce:


|Skutečný stav dodržování předpisů|Hodnota přiřazeného období odkladu|Účinný stav dodržování předpisů|
|---------|---------|---------|
|Nevyhovující předpisům |Bez přiřazeného období odkladu |Nevyhovující předpisům |
|Nevyhovující předpisům |Včerejší datum|Nevyhovující předpisům|
|Nevyhovující předpisům |Zítřejší datum|V období odkladu|

Další informace o monitorování zásad dodržování předpisů zařízením najdete v článku [Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md).

### <a name="assigning-a-resulting-compliance-policy-status"></a>Přiřazení výsledného stavu zásad dodržování předpisů

Pokud je k nějakému zařízení přiřazených několik zásad dodržování předpisů a toto zařízení má pro dvě nebo více z nich různé stavy dodržování předpisů, musí se mu přiřadit jediný výsledný stav dodržování předpisů. Toto přiřazení vychází z koncepční úrovně závažnosti přiřazené jednotlivých stavům dodržování předpisů. Jednotlivé stavy dodržování předpisů mají následující úroveň závažnosti: 

|Stav  |Závažnost  |
|---------|---------|
|Neznámé     |1|
|NotApplicable     |2|
|Vyhovuje|3|
|InGracePeriod|4|
|NonCompliant|5|
|Chyba|6|

Výsledný stav dvou nebo více zásad dodržování předpisů se pak určí tak, že se vybere nejvyšší úroveň závažnosti všech zásad přiřazených k zařízení.
 
Dejme tomu, že k zařízení jsou přiřazené tři zásady dodržování předpisů: jedna má stav Neznámé (závažnost 1), jedna má stav Vyhovuje (závažnost 3) a jedna má stav V období odkladu (závažnost 4). Stav V období odkladu má nejvyšší úroveň závažnosti, takže se přiřadí jako výsledný stav dodržování předpisů všech tří profilů.  

##  <a name="ways-to-use-device-compliance-policies"></a>Způsoby používání zásad dodržování předpisů zařízeními

### <a name="with-conditional-access"></a>S podmíněným přístupem
Zásady dodržování předpisů spolu s podmíněným přístupem umožňují povolit přístup k e-mailu a dalším podnikovým prostředkům jenom zařízením, která vyhovují jednomu nebo více pravidlům zásad dodržování předpisů zařízeními.

### <a name="without-conditional-access"></a>Bez podmíněného přístupu
Zásady dodržování předpisů zařízeními se dají používat nezávisle na podmíněném přístupu. Při nezávislém použití zásad dodržování předpisů se cílová zařízení vyhodnotí a nahlásí se jejich stav dodržování předpisů. Můžete si například nechat nahlásit, kolik zařízení není šifrovaných nebo která zařízení mají jailbreak nebo root. Pokud ale tyto zásady použijete nezávisle, nefunguje žádné omezení přístupu k prostředkům společnosti.

Zásady dodržování předpisů se nasazují uživatelům. Po nasazení zásady dodržování předpisů uživateli se u jeho zařízení kontroluje dodržování předpisů. Další informace o tom, jak dlouho trvá, než mobilní zařízení načte zásady po jejich nasazení, najdete v článku [Řešení potíží s profily zařízení v Microsoft Intune](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

#### <a name="actions-for-non-compliance"></a>Akce při nedodržení předpisů

Akce při nedodržení předpisů umožňují konfigurovat časově řazenou posloupnost akcí, které se použijí na zařízeních, která nevyhovují kritériím zásad dodržování předpisů. Další informace najdete v článku [Automatizace akcí při nedodržení předpisů](actions-for-noncompliance.md).

##  <a name="using-device-compliance-policies-in-the-intune-classic-portal-vs-azure-portal"></a>Použití zásad dodržování předpisů zařízeními na klasickém portálu Intune a na portálu Azure Portal

Abychom vám pomohli při přechodu na nový pracovní postup pro dodržování zásad zařízeními na portálu Azure Portal, chtěli bychom vás upozornit na hlavní rozdíly.

- Zásady dodržování předpisů se na portálu Azure Portal vytvářejí zvlášť pro každou podporovanou platformu.
- Na klasickém portálu Intune měly všechny podporované platformy společnou jednu zásadu dodržování předpisů zařízeními.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migrate-device-compliance-policies-from-the-intune-classic-portal-to-the-azure-portal"></a>Migrace zásad dodržování předpisů zařízeními z klasického portálu Intune na portál Azure Portal

Zásady dodržování předpisů zařízeními vytvořené na [klasickém portálu Intune](https://manage.microsoft.com) se v novém [Intune na Azure Portalu](https://portal.azure.com) nezobrazují. Pro uživatele ale nadále platí a dají se spravovat prostřednictvím klasického portálu Intune.

Pokud chcete využívat nové funkce související s dodržováním předpisů zařízeními na Azure Portalu, musíte vytvořit nové zásady dodržování předpisů zařízeními přímo na Azure Portalu. Pokud přiřadíte nové zásady dodržování předpisů zařízeními na portálu Azure Portal uživateli, kterému byly přiřazeny zásady dodržování předpisů zařízeními také na klasickém portálu Intune, budou mít zásady na portálu Azure Portal přednost před těmi, které byly vytvořeny na klasickém portálu Intune.

##  <a name="next-steps"></a>Další kroky

- Vytvoření zásad dodržování předpisů zařízeními pro následující platformy:

   - [Androidemem](compliance-policy-create-android.md)
   - [Android for work](compliance-policy-create-android-for-work.md)
   - [iOS](compliance-policy-create-ios.md)
   - [macOS](compliance-policy-create-mac-os.md)
   - [Windows](compliance-policy-create-windows.md)

- Informace o entitách zásad Datového skladu Intune najdete v článku [Referenční informace pro entity zásad](reports-ref-policy.md).
