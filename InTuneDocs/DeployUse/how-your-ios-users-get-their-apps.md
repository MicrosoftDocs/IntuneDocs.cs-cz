---
title: "Jak uživatelé systému iOS získávají svoje apikace| Microsoft Intune"
description: "Metody zpřístupnění aplikací pro iOS koncovým uživatelům"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9f1946c02c6267a22844106e8f72555ec5e9cabb
ms.openlocfilehash: 212dcd31697180dae61569dda13b56704a079bf4


---


# Jak uživatelé systému iOS získávají svoje aplikace

Tyto informace slouží k pochopení toho, jak a kde koncoví uživatelé získávají aplikace, které distribuujete pomocí Microsoft Intune.

**Požadované aplikace** – Aplikace, které jsou vyžadované správcem a které se instalují na zařízení s nutností minimálního zásahu ze strany uživatele (v závislosti na platformě).

**Dostupné aplikace** – Aplikace, které jsou k dispozici v seznamu aplikace Portál společnosti a které může uživatel nainstalovat volitelně.

**Spravované aplikace** – Aplikace, které jde spravovat pomocí zásad a které „zabalila“ služba Intune nebo které se sestavily pomocí sady Intune Mobile Application Management (MAM) Software Development Kit (SDK). Tyto aplikace je možné spravovat pomocí služby Intune a je na ně možné aplikovat zásady použití.

**Nespravované aplikace** – Aplikace, které jde spravovat pomocí zásad a které nejsou zabalené službou Intune nebo které nejsou sestavené pomocí sady Intune MAM SDK. Na tyto aplikace nejdou aplikovat zásady použití.

Apple zakazuje, aby se obchodní a spravované aplikace z App Storu zobrazovaly v aplikaci Portál společnosti. Uživatel tak k vyhledání všech svých aplikací musí použít několik zobrazení. Aplikace pro jednotlivé dlaždice zobrazené na stránce Aplikace v aplikaci Portál společnosti jsou dostupné takto:

- Dlaždice **Firemní aplikace** odkazuje na seznam všech aplikací na kartě **VŠE** na [webu Portál společnosti](http://portal.manage.microsoft.com).

- Dlaždice **Ostatní aplikace** v současnosti odkazuje v aplikaci Portál společnosti na zobrazení, ve kterém je uvedený seznam všech aplikací, které Apple aplikaci Portál společnosti povoluje zobrazit. Tento seznam zahrnuje všechny aplikace s výjimkou obchodních aplikací a spravovaných aplikací z App Storu.

- Dlaždice **Kategorie** v současnosti odkazuje v aplikaci Portál společnosti na zobrazení, ve kterém je uvedený seznam kategorií aplikací.

    ![ios-how-to-sync-device-with-intune](./media/ios-sync-comp-portal-apps.png)


###Související témata
[Jak uživatelé s Androidem získávají svoje aplikace](how-your-android-users-get-their-apps.md)</br>
[Jak uživatelé s Windows získávají svoje aplikace](how-your-windows-users-get-their-apps.md)



<!--HONumber=Aug16_HO4-->


