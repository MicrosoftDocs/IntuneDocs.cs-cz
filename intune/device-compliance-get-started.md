---
title: Zásady dodržování předpisů zařízením v Microsoft Intune – Azure | Microsoft Docs
description: Požadavky na použití zásad dodržování předpisů zařízením, přehled stavu a úrovně závažnosti, použití stavu V období odkladu, práce s podmíněným přístupem, manipulace se zařízením bez přiřazených zásad a rozdíl v dodržování předpisů na portálu Azure Portal a Azure Classic Portal v Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 226713d893e05c2c2aeea49cde2ce92591d06391
ms.sourcegitcommit: 1134ecd733356277b40eb1c7f2b318b36d387e00
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2018
ms.locfileid: "50915695"
---
# <a name="get-started-with-device-compliance-policies-in-intune"></a>Začínáme se zásadami dodržování předpisů zařízeními v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Požadavky na dodržování předpisů jsou v podstatě pravidla, která například vyžadují používání kódu PIN v zařízení nebo šifrování. Zásady dodržování předpisů zařízeními definují pravidla a nastavení, která jsou pro zařízení povinná, pokud má toto zařízení vyhovět zásadám. Mezi tato pravidla patří:

- Používání hesla pro přístup k zařízení

- Šifrování

- Jestli je zařízení s jailbreakem nebo rootem

- Požadavek na minimální verzi operačního systému

- Maximální povolená verze operačního systému

- Požadavek, aby zařízení bylo na určité úrovni Mobile Threat Defense nebo pod ní

Zásady dodržování předpisů zařízeními můžete používat i k monitorování stavu dodržování předpisů u vašich zařízení.

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

## <a name="prerequisites"></a>Požadavky
Pokud chcete používat zásady dodržování předpisů zařízeními, musíte splňovat následující podmínky:

- Použití následujících předplatných:

  - Intune
  - Azure Active Directory (AD) Premium

- Použití podporované platformy:

  - Android
  - iOS
  - macOS (preview)
  - Windows 8.1
  - Windows Phone 8.1
  - Windows 10

- Aby mohla zařízení oznamovat stavy dodržování předpisů, musejí být zaregistrovaná v Intune.

- Jsou podporována zařízení zaregistrovaná na jednoho uživatele nebo bez primárního uživatele. Kontexty více uživatelů nejsou podporovány.

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>Jak fungují zásady dodržování předpisů zařízeními v Intune s Azure AD

Když je zařízení zaregistrované v Intune, spustí se proces registrace služby Azure AD a aktualizují se atributy zařízení ve službě Azure AD. Jednou z informací je stav dodržování předpisů zařízením. Tento stav dodržování předpisů zařízením používají zásady podmíněného přístupu k blokování nebo povolení přístupu k e-mailu a dalším podnikovým prostředkům.

Téma věnované [procesu registrace Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction) poskytuje další informace.

### <a name="assign-a-resulting-device-configuration-profile-status"></a>Přiřazení výsledného stavu konfiguračního profilu zařízení

Pokud má nějaké zařízení několik konfiguračních profilů a má pro dva nebo více z nich různé stavy dodržování předpisů, přiřadí se mu jediný výsledný stav dodržování předpisů. Toto přiřazení vychází z koncepční úrovně závažnosti přiřazené jednotlivých stavům dodržování předpisů. Jednotlivé stavy dodržování předpisů mají následující úroveň závažnosti:

|Stav  |Závažnost  |
|---------|---------|
|Čeká     |1|
|Úspěšné     |2|
|Neúspěch     |3|
|Chyba     |4|

Pokud má zařízení více konfiguračních profilů, přiřadí se mu nejvyšší úroveň závažnosti ze všech profilů.

Dejme tomu, že k zařízení jsou přiřazené tři profily: jeden má stav Čeká (závažnost 1), jeden má stav Úspěšné (závažnost 2) a jeden má stav Chyba (závažnost 4). Stav Chyba má nejvyšší úroveň závažnosti, takže všechny tři profily mají stav dodržování předpisů Chyba.

### <a name="assign-an-ingraceperiod-status"></a>Přiřazení stavu V období odkladu

Stav V období odkladu u zásad dodržování předpisů představuje hodnotu. Tuto hodnotu určuje kombinace období odkladu a skutečný stav daných zásad dodržování předpisů u zařízení.

Konkrétně, pokud má zařízení pro přiřazené zásady dodržování předpisů stav Nevyhovující předpisům a:

