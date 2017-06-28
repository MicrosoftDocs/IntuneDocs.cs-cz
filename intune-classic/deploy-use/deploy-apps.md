---
title: "Nasazení aplikací"
description: "Toto téma vysvětluje koncepty, kterým je třeba porozumět před zahájením nasazování aplikací s Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 13c4046ed431dc25bda9a2facc59dbcb6d3e5ab5
ms.contentlocale: cs-cz
ms.lasthandoff: 06/08/2017


---

# <a name="deploy-apps-with-microsoft-intune"></a>Nasazení aplikací s Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Toto téma vysvětluje některé koncepty, kterým je třeba porozumět před zahájením nasazování aplikací s Microsoft Intune.


## <a name="app-deployment-actions"></a>Akce nasazení aplikace
Při nasazování aplikací můžete zvolit jednu z následujících akcí nasazení:

-   **Požadovaná instalace** – Aplikace se nainstaluje do zařízení bez nutnosti zásahu uživatele.

    > [!TIP]
    > Pro zařízení s iOS, která nejsou v dohledovém režimu, a pro všechna zařízení s Androidem, musí uživatel aplikaci před instalací přijmout.
    >
    >  Pokud uživatel odinstaluje aplikaci, kterou jste nasadili jako požadovanou instalaci, Intune ji při příštím cyklu inventáře, který obvykle probíhá každých sedm dní, znovu automaticky nainstaluje.

-   **Dostupná instalace** – Aplikace se zobrazuje na podnikovém portálu a uživatelé ji můžou instalovat na vyžádání.

-   **Odinstalace** – Aplikace se ze zařízení odinstaluje.

-   **Není k dispozici** – Aplikace se nezobrazuje na podnikovém portálu a není nainstalovaná na žádném zařízení.

#### <a name="understand-which-deployment-actions-are-available-for-each-installer-type"></a>Zjistěte, které akce nasazení jsou dostupné pro jednotlivé typy instalačních programů:

|Typ instalačního programu|Požadovaná instalace|Dostupná instalace|Odinstalovat|Není k dispozici|
|------------------|--------------------|---------------------|-------------|------------------|
|Balíček aplikací pro Windows (nasazený pro skupinu uživatelů)|Ano|Ano|Ano|Ano|
|Balíček aplikací pro Windows (nasazený pro skupinu zařízení)|Ano|Ne|Ano|Ano|
|Balíček aplikace pro mobilní zařízení (nasazený pro skupinu uživatelů)|Ano|Ano|Ano|Ano|
|Balíček aplikace pro mobilní zařízení (nasazený pro skupinu zařízení)|Ano|Ne|Ano|Ano|
|Instalační služba systému Windows (nasazené pro skupinu uživatelů)|Ne|Ano|Ne|Ano|
|Instalační služba systému Windows (nasazené pro skupinu zařízení)|Ano|Ne|Ano|Ano|
|Externí odkaz (nasazený pro skupinu uživatelů)|Ne|Ano|Ne|Ano|
|Externí odkaz (nasazený pro skupinu zařízení)|Ne|Ne|Ne|Ne|
|Spravovaná aplikace pro iOS z App Storu (nasazené pro skupinu uživatelů)|Ano|Ano|Ano|Ano|
|Spravovaná aplikace pro iOS z App Storu (nasazené pro skupinu zařízení)|Ano|Ne|Ano|Ano|
> [!TIP]
> Když nasazujete aplikace a vyberete jak skupiny uživatelů, tak zařízení, můžete aplikaci nasadit jenom s možností **Dostupná instalace**.

## <a name="deployment-conflicts"></a>Konflikty nasazení
Při dvou nasazeních platí při přijetí stejné akce nasazení na zařízení následující pravidla:

-   Nasazení pro skupinu zařízení má přednost před nasazením pro skupinu uživatelů. Pokud je ale aplikace nasazená pro skupinu uživatelů pomocí akce nasazení **Dostupné** a v případě, že je stejná aplikace nasazená taky pro skupinu zařízení pomocí akce nasazení **Není k dispozici**, aplikace bude dostupná na podnikovém portálu a uživatelé si ji můžou nainstalovat.

-   Akce instalace má přednost před akcí odinstalace.

-   Pokud zařízení přijme požadovanou i dostupnou instalaci, akce se zkombinují. Jinými slovy uživatel může nainstalovat dostupnou aplikaci z Portálu společnosti před zahájením požadované instalace.


## <a name="next-steps"></a>Další kroky

Přečtěte si, jak [nasazovat aplikace v Microsoft Intune](deploy-apps-in-microsoft-intune.md).

