---
title: Vytvoření zásady dodržování předpisů pro zařízení s iOSem v Microsoft Intune – Azure | Microsoft Docs
description: Můžete vytvořit nebo nakonfigurovat zásady dodržování předpisů Microsoft Intune pro zařízení s iOSem k zadání e-mailového účtu, kontrole zařízení s jailbreakem, kontrole minimální a maximální verze operačního systému a nastavení omezení pro heslo, včetně délky hesla a doby nečinnosti zařízení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 35091139e3afaabac4fad0b22fc6096cf7ada7c3
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/01/2018
ms.locfileid: "52728867"
---
# <a name="add-a-device-compliance-policy-for-ios-devices-in-intune"></a>Přidání zásad dodržování předpisů pro zařízení s iOSem v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zásada dodržování předpisů Intune pro zařízení s iOSem určuje pravidla a nastavení, které musí zařízení s iOSem splňovat, aby dodržovalo předpisy. Když používáte zásady dodržování předpisů zařízením s podmíněným přístupem, můžete povolit nebo blokovat přístup k prostředkům společnosti. Můžete také získat sestavy zařízení a provádět akce v případě nedodržování předpisů. Zásady dodržování předpisů zařízením pro každou platformu můžete vytvořit na portálu Intune Azure. Další informace o zásadách dodržování předpisů a případných požadavcích najdete v tématu [Začínáme s dodržováním předpisů](device-compliance-get-started.md).

Následující tabulka popisuje, jak jsou spravované nevyhovující nastavení při použití zásad dodržování předpisů se zásadami podmíněného přístupu.

---------------------------

| **Nastavení zásad** | **iOS 8.0 a novější** |
| --- | --- |
| **Konfigurace kódu PIN nebo hesla** | Opravené |
| **Šifrování zařízení** | Opravené (nastavením PIN kódu) |
| **Zařízení s jailbreakem nebo rootem** | V karanténě (není nastavení)
| **E-mailový profil** | V karanténě |
|**Minimální verze operačního systému** | V karanténě |
| **Maximální verze operačního systému** | V karanténě |
| **Ověření stavu Windows** | Nelze použít |

---------------------------

**Opravené** = operační systém zařízení vynucuje dodržování předpisů. (Uživatel musí třeba zadat kód PIN.)

**V karanténě** = operační systém zařízení nevynucuje dodržování předpisů. (Například zařízení s Androidem nenutí uživatele šifrovat zařízení.) Pokud zařízení nesplňuje předpisy, provedou se následující akce:

- Zařízení se zablokuje, pokud se zásady podmíněného přístupu vztahují na uživatele.
- Portál společnosti oznamuje uživateli všechny problémy s dodržováním předpisů.

## <a name="create-a-device-compliance-policy"></a>Vytváření zásad dodržování předpisů pro zařízení

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. U možnosti **Platforma** vyberte **iOS**. 
5. Zvolte **nastavení konfigurace**a zadejte **e-mailu**, **stav zařízení**, **vlastnosti zařízení**, a **systému Zabezpečení** nastavení popsané v tomto tématu. Po dokončení zvolte **OK** a **Vytvořit**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="email"></a>E-mailu

- **Vyžadovat, aby mobilní zařízení měla spravovaný e-mailový profil**: Pokud nastavíte možnost Vyžadovat, budou se zařízení, která nemají e-mailový profil spravovaný službou Intune, považovat za nedodržující předpisy. Zařízení nemusí mít spravovaný e-mailový profil, pokud není správně zacíleno nebo pokud uživatel e-mailový účet na zařízení nastavil ručně.

  Zařízení je považováno za nedodržující předpisy v následujících situacích:
  - E-mailový profil je nasazený do jiné skupiny uživatelů, než je ta, která cílí na zásady dodržování předpisů.
  - Uživatel na zařízení už nastavil e-mailový účet, který se shoduje s e-mailovým profilem služby Intune nasazeným na zařízení. Intune nemůže přepsat uživatelem zřízený profil, a proto ho nemůže ani spravovat. Aby zařízení dodržovalo předpisy, musí uživatel odebrat stávající nastavení e-mailu. Pak Intune může nainstalovat spravovaný e-mailový profil.

- **Vyberte e-mailový profil, který se musí spravovat přes Intune**: Pokud je vybraná možnost **E-mailový účet se musí spravovat přes Intune**, zvolte **Vybrat** a nastavte e-mailový profil Intune. Tento e-mailový profil musí být na zařízení.

Podrobnosti o e-mailových profilech najdete v tématu [Konfigurace přístupu k podnikovému e-mailu pomocí e-mailových profilů v Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune).

## <a name="device-health"></a>Device health

