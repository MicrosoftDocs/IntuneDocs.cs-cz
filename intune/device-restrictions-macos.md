---
title: Nastavení omezení pro zařízení s macOS v Microsoft Intune
titlesuffix: ''
description: Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení a funkce na zařízeních s macOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 69ea07e8d0a5d4a54abe7d1e592b3930d4e82354
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="microsoft-intune-macos-device-restriction-settings"></a>Nastavení omezení pro zařízení s macOS v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek ukazuje nastavení omezení zařízení v Microsoft Intune, která můžete nakonfigurovat pro zařízení s macOS.

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

- **Zakázané aplikace** – Zobrazí seznam aplikací (nespravovaných pomocí Intune), které nemají uživatelé dovolené nainstalovat a spustit. Uživatelům není instalace zakázané aplikace znemožněna, ale pokud ji provedou, budete na to upozorněni.
- **Schválené aplikace** – Zobrazí seznam aplikací, které mají uživatelé dovolené instalovat. Uživatelé nesmí instalovat aplikace, které nejsou v seznamu. Aplikace, které spravuje Intune, jsou povolené automaticky. Uživatelům není instalace aplikace nenacházející se v seznamu povolených aplikací znemožněna, ale pokud ji provedou, budete na to upozorněni.

Jestli chcete nakonfigurovat seznam, klikněte na **Přidat**, zadejte nějaký název, případně i vydavatele aplikace, a ID sady prostředků aplikace (například *com.apple.calculator*).

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Zrušení označení e-mailových domén

V poli **Adresa URL e-mailové domény** přidejte do seznamu minimálně jednu adresu URL. Když uživatelé dostanou e-mail z jiné domény než z té, kterou jste nakonfigurovali, označí se v aplikaci iOS Mail daný e-mail jako nedůvěryhodný.

