---
title: "Jak uživatelé s Androidem získávají svoje apikace| Microsoft Intune"
description: "Metody zpřístupnění aplikací pro Android koncovým uživatelům"
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 7/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 627914b2ac877c1b5ff5bc95f7f2098ab8988250
ms.openlocfilehash: 98e712fb852c89c1d092b87482f30ada33010a33


---


# Jak uživatelé s Androidem získávají svoje aplikace
Tyto informace slouží k pochopení toho, jak a kde koncoví uživatelé Androidu získávají aplikace, které distribuujete pomocí Microsoft Intune. Tyto informace se můžou lišit podle typu zařízení (nativního zařízení s Androidem nebo zařízení Samsung Knox).

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

**Spravované aplikace** – aplikace, které jde spravovat prostřednictvím zásad. Jsou „zabalené“ službou Intune nebo sestavené pomocí sady Intune MAM (Mobile Application Management) SDK (Software Development Kit). Tyto aplikace je možné spravovat pomocí služby Intune a je na ně možné aplikovat zásady použití.

**Nespravované aplikace** – aplikace, které nejde spravovat prostřednictvím zásad. Nejsou zabalené službou Intune ani sestavené pomocí sady Intune MAM SDK. Na tyto aplikace nejdou aplikovat zásady použití.

### Viz taky
[Přidávání aplikací s Microsoft Intune](/intune/deploy-use/add-apps)

[Jak uživatelé systému iOS získávají svoje aplikace](how-your-ios-users-get-their-apps.md)

[Jak uživatelé s Windows získávají svoje aplikace](how-your-windows-users-get-their-apps.md)



<!--HONumber=Oct16_HO2-->


