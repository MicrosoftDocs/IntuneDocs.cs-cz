---
title: "Shromažďování protokolů zařízení | Microsoft Intune"
description: "Přečtěte si, jak shromažďovat protokoly ze spravovaných zařízení."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 11/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 19b0b502d2c8c261947c461f27a0e8153df5b186
ms.openlocfilehash: 1e65c1fa25e273ba03218f79ebeff611138e8013


---

# <a name="device-logs"></a>Protokoly zařízení

Jako součást řešení potíží můžete chtít shromažďovat protokoly ze zařízení uživatelů. Pokyny pro shromažďování těchto protokolů najdete tady. Obvykle potřebujete přístup k zařízení nebo požádáte uživatele, aby shromáždil protokoly a poslal vám je.

### <a name="android-logs"></a>Protokoly Androidu
Protokoly Androidu jsou umístěné v adresáři *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. 

Někdy se soubory nezobrazí, zejména na novějších zařízeních s Androidem. V takovém případě řekněte svým koncovým uživatelům, aby si otevřeli aplikaci Portál společnosti pro Android a přešli na **Nastavení**, zvolili **Zkopírovat protokoly** a pak si restartovali zařízení. 

Další informace o tom, jak vám uživatelé můžou posílat svoje protokoly dat, najdete v těchto článcích:

- [Pomoc správci IT s řešením problémů zařízení pomocí podrobného protokolování](/intune/enduser/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android) – Popisuje, jak uživatelé můžou zapnout podrobné protokolování, které vám bude automaticky posílat všechny jejich protokoly dat. Ve výchozím nastavení je podrobné protokolování zapnuté.

- [Odeslání protokolů s diagnostickými daty Androidu e-mailem vašemu správci IT](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android) 

- [Odeslání protokolů s diagnostickými daty správci IT pomocí kabelu USB](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <a name="ios-logs"></a>Protokoly iOS

Uživatelé vám můžou posílat chyby registrace. To se popisuje v tématu [Odeslání chyb registrace zařízení s iOSem správci IT](/intune/enduser/send-errors-to-your-it-admin-ios).

### <a name="mac-os-x-logs"></a>Protokoly Mac OS X

1. Otevřete aplikaci **Konzola**.
2. V části **SOUBORY** zvolte **system.log**.
3. V panelu nabídek nahoře zvolte **Soubor** > **Uložit kopii jako** a uložte soubor.

### <a name="windows-phone"></a>Windows Phone

V aplikace Portál společnosti pro Windows Phone uživatelé zvolí **…** aby měl přístup k nabídce, a pak zvolit **Odeslat protokoly**. Tato možnost je k dispozici před i po přihlášení k aplikaci Portál společnosti.

### <a name="windows"></a>Windows

V případě aplikace Portál společnosti pro Windows se protokoly nacházejí v adresáři *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Nov16_HO2-->


