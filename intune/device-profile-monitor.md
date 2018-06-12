---
title: Zobrazení profilů zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Zobrazte si a spravujte podrobnosti konfiguračního profilu zařízení v Microsoft Intune a zobrazte si graf počtu zařízení přiřazených k profilu a zjistěte, která zařízení mají přiřazené nebo nasazené profily.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9deaed87-fb4b-4689-ba88-067bc61686d7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bffb6832200379fca0221d8718afdebe06163980
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744784"
---
# <a name="monitor-device-profiles-in-microsoft-intune"></a>Sledování profilů zařízení v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune obsahuje na portálu Azure Portal některé funkce, které pomáhají sledovat a spravovat konfigurační profily zařízení. Můžete třeba kontrolovat stav profilu, zjistit, která zařízení jsou přiřazená, a aktualizovat vlastnosti profilu.

## <a name="view-existing-profiles"></a>Zobrazení existujících profilů

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Konfigurace zařízení** > **Profily**.

Uvedené jsou všechny existující profily včetně podrobností jako platforma nebo jestli je profil přiřazený k nějakým zařízením.

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
  - **Vlastnosti**: Můžete změnit název nebo aktualizovat libovolné existující nastavení.
  - **Přiřazení**: Můžete zahrnout nebo vyloučit zařízení, pro která mají zásady platit. Pomocí **Vybraných skupin** vyberte konkrétní skupiny.
  - **Stav zařízení**: Jsou uvedená zařízení přiřazená k profilu a zobrazuje se, jestli je profil úspěšně nasazený. Můžete vybrat konkrétní zařízení a zjistit další podrobnosti, včetně nainstalovaných aplikací.
  - **Stav uživatele**: Uvádí uživatelská jména se zařízeními, na která má tento profil vliv, a jestli je profil úspěšně nasazený. Můžete vybrat konkrétního uživatele a zjistit další podrobnosti.
  - **Stav podle nastavení**: Filtruje výstup tím, že zobrazí jednotlivá nastavení v rámci profilu, a zobrazuje, jestli je toto nastavení úspěšně použité.

## <a name="next-steps"></a>Další kroky
[Přiřazení profilů uživatelů a zařízení](device-profile-assign.md)  
[Běžné problémy a řešení u profilů zařízení](device-profile-troubleshoot.md)