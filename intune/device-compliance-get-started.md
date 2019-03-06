---
title: Zásady dodržování předpisů zařízením v Microsoft Intune – Azure | Microsoft Docs
description: Začínáme se zásadami dodržování předpisů zařízení používá, přehled stavu a úrovně závažnosti, použití stav v období odkladu, práce s podmíněným přístupem, manipulace se zařízením bez přiřazených zásad a rozdíl v dodržování předpisů na portálu Azure portal a portál Classic v Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/28/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6a0cb69612e4cf0181fde957f06f490bede7200e
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57392546"
---
# <a name="set-rules-on-devices-to-allow-access-to-resources-in-your-organization-using-intune"></a>Nastavení pravidel na zařízení a povolení přístupu k prostředkům ve vaší organizaci pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Mnoho řešení pro správu (MDM) mobilních zařízení pomáhají chránit firemní data tím, že vyžaduje uživatelů a zařízení splnit určité požadavky. V Intune tato funkce se nazývá "zásady dodržování předpisů". Zásady dodržování předpisů definují pravidla a nastavení, které uživatelé a zařízení musí splnit, aby vyhovovalo předpisům. V kombinaci s podmíněným přístupem, správci můžou blokovat uživatelů a zařízení, která nesplňují předpisy. 

Například může vyžadovat správce služby Intune:

- Koncoví uživatelé používat hesla pro přístup k datům organizace na mobilních zařízeních
- Zařízení není jailbreakem nebo rootem
- Verze minimální nebo maximální operačního systému v zařízení
- Aby zařízení bylo na nebo pod úroveň hrozby

Tato funkce také můžete monitorovat stav dodržování předpisů na zařízeních ve vaší organizaci.

