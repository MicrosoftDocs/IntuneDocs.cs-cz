---
title: Vytvoření zásady dodržování předpisů pro zařízení s Windows v Microsoft Intune – Azure | Microsoft Docs
description: Vytvořte nebo nakonfigurujte zásady dodržování předpisů pro zařízení v Microsoft Intune pro Windows Phone 8.1, Windows 8.1 nebo novější a Windows 10 Mobile nebo novější. Kontrolujte dodržování minimální a maximální verze operačního systému, nastavte délku a další omezení hesel, vyžadujte nástroj BitLocker, zjistěte antivirová řešení jiných výrobců, nastavte přijatelnou úroveň hrozeb a povolte šifrování v úložišti dat, včetně Surface Hubu a Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 11ccace4ca8e43e09b8aebeb92530629cf50a472
ms.sourcegitcommit: bea4a81d262607c6e9dd1e26f5cd1a2faf7d051b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/14/2018
ms.locfileid: "45602312"
---
# <a name="add-a-device-compliance-policy-for-windows-devices-in-intune"></a>Přidání zásad dodržování předpisů pro zařízení s Windows v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zásada dodržování předpisů Intune pro zařízení s Windows určuje pravidla a nastavení, které musí zařízení s Windows splňovat, aby bylo považováno za dodržující předpisy. Pomocí těchto zásad s podmíněným přístupem můžete povolit nebo zablokovat přístup k prostředkům společnosti. Můžete také získat sestavy zařízení a provádět akce v případě nedodržování předpisů. Zásady dodržování předpisů zařízení pro každou platformu vytvoříte na portálu Intune Azure. Další informace o zásadách dodržování předpisů a případných požadavcích najdete v tématu [Začínáme s dodržováním předpisů](device-compliance-get-started.md).

Následující tabulka popisuje, jak jsou spravované nevyhovující nastavení při použití zásad dodržování předpisů se zásadami podmíněného přístupu.

---------------------------

| **Nastavení zásad** | **Windows 8.1 a novější** | **Windows Phone 8.1 a novější** |
|----| ----| --- |
| **Konfigurace kódu PIN nebo hesla** | Opravené | Opravené |   
| **Šifrování zařízení** | Nelze použít | Opravené |   
| **Zařízení s jailbreakem nebo rootem** | Nelze použít | Nelze použít |  
| **E-mailový profil** | Nelze použít | Nelze použít |   
| **Minimální verze operačního systému** | V karanténě | V karanténě |   
| **Maximální verze operačního systému** | V karanténě | V karanténě |   
| **Ověření stavu Windows** | V karanténě: Windows 10 a Windows 10 Mobile|Nelze použít: Windows 8.1 |

-------------------------------

**Opravené** = operační systém zařízení vynucuje dodržování předpisů. (Uživatel musí třeba zadat kód PIN.)

**V karanténě** = operační systém zařízení nevynucuje dodržování předpisů. (Například zařízení s Androidem nenutí uživatele šifrovat zařízení.) Pokud zařízení nesplňuje předpisy, provedou se následující akce:

- Zařízení se zablokuje, pokud se zásady podmíněného přístupu vztahují na uživatele.
- Portál společnosti oznamuje uživateli všechny problémy s dodržováním předpisů.

## <a name="create-a-device-compliance-policy"></a>Vytváření zásad dodržování předpisů pro zařízení

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. Pro položku **Platforma** vyberte **Windows Phone 8.1**, **Windows 8.1 a novější** nebo **Windows 10 a novější**.
6. Zvolte **Nastavení – Konfigurace** a zadejte nastavení **Stav zařízení**, **Vlastnosti zařízení** a **Zabezpečení systému**. Po dokončení zvolte **OK** a **Vytvořit**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="windows-81-devices-policy-settings"></a>Nastavení zásad pro zařízení s Windows 8.1

Tato nastavení zásad platí pro zařízení s následujícími platformami:

- Windows Phone 8.1
- Windows 8.1 a vyšší

### <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální požadovaný operační systém**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, nahlásí se jako nevyhovující. Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může zařízení upgradovat. Potom získá přístup k prostředkům společnosti.
- **Maximální povolená verze OS**: Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nebude mít toto zařízení přístup k prostředkům společnosti.

