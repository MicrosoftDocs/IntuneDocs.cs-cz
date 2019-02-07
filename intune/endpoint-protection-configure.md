---
title: Konfigurace nastavení ochrany koncových bodů v Microsoft Intune – Azure | Microsoft Docs
description: Nastavení ochrany koncových bodů určete při vytváření profilu zařízení s macOS nebo Windows 10 v Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 1d0111353d874a8236fd87d40bd890deac171bd3
ms.sourcegitcommit: 5b4a6c17bdba2f87e6ae81a3ac0cb88438a0fa27
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55807728"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Přidání nastavení ochrany koncových bodů v Intune

Ochrana koncových bodů dovoluje v zařízeních kontrolovat různé funkce zabezpečení, mimo jiné firewall, BitLocker, povolování a blokování aplikací, Windows Defender nebo šifrování. Tato nastavení můžete v Microsoft Intune konfigurovat pomocí profilů zařízení.

Můžete například vytvořit profil ochrany koncových bodů, který umožní uživatelům macOS instalovat aplikace jenom z Mac App Storu. Nebo můžete při spouštění aplikací na zařízeních s Windows 10 aktivovat filtr Windows SmartScreen.

V tomto článku se dozvíte, jak profil vytvořit. V částech o jednotlivých platformách zařízení pak najdete další podrobnosti o dostupných nastaveních.

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení ochrany koncových bodů

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
4. Zadejte **Název** a **Popis** profilu ochrany koncových bodů.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete vlastní nastavení použít. V současné době můžete pro nastavení omezení zařízení zvolit jednu z těchto platforem:
   - **macOS**
   - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **Ochrana koncového bodu**. 
7. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Podrobnosti o nastaveních na jednotlivých platformách najdete v následujících tématech:
   - [Nastavení macOS](endpoint-protection-macos.md)
   - [Nastavení Windows 10](endpoint-protection-windows-10.md)
8. Až to budete mít, vraťte se na stránku **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se na stránce se seznamem profilů. Pokud chcete přiřadit tento profil ke skupinám, podívejte se na téma [Přiřazení profilů zařízení](device-profile-assign.md).

## <a name="next-steps"></a>Další postup
Pokud chcete profil přiřadit ke skupinám, podívejte se na téma [Přiřazení profilů zařízení](device-profile-assign.md).
