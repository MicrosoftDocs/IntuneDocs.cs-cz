---
# required metadata

title: Možnosti správy počítačů s Windows | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: owenyen
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Možnosti správy počítačů s Windows (pomocí počítačového klienta Microsoft Intune)
Ve většině scénářů si svoje zařízení zaregistrujete v Microsoft Intune. Tato služba poskytuje větší sadu funkcí než počítačový klient Intune. Ke správě počítačů můžete ale také použít počítačového klienta Intune, který poskytuje následující funkce:

-   **Správa aktualizací softwaru.** Vaše počítače můžou být pořád aktuální. Můžete určit, kdy se mají aktualizace použít.

-   **Zásady brány Windows Firewall.** Tyto zásady pomáhají zajistit, že v žádném počítači používaném ve vaší společnosti není neaktivní nebo nesprávně nakonfigurovaná brána Windows Firewall.

-   **Ochrana proti malwaru.** Součástí Intune je služba Endpoint Protection, která pomáhá chránit počítače před malwarem.

-   **Vzdálená pomoc:** Intune umožňuje uživatelům kontaktovat pracovníky technické podpory, kteří jim pak můžou pomoct prostřednictvím funkce vzdálené plochy, která je součástí Intune <!--- (requires TeamViewer software)--->.

-   **Správa licencí na software.** Můžete sledovat, kolik licencí softwaru je dostupných a kolik z nich se právě používá.
-   **Nasazení aplikací.** Do počítačů, které spravujete, můžete nasadit software. Pokud ke správě počítačů použijete klientský software, některé funkce správy nejsou dostupné.


## Požadavky na operační systém
Intune může spravovat počítače s následujícími verzemi Windows (x86 i x64):


-   **Windows Vista** – verze Business, Enterprise a Ultimate

-   **Windows 7** – verze Pro, Enterprise a Ultimate (bez aktualizace Service Pack nebo s aktualizací SP1)

-   **Windows 8** – verze Pro a Enterprise

-   **Windows 8.1** – verze Pro a Enterprise

- **Windows 10** – verze Home, Pro, Education a Enterprise


## Minimální požadavky na hardware
Toto jsou minimální požadavky na hardware pro instalaci počítačového klienta Intune:

|Požadavek|Podrobnosti|
|---------------|--------------------|
|Síť|Klient vyžaduje, aby byl počítač připojený k Internetu.|
|Procesor a paměť|Viz požadavky na procesor a paměť RAM pro operační systém počítače.|
|Místo na disku|200 MB volného místa na disku před instalací klientského softwaru.|

## Další požadavky
Toto jsou požadavky na software pro instalaci počítačového klienta Intune:

|Požadavek|Podrobnosti|
|---------------|--------------------|
|Oprávnění správce|Účet, který instaluje klientský software, musí mít oprávnění místního správce k tomuto počítači.|
|Instalační služba systému Windows verze 3.1|Na počítači musí být nainstalovaná Instalační služba systému Windows minimálně verze 3.1.|
|Odebrání nekompatibilního klientského softwaru|Před instalací klientského počítačového softwaru Intune je potřeba odinstalovat z příslušného počítače tento klientský software:<br /><br />– Všechny verze Configuration Manageru<br />– Všechny verze Microsoft Systems Management Serveru (SMS)|

### Související témata
[Možnosti správy mobilních zařízení v Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)


<!--HONumber=Jun16_HO2-->


