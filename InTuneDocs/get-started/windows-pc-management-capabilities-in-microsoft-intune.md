---
title: "Možnosti softwarového klienta Intune pro počítače | Dokumentace Microsoftu"
description: "Přečtěte si o možnostech Intune při správě počítačů se systémem Windows pomocí softwarového klienta Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f268cf29461447306d0f5c3ca06d541d9a03a49d
ms.openlocfilehash: 36a20feed1756ea8dde2230db81099b6c5f8c7f6
ms.lasthandoff: 12/16/2016


---

# <a name="windows-pc-management-capabilities-when-you-use-the-intune-software-client"></a>Možnosti správy počítačů s Windows při použití softwarového klienta Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ve většině scénářů si svoje zařízení zaregistrujete v Microsoft Intune. Tato služba poskytuje větší sadu funkcí. Ke správě počítačů můžete ale také použít softwarového klienta Intune, který poskytuje následující funkce:

-   **[Správa aktualizací softwaru](/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)** – Počítače můžete udržovat stále aktuální a můžete rozhodnout, kdy se mají aktualizace instalovat.

-   **[Zásady brány Windows Firewall](/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)** – Tyto zásady pomáhají zajistit, že v žádném počítači používaném ve vaší společnosti není neaktivní nebo nesprávně nakonfigurovaná brána Windows Firewall.

-   **[Ochrana proti malwaru](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)** – Součástí Intune je služba Endpoint Protection, která pomáhá chránit počítače před malwarem.

-   **[Vzdálená pomoc](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-to-windows-pcs-that-use-the-intune-client-software )** – Intune umožňuje uživatelům kontaktovat pracovníky technické podpory, kteří jim pak můžou pomoct prostřednictvím funkce vzdálené plochy, která je součástí Intune (vyžaduje software TeamViewer).

-   **[Správa licencí na software](/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)** – Můžete sledovat, kolik licencí softwaru je dostupných a kolik z nich se právě používá.
-   **[Nasazení aplikací](/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)** – Do počítačů, které spravujete, můžete nasadit software. Pokud ke správě počítačů použijete softwarového klienta, některé funkce správy nejsou dostupné.


Intune podporuje instalaci softwarového klienta až v 7000 zařízení se systémem Windows.

## <a name="operating-system-requirements"></a>Požadavky na operační systém
Intune může spravovat počítače s následujícími verzemi Windows (32bitové i 64bitové):


-   **Windows Vista** – verze Business, Enterprise a Ultimate

-   **Windows 7** – verze Pro, Enterprise a Ultimate (bez aktualizace Service Pack nebo s aktualizací SP1)

-   **Windows 8** – verze Pro a Enterprise

-   **Windows 8.1** – verze Pro a Enterprise

- **Windows 10** – verze Pro, Education a Enterprise


## <a name="minimum-hardware-requirements"></a>Minimální požadavky na hardware
Toto jsou minimální požadavky na hardware pro instalaci softwarového klienta Intune:

|Požadavek|Podrobnosti|
|---------------|--------------------|
|Síť|Klient vyžaduje, aby byl počítač připojený k Internetu.|
|Procesor a paměť|Viz požadavky na procesor a paměť RAM pro operační systém počítače.|
|Místo na disku|200 MB volného místa na disku před instalací klientského softwaru.|

## <a name="further-requirements"></a>Další požadavky
Toto jsou požadavky na software pro instalaci softwarového klienta Intune:

|Požadavek|Podrobnosti|
|---------------|--------------------|
|Oprávnění správce|Účet, který instaluje klientský software, musí mít oprávnění místního správce k danému počítači.|
|Instalační služba systému Windows verze 3.1|Na počítači musí být Instalační služba systému Windows minimálně verze 3.1.|
|Odebrání nekompatibilního klientského softwaru|Před instalací klientského počítačového softwaru Intune je potřeba odinstalovat z příslušného počítače tento klientský software:<br /><br />– Všechny verze Configuration Manageru<br />– Všechny verze Microsoft Systems Management Serveru (SMS)|

### <a name="see-also"></a>Související témata
[Možnosti správy zaregistrovaných zařízení v Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)