> [!IMPORTANT]
> Intune se řídí zařízení vrácení se změnami plán pro všechna hodnocení dodržování předpisů na zařízení. [Další informace o zařízení vrácení se změnami plánu](https://docs.microsoft.com/intune/device-profile-troubleshoot#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

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

Chcete-li použít zásady dodržování předpisů zařízením, můžete:

- Použití následujících předplatných:

  - Intune
  - Azure Active Directory (AD) Premium

- Použití podporované platformy:

  - Android
  - iOS
  - macOS (preview)
  - Windows 8.1
  - Windows Phone 8.1
  - Windows 10

- Registrace zařízení v Intune a zjistit stav dodržování předpisů

- Registrace zařízení na jednoho uživatele nebo zaregistrovat bez primárního uživatele. Zařízení zaregistrovaná ve službě více uživatelů nejsou podporovány.

## <a name="how-device-compliance-policies-work-with-azure-ad"></a>Jak fungují zásady dodržování předpisů pro zařízení s Azure AD

Když je zařízení zaregistrované v Intune, spustí se proces registrace služby Azure AD a aktualizují se atributy zařízení ve službě Azure AD. Jednou z informací je stav dodržování předpisů zařízením. Tento stav dodržování předpisů zařízením používají zásady podmíněného přístupu k blokování nebo povolení přístupu k e-mailu a dalším podnikovým prostředkům.

Téma věnované [procesu registrace Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction) poskytuje další informace.

## <a name="refresh-cycle-times"></a>Aktualizovat doby cyklů

Při kontrole dodržování předpisů, Intune používá stejný cyklus aktualizace jako konfigurační profily. Obecně platí časy jsou:

| Platforma | Aktualizovat cyklu|
| --- | --- |
| iOS | Každých 6 hodin |
| macOS | Každých 6 hodin |
| Android | Každých 8 hodin |
| Počítače s Windows 10 zaregistrované jako zařízení | Každých 8 hodin |
| Windows Phone | Každých 8 hodin |
| Windows 8.1 | Každých 8 hodin |

Pokud zařízení zaregistrovalo nedávno, se změnami dodržování předpisů se spustí častěji:

| Platforma | Četnost |
| --- | --- |
| iOS | Prvních 6 hodin každých 15 minut a potom každých 6 hodin |  
| Mac OS X | Prvních 6 hodin každých 15 minut a potom každých 6 hodin | 
| Android | Prvních 15 minut každé 3 minuty, další 2 hodiny každých 15 minut a potom každých 8 hodin | 
| Windows Phone | Prvních 15 minut každých 5 minut, další 2 hodiny každých 15 minut a potom každých 8 hodin | 
| Počítače s Windows zaregistrované jako zařízení | Prvních 30 minut každé 3 minuty a potom každých 8 hodin | 

Na kdykoli a uživatele můžete otevřít aplikaci portál společnosti a synchronizovat zařízení okamžitě zkontroloval zásady.

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

|Stav  |Severity  |
|---------|---------|
|Neznámé     |1|
|NotApplicable     |2|
|Odpovídající|3|
|InGracePeriod|4|
|NonCompliant|5|
|Chyba|6|

Pokud má zařízení více zásad dodržování předpisů, přiřadí se mu nejvyšší úroveň závažnosti ze všech zásad.

Dejme tomu, že k zařízení jsou přiřazené tři zásady dodržování předpisů: jedna má stav Neznámé (závažnost 1), jedna má stav Vyhovuje (závažnost 3) a jedna má stav V období odkladu (závažnost 4). Stav V období odkladu má nejvyšší úroveň závažnosti, a proto mají všechny tři zásady stav dodržování předpisů V období odkladu.

## <a name="ways-to-use-device-compliance-policies"></a>Způsoby používání zásad dodržování předpisů zařízeními

#### <a name="with-conditional-access"></a>S podmíněným přístupem
Zařízením, která vyhovují pravidlům zásad, můžete udělit přístup k e-mailu a dalším podnikovým prostředkům. Pokud zařízení pravidlům zásad nevyhovuje, nezíská přístup k podnikovým prostředkům. Tomu se říká podmíněný přístup.

#### <a name="without-conditional-access"></a>Bez podmíněného přístupu
Zásady dodržování předpisů zařízeními se dají používat také bez podmíněného přístupu. Při nezávislém použití zásad dodržování předpisů se cílová zařízení vyhodnotí a nahlásí se jejich stav dodržování předpisů. Například můžete získat zprávu o tom, kolik zařízení není šifrovaných nebo která zařízení mají jailbreakem nebo rootem. Když používáte zásady dodržování předpisů bez podmíněného přístupu, nejsou k dispozici žádné omezení přístupu k prostředkům organizace.

## <a name="ways-to-deploy-device-compliance-policies"></a>Způsoby nasazení zásad dodržování předpisů zařízeními
Zásady dodržování předpisů můžete nasadit uživatelům ve skupinách uživatelů nebo zařízením ve skupinách zařízení. Po nasazení zásady dodržování předpisů uživateli se u všech jeho zařízení kontroluje dodržování předpisů. Zařízení s Windows 10 verze 1803 a novějšími je doporučeno nasadit do skupin zařízení, *pokud* primární uživatel zařízení nezaregistroval. Použití skupin zařízení pomáhá v této situaci s vykazováním dodržování předpisů.

Sadu nastavení zásad dodržování předpisů integrované (**Intune** > **dodržování předpisů zařízením**) vyhodnoceno na všechna zařízení zaregistrovaná v Intune. Mezi ně patří:

- **Označit zařízení žádné zásady dodržování předpisů, který je přiřazen jako**: Tato vlastnost má dvě hodnoty:

  - **Vyhovující předpisům**: Funkce zabezpečení je vypnuta.
  - **Nevyhovující předpisům** (výchozí): Funkce zabezpečení je zapnuta.

  Pokud zařízení nemá přiřazeny žádné zásady dodržování předpisů, je považováno za nevyhovující předpisům. Ve výchozím nastavení jsou zařízení označena jako **Nevyhovující předpisům**. Pokud používáte podmíněný přístup, doporučujeme změnit nastavení pro **nevyhovující předpisům**. Pokud koncový uživatel není kompatibilní, protože není přiřazená zásada, potom portál společnosti zobrazí `No compliance policies have been assigned`.

- **Vylepšené zjišťování jailbreaků**: Když je povoleno, toto nastavení způsobí, že zařízení s Iosem k Intune častěji. Pokud je povolena, používá tato vlastnost funkce zjišťování polohy zařízení a má vliv na výdrž baterie. Intune data o poloze uživatele neukládá.

  Povolení tohoto nastavení vyžaduje, aby zařízení:
  - povolila zjišťování polohy na úrovni operačního systému,
  - povolila Portálu společnosti používat zjišťování polohy,
  - vyhodnocovat a hlásit do Intune stav jailbreaku minimálně každých 72 hodin. V opačném případě je zařízení označeno jako nedodržující předpisy. Vyhodnocení se aktivuje po otevření aplikace Portál společnosti nebo po fyzickém přemístění zařízení o nejméně 500 metrů. Pokud zařízení čárka nepohybuje 500 měřiče během 72 hodin, uživatel musí otevřete aplikaci portál společnosti pro vyhodnocení přerušení rozšířené jailbreak.

- **Doba platnosti stavu dodržování předpisů (dny)**: Zadejte časové období, kterého zařízení nahlásí stav všech přijatých zásad dodržování předpisů. Zařízení, která během tohoto období nevrátí stav, se považují za nedodržující předpisy. Výchozí hodnota je 30 dní.

Všechna zařízení mají **integrované zásady dodržování předpisů zařízením** (Azure Portal > Dodržování předpisů zařízením > Dodržování zásad). Tyto integrované zásady můžete použít k monitorování nastavení.

Další informace o tom, jak dlouho trvá, než mobilní zařízení načte zásady po jejich nasazení, najdete v článku [Řešení potíží s profily zařízení](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

Sestavy dodržování předpisů představují skvělý způsob, jak můžete kontrolovat stav zařízení. Pokyny najdete v článku [Monitorování zásad dodržování předpisů zařízením](compliance-policy-monitor.md).

### <a name="actions-for-noncompliance"></a>Akce při nedodržení předpisů
Můžete nakonfigurovat časově řazenou posloupnost akcí, které se použijí na zařízeních, která nevyhovují kritériím zásad dodržování předpisů. Tyto akce při nedodržení předpisů mohou být automatické, jak je popsáno v článku [Automatické akce při nedodržení předpisů](actions-for-noncompliance.md).

## <a name="azure-classic-portal-vs-azure-portal"></a>Portál Azure Classic vs. portál Azure

Hlavním rozdíl při použití zásad dodržování předpisů zařízením na portálu Azure Portal:

- Zásady dodržování předpisů se na portálu Azure Portal vytvářejí zvlášť pro každou podporovanou platformu.
- Na portálu Azure Classic mají všechny podporované platformy společnou jednu zásadu dodržování předpisů zařízeními.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

## <a name="device-compliance-policies-in-the-classic-portal-and-azure-portal"></a>Zásady dodržování předpisů zařízeními na portálu Classic a na portálu Azure Portal

Zásady dodržování předpisů vytvořené na [portálu Classic](https://manage.microsoft.com) se na portálu [Azure Portal](https://portal.azure.com) nezobrazují. Pro uživatele ale nadále platí a dají se spravovat prostřednictvím portálu Classic.

Pokud chcete využívat nové funkce související s dodržováním předpisů zařízeními na portálu Azure Portal, musíte vytvořit nové zásady dodržování předpisů zařízeními na portálu Azure Portal. Pokud přiřadíte zásady dodržování předpisů zařízením na Azure Portalu uživateli, kterému byly přiřazeny zásady dodržování předpisů zařízením také na klasickém portálu, budou mít zásady na Azure Portalu přednost před těmi, které byly vytvořeny na klasickém portálu.

## <a name="next-steps"></a>Další postup

- Vytvoření zásad dodržování předpisů zařízeními pro následující platformy:

  - [Android](compliance-policy-create-android.md)
  - [Pracovní profil Androidu](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Informace o entitách zásad Datového skladu Intune najdete v článku [Referenční informace pro entity zásad](reports-ref-policy.md).
