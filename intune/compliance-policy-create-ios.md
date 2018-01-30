---
title: "Vytváření zásad dodržování předpisů pro iOS"
titleSuffix: Azure portal
description: "Naučte se vytvářet zásady dodržování předpisů pro zařízení s iOSem."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d4676a199f3d52ac5ed1c1661fdfe3e024eadf54
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-ios-devices-in-intune"></a>Vytvoření zásad dodržování předpisů pro zařízení s iOSem v Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zásady dodržování předpisů se vytvářejí pro jednotlivé platformy.  Zásady dodržování předpisů můžete vytvořit na portálu Azure Portal. Další informace o tom, co jsou zásady dodržování předpisů najdete v tématu [Co jsou zásady dodržování předpisů u zařízení](device-compliance.md). Další informace o požadavcích, kterým je potřeba vyhovět před vytvořením zásad dodržování předpisů, najdete v tématu [Začínáme se zásadami dodržování předpisů u zařízení](device-compliance-get-started.md).

Tabulka níže popisuje, jak se postupuje u nevyhovujícího nastavení při použití zásad dodržování předpisů se zásadami podmíněného přístupu.

-------------------------------


| **Nastavení zásad** | **iOS 8.0 a novější** |
| --- | --- |
| **Konfigurace kódu PIN nebo hesla** | Opravené |   
| **Šifrování zařízení** | Opravené (nastavením PIN kódu) |
| **Zařízení s jailbreakem nebo rootem** | V karanténě (není nastavení)
| **E-mailový profil** | V karanténě |
|**Minimální verze operačního systému** | V karanténě |
| **Maximální verze operačního systému** | V karanténě |  
| **Ověření stavu Windows** | Nelze použít |  
----------------------------


**Opravené** = operační systém zařízení vynucuje dodržování předpisů. (Uživatel musí třeba zadat kód PIN.)

**V karanténě** = operační systém zařízení nevynucuje dodržování předpisů. (Například zařízení s Androidem nenutí uživatele šifrovat zařízení.) Pokud zařízení nesplňuje předpisy, provedou se následující akce:

- Zařízení se zablokuje, pokud se zásady podmíněného přístupu vztahují na uživatele.
- Portál společnosti oznamuje uživateli všechny problémy s dodržováním předpisů.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Vytvoření zásad dodržování předpisů na portálu Azure Portal

1. V okně **Intune** zvolte **Nastavit dodržování předpisů zařízením**. V části **Správa** zvolte možnost pro **Všechny zásady dodržování předpisů zařízení** a zvolte **Vytvořit**.
2. Zadejte název a popis a zvolte platformu, u které chcete použít tyto zásady.
3. Zvolte **Požadavky na dodržování předpisů** a zadejte nastavení pro **Zabezpečení**, **Stav zařízení** a **Vlastnosti zařízení**. Až to budete mít, klikněte na **OK**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Přiřazení skupin uživatelů

Pokud chcete přiřadit zásady dodržování předpisů uživatelům, vyberte zásady, které jste nakonfigurovali. Existující zásady najdete v okně **Dodržování předpisů – zásady**.

1. Vyberte zásady, které chcete přiřadit uživatelům, a zvolte **Přiřazení**. Otevře se okno, kde můžete vybrat **skupiny zabezpečení Azure Active Directory** a přiřadit je k zásadám.
2. Zvolte **Vybrat skupiny** a otevřete tak okno, ve kterém se zobrazí skupiny zabezpečení v Azure AD.  Po zvolení možnosti **Vybrat** se zásady nasadí u uživatelů.

Zásady jsou teď použité u uživatelů.  U zařízení používaných uživateli, kteří jsou cílem zásad, se bude vyhodnocovat dodržování předpisů.

