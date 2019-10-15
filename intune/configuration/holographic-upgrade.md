---
title: Upgrade na Windows Holografick pro firmy
titleSuffix: Microsoft Intune
description: Naučte se, jak upgradováním zařízení s Windows Holografickím do okna Holografick pro firmy.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6d569d34da1568d0e412d689d98d4a22b00e6545
ms.sourcegitcommit: 45d7c76e760c5117bf134fb57f7e248e5b6c4ad5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/15/2019
ms.locfileid: "72314519"
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Upgrade zařízení s Windows holografickým na Windows Holografick pro firmy

Microsoft Intune obsahuje mnoho nastavení, které vám pomůžou se správou a ochranou vašich zařízení. Tento článek obsahuje seznam a popis nastavení pro upgrade zařízení se systémem Windows holografick pro firmy. Tato nastavení se vytvoří v profilu konfigurace upgradu v Intune, který se předává nebo nasazuje do zařízení.

Jako součást řešení správy mobilních zařízení (MDM) použijte Tato nastavení k upgradu holografických zařízení s Windows. V případě Microsoft HoloLens si můžete koupit komerční sadu a získat tak požadovanou licenci pro upgrade. Další informace najdete v tématu [odemčení funkcí Windows holografick pro firmy](https://docs.microsoft.com/hololens/hololens1-upgrade-enterprise).

Další informace o této funkci najdete v tématu [upgrade edice Windows 10 nebo povolení režimu S](../edition-upgrade-configure-windows-10.md).

## <a name="before-you-begin"></a>Než začnete

[Vytvořte profil konfigurace zařízení](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Upgrade edice

- **Edice, na kterou se má upgradovat**: vyberte **Windows 10 holografick pro firmy**.
- **Soubor s licencí**: vyhledejte a vyberte soubor s licencí XML, který vám byl poskytnut.

  ![Zadejte název souboru XML, který obsahuje informace o licenci pro holografické firmy.](./media/holographic-upgrade/Holographic-edition-upgrade.png)
 
## <a name="next-steps"></a>Další kroky

Profil se vytvoří, ale nemusí ještě nic dělat. Nezapomeňte [profil přiřadit](device-profile-assign.md)a [monitorovat jeho stav](../device-profile-monitor.md).

Můžete také vytvořit profily upgradu edice pro zařízení [s Windows 10 a novějším](edition-upgrade-windows-settings.md) .
