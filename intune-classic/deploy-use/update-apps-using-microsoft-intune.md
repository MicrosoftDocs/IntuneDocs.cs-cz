---
title: "Aktualizace aplikací"
description: "Informace v tomto tématu vám můžou pomoct pochopit, jak můžete aktualizovat aplikace, pokud je vyžadována novější verze."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c643ea0e75a3376a30d43fc0c5ac4ef421c65bea
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/15/2017
---
# <a name="update-apps-using-microsoft-intune"></a>Aktualizace aplikací pomocí služby Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune může pomoci při správě aktualizací aplikací. Informace v tomto tématu vám můžou pomoct pochopit, jak můžete aktualizovat aplikace, pokud je vyžadována novější verze.

## <a name="how-to-update-apps"></a>Jak aplikace aktualizovat
Po vydání nové verze aplikace, kterou máte nasazenou, vám Intune umožní aktualizovat a nasadit novější verze aplikace. Nasazení můžete nahradit jedině novější verzi stejné aplikace (která má stejný identifikátor). Aktualizace aplikací nejde použít k aktualizaci nasazení s jiným balíčkem aplikace.

### <a name="app-identifiers"></a>Identifikátory aplikací
Identifikátor aplikace je vlastnost, která jednoznačně identifikuje aplikaci. Nejde nainstalovat víc kopií aplikace se stejným identifikátorem. Toto jsou některé z příkladů identifikátorů aplikací:

- **iOS** – ID sady (například: com.microsoft.excel)
- **Android** – ID balíčku (například: com.microsoft.excel)
- **Windows Phone** – (instalační program xap), použijte ID produktu (GUID)
- **Windows** – (appx/appxbundle), použijte úplný název balíčku



> [!IMPORTANT]
> Když nasadíte aplikaci pomocí akce nasazení **Požadovaná instalace** a později změníte akci nasazení na **Dostupná instalace**, nenainstalují se aktualizace aplikace automaticky na zařízení, na která se aplikace nainstalovala ještě před provedením změny nasazení. Pokud budete chtít tento problém vyřešit, můžete udělat toto:
>
> -   Dejte uživateli zařízení pokyn, aby přešel na portál společnosti, vybral nainstalovanou aplikaci a pak zvolil **Nainstalovat**.
> -   Změňte akci nasazení na **Odinstalace**a po odinstalaci aplikace aplikaci znovu nasaďte pomocí akce nasazení **Dostupná instalace**.

### <a name="to-update-an-app"></a>Aktualizace aplikace

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) zvolte **Aplikace**&gt;**Aplikace**.

2.  Ze seznamu **Aplikace** vyberte aplikaci, kterou chcete aktualizovat, a potom zvolte **Upravit**.

3.  V průvodci **úpravou softwaru** zadejte jakékoli nového podrobnosti balíčku aplikace.

4.  Po dokončení zvolte **Aktualizovat**.

Až budou zařízení příště zjišťovat dostupnost aplikací, aplikace se automaticky aktualizuje na nejnovější verzi.
Pro aplikace nainstalované z balíčku aplikací (obchodní aplikace) se aplikace automaticky upgraduje v případě požadovaného i dostupného nasazení, pokud má stejný identifikátor.

V případě aplikací nasazených jako odkaz na obchod je aktualizace spravována obchodem, ze kterého aplikace pochází.
