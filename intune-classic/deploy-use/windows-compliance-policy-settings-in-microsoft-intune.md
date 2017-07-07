---
title: "Nastavení zásad dodržování předpisů pro zařízení s Windows"
description: "Toto téma popisuje pravidla a nastavení, které je možné nakonfigurovat pro zásady dodržování předpisů pro zařízení s Windows."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f996842c-e9a4-4819-acb4-ee66e8fb35b8
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 67810c51c7a7b2ec1e1ff33c11a27a8757b2bcbd
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="compliance-policy-settings-for-windows-devices-in-microsoft-intune"></a>Nastavení zásad dodržování předpisů pro zařízení s Windows v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Nastavení zásad popsané v tomto tématu se týká zařízení s operačním systémem Windows. Následující části popisují podporované verze Windows.

Pokud hledáte informace o jiných platformách, vyberte jednu z těchto možností:
> [!div class="op_single_selector"]
- [Nastavení zásad dodržování předpisů pro zařízení s iOSem](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Nastavení zásad dodržování předpisů pro zařízení s Androidem](android-compliance-policy-settings-in-microsoft-intune.md)
- [Nastavení zásad dodržování předpisů pro zařízení s Androidem for Work](afw-compliance-policy-settings-in-microsoft-intune.md)

## <a name="compliance-policy-settings-for-windows-phone-devices"></a>Nastavení zásad dodržování předpisů pro zařízení Windows Phone
Nastavení uvedené v této části je podporované v systémech Windows Phone 8.1 a novějších.

### <a name="system-security-settings"></a>Systémové nastavení zabezpečení
#### <a name="password"></a>Heslo
- **Vyžadovat heslo k odemknutí mobilních zařízení:** Pokud tuto možnost nastavíte na **Ano**, bude uživatel muset zadat heslo, aby mohli získat přístup ke svému zařízení.

- **Povolit jednoduchá hesla**: Pokud tuto možnost nastavíte na **Ano**, umožníte uživateli vytvářet jednoduchá hesla, třeba **1234** nebo **1111**.

-  **Minimální délka hesla:** Určuje minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Vyžadovaný typ hesla:** Určuje, jestli musí uživatel vytvořit **Alfanumerické** nebo **Číselné** heslo.

  U zařízení s Windows zabezpečených účtem Microsoft se zásada dodržování předpisů nevyhodnotí správně, pokud je minimální délka hesla větší než osm znaků nebo pokud je minimální počet znakových sad větší než dvě.

- **Minimální počet znakových sad:** Pokud se **požadovaný typ hesla** nastaví na **Alfanumerické**, toto nastavení určuje nejmenší počet znakových sad, které musí heslo obsahovat. Jde o tyto čtyři znakové sady:
  -   Malá písmena
  -   Velká písmena
  -   Symboly
  -   Čísla

  Po nastavení vyššího čísla v tomto nastavení bude uživatel muset vytvořit složitější heslo. U zařízení s Windows zabezpečených účtem Microsoft se zásada dodržování předpisů nevyhodnotí správně, pokud je minimální délka hesla větší než osm znaků nebo pokud je minimální počet znakových sad větší než dvě.

- **Počet minut nečinnosti, než se požaduje heslo:** Toto nastavení určuje dobu nečinnosti, než uživatel musí znovu zadat heslo.

- **Vypršení platnosti hesla (dny):** Zvolte počet dní, za který uživatelské heslo vyprší a uživatel bude muset vytvořit nové.

- **Pamatovat si historii hesel**: Pokud chcete zabránit uživatelům ve vytváření hesel, která používali dřív, použijte toto nastavení spolu s nastavením **Zakázat opakované použití předchozích hesel**.

- **Zakázat opakované použití předchozích hesel:** Pokud je zvolená možnost **Pamatovat si historii hesel**, zadejte počet předchozích hesel, která se nesmí znovu použít.
- **Po návratu zařízení ze stavu nečinnosti vyžadovat heslo:** Toto nastavení použijte v kombinaci s nastavením **Počet minut nečinnosti před vyžádáním hesla**. Pro přístup k zařízení, které bylo nečinné po dobu uvedenou v nastavení **Počet minut nečinnosti před vyžádáním hesla**, se uživatelům zobrazí výzva k zadání hesla.

  > [!NOTE]
  > Toto nastavení platí jenom pro zařízení s Windows 10 Mobile.

#### <a name="encryption"></a>Šifrování
- **Vyžadovat šifrování u mobilního zařízení:** Nastavte možnost **Ano**, pokud chcete, aby muselo být zařízení vyžadující přístup k prostředkům šifrované.

