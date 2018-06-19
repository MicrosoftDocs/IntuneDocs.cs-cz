---
title: Zobrazení podrobností o zařízeních v Microsoft Intune – Azure | Microsoft Docs
description: Zobrazte si podrobnosti o zařízení, včetně operačních systémů, místa v úložišti, výrobce a modelu. Microsoft Intune v Azure vám umožňuje získat seznam nainstalovaných aplikací, zkontrolovat zásady dodržování předpisů a nastavit TeamViewer. Jedná se o podobný princip jako při zobrazení inventáře zařízení, která spravujete.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f66c0695c7e3d1f4bb7a5ca3abceeb13f6af41f2
ms.sourcegitcommit: 3c4ea8d6809a63042705b5ed4f25ba80f522070e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
ms.locfileid: "34051602"
---
# <a name="see-device-details-in-intune"></a>Zobrazení podrobností o zařízení v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Funkce **Zařízení** poskytuje další podrobnosti o zařízení, která spravujete, včetně jejich hardwaru a nainstalovaných aplikací.

V tomto článku se dozvíte, jak si můžete zobrazit všechna zařízení a jejich vlastnosti na portálu Azure Portal.

## <a name="view-the-device-details"></a>Zobrazení podrobností o zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Zařízení** > **Všechna zařízení** > výběrem zařízení uvedeného v seznamu otevřete podrobné informace o něm:

   - **Přehled** zobrazuje název zařízení a uvádí některé jeho klíčové vlastnosti, včetně toho, jestli se jedná o zařízení programu Přineste si vlastní zařízení (BYOD), kdy bylo zaregistrováno a dalších informací. Když vyberte **Další**, můžete navíc:
     - Odebrání firemních dat
     - Smazat zařízení
     - Zařízení na dálku uzamknout
     - Vymazat zařízení
     - Spustit relaci vzdálené pomoci
   - Pomocí **vlastností** můžete zařízení přiřadit [kategorii, kterou vytvoříte](device-group-mapping.md), a upravit jeho vlastnictví na osobní nebo podnikové.
   - Část **Hardware** obsahuje řadu podrobnosti o zařízení, včetně jeho ID, operačního systému a verze, úložného prostoru, modelu a výrobce, nastavení podmíněného přístupu a další.
   - V části **Zjištěné aplikace** se zobrazuje seznam všech nainstalovaných aplikací, které služba Intune v zařízení našla, včetně jejich verzí. Seznam aplikací můžete také **exportovat** do souboru CSV.
   - V části **Dodržování předpisů zařízení** najdete všechny přiřazené zásady dodržování předpisů a informaci, jestli je zařízení splňuje.
   - Část **Konfigurace zařízení** obsahuje všechny zásady konfigurace přiřazené zařízení a informaci, jestli byly zásady úspěšné.

Intune shromažďuje seznam aplikací jenom na zařízeních vlastněných společností. Na osobních zařízeních se aplikace nekontrolují. V případě počítačů s Windows 10 se uvádí jenom moderní aplikace na zařízeních vlastněných společností. Intune neshromažďuje informace o aplikacích Win32 na zařízeních. V závislosti na operátorovi, kterého zařízení používají, se některé aplikace nemusí shromažďovat.

|Platforma|Pro zařízení v osobním vlastnictví|Pro zařízení ve vlastnictví společnosti|  
|--------------|---------------------------------|--------------------------------|  
|Windows 10 (bez klienta Configuration Manageru)|Pouze spravované aplikace|Pouze spravované aplikace|
|Windows 8.1 (bez klienta Configuration Manageru)|Pouze spravované aplikace|Pouze spravované aplikace|  
|Windows Phone 8|Pouze spravované aplikace|Pouze spravované aplikace|  
|Windows RT|Pouze spravované aplikace|Pouze spravované aplikace|  
|iOS|Pouze spravované aplikace|Všechny aplikace instalované na zařízení|
|macOS|Všechny aplikace instalované na zařízení|Všechny aplikace instalované na zařízení|  
|Android|Pouze spravované aplikace|Všechny aplikace instalované na zařízení|  

## <a name="next-steps"></a>Další kroky
Podívejte se, jaké další akce [správy zařízení](device-management.md) můžete provádět pomocí Intune.