Počítače s Windows 8.1 vrací verzi **3**. Pokud je pravidlo verze operačního systému pro Windows nastavené na Windows 8.1, bude se zařízení uvádět jako nekompatibilní i v případě, že bude používat Windows 8.1.

### <a name="system-security"></a>Zabezpečení systému

#### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadujte**, aby uživatelé před získáním přístupu ke svému zařízení zadali heslo.
- **Jednoduchá hesla**: Pokud nastavíte **Blokovat**, nebudou moct uživatelé vytvořit jednoduchá hesla, jako je třeba **1234** nebo **1111**. Pokud chcete uživatelům umožnit vytváření hesel jako **1234** nebo **1111**, nastavte na **Nenakonfigurováno**.
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.

  Pro zařízení s Windows, ke kterým uživatelé přistupují pomocí účtu Microsoft, se zásady dodržování předpisů nevyhodnotí správně:
  - Pokud je minimální délka hesla větší než osm znaků
  - Nebo pokud je minimální počet znakových sad větší než dvě

- **Typ hesla**: Zvolte, jestli má heslo obsahovat pouze **číselné** znaky, nebo jestli má obsahovat kombinaci čísel a dalších znaků (**alfanumerické**).
  
  - **Počet nealfanumerických znaků v hesle**: Pokud se **Požadovaný typ hesla** nastaví na **Alfanumerické**, určuje toto nastavení minimální počet znakových sad, které musí heslo obsahovat. Jde o tyto čtyři znakové sady:
    - Malá písmena
    - Velká písmena
    - Symboly
    - Numbers

    Po nastavení vyššího čísla bude uživatel muset vytvořit složitější heslo. U zařízení s Windows a účtem Microsoft používaným pro přístup se zásada dodržování předpisů nevyhodnotí správně, pokud bude minimální délka hesla větší než osm znaků nebo bude minimální počet znakových sad větší než dvě.

- **Maximální počet minut nečinnosti, po kterém bude nutné zadat heslo**: Zadejte dobu nečinnosti, která musí uplynout, aby se po uživateli znovu požadovalo zadání hesla.
- **Konec platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která se nesmí použít znovu**: Zadejte počet dříve použitých hesel, která se nesmí znovu použít.

#### <a name="encryption"></a>Šifrování

- **Vyžadovat šifrování u mobilního zařízení:** **Vyžaduje**, aby zařízení přistupující k prostředkům datového úložiště bylo šifrované.

## <a name="windows-10-and-later-policy-settings"></a>Nastavení zásad pro Windows 10 a novější

### <a name="device-health"></a>Device health

- **Vyžadovat BitLocker**: Když je nástroj BitLocker zapnutý, zařízení je při vypnutém systému nebo v režimu hibernace schopné chránit data uložená na disku před neoprávněným přístupem. Nástroj Windows BitLocker Drive Encryption zašifruje všechna data uložená na svazku operačního systému Windows. BitLocker používá k ochraně operačního systému Windows a uživatelských dat čip TPM. Také pomáhá zajistit, aby se s počítačem nemanipulovalo ani v případě, že je ponechaný bez dozoru, ztracený nebo odcizený. Pokud je počítač vybavený kompatibilním čipem TPM, nástroj BitLocker pomocí čipu TPM uzamkne šifrovací klíče, které chrání data. V důsledku toho se ke klíčům nedá získat přístup, dokud čip TPM neověří stav počítače.
- **Vyžadovat, aby na zařízení bylo povolené zabezpečené spuštění**: Pokud je povolené zabezpečené spouštění, musí se systém spouštět do důvěryhodného stavu z výroby. Kromě toho platí, že při povoleném zabezpečeném spouštění musí mít komponenty jádra sloužící ke spuštění počítače správné kryptografické podpisy, které jsou podle výrobce zařízení důvěryhodné. Firmware UEFI nejdříve ověří podpis a až potom povolí spuštění počítače. Pokud u některých souborů došlo k manipulaci, při které se porušil podpis, systém se nespustí.

  > [!NOTE]
  > Nastavení **Vyžadovat, aby na zařízení bylo povolené zabezpečené spuštění** je podporované na zařízeních s čipem TPM 1.2 a 2.0. Pokud zařízení nepodporují TPM 2.0 nebo novější, zobrazí se v Intune stav zásady jako **nevyhovující**. Jde o omezení služby [Ověření stavu zařízení](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation) ve Windows 10.

