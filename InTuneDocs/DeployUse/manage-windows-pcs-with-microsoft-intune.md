---
title: "Správa počítačů s klientským softwarem | Microsoft Intune"
description: "Spravujte počítače s Windows pomocí instalace klientského softwaru Intune."
keywords: 
author: nathbarn
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
ms.sourcegitcommit: 16be49504b24269f9463905ab5767acbda136a0a
ms.openlocfilehash: a13c03cde29c46a78577b58f85daad30a076bf89


---

# Správa počítačů s Windows pomocí klientského počítačového softwaru Intune
Namísto [registrace počítačů s Windows jako mobilních zařízení](set-up-windows-device-management-with-microsoft-intune.md) můžete počítače s Windows registrovat a spravovat pomocí instalace klientského softwaru Intune.

Intune spravuje počítače s Windows pomocí zásad podobně jako objekty zásad skupiny (GPO) služby AD DS (Active Directory Domain Services) Windows Serveru. Pokud budete počítače připojené k doméně Active Directory spravovat pomocí Intune, měli byste [ověřit, že zásady Intune nejsou v konfliktu se žádnými objekty zásad skupiny](resolve-gpo-and-microsoft-intune-policy-conflicts.md), které jsou nastavené pro vaši organizaci.

I když softwarový klient Intune podporuje [zásady, které pomáhají chránit počítače](policies-to-protect-windows-pcs-in-microsoft-intune.md) pomocí správy aktualizací softwaru, brány Windows Firewall a služby Endpoint Protection, počítače spravované pomocí softwarového klienta Intune nemůžou být cílem dalších zásad Intune, včetně nastavení zásad **Windows**, která jsou specifická pro správu mobilních zařízení.

> [!NOTE]
> Zařízení se systémem Windows 8.1 nebo novějším lze spravovat buď pomocí klienta Intune, nebo jako mobilní zařízení. Toto téma se vztahuje na počítače se softwarovým klientem Intune. Instalace klienta Intune současně s registrací ke správě mobilních zařízení není podporována.

## Požadavky na správu počítačového klienta Intune

**Hardware**: Toto jsou minimální požadavky na hardware pro instalaci klienta Intune:

|Požadavek|Další informace|
|---------------|--------------------|
|Síť|Klient vyžaduje, aby byl počítač připojený k Internetu.|
|Procesor a paměť|Viz požadavky na procesor a paměť RAM pro operační systém počítače.|
|Místo na disku|200 MB volného místa na disku před instalací klientského softwaru.|

**Software**: Toto jsou požadavky na software pro instalaci klienta:

|Požadavek|Další informace|
|---------------|--------------------|
|Operační systém | Zařízení s Windows se systémem Windows 7 nebo novějším. |
|Oprávnění správce|Účet, který instaluje klientský software, musí mít oprávnění místního správce pro toto zařízení.|
|Instalační služba systému Windows verze 3.1|Na počítači musí být Instalační služba systému Windows minimálně verze 3.1.<br /><br />Pokud chcete zobrazit verzi Instalační služby systému Windows na počítači:<br /><br />-   Na počítači klikněte pravým tlačítkem na **%windir%\System32\msiexec.exe** a potom klikněte na **Vlastnosti**.<br /><br />Nejnovější verzi Instalační služby systému Windows můžete stáhnout ze stránky [Windows Installer Redistributables](http://go.microsoft.com/fwlink/?LinkID=234258) na webu Microsoft Developer Network.|
|Odebrání nekompatibilního klientského softwaru|Před instalací klientského softwaru Intune musíte z daného počítače odinstalovat veškerý klientský software Configuration Manageru a System Management Serveru.|

## Správa počítačů pomocí počítačového klienta Intune
Po dokončení instalace klientského softwaru Intune budou funkce správy zahrnovat [správu aplikací](deploy-apps-in-microsoft-intune.md), [monitorování v reálném čase a Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md), [správu nastavení brány Windows Firewall](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), inventář softwaru a hardwaru, vzdálené řízení (prostřednictvím žádostí o vzdálenou pomoc), [nastavení aktualizací softwaru](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) a vytváření sestav nastavení dodržování předpisů.

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



<!--HONumber=Sep16_HO1-->


