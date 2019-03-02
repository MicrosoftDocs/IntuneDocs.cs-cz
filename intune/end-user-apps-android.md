---
title: Jak uživatelé s Androidem získávají svoje aplikace
description: Metody zpřístupnění aplikací pro Android koncovým uživatelům
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/21/2017
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: df2e426120740c13673d053a430181040e19ac78
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238740"
---
# <a name="how-your-android-users-get-their-apps"></a>Jak uživatelé s Androidem získávají svoje aplikace

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Tyto informace slouží k pochopení toho, jak a kde koncoví uživatelé Androidu získávají aplikace, které distribuujete pomocí Microsoft Intune. Tyto informace se můžou lišit podle typu zařízení (nativního zařízení s Androidem nebo zařízení se Samsung Knox Standardem).

## <a name="native-non-samsung-knox-standard-android-devices"></a>Nativní zařízení s Androidem (bez Samsung Knox Standardu)

| Typ aplikace | Obchodní aplikace (LOB) | Aplikace obchodu Play  |
| ------------- |-------------| -----|
| Dostupné aplikace      | Uživatelé klepnou na **nainstalovat** na Portálu společnosti. Zobrazí se upozornění, na které pak uživatelé klepnou, aby spustili instalaci. Po úspěšné instalaci oznámení zmizí. | Uživatelé klepnou na aplikaci na Portálu společnosti a jsou přesměrováni na stránku aplikace v obchodě Play, kde můžou instalaci spustit.|
| Required apps      | Uživatelům se zobrazí oznámení, které nejde zrušit a které říká, že potřebují nainstalovat aplikaci. Uživatelé klepnou na oznámení, aby spustili instalaci. Po úspěšné instalaci oznámení zmizí.    | Uživatelům se zobrazí oznámení, které nejde zrušit a které říká, že potřebují nainstalovat aplikaci. Uživatelé klepnou na oznámení a jsou přesměrováni na stránku aplikace v obchodě Play, kde můžou instalaci spustit. Po úspěšné instalaci oznámení zmizí. |

Aby si koncoví uživatelé mohli nainstalovat [obchodní aplikace](lob-apps-android.md), musí povolit instalaci z neznámých zdrojů. Toto nastavení se normálně nachází na dvou různých místech:

* **Android 7.1.2 a starší**: **Nastavení** > **zabezpečení** > **neznámé zdroje**
* **Android 8.0 a novější**: **Nastavení** > **aplikace a oznámení** > **přístup speciálních aplikací** > **instalace neznámých aplikací**  >  **Portál společnosti** > **povolit z tohoto zdroje**

Aplikace Portál společnosti v takovém případě koncového uživatele informuje a navede ho na příslušné nastavení. 


## <a name="samsung-knox-standard-android-devices"></a>Zařízení Samsung Knox Standard s Androidem

| Typ aplikace | Obchodní aplikace (LOB) | Aplikace obchodu Play  |
| ------------- |-------------| -----|
| Dostupné aplikace      | Uživatelé klepnou na **nainstalovat** na Portálu společnosti. Aplikace se nainstaluje bez dalšího zásahu uživatele. | Uživatelé klepnou na aplikaci na Portálu společnosti a jsou přesměrováni na stránku aplikace v obchodě Play, kde můžou instalaci spustit.|
| Required apps      | Aplikace se nainstaluje bez zásahu uživatele.    | Uživatelům se zobrazí oznámení, které nejde zrušit a které říká, že potřebují nainstalovat aplikaci. Uživatelé klepnou na oznámení a jsou přesměrováni na stránku aplikace v obchodě Play, kde můžou instalaci spustit. Po úspěšné instalaci oznámení zmizí. |

Aplikace můžou být spravované nebo nespravované, jak je popsáno dál. Proces převedení aplikace na spravovanou je stejný pro všechny typy zařízení s Androidem.

**Spravované aplikace** – aplikace, které jde spravovat prostřednictvím zásad. Jsou „zabalené“ službou Intune nebo sestavené pomocí sady Intune App SDK. Tyto aplikace je možné spravovat pomocí služby Intune a je na ně možné aplikovat zásady použití.

**Nespravované aplikace** – aplikace, které nejde spravovat prostřednictvím zásad. Nejsou zabalené službou Intune ani sestavené pomocí sady Intune App SDK. Na tyto aplikace nejdou aplikovat zásady použití.

### <a name="see-also"></a>Viz také:
[Přidávání aplikací s Microsoft Intune](apps-add.md)

[Jak uživatelé systému iOS získávají svoje aplikace](end-user-apps-ios.md)

[Jak uživatelé s Windows získávají svoje aplikace](end-user-apps-windows.md)
