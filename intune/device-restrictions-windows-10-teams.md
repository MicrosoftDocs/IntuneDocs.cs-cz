---
title: "Omezení pro zařízení s Windows 10 Team v Intune"
titlesuffix: Azure portal
description: "Přečtěte si o omezení zařízení, která jsou k dispozici pro zařízení s Windows 10 Team."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 33142a4e7b95d8b689ab85ef6a25e56fd365aa82
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/12/2017
---
# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a>Nastavení omezení pro zařízení s Windows 10 Team v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="apps-and-experience"></a>Aplikace a prostředí

- **Probudit obrazovku, když je někdo v místnosti** – Umožňuje automatické probuzení zařízení, když jeho senzor zachytí osobu v místnosti.
- **Zobrazování informací o schůzkách na úvodní obrazovce** – Pokud povolíte tuto možnost, budete moct zvolit informace, které se zobrazí na dlaždici Schůzky na úvodní obrazovce. Můžete postupovat následovně:
    - **Zobrazit jenom organizátora a čas**
    - **Zobrazit organizátora, čas a předmět (u privátních schůzek je předmět skrytý)**
- **Adresa URL obrázku na pozadí úvodní obrazovky** – Povolením tohoto nastavení umožníte zobrazit na **úvodní** obrazovce zařízení s Windows 10 Team vlastní pozadí ze zadané adresy URL.<br>Obrázek musí být ve formátu PNG a adresa URL musí začínat **https://**.

## <a name="azure-operational-insights"></a>Azure Operational Insights

- **Azure Operational Insights** – Služba Azure Operational Insights, která je součástí sady Microsoft Operations Manager, shromažďuje, ukládá a analyzuje data protokolů ze zařízení s Windows 10 Team.
Pokud se chcete připojit k Azure Operational Insights, musíte zadat **ID** a **klíč pracovního prostoru**.

## <a name="maintenance"></a>Údržba

- **Časové období údržby pro aktualizace** – Konfiguruje okno pro provádění aktualizací na zařízení. Můžete nakonfigurovat **Počáteční čas** okna a jeho **Dobu trvání v hodinách** (1 až 5 hodin).

## <a name="wireless-projection"></a>Bezdrátová projekce

- **Kód PIN pro bezdrátovou projekci** – Určuje, jestli před použitím možností bezdrátové projekce zařízení musíte zadat kód PIN.
- **Bezdrátová projekce Miracast** – Tuto možnost vyberte, pokud chcete zařízením s Windows 10 Team umožnit použít k projekci zařízení s podporou Miracastu.
- **Kanál bezdrátové projekce Miracast** – Vyberte kanál Miracast, který se použije k navázání připojení.


## <a name="next-steps"></a>Další kroky

S použitím informací v tématu [Jak nakonfigurovat nastavení omezení zařízení](device-restrictions-configure.md) uložte a přiřaďte profil uživatelům a zařízením.
