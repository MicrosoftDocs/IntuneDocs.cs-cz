---
title: Resetování zařízení s Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Pomocí funkce Začít znovu můžete odebrat nebo odinstalovat aplikace z počítačů s Windows 10 s využitím Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: cd2320e4c3935c4865d785bbb2461bba20afffdb
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52188734"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Resetování zařízení s Windows 10 přes Intune pomocí akce Začít znovu


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Akce zařízení **Začít znovu** odebere veškeré aplikace nainstalované na počítači s Windows 10 ve verzi 1703 nebo novější. Akce Začít znovu pomáhá odebrat předinstalované aplikace (výrobců OEM), které se obvykle instalují na nový počítač.  

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com) a přejděte na > **Microsoft Intune** > **Zařízení** > **Všechna zařízení**.
2. V seznamu zařízení, která spravujete, zvolte zařízení s Windows 10 Desktop.
3. Klikněte na **Začít znovu**. 
4. Vyberte **Zachovat na tomto zařízení data uživatele**, pokud chcete:
   * Zachovat připojení zařízení k Azure AD
    * Zachovat registraci zařízení ve správě mobilních zařízení 
    * Zachovat obsah domovské složky uživatele zařízení a odebrat aplikace a nastavení  
  > [!IMPORTANT]
 > Pokud data uživatele nezachováte, zařízení se obnoví do stavu při svém prvním zapnutí. Jeho registrace v Azure AD a ve správě mobilních zařízení se zruší. 
 
5. Klikněte na **OK**.   
6. Pokud chcete zobrazit stav této akce, přejděte zpět na **Zařízení** a klikněte na **Akce zařízení**.  
