---
title: "Jak uživatelé systému iOS získávají svoje apikace| Microsoft Intune"
description: "Metody zpřístupnění aplikací pro iOS koncovým uživatelům"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 3ba0a5cda91164761c4576df935c54390bc78f8c


---


# <a name="how-your-ios-users-get-their-apps"></a>Jak uživatelé systému iOS získávají svoje aplikace

Tyto informace slouží k pochopení toho, jak a kde koncoví uživatelé získávají aplikace, které distribuujete pomocí Microsoft Intune.

**Požadované aplikace** – aplikace, které jsou vyžadované správcem a které se instalují na zařízení s nutností minimálního zásahu ze strany uživatele (v závislosti na platformě).

**Dostupné aplikace** – aplikace, které jsou v seznamu aplikace Portál společnosti a které si uživatel může volitelně nainstalovat.

**Spravované aplikace** – aplikace, které jde spravovat pomocí zásad a které jsou „zabalené“ službou Intune nebo sestavené pomocí sady Intune MAM (Mobile Application Management) SDK (Software Development Kit). Tyto aplikace je možné spravovat pomocí služby Intune a je na ně možné aplikovat zásady použití.

**Nespravované aplikace** – aplikace, které jde spravovat pomocí zásad a které nejsou zabalené službou Intune ani sestavené pomocí sady Intune MAM SDK. Na tyto aplikace nejdou aplikovat zásady použití.

Omezení společnosti Apple zakazují, aby se firemní a spravované aplikace z App Storu zobrazovaly v aplikaci Portál společnosti. Tento problém jsme obešli tak, že dlaždice v aplikaci Portál společnosti pro iOS odkazují uživatele u všech aplikací na různá zobrazení v jednom umístění (na webu Portál společnosti).

Zaregistrovaní uživatelé můžou používat aplikace po klepnutí na následující dlaždice na obrazovce Aplikace v aplikaci Portál společnosti:

- **Všechny aplikace** zobrazí seznam všech aplikací na kartě VŠE na [webu Portál společnosti](http://portal.manage.microsoft.com).

- Po klepnutí na **Vybrané aplikace** se uživatelům zobrazí na webu Portál společnosti karta VYBRANÉ.

- **Kategorie** odkazují na webu Portál společnosti na kartu KATEGORIE.

 
![Obrazovka aplikací na Portálu společnosti pro iOS](./media/ios-cp-app-main-apps-screen.png)

Informace o tom, jak přidat aplikace a umístit je do těchto dlaždic, najdete v tématu [Přidávání aplikací pro zaregistrovaná zařízení do Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md).

### <a name="see-also"></a>Související témata
[Jak uživatelé s Androidem získávají svoje aplikace](how-your-android-users-get-their-apps.md)

[Jak uživatelé s Windows získávají svoje aplikace](how-your-windows-users-get-their-apps.md)



<!--HONumber=Nov16_HO1-->


