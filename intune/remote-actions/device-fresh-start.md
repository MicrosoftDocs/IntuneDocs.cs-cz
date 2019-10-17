---
title: Resetování zařízení s Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Pomocí funkce Začít znovu můžete odebrat nebo odinstalovat aplikace z počítačů s Windows 10 s využitím Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/09/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ff1dc2565ef52f81619abe8f14e78c58da0fce7d
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72508619"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Resetování zařízení s Windows 10 přes Intune pomocí akce Začít znovu


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Akce zařízení **Začít znovu** odebere veškeré aplikace nainstalované na počítači s Windows 10 ve verzi 1703 nebo novější. Akce Začít znovu pomáhá odebrat předinstalované aplikace (výrobců OEM), které se obvykle instalují na nový počítač. 

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com) a přejděte na > **Microsoft Intune** > **Zařízení** > **Všechna zařízení**.
2. V seznamu zařízení, která spravujete, zvolte zařízení s Windows 10 Desktop.
3. Klikněte na **Začít znovu**. 
4. Vyberte **Zachovat na tomto zařízení data uživatele**, pokud chcete:
   * Zachovat připojení zařízení k Azure AD
   * Zařízení se znovu zaregistruje do správy mobilních zařízení, když se uživatel s povoleným Azure Active Directory přihlásí do zařízení.
   * Zachovat obsah domovské složky uživatele zařízení a odebrat aplikace a nastavení

  > [!IMPORTANT]
 > Pokud nezachováte uživatelská data, zařízení bude obnoveno na výchozí nastavení OOBE (předem připraveno), které zachová vestavěný účet správce.
 > Zařízení BYOD budou odregistrována v Azure AD a správě mobilních zařízení.
 > Zařízení připojená k Azure AD se znovu zaregistrují do správy mobilních zařízení, když se uživatel s povoleným Azure Active Directory přihlásí do zařízení.
 
5. Klikněte na **OK**.   
6. Pokud chcete zobrazit stav této akce, přejděte zpět na **Zařízení** a klikněte na **Akce zařízení**.  
7. Zařízení se obnoví na úvodní obrazovku pro přihlášení.
