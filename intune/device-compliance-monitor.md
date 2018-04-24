---
title: Monitorování dodržování předpisů zařízením
titlesuffix: Microsoft Intune
description: Informace o tom, jak monitorovat dodržování zásad v zařízeních
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b363e074b1b0652a81d56c68e28cf11220adfa56
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="monitor-device-compliance-in-intune"></a>Monitorování dodržování předpisů zařízením v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

V okně **Přehled** si můžete zobrazit souhrn stavu vašich **profilů dodržování předpisů**.
Klikáním v grafech si můžete interaktivně zobrazit podrobnosti. Pokud máte nakonfigurovaných několik profilů dodržování předpisů, můžete si zobrazit stav zásad v okně zásad v části **Spravovat** > **Sestavy**.

##  <a name="device-compliance"></a>Dodržování předpisů zařízení

Souhrnné zobrazení sestavy dodržování předpisů zařízením uvádí agregované informace o počtu zařízení, která se hlásí v jednom z následujících stavů:

- **Vyhovující**: Zařízení se nedávno vyhodnotilo jako vyhovující nastavením profilu dodržování předpisů, která jste určili.
- **Nevyhovující**: Zařízení se vyhodnotilo jako nevyhovující.  Pokud se v profilu nastavilo období odkladu, při přechodu zařízení do stavu Nevyhovující toto období vypršelo.
- **Období odkladu**: Zařízení se vyhodnotilo jako nevyhovující. Stále ale běží období odkladu, do jehož skončení se zařízení neoznačí jako nevyhovující.

V každé sekci si můžete zobrazit podrobnosti o jednotlivých zařízeních a uživatelích.

## <a name="setting-compliance"></a>Dodržování nastavení

Sestava dodržování nastavení poskytuje podrobnosti pro jednotlivá nastavení dodržování předpisů, jako jsou například:

- Počet zařízení nevyhovujících danému nastavení
- Platforma, na kterou se nastavení vztahuje

V každém nastavení si můžete zobrazit více informací o profilech, pro které jsou tato nastavení povolená, a hodnotu daného nastavení.
