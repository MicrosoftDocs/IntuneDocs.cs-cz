---
title: "Jak uživatelé s Androidem získávají svoje apikace| Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d3bcf89636f9da8fd8bfa5cc52391742a9ce9f92
ms.openlocfilehash: 25571ce1b214c927f3dc2ea3968d00970621e474


---


# Jak uživatelé s Androidem získávají svoje aplikace
Tyto informace slouží k pochopení toho, jak a kde koncoví uživatelé získávají aplikace, které distribuujete pomocí Microsoft Intune. 

**Požadované aplikace** – Aplikace, které jsou vyžadované správcem a které se instalují na zařízení s nutností minimálního zásahu ze strany uživatele (v závislosti na platformě).
 
- **Zařízení Samsung Knox**: Pokud nasadíte požadovanou aplikaci v zařízeních Samsung Knox, nainstaluje se do zařízení automaticky a bezobslužně.
- **Nativní zařízení (jiná než Samsung Knox**: Pokud nasadíte požadovanou aplikaci v jiných zařízeních než Samsung Knox, nenainstaluje se do zařízení uživatelů automaticky. Místo toho jsou uživatelé vyzváni k instalaci aplikace. Po přijetí výzvy se aplikace stáhne a uživatelé pak obdrží oznámení s informací, že musí aplikaci nainstalovat. 

**Dostupné aplikace** – Aplikace, které jsou k dispozici v seznamu aplikace Portál společnosti a které může uživatel nainstalovat volitelně.

**Spravované aplikace** – Aplikace, které jde spravovat pomocí zásad a které „zabalila“ služba Intune nebo které se sestavily pomocí sady Intune Mobile Application Management (MAM) Software Development Kit (SDK). Tyto aplikace je možné spravovat pomocí služby Intune a je na ně možné aplikovat zásady použití.

**Nespravované aplikace** – Aplikace, které jde spravovat pomocí zásad a které nejsou zabalené službou Intune nebo které nejsou sestavené pomocí sady Intune MAM SDK. Na tyto aplikace nejdou aplikovat zásady použití.

###Související témata
[Přidávání aplikací s Microsoft Intune](/intune/deploy-use/add-apps)
[Jak uživatelé systému iOS získají svoje aplikace](how-your-ios-users-get-their-apps.md)
[Jak uživatelé s Windows získávají svoje aplikace](how-your-windows-users-get-their-apps.md)


<!--HONumber=Jul16_HO1-->


