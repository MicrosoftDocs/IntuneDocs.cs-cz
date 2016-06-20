---
# required metadata

title: Instalace klienta na počítači s Windows pomocí Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 64c11e53-8d64-41b9-9550-4b4e395e8c52

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Instalace klienta na počítači s Windows pomocí Microsoft Intune
Tento průvodce vám pomůže se správou počítače s Windows klientským softwarem Microsoft Intune.

## Než začnete
Před zahájením instalace klientského softwaru Intune si přečtěte téma [Řešení konfliktů GPO a zásad Microsoft Intune](resolve-gpo-and-microsoft-intune-policy-conflicts.md), abyste zjistili, co musíte zajistit pro správnou instalaci klienta, a pak se k těmto pokynům vraťte.

## Instalace klienta
Pomocí těchto kroků nainstalujte klienta:

-   [Stažení klientského softwaru](#to-download-the-client-software)

Pak klienta nechte nainstalovat pomocí jednoho nebo více z těchto způsobů:

-   [Ruční nasazení klientského softwaru](#to-manually-deploy-the-client-software)

-   [Automatické nasazení klientského softwaru pomocí zásad skupiny](#to-automatically-deploy-the-client-software-by-using-group-policy)

-   [Jak můžou uživatelé svoje počítače sami zaregistrovat](#how-users-can-self-enroll-their-computers)

-   [Instalace klientského softwaru Microsoft Intune v rámci bitové kopie](#install-the-microsoft-intune-client-software-as-part-of-an-image)

Pokud už počítač s Intune spravovat nepotřebujete, můžete ho vyřadit. Tím se taky z počítače odebere klientský software. Další informace najdete v tématu [Běžné úlohy správy počítačů s Windows pomocí počítačového klienta Microsoft Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)..

### Stažení klientského softwaru

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) klikněte na **Správce** &gt; **Stažení klientského softwaru**

  ![Stažení počítačového klienta Intune](./media/pc-SA-client-download.png)

2.  Na stránce **Stažení klientského softwaru** klikněte na **Stáhnout klientský software** a uložte balíček **Microsoft_Intune_Setup.zip** obsahující software do zabezpečeného umístění v síti.

    > [!NOTE]
    > Instalační balíček klientského softwaru Intune obsahuje informace o vašem účtu. Pokud k instalačnímu balíčku získají přístup neoprávnění uživatelé, můžou zaregistrovat počítače k účtu, který je zastoupený svým vloženým certifikátem.

3.  Extrahujte obsah instalačního balíčku do zabezpečeného umístění v síti.

    > [!IMPORTANT]
    > Soubor **ACCOUNTCERT**, který se extrahuje, nepřejmenovávejte ani neodebírejte, jinak se instalace klientského softwaru nezdaří.

### Ruční nasazení klientského softwaru

1.  Na počítači přejděte do složky, kde se nacházejí instalační soubory klientského softwaru, a spuštěním souboru **Microsoft_Intune_Setup.exe** klientský software nainstalujte.

    > [!NOTE]
    > Stav instalace se zobrazí, když ukazatel myši přesunete na ikonu v oznamovací oblasti v klientském počítači.

### Automatické nasazení klientského softwaru pomocí zásad skupiny

1.  Ve složce, která obsahuje soubory **Microsoft_Intune_Setup.exe** a **MicrosoftIntune.accountcert**, spusťte následující příkaz k extrakci instalačních programů založených na Instalační službě systému Windows pro 32bitové a 64bitové počítače:

    ```
    Microsoft_Intune_Setup.exe/Extract <destination folder>
    ```

2.  Zkopírujte soubory **Microsoft_Intune_x86.msi**, **Microsoft_Intune_x64.msi** a **MicrosoftIntune.accountcert** do umístění v síti, ke kterému mají přístup všechny počítače, na které se má klientský software nainstalovat.

    > [!IMPORTANT]
    > Soubory od sebe neoddělujte ani nepřejmenovávejte, jinak se instalace klientského softwaru nezdaří.

3.  Pomocí zásad skupiny nasaďte software do počítačů v síti.

    Další informace o tom, jak automaticky nasadit software pomocí zásad skupiny, najdete v dokumentaci k Windows Serveru.

### Jak můžou uživatelé svoje počítače sami zaregistrovat
Uživatelé můžou své počítače sami zaregistrovat pomocí portálu společnosti Intune. Každý zaregistrovaný počítač se propojí s uživatelským účtem použitým při instalaci klientského softwaru.

> [!NOTE]
> -   Aby mohl uživatel klientský software nainstalovat, musí být na počítači správcem.
> -   Vlastní registrace uživatelem vyžaduje, aby byl na klientském počítači nainstalovaný Internet Explorer.
> -   Pokaždé, když uživatel sám zaregistruje počítač, použije se licence Intune.
> -   Pro vlastní registraci počítače musíte použít pracovní nebo školní účet. Pomocí účtu Microsoft sami počítač zaregistrovat nemůžete.
> -   Pokud je už klientský software na počítači nainstalovaný, koncovému uživateli se zobrazí chyba.

### Vlastní registrace počítače (informace pro koncové uživatele)

1.  Přihlaste se k firemnímu portálu z počítače, který chcete zaregistrovat.

2.  Klikněte na **Přidat zařízení**..

3.  Klikněte na **Stáhnout software** a potom na **Spustit**..

4.  Kliknutím na **Další** spusťte průvodce instalací Microsoft Intune.

5.  Po dokončení průvodce instalací klikněte na **Dokončit**..

### Instalace klientského softwaru Microsoft Intune v rámci bitové kopie
Klientský software Intune můžete do počítačů nasadit v rámci bitové kopie operačního systému. Jako příklad poslouží tento základní postup:

1.  Zkopírujte instalační soubory klienta, **Microsoft_Intune_Setup.exe** a **MicrosoftIntune.accountcert**, do složky **%Systemdrive%\Temp\Microsoft_Intune_Setup** na referenčním počítači.

2.  Vytvořte položku registru **WindowsIntuneEnrollPending** přidáním následujícího příkazu do skriptu **SetupComplete.cmd** :

    ```
    %windir%\system32\reg.exe add HKEY_LOCAL_MACHINE\Software\Microsoft\Onlinemanagement\Deployment /v
    WindowsIntuneEnrollPending /t REG_DWORD /d 1
    ```

3.  Přidáním následujícího příkazu do skriptu **setupcomplete.cmd** spusťte registrační balíček s argumentem příkazového řádku /PrepareEnroll:

    ```
    %systemdrive%\temp\Microsoft_Intune_Setup\Microsoft_Intune_Setup.exe /PrepareEnroll
    ```
    > [!TIP]
    > Skript **SetupComplete.cmd** umožňuje, aby instalační program systému Windows provedl změny systému před přihlášením uživatele. Argument příkazového řádku **/PrepareEnroll** připraví cílový počítač, aby se po dokončení instalačního programu systému Windows automaticky zaregistroval v Intune.

4.  Skript **SetupComplete.cmd** umístěte do složky **%Windir%\Setup\Scripts** na referenčním počítači.

5.  Vytvořte bitovou kopii referenčního počítače a pak ji nasaďte do cílových počítačů.

Když se cílový počítač po dokončení instalačního programu systému Windows restartuje, vytvoří se klíč registru **WindowsIntuneEnrollPending** . Registrační balíček ověří, jestli je počítač zaregistrovaný. Pokud je počítač zaregistrovaný, neprovede se žádná další akce. Pokud není počítač registrovaný, registrační balíček vytvoří úlohu automatické registrace Microsoft Intune.

Když je úloha automatické registrace spuštěná v příští naplánovanou dobu, zkontroluje existenci hodnoty registru **WindowsIntuneEnrollPending** a pokusí se registrovat cílový počítač v Intune. Pokud se registrace z jakéhokoli důvodu nezdaří, při dalším spuštění úlohy se pokus o registraci opakuje. Opakované pokusy pokračují po dobu jednoho měsíce.

Úloha automatické registrace Intune, úloha registru **WindowsIntuneEnrollPending** a certifikát účtu se po úspěšné registraci nebo jednom měsíci vymažou z cílového počítače.

## Sledování a ověření úspěšného nasazení klienta
Pomocí některého z následujících postupů můžete sledovat a ověřit úspěšné nasazení klienta.

### Ověření instalace klientského softwaru v konzole správce Microsoft Intune

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/), klikněte na **Skupiny** &gt; **Všechna zařízení** &gt; **Všechny počítače**.

2.  Projděte dolů seznam a vyhledejte spravované počítače, které komunikují s Intune, nebo konkrétní spravované počítač zadáním názvu počítače nebo libovolné části názvu do pole **Hledat zařízení**.

3.  Ve spodním podokně konzole zkontrolujte stav počítače a vyřešte případné chyby.

### Vytvoření sestavy inventáře počítače pro zobrazení všech zaregistrovaných počítačů

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) klikněte na **Sestavy** &gt; **Sestavy inventáře počítače**..

2.  Na stránce **Vytvořit novou sestavu** nechte ve všech polích výchozí hodnoty (pokud nechcete použít filtry) a klikněte na **Zobrazit sestavu**..

3.  Stránka **Sestava inventáře počítače** se otevře v novém okně s uvedením všech počítačů, které jsou úspěšně zaregistrované v Intune.

    > [!TIP]
    > Kliknutím na záhlaví libovolného sloupce v sestavě seřadíte seznam podle obsahu sloupce.


### Viz také
[Správa počítačů s Windows pomocí Intune](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->

