---
title: "Obnovení zařízení s iOSem spravovaných přes Intune ze zálohy | Dokumentace Microsoftu"
description: "Nabídněte koncovým uživatelům pokyny, jak svoje zařízení po obnovení ze zálohy znovu zaregistrují."
keywords: "obnovení, spravované, iOS"
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 2dd3844e83818f760df22fb748e74c8013ddd9cd
ms.lasthandoff: 12/10/2016


---

# <a name="restore-intune-managed-ios-devices-from-backup"></a>Obnovení zařízení s iOSem spravovaných přes Intune ze zálohy

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Občas budete vy nebo vaši uživatelé potřebovat obnovit zařízení s iOSem ze zálohy, třeba když uživatel dostane nové zařízení. Toto téma vysvětluje dodatečný postup, který budete muset udělat, abyste po obnovení zařízení nastavili správu přes Intune.

## <a name="restoring-backups-onto-the-same-device"></a>Obnovení záloh do stejného zařízení

Pokud zálohu obnovujete do stejného zařízení, obnoví se zároveň stav registrace tohoto zařízení. Nemusíte dělat nic dalšího.

## <a name="restoring-backups-onto-different-devices"></a>Obnovení záloh do jiných zařízení

Pokud zálohu obnovujete do jiného zařízení, neobnoví se v novém zařízení automaticky stav registrace. Uživatelé musí v aplikaci Portál společnosti verze 2.1.22 nebo novější standardním postupem [zaregistrovat své zařízení s iOSem do Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

> [!NOTE]
> Pokud na koncové uživatele uplatňujete zásady podmíněného přístupu, budou mít k firemnímu e-mailu přístup až po opětovné registraci.

> [!TIP]
> Tady je příklad sdělení pro vaše uživatele: Pokud chcete svoje nové zařízení zaregistrovat, ověřte, že používáte aplikaci Portál společnosti verze 2.1.22 nebo novější. Verzi zkontrolujete tak, že otevřete aplikaci Portál společnosti, klepnete na tlačítko Nabídka vpravo nahoře a pak klepnete na O produktu. Pokud používáte starší verzi, ukončete aplikaci Portál společnosti a otevřete App Store. Klepněte na tlačítko Aktualizace v pravém dolním rohu a pak klepněte na tlačítko Aktualizovat vedle položky Portál společnosti v seznamu. Po dokončení aktualizace spusťte aplikaci Portál společnosti a [zaregistrujte zařízení s iOSem do Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

## <a name="resolving-known-issues-with-restores"></a>Řešení známých problémů s obnovením

Uživatelé, kteří obnovili své zařízení a spustili aplikaci Portál společnosti ve verzi 2.1.21 nebo starší, mohou zaznamenat určité potíže. Tyto potíže vyřešíte tak, že provedete příslušné kroky, které odpovídají situaci uživatele.

### <a name="for-users-who-will-only-use-their-new-device"></a>Uživatelé, kteří budou požívat jenom nové zařízení
Spusťte aplikaci Portál společnosti a zrušte registraci tím, že vyberete dlaždici aktuálního zařízení a klepnete na tlačítko __Odebrat__. Po odebrání použijte standardní postup registrace k [zaregistrování zařízení s iOSem do Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

### <a name="for-users-who-will-use-both-their-old-and-new-devices"></a>Uživatelé, kteří budou používat staré i nové zařízení
Zrušte v Safari soubory cookie tím, že klepnete na __Nastavení__ > __Safari__ > __Smazat historii a data stránek__. Po vymazání odinstalujte aplikaci Portál společnosti a znovu ji nainstalujte. Pak použijte standardní postup registrace k [zaregistrování zařízení s iOSem do Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

