---
title: "Začínáme s aplikacemi"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 71093f8ac17fc6d6938f5c263a40204f89419726
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/03/2017
---
# <a name="getting-started-with-apps"></a>Začínáme s aplikacemi

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune podporuje různé způsoby nasazení aplikací na firemní zařízení:

* **Instalační programy softwaru**: Umožňují nahrát soubor, který se stáhne do zařízení uživatelů.
* __Externí odkazy__: Když máte aplikaci ve veřejném obchodě s aplikacemi nebo máte webovou aplikaci.
* **Spravované aplikace**: Pro zařízení s iOS, pokud potřebujete u mobilních aplikací, které jsou dostupné v App Storu, použít další správu.

Pojďme si projít jednu z rychlejších metod, kterou je nasazení aplikace tím, že ji přiřadíte z veřejného obchodu.

__Jak přiřadím aplikaci z veřejného obchodu?__

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. V části **Hledat prostředky** vyhledejte **Intune**.
3. Vyberte **Mobilní aplikace** a pak vyberte **Aplikace**.
4. Vyberte **Přidat** a jako **Typ aplikace** vyberte **Aplikace z obchodu pro iOS**.
5. V textovém poli najděte aplikaci, kterou chcete zařízení přiřadit. Zvolte aplikaci a vyberte **OK**.
6. V okně **Přidat aplikaci** vyberte **Informace o aplikaci** a vyplňte všechny informace o aplikaci. Můžete přidat i další podrobnosti užitečné pro zařazení aplikace, jako je **Vlastník**, **Poznámky**, **Vývojář** a **Adresa URL informací o ochraně osobních údajů** pro zásady ochrany osobních údajů používané vaší společností.
7. Nezapomeňte vybrat Ano u možnosti Zobrazit na Portálu společnosti jako vybranou aplikaci a pak vyberte OK.
8. Pokud chcete aplikaci přidat, vyberte **Přidat**. Dostanete se do **přehledu** aplikace. Zvolte **Přiřazení**, klikněte na **Vybrat skupiny** a přiřaďte aplikaci testovací skupině. Dejte aplikaci **k dispozici** ke stažení. Pak by se aplikace na testovacím zařízení měla zobrazit jako **doporučená aplikace**.
