---
title: "Nasazení aplikací Skycure, aplikace Microsoft Authenticator a zásad konfigurace pro iOS"
description: "Nasaďte aplikace Skycure, aplikaci Microsoft Authenticator a zásady konfigurace pro iOS do klasické konzoly Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45826fbc-6df5-41b2-8e80-d1353f904b43
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 60f4ab5a656a2e253d82971d7bea6b3a6c9eb25a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy"></a>Nasazení aplikací Skycure, aplikace Microsoft Authenticator a zásad konfigurace aplikací pro iOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Před zahájením

-   Níže uvedený postup musíte provést v [klasické konzole Intune](https://manage.microsoft.com/).

-   K přihlášení do klasické konzoly Intune použijte stejný účet Azure AD, který jste dříve nakonfigurovali v konzole pro správu Skycure.

-   Ověřte si, že jste seznámení s těmito postupy:

    -   [Nasazení aplikace pomocí služby Microsoft Intune](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune)

    -   [Nasazení zásad konfigurace aplikace pro iOS](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

## <a name="to-deploy-skycure-apps-microsoft-authenticator-app-and-the-ios-app-configuration-policy"></a>Postup nasazení aplikací Skycure, aplikace Microsoft Authenticator a zásad konfigurace aplikací pro iOS

1.  V klasické konzole Intune zvolte **Aplikace** &gt; **Aplikace**, abyste si zobrazili seznam aplikací, které můžete spravovat.

2.  Vyberte následující aplikace:

    a.  Microsoft Authenticator

    b.  Aplikace Skycure pro Android

    c.  Aplikace Skycure pro iOS

       ![Nasazení všech aplikací pomocí klasické konzoly Intune](../media/mtp/skycure-deploy-app-1.png)

3.  Zvolte **Spravovat nasazení**, vyberte skupinu zabezpečení služby Azure AD, ve které jsou uživatelé Skycure, a potom klikněte na **Další**.

4.  Na stránce **Akce nasazení** vyberte z rozevíracího seznamu **Schválení** možnost **Požadovaná instalace** a potom klikněte na **Další**.

    ![Akce nasazení v klasické konzole Intune](../media/mtp/skycure-deploy-app-2.png)

5.  Na stránce **Profil VPN** vyberte z rozevíracího seznamu **Zásady VPN** možnost **Žádné** a potom klikněte na **Další**.

6.  Na stránce **Konfigurace mobilní aplikace** z rozevíracího seznamu **Zásada konfigurace aplikace** vyberte dříve vytvořené zásady konfigurace aplikací pro iOS a potom klikněte na **Dokončit**.

    ![Konfigurace mobilních aplikací v klasické konzole Intune](../media/mtp/skycure-deploy-app-3.png)

## <a name="next-steps"></a>Další kroky

[Nastavení integrace služby Skycure se službou Intune](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)
