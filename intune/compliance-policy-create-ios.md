---
title: Vytvoření zásady dodržování předpisů pro zařízení s iOSem v Microsoft Intune – Azure | Microsoft Docs
description: Můžete vytvořit zásady dodržování předpisů Microsoft Intune pro zařízení s iOSem k zadání e-mailového účtu, kontrole zařízení s jailbreakem, kontrole minimální a maximální verze operačního systému a nastavení omezení pro heslo včetně délky hesla a doby nečinnosti zařízení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b05eb725adb61ae47a24ca884d0e73ffe0dd269f
ms.sourcegitcommit: a22309174e617e59ab0cdd0a55abde38711a5f35
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/23/2018
---
# <a name="add-a-device-compliance-policy-for-ios-devices-in-intune"></a>Přidání zásad dodržování předpisů pro zařízení s iOSem v Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zásada dodržování předpisů Intune pro zařízení s iOSem určuje pravidla a nastavení, které musí zařízení s iOSem splňovat, aby dodržovalo předpisy. Když používáte zásady dodržování předpisů zařízením s podmíněným přístupem, můžete povolit nebo blokovat přístup k prostředkům společnosti. Můžete také získat sestavy zařízení a provádět akce v případě nedodržování předpisů. Zásady dodržování předpisů zařízením pro každou platformu můžete vytvořit na portálu Intune Azure. Další informace o zásadách dodržování předpisů a potřebných požadavcích před vytvořením zásad dodržování předpisů najdete v tématu [Začínáme se zásadami dodržování předpisů zařízeními](device-compliance-get-started.md).

Následující tabulka popisuje, jak jsou spravované nevyhovující nastavení při použití zásad dodržování předpisů se zásadami podmíněného přístupu.

| **Nastavení zásad** | **iOS 8.0 a novější** |
| --- | --- |
| **Konfigurace kódu PIN nebo hesla** | Opravené |
| **Šifrování zařízení** | Opravené (nastavením PIN kódu) |
| **Zařízení s jailbreakem nebo rootem** | V karanténě (není nastavení)
| **E-mailový profil** | V karanténě |
|**Minimální verze operačního systému** | V karanténě |
| **Maximální verze operačního systému** | V karanténě |
| **Ověření stavu Windows** | Nelze použít |

**Opravené** = operační systém zařízení vynucuje dodržování předpisů. (Uživatel musí třeba zadat kód PIN.)

**V karanténě** = operační systém zařízení nevynucuje dodržování předpisů. (Například zařízení s Androidem nenutí uživatele šifrovat zařízení.) Pokud zařízení nesplňuje předpisy, provedou se následující akce:

- Zařízení se zablokuje, pokud se zásady podmíněného přístupu vztahují na uživatele.
- Portál společnosti oznamuje uživateli všechny problémy s dodržováním předpisů.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Vytvoření zásad dodržování předpisů na portálu Azure Portal

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**.
4. Zadejte název a popis a zvolte platformu, na kterou chcete zásadu použít.
5. Zvolte **Nastavení**, kde můžete zadat nastavení **E-mail**, **Stav zařízení**, **Vlastnosti zařízení** a **Zabezpečení systému**. Po dokončení vyberte **OK**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Přiřazení skupin uživatelů

Pokud chcete přiřadit zásady dodržování předpisů uživatelům, vyberte zásady, které jste nakonfigurovali. Existující zásady najdete v podokně **Dodržování předpisů zařízením – Zásady**.

1. Vyberte zásady, které chcete přiřadit uživatelům, a zvolte **Přiřazení**. Otevře se podokno, kde můžete vybrat **skupiny zabezpečení Azure Active Directory** a přiřadit je k zásadám.
2. Zvolte **Vybrat skupiny** a otevřete tak podokno, kde se zobrazí skupiny zabezpečení v Azure AD.  Pomocí **Uložit** se zásada nasadí uživatelům.