- **Vyžadovat integritu kódu**: Integrita kódu je funkce, která ověřuje integritu ovladače nebo systémového souboru při každém načtení do paměti. Integrita kódu zjistí, jestli se do jádra načítá nepodepsaný ovladač nebo systémový soubor. Nebo jestli systémový soubor nebyl změněn škodlivým softwarem spuštěným pomocí uživatelského účtu s oprávněními správce.

Podrobnosti o fungování služby pro ověření stavu najdete v tématu o [poskytovateli CSP služby pro ověření stavu](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp).

Pokud chcete Ochranu ATP v programu Windows Defender (rozšířenou ochranu před internetovými útoky) nastavit jako službu ochrany před hrozbami, přečtěte si téma [Povolení Ochrany ATP v programu Windows Defender s podmíněným přístupem](advanced-threat-protection.md).

### <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální verze OS**: Zadejte minimální povolenou verzi ve formátu **hlavní verze.podverze.sestavení.číslo CU**. Správnou hodnotu získáte, když otevřete příkazový řádek a zadáte `ver`. Příkaz `ver` vrátí verzi v následujícím formátu:

  `Microsoft Windows [Version 10.0.17134.1]`

  Pokud má zařízení starší verzi operačního systému, než je zadaná verze, uvede se jako nekompatibilní. Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může upgradovat svoje zařízení. Potom bude mít přístup k prostředkům společnosti.

- **Maximální verze OS**: Zadejte maximální povolenou verzi ve formátu **hlavní verze.podverze.sestavení.číslo revize**. Správnou hodnotu získáte, když otevřete příkazový řádek a zadáte `ver`. Příkaz `ver` vrátí verzi v následujícím formátu:

  `Microsoft Windows [Version 10.0.17134.1]`

  Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.

- **Minimální verze operačního systému pro mobilní zařízení**: Zadejte minimální povolenou verzi ve formátu major.minor.build.

  Pokud má zařízení starší verzi operačního systému, než je zadaná verze, uvede se jako nekompatibilní. Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může upgradovat svoje zařízení. Potom bude mít přístup k prostředkům společnosti.

- **Maximální verze operačního systému pro mobilní zařízení**: Zadejte maximální povolenou verzi ve formátu major.minor.build.

  Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.

- **Platná sestavení operačního systému**: Zadejte rozsah pro povolené verze operačního systému, včetně minimální a maximální. Seznam vyhovujících čísel buildů operačních systémů také můžete **exportovat** do textového souboru CSV s oddělovači.

### <a name="system-security-settings"></a>Systémové nastavení zabezpečení

#### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadujte**, aby uživatelé před získáním přístupu ke svému zařízení zadali heslo.
- **Jednoduchá hesla**: Pokud nastavíte **Blokovat**, nebudou moct uživatelé vytvořit jednoduchá hesla, jako je třeba **1234** nebo **1111**. Pokud chcete uživatelům umožnit vytváření hesel jako **1234** nebo **1111**, nastavte na **Nenakonfigurováno**.
- **Typ hesla**: Zvolte, jestli má heslo obsahovat pouze **číselné** znaky, nebo jestli má obsahovat kombinaci čísel a dalších znaků (**alfanumerické**).

  - **Počet nealfanumerických znaků v hesle**: Pokud se **Požadovaný typ hesla** nastaví na **Alfanumerické**, určuje toto nastavení minimální počet znakových sad, které musí heslo obsahovat. Jde o tyto čtyři znakové sady:
    - Malá písmena
    - Velká písmena
    - Symboly
    - Numbers

    Po nastavení vyššího čísla bude uživatel muset vytvořit složitější heslo.

- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Maximální počet minut nečinnosti, po kterém bude nutné zadat heslo**: Zadejte dobu nečinnosti, která musí uplynout, aby se po uživateli znovu požadovalo zadání hesla.
- **Konec platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která se nesmí použít znovu**: Zadejte počet dříve použitých hesel, která se nesmí znovu použít.
- **Vyžadovat heslo při návratu zařízení ze stavu nečinnosti (Mobile a Holographic)**: Vynutí zadání hesla uživatelem při každém návratu zařízení ze stavu nečinnosti.

