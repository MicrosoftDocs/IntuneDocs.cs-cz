---
title: "Vytváření zásad dodržování předpisů pro Windows"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si, jak vytvořit zásady dodržování předpisů pro zařízení s Windows."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 13fc7783-d4de-47d0-b1b8-4c8710a9e6ab
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 5a50f4abea58a39b18347d03bb1553856d592c93
ms.lasthandoff: 02/18/2017


---
# <a name="how-to-create-a-device-compliance-policy-for-windows-devices-in-intune-azure-preview"></a>Vytvoření zásad dodržování předpisů pro zařízení s Windows v Intune Azure Preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Zásady dodržování předpisů se vytvářejí pro jednotlivé platformy.  Zásady dodržování předpisů můžete vytvořit na portálu Azure Portal. Další informace o tom, co jsou zásady dodržování předpisů, najdete v tématu [Co jsou zásady dodržování předpisů u zařízení](what-is-device-compliance.md). Další informace o požadavcích, kterým je potřeba vyhovět před vytvořením zásad dodržování předpisů, najdete v tématu [Začínáme se zásadami dodržování předpisů u zařízení](get-started-with-device-compliance.md).

Tabulka níže popisuje, jak se postupuje u nevyhovujícího nastavení při použití zásad dodržování předpisů se zásadami podmíněného přístupu.

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

**Opravené** = operační systém zařízení vynucuje dodržování předpisů. (Uživatel musí třeba zadat PIN.)

**V karanténě** = operační systém zařízení nevynucuje dodržování předpisů. (Například zařízení s Androidem nenutí uživatele šifrovat zařízení.) Pokud zařízení nesplňuje předpisy, provedou se následující akce:

- Zařízení se zablokuje, pokud se zásady podmíněného přístupu vztahují na uživatele.
- Portál společnosti oznamuje uživateli všechny problémy s dodržováním předpisů.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Vytvoření zásad dodržování předpisů na portálu Azure Portal

1. V okně **Intune** zvolte **Nastavit dodržování předpisů zařízením**. V části **Správa** zvolte možnost pro **Všechny zásady dodržování předpisů zařízení** a zvolte **Vytvořit**.
2. Zadejte název a popis a zvolte platformu, u které chcete použít tyto zásady.
3. Zvolte **Požadavky na dodržování předpisů** a otevřete tak okno s požadavky na dodržování předpisů.  Můžete tady zadat nastavení pro **Zabezpečení**, **Stav zařízení** a **Vlastnosti zařízení**. Až skončíte, klikněte na **Ok**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
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

- **Vyžadovat heslo k odemknutí mobilních zařízení:** Pokud tuto možnost nastavíte na **Ano**, budou muset uživatelé zadat heslo, aby mohli získat přístup ke svému zařízení.
- **Povolit jednoduchá hesla**: Pokud tuto možnost nastavíte na **Ano**, umožníte uživatelům vytvářet jednoduchá hesla, třeba **1234** nebo **1111**.
- **Minimální délka hesla**: Určuje minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Požadovaný typ hesla**: Určuje, jestli musí uživatelé vytvořit heslo typu **Alfanumerické** nebo **Číselné**.

U zařízení s Windows zabezpečených účtem Microsoft se zásada dodržování předpisů nevyhodnotí správně, pokud je minimální délka hesla větší než osm znaků nebo pokud je minimální počet znakových sad větší než dvě.

- **Minimální počet znakových sad**: Pokud se **Požadovaný typ hesla** nastaví na **Alfanumerické**, určuje toto nastavení nejmenší počet znakových sad, které musí heslo obsahovat. Jde o tyto čtyři znakové sady:
  - Malá písmena
  - Velká písmena
  - Symboly
  - Čísla

Pokud se v tomto nastavení nastaví větší číslo, uživatelé budou muset vytvářet složitější hesla. U zařízení s Windows zabezpečených účtem Microsoft se zásada dodržování předpisů nevyhodnotí správně, pokud je minimální délka hesla větší než osm znaků nebo pokud je minimální počet znakových sad větší než dvě.

- **Počet minut nečinnosti před vyžádáním hesla**: Určuje dobu nečinnosti, než bude muset uživatel znovu zadat heslo.
- **Konec platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost uživatelského hesla a uživatel bude muset vytvořit nové.
- **Pamatovat si historii hesel:** Pokud chcete zabránit uživatelům ve vytváření hesel, která používali dřív, použijte toto nastavení spolu s nastavením **Zakázat opakované použití předchozích hesel**.
- **Zakázat opakované použití předchozích hesel:** Pokud je zvolená možnost **Pamatovat si historii hesel**, zadejte počet předchozích hesel, která se nesmí znovu použít.
- **Po návratu zařízení ze stavu nečinnosti vyžadovat heslo:** Toto nastavení by se mělo použít v kombinaci s nastavením **Počet minut nečinnosti před vyžádáním hesla**. Pro přístup k zařízení, které bylo nečinné po dobu uvedenou v nastavení **Počet minut nečinnosti před vyžádáním hesla**, se koncovým uživatelům zobrazí výzva k zadání hesla.

