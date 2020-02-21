---
title: Jak uživatelé iOS/iPadOS získávají své aplikace
description: Metody zpřístupnění aplikací pro iOS/iPadOS koncovým uživatelům
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 344c2e3f3ed53852aa6b749c9ebf6d451dd313ff
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514383"
---
# <a name="how-your-iosipados-users-get-their-apps"></a>Jak uživatelé iOS/iPadOS získávají své aplikace

Tyto informace slouží k pochopení toho, jak a kde koncoví uživatelé získávají aplikace, které distribuujete pomocí Microsoft Intune.

**Požadované aplikace** – aplikace, které jsou vyžadované správcem a které se instalují na zařízení s nutností minimálního zásahu ze strany uživatele (v závislosti na platformě).

**Dostupné aplikace** – aplikace, které jsou v seznamu aplikace Portál společnosti a které si uživatel může volitelně nainstalovat.

**Spravované aplikace** – aplikace, které jde spravovat pomocí zásad a které jsou „zabalené“ službou Intune nebo sestavené pomocí sady Intune App SDK. Tyto aplikace je možné spravovat pomocí služby Intune a je na ně možné aplikovat zásady ochrany aplikací.

**Nespravované aplikace**– aplikace, které uživatelé můžou stahovat z App Storu pro iOS/iPadOS, které nejsou integrované se sadou Intune App SDK. Intune nemá žádnou kontrolu nad distribucí, správou nebo selektivním vymazáním těchto aplikací.  

Omezení společnosti Apple zakazují, aby se firemní a spravované aplikace z App Storu zobrazovaly v aplikaci Portál společnosti. Chcete-li se tomuto problému vyhnout, dlaždice v aplikaci Portál společnosti pro iOS/iPadOS ukazují uživatele do různých zobrazení v jednom umístění (Portál společnosti webu) pro všechny své aplikace.

Zaregistrovaní uživatelé můžou používat aplikace po klepnutí na následující dlaždice na obrazovce Aplikace v aplikaci Portál společnosti:

- **Všechny aplikace** zobrazí seznam všech aplikací na kartě VŠE na [webu Portál společnosti](https://portal.manage.microsoft.com).

- Po klepnutí na **Vybrané aplikace** se uživatelům zobrazí na webu Portál společnosti karta VYBRANÉ.

- **Kategorie** odkazují na webu Portál společnosti na kartu KATEGORIE.

![Obrazovka aplikací na Portálu společnosti pro iOS](./media/end-user-apps-ios/ios-cp-app-main-apps-screen.png)

Další informace o přidávání aplikací najdete v článku [Přidání aplikací do Microsoft Intune](../apps/apps-add.md).

## <a name="see-also"></a>Viz také

[Jak uživatelé s Androidem získávají svoje aplikace](end-user-apps-android.md)

[Jak uživatelé s Windows získávají svoje aplikace](end-user-apps-windows.md)
