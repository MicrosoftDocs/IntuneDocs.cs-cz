---
title: "Shromažďování protokolů zařízení | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: angrobe
ms.date: 06/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb0aeac2f94dfde50d9398b09c6b21c7ae40624
ms.openlocfilehash: fb4bc718212480b9e44dc964b432dc2e37b3e531


---

# Protokoly zařízení

Jako součást řešení potíží můžete chtít shromažďovat protokoly ze zařízení uživatelů. Pokyny pro shromažďování těchto protokolů najdete tady. Obvykle potřebujete přístup k zařízení nebo požádáte uživatele, aby shromáždil protokoly a poslal vám je.

### Umístění protokolů Androidu
Protokoly Androidu jsou umístěné v adresáři *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. Uživatel vám může také poslat soubory protokolů e-mailem, jak je popsáno v tématu [Odeslání protokolů s diagnostickými daty ze zařízení s Androidem správci IT e-mailem](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android).

### Protokoly iOS

Uživatel vám může poslat chyby registrace, jak je popsáno v tématu [Odeslání chyb registrace zařízení s iOS správci IT](/intune/enduser/send-errors-to-your-it-admin-ios).

### Zařízení s Mac OS X

1. Otevřete aplikaci **Konzola**.
2. V části **SOUBORY** zvolte **system.log**.
3. V panelu nabídek nahoře zvolte **Soubor** > **Uložit kopii jako** a uložte soubor.

### Windows Phone

V aplikaci **Portál společnosti pro Windows Phone** uživatel bude muset zvolit **...**, aby měl přístup k nabídce, a pak zvolit **Odeslat protokoly**. Tato možnost je k dispozici před i po přihlášení k portálu.

### Windows

V případě aplikace Portál společnosti pro Windows jsou protokoly umístěny v adresáři *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Aug16_HO1-->


