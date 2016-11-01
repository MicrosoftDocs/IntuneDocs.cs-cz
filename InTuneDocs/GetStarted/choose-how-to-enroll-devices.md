---
title: "Volba způsobu registrace mobilních zařízení | Microsoft Intune"
description: "Volba způsobu registrace mobilních zařízení v Intune zodpovězením několik jednoduchých dotazů"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 2c14071f5fb1a3604b897d6b2f81797d40bedc6d
ms.openlocfilehash: 1fd8495811e2cbcf4761707f2d1b705e49a240c6


---

# Volba způsobu registrace mobilních zařízení

Odpovězte na následující otázky, abyste zjistili nejvhodnější způsob registrace spravovaných zařízení.

## **Přinášejí si zaměstnanci vlastní zařízení nebo jim zařízení poskytuje organizace?**

  - **Zařízení vlastněná uživateli** – Registrace BYOD (Přineste si vlastní zařízení)
  - **Zařízení vlastněná společností** – Registrace COD

> [!div class="button"]
[Registrace BYOD >](#what-byod-devices-can-your-users-enroll)   
> [!div class="button"]
[Registrace COD >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## **Která zařízení BYOD můžou vaši uživatelé zaregistrovat?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS a Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile a Windows Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Počítače s Windows](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## **Zařízení, která patří společnosti, jsou sdílená nebo mají vyhrazené uživatele?**

> [!div class="button"]
[Sdílené >](#what-operating-system-are-your-shared-devices-running)   [Vyhrazené >](#how-will-you-manage-dedicated-ios-devices)


## **Který operační systém běží na sdílených zařízeních?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## **Jak budete spravovat sdílená zařízení s iOS?**

  > [!div class="button"]
  [Registrace DEP pro iOS >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Přímá registrace pro iOS >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune) [Registrace DEM >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Program DEP (Device Enrollment Program) společnosti Apple** – Zařízení s iOS, která jsou zakoupená nebo spravovaná v programu DEP, je možné přidružit k profilu registrace. Při prvním zapnutí uživateli si zařízení stáhne profil DEP a použije ho k registraci.

  - **Apple Configurator na Macu:** Apple Configurator je aplikace Apple, která běží na počítačích Mac. Zařízení s iOS můžete připojit k počítači Mac kabelem USB a nainstalovat na ně profil registrace. Pokud můžete obnovit tovární nastavení zařízení, abyste je mohli zaregistrovat, použijte k registraci pomocníka s nastavením. Pokud zařízení nechcete obnovit do továrního nastavení, použijte možnost přímé registrace.

  - **Správce registrace zařízení (Intune)** – Správce registrace zařízení (DEM) služby Intune umožňuje manažerovi nebo správci, aby pod jedním uživatelským účtem zaregistroval více mobilních zařízení. Tato zařízení nemohou mít vyhrazené uživatele (přidružení uživatelů). Musí se zaregistrovat tak, že si nainstalují aplikaci Portál společnosti a přihlásí se do ní.

## **Jak budete spravovat vyhrazená zařízení s iOS?**

  > [!div class="button"]
   [Program DEP pro iOS](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Průvodce nastavením iOS](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Označení kódem IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Zařízení vlastněná společností s vyhrazenými uživateli se dají registrovat těmito způsoby:

  - **Program DEP (Device Enrollment Program) společnosti Apple** – Zařízení s iOS, která jsou zakoupená nebo spravovaná v programu DEP, je možné přidružit k profilu registrace. Když uživatelé zařízení poprvé zapnou, zařízení stáhne profil DEP a zaregistruje se v Intune.

  - **Apple Configurator na Macu:** Apple Configurator je aplikace Apple, která běží na počítačích Mac. Zařízení s iOS můžete připojit k počítači Mac kabelem USB a nainstalovat na ně profil registrace. Pokud můžete obnovit tovární nastavení zařízení, abyste je mohli zaregistrovat, použijte k registraci pomocníka s nastavením.

  - **Označení kódem IMEI** – Pokud naimportujete kódy IMEI (International Mobile Equipment Identity) zařízení, která jsou ve vlastnictví společnosti, můžete je v Intune označit jako zařízení patřící společnosti. Uživatelé si pak mohou zaregistrovat vlastní zařízení jako osobní zařízení tím, že si nainstalují Portál společnosti, aby měli přístup k prostředkům společnosti, jako je e-mail, aplikace a data.



<!--HONumber=Oct16_HO3-->


