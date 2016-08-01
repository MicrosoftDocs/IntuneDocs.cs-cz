---
title: "Přizpůsobení zobrazení konzoly pro role | Microsoft Intune"
description: "Toto téma vám může pomoct filtrovat zobrazení konzoly správce Intune a povolit správcům zobrazení pouze těch položek, které potřebují kvůli své roli."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 132648f4c4d13983b169fa8497deae9787fe6db5


---

# Přizpůsobení zobrazení konzoly Intune podle rolí administrátora
Můžete filtrovat zobrazení konzoly správce Microsoft Intune a povolit správcům zobrazení pouze těch položek, které potřebují kvůli své roli. Můžete třeba povolit aktualizace definic malwaru nebo obnovování hesel pro zařízení jenom operátorům konzoly pro správu. To provedete pomocí přednastavených **označení**, která přiřadíte konkrétním uživatelům. Když pak tito uživatelé přejdou do konzoly pro správu, uvidí jenom položky specifické pro své označení.

## Vytvoření vlastního zobrazení

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Správce**&gt;**Správci služeb**.

2.  Ze seznamu správců služeb zvolte uživatele, u kterého chcete změnit označení, a pak vyberte **Spravovat přístup**.

3.  V dialogu **Spravovat přístup** vyberte úroveň přístupu, kterou chcete vybranému uživateli přidělit. Na výběr máte tyto:

    -   **Úplný přístup**
    -   **Oprávnění k přístupu jen pro čtení**
    -   **Helpdesk – uzel Skupiny**

    Plný přístup a přístup jen pro čtení není potřeba vysvětlovat. <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] admin console:--->

    **Helpdesk – uzel Skupiny** omezuje to, co mohou správci zobrazovat a dělat s následujícími položkami:

    -   Zobrazení seznamu uživatelů a zařízení Správce nemůže používat filtry k úpravě zařízení. Můžete ale pomocí filtrování skupiny změnit, co správce uvidí. Další informace najdete v tématu [Použití skupin pro správu uživatelů a zařízení s Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

    -   Tisk seznamu uživatelů a zařízení

    -   Export seznamu uživatelů a zařízení

    -   Zobrazení vlastností uživatele nebo zařízení

    -   Provádějte následující vzdálené úlohy:

        -   Spustit úplnou kontrolu malwaru

        -   Spustit rychlou kontrolu malwaru

        -   Restartovat počítač

        -   Aktualizovat definice malwaru

        -   Aktualizovat zásady

        -   Aktualizovat inventáře

        -   Vzdáleně uzamknout zařízení

        -   Resetování hesla

Když nakonfigurovaný správce později otevře konzolu správce Intune , bude mu udělená úroveň přístupu, kterou jste určili.



<!--HONumber=Jul16_HO3-->


