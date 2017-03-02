---
title: "Monitorování dodržování zásad v zařízeních"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Informace o tom, jak monitorovat dodržování předpisů zařízeními"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: d59d94aafa71a9891a6746902339255ea7a9ad15
ms.lasthandoff: 02/18/2017


---
# <a name="how-to-monitor-compliance-in-intune-azure-preview"></a>Jak monitorovat dodržování předpisů zařízeními

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

V okně **Přehled** si můžete zobrazit souhrn stavu vašich **profilů dodržování předpisů**.
Klikáním v grafech si můžete interaktivně zobrazit podrobnosti. Pokud máte nakonfigurovaných několik profilů dodržování předpisů, můžete si navíc zobrazit stav jednotlivých zásad. Stačí přejít na okno zásad a v části **Spravovat** zvolit **Sestavy**.  Podrobnosti sestav, které jsou k dispozici ve verzi Preview, jsou uvedeny níže.

##  <a name="device-compliance"></a>Dodržování předpisů zařízení

Souhrnné zobrazení sestavy dodržování předpisů zařízením začíná agregovanými informacemi o počtu zařízení, která se hlásí jako jedna z následujících:

- **Vyhovující**: Nedávno se vyhodnotilo dodržování předpisů daným zařízením. Zařízení se vyhodnotilo jako vyhovující nastavením profilu dodržování předpisů, která jste určili.
- **Nevyhovující**: Zařízení se vyhodnotilo jako nevyhovující.  Pokud se v profilu nastavilo období odkladu, při přechodu zařízení do stavu Nevyhovující toto období vypršelo.
- **Období odkladu**: Zařízení se vyhodnotilo jako nevyhovující. Stále ale běží období odkladu, do jehož skončení se zařízení neoznačí jako nevyhovující.

V každé sekci si můžete zobrazit podrobnosti o jednotlivých zařízeních a uživatelích.

## <a name="setting-compliance"></a>Dodržování nastavení

Sestava o dodržování nastavení poskytuje podrobnosti pro jednotlivá nastavení dodržování předpisů, jako je:

- Počet zařízení nevyhovujících danému nastavení
- Platforma, na kterou se nastavení vztahuje

V každém nastavení si můžete zobrazit více informací o profilech, pro které jsou tato nastavení povolená, a nakonfigurovanou hodnotu daného nastavení.

