---
title: "Volba způsobu registrace mobilních zařízení | Microsoft Intune"
description: "Volba způsobu registrace mobilních zařízení v Intune zodpovězením několik jednoduchých dotazů"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: e1fe6b167b7d46f03472833bc1c3c19030f47bce
ms.openlocfilehash: 38dce11fa7df302bc2dffc3a2352d516c873fedb


---
# Volba způsobu registrace mobilních zařízení

Vaše odpovědi na tuto řadu otázek vám pomohou určit nejlepší metody registrace zařízení, která spravujete.

## **Jak budete spravovat vyhrazená zařízení s iOS?**

  > [!div class="button"]
  [Označení kódem IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [DEP pro iOS >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Průvodce nastavením iOS >](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Označení kódem IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Zařízení vlastněná společností s vyhrazenými uživateli se dají registrovat těmito způsoby:

  - **Program DEP (Device Enrollment Program) společnosti Apple:** Na zakoupená nebo spravovaná zařízení iOS je možné cílit s profilem registrace. Když uživatelé zařízení poprvé zapnou, zařízení stáhne profil DEP a zaregistruje se v Intune.

  - **Apple Configurator na Macu:** Apple Configurator je aplikace Apple, která běží na počítačích Mac. Zařízení s iOS můžete připojit k počítači Mac kabelem USB a nainstalovat na ně profil registrace. Pokud je to možné, obnovte zařízení do továrního nastavení a zaregistrujte ho pomocí Pomocníka s nastavením.

  - **Značka s číslem IMEI:** Naimportováním čísel IMEI (International Mobile Equipment Identity) zařízení vlastněných společností můžete v Intune tato zařízení označit jako zařízení ve vlastnictví společnosti. Uživatelé si pak můžou zaregistrovat svá zařízení jako osobní zařízení nainstalováním Portálu společnosti pro přístup k podnikovým prostředkům, například k e-mailu, aplikacím a datům.

  > [!div class="button"]
  [< Zpět](choose-how-to-enroll-devices3.md)



<!--HONumber=Aug16_HO2-->


