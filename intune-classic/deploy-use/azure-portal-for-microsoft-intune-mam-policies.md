---
title: "Portál Azure pro zásady MAM"
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
ms.custom: intune-classic
ms.openlocfilehash: 00328885d7fb5e75ffe894326591c0225f4b07ab
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="azure-portal-for-intune-app-protection-policies"></a>Azure Portal pro zásady ochrany aplikací Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Azure Portal slouží k vytváření a správě zásad ochrany aplikací pro:

- Aplikace spuštěné v zařízeních, která **jsou zaregistrovaná a spravovaná v Intune**

- Aplikace spuštěné v zařízeních, která **nejsou zaregistrovaná** v žádném řešení MDM
- Aplikace spuštěné v zařízeních, která **jsou zaregistrovaná v řešení MDM třetí strany**.

>[!IMPORTANT]
> Azure Portal je nová konzola pro správu, která slouží k vytváření zásad ochrany aplikací, ale umožňuje také vytvářet zásady ochrany aplikací, které podporují aplikace pro zařízení zaregistrované v Intune pomocí [konzoly pro správu Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) pro scénáře MDM.

> V konzole pro správu Intune se nemusí zobrazovat všechna dostupná nastavení zásad ochrany aplikací. Kromě toho platí, že pokud vytvoříte zásady ochrany aplikací v konzole pro správu Intune i na portálu Azure Portal, přepíšou zásady vytvořené na portálu Azure Portal zásady vytvořené v konzole pro správu Intune. V tomto scénáři se zásady ochrany aplikací vytvořené na portálu Azure Portal použijí u aplikací a nasadí u uživatelů.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Přihlášení na portál Azure Portal a přizpůsobení úvodní stránky

1.  Přejděte na portál [Azure Portal](https://portal.azure.com) a přihlaste se pomocí svých přihlašovacích údajů k Intune.

    ![Snímek obrazovky s přihlašovací stránkou portálu Azure Portal](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Po úspěšném přihlášení se zobrazí **Řídicí panel**. Stránku **Řídicí panel** jde přizpůsobit.

    ![Snímek obrazovky Řídicí panel portálu Azure Portal](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  V nabídce vlevo zvolte **Další služby** a do filtru textového pole pak zadejte **Intune**.

    ![Snímek obrazovky nabídky Procházet se zvýrazněnou možností Intune](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  Zvolte **Intune App Protection** > **Správa mobilních aplikací Intune** > **Veškerá nastavení**.

    ![Snímek obrazovky okna Správa mobilních aplikací Intune](../media/AppManagement/MAM-Azure-Portal-2.png)

5. (Nepovinné): Pokud chcete připnout okno na **Uvítací** stránku, použijte v okně volbu **připnout**. Kliknutím na ikonu připnutí **v okně správy mobilních aplikací Intune** toto okno připnete na **Uvítací** stránku.

    ![Snímek obrazovky okna Správa mobilních aplikací Intune se zvýrazněnou ikonou připnutí](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Snímek obrazovky Řídicí panel s připnutou dlaždicí Intune](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <a name="next-steps"></a>Další kroky
[Příprava ke konfiguraci zásad ochrany aplikací](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
