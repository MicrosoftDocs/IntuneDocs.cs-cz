---
title: "Nastavení konfigurace sdíleného zařízení v Microsoft Intune pro iOS"
titlesuffix: 
description: "Přečtěte si o nastaveních Microsoft Intune, která můžete použít k zobrazení informací na zamykací obrazovce zařízení s iOSem."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/5/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9147eaff2bd366dbfd86c6422e0f7a29f685db62
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Nastavení konfigurace sdíleného zařízení pro zobrazení zpráv na zamykací obrazovce zařízení s iOSem

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Tento článek ukazuje nastavení Microsoft Intune, která můžete použít k zobrazení informací na zamykací obrazovce zařízení s iOSem.

Nastavení konfigurace sdíleného zařízení vám umožňuje zadat volitelný text, který se zobrazí v přihlašovacím okně a na zamykací obrazovce. Například můžete zadat zprávu Při ztrátě vrátit a informace z inventárního štítku majetku. 

>[!IMPORTANT]
> Tato funkce se podporuje na zařízeních pod dohledem, která používají iOS 9.3 a novější.

## <a name="create-shared-device-settings"></a>Vytvoření nastavení sdíleného zařízení

1. Z [Intune na portálu Azure Portal](https://portal.azure.com) přejděte na [**Funkce zařízení** v oblasti konfigurace zařízení](device-features-configure.md). 
1. V podokně **Funkce zařízení** zvolte **Konfigurace sdíleného zařízení (jenom pod dohledem)**.
2. V podokně **Konfigurace sdíleného zařízení (jenom pod dohledem)** nakonfigurujte tato nastavení:
    - **Informace z inventárního štítku majetku** – zadejte informace o inventárním štítku zařízení. Příklad: **Majetek společnosti Contoso Corp**. Zadané informace se použijí u všech zařízení, kterým tento profil přiřadíte.
    - **Poznámka pod čarou na zamykací obrazovce** – zadejte poznámku, která v případě ztráty nebo odcizení může pomoct zařízení vrátit do správných rukou. Například: **Pokud zařízení najdete, zavolejte na číslo „telefonní číslo“**.
3. Po dokončení zvolte **OK** a postupně se vraťte do podokna **Vytvořit profil**. Pak zvolte **Vytvořit**. 


## <a name="next-steps"></a>Další kroky

Nyní můžete profil zařízení přiřadit do požadované skupiny. Podrobnosti najdete v tématu [Přiřazení profilů zařízení](device-profile-assign.md).
