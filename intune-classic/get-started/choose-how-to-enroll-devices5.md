---
title: Volba způsobu registrace mobilních zařízení
description: Volba způsobu registrace mobilních zařízení v Intune zodpovězením několik jednoduchých dotazů
keywords: ''
author: NathBarn
ms.author: nathbarn
manager: dougeby
ms.date: 03/27/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ed9250aa-e894-4eac-92b8-5f1a3748e255
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.openlocfilehash: c9744358afca288978e14b4ec9967a52100076f1
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="choose-how-to-enroll-mobile-devices"></a>Volba způsobu registrace mobilních zařízení

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vaše odpovědi na tuto řadu otázek vám pomohou určit nejlepší metody registrace zařízení, která spravujete.

## <a name="how-will-you-manage-shared-ios-devices"></a>**Jak budete spravovat sdílená zařízení s iOSem?**

> [!div class="button"]
[Registrace DEP pro iOS >](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
> [!div class="button"]
[Přímá registrace pro iOS >](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
> [!div class="button"]
[Registrace DEM >](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Program DEP (Device Enrollment Program) společnosti Apple:** Na zakoupená nebo spravovaná zařízení iOS je možné cílit s profilem registrace. Když uživatelé zařízení poprvé zapnou, zařízení stáhne profil DEP a zaregistruje se s ním.

  - **Apple Configurator na Macu:** Apple Configurator je aplikace Apple, která běží na počítačích Mac. Zařízení s iOSem můžete připojit k počítači Mac kabelem USB a nainstalovat na ně profil registrace. Pokud je to možné, obnovte zařízení do továrního nastavení a zaregistrujte ho pomocí Pomocníka s nastavením. Pokud zařízení nechcete obnovit do továrního nastavení, použijte tzv. přímou registraci.

  - **Správce registrace zařízení:** Správce registrace zařízení (DEM) služby Intune umožňuje, aby manažer nebo správce zaregistroval mnoho mobilních zařízení s jedním uživatelským účtem. Tato zařízení nemohou mít přidružení uživatele (to znamená vyhrazené uživatele) a musí se registrovat instalací a přihlášením pomocí aplikace Portál společnosti.

> [!div class="button"]
[< Zpět](choose-how-to-enroll-devices3.md)
