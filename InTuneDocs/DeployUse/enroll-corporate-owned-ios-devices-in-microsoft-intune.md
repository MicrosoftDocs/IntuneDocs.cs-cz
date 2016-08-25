---
title: "Registrace zařízení iOS vlastněných společností v Microsoft Intun | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ROBOTS: noindex,nofollow
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 48359b44bec9ac3e1c9510debc01d2cf8abf6d2b


---

# Registrace zařízení iOS vlastněných společností v Microsoft Intune
Microsoft Intune podporuje registraci firemních zařízení iOS prostřednictvím programu Apple Device Enrollment Program (DEP) nebo pomocí nástroje [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) spuštěného na počítači Mac.

Existují tři způsoby registrace firmou zaregistrovaných zařízení iOS:

-   **Registrace v průvodci nastavením** – Obnoví tovární nastavení a připraví zařízení k nastavení jeho novým uživatelem. Tato metoda vyžaduje, aby se správce připojil pomocí USB k počítači Mac, na které je spuštěný nástroj Apple Configurator, a předkonfiguroval registraci. Zařízení jsou potom doručovaná uživatelům, kteří spustí proces průvodce nastavením a nakonfigurují zařízení svými pracovními nebo školními pověřovacími údaji a dokončí proces registrace. [Registrace zařízení s iOS pomocí nástroje Apple Configurator a Průvodce nastavením](ios-setup-assistant-enrollment-in-microsoft-intune.md)

-   **Přímá registrace** – Vytvoří soubor kompatibilní s Apple Configuratorem, který můžete použít při přípravě zařízení. Zaregistrované zařízení nemá obnovené tovární nastavení a nemá přiřazeného uživatele. Tato metoda vyžaduje, aby se správce připojil pomocí USB k počítači Mac, na které je spuštěný nástroj Apple Configurator, a registroval zařízení. [Registrace zařízení s iOS pomocí přímé registrace nástroje Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md)

-   **Program registrace zařízení (DEP)** – Nasadí do zařízení koupeného prostřednictvím programu registrace zařízení Apple profil pro registraci „vzduchem“. Když uživatel na zařízení spustí průvodce nastavením, zařízení se registruje v Intune.  U zařízení zaregistrovaných v programu DEP uživatelé nemůžou registraci zrušit. [Registrace zařízení s iOS pomocí programu registrace zařízení DEP](ios-device-enrollment-program-in-microsoft-intune.md)




### Související témata
[Příprava registrace zařízení v Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


