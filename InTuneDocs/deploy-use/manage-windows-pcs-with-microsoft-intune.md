---
title: "Správa počítačů s klientským softwarem | Dokumentace Microsoftu"
description: "Spravujte počítače s Windows pomocí instalace klientského softwaru Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 2e7062169ceb855f03a13d1afb4b4de41af593ac
ms.openlocfilehash: 10ba007095182c9cb07710656ba5f275e254d92e
ms.lasthandoff: 02/15/2017


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Správa počítačů s Windows pomocí klientského počítačového softwaru Intune
Preferovaný způsob registrace počítačů s Windows do Intune je [registrace počítačů s Windows jako mobilních zařízení](set-up-windows-device-management-with-microsoft-intune.md). Existuje ale také další možnost – registrace a správa počítačů s Windows na základě instalace klientského softwaru Intune, jak je popsáno v tomto tématu.

Intune spravuje počítače s Windows pomocí zásad podobně jako objekty zásad skupiny (GPO) služby AD DS (Active Directory Domain Services) Windows Serveru. Pokud budete počítače připojené k doméně Active Directory spravovat pomocí Intune, [je nutné, aby zásady Intune nekolidovaly se žádnými objekty zásad skupiny](resolve-gpo-and-microsoft-intune-policy-conflicts.md), které jsou nastavené pro vaši organizaci. Další informace najdete v článku [Objekty zásad skupiny](https://technet.microsoft.com/library/hh147307.aspx).

## <a name="policies-and-app-deployments-for-the-intune-software-client"></a>Zásady a nasazení aplikace pro klientský software Intune

I když klientský software Intune podporuje [možnosti správy, které pomáhají chránit počítače](policies-to-protect-windows-pcs-in-microsoft-intune.md) pomocí správy aktualizací softwaru, brány Windows Firewall a služby Endpoint Protection, nemůžou být na počítače spravované pomocí klientského softwaru Intune zacílené jiné zásady Intune, včetně nastavení zásad **Windows**, která jsou specifická pro správu mobilních zařízení. 

Pokud ke správě počítačů s Windows používáte klientský software Intune, můžete používat jenom zásady, které jsou uvedené v části **Správa počítače**.

  ![Výběr šablony pro nové zásady počítačů PC se systémem Windows](../media/select-template-for-pc-policy.png)

Podrobný popis zásad, které je možné nastavit, najdete v těchto tématech:

- [Použití zásad k ochraně počítačů PC s Windows, na nichž běží klientský software Intune](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)
- [Udržování počítačů s Windows v aktuálním stavu díky softwarovým aktualizacím v Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)
- [Pomoc při ochraně počítačů s Windows pomocí zásad brány Windows Firewall v Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)
- [Pomoc se zabezpečením počítačů s Windows pomocí služby Endpoint Protection pro Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

K nasazování aplikací můžete navíc použít pouze Instalační službu systému Windows (.exe, .msi).

  ![Výběr platformy a umístění softwarových souborů klientského počítače](../media/select-platform-of-software-files-for-pc-agent.png)

> [!NOTE]
> Zařízení s Windows 8.1 nebo novější verzí můžete spravovat jako počítače pomocí klientského softwaru Intune nebo jako mobilní zařízení pomocí funkce pro správu mobilních zařízení (MDM). Není možné používat obě metody současně. Než se tedy rozhodnete používat ke správě počítačů klientský software Intune, pečlivě svoje rozhodnutí zvažte. Toto téma se týká jenom správy zařízení jako počítačů pomocí klientského softwaru Intune.

## <a name="requirements-for-intune-pc-client-management"></a>Požadavky na správu počítačového klienta Intune

**Hardware**: Minimální požadavky na hardware pro instalaci klientského softwaru Intune:

|Požadavek|Další informace|
|---------------|--------------------|
|Síť|Klient vyžaduje, aby byl počítač připojený k Internetu.|
|Procesor a paměť|Viz požadavky na procesor a paměť RAM pro operační systém počítače.|
|Místo na disku|200 MB volného místa na disku před instalací klientského softwaru.|

**Software**: Požadavky na software pro instalaci klientského softwaru:

|Požadavek|Další informace|
|---------------|--------------------|
|Operační systém | Zařízení s Windows se systémem Windows Vista nebo novějším. </br></br>**Verze Home Edition nejsou podporovány.**|
|Oprávnění správce|Účet, který instaluje klientský software, musí mít oprávnění místního správce pro toto zařízení.|
|Instalační služba systému Windows verze 3.1|Na počítači musí být Instalační služba systému Windows minimálně verze 3.1.<br /><br />Pokud chcete zobrazit verzi Instalační služby systému Windows na počítači:<br /><br />  Na počítači klikněte pravým tlačítkem myši na **%windir%\System32\msiexec.exe** a potom klikněte na **Vlastnosti**.<br /><br />Nejnovější verzi Instalační služby systému Windows můžete stáhnout ze stránky [Windows Installer Redistributables](http://go.microsoft.com/fwlink/?LinkID=234258) na webu Microsoft Developer Network.|
|Odebrání nekompatibilního klientského softwaru|Před instalací klientského softwaru Intune odinstalujte z počítače tento klientský software: Configuration Manager, Operations Manager, Operations Management Suite a Service Manager.|

## <a name="computer-management-capabilities-with-the-intune-client-software"></a>Možnosti správy počítačů pomocí klientského softwaru Intune

Po instalaci klientského softwaru Intune patří mezi možnosti správy tyto funkce: 

- [Správa aplikací](deploy-apps-in-microsoft-intune.md)

- [Sledování v reálném čase a Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) – Endpoint Protection je totéž jako Windows Defender. Endpoint Protection se používal pro Windows 7 a Windows 8. Pro Windows 10 a novější verze se název produktu změnil na Windows Defender.

- [Správa nastavení brány Windows Firewall](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), inventář hardwaru a softwaru, vzdálené řízení (prostřednictvím žádostí o vzdálenou pomoc)

- [Nastavení aktualizací softwaru](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)

- Sestavy s nastaveními dodržování předpisů

V konzole správce Intune se některé části, jako například Aktualizace, Ochrana a Licence, zobrazí jenom v případě, že jsou vaše zařízení zaregistrovaná pomocí klientského softwaru Intune.

  ![Položky konzoly správce, které se zobrazují pouze pro počítačového klienta](../media/admin-console-settings-only-for-pc-agent.png)

Konzolu správce Intune můžete využít také k dalším běžným úlohám správy u počítačů s Windows s nainstalovaným klientem:

-   Zobrazení informací o inventáři hardwaru a softwaru pro spravované počítače
-   Vzdálené restartování počítače
-   Vyřazení počítače pro odinstalaci klientského softwaru a jeho odebrání ze správy pomocí Intune
-   Propojení uživatelů ke konkrétním spravovaným počítačům
-   Odpověď na žádosti o vzdálenou pomoc

Další informace o výše uvedených úkolech najdete v části, která se týká [běžných úloh správy počítače](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

## <a name="management-limitations-of-the-intune-client-software"></a>Omezení správy klientského softwaru Intune

Některé možnosti správy, které je možné použít ke správě počítačů PC jako mobilních zařízení, není možné použít u počítačů PC, které se spravují pomocí klientského softwaru Intune:

-   Úplné vymazání (selektivní vymazání je k dispozici)

-   podmíněný přístup

## <a name="help-with-troubleshooting"></a>Pomoc s odstraňováním problémů

Klientský software Intune obvykle běží tiše na pozadí a nevyžaduje skoro žádnou interakci ze strany uživatele ani řešení potíží. Pokud potřebujete vyřešit problémy týkající se správy počítačů PC, můžete si projít informace v protokolech. Klientský software Intune a odpovídající protokoly jsou nainstalované v adresáři %Program Files%\Microsoft\OnlineManagement.

Můžete si také projít informace v článku [Řešení potíží s instalací klientů v Microsoft Intune](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune), kde zjistíte, k jakým problémům by mohlo dojít a jaká (alternativní) řešení je možné použít.