- k zařízení není přiřazené žádné období odkladu, přiřadí se zásadám dodržování předpisů hodnota Nevyhovující předpisům.
- zařízení má období odkladu, které vypršelo, přiřadí se zásadám dodržování předpisů hodnota Nevyhovující předpisům.
- zařízení má období odkladu, které je v budoucnosti, přiřadí se zásadám dodržování předpisů hodnota V období odkladu.

V následující tabulce najdete souhrnný přehled těchto bodů:

|Skutečný stav dodržování předpisů|Hodnota přiřazeného období odkladu|Účinný stav dodržování předpisů|
|---------|---------|---------|
|Nevyhovující předpisům |Bez přiřazeného období odkladu |Nevyhovující předpisům |
|Nevyhovující předpisům |Včerejší datum|Nevyhovující předpisům|
|Nevyhovující předpisům |Zítřejší datum|V období odkladu|

Další informace o monitorování zásad dodržování předpisů zařízením najdete v článku [Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md).

### <a name="assign-a-resulting-compliance-policy-status"></a>Přiřazení výsledného stavu zásad dodržování předpisů

Pokud má nějaké zařízení několik zásad dodržování předpisů a pro dvě nebo více z nich má různé stavy dodržování předpisů, přiřadí se mu jediný výsledný stav dodržování předpisů. Toto přiřazení vychází z koncepční úrovně závažnosti přiřazené jednotlivých stavům dodržování předpisů. Jednotlivé stavy dodržování předpisů mají následující úroveň závažnosti:

|Stav  |Závažnost  |
|---------|---------|
|Neznámé     |1|
|NotApplicable     |2|
|Vyhovuje|3|
|InGracePeriod|4|
|NonCompliant|5|
|Chyba|6|

Pokud má zařízení více zásad dodržování předpisů, přiřadí se mu nejvyšší úroveň závažnosti ze všech zásad.

Dejme tomu, že k zařízení jsou přiřazené tři zásady dodržování předpisů: jedna má stav Neznámé (závažnost 1), jedna má stav Vyhovuje (závažnost 3) a jedna má stav V období odkladu (závažnost 4). Stav V období odkladu má nejvyšší úroveň závažnosti, a proto mají všechny tři zásady stav dodržování předpisů V období odkladu.

## <a name="ways-to-use-device-compliance-policies"></a>Způsoby používání zásad dodržování předpisů zařízeními

#### <a name="with-conditional-access"></a>S podmíněným přístupem
Zařízením, která vyhovují pravidlům zásad, můžete udělit přístup k e-mailu a dalším podnikovým prostředkům. Pokud zařízení pravidlům zásad nevyhovuje, nezíská přístup k podnikovým prostředkům. Tomu se říká podmíněný přístup.

#### <a name="without-conditional-access"></a>Bez podmíněného přístupu
Zásady dodržování předpisů zařízeními se dají používat také bez podmíněného přístupu. Při nezávislém použití zásad dodržování předpisů se cílová zařízení vyhodnotí a nahlásí se jejich stav dodržování předpisů. Můžete si například nechat nahlásit, kolik zařízení není šifrovaných nebo která zařízení mají jailbreak nebo root. Pokud ale tyto zásady použijete bez podmíněného přístupu, neexistuje žádné omezení přístupu k prostředkům společnosti.

## <a name="ways-to-deploy-device-compliance-policies"></a>Způsoby nasazení zásad dodržování předpisů zařízeními
Zásady dodržování předpisů můžete nasadit uživatelům ve skupinách uživatelů nebo zařízením ve skupinách zařízení. Po nasazení zásady dodržování předpisů uživateli se u všech jeho zařízení kontroluje dodržování předpisů. Zařízení s Windows 10 verze 1803 a novějšími je doporučeno nasadit do skupin zařízení, *pokud* primární uživatel zařízení nezaregistroval. Použití skupin zařízení pomáhá v této situaci s vykazováním dodržování předpisů.

Na všech zařízeních zaregistrovaných v Intune můžete vyhodnotit sadu integrovaných **nastavení zásad dodržování předpisů** (Azure Portal > Dodržování předpisů zařízením). Patří k nim:

