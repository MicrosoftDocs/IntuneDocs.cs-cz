---

title: "Instalace klientského softwaru na počítači | Dokumentace Microsoftu"
description: "Tento průvodce vám pomůže se správou počítače s Windows klientským softwarem Microsoft Intune."
keywords: 
author: staciebarker
ms.author: stabar
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64c11e53-8d64-41b9-9550-4b4e395e8c52
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 928e4e8097b9cd326e0863a45b183226a7eae056
ms.openlocfilehash: c9a29b6bf9af97f05730251a37b313a662c27a35


---

# <a name="install-the-intune-software-client-on-windows-pcs"></a>Instalace klientského softwaru Intune na počítače se systémem Windows
Počítače se systémem Windows se dají zaregistrovat přes klientský software Intune. Klientský software Intune se dá nainstalovat jedním z následujících způsobů:

- Ruční instalace
- Instalace pomocí zásad skupiny
- Zahrnutí do image disku
- Instalace uživateli

Klientský software Intune při prvním stažení obsahuje minimální software nutný k registraci počítače v systému správy Intune. Po registraci počítače potom klientský software Intune stáhne veškerý klientský software potřebný ke správě počítače.

Tato série stahování minimalizuje dobu potřebnou k počáteční registraci počítače v Intune. Zajistí také to, že po dokončení druhého stahování bude mít klient k dispozici nejnovější dostupný software.

## <a name="download-the-intune-client-software"></a>Stažení klientského softwaru Intune

Všechny metody kromě těch, kdy si uživatelé nainstalují klientský software Intune sami, vyžadují stažení softwaru, aby ho bylo možné nasadit.

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) klikněte na **Správce** &gt; **Stažení klientského softwaru**.

  ![Stažení počítačového klienta Intune](../media/pc-sa-client-download.png)

2.  Na stránce **Stažení klientského softwaru** klikněte na **Stáhnout klientský software**. Uložte balíček **Microsoft_Intune_Setup.zip**, který obsahuje software, do zabezpečeného umístění v síti.

    > [!NOTE]
    > Instalační balíček klientského softwaru Intune obsahuje informace o vašem účtu. Pokud k instalačnímu balíčku získají přístup neoprávnění uživatelé, můžou zaregistrovat počítače k účtu, který reprezentuje vložený certifikát, a můžou tak získat přístup k podnikovým prostředkům.

3.  Extrahujte obsah instalačního balíčku do zabezpečeného umístění v síti.

    > [!IMPORTANT]
    > Soubor **ACCOUNTCERT**, který se extrahuje, nepřejmenovávejte ani neodebírejte, jinak se instalace klientského softwaru nezdaří.

## <a name="deploy-the-client-software-manually"></a>Ruční nasazení klientského softwaru

Na počítači přejděte do složky, kde se nacházejí instalační soubory klientského softwaru. Spusťte **Microsoft_Intune_Setup.exe** a klientský software tak nainstalujte.

    > [!NOTE]
    > The status of the installation is displayed when you hover over the icon in the taskbar on the client computer.

## <a name="deploy-the-client-software-by-using-group-policy"></a>Nasazení klientského softwaru pomocí zásad skupiny

1.  Ve složce, která obsahuje soubory **Microsoft_Intune_Setup.exe** a **MicrosoftIntune.accountcert**, spusťte následující příkaz k extrakci instalačních programů založených na Instalační službě systému Windows pro 32bitové a 64bitové počítače:

    ```
    Microsoft_Intune_Setup.exe/Extract <destination folder>
    ```

2.  Zkopírujte soubory **Microsoft_Intune_x86.msi**, **Microsoft_Intune_x64.msi** a **MicrosoftIntune.accountcert** do umístění v síti, ke kterému mají přístup všechny počítače, na které se klientský software nainstaluje.

    > [!IMPORTANT]
    > Soubory od sebe neoddělujte ani nepřejmenovávejte, jinak se instalace klientského softwaru nezdaří.

3.  Pomocí zásad skupiny nasaďte software do počítačů v síti.

    Další informace o tom, jak automaticky nasadit software pomocí zásad skupiny, najdete v dokumentaci k Windows Serveru.

