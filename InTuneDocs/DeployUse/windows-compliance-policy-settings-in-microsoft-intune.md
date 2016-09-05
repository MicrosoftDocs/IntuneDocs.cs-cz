---
title: "Nastavení zásad dodržování předpisů pro zařízení s Windows | Microsoft Intune"
description: 
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f996842c-e9a4-4819-acb4-ee66e8fb35b8
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: 12239464012029e3ffff3a9bed4f4ccb2cebe633


---

# Nastavení zásad dodržování předpisů pro zařízení s Windows v Microsoft Intune

Nastavení zásad popsané v tomto tématu se týká zařízení s operačním systémem Windows. V následujících částech najdete konkrétní podporované verze Windows.

Pokud hledáte informace o jiných platformách, vyberte jednu z těchto možností:
> [!div class="op_single_selector"]
- [Nastavení zásad dodržování předpisů pro zařízení s iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Nastavení zásad dodržování předpisů pro zařízení s Androidem](android-compliance-policy-settings-in-microsoft-intune.md)

## Nastavení zásad dodržování předpisů pro zařízení Windows Phone
Nastavení uvedené v této části je podporované v systémech Windows Phone 8.1 a novějších.

## Systémové nastavení zabezpečení
### Heslo
- **Vyžadovat heslo k odemknutí mobilních zařízení:** Pokud tuto možnost nastavíte na **Ano**, budou muset uživatelé zadat heslo, aby mohli získat přístup ke svému zařízení.

- **Povolit jednoduchá hesla:** Pokud tuto možnost nastavíte na **Ano**, umožníte uživatelům vytvářet jednoduchá hesla, třeba **1234** nebo **1111**.

-  **Minimální délka hesla:** Určuje minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Vyžadovaný typ hesla:** Určuje, jestli musí uživatelé vytvořit heslo typu **Alfanumerický**, nebo **Číslo**.

  U zařízení s Windows zabezpečených účtem Microsoft se zásada dodržování předpisů nevyhodnotí správně, pokud je minimální délka hesla větší než osm znaků nebo pokud je minimální počet znakových sad větší než dvě.

- **Minimální počet znakových sad:** Pokud se **Požadovaný typ hesla** nastaví na **Alfanumerické**, toto nastavení určuje nejmenší počet znakových sad, které musí heslo obsahovat. Jde o tyto čtyři znakové sady:
  -   Malá písmena
  -   Velká písmena
  -   Symboly
  -   Čísla

  Pokud se v tomto nastavení nastaví větší číslo, uživatelé budou muset vytvářet složitější hesla. U zařízení s Windows zabezpečených účtem Microsoft se zásada dodržování předpisů nevyhodnotí správně, pokud je minimální délka hesla větší než osm znaků nebo pokud je minimální počet znakových sad větší než dvě.
- **Počet minut nečinnosti, než se požaduje heslo:** Určuje dobu nečinnosti, než uživatel musí znovu zadat heslo.

- **Vypršení platnosti hesla (dny):** Zvolte počet dní, za který uživatelské heslo vyprší a uživatel bude muset vytvořit nové.

- **Pamatovat si historii hesel:** Pokud chcete zabránit uživatelům ve vytváření hesel, která používali dřív, použijte toto nastavení spolu s nastavením **Zakázat opakované použití předchozích hesel**.

- **Zakázat opakované použití předchozích hesel:** Pokud je zvolená možnost **Pamatovat si historii hesel**, zadejte počet předchozích hesel, která se nesmí znovu použít.
- **Po návratu zařízení ze stavu nečinnosti vyžadovat heslo:** Toto nastavení by se mělo použít v kombinaci s nastavením **Počet minut nečinnosti před vyžádáním hesla**. Pro přístup k zařízení, které bylo nečinné po dobu uvedenou v nastavení **Počet minut nečinnosti před vyžádáním hesla**, se koncovým uživatelům zobrazí výzva k zadání hesla.

  **Toto nastavení platí jenom pro zařízení s Windows 10 Mobile.**
### Šifrování
- **Vyžadovat šifrování u mobilního zařízení:** Nastavte možnost **Ano**, pokud chcete, aby muselo být zařízení vyžadující přístup k prostředkům šifrované.

