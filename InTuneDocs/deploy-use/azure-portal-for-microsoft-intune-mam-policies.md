---
title: "Portál Azure Portal pro zásady MAM | Dokumentace Microsoftu"
description: "Vytvořte zásady správy mobilních aplikací na portálu Azure Portal. Zásady, které zde vytvoříte, lze použít na zařízení s registrací v Intune nebo bez ní."
keywords: 
author: andredm7
ms.author: andredm
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
ms.sourcegitcommit: fe44466fbcef67d02b16d3d2d335f657251451d3
ms.openlocfilehash: fa8d839da1cf0b2d207edc0b28de8a714ba0df02


---

# <a name="azure-portal-for-microsoft-intune-mam-policies"></a>Portál Azure Portal pro zásady MAM v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Azure Portal slouží k vytváření a správě zásad správy mobilních aplikací (MAM) pro tyto aplikace:

- Aplikace spuštěné v zařízeních, která **jsou zaregistrovaná a spravovaná v Intune**

- Aplikace spuštěné v zařízeních, která **nejsou zaregistrovaná** v žádném řešení MDM
- Aplikace spuštěné v zařízeních, která **jsou zaregistrovaná v řešení MDM třetí strany**.

>[!IMPORTANT]
> Azure Portal je nová konzola pro správu pro vytváření zásad MAM, ale umožňuje také vytvářet zásady MAM, které podporují aplikace pro zařízení zaregistrované v Intune pomocí [konzoly pro správu Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) pro scénáře MDM.

> V konzole pro správu Intune se nemusí zobrazovat všechna dostupná nastavení zásad MAM. Kromě toho pokud vytvoříte zásady MAM jak v konzole pro správu Intune, tak i na portálu Azure Portal, přepíšou zásady vytvořené na portálu Azure Portal zásady vytvořené v konzole pro správu Intune. V tomto scénáři se zásady MAM vytvořené na portálu Azure Portal použijí u aplikací a nasadí u uživatelů.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Přihlášení na portál Azure Portal a přizpůsobení úvodní stránky

1.  Přejděte na [portál Azure Portal](https://portal.azure.com) a přihlaste se. Použijte přihlašovací údaje služby [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Snímek obrazovky s přihlašovací stránkou portálu Azure Portal](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Po úspěšném přihlášení se zobrazí **Řídicí panel**. Stránku **Řídicí panel** jde přizpůsobit.

    ![Snímek obrazovky Řídicí panel portálu Azure Portal](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  V nabídce **Procházet** vyberte **Intune**.

    ![Snímek obrazovky nabídky Procházet se zvýrazněnou možností Intune](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  Zvolte **Intune** > **Správa mobilních aplikací Intune** > **Nastavení**.

    ![Snímek obrazovky okna Správa mobilních aplikací Intune](../media/AppManagement/MAM-Azure-Portal-2.png)

5. (Nepovinné): Pokud chcete připnout okno na **Uvítací** stránku, použijte v okně volbu **připnout**. Kliknutím na ikonu připnutí **v okně správy mobilních aplikací Intune** toto okno připnete na **Uvítací** stránku.

    ![Snímek obrazovky okna Správa mobilních aplikací Intune se zvýrazněnou ikonou připnutí](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Snímek obrazovky Řídicí panel s připnutou dlaždicí Intune](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <a name="next-steps"></a>Další kroky
[Příprava před konfigurací zásad správy mobilních aplikací](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jan17_HO2-->


