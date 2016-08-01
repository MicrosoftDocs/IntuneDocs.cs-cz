---
title: "Jak uživatelé s Androidem získávají svoje apikace| Microsoft Intune"
description: "Metody zpřístupnění aplikací pro Android koncovým uživatelům"
keywords: 
author: Staciebarker
manager: arob98
ms.date: 7/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: 43b7eb3378d9977b9d19196c91a812d9411752b9


---


# Jak uživatelé s Androidem získávají svoje aplikace
Tyto informace slouží k pochopení toho, jak a kde koncoví uživatelé Androidu získávají aplikace, které distribuujete pomocí Microsoft Intune. Informace pro nativní zařízení s Androidem se oproti zařízení Samsung Knox mohou lišit.

## Nativní zařízení s Androidem (ne Samsung Knox)

| Typ aplikace | Obchodní aplikace (LOB) | Aplikace obchodu Play  |
| ------------- |-------------| -----|
| Dostupné aplikace      | Uživatelé klepnou na **nainstalovat** na Portálu společnosti. Zobrazí se upozornění, na které pak uživatelé klepnou, aby spustili instalaci. Po úspěšné instalaci oznámení zmizí. | Uživatelé klepnou na aplikaci na Portálu společnosti a jsou přesměrováni na stránku aplikace v obchodě Play, kde můžou instalaci spustit.|
| Required apps      | Uživatelům se zobrazí oznámení, které nejde zrušit a které říká, že potřebují nainstalovat aplikaci. Uživatelé klepnou na oznámení, aby spustili instalaci. Po úspěšné instalaci oznámení zmizí.    | Uživatelům se zobrazí oznámení, které nejde zrušit a které říká, že potřebují nainstalovat aplikaci. Uživatelé klepnou na oznámení a jsou přesměrováni na stránku aplikace v obchodě Play, kde můžou instalaci spustit. Po úspěšné instalaci oznámení zmizí. |

## Zařízení s Androidem Samsung Knox

| Typ aplikace | Obchodní aplikace (LOB) | Aplikace obchodu Play  |
| ------------- |-------------| -----|
| Dostupné aplikace      | Uživatelé klepnou na **nainstalovat** na Portálu společnosti. Aplikace se nainstaluje bez dalšího zásahu uživatele. | Uživatelé klepnou na aplikaci na Portálu společnosti a jsou přesměrováni na stránku aplikace v obchodě Play, kde můžou instalaci spustit.|
| Required apps      | Aplikace se nainstaluje bez zásahu uživatele.    | Uživatelům se zobrazí oznámení, které nejde zrušit a které říká, že potřebují nainstalovat aplikaci. Uživatelé klepnou na oznámení a jsou přesměrováni na stránku aplikace v obchodě Play, kde můžou instalaci spustit. Po úspěšné instalaci oznámení zmizí. |

Aplikace můžou být spravované nebo nespravované, jak je popsáno dál. Proces převedení aplikace na spravovanou je stejný pro všechny typy zařízení s Androidem.

**Spravované aplikace** – Aplikace, které jde spravovat pomocí zásad a které „zabalila“ služba Intune nebo které se sestavily pomocí sady Intune Mobile Application Management (MAM) Software Development Kit (SDK). Tyto aplikace je možné spravovat pomocí služby Intune a je na ně možné aplikovat zásady použití.

**Nespravované aplikace** – Aplikace, které jde spravovat pomocí zásad a které nejsou zabalené službou Intune nebo které nejsou sestavené pomocí sady Intune MAM SDK. Na tyto aplikace nejdou aplikovat zásady použití.

### Související témata
[Přidávání aplikací s Microsoft Intune](/intune/deploy-use/add-apps)
[Jak uživatelé systému iOS získají svoje aplikace](how-your-ios-users-get-their-apps.md)
[Jak uživatelé s Windows získávají svoje aplikace](how-your-windows-users-get-their-apps.md)



<!--HONumber=Jul16_HO3-->