**Toto nastavení platí jenom pro zařízení s Windows 10 Mobile.**

### <a name="encryption"></a>Šifrování

- **Vyžadovat šifrování u mobilního zařízení:** Nastavte možnost **Ano**, pokud chcete, aby muselo být zařízení vyžadující přístup k prostředkům šifrované.



## <a name="device-health-settings"></a>Nastavení stavu zařízení

- **Vyžadovat, aby oznámený stav zařízení byl v pořádku:** Můžete nastavit pravidlo, které vyžaduje, že zařízení s **Windows 10 Mobile** musí být v nových nebo existujících zásadách dodržování předpisů hlášená jako v pořádku. Pokud je toto nastavení povolené, vyhodnotí u zařízení s Windows 10 služba Health Attestation Service (HAS) následující datové body:
  - **Povolený nástroj BitLocker:** Když je nástroj BitLocker zapnutý, při vypnutém systému nebo v režimu hibernace je zařízení schopné chránit data uložená na disku před neoprávněným přístupem. Nástroj Windows BitLocker Drive Encryption zašifruje všechna data uložená na svazku operačního systému Windows. Nástroj BitLocker chrání data operačního systému Windows a uživatelská data pomocí čipu TPM a pomáhá zajistit, aby s počítačem nemohl nikdo manipulovat, ani když ho uživatel ponechá bez dozoru nebo dojde k jeho ztrátě nebo odcizení. Pokud je počítač vybavený kompatibilním čipem TPM, nástroj BitLocker pomocí čipu TPM uzamkne šifrovací klíče, které chrání data. V důsledku toho se ke klíčům nedá získat přístup, dokud čip TPM neověří stav počítače.
  - **Povolená integrita kódu:** Integrita kódu je funkce, která ověřuje integritu ovladače nebo systému souboru při každém načtení do paměti. Integrita kódu zjistí, jestli se do jádra nenačítá nepodepsaný ovladač nebo systémový soubor nebo jestli nedošlo k úpravě některého systémového souboru škodlivým softwarem spuštěným pomocí uživatelského účtu s oprávněním správce.
  - **Povolené zabezpečené spouštění:** Pokud je povolené zabezpečené spouštění, musí se systém spouštět do důvěryhodného stavu z výroby. Kromě toho platí, že při povoleném zabezpečeném spouštění musí mít komponenty jádra sloužící ke spuštění počítače správné kryptografické podpisy, které jsou podle výrobce zařízení důvěryhodné. Firmware UEFI to nejdřív ověří a až potom povolí spuštění počítače. Pokud u některých souborů došlo k manipulaci, při které se porušil podpis, systém se nespustí.

