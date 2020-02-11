---
title: Používání virtuálních počítačů s Windows 10 s Microsoft Intune
titleSuffix: ''
description: Pokyny k používání virtuálních počítačů s Windows 10 s Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 486ca7eae1b1e8b016f44c735ec04a23145421a8
ms.sourcegitcommit: e1ff157f692983b49bdd6e20cc9d0f93c3b3733c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124975"
---
# <a name="using-windows-10-virtual-machines-with-intune"></a>Používání virtuálních počítačů s Windows 10 s Intune

Intune podporuje správu virtuálních počítačů s Windows 10 Enterprise s určitými omezeními. Správa služby Intune nezávisí na tom, nebo brání správě virtuálních počítačů s Windows stejného virtuálního počítače.

Při správě virtuálních počítačů s Windows 10 pomocí Intune mějte na paměti následující skutečnosti:

## <a name="enrollment"></a>Registrace
- Ve službě Intune nedoporučujeme spravovat virtuální počítače na vyžádání a hostitele relací. Každý virtuální počítač musí být při vytvoření zaregistrován. I když se virtuální počítače pravidelně odstraňují, zůstanou v Intune záznamy osamocené zařízení, dokud se [nevyčistí](../remote-actions/devices-wipe.md#automatically-delete-devices-with-cleanup-rules). 
- Nepodporují se samostatné nasazení Windows autopilotu a typy nasazení White šetrnější, protože vyžadují fyzický Trusted Platform Module (TPM). 
- Registrace na základě služby mimo prostředí není podporovaná na virtuálních počítačích, ke kterým se dá dostat jenom pomocí protokolu RDP (například virtuálních počítačů hostovaných v Azure). Toto omezení znamená:
    - Windows autopilot a komerční OOBE se nepodporují.
    - Možnosti stránky stavu registrace pro zásady kontextu zařízení nejsou podporované.

## <a name="configuration"></a>Konfigurace
Intune nepodporuje žádnou konfiguraci, která využívá modul Trusted Platform nebo správu hardwaru, včetně těchto:
- [Nastavení BitLockeru](../configuration/device-profiles.md#endpoint-protection)
- [Nastavení rozhraní pro konfiguraci firmwaru zařízení](../configuration/device-profiles.md#device-firmware-configuration-interface)

## <a name="reporting"></a>Generování sestav
Intune automaticky detekuje virtuální počítače a hlásí je jako "virtuální počítač" v **zařízeních** > **všechna zařízení** > vyberte pole **model** > **Přehled** > . 

Naplnění virtuálních počítačů můžou přispět k sestavám zařízení nesplňujících požadavky, protože se nemůžou [zaregistrovat ve službě Intune](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

## <a name="retirement"></a>Důchod
Pokud máte přístup přes protokol RDP, nepoužívejte [akci vymazání](../remote-actions/devices-wipe.md#wipe). Akce vymazání odstraní nastavení RDP virtuálního počítače a zabrání vám v připojení znovu.


