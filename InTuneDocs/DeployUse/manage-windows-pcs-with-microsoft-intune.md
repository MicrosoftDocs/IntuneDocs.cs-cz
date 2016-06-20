---
# required metadata

title: Správa počítačů s Windows pomocí Intune | Microsoft Intune
description:
keywords:
author: nathbarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Správa počítačů s Windows pomocí Intune
Intune můžete kromě registrace mobilních zařízení použít taky ke správě počítačů Windows s podporovaným operačním systémem pomocí klientského softwaru Intune počítače s Windows. Požadavky na hardware a software pro spuštění počítačového klienta jsou minimální, dá se říct, že je podporovaný libovolný systém schopný spustit Windows 7 nebo novější verzi.  Klientský software se taky dá snadno nainstalovat do počítačů připojených k doméně (v libovolné doméně) i do počítačů, které do žádné domény připojené nejsou.

Intune spravuje počítače s Windows pomocí zásad podobně jako objekty zásad skupiny (GPO) služby AD DS (Active Directory Domain Services) Windows Serveru. Pokud budete počítače připojené k doméně Active Directory spravovat pomocí Intune, měli byste [ověřit, že zásady Intune nejsou v konfliktu se žádnými objekty zásad skupiny](resolve-gpo-and-microsoft-intune-policy-conflicts.md), které jsou nastavené pro vaši organizaci.

> [!NOTE]
> Microsoft Intune jako samostatná služba nabízí tyto funkce pro správu počítačů. Zařízení se systémem Windows 8.1 můžete spravovat pomocí klienta Intune nebo je můžete zaregistrovat jako mobilní zařízení. Níže uvedené informace platí pro počítače, které používají klienta Intune.

## Požadavky na správu stolních počítačů Intune

**Hardware:**:
Toto jsou minimální požadavky na hardware pro instalaci klienta Intune:

|Požadavek|Další informace|
|---------------|--------------------|
|Síť|Klient vyžaduje, aby byl počítač připojený k Internetu.|
|Procesor a paměť|Viz požadavky na procesor a paměť RAM pro operační systém počítače.|
|Místo na disku|200 MB volného místa na disku před instalací klientského softwaru.|

**Software**:
Požadavky na software pro instalaci klienta:

|Požadavek|Další informace|
|---------------|--------------------|
|Oprávnění správce|Účet, který instaluje klientský software, musí mít oprávnění místního správce k tomuto počítači.|
|Instalační služba systému Windows verze 3.1|Na počítači musí být Instalační služba systému Windows minimálně verze 3.1.<br /><br />Pokud chcete zobrazit verzi Instalační služby systému Windows na počítači:<br /><br />-   Na počítači klikněte pravým tlačítkem na **%windir%\System32\msiexec.exe** a potom klikněte na **Vlastnosti**..<br /><br />Nejnovější verzi Instalační služby systému Windows můžete stáhnout ze stránky [Windows Installer Redistributables](http://go.microsoft.com/fwlink/?LinkID=234258) na webu Microsoft Developer Network.|
|Odebrání nekompatibilního klientského softwaru|Před instalací klientského softwaru Intune musíte z daného počítače odinstalovat veškerý klientský software Configuration Manageru a System Management Serveru.|

## Instalace počítačového klienta Intune
Prvním krokem při správě počítačů s Windows pomocí Intune je instalace klienta. Klientský software se dá nainstalovat, když je počítač zaregistrovaný v Intune jedním z následujících způsobů:

-   Můžete [ručně nasadit klientský software Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md#to-manually-deploy-the-client-software). U tohoto typu nasazení správce stáhne klientský software Intune a ručně ho nainstaluje do všech počítačů.

    Pokud chcete stáhnout klientský software Intune, otevřete konzolu správy Intune a v části Stažení klientského softwaru stáhněte balíček klientského softwaru. Po dokončení instalace klientského softwaru Intune automaticky nainstaluje další software nezbytný ke správě počítače.

-   Stejné soubory, které jste stáhli pro ruční instalaci klienta Intune, můžete použít pro [nasazení klienta do počítačů připojených k doméně pomocí objektů zásad skupiny Active Directory](install-the-windows-pc-client-with-microsoft-intune.md#to-automatically-deploy-the-client-software-by-using-group-policy)..

-   [Koncoví uživatelé můžou své počítače sami zaregistrovat](install-the-windows-pc-client-with-microsoft-intune.md#how-users-can-self-enroll-their-computers) pomocí portálu společnosti Intune. Každý zaregistrovaný počítač se pak automaticky propojí s uživatelským účtem použitým při instalaci klientského softwaru Intune.

-   Klientský software Intune můžete do počítačů taky nasadit jako součást [nasazení operačního systému](install-the-windows-pc-client-with-microsoft-intune.md#install-the-microsoft-intune-client-software-as-part-of-an-image)..

## Správa počítačů pomocí počítačového klienta Intune
Po dokončení instalace klienta Intune klientský software povolí několik funkcí správy počítačů, včetně [správy aplikací](deploy-apps-in-microsoft-intune.md), Endpoint Protection, inventáře softwaru a hardwaru, vzdáleného řízení (prostřednictvím žádostí o vzdálenou pomoc), aktualizací softwaru a vytváření sestav nastavení dodržování předpisů.

Některé úlohy správy počítačů povolené počítačovým klientem se spravují pomocí zásad Intune, jako třeba:

-   Konfigurace [nastavení brány Windows Firewall](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) ve spravovaných počítačích.

-   Konfigurace [nastavení aktualizací softwaru](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) , které mají spravované počítače kontrolovat, a stažení požadovaných aktualizací softwaru.

-   Pomoc při zabezpečení spravovaných počítačů před potenciálními hrozbami a škodlivým softwarem pomocí správy [monitorování v reálném čase a Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).

Kromě akcí klientského agenta Intune prováděných lokálně v jednotlivých počítačích je možné konzolu správce Intune využít taky k dalším [běžným úlohám správy](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) u počítačů s Windows s nainstalovaným klientem:

-   Zobrazení informací o inventáři hardwaru a softwaru pro spravované počítače

-   Vzdálené restartování počítače

-   Vyřazení počítače pro odinstalaci klientského softwaru a jeho odebrání ze správy pomocí Intune

-   Propojení uživatelů ke konkrétním spravovaným počítačům

-   Odpověď na žádosti o vzdálenou pomoc

Klientský agent Intune obvykle běží tiše na pozadí a nevyžaduje skoro žádnou interakci ze strany uživatele ani řešení potíží. Pokud byste ale potřebovali pomoc při řešení potíží se správou počítačů, je dostupných několik [prostředků, které vám je pomůžou vyřešit](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune)..


<!--HONumber=May16_HO1-->

