---
title: Zobrazení profilů zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Zobrazte a spravujte podrobnosti konfiguračního profilu zařízení v Microsoft Intune, prohlédněte si graf počtu zařízení přiřazených k profilu a zjistěte, která zařízení mají přiřazené nebo nasazené profily. Můžete také vyřešit problémy s profily, které mají konfliktní nastavení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9deaed87-fb4b-4689-ba88-067bc61686d7
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 786cd6e7d0acaeb6e78035d8ec580c30d29d09e7
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57391714"
---
# <a name="monitor-device-profiles-in-microsoft-intune"></a>Sledování profilů zařízení v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune obsahuje na portálu Azure Portal některé funkce, které pomáhají sledovat a spravovat konfigurační profily zařízení. Můžete třeba kontrolovat stav profilu, zjistit, která zařízení jsou přiřazená, a aktualizovat vlastnosti profilu.

## <a name="view-existing-profiles"></a>Zobrazení existujících profilů

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Konfigurace zařízení** > **Profily**.

Vypíšou se všechny existující profily včetně podrobností jako je platforma, a zobrazí se, jestli je profil přiřazený k nějakým zařízením.

## <a name="view-details-on-a-profile"></a>Zobrazení podrobností profilu

Po vytvoření profilu zařízení Intune nabízí grafy. Tyto grafy zobrazují stav profilu, třeba že je úspěšně přiřazený k zařízením nebo jestli profil vykazuje konflikt.

1. Vyberte existující profil. Můžete třeba vybrat profil macOS.
2. Vyberte kartu **Přehled**.

    Horní graf znázorňuje počet zařízení přiřazených ke konkrétnímu profilu zařízení. Pokud třeba konfigurační profil zařízení platí pro zařízení s macOS, zobrazí se v grafu počet zařízení s macOS.

    Ukazuje také počet zařízení pro jiné platformy, která jsou přiřazená ke stejnému profilu zařízení. Může třeba ukazovat počet zařízení bez macOS.

    ![Zobrazení počtu zařízení přiřazených k profilu zařízení](./media/device-configuration-profile-graphical-chart.png)

    Dolní graf znázorňuje počet uživatelů přiřazených ke konkrétnímu profilu zařízení. Pokud třeba konfigurační profil zařízení platí pro uživatele s macOS, zobrazí se v grafu počet uživatelů s macOS.

3. Vyberte kruh v horním grafu. Otevře se **Stav zařízení**.

    Jsou uvedená zařízení přiřazená k profilu a zobrazuje se, jestli je profil úspěšně nasazený. Všimněte si také, že jsou uvedená jenom zařízení s konkrétní platformou (třeba macOS).

    Zavřete podrobné informace **Stav zařízení**.

4. Vyberte kruh v dolním grafu. Otevře se **Stav uživatele**. 

    Jsou uvedení uživatelé přiřazení k profilu a zobrazuje se, jestli je profil úspěšně nasazený. Všimněte si také, že jsou uvedení jenom uživatelé s konkrétní platformou (třeba macOS).

    Zavřete podrobné informace **Stav uživatele**.

5. V seznamu **Profily** vyberte konkrétní profil. Můžete také změnit stávající vlastnosti:
  - **Vlastnosti**: Změnit název nebo aktualizovat stávající nastavení.
  - **Přiřazení**: Zahrňte nebo vylučte zařízení, které mají zásady platit. Pomocí **Vybraných skupin** vyberte konkrétní skupiny.
  - **Stav zařízení**: Jsou uvedená zařízení přiřazená k profilu a zobrazuje se, jestli je profil úspěšně nasazený. Můžete vybrat konkrétní zařízení a zjistit další podrobnosti, včetně nainstalovaných aplikací.
  - **Stav uživatele**: Obsahuje seznam uživatelských jmen s zařízení vliv tento profil, a pokud profil se úspěšně nasadil. Můžete vybrat konkrétního uživatele a zjistit další podrobnosti.
  - **Stav podle nastavení**: Filtruje výstup tím, že zobrazuje jednotlivá nastavení v rámci profilu a zobrazí, pokud je toto nastavení úspěšně použito.

## <a name="view-conflicts"></a>Zobrazení konfliktů

V **Zařízení** > **Všechna zařízení** se zobrazují všechna nastavení, která způsobují konflikt. Při existujícím konfliktu se zobrazují také všechny konfigurační profily, které toto nastavení obsahují. Správci můžou tuto funkci použít k vyřešení všech nesrovnalostí v profilech.

1. V Intune vyberte **Zařízení** > **Všechna zařízení** > vyberte existující zařízení v seznamu. Koncový uživatel může název zařízení získat z aplikace Portál společnosti.
2. Vyberte **Konfigurace zařízení**. Zobrazí se všechny zásady konfigurace uplatněné na dané zařízení.
3. Vyberte zásadu. Zobrazí se všechna nastavení této zásady, která se uplatňují na dané zařízení. Pokud je zařízení v **konfliktním** stavu, vyberte tento řádek. V novém okně uvidíte všechny profily a názvy profilů obsahujících nastavení, které tento konflikt způsobuje.

Teď, když znáte konfliktní nastavení a zásady, které toto nastavení obsahují, by mělo být snadnější konflikt vyřešit. 

## <a name="next-steps"></a>Další postup
[Přiřazení profilů uživatelů a zařízení](device-profile-assign.md)  
[Běžné problémy a řešení u profilů zařízení](device-profile-troubleshoot.md)
