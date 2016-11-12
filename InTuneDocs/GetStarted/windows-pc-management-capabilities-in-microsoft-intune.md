---
title: "Možnosti softwarového klienta Intune pro počítače | Microsoft Intune"
description: "Přečtěte si o možnostech Intune při správě počítačů se systémem Windows pomocí softwarového klienta Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: e786cd33b5c963fa373d281e93721d0dd0f5456c


---

# Možnosti správy počítačů s Windows při použití softwarového klienta Intune
Ve většině scénářů si svoje zařízení zaregistrujete v Microsoft Intune. Tato služba poskytuje větší sadu funkcí. Ke správě počítačů můžete ale také použít softwarového klienta Intune, který poskytuje následující funkce:

-   **[Správa aktualizací softwaru](/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)** – Počítače můžete udržovat stále aktuální a můžete rozhodnout, kdy se mají aktualizace instalovat.

-   **[Zásady brány Windows Firewall](/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)** – Tyto zásady pomáhají zajistit, že v žádném počítači používaném ve vaší společnosti není neaktivní nebo nesprávně nakonfigurovaná brána Windows Firewall.

-   **[Ochrana proti malwaru](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)** – Součástí Intune je služba Endpoint Protection, která pomáhá chránit počítače před malwarem.

-   **[Vzdálená pomoc](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-to-windows-pcs-that-use-the-intune-client-software )** – Intune umožňuje uživatelům kontaktovat pracovníky technické podpory, kteří jim pak můžou pomoct prostřednictvím funkce vzdálené plochy, která je součástí Intune (vyžaduje software TeamViewer).

-   **[Správa licencí na software](/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)** – Můžete sledovat, kolik licencí softwaru je dostupných a kolik z nich se právě používá.
-   **[Nasazení aplikací](/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)** – Do počítačů, které spravujete, můžete nasadit software. Pokud ke správě počítačů použijete softwarového klienta, některé funkce správy nejsou dostupné.


Intune podporuje instalaci softwarového klienta až v 7000 zařízení se systémem Windows.

## Požadavky na operační systém
Intune může spravovat počítače s následujícími verzemi Windows (32bitové i 64bitové):


-   **Windows Vista** – verze Business, Enterprise a Ultimate

-   **Windows 7** – verze Pro, Enterprise a Ultimate (bez aktualizace Service Pack nebo s aktualizací SP1)

-   **Windows 8** – verze Pro a Enterprise

-   **Windows 8.1** – verze Pro a Enterprise

- **Windows 10** – verze Pro, Education a Enterprise


## Minimální požadavky na hardware
Toto jsou minimální požadavky na hardware pro instalaci softwarového klienta Intune:

|Požadavek|Podrobnosti|
|---------------|--------------------|
|Síť|Klient vyžaduje, aby byl počítač připojený k Internetu.|
|Procesor a paměť|Viz požadavky na procesor a paměť RAM pro operační systém počítače.|
|Místo na disku|200 MB volného místa na disku před instalací klientského softwaru.|

## Další požadavky
Toto jsou požadavky na software pro instalaci softwarového klienta Intune:

|Požadavek|Podrobnosti|
|---------------|--------------------|
|Oprávnění správce|Účet, který instaluje klientský software, musí mít oprávnění místního správce k danému počítači.|
|Instalační služba systému Windows verze 3.1|Na počítači musí být Instalační služba systému Windows minimálně verze 3.1.|
|Odebrání nekompatibilního klientského softwaru|Před instalací klientského počítačového softwaru Intune je potřeba odinstalovat z příslušného počítače tento klientský software:<br /><br />– Všechny verze Configuration Manageru<br />– Všechny verze Microsoft Systems Management Serveru (SMS)|

### Související témata
[Možnosti správy zaregistrovaných zařízení v Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Oct16_HO4-->


