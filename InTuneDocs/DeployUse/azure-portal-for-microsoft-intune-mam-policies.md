---
title: "Portál Azure pro zásady MAM | Microsoft Intune"
description: "Vytvořte zásady správy mobilních aplikací pomocí portálu Azure. Zásady, které zde vytvoříte, lze použít na zařízení s registrací v Intune nebo bez ní."
keywords: 
author: karthikaraman
manager: arob98
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2038ed6219a94dc4285891d71ce00fd51310f3e3
ms.openlocfilehash: 22aea1a9a2ff55ae7a8a115fae31b1358305a4a5


---

# Portál Azure pro zásady MAM v Microsoft Intune
## Přístup k portálu Azure
**Portál Azure** umožňuje vytvářet a spravovat zásady správy mobilních aplikací.

Portál Azure podporuje vytváření zásad MAM pro:
- Aplikace běžící v zařízeních **zaregistrovaných a spravovaných v Intune**
- Aplikace běžící v zařízeních, která **nejsou zaregistrovaná** v žádném řešení MDM
- Aplikace běžící v zařízeních, která jsou **zaregistrovaná v řešení MDM třetí strany**

>[!IMPORTANT]

> Pokud teď ke správě svých zařízení používáte [konzolu pro správu Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md), můžete zásadu MAM podporující aplikace pro zařízení zaregistrovaná v Intune vytvořit pomocí konzoly pro správu Intune.

> V Konzole správce Intune nemusíte vidět všechna nastavení zásad MAM. Portál Azure je nové konzola pro správu, která umožňuje vytváření zásad MAM. Pokud vytváříte zásady MAM v konzole pro správu Intune i na portálu Azure, pro aplikace se použije a pro uživatele se nasadí zásada na portálu Azure.

## Přihlášení na portál Azure a přizpůsobení úvodní stránky

1.  Přejděte na [portál Azure](https://portal.azure.com) a přihlaste se pomocí svých přihlašovacích údajů služby [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Snímek obrazovky přihlašovací stránky portálu Azure](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Po úspěšném přihlášení se zobrazí **Řídicí panel**. Stránku **Řídicí panel** jde přizpůsobit.

    ![Snímek obrazovky Řídicí panel portálu Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  V nabídce **Procházet** vyberte **Intune**.![Snímek obrazovky nabídky Procházet se zvýrazněnou službou Intune](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Zvolte **Intune > Správa mobilních aplikací Intune > Nastavení**.

    ![Snímek obrazovky okna Správa mobilních aplikací Intune](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > Chcete-li připnout okno na **Uvítací** stránku, použijte volbu **připnout** v okně.  Kliknutím na ikonu připnutí **v okně správy mobilních aplikací Intune**toto okno připnete na **Uvítací** stránku.

    ![Snímek obrazovky okna Správa mobilních aplikací Intune se zvýrazněnou ikonou připnutí](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Snímek obrazovky Řídicí panel s připnutou dlaždicí Intune](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## Další kroky
[Příprava před konfigurací zásad správy mobilních aplikací](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


