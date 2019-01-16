---
title: Data JAMF Pro odesílá do Intune | Microsoft Intune
description: Seznam dat, která odesílá Jamf Pro Microsoft Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 5b58a92ed59d4485f06370672d8c335ff2fffcc7
ms.sourcegitcommit: 7c41f42d6e398ed46aa602ec8aaa4f39aaf92772
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54325059"
---
# <a name="data-jamf-pro-sends-to-intune"></a>Data Jamf Pro odesílaná do Intune

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