- **Označit zařízení, která nemají přiřazené žádné zásady dodržování předpisů, jako**: Tato vlastnost má dvě hodnoty:

  - **Vyhovující předpisům**: Funkce zabezpečení je vypnuta.
  - **Nevyhovující předpisům** (výchozí): Funkce zabezpečení je zapnuta.

  Pokud zařízení nemá přiřazeny žádné zásady dodržování předpisů, je považováno za nevyhovující předpisům. Ve výchozím nastavení jsou zařízení označena jako **Vyhovující předpisům**. Pokud používáte podmíněný přístup, doporučujeme změnit nastavení na **Nevyhovující předpisům**. Pokud koncový uživatel nevyhovuje předpisům, protože nejsou přiřazeny žádné zásady, na Portálu společnosti je uvedeno `No compliance policies have been assigned`.

- **Vylepšené zjišťování jailbreaků**: Když toto nastavení povolíte, budou se zařízení s iOSem vracet se změnami pomocí Intune častěji. Pokud je povolena, používá tato vlastnost funkce zjišťování polohy zařízení a má vliv na výdrž baterie. Intune data o poloze uživatele neukládá.

  Povolení tohoto nastavení vyžaduje, aby zařízení:
  - povolila zjišťování polohy na úrovni operačního systému,
  - povolila Portálu společnosti používat zjišťování polohy,
  - vyhodnocovat a hlásit do Intune stav jailbreaku minimálně každých 72 hodin. V opačném případě je zařízení označeno jako nedodržující předpisy. Vyhodnocení se aktivuje po otevření aplikace Portál společnosti nebo po fyzickém přemístění zařízení o nejméně 500 metrů.

- **Doba platnosti stavu dodržování předpisů (dny)**: Zadejte časové období, během kterého zařízení nahlásí stav všech přijatých zásad dodržování předpisů. Zařízení, která během tohoto období nevrátí stav, se považují za nedodržující předpisy. Výchozí hodnota je 30 dní.

Všechna zařízení mají **integrované zásady dodržování předpisů zařízením** (Azure Portal > Dodržování předpisů zařízením > Dodržování zásad). Tyto integrované zásady můžete použít k monitorování nastavení.

Další informace o tom, jak dlouho trvá, než mobilní zařízení načte zásady po jejich nasazení, najdete v článku [Řešení potíží s profily zařízení](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

Sestavy dodržování předpisů představují skvělý způsob, jak můžete kontrolovat stav zařízení. Pokyny najdete v článku [Monitorování zásad dodržování předpisů zařízením](compliance-policy-monitor.md).

### <a name="actions-for-noncompliance"></a>Akce při nedodržení předpisů
Můžete nakonfigurovat časově řazenou posloupnost akcí, které se použijí na zařízeních, která nevyhovují kritériím zásad dodržování předpisů. Tyto akce při nedodržení předpisů mohou být automatické, jak je popsáno v článku [Automatické akce při nedodržení předpisů](actions-for-noncompliance.md).

## <a name="azure-classic-portal-vs-azure-portal"></a>Portál Azure Classic vs. Portál Azure Portal

Hlavním rozdíl při použití zásad dodržování předpisů zařízením na portálu Azure Portal:

- Zásady dodržování předpisů se na portálu Azure Portal vytvářejí zvlášť pro každou podporovanou platformu.
- Na portálu Azure Classic mají všechny podporované platformy společnou jednu zásadu dodržování předpisů zařízeními.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

## <a name="device-compliance-policies-in-the-classic-portal-and-azure-portal"></a>Zásady dodržování předpisů zařízeními na portálu Classic a na portálu Azure Portal

Zásady dodržování předpisů vytvořené na [portálu Classic](https://manage.microsoft.com) se na portálu [Azure Portal](https://portal.azure.com) nezobrazují. Pro uživatele ale nadále platí a dají se spravovat prostřednictvím portálu Classic.

Pokud chcete využívat nové funkce související s dodržováním předpisů zařízeními na portálu Azure Portal, musíte vytvořit nové zásady dodržování předpisů zařízeními na portálu Azure Portal. Pokud přiřadíte zásady dodržování předpisů zařízením na Azure Portalu uživateli, kterému byly přiřazeny zásady dodržování předpisů zařízením také na klasickém portálu, budou mít zásady na Azure Portalu přednost před těmi, které byly vytvořeny na klasickém portálu.

## <a name="next-steps"></a>Další kroky

- Vytvoření zásad dodržování předpisů zařízeními pro následující platformy:

  - [Androidemem](compliance-policy-create-android.md)
  - [Pracovní profil Androidu](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Informace o entitách zásad Datového skladu Intune najdete v článku [Referenční informace pro entity zásad](reports-ref-policy.md).
