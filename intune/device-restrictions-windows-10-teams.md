---
title: "Omezení pro zařízení s Windows 10 Team v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si o omezení zařízení, která jsou k dispozici pro zařízení s Windows 10 Team."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: afbbe6b7649e1ffc3f84ada64396d9033a2db200
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a>Nastavení omezení pro zařízení s Windows 10 Team v Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

- **Probudit obrazovku, když je někdo v místnosti** – Umožňuje automatické probuzení zařízení, když jeho senzor zachytí osobu v místnosti.
- **Kód PIN pro bezdrátovou projekci** – Určuje, jestli před použitím možností bezdrátové projekce zařízení musíte zadat kód PIN.
- **Bezdrátová projekce Miracast** – Tuto možnost povolte, pokud chcete zařízením s Windows 10 Team umožnit použít k projekci zařízení s podporou Miracast.
- **Zobrazování informací o schůzkách na úvodní obrazovce** – Pokud povolíte tuto možnost, budete moct zvolit informace, které se zobrazí na dlaždici Schůzky na úvodní obrazovce. Můžete postupovat následovně:
    - **Zobrazit jenom organizátora a čas**
    - **Zobrazit organizátora, čas a předmět (pro soukromé schůzky se předmět skryje)**
- **Adresa URL obrázku na pozadí úvodní obrazovky** – Povolením tohoto nastavení umožníte zobrazit na **úvodní** obrazovce zařízení s Windows 10 Team vlastní pozadí ze zadané adresy URL.<br>Obrázek musí být ve formátu PNG a adresa URL musí začínat **https://**.
- **Časové období údržby pro aktualizace** – Konfiguruje okno pro provádění aktualizací na zařízení. Můžete nakonfigurovat čas zahájení okna a jeho trvání (1 až 5 hodin).
- **Azure Operational Insights** – Služba Azure Operational Insights, která je součástí sady Microsoft Operations Manager, shromažďuje, ukládá a analyzuje data protokolů ze zařízení s Windows 10 Team.<br>Pokud se chcete připojit k Azure Operational Insights, musíte zadat **ID** a **klíč pracovního prostoru**.

