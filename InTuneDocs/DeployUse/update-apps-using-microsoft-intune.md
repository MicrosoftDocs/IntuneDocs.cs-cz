---
title: "Aktualizace aplikací | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ms.reviewer: mghadial
ms.suite: ems
ms.sourcegitcommit: 0581d1476fba5bedcdd4446df20f8f92b151f41b
ms.openlocfilehash: 9e5b8f4a467e8e58cc2f8fa495b5f008eee7e35b


---

# Aktualizace aplikací pomocí služby Microsoft Intune
Microsoft Intune může pomoci při správě aktualizací aplikací. Informace v tomto tématu vám můžou pomoct pochopit, jak můžete aktualizovat aplikace, pokud je vyžadována novější verze.

## Jak aplikace aktualizovat
Po vydání nové verze aplikace, kterou máte nasazenou, vám Intune umožní aktualizovat a nasadit novější verze aplikace. Nasazení můžete nahradit jedině novější verzi stejné aplikace (pomocí stejného identifikátoru). Aktualizace aplikací nejde použít k aktualizaci nasazení s jiným balíčkem aplikace.

> [!IMPORTANT]
> Když nasadíte aplikaci pomocí akce nasazení **Požadovaná instalace** a později změníte akci nasazení na **Dostupná instalace**, nenainstalují se aktualizace aplikace automaticky na zařízení, na která se aplikace nainstalovala ještě před provedením změny nasazení. Pokud budete chtít tento problém vyřešit, můžete udělat toto:
> 
> -   Dejte uživateli zařízení pokyn, aby přešel na portál společnosti, vybral nainstalovanou aplikaci a zvolil **Nainstalovat**.
> -   Změňte akci nasazení na **Odinstalace**a po odinstalaci aplikace aplikaci znovu nasaďte pomocí akce nasazení **Dostupná instalace**.

### Aktualizace aplikace

1.  V [konzole správce Microsoft Intune](https://manage.microsoft.com) zvolte **Aplikace**&gt;**Aplikace**.

2.  Ze seznamu **Aplikace** vyberte aplikaci, kterou chcete aktualizovat, a potom zvolte **Upravit**.

3.  V průvodci **úpravou softwaru** zadejte jakékoli nového podrobnosti balíčku aplikace.

4.  Po dokončení zvolte **Aktualizovat**.

Až budou zařízení příště zjišťovat dostupnost aplikací, aplikace se automaticky aktualizuje na nejnovější verzi.
Pro aplikace nainstalované z balíčku aplikací (obchodní aplikace) bude aplikace automaticky upgradována v případě požadovaného i dostupného nasazení, pokud má aplikace stejný identifikátor.
V případě aplikací nasazených jako odkaz na obchod je aktualizace spravována obchodem, ze kterého aplikace pochází.






<!--HONumber=Jul16_HO2-->


