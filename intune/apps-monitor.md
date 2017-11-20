---
title: "Postup monitorování informací a přiřazení aplikace"
titlesuffix: Azure portal
description: "Po přiřazení aplikace uživatelům nebo zařízením můžete použít tyto informace, které vám usnadní monitorování jejího stavu."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3736b6d43f5cd3b6c75097a2ceabebffd75f0caa
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Postup monitorování informací a přiřazení aplikace pomocí Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune poskytuje několik způsobů, jak můžete monitorovat vlastnosti vámi spravovaných aplikací a stav jejich přiřazení.

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** + **Intune**.
3. V úloze **Mobilní aplikace** zvolte ve skupině **Spravovat** možnost **Aplikace**.
     
    ![Okno stavu instalace aplikace](./media/monitor-apps.png)
5. V okně seznamu aplikací zvolte aplikaci. Pak se vám zobrazí okno <*název aplikace*> **Stav instalace zařízení**.

Sestava stavu instalace zařízení obsahuje tyto sloupce:

1.  **Název zařízení** – název typu zařízení
2.  **Uživatelské jméno** – jméno uživatele
3.   **Platforma** – operační systém nainstalovaný v zařízení
4.  **Verze** – číslo verze aplikace
5.   **Stav** – možné stavy aplikací: **Nainstalováno**, **Nenainstalováno**, **Instalace čeká** a **Chyba**
6. **Podrobnosti stavu** – čitelný popis stavu aplikace v zařízení
7. **Poslední vrácení se změnami** – čas, kdy se naposledy zařízení vrátilo do Intune se změnami

Pak zjistěte další informace o aplikacích a jejich přiřazení pomocí jedné z následujících akcí.

## <a name="general"></a>Obecné

- **Přehled** – poskytuje základní přehled aplikace a informace o stavu všech přiřazení této aplikace. Pomocí některého z přehledů můžete otevřít okna **Stav instalace zařízení** nebo **Stav instalace uživatele** a získat podrobnější informace.

## <a name="manage"></a>Správa

- **Vlastnosti** – umožňují zobrazit a změnit informace o vybrané aplikaci. Další informace o vlastnostech aplikací najdete v tématu [Přidání aplikace do Microsoft Intune](apps-add.md).
- **Přiřazení** – poskytují informace o přiřazeních této aplikace. Další informace najdete v článku [Jak přiřadit aplikace do skupin pomocí Microsoft Intune](apps-deploy.md).

## <a name="monitor"></a>Monitorování

- **Stav instalace zařízení** – poskytuje podrobné informace o každém zařízení, kterému jste přiřadili vybranou aplikaci, včetně názvu zařízení, operačního systému, data posledního přihlášení zařízení do Intune a stavu instalace aplikace.
- **Stav instalace uživatele** – poskytuje podrobné informace o uživateli, kterému jste vybranou aplikaci přiřadili, včetně počtu instalací aplikace, které má uživatel na všech svých zařízeních, a informací o případných chybách instalace.