---
title: "Jak ověřit nastavení MAM | Dokumentace Microsoftu"
description: "V tématu popisujeme, jak otestovat a ověřit, jestli jste správně nastavili zásady MAM a ty fungují podle očekávání."
keywords: 
author: andredm7
ms.author: andredm
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ms.reviewer: joglocke
translationtype: Human Translation
ms.sourcegitcommit: d6ff74f0b46baf384dbdedf13ad75538dd33a089
ms.openlocfilehash: 080d8f4fd4b6e1b53df860f4319b1c199d504c06


---

# <a name="validating-your-mobile-application-management-setup"></a>Jak ověřit nastavení správy mobilních aplikací

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Toto téma obsahuje informace o tom, jak zkontrolovat, jestli vám správa mobilních aplikací (MAM) funguje bez problémů. Návod se vztahuje k zásadám MAM na webu Azure Portal.

### <a name="checking-for-symptoms"></a>Zjišťování příznaků
Není pravděpodobné, že by problém nahlásili uživatelé, protože MAM je nástroj na ochranu dat. Pokud je s konfigurací MAM nějaký problém, uživatelé budou mít stejně neomezený přístup jako bez MAM a potíží si nevšimnou. Proto doporučujeme, abyste konfiguraci MAM prověřili s malou skupinou uživatelů, kteří mohou omezení MAM cíleně vyzkoušet.


### <a name="what-to-check"></a>Co zkontrolovat

Pokud testování odhalí, že zásady MAM nepřináší očekávané výsledky, doporučujeme zkontrolovat následující:

- Mají uživatelé licenci k MAM?
- Mají uživatelé licenci k O365?
- Stav všech aplikací MAM každého uživatele. Aplikace můžou být ve stavu **Zaregistrováno** a **Není zaregistrováno**.

#### <a name="user-mam-status"></a>Stav uživatele v rámci MAM
1. Na webu Azure Portal vyberte možnost **Správa mobilních aplikací Intune** > **Nastavení** > **Správa aplikací** > **Všechna nastavení** > **Vytváření sestav aplikace uživatelem** > **Uživatelé**.

2. Vyberte uživatele ze seznamu nebo ho vyhledejte, pak vyberte a klikněte na **Vybrat uživatele**. V horní části sloupce **Sestavy aplikace** uvidíte, jestli má uživatel licenci k MAM. Níže se zobrazí, jestli má licenci k O365 a jaký je stav aplikace na všech jeho zařízeních.

![Stav aplikace v rámci MAM](..\media\ts-mam-user-apps.png)

### <a name="what-to-do"></a>Co dělat
Postupujte podle stavu uživatele:

- Pokud uživatel nemá licenci k MAM, přiřaďte mu licenci Intune, jak je popsáno v tématu [Správa licencí Intune](..\get-started\start-with-a-paid-subscription-to-microsoft-intune.md).
- Pokud uživatel nemá licenci k O365, získejte ji pro něj.
- Pokud je uživatelova aplikace uvedena ve stavu **Není zaregistrováno**, zkontrolujte, jestli jste, co se této aplikace týče, správně nakonfigurovali zásady MAM.
- Dejte pozor, aby se uvedené nastavení použilo pro všechny uživatele, u kterých chcete zásady MAM uplatnit.

### <a name="see-also"></a>Související témata
[Příprava před konfigurací zásad správy mobilních aplikací pomocí Microsoft Intune](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

[Ochrana aplikačních dat pomocí zásad správy mobilních aplikací v Microsoft Intune](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