<!---## Compliance policy settings--->

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: Pokud tuto možnost nastavíte na **Ano**, budou muset uživatelé zadat heslo, aby mohli získat přístup ke svému zařízení. Zařízení s iOSem, která používají heslo, jsou zašifrovaná.
- **Povolit jednoduchá hesla**: Pokud tuto možnost nastavíte na **Ano**, umožníte uživateli vytvářet jednoduchá hesla, třeba **1234** nebo **1111**.
- **Minimální délka hesla**: Určuje minimální počet číslic nebo znaků, které musí obsahovat heslo uživatele.
- **Požadovaný typ hesla**: Určuje, jestli musí uživatel vytvořit **Alfanumerické** nebo **Číselné** heslo.
- **Minimální počet znakových sad**: Pokud nastavíte **Požadovaný typ hesla** na možnost **Alfanumerické**, určuje toto nastavení nejmenší počet znakových sad, které musí heslo mít. Jde o tyto čtyři znakové sady:
  - Malá písmena
  - Velká písmena
  - Symboly
  - Numbers

Po nastavení vyššího čísla bude uživatel muset vytvořit složitější heslo.

Pro zařízení se systémem iOS toto nastavení určuje počet speciálních znaků (třeba **!** , **#**, **&amp;**), které musí heslo obsahovat.

- **Počet minut nečinnosti před vyžádáním hesla**: Určuje dobu nečinnosti, než bude muset uživatel znovu zadat heslo.
- **Konec platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Pamatovat si historii hesel**: Pokud chcete zabránit uživatelům ve vytváření hesel, která používali dřív, použijte toto nastavení spolu s nastavením **Zakázat opakované použití předchozích hesel**.
- **Zakázat opakované použití předchozích hesel**: Pokud jste vybrali možnost **Pamatovat si historii hesel**, zadejte počet předchozích hesel, která se nesmí znovu použít.
- **Po návratu zařízení ze stavu nečinnosti vyžadovat heslo**: Toto nastavení použijte v kombinaci s nastavením **Počet minut nečinnosti před vyžádáním hesla**. Pro přístup k zařízení, které bylo nečinné po dobu uvedenou v nastavení **Počet minut nečinnosti před vyžádáním hesla**, se uživatelům zobrazí výzva k zadání hesla.

### <a name="email-profile"></a>e-mailový profil

- **E-mailový účet musí být spravovaný přes Intune**: Pokud je tato možnost nastavená na hodnotu **Ano**, musí zařízení používat e-mailový profil nasazený na zařízení. Zařízení je považováno za nedodržující předpisy v následujících situacích:
  - E-mailový profil je nasazený do jiné skupiny uživatelů, než je ta, která cílí na zásady dodržování předpisů.
  - Uživatel na zařízení už nastavil e-mailový účet, který se shoduje s e-mailovým profilem služby Intune nasazeným na zařízení. Intune nemůže přepsat uživatelem zřízený profil, a proto ho nemůže ani spravovat. Aby zařízení dodržovalo předpisy, musí uživatel odebrat stávající nastavení e-mailu. Pak Intune může nainstalovat spravovaný e-mailový profil.
- **Vyberte e-mailový profil, který se musí spravovat přes Intune**: Pokud je vybraná možnost **E-mailový účet musí být spravovaný přes Intune**, zvolte **Vybrat** a nastavte e-mailový profil Intune. Tento e-mailový profil musí být na zařízení.

Podrobnosti o e-mailových profilech najdete v tématu [Konfigurace přístupu k podnikovému e-mailu pomocí e-mailových profilů v Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune).

## <a name="device-health-settings"></a>Nastavení stavu zařízení

- **Zařízení nesmí mít jailbreak ani root**: Pokud povolíte toto nastavení, budou se zařízení s jailbreakem považovat za nevyhovující předpisům.

## <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální verze OS**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nekompatibilní. Zobrazí se odkaz s informacemi, jak upgradovat. Uživatel může zvolit upgrade svého zařízení. Pak může přistupovat k prostředkům společnosti.
- **Maximální verze OS**: Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
