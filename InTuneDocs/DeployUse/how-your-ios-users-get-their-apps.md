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
ms.sourcegitcommit: 37841027c7ae040163440a19f9e163fb4eb87233
ms.openlocfilehash: ad780fb3403f6caaee1218d785a5cad326c18df5


---


# Jak uživatelé systému iOS získávají svoje aplikace

Tyto informace slouží k pochopení toho, jak a kde koncoví uživatelé získávají aplikace, které distribuujete pomocí Microsoft Intune.

**Požadované aplikace** – aplikace, které jsou vyžadované správcem a které se instalují na zařízení s nutností minimálního zásahu ze strany uživatele (v závislosti na platformě).

**Dostupné aplikace** – aplikace, které jsou v seznamu aplikace Portál společnosti a které si uživatel může volitelně nainstalovat.

**Spravované aplikace** – aplikace, které jde spravovat pomocí zásad a které jsou „zabalené“ službou Intune nebo sestavené pomocí sady Intune MAM (Mobile Application Management) SDK (Software Development Kit). Tyto aplikace je možné spravovat pomocí služby Intune a je na ně možné aplikovat zásady použití.

**Nespravované aplikace** – aplikace, které jde spravovat pomocí zásad a které nejsou zabalené službou Intune ani sestavené pomocí sady Intune MAM SDK. Na tyto aplikace nejdou aplikovat zásady použití.

Omezení společnosti Apple zakazují, aby se firemní a spravované aplikace z App Storu zobrazovaly v aplikaci Portál společnosti. Tento problém jsme obešli tak, že dlaždice v aplikaci Portál společnosti pro iOS odkazují uživatele u všech aplikací na různá zobrazení v jednom umístění (na webu Portál společnosti).

- **Firemní aplikace** dříve odkazovaly na seznam všech aplikací na kartě VŠE na [webu Portál společnosti](http://portal.manage.microsoft.com) a budou tak fungovat i dál. Název dlaždice byl změněn na **Všechny aplikace**.

- **Další aplikace** dříve odkazovaly na zobrazení v aplikaci Portál společnosti, ve kterém byl uvedený seznam všech aplikací, které Apple aplikaci Portál společnosti dovoluje zobrazit. Název dlaždice byl změněn na **Doporučené aplikace**. Po klepnutí na tuto dlaždici uživatelé přejdou na kartu DOPORUČENÉ na webu Portál společnosti.

-  **Kategorie** dříve odkazovaly na zobrazení v aplikaci Portál společnosti, ve kterém byl uvedený seznam kategorií aplikací. Název této dlaždice nebyl změněn, ale nyní odkazuje na kartu KATEGORIE na webu Portál společnosti.
Aktualizované snímky obrazovky najdete v článku [Vylepšení toho, jak koncoví uživatelé iOS získají svoje aplikace](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).



### Související témata
[Jak uživatelé s Androidem získávají svoje aplikace](how-your-android-users-get-their-apps.md)

[Jak uživatelé s Windows získávají svoje aplikace](how-your-windows-users-get-their-apps.md)



<!--HONumber=Oct16_HO2-->


