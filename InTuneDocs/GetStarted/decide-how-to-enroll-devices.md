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
ms.assetid: 178df739-d3b9-43cb-8440-c5c110b1276b
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 90a26e1008a8e0800b07940c11a8adcd00cbb241
ms.openlocfilehash: becbaa195dc3fde6bc0a0edb0916c75a4d07c017


---

# Volba způsobu registrace mobilních zařízení

Registrace mobilních zařízení je proces, který zajišťuje správu smartphonů, tabletů a počítačů přes Microsoft Intune. Z pozice správce musíte určit, jak nejlépe provést registraci zařízení, podle těchto kritérií:

 -  Vlastnictví (osobní zařízení vs. zařízení patřící společnosti)
 -  Využívání (sdílené vs. osobní)
 -  Platforma (iOS, Android, Windows Phone, počítač s Windows, počítač Mac)

Nejvhodnější způsob registrace zařízení, která spravujete, vám pomůžou s odpověďmi na následující otázky.

## **Přinášejí si zaměstnanci vlastní zařízení nebo se používají zařízení poskytnutá vaší organizací?**

  - **Zařízení ve vlastnictví uživatelé:** V takovém případě jde o registraci typu Přineste si vlastní zařízení (BYOD – Bring Your Own Device). Uživatelé si můžou na zařízení nainstalovat aplikaci Portál společnosti Intune a pak zařízení zaregistrovat, aby měli přístup k prostředkům společnosti (například k e-mailům, podnikovým aplikacím, datům společnosti a podpoře).  

  - **Zařízení vlastněná společností:** Zařízení vlastněná společností (COD – Company-Owned Devices) je možné do Intune registrovat několika různými způsoby v závislosti na potřebách organizace a typech spravovaných zařízení.

> [!div class="button"]
[Registrace BYOD >](#what-byod-devices-can-your-users-enroll)   [Registrace COD >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## **Která zařízení BYOD můžou vaši uživatelé zaregistrovat?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS a Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile a Windows Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Počítače s Windows](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## **Jak se zařízení ve vlastnictví společnosti využívají? Jsou sdílená nebo je využívá vždycky jenom jeden konkrétní uživatel?**

- **Sdílená zařízení vlastněná společností:** Tato zařízení nemají jenom jednoho konkrétního uživatele a obvykle nejsou nakonfigurovaná pro přístup k e-mailu. O taková zařízení jde například v případě zařízení sloužících jako veřejný terminál nebo v případě zařízení, která si uživatelé vždy pouze vypůjčí na konkrétní úkol. Doporučené metody registrace závisí na platformě zařízení.

- **Vyhrazení uživatelé:** Zařízení vlastněná společností, která dostali k užívání konkrétní uživatelé, je třeba sledovat jako majetek společnosti a současně je potřeba uživatelům umožnit, aby je využívali jako osobní zařízení pro přístup k e-mailům a datům. Doporučené metody registrace závisí na platformě zařízení.

> [!div class="button"]
[Sdílené >](#what-operating-system-are-your-shared-devices-running)   [Vyhrazené >](#how-will-you-manage-dedicated-ios-devices)


## **Který operační systém běží na sdílených zařízeních?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## **Jak budete spravovat sdílená zařízení s iOS?**

- **Program DEP (Device Enrollment Program) společnosti Apple:** Na zakoupená nebo spravovaná zařízení iOS je možné cílit s profilem registrace. Když uživatelé zařízení poprvé zapnou, zařízení stáhne profil DEP a zaregistruje se s ním.

- **Apple Configurator na Macu:** Apple Configurator je aplikace Apple, která běží na počítačích Mac. Zařízení s iOS můžete připojit k počítači Mac kabelem USB a nainstalovat na ně profil registrace. Pokud je to možné, obnovte zařízení do továrního nastavení a zaregistrujte ho pomocí Pomocníka s nastavením. Pokud zařízení nechcete obnovit do továrního nastavení, použijte tzv. přímou registraci.

- **Správce registrace zařízení:** Správce registrace zařízení (DEM) služby Intune umožňuje, aby manažer nebo správce zaregistroval mnoho mobilních zařízení s jedním uživatelským účtem. Tato zařízení nemohou mít přidružení uživatele (to znamená vyhrazené uživatele) a musí se registrovat instalací a přihlášením pomocí aplikace Portál společnosti.

  > [!div class="button"]
  [Registrace DEP pro iOS >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Přímá registrace pro iOS >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)  [Registrace DEM >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

## **Jak budete spravovat vyhrazená zařízení s iOS?**

Zařízení vlastněná společností s vyhrazenými uživateli se dají registrovat těmito způsoby:

- **Program DEP (Device Enrollment Program) společnosti Apple:** Na zakoupená nebo spravovaná zařízení iOS je možné cílit s profilem registrace. Když uživatelé zařízení poprvé zapnou, zařízení stáhne profil DEP a zaregistruje se v Intune.

- **Apple Configurator na Macu:** Apple Configurator je aplikace Apple, která běží na počítačích Mac. Zařízení s iOS můžete připojit k počítači Mac kabelem USB a nainstalovat na ně profil registrace. Pokud je to možné, obnovte zařízení do továrního nastavení a zaregistrujte ho pomocí Pomocníka s nastavením.

- **Značka s číslem IMEI:** Naimportováním čísel IMEI (International Mobile Equipment Identity) zařízení vlastněných společností můžete v Intune tato zařízení označit jako zařízení ve vlastnictví společnosti. Uživatelé si pak můžou zaregistrovat svá zařízení jako osobní zařízení nainstalováním Portálu společnosti pro přístup k podnikovým prostředkům, například k e-mailu, aplikacím a datům.

  > [!div class="button"]
  [Označení kódem IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [DEP pro iOS](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Průvodce nastavením iOS](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Označení kódem IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)



<!--HONumber=Aug16_HO2-->


