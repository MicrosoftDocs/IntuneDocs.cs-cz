---
title: "Zobrazení inventáře zařízení spravovaných přes Intune"
titlesuffix: Azure portal
description: "Informace o tom, jak zobrazit zařízení spravovaná přes Intune a zjistit jejich hardware a nainstalované aplikace"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 11/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 772e2b1380626384d618e653b90b31a1f421eb72
ms.sourcegitcommit: 80a2eefc1896a42cc2bc16be23093d1abf58b088
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/27/2018
---
# <a name="how-to-view-intune-device-inventory"></a>Jak zobrazit inventář zařízení spravovaných přes Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Úloha **Zařízení** poskytuje přehled o zařízeních, která spravujete, včetně jejich hardwarových možností a aplikací na nich nainstalovaných. 

Zobrazení inventáře zařízení:

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V okně **Intune** zvolte **Zařízení**.

Teď zvolte jednu z následujících možností:

- **Přehled** – získáte informace o zaregistrovaných zařízeních a operačních systémech na jednotlivých zařízeních.
- **Spravovat** – volbou možnosti **Všechna zařízení** zobrazíte seznam všech spravovaných zařízení.
    Když vyberete některé zařízení v tomto seznamu, otevře se okno <*název zařízení*> **Přehled**, kde můžete vybrat jednu z těchto možností:
    - **Přehled** – zobrazí se obecné informace o tomto zařízení, například název, vlastník, jestli se jedná o vlastní zařízení uživatele, kdy se přihlásilo a další.
    - **Hardware** – zobrazí podrobnější informace o zařízení, například volný úložný prostor, model a výrobce.
    - **Zjištěné aplikace** – zobrazí seznam všech nainstalovaných aplikací, které služba Intune našla na zařízení.
    - **Dodržování předpisů zařízením** – zobrazí, jak se na zařízení dodržují všechny zásady dodržování předpisů, které k němu byly přiřazeny.
    - **Konfigurace zařízení** – zobrazí, jak se na zařízení dodržují všechny zásady konfigurace zařízení, které k němu byly přiřazeny.
- **Monitorování** – volbou možnosti **Akce zařízení** zobrazíte seznam akcí, které byly na spravovaných zařízeních provedeny, a jejich aktuální stav.
- **Nastavení** > **Konektor pro TeamViewer**  – umožňuje konfiguraci vzdálené správy na zařízeních pomocí softwaru TeamViewer. Další informace najdete v tématu [Poskytování vzdálené pomoci pro zařízení s Androidem, která se spravují přes Intune](/intune/device-profile-android-teamviewer).

Intune shromažďuje inventář aplikací jenom na zařízeních vlastněných společností. Na osobních zařízeních se aplikace neinventarizují. V případě počítačů s Windows 10 se shromažďuje jenom inventář moderních aplikací na zařízeních vlastněných společností. Intune neshromažďuje informace o aplikacích Win32 na zařízeních. V závislosti na operátorovi, kterého pro zařízení používáte, se nemusí shromažďovat všechny položky inventáře.