### <a name="device-health-settings"></a>Nastavení stavu zařízení
- **Vyžadovat, aby oznámený stav zařízení byl v pořádku:** Můžete nastavit pravidlo, které vyžaduje, že zařízení s **Windows 10 Mobile** musí být v nových nebo existujících zásadách dodržování předpisů hlášená jako zařízení se stavem V pořádku.  Pokud je toto nastavení povolené, zařízení s Windows 10 se vyhodnotí prostřednictvím služby Health Attestation na základě těchto datových bodů:
  -  **Povolený nástroj BitLocker:** Když je nástroj BitLocker zapnutý, při vypnutém systému nebo v režimu hibernace může zařízení pomáhat chránit data uložená na disku před neoprávněným přístupem. Nástroj Windows BitLocker Drive Encryption zašifruje všechna data uložená na svazku operačního systému Windows. BitLocker používá k ochraně operačního systému Windows a uživatelských dat čip TPM. BitLocker také pomáhá zajistit, aby se s počítačem nemanipulovalo ani v případě, že je ponechaný bez dozoru nebo je ztracený/odcizený. Pokud je počítač vybavený kompatibilním čipem TPM, nástroj BitLocker pomocí čipu TPM uzamkne šifrovací klíče, které pomáhají chránit data. V důsledku toho se ke klíčům nedá získat přístup, dokud čip TPM neověří stav počítače.
  -  **Povolená integrita kódu:** Integrita kódu je funkce, která ověřuje integritu ovladače nebo systému souboru při každém načtení do paměti. Integrita kódu zjistí, jestli se do jádra načítá nepodepsaný ovladač nebo systémový soubor. Zjistí také, jestli systémový soubor nebyl změněn škodlivým softwarem, který je spuštěný pomocí uživatelského účtu s oprávněními správce.
  - **Povolené zabezpečené spouštění:** Pokud je povolené zabezpečené spouštění, musí se systém spouštět do důvěryhodného stavu z výroby. Kromě toho platí, že při povoleném zabezpečeném spouštění musí mít komponenty jádra sloužící ke spuštění počítače správné kryptografické podpisy, které jsou podle výrobce zařízení důvěryhodné. Firmware UEFI to nejdřív ověří a až potom povolí spuštění počítače. Pokud u některých souborů došlo k manipulaci, při které se porušil podpis, systém se nespustí.

  > [!IMPORTANT]
  > Zařízení s Windows nepodporují software **ELAM (Early Launch Anti Malware)** třetích stran nainstalovaný jako součást Ověření stavu zařízení.

  Informace o způsobu fungování služby ověření stavu najdete v tématu [Poskytovatel CSP služby Health Attestation](https://msdn.microsoft.com/library/dn934876.aspx).
###  <a name="device-property-settings"></a>Nastavení vlastností zařízení
- **Minimální požadovaný operační systém**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nekompatibilní.
    Zobrazí se odkaz s informacemi o postupu upgradu. Uživatel si může zařízení upgradovat. Potom bude mít přístup k prostředkům společnosti.

- **Maximální povolená verze operačního systému:** Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.


## <a name="compliance-policy-settings-for-windows-pcs"></a>Nastavení zásad dodržování předpisů pro počítače s Windows
Nastavení uvedené v této části je podporované na počítačích s Windows Phone.
### <a name="system-security-settings"></a>Systémové nastavení zabezpečení
#### <a name="password"></a>Heslo
- **Minimální délka hesla:** Podporuje se ve Windows 8.1.

  Určuje minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.

  U zařízení s Windows zabezpečených účtem Microsoft se zásada dodržování předpisů nevyhodnotí správně, pokud je **minimální délka hesla** větší než osm znaků nebo pokud je **minimální počet znakových sad** větší než dvě.

- **Vyžadovaný typ hesla:** Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

  Určuje, jestli musí uživatel vytvořit **alfanumerické** nebo **číselné** heslo.

- **Minimální počet znakových sad:** Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

  Pokud se **požadovaný typ hesla** nastaví na **Alfanumerické**, toto nastavení určuje nejmenší počet znakových sad, které musí heslo obsahovat. Jde o tyto čtyři znakové sady:
  -   Malá písmena
  -   Velká písmena
  -   Symboly
  -   Čísla     

  Po nastavení vyššího čísla v tomto nastavení bude uživatel muset vytvořit složitější heslo. U zařízení s Windows zabezpečených účtem Microsoft se zásada dodržování předpisů nevyhodnotí správně, pokud je **minimální délka hesla** větší než osm znaků nebo pokud je **minimální počet znakových sad** větší než dvě.

- **Počet minut nečinnosti před vyžádáním hesla:** Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

  Určuje dobu nečinnosti, po které bude uživatel muset zadat svoje heslo znovu.

- **Vypršení platnosti hesla (dny):** Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

  Zvolte počet dní, za který uživatelské heslo vyprší a uživatel bude muset vytvořit nové.

- **Pamatovat si historii hesel:** Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

  Pokud chcete zabránit uživatelům ve vytváření hesel, která používali dřív, použijte toto nastavení spolu s nastavením **Zakázat opakované použití předchozích hesel**.

- **Zakázat opakované použití předchozích hesel:** Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

  Pokud je zvolená možnost **Pamatovat si historii hesel**, zadejte počet předchozích hesel, která se nesmí znovu použít.

### <a name="device-health-settings"></a>Nastavení stavu zařízení
- **Vyžadovat, aby oznámený stav zařízení byl v pořádku:** Podporuje se na zařízeních s Windows 10.
Můžete nastavit pravidlo, které vyžaduje, že zařízení s Windows 10 musí být v nových nebo existujících zásadách dodržování předpisů hlášená jako zařízení se stavem V pořádku. Pokud je toto nastavení povolené, zařízení s Windows 10 se vyhodnotí prostřednictvím služby Health Attestation na základě těchto datových bodů:
  -  **Povolený nástroj BitLocker:** Když je nástroj BitLocker zapnutý, při vypnutém systému nebo v režimu hibernace může zařízení pomáhat chránit data uložená na disku před neoprávněným přístupem. Nástroj Windows BitLocker Drive Encryption zašifruje všechna data uložená na svazku operačního systému Windows. BitLocker používá k ochraně operačního systému Windows a uživatelských dat čip TPM. BitLocker také pomáhá zajistit, aby se s počítačem nemanipulovalo ani v případě, že je ponechaný bez dozoru nebo je ztracený/odcizený. Pokud je počítač vybavený kompatibilním čipem TPM, nástroj BitLocker pomocí čipu TPM uzamkne šifrovací klíče, které pomáhají chránit data. V důsledku toho se ke klíčům nedá získat přístup, dokud čip TPM neověří stav počítače.
  -  **Povolená integrita kódu:** Integrita kódu je funkce, která ověřuje integritu ovladače nebo systému souboru při každém načtení do paměti. Integrita kódu zjistí, jestli se do jádra načítá nepodepsaný ovladač nebo systémový soubor. Zjistí také, jestli systémový soubor nebyl změněn škodlivým softwarem, který je spuštěný pomocí uživatelského účtu s oprávněními správce.
  - **Povolené zabezpečené spouštění:** Pokud je povolené zabezpečené spouštění, musí se systém spouštět do důvěryhodného stavu z výroby. Kromě toho platí, že při povoleném zabezpečeném spouštění musí mít komponenty jádra sloužící ke spuštění počítače správné kryptografické podpisy, které jsou podle výrobce zařízení důvěryhodné. Firmware UEFI to nejdřív ověří a až potom povolí spuštění počítače. Pokud u některých souborů došlo k manipulaci, při které se porušil podpis, systém se nespustí.
  - **Je povolený ovladač ELAM (Early Launch Antimalware):** Ovladač ELAM (Early Launch Antimalware) chrání počítače v síti během spouštění a před inicializací ovladačů jiných výrobců.

  Informace o způsobu fungování služby ověření stavu najdete v tématu [Poskytovatel CSP služby Health Attestation](https://msdn.microsoft.com/library/dn934876.aspx).

### <a name="device-property-settings"></a>Nastavení vlastností zařízení
- **Minimální požadovaný operační systém:** Podporuje se v systémech Windows 8.1 a Windows 10.

  Sem zadejte číslo ve formátu major.minor.build. Číslo verze musí odpovídat verzi vrácené příkazem **winver**.

  Pokud má zařízení starší verzi operačního systému, než je zadaná verze, nahlásí se jako nevyhovující. Zobrazí se odkaz s informacemi o postupu upgradu. Uživatel si může zařízení upgradovat. Potom bude mít přístup k prostředkům společnosti.

- **Maximální povolená verze operačního systému:** Podporuje se v systémech Windows 8.1 a Windows 10.

  Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.

K vyhledání verze operačního systému, kterou máte použít v nastaveních **Minimální požadovaný operační systém** a **Maximální povolená verze operačního systému**, spusťte z příkazového řádku příkaz **winver**. Příkaz **winver** vrátí hlášenou verzi operačního systému.

- Počítače s Windows 8.1 vrací verzi **6.3**. Pokud je pravidlo verze operačního systému pro Windows nastavené na Windows 8.1, bude se zařízení uvádět jako nekompatibilní i v případě, že bude používat Windows 8.1.

- U počítačů s Windows 10 musí být verze nastavená jako **10.0** plus číslo sestavení operačního systému vrácené příkazem **winver**. Může to být třeba 10.0.10586.
> ![Verze sestavení operačního systému zvýrazněná v dialogovém okně „O produktu Windows“](./media/ca_win10-os-version.png)
