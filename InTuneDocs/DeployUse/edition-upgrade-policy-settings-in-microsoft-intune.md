---
title: "Nastavení zásad upgradu edice Windows | Microsoft Intune"
description: "Přečtěte si, jak lze automaticky upgradovat zařízení s Windows 10 na nejnovější verzi pomocí Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4bed62ebe07d5470414183626b34e68dd91f2d01
ms.openlocfilehash: 17933e41a646f305f9fb765e790c0de36a5036ba


---

# Nastavení zásad upgradu edice Windows v Microsoft Intune
**Zásady upgradu edice** Intune umožňují automaticky upgradovat zařízení s některou z následujících verzí systému Windows 10 na novější edici:
* Windows 10 Desktop
* Windows 10 Holographic

## Než začnete
Před zahájením upgradu zařízení na nejnovější verzi budete potřebovat:
* Kód Product Key, který opravňuje k instalaci nové verze Windows ve všech zařízeních, na která touto zásadou cílíte (pro edice Windows 10 Desktop). Můžete využít klíče k vícenásobné aktivaci (MAK) nebo kódy serveru správy klíčů (KMS).
**nebo** Licenční soubor od Microsoftu, který obsahuje licenční informace pro instalaci nové verze Windows ve všech zařízeních, na která touto zásadou cílíte (pro edice Windows 10 Mobile a Windows 10 Holographic).
* Cílová zařízení Windows 10 musí být registrovaná v Microsoft Intune. Zásady upgradu edice nejde použít pro počítače s klientským softwarem Intune pro počítače.

## Nastavení zásad upgradu edice

|Název nastavení|Podrobnosti|
|-|-|
|**Název**|Zadejte název pro zásady upgradu edice.|
|**Popis**|Volitelně zadejte popis zásad, který vám pomůže při jejich identifikaci v konzole Intune.
|**Edice, na kterou bude provedený upgrade**|V rozevíracím seznamu vyberte verzi Windows 10 Desktop, Windows 10 Holographic nebo Windows 10 Mobile, na kterou chcete cílová zařízení upgradovat.
|**Kód Product Key**|Zadejte kód Product Key, který jste získali od Microsoftu a můžete ho použít k upgradu všech cílových zařízení s Windows 10 Desktop.<br>Až vytvoříte zásady obsahující kód Product Key, nebudete moct tento kód Product Key změnit. Důvodem je to, že kód se z bezpečnostních důvodů schová. Pokud chcete kód Product Key změnit, musíte celý kód zadat znovu.
|**Soubor licencí**|Zvolte **Procházet** a vyberte soubor licencí získaný od Microsoft, který obsahuje informace o licenci pro edici Windows Holographic nebo Windows 10 Mobile, na kterou chcete provést upgrade cílových zařízení.

### Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO4-->


