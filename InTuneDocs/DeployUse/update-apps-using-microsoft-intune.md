---
title: "Aktualizace aplikací | Microsoft Intune"
description: "Informace v tomto tématu vám můžou pomoct pochopit, jak můžete aktualizovat aplikace, pokud je vyžadována novější verze."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: bb077902e33d6ab18dea33a6ab2d1ff9a70ce937


---

# Aktualizace aplikací pomocí služby Microsoft Intune
Microsoft Intune může pomoci při správě aktualizací aplikací. Informace v tomto tématu vám můžou pomoct pochopit, jak můžete aktualizovat aplikace, pokud je vyžadována novější verze.

## Jak aplikace aktualizovat
Po vydání nové verze aplikace, kterou máte nasazenou, vám Intune umožní aktualizovat a nasadit novější verze aplikace. Nasazení můžete nahradit jedině novější verzi stejné aplikace (pomocí stejného identifikátoru). Aktualizace aplikací nejde použít k aktualizaci nasazení s jiným balíčkem aplikace.

### Identifikátory aplikací
Identifikátor aplikace je vlastnost, která jednoznačně identifikuje aplikaci. Nejde nainstalovat víc kopií aplikace se stejným identifikátorem. Například:

- **iOS** – ID sady (například: com.microsoft.excel)
- **Android** – ID balíčku (například: com.microsoft.excel)
- **Windows Phone** – (instalační program xap), použijte ID produktu (GUID)
- **Windows** – (appx/appxbundle), použijte úplný název balíčku



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






<!--HONumber=Jul16_HO3-->


