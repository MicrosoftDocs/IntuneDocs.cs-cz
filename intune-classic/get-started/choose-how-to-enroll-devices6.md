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
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 364064f3507c00f87b367c0aa4ff7b0f31cea4b7
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---
# <a name="choose-how-to-enroll-mobile-devices"></a>Volba způsobu registrace mobilních zařízení

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vaše odpovědi na tuto řadu otázek vám pomohou určit nejlepší metody registrace zařízení, která spravujete.

## <a name="how-will-you-manage-dedicated-corporate-owned-devices"></a>**Jak budete spravovat vyhrazená zařízení ve vlastnictví firmy?**

  > [!div class="button"]
[DEP pro iOS >]/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)  
> [!div class="button"]
[Průvodce nastavením pro iOS >]/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [!div class="button"]
> [Označení pomocí kódů IMEI >]/intune-classic/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Zařízení vlastněná společností s vyhrazenými uživateli se dají registrovat těmito způsoby:

  - **Program DEP (Device Enrollment Program) společnosti Apple:** Na zakoupená nebo spravovaná zařízení iOS je možné cílit s profilem registrace. Když uživatelé zařízení poprvé zapnou, zařízení stáhne profil DEP a zaregistruje se v Intune.

  - **Apple Configurator na Macu:** Apple Configurator je aplikace Apple, která běží na počítačích Mac. Zařízení s iOSem můžete připojit k počítači Mac kabelem USB a nainstalovat na ně profil registrace. Pokud je to možné, obnovte zařízení do továrního nastavení a zaregistrujte ho pomocí Pomocníka s nastavením.

  - **Značka s číslem IMEI:** Naimportováním čísel IMEI (International Mobile Equipment Identity) zařízení vlastněných společností můžete v Intune tato zařízení označit jako zařízení ve vlastnictví společnosti. Toto je jediný způsob, jak identifikovat vyhrazená („jednouživatelská“) zařízení se systémem Windows a Android jako zařízení ve vlastnictví společnosti. Zařízení s iOSem, která nebudou zaregistrovaná pomocí programu registrace zařízení Apple nebo nástroje Apple Configurator, je také možné označit pomocí čísla IMEI. Poté, co zařízení předběžně deklarujete, aby byla označená jako firemní, je můžete distribuovat uživatelům. Uživatelé si pak můžou zaregistrovat svá zařízení jako vyhrazená nainstalováním Portálu společnosti pro přístup k podnikovým prostředkům, například k e-mailu, aplikacím a datům.

> [!div class="button"]
[< Zpět](choose-how-to-enroll-devices3.md)
