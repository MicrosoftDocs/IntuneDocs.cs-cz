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
ms.sourcegitcommit: 52b9e786fe22b04081441db88a3629062fc85668
ms.openlocfilehash: a215d547507dcc460e83009cc6a04baf3fd8f4a4


---


# Jak uživatelé systému iOS získávají svoje aplikace

Tyto informace slouží k pochopení toho, jak a kde koncoví uživatelé získávají aplikace, které distribuujete pomocí Microsoft Intune.

**Požadované aplikace** – Aplikace, které jsou vyžadované správcem a které se instalují na zařízení s nutností minimálního zásahu ze strany uživatele (v závislosti na platformě).

**Dostupné aplikace** – Aplikace, které jsou k dispozici v seznamu aplikace Portál společnosti a které může uživatel nainstalovat volitelně.

**Spravované aplikace** – Aplikace, které jde spravovat pomocí zásad a které „zabalila“ služba Intune nebo které se sestavily pomocí sady Intune Mobile Application Management (MAM) Software Development Kit (SDK). Tyto aplikace je možné spravovat pomocí služby Intune a je na ně možné aplikovat zásady použití.

**Nespravované aplikace** – Aplikace, které jde spravovat pomocí zásad a které nejsou zabalené službou Intune nebo které nejsou sestavené pomocí sady Intune MAM SDK. Na tyto aplikace nejdou aplikovat zásady použití.

Omezení společnosti Apple zakazují, aby se obchodní a spravované aplikace z App Storu zobrazovaly v aplikaci Portál společnosti. Tento problém jsme vyřešili tak, že dlaždice aplikací v aplikaci Portál společnosti pro iOS odkazují uživatele u všech aplikací na různá zobrazení v jednom umístění (na webu Portál společnosti):

- Dlaždice **Firemní aplikace** dříve odkazovala na seznam všech aplikací na kartě VŠE na [webu Portál společnosti](http://portal.manage.microsoft.com) a bude tak fungovat i nadále. Název dlaždice byl změněn na **Všechny aplikace**.

- Dlaždice **Ostatní aplikace** dříve odkazovala v aplikaci Portál společnosti na zobrazení, ve kterém je uvedený seznam všech aplikací, které Apple aplikaci Portál společnosti povoluje zobrazit. Název dlaždice byl změněn na **Doporučené aplikace**. Po klepnutí na tuto dlaždici uživatelé přejdou na kartu DOPORUČENÉ na webu Portál společnosti.

-  Dlaždice **Kategorie** dříve odkazovala v aplikaci Portál společnosti na zobrazení, ve kterém je uvedený seznam kategorií aplikací. Název této dlaždice nebyl změněn, ale nyní na webu Portál společnosti odkazuje na kartu KATEGORIE.
Aktualizované snímky obrazovky najdete [tady](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).



###Související témata
[Jak uživatelé s Androidem získávají svoje aplikace](how-your-android-users-get-their-apps.md)</br>
[Jak uživatelé s Windows získávají svoje aplikace](how-your-windows-users-get-their-apps.md)



<!--HONumber=Sep16_HO3-->