- **Zařízení s Jailbreakem**: Pokud toto nastavení povolíte, zařízení s jailbreakem nebudou dodržovat předpisy.
- **Vyžadovat, aby zařízení bylo na určité úrovni hrozby pro zařízení nebo pod ní** (iOS 8.0 a novější): Zvolte maximální úroveň hrozby, nad kterou se zařízení označí jako nedodržující předpisy. Zařízení, která tuto úroveň hrozby překročí, se označí jako nedodržující předpisy:
  - **Zabezpečeno**: Tato možnost je nejbezpečnější, protože zařízení nesmí být nijak ohroženo. Pokud se v zařízení zjistí libovolná úroveň hrozeb, vyhodnotí se jako nedodržující předpisy.
  - **Nízká:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm nachází i jen nízká úroveň hrozeb. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední**: Zařízení se vyhodnotí jako vyhovující, pokud se existující hrozby pohybují na střední nebo nízké úrovni. Pokud se zjistí, že zařízení má i hrozby vysoké úrovně, bude vyhodnoceno jako nedodržující předpisy.
  - **Vysoká**: Tato možnost je nejméně bezpečná a umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.

## <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální požadovaný operační systém**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nekompatibilní. Zobrazí se odkaz s informacemi, jak upgradovat. Uživatel může zvolit upgrade svého zařízení. Pak může přistupovat k prostředkům společnosti.
- **Maximální povolená verze OS**: Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nebude mít toto zařízení přístup k prostředkům společnosti.
- **Minimální operační systém sestavení verze**: když Apple publikuje aktualizace zabezpečení, je obvykle aktualizovat číslo sestavení, verzi operačního systému. Pomocí této funkce lze zadat číslo minimální povolenou sestavení na zařízení. Tato kontrola dodržování předpisů se podporuje zařízení se systémem iOS 8.0 a novější. 
- **Maximální verze operačního systému sestavení verze**: když Apple publikuje aktualizace zabezpečení, je obvykle aktualizovat číslo sestavení, verzi operačního systému. Pomocí této funkce lze zadat maximální povolené sestavení číslo na zařízení. Tato kontrola dodržování předpisů se podporuje zařízení se systémem iOS 8.0 a novější.

## <a name="system-security"></a>Zabezpečení systému

### <a name="password"></a>Heslo

> [!NOTE]
> Po použití zásad dodržování předpisů nebo konfigurace u zařízení s iOSem se uživatelům bude každých 15 minut zobrazovat výzva k nastavení hesla. Uživatelům se výzva bude zobrazovat tak dlouho, dokud heslo nenastaví.

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadujte**, aby uživatelé před získáním přístupu ke svému zařízení zadali heslo. Zařízení s iOSem, která používají heslo, jsou zašifrovaná.
- **Jednoduchá hesla**: Pokud nastavíte **Blokovat**, nebudou moct uživatelé vytvořit jednoduchá hesla, jako je třeba **1234** nebo **1111**. Pokud chcete uživatelům umožnit vytváření hesel jako **1234** nebo **1111**, nastavte na **Nenakonfigurováno**.
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Požadovaný typ hesla**: Zvolte, jestli má heslo obsahovat pouze **číselné** znaky nebo jestli má obsahovat kombinaci čísel a dalších znaků (**alfanumerické**).
- **Počet nealfanumerických znaků v hesle**: Zadejte minimální počet speciálních znaků (&, #, %, ! a podobně), které musí heslo obsahovat.

    Po nastavení vyššího čísla bude uživatel muset vytvořit složitější heslo.

- **Maximální počet minut nečinnosti, po kterém bude nutné zadat heslo**: Zadejte dobu nečinnosti, která musí uplynout, aby se po uživateli znovu požadovalo zadání hesla.
- **Konec platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která se nesmí použít znovu**: Zadejte počet dříve použitých hesel, která se nesmí znovu použít.

### <a name="restricted-applications"></a>Omezené aplikace 
Aplikace můžete omezit přidáním jejich ID sady prostředků do zásady. Pokud si uživatel aplikaci nainstaluje na zařízení, označí se toto zařízení jako nevyhovující předpisům. 
- **Název aplikace**: Zadejte popisný název, který vám pomůže dané ID sady prostředků identifikovat. 
- **ID sady prostředků aplikace**: Zadejte jedinečný identifikátor sady prostředků přidělený poskytovatelem aplikace. Pokud potřebujete ID vyhledat, přečtěte si článek o [postupu nalezení ID sady prostředků aplikací pro iOS](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app).  

## <a name="assign-user-groups"></a>Přiřazení skupin uživatelů

1. Vyberte zásadu, kterou jste nakonfigurovali. Existující zásady najdete v **Dodržování předpisů zařízením** > **Zásady**.
2. Zvolte zásady a pak **Přiřazení**. Můžete zahrnout nebo vyloučit skupiny zabezpečení služby Azure Active Directory (AD).
3. Vyberte **Vybrané skupiny** a zobrazte skupiny zabezpečení Azure AD. Můžete vybrat skupiny uživatelů, na které chcete zásady použít, a pak pomocí **Uložit** tyto zásady uživatelům nasadit.

Tím jste zásady uplatnili u uživatelů. U zařízení používaných uživateli, na které zásady cílí, se vyhodnotí dodržování předpisů.

## <a name="next-steps"></a>Další postup
[Automatické e-maily a přidání akcí pro zařízení nedodržující předpisy](actions-for-noncompliance.md)  
[Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md)