#### <a name="encryption"></a>Šifrování

- **Šifrování úložiště dat na zařízení**: Vyberte **Vyžadovat** a zašifrujte úložiště dat na vašich zařízeních.

#### <a name="device-security"></a>Zabezpečení zařízení

- **Antivirus**: Když je tato možnost nastavená na **Vyžadovat**, můžete dodržování předpisů kontrolovat pomocí antivirových řešení (například Symantec nebo Windows Defender), která jsou registrovaná Centrem zabezpečení Windows. Pokud **není nakonfigurovaná**, nezjišťuje Intune žádná antivirová řešení nainstalovaná v zařízení.
- **Antispyware**: Když je tato možnost nastavená na **Vyžadovat**, můžete dodržování předpisů kontrolovat pomocí antispywarových řešení (například Symantec nebo Windows Defender), která jsou registrovaná Centrem zabezpečení Windows. Pokud **není nakonfigurovaná**, nezjišťuje Intune žádná antispywarová řešení nainstalovaná v zařízení.

### <a name="windows-defender-atp"></a>Ochrana ATP v programu Windows Defender

- **Vyžadovat, aby zařízení mělo určité nebo nižší skóre rizika počítače**: Toto nastavení použijte, pokud chcete jako podmínku dodržování předpisů použít vyhodnocování rizika z vašich služeb ochrany před hrozbami. Vyberte maximální povolenou úroveň hrozby:
  - **Vymazat**: Tato možnost je nejbezpečnější, protože zařízení nesmí být nijak ohroženo. Pokud se v zařízení zjistí libovolná úroveň hrozeb, vyhodnotí se jako nedodržující předpisy.
  - **Nízká:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm nachází i jen nízká úroveň hrozeb. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední**: Zařízení se vyhodnotí jako vyhovující, pokud se existující hrozby pohybují na střední nebo nízké úrovni. Pokud se zjistí, že zařízení má i hrozby vysoké úrovně, bude vyhodnoceno jako nedodržující předpisy.
  - **Vysoká**: Tato možnost je nejméně bezpečná a umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Windows Holographic for Business používá platformu **Windows 10 a novější**. Windows Holographic for Business podporuje následující nastavení:

- **Zabezpečení systému** > **Šifrování** > **Šifrování datového úložiště na zařízení**.

Pokud chcete ověřit šifrování u zařízení Microsoft HoloLens, přečtěte si článek [Ověření šifrování zařízení](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption).

## <a name="surface-hub"></a>Surface Hub
Surface Hub používá platformu **Windows 10 a novější**. Zařízení Surface Hub podporují dodržování předpisů i podmíněný přístup. Pokud chcete tyto funkce na zařízeních Surface Hub povolit, doporučujeme [povolit automatickou registraci Windows 10](windows-enroll.md) v Intune (vyžaduje také Azure Active Directory (AAD)) a cílit na zařízení Surface Hub jako na skupiny zařízení. Zařízení Surface Hub je potřeba propojit s Azure Active Directory, aby se zajistilo dodržování předpisů a podmíněný přístup k funkci.

Pokyny najdete v článku [Nastavení registrace pro zařízení s Windows](windows-enroll.md).

## <a name="assign-user-or-device-groups"></a>Přiřazení skupin uživatelů nebo zařízení

1. Vyberte zásadu, kterou jste nakonfigurovali. Existující zásady najdete v **Dodržování předpisů zařízením** > **Zásady**.
2. Zvolte zásady a pak **Přiřazení**. Můžete zahrnout nebo vyloučit skupiny zabezpečení služby Azure AD.
3. Vyberte **Vybrané skupiny** a zobrazte skupiny zabezpečení Azure AD. Můžete vybrat skupiny uživatelů nebo zařízení, na které chcete zásady použít, a pak zvolením možnosti **Uložit** tyto zásady uživatelům nasadit.

Nasazení zásad je dokončeno. U zařízení používaných uživateli, na které zásady cílí, se vyhodnotí dodržování předpisů.

## <a name="next-steps"></a>Další kroky
[Automatické e-maily a přidání akcí pro zařízení nedodržující předpisy](actions-for-noncompliance.md)  
[Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md)
