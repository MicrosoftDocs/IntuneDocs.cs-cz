---
title: "Jak uživatelé s Androidem získávají svoje aplikace"
description: "Metody zpřístupnění aplikací pro Android koncovým uživatelům"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4f0364750edf2e97e2b621c27fb25bea8e0f537c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="how-your-android-users-get-their-apps"></a>Jak uživatelé s Androidem získávají svoje aplikace

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Tyto informace slouží k pochopení toho, jak a kde koncoví uživatelé Androidu získávají aplikace, které distribuujete pomocí Microsoft Intune. Tyto informace se můžou lišit podle typu zařízení (nativního zařízení s Androidem nebo zařízení se Samsung Knox Standardem).

## <a name="native-non-samsung-knox-standard-android-devices"></a>Nativní zařízení s Androidem (bez Samsung Knox Standardu)

| Typ aplikace | Obchodní aplikace (LOB) | Aplikace obchodu Play  |
| ------------- |-------------| -----|
| Dostupné aplikace      | Uživatelé klepnou na **nainstalovat** na Portálu společnosti. Zobrazí se upozornění, na které pak uživatelé klepnou, aby spustili instalaci. Po úspěšné instalaci oznámení zmizí. | Uživatelé klepnou na aplikaci na Portálu společnosti a jsou přesměrováni na stránku aplikace v obchodě Play, kde můžou instalaci spustit.|
| Required apps      | Uživatelům se zobrazí oznámení, které nejde zrušit a které říká, že potřebují nainstalovat aplikaci. Uživatelé klepnou na oznámení, aby spustili instalaci. Po úspěšné instalaci oznámení zmizí.    | Uživatelům se zobrazí oznámení, které nejde zrušit a které říká, že potřebují nainstalovat aplikaci. Uživatelé klepnou na oznámení a jsou přesměrováni na stránku aplikace v obchodě Play, kde můžou instalaci spustit. Po úspěšné instalaci oznámení zmizí. |

## <a name="samsung-knox-standard-android-devices"></a>Zařízení Samsung Knox Standard s Androidem

| Typ aplikace | Obchodní aplikace (LOB) | Aplikace obchodu Play  |
| ------------- |-------------| -----|
| Dostupné aplikace      | Uživatelé klepnou na **nainstalovat** na Portálu společnosti. Aplikace se nainstaluje bez dalšího zásahu uživatele. | Uživatelé klepnou na aplikaci na Portálu společnosti a jsou přesměrováni na stránku aplikace v obchodě Play, kde můžou instalaci spustit.|
| Required apps      | Aplikace se nainstaluje bez zásahu uživatele.    | Uživatelům se zobrazí oznámení, které nejde zrušit a které říká, že potřebují nainstalovat aplikaci. Uživatelé klepnou na oznámení a jsou přesměrováni na stránku aplikace v obchodě Play, kde můžou instalaci spustit. Po úspěšné instalaci oznámení zmizí. |

Aplikace můžou být spravované nebo nespravované, jak je popsáno dál. Proces převedení aplikace na spravovanou je stejný pro všechny typy zařízení s Androidem.

**Spravované aplikace** – aplikace, které jde spravovat prostřednictvím zásad. Jsou „zabalené“ službou Intune nebo sestavené pomocí sady Intune MAM (Mobile Application Management) SDK (Software Development Kit). Tyto aplikace je možné spravovat pomocí služby Intune a je na ně možné aplikovat zásady použití.

**Nespravované aplikace** – aplikace, které nejde spravovat prostřednictvím zásad. Nejsou zabalené službou Intune ani sestavené pomocí sady Intune MAM SDK. Na tyto aplikace nejdou aplikovat zásady použití.

### <a name="see-also"></a>Související témata
[Přidávání aplikací s Microsoft Intune](apps-add.md)

[Jak uživatelé systému iOS získávají svoje aplikace](end-user-apps-ios.md)

[Jak uživatelé s Windows získávají svoje aplikace](end-user-apps-windows.md)