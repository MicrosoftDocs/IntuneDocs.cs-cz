---
title: "Možnosti softwarového klienta Intune pro počítače | Microsoft Intune"
description: "Přečtěte si o možnostech Intune při správě počítačů se systémem Windows pomocí softwarového klienta Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 12d75bc67fd61a2e807eed2543f21b756a65a900
ms.openlocfilehash: 3066ef98c0a1df6fc0ae455860635e7c12f82c4f


---

# Možnosti správy počítačů s Windows při použití softwarového klienta Intune
Ve většině scénářů si svoje zařízení zaregistrujete v Microsoft Intune. Tato služba poskytuje větší sadu funkcí. Ke správě počítačů můžete ale také použít softwarového klienta Intune, který poskytuje následující funkce:

-   **Správa aktualizací softwaru** – Počítače můžete udržovat stále aktuální a můžete rozhodnout, kdy se mají aktualizace instalovat.

-   **Zásady brány Windows Firewall** – Tyto zásady pomáhají zajistit, že v žádném počítači používaném ve vaší společnosti není neaktivní nebo nesprávně nakonfigurovaná brána Windows Firewall.

-   **Ochrana proti malwaru** – Součástí Intune je služba Endpoint Protection, která pomáhá chránit počítače před malwarem.

-   **Vzdálená pomoc** – Intune umožňuje uživatelům kontaktovat pracovníky technické podpory, kteří jim pak můžou pomoct prostřednictvím funkce vzdálené plochy, která je součástí Intune (vyžaduje software TeamViewer).

-   **Správa licencí na software** – Můžete sledovat, kolik licencí softwaru je dostupných a kolik z nich se právě používá.
-   **Nasazení aplikací** – Do počítačů, které spravujete, můžete nasadit software. Pokud ke správě počítačů použijete softwarového klienta, některé funkce správy nejsou dostupné.


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



<!--HONumber=Aug16_HO4-->


