---
title: "Nastavení zásad upgradu edice Windows | Microsoft Intune"
description: "Přečtěte si, jak lze automaticky upgradovat zařízení s Windows 10 na nejnovější verzi pomocí Intune."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 94ce40589180ebafcacfb497bc4de9f3458f4ca3


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


<!--HONumber=Jul16_HO3-->


