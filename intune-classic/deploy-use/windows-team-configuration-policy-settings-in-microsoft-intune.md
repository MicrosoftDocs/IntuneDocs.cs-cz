---
title: Nastavení zásad konfigurace pro Windows Team
description: Použijte **obecné zásady konfigurace Microsoft Intune pro Windows 10 Team** ke konfiguraci nastavení pro registrovaná zařízení se systémem Windows 10, jako je třeba Microsoft Surface Hub.
keywords: ''
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 70b1091cd58439b7d42eab1a612b0b63ca39103d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>Nastavení zásad konfigurace pro Windows Team v Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Použijte **obecné zásady konfigurace Microsoft Intune pro Windows 10 Team** ke konfiguraci nastavení pro registrovaná zařízení se systémem Windows 10, jako je třeba Microsoft Surface Hub.


|                                  Název nastavení                                   |                                                                                                                                                                Podrobnosti                                                                                                                                                                |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <strong>Povolit automatické probuzení obrazovky, když je někdo v místnosti</strong>   |                                                                                                                         Umožňuje zařízení automatické probuzení, když jeho senzor zachytí osobu v místnosti.                                                                                                                          |
|              <strong>Požadovat pro bezdrátové promítání PIN</strong>               |                                                                                                             Určuje, jestli před použitím možností bezdrátové projekce zařízení musíte zadat kód PIN.                                                                                                             |
|          <strong>Nastavit časové období údržby pro aktualizace zařízení</strong>           |                                                                                          Konfiguruje okno při provádění aktualizací na zařízení. Můžete nakonfigurovat čas zahájení okna a jeho trvání (1 až 5 hodin).                                                                                           |
|               <strong>Povolit Azure Operational Insights</strong>                |                  Služba Azure Operational Insights, která je součástí sady Microsoft Operations Manager, shromažďuje, ukládá a analyzuje data protokolů ze zařízení s Windows 10 Team.<br /><br />Pokud se chcete připojit k Azure Operational Insights, musíte zadat <strong>ID</strong> a <strong>klíč pracovního prostoru</strong>.                   |
|              <strong>Povolit bezdrátové promítání Miracast</strong>               |                                          Tuto možnost povolte, pokud chcete zařízením s Windows 10 Team umožnit použít k projekci zařízení s podporou Miracast.<br /><br />Pokud tuto možnost povolíte, v seznamu <strong>Vybrat kanál Miracast</strong> vyberte kanál Miracast použitý k projekci obsahu.                                           |
| <strong>Zvolit informace o schůzce zobrazené na úvodní obrazovce</strong> | Pokud povolíte tuto možnost, můžete zvolit informace, které se zobrazí na dlaždici <strong>Schůzky</strong> na <strong>úvodní</strong> obrazovce. Můžete postupovat následovně:<br /><br />-   <strong>Zobrazit jenom organizátora a čas</strong><br />-   <strong>Zobrazit organizátora, čas a předmět (pro soukromé schůzky se předmět skryje)</strong> |
|                <strong>Adresa URL obrázku pozadí zamykací obrazovky</strong>                 |                                           Povolením tohoto nastavení umožníte zobrazit na <strong>úvodní</strong> obrazovce zařízení s Windows 10 Team vlastní pozadí ze zadané adresy URL.<br /><br />Obrázek musí být ve formátu PNG a adresa URL musí začínat <strong>https://</strong>.                                            |

### <a name="see-also"></a>Viz taky
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

