---
title: "Začínáme s aplikacemi"
titlesuffix: Azure portal
description: "Najděte a přidejte aplikace do zařízení, aby mohli vaši zaměstnanci plnit úkoly."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bb02c362f056c454f4d141ce7ae20b9c3ca8035d
ms.sourcegitcommit: a7c1e10e615e5c975bb5d52eca986c5cf5287687
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/07/2017
---
# <a name="get-started-with-adding-apps"></a>Začínáme s přidáváním aplikací

Intune podporuje různé způsoby nasazení aplikací na firemní zařízení:

* **Instalační programy softwaru**: Umožňují nahrát soubor, který se stáhne do zařízení uživatelů.
* __Externí odkazy__: Když máte aplikaci ve veřejném obchodě s aplikacemi nebo máte webovou aplikaci.
* **Spravované aplikace**: Pro zařízení s iOS, pokud potřebujete u mobilních aplikací, které jsou dostupné v App Storu, použít další správu.

Pojďme si projít jednu z rychlejších metod, kterou je nasazení aplikace tím, že ji přiřadíte z veřejného obchodu.

## <a name="how-do-i-assign-a-public-store-app"></a>Jak přiřadím aplikaci z veřejného obchodu?

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. V části **Hledat prostředky** vyhledejte **Intune**.
3. Vyberte **Mobilní aplikace** a pak vyberte **Aplikace**.
4. Vyberte **Přidat** a jako **Typ aplikace** v části **Aplikace pro Store** vyberte **iOS**.
5. Zvolte **Vybrat aplikaci**, aby se zobrazilo okno **Hledat v App Storu**.
6. V textovém poli najděte aplikaci, kterou chcete zařízení přiřadit. Zvolte aplikaci a klikněte na **Vybrat**.
7. V okně **Přidat aplikaci** vyberte **Informace o aplikaci** a vyplňte všechny informace o aplikaci. Můžete přidat i další podrobnosti užitečné pro zařazení aplikace, jako je **Vlastník**, **Poznámky**, **Vývojář** a **Adresa URL informací o ochraně osobních údajů** pro zásady ochrany osobních údajů používané vaší společností.
8. Nezapomeňte vybrat **Ano** u možnosti **Zobrazit na Portálu společnosti jako vybranou aplikaci** a pak vyberte **OK**.
9. V okně **Přidat aplikaci** vyberte **Přidat**, aby se daná aplikace přidala. Dostanete se do **přehledu** aplikace. Zvolte **Přiřazení**, klikněte na **Vybrat skupiny** a přiřaďte aplikaci testovací skupině. Dejte aplikaci **k dispozici** ke stažení. Pak by se aplikace na testovacím zařízení měla zobrazit jako **doporučená aplikace**.

## <a name="learn-more"></a>Další informace

* [Co je správa aplikací pomocí Intune?](app-management.md)
* [Přehled životního cyklu aplikace](app-lifecycle.md)
* [Co jsou zásady ochrany aplikací?](app-protection-policy.md)
