---
title: Konfigurace nastavení ochrany koncových bodů v Microsoft Intune – Azure | Microsoft Docs
description: Nastavení ochrany koncových bodů určete při vytváření profilu zařízení s macOS nebo Windows 10 v Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 5/17/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
mr.reviewer: karthib
ms.openlocfilehash: c13c5d71d1ff631d7a3c84cd3f62037569757917
ms.sourcegitcommit: bc5e4dff18f5f9b79077a888f8a58dcc490708c0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/21/2019
ms.locfileid: "65975762"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Přidání nastavení ochrany koncových bodů v Intune

S Intune můžete použít profily konfigurace zařízení ke správě běžné funkce zabezpečení na zařízeních, včetně koncového bodu ochrany:
- Brána firewall 
- BitLocker
- Povolování a blokování aplikací  
- Program Windows Defender a šifrování

Můžete například vytvořit profil ochrany koncových bodů, který umožní uživatelům macOS instalovat aplikace jenom z Mac App Storu. Nebo můžete při spouštění aplikací na zařízeních s Windows 10 aktivovat filtr Windows SmartScreen.

Než vytvoříte profil, že podrobnosti, které můžete spravovat nastavení ochrany koncového bodu Intune pro každou podporovanou platformu najdete v následujících článcích: 
   - [Nastavení macOS](endpoint-protection-macos.md)
   - [Nastavení Windows 10](endpoint-protection-windows-10.md)

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení ochrany koncových bodů

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=20909).
3. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
4. Zadejte **Název** a **Popis** profilu ochrany koncových bodů.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete vlastní nastavení použít. V současné době můžete pro nastavení omezení zařízení zvolit jednu z těchto platforem:
   - **macOS**
   - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **Ochrana koncového bodu**. 
7. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Další informace:
   - [Nastavení macOS](endpoint-protection-macos.md)
   - [Nastavení Windows 10](endpoint-protection-windows-10.md)  

8. Po konfiguraci příslušných nastavení, vyberte **vytvořit** na **vytvořit profil** stránky.

   Profil se vytvoří a zobrazí se na stránce se seznamem profilů. Pokud chcete přiřadit tento profil ke skupinám, podívejte se na téma [Přiřazení profilů zařízení](device-profile-assign.md).


## <a name="next-steps"></a>Další postup  

Pokud chcete profil přiřadit ke skupinám, podívejte se na téma [Přiřazení profilů zařízení](device-profile-assign.md).
