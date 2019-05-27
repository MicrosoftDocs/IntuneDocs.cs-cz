---
title: Data JAMF Pro odesílá do Intune
titleSuffix: Microsoft Intune
description: Seznam dat, která odesílá Jamf Pro Microsoft Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 287ed06ddab0b98117aa4a75942087f360e4656d
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66048554"
---
# <a name="data-jamf-pro-sends-to-intune"></a>Data, která Jamf Pro odesílaná do Intune

Při použití [Jamf Pro](https://www.jamf.com) spravovat vaši koncoví uživatelé Mac v Intune, Jamf Pro zaznamená informace o inventáři o spravovaných zařízeních macOS. Jamf Pro dodá do Intune následující informace:

* ID zařízení v Azure AD
* Stav inventáře JAMF (stav inventáře počítače připojeného k Jamf Pro během posledních 24 hodin)
* Verze operačního systému
* ID uživatele v Azure AD
* Šifrované (FileVault 2)
* Stav serveru gatekeeper
* Heslo: minimální počet znakových sad
* Vypršení platnosti hesla (dny)
* Typ hesla – jednoduché, alfanumerické nebo neznámé
* Zakázat automatické přihlášení
* Požadovaná délka hesla
* Heslo: počet předchozích hesel, aby se předešlo opětovnému použití
* Ochrana Integrity systému
* Poslední vrácení se změnami
* Typ architektury
* Dostupné sloty paměti RAM
* Kapacita baterie
* Spouštěcí paměť ROM
* Rychlost sběrnice
* Velikost mezipaměti
* Název zařízení
* Připojení k doméně
* ID Jamf
* Adresa MAC
* Vytvoření
* Model
* Identifikátor modelu
* Rychlost síťové karty
* Počet jader
* Počet procesorů
* Operační systém
* Platforma
* Rychlost procesoru
* Typ procesoru
* Sekundární adresa MAC
* Sériové číslo
* Verze řadiče pro správu systému (SMC)
* Celkové paměti RAM
* UDID
* E-mail uživatele


Zařízení spravované prostřednictvím Jamf můžete z konzoly Intune odebrat výběrem možnosti **Odstranit** v zobrazení **Všechna zařízení**. Hromadné odstranění zařízení se dá povolit výběrem více zařízení a kliknutím na **Odstranit**.

Získejte informace o [odebírání zařízení spravovaného prostřednictvím Jamf v dokumentaci k Jamf Pro](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information). Můžete také pomocí lístku podpory požádat o další pomoc [podporu Jamf](https://www.jamf.com/support/). 

