---
title: Upgrade softwaru Windows Holographic na Windows Holographic for Business
titleSuffix: Azure portal
description: "Přečtěte si, jak upgradovat v zařízení software Windows Holographic na Windows Holographic for Business."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 1/30/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c467d2d4e02785bfac48afe2b39c50300eb4be40
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/03/2018
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Upgrade zařízení se softwarem Windows Holographic na Windows Holographic for Business


Pokud chcete spravovat zařízení s Windows Holographic for Business v Microsoft Intune, je nutné, abyste si vytvořili profil Upgrade edice, který se použije k upgradu zařízení z Windows Holographic na Windows Holographic for Business. V případě zařízení Microsoft HoloLens můžete požadovanou licenci pro upgrade získat zakoupením edice Commercial Suite. Další informace najdete v tématu [Odblokování funkcí Windows Holographic for Business](https://docs.microsoft.com/en-us/hololens/hololens-upgrade-enterprise).

## <a name="to-set-up-an-edition-upgrade-device-configuration-profile"></a>Nastavení profilu konfigurace zařízení s upgradem edice

1. Přihlaste se k portálu [Azure Portal](https://portal.azure.com) s účtem správce.


2.  Klikněte na **Konfigurace zařízení**, **Profily** a potom na **Vytvořit profil**.

    ![Vytvoření profilu](media/Holographic-create-profile.png)

3.  V okně **Vytvořit profil** zadejte název pro profil a vyberte **Windows 10 a novější** pro platformu a **Upgrade edice** pro typ profilu. Klikněte na **Konfigurovat nastavení**.

5. V okně **Upgrade edice** vyberte v části **Edice, na kterou se má upgradovat** možnost **Windows 10 Holographic pro firmy**. V části **Soubor s licencí** vyhledejte a vyberte soubor XML s licencí, kterou jste obdrželi.

    ![Zadejte název souboru XML.](media/Holographic-edition-upgrade.png)
 
5.  Klikněte na **OK**, **Vytvořit** a vytvořte profil.


## <a name="deploy-the-edition-upgrade-policy"></a>Nasazení zásad upgradu edice

V dalším kroku přiřadíte profil Upgrade edice k vybraným skupinám nebo zařízením.

1. V profilu, který jste vytvořili v předchozím postupu, klikněte na tlačítko **Přiřazení**.

2. V okně **Přiřazení** vyberte skupiny uživatelů a zařízení, které chcete zahrnout a vyloučit pomocí zásad.

![Zahrnutí a vyloučení skupin](media/Holographic-groups.PNG)

Po registraci těchto uživatelů nebo zařízení do Intune se použije profil Upgrade edice. 

## <a name="next-steps"></a>Další kroky

Další informace o skupinách najdete v tématu [Začínáme se skupinami](get-started-groups.md).


