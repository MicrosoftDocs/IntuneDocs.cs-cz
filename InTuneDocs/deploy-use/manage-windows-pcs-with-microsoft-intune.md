---
title: "Správa počítačů s klientským softwarem | Dokumentace Microsoftu"
description: "Spravujte počítače s Windows pomocí instalace klientského softwaru Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3d2f3a7233ea7a5127baf5a08be1ccb41f717244
ms.openlocfilehash: 4344251ede6d8cc338d84782d224d87fd78d5bd8


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Správa počítačů s Windows pomocí klientského počítačového softwaru Intune
Namísto [registrace počítačů s Windows jako mobilních zařízení](set-up-windows-device-management-with-microsoft-intune.md) můžete počítače s Windows registrovat a spravovat pomocí instalace klientského softwaru Intune.

Intune spravuje počítače s Windows pomocí zásad podobně jako objekty zásad skupiny (GPO) služby AD DS (Active Directory Domain Services) Windows Serveru. Pokud budete počítače připojené k doméně Active Directory spravovat pomocí Intune, [je nutné, aby zásady Intune nekolidovaly se žádnými objekty zásad skupiny](resolve-gpo-and-microsoft-intune-policy-conflicts.md), které jsou nastavené pro vaši organizaci.

I když softwarový klient Intune podporuje [možnosti správy, které pomáhají chránit počítače](policies-to-protect-windows-pcs-in-microsoft-intune.md) pomocí správy aktualizací softwaru, brány Windows Firewall a služby Endpoint Protection, počítače spravované pomocí softwarového klienta Intune nemůžou být cílem jiných zásad Intune, včetně nastavení zásad **Windows**, která jsou specifická pro správu mobilních zařízení.

> [!NOTE]
> Zařízení s Windows 8.1 nebo novější verzí můžete spravovat jako počítače pomocí klienta Intune nebo jako mobilní zařízení pomocí funkce pro správu mobilních zařízení (MDM). Obě metody nejde použít současně. Toto téma se týká jenom správy zařízení jako počítače pomocí softwarového klienta Intune.

## <a name="requirements-for-intune-pc-client-management"></a>Požadavky na správu počítačového klienta Intune

**Hardware**: Toto jsou minimální požadavky na hardware pro instalaci klienta Intune:

|Požadavek|Další informace|
|---------------|--------------------|
|Síť|Klient vyžaduje, aby byl počítač připojený k Internetu.|
|Procesor a paměť|Viz požadavky na procesor a paměť RAM pro operační systém počítače.|
|Místo na disku|200 MB volného místa na disku před instalací klientského softwaru.|

**Software**: Toto jsou požadavky na software pro instalaci klienta:

|Požadavek|Další informace|
|---------------|--------------------|
|Operační systém | Zařízení s Windows se systémem Windows Vista nebo novějším. Verze Home Edition nejsou podporovány.|
|Oprávnění správce|Účet, který instaluje klientský software, musí mít oprávnění místního správce pro toto zařízení.|
|Instalační služba systému Windows verze 3.1|Na počítači musí být Instalační služba systému Windows minimálně verze 3.1.<br /><br />Pokud chcete zobrazit verzi Instalační služby systému Windows na počítači:<br /><br />  Na počítači klikněte pravým tlačítkem myši na **%windir%\System32\msiexec.exe** a potom klikněte na **Vlastnosti**.<br /><br />Nejnovější verzi Instalační služby systému Windows můžete stáhnout ze stránky [Windows Installer Redistributables](http://go.microsoft.com/fwlink/?LinkID=234258) na webu Microsoft Developer Network.|
|Odebrání nekompatibilního klientského softwaru|Před instalací klientského softwaru Intune odinstalujte z počítače tento klientský software: Configuration Manager, Operations Manager, Operations Management Suite a Service Manager.|

## <a name="computer-management-with-the-intune-computer-client"></a>Správa počítačů pomocí počítačového klienta Intune
Po instalaci klientského softwaru Intune patří mezi možnosti správy tyto funkce: 

- [Správa aplikací](deploy-apps-in-microsoft-intune.md)

- [Sledování v reálném čase a Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)

- [Správa nastavení brány Windows Firewall](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), inventář hardwaru a softwaru, vzdálené řízení (prostřednictvím žádostí o vzdálenou pomoc)

- [Nastavení aktualizací softwaru](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)

- Sestavy s nastaveními dodržování předpisů

Některé možnosti správy dostupné pro počítače spravované jako mobilní zařízení nejsou k dispozici pro počítače spravované softwarovým klientem, například:

-   Úplné vymazání (selektivní vymazání je k dispozici)

-   Podmíněný přístup

-   Zásady systému Windows jiné než zásady pro **Správu počítače**

  ![Šablony zásad pro počítače s Windows](../media/pc_policy_template.png)

Kromě akcí klientského agenta Intune prováděných lokálně v jednotlivých počítačích je možné konzolu správce Intune využít taky k dalším [běžným úlohám správy](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) u počítačů s Windows s nainstalovaným klientem:

-   Zobrazení informací o inventáři hardwaru a softwaru pro spravované počítače

-   Vzdálené restartování počítače

-   Vyřazení počítače pro odinstalaci klientského softwaru a jeho odebrání ze správy pomocí Intune

-   Propojení uživatelů ke konkrétním spravovaným počítačům

-   Odpověď na žádosti o vzdálenou pomoc

Klientský agent Intune obvykle běží tiše na pozadí a nevyžaduje skoro žádnou interakci ze strany uživatele ani řešení potíží. Pokud byste ale potřebovali pomoc při řešení potíží se správou počítačů, je k dispozici několik [prostředků, které vám je pomůžou vyřešit](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune).



<!--HONumber=Dec16_HO3-->


