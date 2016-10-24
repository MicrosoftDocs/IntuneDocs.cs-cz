---
title:
- "Jak ověřit nastavení MAM | Microsoft Intune"
description: "V tématu popisujeme, jak otestovat a ověřit, jestli jste správně nastavili zásady MAM a ty fungují podle očekávání."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angerobe
ms.date: 08/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ms.reviewer: joglocke
translationtype: Human Translation
ms.sourcegitcommit: 0736b5f24065f55d8fbd312395e4bb7226ebf619
ms.openlocfilehash: 5b6253d3d4c969b6947d83b5c8695a484f8c1d27


---

# Jak ověřit nastavení správy mobilních aplikací

Toto téma obsahuje informace o tom, jak zkontrolovat, jestli vám správa mobilních aplikací (MAM) funguje bez problémů. Návod se vztahuje k zásadám MAM na webu Azure Portal.

### Zjišťování příznaků
Není pravděpodobné, že by problém nahlásili uživatelé, protože MAM je nástroj na ochranu dat. Pokud je s konfigurací MAM nějaký problém, uživatelé budou mít stejně neomezený přístup jako bez MAM a potíží si nevšimnou. Proto doporučujeme, abyste konfiguraci MAM prověřili s malou skupinou uživatelů, kteří mohou omezení MAM cíleně vyzkoušet.


### Co zkontrolovat

Pokud testování odhalí, že zásady MAM nepřináší očekávané výsledky, doporučujeme zkontrolovat následující:

- Mají uživatelé licenci k MAM?
- Mají uživatelé licenci k O365?
- Stav všech aplikací MAM každého uživatele. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**.

#### Stav uživatele v rámci MAM
1. Na webu Azure Portal vyberte možnost **Správa mobilních aplikací Intune** > **Nastavení** > **Správa aplikací** > **Všechna nastavení** > **Vytváření sestav aplikace uživatelem** > **Uživatelé**.

2. Vyberte uživatele ze seznamu nebo ho vyhledejte, pak vyberte a klikněte na **Vybrat uživatele**. V horní části sloupce **Sestavy aplikace** uvidíte, jestli má uživatel licenci k MAM. Níže se zobrazí, jestli má licenci k O365 a jaký je stav aplikace na všech jeho zařízeních.

![Stav aplikace v rámci MAM](..\media\ts-mam-user-apps.png) 

### Co dělat
Postupujte podle stavu uživatele:

- Pokud uživatel nemá licenci k MAM, přiřaďte mu licenci Intune, jak je popsáno v tématu [Správa licencí Intune](..\get-started\start-with-a-paid-subscription-to-microsoft-intune).
- Pokud uživatel nemá licenci k O365, získejte ji pro něj.
- Pokud je uživatelova aplikace uvedena ve stavu **Není zaregistrováno**, zkontrolujte, jestli jste, co se této aplikace týče, správně nakonfigurovali zásady MAM.
- Dejte pozor, aby se uvedené nastavení použilo pro všechny uživatele, u kterých chcete zásady MAM uplatnit.

### Související témata
[Příprava před konfigurací zásad správy mobilních aplikací pomocí Microsoft Intune](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

[Ochrana aplikačních dat pomocí zásad správy mobilních aplikací v Microsoft Intune](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)



<!--HONumber=Oct16_HO1-->


