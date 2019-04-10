---
title: Zásady dodržování předpisů zařízením v Microsoft Intune – Azure | Microsoft Docs
description: Začínáme se zásadami dodržování předpisů zařízení používá, přehled stavu a úrovně závažnosti, použití stav v období odkladu, práce s podmíněným přístupem, manipulace se zařízením bez přiřazených zásad a rozdíl v dodržování předpisů na portálu Azure portal a portál Classic v Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/08/2019
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
ms.openlocfilehash: fbed6185abe7656c3269805d1d5ed09eccbaf05e
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423524"
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
> Intune se řídí zařízení vrácení se změnami plán pro všechna hodnocení dodržování předpisů na zařízení. [Další informace o zařízení vrácení se změnami plánu](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

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

## <a name="device-compliance-policies-work-with-azure-ad"></a>Zásady dodržování předpisů zařízením pracovat s Azure AD

Intune používá Azure Active Directory (AD) [podmíněného přístupu](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) (otevře jiný web docs) k podpoře vynucení dodržování předpisů. Když se zařízení zaregistruje v Intune, proces registrace Azure AD spustí a ve službě Azure AD se aktualizovaly informace o zařízení. Jednou z informací je stav dodržování předpisů zařízením. Tento stav dodržování předpisů používá zásady podmíněného přístupu k blokování nebo povolení přístupu k e-mailu a jiným prostředkům organizace.

- [Co je Správa zařízení ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction) je skvělý prostředek na tom, proč a jak jsou zařízení zaregistrovaná ve službě Azure AD.

- [Podmíněný přístup](conditional-access.md) a [běžné způsoby použití podmíněného přístupu](conditional-access-intune-common-ways-use.md) popisují tato funkce se týká do Intune.

## <a name="ways-to-use-device-compliance-policies"></a>Způsoby používání zásad dodržování předpisů zařízeními

#### <a name="with-conditional-access"></a>S podmíněným přístupem

Pro zařízení, která vyhovují pravidlům zásad můžete udělit přístup k e-mailu a jiným prostředkům organizace. Pokud zařízení pravidlům zásad nevyhovuje, nezíská přístup k prostředkům organizace. Tomu se říká podmíněný přístup.

#### <a name="without-conditional-access"></a>Bez podmíněného přístupu

Zásady dodržování předpisů zařízeními se dají používat také bez podmíněného přístupu. Při nezávislém použití zásad dodržování předpisů se cílová zařízení vyhodnotí a nahlásí se jejich stav dodržování předpisů. Například můžete získat zprávu o tom, kolik zařízení není šifrovaných nebo která zařízení mají jailbreakem nebo rootem. Když používáte zásady dodržování předpisů bez podmíněného přístupu, nejsou k dispozici žádné omezení přístupu k prostředkům organizace.

## <a name="ways-to-deploy-device-compliance-policies"></a>Způsoby nasazení zásad dodržování předpisů zařízeními

Zásady dodržování předpisů můžete nasadit uživatelům ve skupinách uživatelů nebo zařízením ve skupinách zařízení. Po nasazení zásady dodržování předpisů uživateli se u všech jeho zařízení kontroluje dodržování předpisů. Zařízení s Windows 10 verze 1803 a novějšími je doporučeno nasadit do skupin zařízení, *pokud* primární uživatel zařízení nezaregistroval. Použití skupin zařízení pomáhá v této situaci s vykazováním dodržování předpisů.

Intune také obsahuje sadu nastavení zásad dodržování předpisů integrované. Získat následující předdefinované zásady vyhodnotí na všechna zařízení zaregistrovaná v Intune:

- **Označit zařízení žádné zásady dodržování předpisů, který je přiřazen jako**: Tato vlastnost má dvě hodnoty:

  - **Vyhovující předpisům**: Funkce zabezpečení je vypnuta.
  - **Nevyhovující předpisům** (výchozí): Funkce zabezpečení je zapnuta.

  Pokud zařízení nemá přiřazeny žádné zásady dodržování předpisů, je považováno za nevyhovující předpisům. Ve výchozím nastavení jsou zařízení označena jako **Nevyhovující předpisům**. Pokud používáte podmíněný přístup, doporučujeme změnit nastavení pro **nevyhovující předpisům**. Pokud koncový uživatel není kompatibilní, protože není přiřazená zásada, pak bude [aplikaci portál společnosti](company-portal-app.md) ukazuje `No compliance policies have been assigned`.

- **Vylepšené zjišťování jailbreaků**: Když je povoleno, toto nastavení způsobí, že zařízení s Iosem k Intune častěji. Pokud je povolena, používá tato vlastnost funkce zjišťování polohy zařízení a má vliv na výdrž baterie. Data o poloze uživatele neukládá přes Intune.

  Povolení tohoto nastavení vyžaduje, aby zařízení:
  - Povolila zjišťování polohy na úrovni operačního systému.
  - Povolit pro portál společnosti používat zjišťování polohy.
  - vyhodnocovat a hlásit do Intune stav jailbreaku minimálně každých 72 hodin. V opačném případě je zařízení označeno jako nedodržující předpisy. Vyhodnocení se aktivuje, otevřete aplikaci portál společnosti nebo fyzickým přesunutím 500 měřiče nebo více zařízení. Pokud zařízení čárka nepohybuje 500 měřiče během 72 hodin, uživatel musí otevřete aplikaci portál společnosti pro vyhodnocení přerušení rozšířené jailbreak.

- **Doba platnosti stavu dodržování předpisů (dny)**: Zadejte časové období, kterého zařízení nahlásí stav všech přijatých zásad dodržování předpisů. Zařízení, která během tohoto období nevrátí stav, se považují za nedodržující předpisy. Výchozí hodnota je 30 dní.

Tyto předdefinované zásady můžete použít k monitorování těchto nastavení. Intune také [aktualizuje nebo znovu zkontroluje aktualizace](create-compliance-policy.md#refresh-cycle-times) v různých intervalech v závislosti na platformě zařízení. [Běžné dotazy, problémy a řešení u profilů v Microsoft Intune a zásad zařízení](device-profile-troubleshoot.md) Dobrým zdrojem informací je.

Sestavy dodržování předpisů představují skvělý způsob, jak můžete kontrolovat stav zařízení. [Monitorování zásad dodržování předpisů](compliance-policy-monitor.md) zahrnuje některé pokyny.

## <a name="non-compliance-and-conditional-access-on-the-different-platforms"></a>Nedodržení předpisů a podmíněného přístupu na různých platformách

Následující tabulka popisuje, jak jsou spravované nevyhovující nastavení při použití zásad dodržování předpisů se zásadami podmíněného přístupu.

---------------------------

|**Nastavení zásad**| **Platforma** |
| --- | ----|
| **Konfigurace kódu PIN nebo hesla** | - **Android 4.0 nebo novější**: V karanténě</br>- **Samsung Knox Standard 4.0 a novější**: V karanténě</br>- **Android Enterprise**: V karanténě</br></br>- **iOS 8.0 a novější**: Opravené</br>- **macOS 10.11 a novější**: Opravené</br></br>- **Windows 8.1 a novější**: Opravené</br>- **Windows Phone 8.1 a novější**: Opravené|
| **Šifrování zařízení** | - **Android 4.0 nebo novější**: V karanténě</br>- **Samsung Knox Standard 4.0 a novější**: V karanténě</br>- **Android Enterprise**: V karanténě</br></br>- **iOS 8.0 a novější**: Opravené (nastavením PIN kódu)</br>- **macOS 10.11 a novější**: Opravené (nastavením PIN kódu)</br></br>- **Windows 8.1 a novější**: Nelze použít</br>- **Windows Phone 8.1 a novější**: Opravené |
| **Zařízení s jailbreakem nebo rootem** | - **Android 4.0 nebo novější**: V karanténě (není nastavení)</br>- **Samsung Knox Standard 4.0 a novější**: V karanténě (není nastavení)</br>- **Android Enterprise**: V karanténě (není nastavení)</br></br>- **iOS 8.0 a novější**: V karanténě (není nastavení)</br>- **macOS 10.11 a novější**: Nelze použít</br></br>- **Windows 8.1 a novější**: Nelze použít</br>- **Windows Phone 8.1 a novější**: Nelze použít |
| **E-mailový profil** | - **Android 4.0 nebo novější**: Nelze použít</br>- **Samsung Knox Standard 4.0 a novější**: Nelze použít</br>- **Android Enterprise**: Nelze použít</br></br>- **iOS 8.0 a novější**: V karanténě</br>- **macOS 10.11 a novější**: V karanténě</br></br>- **Windows 8.1 a novější**: Nelze použít</br>- **Windows Phone 8.1 a novější**: Nelze použít |
| **Minimální verze operačního systému** | - **Android 4.0 nebo novější**: V karanténě</br>- **Samsung Knox Standard 4.0 a novější**: V karanténě</br>- **Android Enterprise**: V karanténě</br></br>- **iOS 8.0 a novější**: V karanténě</br>- **macOS 10.11 a novější**: V karanténě</br></br>- **Windows 8.1 a novější**: V karanténě</br>- **Windows Phone 8.1 a novější**: V karanténě |
| **Maximální verze operačního systému** | - **Android 4.0 nebo novější**: V karanténě</br>- **Samsung Knox Standard 4.0 a novější**: V karanténě</br>- **Android Enterprise**: V karanténě</br></br>- **iOS 8.0 a novější**: V karanténě</br>- **macOS 10.11 a novější**: V karanténě</br></br>- **Windows 8.1 a novější**: V karanténě</br>- **Windows Phone 8.1 a novější**: V karanténě |
| **Ověření stavu Windows** | - **Android 4.0 nebo novější**: Nelze použít</br>- **Samsung Knox Standard 4.0 a novější**: Nelze použít</br>- **Android Enterprise**: Nelze použít</br></br>- **iOS 8.0 a novější**: Nelze použít</br>- **macOS 10.11 a novější**: Nelze použít</br></br>- **Windows 10 a Windows 10 Mobile**: V karanténě</br>- **Windows 8.1 a novější**: V karanténě</br>- **Windows Phone 8.1 a novější**: Nelze použít |

---------------------------

**Opravené**: Operační systém zařízení vynucuje dodržování předpisů. Uživatel musí třeba zadat kód PIN.

**V karanténě**: Operační systém zařízení nebude vynucování dodržování předpisů. Například zařízení s Androidem a s Androidem Enterprise Nevynucovat uživatele šifrovat svoje zařízení. Pokud zařízení nevyhovuje, provedou se následující akce:

  - Pokud se zásady podmíněného přístupu vztahují na uživatele, zařízení se zablokuje.
  - Aplikace portál společnosti upozorní uživatele na všechny problémy s dodržováním předpisů.

## <a name="azure-classic-portal-vs-azure-portal"></a>Portál Azure Classic vs. portál Azure

Hlavním rozdíl při použití zásad dodržování předpisů zařízením na portálu Azure Portal:

- Zásady dodržování předpisů se na portálu Azure Portal vytvářejí zvlášť pro každou podporovanou platformu.
- Na portálu Azure Classic mají všechny podporované platformy společnou jednu zásadu dodržování předpisů zařízeními.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are initiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

Zásady dodržování předpisů vytvořené na [portálu Classic](https://manage.microsoft.com) se na portálu [Azure Portal](https://portal.azure.com) nezobrazují. Pro uživatele ale nadále platí a dají se spravovat prostřednictvím portálu Classic.

Pokud chcete využívat nové funkce související s dodržováním předpisů zařízeními na portálu Azure Portal, musíte vytvořit nové zásady dodržování předpisů zařízeními na portálu Azure Portal. Pokud přiřadíte zásady dodržování předpisů zařízením na Azure Portalu uživateli, kterému byly přiřazeny zásady dodržování předpisů zařízením také na klasickém portálu, budou mít zásady na Azure Portalu přednost před těmi, které byly vytvořeny na klasickém portálu.

## <a name="next-steps"></a>Další postup

- [Vytvořit zásadu](create-compliance-policy.md) a zobrazit požadavky.
- Podívejte se na nastavení dodržování předpisů pro různé platformy zařízení:

  - [Android](compliance-policy-create-android.md)
  - [Android Enterprise](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows 10 a novější](compliance-policy-create-windows.md)
  - [Windows 8.1 a Windows Phone 8.1](compliance-policy-create-windows-8-1.md)

- [Referenční informace pro entity zásad](reports-ref-policy.md) obsahuje informace o entitách zásad datového skladu Intune.