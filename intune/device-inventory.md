---
title: "Zobrazení inventáře zařízení spravovaných přes Intune"
titleSuffix: Intune on Azure
description: "Informace o tom, jak zobrazit zařízení spravovaná přes Intune a zjistit jejich hardware a nainstalované aplikace"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dae92c117bcf8a4a8ff133ed613f9f77ea0c07c2
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-view-intune-device-inventory"></a>Jak zobrazit inventář zařízení spravovaných přes Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Úloha **Zařízení** poskytuje přehled o zařízeních, která spravujete, včetně jejich hardwarových možností a aplikací na nich nainstalovaných. 

Zobrazení inventáře zařízení:

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Zařízení**.

Teď zvolte jednu z následujících možností:

- **Přehled** – získáte informace o zaregistrovaných zařízeních a operačních systémech na jednotlivých zařízeních.
- **Spravovat** – volbou možnosti **Všechna zařízení** zobrazíte seznam všech spravovaných zařízení.
    Když vyberete některé zařízení v tomto seznamu, otevře se okno <*název zařízení*> **Přehled**, kde můžete vybrat jednu z těchto možností:
    - **Přehled** – zobrazí se obecné informace o tomto zařízení, například název, vlastník, jestli se jedná o vlastní zařízení uživatele, kdy se přihlásilo a další.
    ![Přehled zařízení](./media/device-overview.png)
    - **Hardware** – zobrazí podrobnější informace o zařízení, například volný úložný prostor, model a výrobce.
    ![Inventář hardwaru spravovaných zařízení](./media/hardware-inventory.png)
    - **Zjištěné aplikace** – zobrazí seznam všech nainstalovaných aplikací, které služba Intune našla na zařízení.
    ![Uzel zjištěných aplikací](./media/detected-applications.png)
    - **Dodržování předpisů zařízením** – zobrazí, jak se na zařízení dodržují všechny zásady dodržování předpisů, které k němu byly přiřazeny.
    - **Konfigurace zařízení** – zobrazí, jak se na zařízení dodržují všechny zásady konfigurace zařízení, které k němu byly přiřazeny.
- **Monitorování** – volbou možnosti **Akce zařízení** zobrazíte seznam akcí, které byly na spravovaných zařízeních provedeny, a jejich aktuální stav.
- **Nastavení** > **Konektor pro TeamViewer**  – umožňuje konfiguraci vzdálené správy na zařízeních pomocí softwaru TeamViewer. Další informace najdete v tématu [Poskytování vzdálené pomoci pro zařízení s Androidem, která se spravují přes Intune](/intune/device-profile-android-teamviewer).