Tím jste zásady uplatnili u uživatelů.  U zařízení používaných uživateli, na které zásady cílí, se vyhodnotí dodržování předpisů.

<!---## Compliance policy settings--->

## <a name="email"></a>E-mailu

- **E-mailový účet se musí spravovat přes Intune**: Pokud je tato možnost nastavená na hodnotu **Ano**, zařízení musí používat e-mailový profil nasazený na zařízení. Zařízení je považováno za nedodržující předpisy v následujících situacích:
  - E-mailový profil je nasazený do jiné skupiny uživatelů, než je ta, která cílí na zásady dodržování předpisů.
  - Uživatel na zařízení už nastavil e-mailový účet, který se shoduje s e-mailovým profilem služby Intune nasazeným na zařízení. Intune nemůže přepsat uživatelem zřízený profil, a proto ho nemůže ani spravovat. Aby zařízení dodržovalo předpisy, musí uživatel odebrat stávající nastavení e-mailu. Pak Intune může nainstalovat spravovaný e-mailový profil.
- **Vyberte e-mailový profil, který se musí spravovat přes Intune**: Pokud je vybraná možnost **E-mailový účet se musí spravovat přes Intune**, zvolte **Vybrat** a nastavte e-mailový profil Intune. Tento e-mailový profil musí být na zařízení.

Podrobnosti o e-mailových profilech najdete v tématu [Konfigurace přístupu k podnikovému e-mailu pomocí e-mailových profilů v Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune).

## <a name="device-health"></a>Device health

- **Zařízení s Jailbreakem**: Pokud toto nastavení povolíte, zařízení s jailbreakem nebudou dodržovat předpisy.
- **Vyžadovat, aby zařízení bylo na určité úrovni hrozby pro zařízení nebo pod ní**: Zvolte maximální úroveň hrozby, nad kterou se zařízení označí jako nedodržující předpisy. Pokud třeba úroveň hrozby nastavíte na **Střední**, pak zařízení na úrovních střední, nízké nebo zabezpečené dodržují předpisy. Zařízení s vysokou úrovní hrozby předpisy nedodržují.

## <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální požadovaný operační systém**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nekompatibilní. Zobrazí se odkaz s informacemi, jak upgradovat. Uživatel může zvolit upgrade svého zařízení. Pak může přistupovat k prostředkům společnosti.
- **Maximální povolená verze OS**: Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nebude mít toto zařízení přístup k prostředkům společnosti.

## <a name="system-security"></a>Zabezpečení systému

### <a name="password"></a>Heslo

> [!NOTE]
> Po použití zásad dodržování předpisů nebo konfigurace u zařízení s iOSem se uživatelům bude každých 15 minut zobrazovat výzva k nastavení hesla. Uživatelům se výzva bude zobrazovat tak dlouho, dokud heslo nenastaví.

- **Vyžadovat heslo k odemknutí mobilních zařízení:** Pokud tuto možnost nastavíte na **Ano**, bude uživatel muset zadat heslo, aby získal přístup ke svému zařízení. Zařízení s iOSem, která používají heslo, jsou zašifrovaná.
- **Jednoduchá hesla**: Pokud tuto možnost nastavíte na **Ano**, umožníte uživateli vytvářet hesla jako **1234** nebo **1111**.
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Vyžadovaný typ hesla:** Zadejte, jestli musí uživatel vytvořit **Alfanumerické** nebo **Číselné** heslo.
- **Počet nealfanumerických znaků v hesle**: Zadejte minimální počet speciálních znaků (&, #, %, ! a podobně), které musí heslo obsahovat.

    Po nastavení vyššího čísla bude uživatel muset vytvořit složitější heslo.

- **Maximální počet minut nečinnosti, po kterém bude nutné zadat heslo**: Zadejte dobu nečinnosti, která musí uplynout, aby se po uživateli znovu požadovalo zadání hesla.
- **Konec platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která se nesmí použít znovu**: Zadejte počet dříve použitých hesel, která se nesmí znovu použít.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
