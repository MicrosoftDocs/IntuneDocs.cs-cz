---
title: "Nastavení omezení zařízení Intune pro macOS | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3129cbaf-96c2-4837-8907-ca87a605a496
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1e9c97d66e80de635ad43a1339d092b7987f738b
ms.openlocfilehash: 6856303581f5275c88d5d4efe07088de8f7ab713


---

# <a name="macos-device-restriction-settings-in-intune-azure-preview"></a>Nastavení omezení pro zařízení s macOS v Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="password"></a>Heslo
-   **Zadání hesla nutné** – Vyžaduje, aby koncový uživatel zadal heslo k přístupu k zařízení.
    -   **Požadovaný typ hesla** – Určete, jestli je možné použít jenom číselné heslo nebo jestli je potřeba použít alfanumerické heslo (obsahuje písmena i číslice). Toto nastavení je podporované jenom v systému Mac OS X 10.10.3 a v novějších verzích.
    -   **Počet nealfanumerických znaků v hesle** – Zadejte počet složitých znaků vyžadovaných v hesle (**0** až **4**).<br>Složitý znak je symbol, jako třeba **?**.
    -   **Minimální délka hesla** – Zadejte minimální délku hesla, které uživatel musí nakonfigurovat (mezi **4** a **16** znaky).
    -   **Jednoduchá hesla** – Povolí používat jednoduchá hesla, jako je **0000** nebo **1234**.
    -   **Maximální počet minut po uzamčení obrazovky, po kterém bude nutné zadat heslo** – Určete, jak dlouho musí být počítač neaktivní, než bude nutné k jeho odemknutí heslo.
    -   **Maximální počet minut nečinnosti, po kterém se zamkne obrazovka** – Určete dobu, která musí být počítač v nečinnosti, než se zamkne obrazovka.
    -   **Konec platnosti hesla (dny)** – Určete, jak dlouho si může uživatel nechat stejné heslo, než ho bude muset změnit (**1** až **255** dnů).
    -   **Zakázat opakované použití předchozích hesel** – Určete počet použitých hesel, která se nesmí znova použít (**1** až **24**).

## <a name="restricted-apps"></a>Omezené aplikace

V seznamu omezených aplikací můžete nakonfigurovat jeden z následujících seznamů:

**Zakázané aplikace** – Zobrazí seznam aplikací (nespravovaných pomocí Intune), které nemají uživatelé dovolené nainstalovat a spustit.
**Schválené aplikace** – Zobrazí seznam aplikací, které mají uživatelé dovolené instalovat. Aby byla zachovaná kompatibilita, uživatelé nesmí instalovat aplikace, které nejsou v seznamu. Aplikace, které spravuje Intune, jsou povolené automaticky.

Jestli chcete nakonfigurovat seznam, klikněte na **Přidat**, zadejte nějaký název, případně i vydavatele aplikace, a ID sady prostředků aplikace (například *com.apple.calculator*).





<!--HONumber=Feb17_HO1-->


