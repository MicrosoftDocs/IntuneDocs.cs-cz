---
# required metadata

title: Portál Azure pro zásady MAM | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Portál Azure pro zásady MAM v Microsoft Intune
## Přístup k portálu Azure
**Portál Azure** umožňuje vytvářet a spravovat zásady správy mobilní aplikace.

Portál Azure podporuje vytváření zásad MAM pro:
- Aplikace běžící v zařízeních **zaregistrovaných a spravovaných v Intune**.
- Aplikace běžící v zařízeních, která **nejsou zaregistrovaná** v žádném řešení MDM
- Aplikace běžící v zařízeních, která jsou **zaregistrovaná v řešení MDM třetí strany**.

Pokud aktuálně ke správě svých zařízení používáte **Konzolu správce Intune**, můžete zásadu MAM podporující aplikace pro zařízení zaregistrovaná v Intune vytvořit pomocí [Konzoly správce Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)..
>[!IMPORTANT]
> V Konzole správce Intune nemusíte vidět všechna nastavení zásad MAM. Portál Azure je nová konzola správce pro vytváření zásad MAM.

## Přihlášení na portál Azure a přizpůsobení úvodní stránku

1.  Přejděte na [portál Azure](https://portal.azure.com) a přihlaste se pomocí svých přihlašovacích údajů pro [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Snímek obrazovky přihlašovací stránky portálu Azure](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Po přihlášení se vám zobrazí **Řídící panel**. Stránka **Řídící panel** obsahuje sadu výchozích dlaždic. Přidáním nových dlaždic nebo jejich odebráním si stránku můžete přizpůsobit.

    ![Snímek obrazovky řídícího panelu portálu Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  Z nabídky **Procházet** vyberte **Intune**.![Snímek obrazovky nabídky Procházet se zvýrazněným Intune](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Klikněte na **Intune > Správa mobilních aplikací Intune > Nastavení**..

    ![Snímek obrazovky okna Správa mobilních aplikací Intune](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > Chcete-li připnout okno na **Uvítací** stránku, použijte volbu **připnout** v okně.  Kliknutím na ikonu připnutí **v okně správy mobilních aplikací Intune**toto okno připnete na **Uvítací** stránku.

    ![Snímek obrazovky okna Správa mobilních aplikací Intune se zvýrazněnou ikonou připnutí](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Snímek obrazovky řídicího panelu s připnutou dlaždicí Intune](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## Další kroky
[Příprava před konfigurací zásad správy mobilních aplikací](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


