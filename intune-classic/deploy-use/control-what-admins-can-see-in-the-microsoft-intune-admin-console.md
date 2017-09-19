---
title: "Přizpůsobení zobrazení konzoly pro role"
description: "Toto téma vám může pomoct filtrovat zobrazení konzoly správce Intune a povolit správcům zobrazení pouze těch položek, které potřebují kvůli své roli."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9525964117b6d7d459f5ea608a35343ab19f249f
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/15/2017
---
# <a name="customize-intune-console-views-according-to-admin-roles"></a>Přizpůsobení zobrazení konzoly Intune podle rolí administrátora

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Můžete filtrovat zobrazení konzoly pro správu Microsoft Intune a povolit správcům zobrazení pouze těch položek, které potřebují kvůli své roli. Můžete třeba povolit aktualizace definic malwaru nebo obnovování hesel pro zařízení jenom operátorům konzoly pro správu. To provedete pomocí přednastavených **označení**, která přiřadíte konkrétním uživatelům. Když pak tito uživatelé přejdou do konzoly pro správu, uvidí jenom položky specifické pro své označení.

## <a name="to-create-a-custom-view"></a>Vytvoření vlastního zobrazení

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Správce**&gt;**Správci služeb**.

2.  Ze seznamu správců služeb zvolte uživatele, u kterého chcete změnit označení, a pak vyberte **Spravovat přístup**.

3.  V dialogu **Spravovat přístup** vyberte úroveň přístupu, kterou chcete vybranému uživateli přidělit. Na výběr máte tyto:

    -   **Úplný přístup**
    -   **Přístup jen pro čtení**
    -   **Helpdesk – uzel Skupiny**

    Plný přístup a přístup jen pro čtení není potřeba vysvětlovat. <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the Intune admin console:--->

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

        -   Vzdálené zamknutí zařízení

        -   Resetování hesla

Když nakonfigurovaný správce později otevře konzolu pro správu Intune, bude mu udělená úroveň přístupu, kterou jste určili.