## <a name="deploy-the-client-software-as-part-of-an-image"></a>Nasazení klientského softwaru jako součásti image
Klientský software Intune můžete do počítače nasadit jako součást image operačního systému. Jako příklad poslouží tento postup:

1.  Zkopírujte instalační soubory klienta, **Microsoft_Intune_Setup.exe** a **Microsoft_Intune_Setup.exe** do složky **%Systemdrive%\Temp\Microsoft_Intune_Setup** na referenčním počítači.

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

5.  Vytvořte image referenčního počítače a pak ji nasaďte do cílových počítačů.

Když se cílový počítač po dokončení instalačního programu systému Windows restartuje, vytvoří se klíč registru **WindowsIntuneEnrollPending**. Registrační balíček ověří, jestli je počítač zaregistrovaný. Pokud je počítač zaregistrovaný, neprovede se žádná další akce. Pokud není počítač registrovaný, registrační balíček vytvoří úlohu automatické registrace Microsoft Intune.

Když je úloha automatické registrace spuštěná v příští naplánovanou dobu, zkontroluje existenci hodnoty registru **WindowsIntuneEnrollPending** a pokusí se registrovat cílový počítač v Intune. Pokud se registrace z jakéhokoli důvodu nezdaří, při dalším spuštění úlohy se pokus o registraci opakuje. Opakované pokusy pokračují po dobu jednoho měsíce.

Úloha automatické registrace Intune, hodnota registru **WindowsIntuneEnrollPending** a certifikát účtu se po úspěšné registraci nebo po jednom měsíci vymažou z cílového počítače (podle toho, která z těchto situací nastane první).

## <a name="instruct-users-to-self-enroll"></a>Pokyny pro uživatele, jak se zaregistrovat sami

Uživatelé můžou nainstalovat klientský software Intune tak, že přejdou na [web Portál společnosti](http://portal.manage.microsoft.com). Pokud webový portál dokáže zařízení identifikovat jako počítač se systémem Windows, zobrazí uživatelům výzvu, aby počítač zaregistrovali pomocí staženého klientského softwaru Intune. Po stažení můžou uživatelé software nainstalovat a zahrnout tak svoje počítače do správy.

![Zobrazení výzvy ke stažení klientského softwaru Intune na portálu služby Intune](../media/software-client-download.png)

## <a name="monitor-and-validate-successful-client-deployment"></a>Sledování a ověření úspěšného nasazení klienta
Pomocí některého z následujících postupů můžete sledovat a ověřit úspěšné nasazení klienta.

### <a name="to-verify-the-installation-of-the-client-software-from-the-microsoft-intune-administrator-console"></a>Ověření instalace klientského softwaru v konzole správce Microsoft Intune

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) klikněte na **Skupiny** &gt; **Všechna zařízení** &gt; **Všechny počítače**.

2.  V seznamu vyhledejte počítače, které komunikují s Intune, nebo vyhledejte konkrétní spravovaný počítač po zadání názvu počítače (nebo libovolné části názvu) do pole **Hledat zařízení**.

3.  V dolním podokně konzoly zkontrolujte stav počítače. Vyřešte všechny chyby.

### <a name="to-create-a-computer-inventory-report-to-display-all-enrolled-computers"></a>Vytvoření sestavy inventáře počítače pro zobrazení všech zaregistrovaných počítačů

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) klikněte na **Sestavy** &gt; **Sestavy inventáře počítače**.

2.  Na stránce **Vytvořit novou sestavu** nechejte ve všech polích výchozí hodnoty (pokud nechcete použít filtry) a klikněte na **Zobrazit sestavu**.

3.  Stránka **Sestava inventáře počítače** se otevře v novém okně s uvedením všech počítačů, které jsou úspěšně zaregistrované v Intune.

    > [!TIP]
    > Kliknutím na záhlaví libovolného sloupce v sestavě seřadíte seznam podle obsahu sloupce.


### <a name="see-also"></a>Viz taky
[Správa počítačů s Windows pomocí Intune](manage-windows-pcs-with-microsoft-intune.md)
[Řešení potíží s instalací klientů](../troubleshoot/troubleshoot-client-setup-in-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


