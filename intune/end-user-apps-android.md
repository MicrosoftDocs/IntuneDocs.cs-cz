---
title: Jak uživatelé s Androidem získávají svoje aplikace
description: Metody zpřístupnění aplikací pro Android koncovým uživatelům
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 960c440372613fed2c92ce00c604d97e1f122e8f
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2019
ms.locfileid: "71239824"
---
# <a name="how-your-android-users-get-their-apps"></a>Jak uživatelé s Androidem získávají svoje aplikace

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Tento článek vám pomůže pochopit, jak a kde koncoví uživatelé Androidu získávají aplikace, které distribuujete přes Microsoft Intune. Tyto informace se můžou lišit podle typu zařízení (nativního zařízení s Androidem nebo zařízení se Samsung Knox Standardem).

## <a name="native-non-samsung-knox-standard-android-devices"></a>Nativní zařízení s Androidem (bez Samsung Knox Standardu)

| Typ aplikace | Obchodní aplikace (LOB) | Aplikace obchodu Play  |
| ------------- |-------------| -----|
| Dostupné aplikace      | Uživatelé klepnou na **nainstalovat** na Portálu společnosti. Zobrazí se upozornění, na které pak uživatelé klepnou, aby spustili instalaci. Po úspěšné instalaci oznámení zmizí. | Uživatel klepne na aplikaci v Portál společnosti a přejde na stránku aplikace v Obchod Play. V takovém případě spustí instalaci.|
| Required apps      | Uživatelům se zobrazí oznámení, které nelze zavřít, což znamená, že musí nainstalovat aplikaci. Uživatelé klepnou na oznámení, aby spustili instalaci. Po úspěšné instalaci oznámení zmizí.    | Uživatelům se zobrazí oznámení, které nelze zavřít, což znamená, že musí nainstalovat aplikaci. Uživatel klepne na oznámení a přejde na stránku aplikace v Obchod Play. V takovém případě spustí instalaci. Po úspěšné instalaci oznámení zmizí. |

Koncoví uživatelé potřebují pro instalaci obchodních [aplikací](lob-apps-android.md)povolení instalace z neznámých zdrojů. Toto nastavení se obvykle nachází na dvou různých místech:

* **Android 7.1.2 a nižší**: **Nastavení** > zabezpečeníneznámé > **zdroje**
* **Android 8,0 a novější**: **Nastavení** > aplikace&oznámeníspeciálnípřístup > k aplikacím**instalovat neznámé aplikace**portál společnostiz > tohotozdrojepovolené >  > 

Aplikace Portál společnosti v takovém případě koncového uživatele informuje a navede ho na příslušné nastavení. 

## <a name="samsung-knox-standard-android-devices"></a>Zařízení Samsung Knox Standard s Androidem

| Typ aplikace | Obchodní aplikace (LOB) | Aplikace obchodu Play  |
| ------------- |-------------| -----|
| Dostupné aplikace      | Uživatelé klepnou na **nainstalovat** na Portálu společnosti. Aplikace se nainstaluje bez dalšího zásahu uživatele. | Uživatel klepne na aplikaci v Portál společnosti a přejde na stránku aplikace v Obchod Play. V takovém případě spustí instalaci.|
| Required apps      | Aplikace se nainstaluje bez zásahu uživatele.    | Uživatelům se zobrazí oznámení, které nelze zavřít, což znamená, že musí nainstalovat aplikaci. Uživatel klepne na oznámení a přejde na stránku aplikace v Obchod Play. V takovém případě spustí instalaci. Po úspěšné instalaci oznámení zmizí. |

Aplikace můžou být spravované nebo nespravované, jak je popsáno dál. Proces převedení aplikace na spravovanou je stejný pro všechny typy zařízení s Androidem.

**Spravované aplikace** – tyto aplikace se spravují pomocí zásad. Jsou "zabalené" službou Intune nebo sestavené pomocí sady Intune App SDK. Tyto aplikace je možné spravovat pomocí služby Intune a je na ně možné aplikovat zásady použití.

**Nespravované aplikace** – tyto aplikace se nespravují prostřednictvím zásad. Nejsou zabalené službou Intune nebo nezahrnují sadu Intune App SDK. Pro tyto aplikace nelze použít zásady použití.

## <a name="zebra-devices-with-zebra-mobility-extensions"></a>Zařízení Zebra s rozšířeními mobility Zebra

Intune používá k tiché instalaci aplikací na zařízeních Zebra spravovaných správcem zařízení sadu nástrojů MX (Zebra mobility Extension). Tato funkce umožňuje nasadit a aktualizovat aplikace na zařízeních Zebra bez zásahu uživatele. Pokud je verze MX v zařízení 4,2 nebo starší, aplikace se neinstalují tiše. Další informace najdete v části [plná matice funkcí MX](http://techdocs.zebra.com/mx/compatibility/) na webu zebra.

Obchodní aplikace nasazené do zařízení Zebra musí být nainstalované z veřejného umístění na zařízení. Balíček aplikace. apk může být přístupný pro jiné aplikace a služby, které mají také přístup k veřejnému úložišti na zařízení. Tento přístup je obvykle malé okno mezi dokončením stahování aplikace a na začátku instalace. Toto okno může být pro určitý časový útok možné. Například balíček. apk může být během tohoto okna změněn. Intune minimalizuje dobu, po kterou se. apk stráví ve veřejném úložišti, a nepovoluje instalaci nepodepsaných aplikací. Aby se minimalizovalo riziko zabezpečení, ujistěte se, že soubory. apk, které nahráváte, neobsahují citlivé informace.

## <a name="see-also"></a>Viz také:

[Přidávání aplikací s Microsoft Intune](apps-add.md)

[Jak uživatelé systému iOS získávají svoje aplikace](end-user-apps-ios.md)

[Jak uživatelé s Windows získávají svoje aplikace](end-user-apps-windows.md)
