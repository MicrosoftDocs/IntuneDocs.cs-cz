---
title: "Nastavení zásad upgradu edice Windows | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8e911193075d2a621ef94f2917b2126501ea2100
ms.openlocfilehash: e468ff102b45bf0c23fd76d8d15c44978861ae8a


---

# Nastavení zásad upgradu edice Windows v Microsoft Intune
**Zásady upgradu edice** Intune umožňují automaticky upgradovat zařízení s některou z následujících verzí systému Windows 10 na novější edici:
* Windows 10 Desktop
* Windows 10 Holographic

## Než začnete
Před zahájením upgradu zařízení na nejnovější verzi budete potřebovat:
* Kód Product Key, který opravňuje k instalaci nové verze Windows ve všech zařízeních, na která touto zásadou cílíte (pro edice Windows 10 Desktop).
* Licenční soubor od Microsoftu, který obsahuje licenční informace pro instalaci nové verze Windows ve všech zařízeních, na která touto zásadou cílíte (pro edice Windows 10 Mobile a Windows 10 Holographic).
* Cílová zařízení Windows 10 musí být registrovaná v Microsoft Intune.

## Nastavení zásad upgradu edice

|Název nastavení|Podrobnosti|
|-|-|
|**Název**|Zadejte název pro zásady upgradu edice.|
|**Popis**|Volitelně zadejte popis zásad, který vám pomůže při jejich identifikaci v konzole Intune.
|**Edice, na kterou bude provedený upgrade**|V rozevíracím seznamu vyberte verzi Windows 10 Desktop, Windows 10 Holographic nebo Windows 10 Mobile, na kterou chcete cílová zařízení upgradovat.
|**Kód Product Key**|Zadejte kód Product Key, který jste získali od Microsoftu a můžete ho použít k upgradu všech cílových zařízení s Windows 10 Desktop.<br>Až vytvoříte zásady obsahující kód Product Key, nebudete moct tento kód Product Key změnit. Důvodem je to, že kód se z bezpečnostních důvodů schová. Pokud chcete kód Product Key změnit, musíte celý kód zadat znovu.
|**Soubor licencí**|Klikněte na **Procházet** a vyberte soubor licencí získaný od Microsoft, který obsahuje informace o licenci pro edici Windows Holographic nebo Windows 10 Mobile, na kterou chcete provést upgrade cílových zařízení.

### Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)


<!--HONumber=Jun16_HO4-->


