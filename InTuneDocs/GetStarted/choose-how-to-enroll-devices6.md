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
ms.sourcegitcommit: a5f80058e004f119acc9a918123c897b72b71314
ms.openlocfilehash: ecc6834b18d7906633bf1a029f5d63a4432c4989


---
# Volba způsobu registrace mobilních zařízení

Vaše odpovědi na tuto řadu otázek vám pomohou určit nejlepší metody registrace zařízení, která spravujete.

## **Jak budete spravovat vyhrazená zařízení ve vlastnictví firmy?**

  > [!div class="button"]
[iOS DEP >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)<br>[Průvodce nastavením iOS >](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)<br>[Označení kódem IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Zařízení vlastněná společností s vyhrazenými uživateli se dají registrovat těmito způsoby:

  - **Program DEP (Device Enrollment Program) společnosti Apple:** Na zakoupená nebo spravovaná zařízení iOS je možné cílit s profilem registrace. Když uživatelé zařízení poprvé zapnou, zařízení stáhne profil DEP a zaregistruje se v Intune.

  - **Apple Configurator na Macu:** Apple Configurator je aplikace Apple, která běží na počítačích Mac. Zařízení s iOS můžete připojit k počítači Mac kabelem USB a nainstalovat na ně profil registrace. Pokud je to možné, obnovte zařízení do továrního nastavení a zaregistrujte ho pomocí Pomocníka s nastavením.

  - **Značka s číslem IMEI:** Naimportováním čísel IMEI (International Mobile Equipment Identity) zařízení vlastněných společností můžete v Intune tato zařízení označit jako zařízení ve vlastnictví společnosti. Toto je jediný způsob, jak identifikovat vyhrazená („jednouživatelská“) zařízení se systémem Windows a Android jako zařízení ve vlastnictví společnosti. Zařízení s iOS, která nebudou zaregistrovaná pomocí programu registrace zařízení Apple nebo nástroje Apple Configurator, je také možné označit pomocí čísla IMEI. Poté, co zařízení předběžně deklarujete, aby byla označená jako firemní, je můžete distribuovat uživatelům. Uživatelé si pak můžou zaregistrovat svá zařízení jako vyhrazená nainstalováním Portálu společnosti pro přístup k podnikovým prostředkům, například k e-mailu, aplikacím a datům.

  > [!div class="button"]
  [< Zpět](choose-how-to-enroll-devices3.md)



<!--HONumber=Aug16_HO5-->


