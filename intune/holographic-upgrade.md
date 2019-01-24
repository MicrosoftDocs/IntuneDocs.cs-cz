---
title: Upgrade na Windows Holographic for Business
titleSuffix: Microsoft Intune
description: Přečtěte si, jak upgradovat v zařízení software Windows Holographic na Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 80d4cf8db5789e6eeb22a777eeef74dce3009856
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831288"
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Upgrade zařízení se softwarem Windows Holographic na Windows Holographic for Business

Microsoft Intune zahrnuje mnoho nastavení, která pomáhá spravovat a chránit vaše zařízení. Tento článek uvádí a popisuje nastavení pro upgrade zařízení s Windows Holographic na Windows Holographic for Business. Tato nastavení se vytvoří v profilu konfigurace upgradem v Intune, které jsou vloženy nebo nasadit do zařízení.

Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete upgradovat zařízení s Windows Holographic. Pro Microsoft HoloLens můžete můžete zakoupením edice Commercial Suite k získání požadovanou licenci pro upgrade. Další informace najdete v tématu [Odblokování funkcí Windows Holographic for Business](https://docs.microsoft.com/hololens/hololens-upgrade-enterprise).

Další informace o této funkci najdete v tématu [edice upgradovat Windows 10 nebo režim povolit S](edition-upgrade-configure-windows-10.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Upgrade edice

- **Upgrade edice na**: Vyberte **Windows 10 Holographic pro firmy**.
- **Soubor s licencí**: Vyhledejte a vyberte soubor XML s licencí, který jste obdrželi.

  ![Zadejte název souboru XML, který obsahuje Holographic pro firmy licenčních informací](media/Holographic-edition-upgrade.png)
 
## <a name="next-steps"></a>Další postup

Vytvoření profilu, ale to nemusí být teď zrovna nic nedělá ještě. Nezapomeňte [přiřadit profil](device-profile-assign.md), a [monitorování jejího stavu](device-profile-monitor.md).

Můžete také vytvořit vydání upgradu profily pro [Windows 10 a novější](edition-upgrade-windows-settings.md) zařízení.
