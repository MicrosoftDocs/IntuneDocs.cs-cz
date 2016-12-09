---
title: "Portál Azure Portal pro zásady MAM | Microsoft Intune"
description: "Vytvořte zásady správy mobilních aplikací na portálu Azure Portal. Zásady, které zde vytvoříte, lze použít na zařízení s registrací v Intune nebo bez ní."
keywords: 
author: NathBarn
ms.author: nathbarn
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
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: b377d527621693f4c231f6f8b16cab277853cdf7


---

# <a name="azure-portal-for-microsoft-intune-mam-policies"></a>Portál Azure Portal pro zásady MAM v Microsoft Intune

## <a name="use-the-azure-portal"></a>Použití portálu Azure Portal
Portál Azure Portal umožňuje vytvářet a spravovat zásady správy mobilních aplikací (MAM).

Portál Azure Portal podporuje vytváření zásad MAM pro:
- Aplikace spuštěné v zařízeních, která **jsou zaregistrovaná a spravovaná v Intune**

- Aplikace spuštěné v zařízeních, která **nejsou zaregistrovaná** v žádném řešení MDM
- Aplikace spuštěné v zařízeních, která **jsou zaregistrovaná v řešení MDM třetí strany**.

>[!IMPORTANT]


> Pokud zařízení spravujete v konzole pro správu Intune, můžete k vytvoření zásady MAM, která podporuje aplikace pro zařízení zaregistrovaná v Intune, použít [konzolu pro správu Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> V konzole pro správu Intune se nemusí zobrazovat všechna nastavení zásad MAM. Na portálu Azure Portal najdete novou konzolu pro správu, kterou je možné používat pro vytváření zásad MAM. Pokud k vytváření zásad MAM používáte konzolu pro správu Intune i portál Azure Portal, použije se u aplikací zásada z portálu Azure Portal, která bude také nasazena u uživatelů.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Přihlášení na portál Azure Portal a přizpůsobení úvodní stránky

1.  Přejděte na [portál Azure Portal](https://portal.azure.com) a přihlaste se. Použijte přihlašovací údaje služby [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Snímek obrazovky s přihlašovací stránkou portálu Azure Portal](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Po úspěšném přihlášení se zobrazí **Řídicí panel**. Stránku **Řídicí panel** jde přizpůsobit.

    ![Snímek obrazovky Řídicí panel portálu Azure Portal](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  V nabídce **Procházet** vyberte **Intune**.![Snímek obrazovky nabídky Procházet se zvýrazněnou možností Intune](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Zvolte **Intune** > **Správa mobilních aplikací Intune** > **Nastavení**.

    ![Snímek obrazovky okna Správa mobilních aplikací Intune](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]

    > Chcete-li připnout okno na **Uvítací** stránku, použijte volbu **připnout** v okně. Kliknutím na ikonu připnutí **v okně správy mobilních aplikací Intune** toto okno připnete na **Uvítací** stránku.

    ![Snímek obrazovky okna Správa mobilních aplikací Intune se zvýrazněnou ikonou připnutí](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Snímek obrazovky Řídicí panel s připnutou dlaždicí Intune](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## <a name="next-steps"></a>Další kroky
[Příprava před konfigurací zásad správy mobilních aplikací](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