Informace o způsobu fungování služby ověření stavu najdete v tématu [Poskytovatel CSP služby Health Attestation](https://msdn.microsoft.com/library/dn934876.aspx).

## <a name="device-property-settings"></a>Nastavení vlastností zařízení

- **Minimální požadovaný operační systém:** Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nekompatibilní. Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může upgradovat svoje zařízení. Potom bude mít přístup k prostředkům společnosti.
- **Maximální povolená verze operačního systému:** Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.

<!---## Compliance policy settings for Windows PCs--->

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení

### <a name="password"></a>Heslo

- **Minimální délka hesla:** Podporuje se ve Windows 8.1.

Určuje minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.

U zařízení s Windows zabezpečených účtem Microsoft se zásada dodržování předpisů nevyhodnotí správně, pokud je **Minimální délka hesla** větší než 8 znaků nebo pokud je **Minimální počet znakových sad** větší než 2.

- **Požadovaný typ hesla**: Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

Určuje, jestli musí uživatelé vytvořit heslo typu **Alfanumerické** nebo **Číselné**.

- **Minimální počet znakových sad**: Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1. Pokud se **Požadovaný typ hesla** nastaví na **Alfanumerické**, určuje toto nastavení nejmenší počet znakových sad, které musí heslo obsahovat. Jde o tyto čtyři znakové sady:
  - Malá písmena
  - Velká písmena
  - Symboly
  - Čísla: Pokud se v tomto nastavení nastaví větší číslo, budou uživatelé muset vytvářet složitější hesla.

U zařízení s Windows zabezpečených účtem Microsoft se zásada dodržování předpisů nevyhodnotí správně, pokud je **Minimální délka hesla** větší než 8 znaků nebo pokud je **Minimální počet znakových sad** větší než dvě.

- **Počet minut nečinnosti před vyžádáním hesla:** Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

Určuje dobu nečinnosti, po které bude uživatel muset zadat svoje heslo znovu.

- **Konec platnosti hesla (dny)**: Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

Vyberte počet dní, za který uživatelské heslo vyprší a uživatel bude muset vytvořit nové.

- **Pamatovat si historii hesel:** Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

Pokud chcete zabránit uživatelům ve vytváření hesel, která používali dřív, použijte toto nastavení spolu s nastavením **Zakázat opakované použití předchozích hesel**.

- **Zakázat opakované použití předchozích hesel:** Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

Pokud je zvolená možnost **Pamatovat si historii hesel**, zadejte počet předchozích hesel, která se nesmí znovu použít.


## <a name="device-health-settings"></a>Nastavení stavu zařízení

- **Vyžadovat, aby oznámený stav zařízení byl v pořádku:** Podporuje se na zařízeních s Windows 10. Můžete nastavit, které vyžaduje, že zařízení s Windows 10 musí být v nových nebo existujících zásadách dodržování předpisů hlášená jako v pořádku. Pokud je toto nastavení povolené, vyhodnotí u zařízení s Windows 10 služba Health Attestation Service (HAS) následující datové body:
  - **Povolený nástroj BitLocker:** Když je nástroj BitLocker zapnutý, při vypnutém systému nebo v režimu hibernace je zařízení schopné chránit data uložená na disku před neoprávněným přístupem. Nástroj Windows BitLocker Drive Encryption zašifruje všechna data uložená na svazku operačního systému Windows. Nástroj BitLocker chrání data operačního systému Windows a uživatelská data pomocí čipu TPM a pomáhá zajistit, aby s počítačem nemohl nikdo manipulovat, ani když ho uživatel ponechá bez dozoru nebo dojde k jeho ztrátě nebo odcizení. Pokud je počítač vybavený kompatibilním čipem TPM, nástroj BitLocker pomocí čipu TPM uzamkne šifrovací klíče, které chrání data. V důsledku toho se ke klíčům nedá získat přístup, dokud čip TPM neověří stav počítače.
  - **Povolená integrita kódu:** Integrita kódu je funkce, která ověřuje integritu ovladače nebo systému souboru při každém načtení do paměti. Integrita kódu zjistí, jestli se do jádra nenačítá nepodepsaný ovladač nebo systémový soubor nebo jestli nedošlo k úpravě některého systémového souboru škodlivým softwarem spuštěným pomocí uživatelského účtu s oprávněním správce.
  - **Povolené zabezpečené spouštění:** Pokud je povolené zabezpečené spouštění, musí se systém spouštět do důvěryhodného stavu z výroby. Kromě toho platí, že při povoleném zabezpečeném spouštění musí mít komponenty jádra sloužící ke spuštění počítače správné kryptografické podpisy, které jsou podle výrobce zařízení důvěryhodné. Firmware UEFI to nejdřív ověří a až potom povolí spuštění počítače. Pokud u některých souborů došlo k manipulaci, při které se porušil podpis, systém se nespustí.
  - **Je povolený ovladač ELAM (Early Launch Antimalware):** Ovladač ELAM (Early Launch Antimalware) chrání počítače v síti během spouštění a před inicializací ovladačů jiných výrobců.

Informace o způsobu fungování služby ověření stavu najdete v tématu [Poskytovatel CSP služby Health Attestation](https://msdn.microsoft.com/library/dn934876.aspx).

## <a name="device-property-settings"></a>Nastavení vlastností zařízení

- **Minimální požadovaný operační systém:** Podporuje se v systémech Windows 8.1 a Windows 10.

Sem zadejte číslo ve formátu major.minor.build. Číslo verze musí odpovídat verzi vrácené příkazem ```winver```.

Pokud má zařízení starší verzi operačního systému, než je zadaná verze, uvede se jako nekompatibilní. Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může upgradovat svoje zařízení. Potom bude mít přístup k prostředkům společnosti.

- **Maximální povolená verze operačního systému:** Podporuje se v systémech Windows 8.1 a Windows 10.

Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.

K vyhledání verze operačního systému, kterou máte použít v nastaveních **Minimální verze OS** a **Maximální verze OS**, spusťte z příkazového řádku příkaz **winver**. Příkaz winver vrátí verzi operačního systému.

- Počítače s Windows 8.1 vrací verzi **3**. Pokud je pravidlo verze operačního systému pro Windows nastavené na Windows 8.1, bude se zařízení uvádět jako nekompatibilní i v případě, že bude používat Windows 8.1.
- U počítačů s Windows 10 musí být verze nastavená jako &quot;10.0&quot; + číslo sestavení operačního systému vrácené příkazem winver.

<!--- ## Next steps

[How to monitor device compliance](monitor-device-compliance.md)--->

