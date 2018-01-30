---
title: "Nastavení omezení pro zařízení s macOS v Intune"
titlesuffix: Azure portal
description: "Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s macOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3129cbaf-96c2-4837-8907-ca87a605a496
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 69fc2959c7694a0120efff8653ce8d619f33a9d3
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="macos-device-restriction-settings-in-microsoft-intune"></a>Nastavení omezení pro zařízení s macOS v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pomocí těchto nastavení můžete spravovat zařízení s macOS.

## <a name="password"></a>Heslo
-   **Heslo** – Vyžaduje, aby koncový uživatel zadal heslo pro přístup k zařízení.
    -   **Požadovaný typ hesla** – Určete, jestli je možné použít jenom číselné heslo nebo jestli je potřeba použít alfanumerické heslo (obsahuje písmena i číslice). Toto nastavení je podporované jenom v systému Mac OS X 10.10.3 a v novějších verzích.
    -   **Počet nealfanumerických znaků v hesle** – Zadejte počet složitých znaků vyžadovaných v hesle (**0** až **4**).<br>Složitý znak je symbol, například **?**.
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

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Zrušení označení e-mailových domén

V poli **Adresa URL e-mailové domény** přidejte do seznamu minimálně jednu adresu URL. Když koncoví uživatelé dostanou e-mail z jiné domény než z té, kterou jste nakonfigurovali, označí se v aplikaci iOS Mail daný e-mail jako nedůvěryhodný.

