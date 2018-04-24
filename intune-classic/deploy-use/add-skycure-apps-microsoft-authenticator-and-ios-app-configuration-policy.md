---
title: Přidání aplikací Skycure, aplikace Microsoft Authenticator a zásad konfigurace pro iOS
description: Přidejte aplikace Skycure, aplikaci Microsoft Authenticator a zásady konfigurace pro iOS do klasického portálu Intune.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 018d26f4-4a75-4e27-bb04-54f54106cb2f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3538b3b326ee45dfcc0912c89d1766e04d88051e
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="add-skycure-apps-microsoft-authenticator-app-and-ios-configuration-policy"></a>Přidání aplikací Skycure, aplikace Microsoft Authenticator a zásad konfigurace pro iOS

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Pokud chcete přidat a nasadit aplikace Skycure, aby koncoví uživatelé mohli dostávat oznámení, když je v jejich mobilních zařízeních identifikována hrozba, a získat pokyny k nápravě těchto hrozeb, budete muset použít službu Intune.

Kromě toho budete potřebovat [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), aby se mohla identita uživatelů ověřit pomocí služby Azure AD a zásad konfigurace aplikace pro iOS. Ty aplikaci Skycure pro iOS signalizují, že má použít službu Intune a jednotné přihlašování (SSO) služby Azure AD, aby uživatelé nemuseli zadávat uživatelské jméno a heslo pokaždé, když se do aplikace Skycure přihlašují.

## <a name="before-you-begin"></a>Před zahájením

-   Níže uvedený postup musíte provést na [klasickém portálu Intune](https://manage.microsoft.com/).

-   Použijte stejný účet Azure AD, který jste dříve nakonfigurovali v konzole pro správu Skycure. Mělo by jít o stejný účet, který slouží k přihlašování ke klasickému portálu Intune.

-   Musíte mít připravený integrační soubor Skycure. Je to soubor .zip, který jste v předchozím kroku stáhli z konzoly pro správu Skycure a který obsahoval soubor **skycure\_configuration.plist** s parametry zásad konfigurace aplikace pro iOS.

-   Ověřte si, že jste seznámení s těmito postupy:

    -   [Přidání aplikace do služby Intune](/intune-classic/deploy-use/add-apps)

    -   [Přidání zásad konfigurace aplikace pro iOS do služby Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

## <a name="to-add-the-skycure-app-for-android"></a>Postup přidání aplikace Skycure pro Android

1.  Na klasickém portálu Intune vyberte **Aplikace** &gt; **Přidat aplikace**. Tím se spustí Vydavatel softwaru Intune. Potom klikněte na **Další**.

2.  Na stránce **Instalace softwaru** vyberte **Externí odkaz** a potom v části **Zadejte adresu URL** vložte adresu URL pro [aplikaci Skycure pro Android](https://play.google.com/store/apps/details?id=com.skycure.skycure).

    ![Zadání adresy URL ve Vydavateli softwaru Intune](../media/mtp/skycure-add-apps-1.png)

3.  Na stránce **Popis softwaru** zadejte **vydavatele**, **název** a **popis**, vyberte možnost **Zobrazit tuto aplikaci jako doporučenou aplikaci a zvýraznit ji na portálu společnosti** a potom klikněte na **Další**.

    ![Popis softwaru ve Vydavateli softwaru Intune](../media/mtp/skycure-add-apps-2.png)

4.  Klikněte na **Nahrát** a potom na **Zavřít**.

## <a name="to-add-the-skycure-app-for-ios"></a>Postup přidání aplikace Skycure pro iOS

1.  Na klasickém portálu Intune vyberte **Aplikace** &gt; **Přidat aplikace**. Tím se spustí Vydavatel softwaru Intune. Potom klikněte na **Další**.

2.  Na stránce **Instalace softwaru** vyberte **Spravovaná aplikace pro iOS z App Storu** a potom v části **Zadejte adresu URL** vložte adresu URL pro [aplikaci Skycure pro iOS](https://itunes.apple.com/us/app/skycure/id695620821?mt=8).

    ![Spravovaná aplikace pro iOS ve Vydavateli softwaru Intune](../media/mtp/skycure-add-apps-3.png)

3.  Na stránce **Popis softwaru** zadejte **vydavatele**, **název** a **popis**, vyberte možnost **Zobrazit tuto aplikaci jako doporučenou aplikaci a zvýraznit ji na portálu společnosti** a potom klikněte na **Další**.

    ![Možnosti ve Vydavateli softwaru Intune](../media/mtp/skycure-add-apps-4.png)

4.  Na stránce **Požadavky** vyberte v části **Typ mobilního zařízení** možnost **Jakýkoli** a potom klikněte na **Další**.

5.  Klikněte na **Nahrát** a potom na **Zavřít**.

## <a name="to-add-the-microsoft-authenticator-app-for-ios"></a>Postup přidání aplikace Microsoft Authenticator pro iOS

1.  Na klasickém portálu Intune vyberte **Aplikace** &gt; **Přidat aplikace**. Tím se spustí Vydavatel softwaru Intune. Potom klikněte na **Další**.

2.  Na stránce **Instalace softwaru** vyberte **Spravovaná aplikace pro iOS z App Storu** a potom v části **Zadejte adresu URL** vložte adresu URL pro [aplikaci Microsoft Authenticator pro iOS](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8).

    ![Druhá spravovaná aplikace pro iOS ve Vydavateli softwaru Intune](../media/mtp/skycure-add-apps-5.png)

3.  Na stránce **Popis softwaru** zadejte **vydavatele**, **název** a **popis**, vyberte možnost **Zobrazit tuto aplikaci jako doporučenou aplikaci a zvýraznit ji na portálu společnosti** a potom klikněte na **Další**.

    ![Třetí spravovaná aplikace pro iOS ve Vydavateli softwaru Intune](../media/mtp/skycure-add-apps-6.png)

4.  Na stránce **Požadavky** vyberte v části **Typ mobilního zařízení** možnost **Jakýkoli** a potom klikněte na **Další**.

5.  Klikněte na **Nahrát** a potom na **Zavřít**.

## <a name="to-add-the-skycure-ios-app-configuration-policy"></a>Postup přidání zásad konfigurace aplikace Skycure pro iOS

1.  Na klasickém portálu Intune vyberte **Zásady** &gt; **Přehled &gt; Přidat zásadu**.

2.  V seznamu zásad rozbalte **iOS**, zvolte **Zásada konfigurace mobilní aplikace (iOS 8.0 a novější)** a pak zvolte **Vytvořit zásadu**.

    ![Zásada konfigurace aplikace pro iOS](../media/mtp/skycure-add-apps-7.png)

3.  Na stránce **Vytvořit zásadu** v části **Obecné** zadejte název a nepovinný popis zásady konfigurace aplikace pro iOS.

    a.  Otevřete pomocí textového editoru, jako je Poznámkový blok, soubor **skycure\_configuration.plist**, zkopírujte jeho obsah a vložte ho do těla **Zásada konfigurace mobilní aplikace**, zvolte **Ověřit** a potom zvolte **Uložit zásadu**.

       ![Druhá zásada konfigurace aplikace pro iOS](../media/mtp/skycure-add-apps-8.png)

## <a name="next-steps"></a>Další kroky

[Nasazení aplikací Skycure, aplikace Microsoft Authenticator a zásad konfigurace aplikace pro iOS](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)
