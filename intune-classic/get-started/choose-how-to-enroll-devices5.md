---
title: "Volba způsobu registrace mobilních zařízení | Dokumentace Microsoftu"
description: "Volba způsobu registrace mobilních zařízení v Intune zodpovězením několik jednoduchých dotazů"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed9250aa-e894-4eac-92b8-5f1a3748e255
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 64f8a051cfa873df034e3d260862181ce637948c
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---
# <a name="choose-how-to-enroll-mobile-devices"></a>Volba způsobu registrace mobilních zařízení

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vaše odpovědi na tuto řadu otázek vám pomohou určit nejlepší metody registrace zařízení, která spravujete.

## <a name="how-will-you-manage-shared-ios-devices"></a>**Jak budete spravovat sdílená zařízení s iOSem?**

> [!div class="button"]
[Registrace DEP pro iOS >]/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [!div class="button"]
> [Přímá registrace pro iOS >]/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune) [!div class="button"]
[Registrace DEM >]/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Program DEP (Device Enrollment Program) společnosti Apple:** Na zakoupená nebo spravovaná zařízení iOS je možné cílit s profilem registrace. Když uživatelé zařízení poprvé zapnou, zařízení stáhne profil DEP a zaregistruje se s ním.

  - **Apple Configurator na Macu:** Apple Configurator je aplikace Apple, která běží na počítačích Mac. Zařízení s iOSem můžete připojit k počítači Mac kabelem USB a nainstalovat na ně profil registrace. Pokud je to možné, obnovte zařízení do továrního nastavení a zaregistrujte ho pomocí Pomocníka s nastavením. Pokud zařízení nechcete obnovit do továrního nastavení, použijte tzv. přímou registraci.

  - **Správce registrace zařízení:** Správce registrace zařízení (DEM) služby Intune umožňuje, aby manažer nebo správce zaregistroval mnoho mobilních zařízení s jedním uživatelským účtem. Tato zařízení nemohou mít přidružení uživatele (to znamená vyhrazené uživatele) a musí se registrovat instalací a přihlášením pomocí aplikace Portál společnosti.

> [!div class="button"]
[< Zpět](choose-how-to-enroll-devices3.md)

