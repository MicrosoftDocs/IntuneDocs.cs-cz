---
title: "Portál Azure pro zásady MAM | Microsoft Intune"
description: "Vytvořte zásady správy mobilních aplikací na portálu Azure. Zásady, které zde vytvoříte, lze použít na zařízení s registrací v Intune nebo bez ní."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9eb7e79bee2bc36dffab97ffdb6f665218bc739e
ms.openlocfilehash: 0acef421f179ebf922ec8af71ba336e3e5f96bd2


---

# Portál Azure pro zásady MAM v Microsoft Intune
## Použití portálu Azure
Portál Azure umožňuje vytvářet a spravovat zásady správy mobilních aplikací (MAM).

Portál Azure podporuje vytváření zásad MAM pro:
- Aplikace spuštěné v zařízeních, která **jsou zaregistrovaná a spravovaná v Intune**.
- Aplikace spuštěné v zařízeních, která **nejsou zaregistrovaná** v žádném řešení MDM
- Aplikace spuštěné v zařízeních, která **jsou zaregistrovaná v řešení MDM třetí strany**.

>[!IMPORTANT]

> Pokud zařízení spravujete v konzole pro správu Intune, můžete k vytvoření zásady MAM, která podporuje aplikace pro zařízení zaregistrovaná v Intune, použít [konzolu pro správu Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> V konzole pro správu Intune se nemusí zobrazovat všechna nastavení zásad MAM. Na Portálu Azure najdete novou konzolu pro správu, kterou je možné používat pro vytváření zásad MAM. Pokud k vytváření zásad MAM používáte konzolu pro správu Intune i portál Azure, použije se u aplikací zásada z portálu Azure, která bude také nasazena u uživatelů.

## Přihlášení na portál Azure a přizpůsobení úvodní stránky

1.  Přejděte na [portál Azure](https://portal.azure.com) a přihlaste se. Použijte přihlašovací údaje služby [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Snímek obrazovky s přihlašovací stránkou portálu Azure Portal](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Po přihlášení se zobrazí stránka **Řídicí panel**. Stránku **Řídicí panel** jde přizpůsobit.

    ![Snímek obrazovky Řídicí panel portálu Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  V nabídce **Procházet** vyberte **Intune**.![Snímek obrazovky nabídky Procházet se zvýrazněnou službou Intune](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Zvolte **Intune** > **Správa mobilních aplikací Intune** > **Nastavení**.

    ![Snímek obrazovky okna Správa mobilních aplikací Intune](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > Pokud chcete okno připnout na **úvodní stránku**, použijte v okně **Správa mobilních aplikací Intune** ikonu špendlíku.

    ![Snímek obrazovky okna Správa mobilních aplikací Intune se zvýrazněnou ikonou připnutí](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Snímek obrazovky Řídicí panel s připnutou dlaždicí Intune](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## Další kroky
[Příprava před konfigurací zásad správy mobilních aplikací](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


