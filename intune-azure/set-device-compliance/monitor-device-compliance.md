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
ms.sourcegitcommit: 15415f9f31d520d66257df3a7e134e4b1de8467c
ms.openlocfilehash: d70b3bc82b528184b5cfb4d4cad19cb034093e94
ms.lasthandoff: 04/07/2017


---
# <a name="how-to-monitor-device-compliance-in-intune-azure-preview"></a>Informace o tom, jak monitorovat dodržování předpisů zařízeními v Intune Azure Preview

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

Sestava dodržování nastavení poskytuje podrobnosti pro jednotlivá nastavení dodržování předpisů, jako je:

- Počet zařízení nevyhovujících danému nastavení
- Platforma, na kterou se nastavení vztahuje

V každém nastavení si můžete zobrazit více informací o profilech, pro které jsou tato nastavení povolená, a hodnotu daného nastavení.