## Nastavení stavu zařízení
- **Vyžadovat, aby oznámený stav zařízení byl v pořádku:** Můžete nastavit pravidlo, které vyžaduje, že zařízení s **Windows 10 Mobile** musí být v nových nebo existujících zásadách dodržování předpisů hlášená jako v pořádku.  Pokud je toto nastavení povolené, zařízení s Windows 10 se vyhodnotí prostřednictvím služby Health Attestation na základě těchto datových bodů:
  -  **Povolený nástroj BitLocker:** Když je nástroj BitLocker zapnutý, při vypnutém systému nebo v režimu hibernace je zařízení schopné chránit data uložená na disku před neoprávněným přístupem. Nástroj Windows BitLocker Drive Encryption zašifruje všechna data uložená na svazku operačního systému Windows. Nástroj BitLocker chrání data operačního systému Windows a uživatelská data pomocí čipu TPM a pomáhá zajistit, aby s počítačem nemohl nikdo manipulovat, ani když ho uživatel ponechá bez dozoru nebo dojde k jeho ztrátě nebo odcizení. Pokud je počítač vybavený kompatibilním čipem TPM, nástroj BitLocker pomocí čipu TPM uzamkne šifrovací klíče, které chrání data. V důsledku toho se ke klíčům nedá získat přístup, dokud čip TPM neověří stav počítače.
  -  **Povolená integrita kódu:** Integrita kódu je funkce, která ověřuje integritu ovladače nebo systému souboru při každém načtení do paměti. Integrita kódu zjistí, jestli se do jádra nenačítá nepodepsaný ovladač nebo systémový soubor nebo jestli nedošlo k úpravě některého systémového souboru škodlivým softwarem spuštěným pomocí uživatelského účtu s oprávněním správce.
  - **Povolené zabezpečené spouštění:** Pokud je povolené zabezpečené spouštění, musí se systém spouštět do důvěryhodného stavu z výroby. Kromě toho platí, že při povoleném zabezpečeném spouštění musí mít komponenty jádra sloužící ke spuštění počítače správné kryptografické podpisy, které jsou podle výrobce zařízení důvěryhodné. Firmware UEFI to nejdřív ověří a až potom povolí spuštění počítače. Pokud u některých souborů došlo k manipulaci, při které se porušil podpis, systém se nespustí.

  Informace o způsobu fungování služby ověření stavu najdete v tématu [Poskytovatel CSP služby Health Attestation](https://msdn.microsoft.com/library/dn934876.aspx).
##  Nastavení vlastností zařízení
- **Minimální požadovaný operační systém:** Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nekompatibilní.
    Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může upgradovat svoje zařízení. Potom bude mít přístup k prostředkům společnosti.

- **Maximální povolená verze operačního systému:** Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.


## Nastavení zásad dodržování předpisů pro počítače s Windows
Nastavení uvedené v této části je podporované na počítačích s Windows Phone.
## Systémové nastavení zabezpečení
### Heslo
- **Minimální délka hesla:** Podporuje se ve Windows 8.1.

  Určuje minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.

  U zařízení s Windows zabezpečených účtem Microsoft se zásada dodržování předpisů nevyhodnotí správně, pokud je **Minimální délka hesla** větší než 8 znaků nebo pokud je **Minimální počet znakových sad** větší než 2.

- **Vyžadovaný typ hesla:** Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

  Určuje, jestli musí uživatelé vytvořit heslo typu **Alfanumerický**, nebo **Číslo**.

- **Minimální počet znakových sad:** Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1. Pokud se **Požadovaný typ hesla** nastaví na **Alfanumerické**, toto nastavení určuje nejmenší počet znakových sad, které musí heslo obsahovat. Jde o tyto čtyři znakové sady:
  -   Malá písmena
  -   Velká písmena
  -   Symboly
  -   Čísla: Pokud se v tomto nastavení nastaví větší číslo, uživatelé budou muset vytvářet složitější hesla.

  U zařízení s Windows zabezpečených účtem Microsoft se zásada dodržování předpisů nevyhodnotí správně, pokud je **Minimální délka hesla** větší než 8 znaků nebo pokud je **Minimální počet znakových sad** větší než dvě.
- **Počet minut nečinnosti před vyžádáním hesla:** Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

  Určuje dobu nečinnosti, po které bude uživatel muset zadat svoje heslo znovu.

- **Vypršení platnosti hesla (dny):** Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

  Zvolte počet dní, za který uživatelské heslo vyprší a uživatel bude muset vytvořit nové.

- **Pamatovat si historii hesel:** Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

  Pokud chcete zabránit uživatelům ve vytváření hesel, která používali dřív, použijte toto nastavení spolu s nastavením **Zakázat opakované použití předchozích hesel**.
- **Zakázat opakované použití předchozích hesel:** Podporuje se ve Windows RT, Windows RT 8.1 a Windows 8.1.

  Pokud je zvolená možnost **Pamatovat si historii hesel**, zadejte počet předchozích hesel, která se nesmí znovu použít.

## Nastavení stavu zařízení
- **Vyžadovat, aby oznámený stav zařízení byl v pořádku:** Podporuje se na zařízeních s Windows 10.
Můžete nastavit, které vyžaduje, že zařízení s Windows 10 musí být v nových nebo existujících zásadách dodržování předpisů hlášená jako v pořádku.  Pokud je toto nastavení povolené, zařízení s Windows 10 se vyhodnotí prostřednictvím služby Health Attestation na základě těchto datových bodů:
  -  **Povolený nástroj BitLocker:** Když je nástroj BitLocker zapnutý, při vypnutém systému nebo v režimu hibernace je zařízení schopné chránit data uložená na disku před neoprávněným přístupem. Nástroj Windows BitLocker Drive Encryption zašifruje všechna data uložená na svazku operačního systému Windows. Nástroj BitLocker chrání data operačního systému Windows a uživatelská data pomocí čipu TPM a pomáhá zajistit, aby s počítačem nemohl nikdo manipulovat, ani když ho uživatel ponechá bez dozoru nebo dojde k jeho ztrátě nebo odcizení. Pokud je počítač vybavený kompatibilním čipem TPM, nástroj BitLocker pomocí čipu TPM uzamkne šifrovací klíče, které chrání data. V důsledku toho se ke klíčům nedá získat přístup, dokud čip TPM neověří stav počítače.
  -  **Povolená integrita kódu:** Integrita kódu je funkce, která ověřuje integritu ovladače nebo systému souboru při každém načtení do paměti. Integrita kódu zjistí, jestli se do jádra nenačítá nepodepsaný ovladač nebo systémový soubor nebo jestli nedošlo k úpravě některého systémového souboru škodlivým softwarem spuštěným pomocí uživatelského účtu s oprávněním správce.
  - **Povolené zabezpečené spouštění:** Pokud je povolené zabezpečené spouštění, musí se systém spouštět do důvěryhodného stavu z výroby. Kromě toho platí, že při povoleném zabezpečeném spouštění musí mít komponenty jádra sloužící ke spuštění počítače správné kryptografické podpisy, které jsou podle výrobce zařízení důvěryhodné. Firmware UEFI to nejdřív ověří a až potom povolí spuštění počítače. Pokud u některých souborů došlo k manipulaci, při které se porušil podpis, systém se nespustí.
  - **Je povolený ovladač ELAM (Early Launch Antimalware):** Ovladač ELAM (Early Launch Antimalware) chrání počítače v síti během spouštění a před inicializací ovladačů jiných výrobců.

  Informace o způsobu fungování služby ověření stavu najdete v tématu [Poskytovatel CSP služby Health Attestation](https://msdn.microsoft.com/library/dn934876.aspx).

## Nastavení vlastností zařízení
- **Minimální požadovaný operační systém:** Podporuje se v systémech Windows 8.1 a Windows 10.

  Sem zadejte číslo ve formátu major.minor.build. Číslo verze musí odpovídat verzi vrácené příkazem winver.

  Pokud má zařízení starší verzi operačního systému, než je zadaná verze, nahlásí se jako nevyhovující. Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může upgradovat svoje zařízení. Potom bude mít přístup k prostředkům společnosti.

- **Maximální povolená verze operačního systému:** Podporuje se v systémech Windows 8.1 a Windows 10.

  Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.

K vyhledání verze operačního systému, kterou máte použít v nastaveních **Minimální požadovaný operační systém** a **Maximální povolená verze operačního systému** spusťte z příkazového řádku příkaz **winver**. Příkaz winver vrátí hlášenou verzi operačního systému.
- Počítače s Windows 8.1 vrací verzi **6.3**.    Pokud je pravidlo verze operačního systému pro Windows nastavené na Windows 8.1, bude se zařízení uvádět jako nekompatibilní i v případě, že bude používat Windows 8.1.
- U počítačů s Windows 10 musí být verze nastavená jako „10.0“ + číslo sestavení operačního systému vrácené příkazem winver. Může to být třeba 10.0.10586.
> ![CA_Win10OSVersion](./media/ca_win10-os-version.png)



<!--HONumber=Jul16_HO5-->


