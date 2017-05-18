---
title: "Nastavení zásad konfigurace pro Windows Team | Dokumentace Microsoftu"
description: "Použijte **obecné zásady konfigurace Microsoft Intune pro Windows 10 Team** ke konfiguraci nastavení pro registrovaná zařízení se systémem Windows 10, jako je třeba Microsoft Surface Hub."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: 136f83a7340424b420e4a487a0758992a802ece3
ms.lasthandoff: 12/30/2016


---

# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>Nastavení zásad konfigurace pro Windows Team v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Použijte **obecné zásady konfigurace Microsoft Intune pro Windows 10 Team** ke konfiguraci nastavení pro registrovaná zařízení se systémem Windows 10, jako je třeba Microsoft Surface Hub.

|Název nastavení|Podrobnosti|
|----------------|-----------|
|**Povolit automatické probuzení obrazovky, když je někdo v místnosti**|Umožňuje zařízení automatické probuzení, když jeho senzor zachytí osobu v místnosti.|
|**Požadovat pro bezdrátové promítání PIN**|Určuje, jestli před použitím možností bezdrátové projekce zařízení musíte zadat kód PIN.|
|**Nastavit časové období údržby pro aktualizace zařízení**|Konfiguruje okno při provádění aktualizací na zařízení. Můžete nakonfigurovat čas zahájení okna a jeho trvání (1 až 5 hodin).|
|**Povolit Azure Operational Insights**|Služba Azure Operational Insights, která je součástí sady Microsoft Operations Manager, shromažďuje, ukládá a analyzuje data protokolů ze zařízení s Windows 10 Team.<br /><br />Pokud se chcete připojit k Azure Operational Insights, musíte zadat **ID** a **klíč pracovního prostoru**.|
|**Povolit bezdrátové promítání Miracast**|Tuto možnost povolte, pokud chcete zařízením s Windows 10 Team umožnit použít k projekci zařízení s podporou Miracast.<br /><br />Pokud tuto možnost povolíte, v seznamu **Vybrat kanál Miracast** vyberte kanál Miracast použitý k projekci obsahu.|
|**Zvolit informace o schůzce zobrazené na úvodní obrazovce**|Pokud povolíte tuto možnost, můžete zvolit informace, které se zobrazí na dlaždici **Schůzky** na **úvodní** obrazovce. Můžete postupovat následovně:<br /><br />-   **Zobrazit jenom organizátora a čas**<br />-   **Zobrazit organizátora, čas a předmět (pro soukromé schůzky se předmět skryje)**|
|**Adresa URL obrázku pozadí zamykací obrazovky**|Povolením tohoto nastavení umožníte zobrazit na **úvodní** obrazovce zařízení s Windows 10 Team vlastní pozadí ze zadané adresy URL.<br /><br />Obrázek musí být ve formátu PNG a adresa URL musí začínat **https://**.|


### <a name="see-also"></a>Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

