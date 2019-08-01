---
title: Data JAMF pro odesílá do Intune.
titleSuffix: Microsoft Intune
description: Projděte si seznam dat, která Jamf pro odesílá do Microsoft Intune při integraci Jamf pro pro správu počítačů Mac s Intune.
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
ms.openlocfilehash: ce9a92a9fffad13c6723504735b1b1cb9442f61f
ms.sourcegitcommit: 864fdf995c2b41f104a98a7e2665088c2864774f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/31/2019
ms.locfileid: "68680020"
---
# <a name="data-jamf-pro-sends-to-intune"></a>Data, která Jamf Pro odesílaná do Intune

Pokud ke správě počítačů Mac koncových uživatelů s Intune používáte [Jamf pro](https://www.jamf.com) , zachytí Jamf pro informace o inventáři spravovaných zařízení MacOS. 

## <a name="data"></a>Data  
Jamf Pro dodá do Intune následující informace:  

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
* OS
* Platforma
* Rychlost procesoru
* Typ procesoru
* Sekundární adresa MAC
* Sériové číslo
* Verze řadiče pro správu systému (SMC)
* Celková paměť RAM
* UDID
* E-mail uživatele

Zařízení spravované prostřednictvím Jamf můžete z konzoly Intune odebrat výběrem možnosti **Odstranit** v zobrazení **Všechna zařízení**. Hromadné odstranění zařízení se dá povolit výběrem více zařízení a kliknutím na **Odstranit**.

## <a name="next-steps"></a>Další postup
Získejte informace o [odebírání zařízení spravovaného prostřednictvím Jamf v dokumentaci k Jamf Pro](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information). Můžete také pomocí lístku podpory požádat o další pomoc [podporu Jamf](https://www.jamf.com/support/). 

