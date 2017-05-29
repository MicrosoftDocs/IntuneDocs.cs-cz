---
title: "Postup monitorování informací a přiřazení aplikace | Dokumentace Microsoftu"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Po přiřazení aplikace uživatelům nebo zařízením můžete použít tyto informace, které vám usnadní monitorování jejího stavu."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7c39c904cd2a7bd20525d9072067c6e484b4437a
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Postup monitorování informací a přiřazení aplikace pomocí Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Intune poskytuje několik způsobů, jak můžete monitorovat vlastnosti vámi spravovaných aplikací a stav jejich přiřazení.

1. V úloze **Mobilní aplikace** zvolte **Spravovat** > **Aplikace**.
2. V okně se seznamem aplikací zvolte aplikaci, pro kterou chcete informace zobrazit. Pak se vám zobrazí okno <*název aplikace*> **Stav instalace zařízení**: ![Stav instalace aplikace.](./media/monitor-apps.png)

Pak zjistěte další informace o aplikacích a jejich přiřazení pomocí jedné z následujících akcí.

## <a name="general"></a>Obecné

- **Přehled** – poskytuje základní přehled aplikace a informace o stavu všech přiřazení této aplikace. Pomocí některého z přehledů můžete otevřít okna **Stav instalace zařízení** nebo **Stav instalace uživatele** a získat podrobnější informace.

## <a name="manage"></a>Správa

- **Vlastnosti** – umožňují zobrazit a změnit informace o vybrané aplikaci. Další informace o vlastnostech aplikací najdete v tématu [Přidání aplikace do Microsoft Intune](apps-add.md).
- **Přiřazení** – poskytují informace o přiřazeních této aplikace. Další informace najdete v článku [Jak přiřadit aplikace do skupin pomocí Microsoft Intune](apps-deploy.md).

## <a name="monitor"></a>Monitorování

- **Stav instalace zařízení** – poskytuje podrobné informace o každém zařízení, kterému jste přiřadili vybranou aplikaci, včetně názvu zařízení, operačního systému, data posledního přihlášení zařízení do Intune a stavu instalace aplikace.
- **Stav instalace uživatele** – poskytuje podrobné informace o uživateli, kterému jste vybranou aplikaci přiřadili, včetně počtu instalací aplikace, které má uživatel na všech svých zařízeních, a informací o případných chybách instalace.
