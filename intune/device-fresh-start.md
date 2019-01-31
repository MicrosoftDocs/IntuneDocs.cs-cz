---
title: Resetování zařízení s Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Pomocí funkce Začít znovu můžete odebrat nebo odinstalovat aplikace z počítačů s Windows 10 s využitím Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
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
ms.openlocfilehash: 1eb1e671cc16196974cb15cdc785ba7d99fa8f46
ms.sourcegitcommit: 4bd992da609b8bcc85edc2d64fe8128546aa4617
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55303408"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Resetování zařízení s Windows 10 přes Intune pomocí akce Začít znovu


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Akce zařízení **Začít znovu** odebere veškeré aplikace nainstalované na počítači s Windows 10 ve verzi 1703 nebo novější. Akce Začít znovu pomáhá odebrat předinstalované aplikace (výrobců OEM), které se obvykle instalují na nový počítač.  

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com) a přejděte na > **Microsoft Intune** > **Zařízení** > **Všechna zařízení**.
2. V seznamu zařízení, která spravujete, zvolte zařízení s Windows 10 Desktop.
3. Klikněte na **Začít znovu**. 
4. Vyberte **Zachovat na tomto zařízení data uživatele**, pokud chcete:
   * Zachovat připojení zařízení k Azure AD
    * Zařízení se zaregistruje ke správě mobilních zařízení znovu při obrysů službu Azure Active Directory uživatel přihlašuje k zařízení.
    * Zachovat obsah domovské složky uživatele zařízení a odebrat aplikace a nastavení  
  > [!IMPORTANT]
 > Pokud data uživatele nezachováte, zařízení se obnoví do stavu při svém prvním zapnutí. VLASTNÍ zařízení uživatelů se zruší se tím registrace ze služby Azure AD a správa mobilních zařízení.
 > Podpora k zařízením Azure AD, které jsou připojené k zaregistruje se na správu mobilních zařízení znovu obrysů službu Azure Active Directory uživatel přihlašuje k zařízení.
 
5. Klikněte na **OK**.   
6. Pokud chcete zobrazit stav této akce, přejděte zpět na **Zařízení** a klikněte na **Akce zařízení**.  
