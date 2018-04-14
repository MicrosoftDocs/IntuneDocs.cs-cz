---
title: Upgrade softwaru Windows Holographic na Windows Holographic for Business
titleSuffix: Microsoft Intune
description: "Přečtěte si, jak upgradovat v zařízení software Windows Holographic na Windows Holographic for Business."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e7c750b372c297637abcdb9e941dae17714d081b
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Upgrade zařízení se softwarem Windows Holographic na Windows Holographic for Business


Pokud chcete spravovat zařízení s Windows Holographic v Microsoft Intune, musíte zařízení upgradovat z Windows Holographic na Windows Holographic for Business. K provedení upgradu můžete vytvořit profil Upgrade edice. V případě zařízení Microsoft HoloLens můžete požadovanou licenci pro upgrade získat zakoupením edice Commercial Suite. Další informace najdete v tématu [Odblokování funkcí Windows Holographic for Business](https://docs.microsoft.com/en-us/hololens/hololens-upgrade-enterprise).

## <a name="to-set-up-an-edition-upgrade-device-configuration-profile"></a>Nastavení profilu konfigurace zařízení s upgradem edice

1. Přihlaste se k portálu [Azure Portal](https://portal.azure.com) s účtem správce.


2.  Klikněte na **Konfigurace zařízení**, **Profily** a potom na **Vytvořit profil**.

    ![Vytvoření profilu](media/Holographic-create-profile.png)

3.  V podokně **Vytvořit profil** zadejte název pro profil a jako platformu vyberte **Windows 10 a novější** a jako typ profilu vyberte **Upgrade edice**. Klikněte na **Konfigurovat nastavení**.

5. V podokně **Upgrade edice** vyberte v části **Edice, na kterou se má upgradovat** možnost **Windows 10 Holographic pro firmy**. V části **Soubor s licencí** vyhledejte a vyberte soubor XML s licencí, kterou jste obdrželi.

    ![Zadejte název souboru XML.](media/Holographic-edition-upgrade.png)
 
5.  Klikněte na **OK**, **Vytvořit** a vytvořte profil.


## <a name="deploy-the-edition-upgrade-policy"></a>Nasazení zásad upgradu edice

V dalším kroku přiřadíte profil Upgrade edice k vybraným skupinám nebo zařízením.

1. V profilu, který jste vytvořili v předchozím postupu, klikněte na tlačítko **Přiřazení**.

2. V podokně **Přiřazení** vyberte skupiny uživatelů a zařízení, které chcete zahrnout a vyloučit pomocí zásad.

![Zahrnutí a vyloučení skupin](media/Holographic-groups.PNG)

Po registraci těchto uživatelů nebo zařízení do Intune se použije profil Upgrade edice. 

## <a name="next-steps"></a>Další kroky

Další informace o skupinách najdete v tématu [Začínáme se skupinami](get-started-groups.md).

