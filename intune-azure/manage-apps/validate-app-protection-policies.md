---
title: "Ověření zásad ochrany aplikací"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: V tématu popisujeme, jak otestovat a ověřit, zda jste správně nastavili zásady ochrany aplikací a zda fungují, jak mají."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angerobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 086ea61de3423be254d3d8f2224c4ad96d90385d
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-validate-your-app-protection-policy-setup"></a>Ověření nastavení zásad ochrany aplikací

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Toto téma obsahuje informace o tom, jak zkontrolovat, jestli vám zásady ochrany aplikací fungují bez problémů. Tento návod se vztahuje k zásadám ochrany aplikací na portálu Azure Portal **Preview**.

### <a name="checking-for-symptoms"></a>Zjišťování příznaků
Není pravděpodobné, že by problém nahlásili uživatelé, protože ochrana aplikací je nástroj na ochranu dat. Pokud je s konfigurací ochrany aplikací nějaký problém, uživatelé budou mít stejně neomezený přístup jako bez ochrany aplikací a potíží si nevšimnou. Proto doporučujeme, abyste konfiguraci ochrany aplikací prověřili s malou skupinou uživatelů, kteří mohou omezení ochrany aplikací cíleně vyzkoušet.


### <a name="what-to-check"></a>Co zkontrolovat

Pokud testování odhalí, že zásady ochrany aplikací nepřináší očekávané výsledky, doporučujeme zkontrolovat následující:

- Mají uživatelé licenci k ochraně aplikací?
- Mají uživatelé licenci k O365?
- Stav všech aplikací ochrany aplikací jednotlivých uživatelů. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**.

#### <a name="user-app-protection-status"></a>Stav uživatele ochrany aplikací
1. Na portálu Azure Portal zvolte **Spravovat aplikace** > **Monitorovat** >  **Stav uživatele ochrany aplikací** > **uživatelé**.

2. Vyberte uživatele ze seznamu nebo ho vyhledejte, pak vyberte a klikněte na **Vybrat uživatele**. V horní části sloupce **Vytváření sestav aplikace** uvidíte, jestli má uživatel licenci k ochraně aplikací. Níže se zobrazí, jestli má licenci k O365 a jaký je stav aplikace na všech jeho zařízeních.



### <a name="what-to-do"></a>Co dělat
Postupujte podle stavu uživatele:

- Pokud uživatel licenci k ochraně aplikací nemá, přiřaďte mu licenci k Intune.
- Pokud uživatel nemá licenci k O365, získejte ji pro něj.
- Pokud je aplikace uživatele uvedená ve stavu **Není zaregistrováno**, zkontrolujte, jestli jste pro danou aplikaci správně nakonfigurovali zásady ochrany aplikací.
- Dejte pozor, aby se uvedené nastavení použilo pro všechny uživatele, u kterých chcete zásady ochrany aplikací uplatnit.

### <a name="see-also"></a>Související témata

[Co jsou zásady ochrany aplikací Intune?](app-protection-policies.md)
