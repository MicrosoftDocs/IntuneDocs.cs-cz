---
title: Monitorování dodržování předpisů zařízením
titlesuffix: Microsoft Intune
description: Informace o tom, jak monitorovat dodržování zásad v zařízeních
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 534e8316e584259a818130ea9f83c88b44b67fee
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55848079"
---
# <a name="monitor-device-compliance-in-intune"></a>Monitorování dodržování předpisů zařízením v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

V okně **Přehled** si můžete zobrazit souhrn stavu vašich **profilů dodržování předpisů**.
Klikáním v grafech si můžete interaktivně zobrazit podrobnosti. Pokud máte nakonfigurovaných několik profilů dodržování předpisů, můžete si zobrazit stav zásad v okně zásad v části **Spravovat** > **Sestavy**.

##  <a name="device-compliance"></a>Dodržování předpisů zařízení

Souhrnné zobrazení sestavy dodržování předpisů zařízením uvádí agregované informace o počtu zařízení, která se hlásí v jednom z následujících stavů:

- **Kompatibilní**: Zařízení naposledy byl vyhodnocen a v souladu s nastavením profilu dodržování předpisů, které jste zadali.
- **Nekompatibilní**: Zařízení se vyhodnotí a vyhodnotí se jako nevyhovující.  Pokud se v profilu nastavilo období odkladu, při přechodu zařízení do stavu Nevyhovující toto období vypršelo.
- **Období odkladu**: Zařízení se vyhodnotí a vyhodnotí se jako nevyhovující. Stále ale běží období odkladu, do jehož skončení se zařízení neoznačí jako nevyhovující.

V každé sekci si můžete zobrazit podrobnosti o jednotlivých zařízeních a uživatelích.

## <a name="setting-compliance"></a>Dodržování nastavení

Sestava dodržování nastavení poskytuje podrobnosti pro jednotlivá nastavení dodržování předpisů, jako jsou například:

- Počet zařízení nevyhovujících danému nastavení
- Platforma, na kterou se nastavení vztahuje

V každém nastavení si můžete zobrazit více informací o profilech, pro které jsou tato nastavení povolená, a hodnotu daného nastavení.
