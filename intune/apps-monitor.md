---
title: "Postup monitorování informací a přiřazení aplikace"
titlesuffix: Azure portal
description: "Po přiřazení aplikace uživatelům nebo zařízením můžete použít tyto informace, které vám usnadní monitorování jejího stavu."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0298fc255b3c11a12b5bf225968d6f2303192053
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Postup monitorování informací a přiřazení aplikace pomocí Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune poskytuje několik způsobů, jak můžete monitorovat vlastnosti vámi spravovaných aplikací a stav jejich přiřazení.

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** + **Intune**.
3. V úloze **Mobilní aplikace** zvolte ve skupině **Spravovat** možnost **Aplikace**.
5. V okně seznamu aplikací zvolte aplikaci. Pak se vám zobrazí okno <*název aplikace*> **Stav instalace zařízení**.

## <a name="app-overview-blade"></a>Přehled okna aplikací

V okně **Stav instalace zařízení** <*název aplikace*>  si můžete zkontrolovat podrobnosti o stavu aplikace ve vašem prostředí.

### <a name="essentials"></a>Essentials

Část **Základy** obsahuje následující informace o aplikaci:

 - **Vydavatel**  
Vydavatel aplikace
 - **Operační systém**  
Operační systém aplikace (Windows, iOS, Android atd.)
 - **Vytvořit**  
Čas vytvoření této revize
 - **Přiřazeno**  
Označuje, zda byla aplikace přiřazena – **Ano** nebo **Ne**.

### <a name="status"></a>Stav
Jednotlivé grafy zobrazují počty pro následující stav:

 - **Instalováno**  
Počet nainstalovaných aplikací
 - **Nenainstalováno**  
Počet nenainstalovaných aplikací
 - **Instalace čeká**  
Počet aplikací, které se právě instalují
 - **Neúspěch**  
Počet neúspěšných instalací
 - **Neznámé**  
Počet aplikací s neznámým stavem

### <a name="device-status"></a>Stav zařízení

Stav zařízení. Prstencový graf, který zobrazuje stav instalace aplikace na zařízeních. Kliknutím na graf otevřete seznam podrobností o stavu zařízení. Tabulka s podrobnostmi obsahuje následující sloupce:

 - **Název zařízení**  
Název zařízení na platformách, které umožňují pojmenování zařízení. Na ostatních platformách Intune vytvoří název z dalších vlastností. Tento atribut nemůže být dostupný pro všechna zařízení.
 - **Uživatelské jméno**  
Jméno uživatele
 - **Platforma**  
Operační systém zařízení (Windows, iOS, Android atd.)
 - **Verze**  
Číslo verze aplikace. U obchodních aplikací se zobrazuje celé číslo verze aplikace. Celé číslo verze identifikuje konkrétní vydanou verzi aplikace. Číslo se zobrazí jako _Verze_(_build_). Příklad: 2.2(2.2.17560800)
 - **Stav**  
Stav aplikace
 - **Podrobnosti stavu**  
Podrobnosti o stavu
 - **Poslední vrácení se změnami**  
Datum, kdy se zařízení naposledy synchronizovalo s Intune


### <a name="user-status"></a>Stav uživatele

Stav uživatele. Prstencový graf, který zobrazuje stav instalace aplikace u uživatelů. Kliknutím na graf otevřete seznam podrobností o stavu zařízení. Tabulka s podrobnostmi obsahuje následující sloupce:
 - **Název**  
Jméno uživatele ve službě Azure AD
 - **Uživatelské jméno**  
Jedinečné jméno uživatele
 - **Instalace**  
Počet instalací aplikace použitých uživatelem
 - **Chyby**  
Počet neúspěšných instalací uživatelem
 - **Nenainstalováno**  
Počet aplikací, které nenainstaloval uživatel


## <a name="next-steps"></a>Další kroky

Další informace o práci s daty Intune najdete v tématu [Použití datového skladu Intune](reports-nav-create-intune-reports.md).