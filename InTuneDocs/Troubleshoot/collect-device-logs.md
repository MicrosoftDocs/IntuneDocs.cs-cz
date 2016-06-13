---
# required metadata

title: Shromažďování protokolů zařízení | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 06/01/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

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


<!--HONumber=Jun16_HO1-->


