---
title: "Nastavení konfigurace sdíleného zařízení v Intune pro iOS"
titlesuffix: Azure portal
description: "Přečtěte si o nastavení Intune, které můžete použít k zobrazení informací na zamykací obrazovce zařízení s iOSem."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1f9256594493aeebda9ab65e3df269ea7acaca5b
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/12/2017
---
# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Nastavení konfigurace sdíleného zařízení pro zobrazení zpráv na zamykací obrazovce zařízení s iOSem

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Nastavení konfigurace sdíleného zařízení vám umožňuje zadat volitelný text, který se zobrazí v přihlašovacím okně a na zamykací obrazovce. Například můžete zadat zprávu Při ztrátě vrátit a informace z inventárního štítku majetku. 

>[!IMPORTANT]
> Tato funkce se podporuje na zařízeních pod dohledem, která používají iOS 9.3 a novější.

## <a name="create-shared-device-settings"></a>Vytvoření nastavení sdíleného zařízení

1. V okně **Funkce zařízení** zvolte **Konfigurace sdíleného zařízení (jenom pod dohledem)**.
2. V okně **Konfigurace sdíleného zařízení (jenom pod dohledem)** nakonfigurujte následující nastavení:
    - **Informace z inventárního štítku majetku** – zadejte informace o inventárním štítku zařízení. Příklad: **Majetek společnosti Contoso Corp**. Zadané informace se použijí u všech zařízení, kterým tento profil přiřadíte.
    - **Poznámka pod čarou na zamykací obrazovce** – zadejte poznámku, která v případě ztráty nebo odcizení může pomoct zařízení vrátit do správných rukou. Například: **Pokud zařízení najdete, zavolejte na číslo „telefonní číslo“**.
3. Po dokončení zvolte **OK** a postupně se vraťte do okna **Vytvořit profil**. Potom zvolte **Vytvořit**. 


## <a name="next-steps"></a>Další kroky

Nyní můžete profil zařízení přiřadit do požadované skupiny. Podrobnosti najdete v tématu [Přiřazení profilů zařízení](device-profile-assign.md).
