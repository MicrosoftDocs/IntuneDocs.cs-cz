---
title: "Co je nového | Microsoft Intune"
description: "Zjistěte, co je nového v aktualizaci služby Microsoft Intune v tomto měsíci nebo dříve"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8ef3b7e4eec5a520c93fb3f70c8e5b6ee7d2c3aa
ms.openlocfilehash: e0b0c7eb3ddc07f05fc0c2e4caa6726ed052c9d8


---
# <a name="whats-new-in-microsoft-intune---november-2016"></a>Co je nového v Microsoft Intune – listopad 2016
Zjistěte, co je nového v této verzi Microsoft Intune. Můžete také získat informace o nadcházejících změnách, se kterými byste měli počítat, a o minulých verzích.

> [!Note]
> Všechny tyto funkce budou posléze podporované pro zákazníky využívající hybridní nasazení (Configuration Manager s Intune). Další informace o nových funkcích pro hybridní nasazení najdete na naší [stránce Co je nového pro hybridní nasazení](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nové funkce

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

__Nový Portál společnosti Microsoft Intune pro zařízení s Windows 10:__ Společnost Microsoft vydala novou [aplikaci Portál společnosti Microsoft Intune pro zařízení s Windows 10](https://www.microsoft.com/store/apps/9wzdncrfj3pz). Tato aplikace, která využívá nový univerzální formát Windows 10, poskytne uživatelům aktualizované prostředí, které je identické napříč všemi zařízeními s Windows 10, ať už jsou to počítače, nebo mobilní zařízení, a nabídne přitom stejné funkce, které v současnosti využívají.

Tato nová aplikace také uživatelům umožní využít v zařízeních s Windows 10 další funkce platformy, jako je jednotné přihlašování (SSO) a ověřování na základě certifikátů. Tato aplikace bude dostupná jako upgrade stávající aplikace Portál společnosti Windows 8.1 a Portál společnosti Windows Phone 8.1 a instaluje se z Windows Storu. Další podrobnosti najdete na adrese [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __Aktuální informace o Intune a Android for Work__

> I když aplikace Android for Work můžete nasazovat s akcí __Požadované__, pokud byly vaše skupiny Intune migrovány do nového prostředí Azure AD, můžete aplikace nasazovat jenom jako __Dostupné__.

### <a name="intune-app-sdk-for-cordova-plugin-now-supports-mam-without-enrollment"></a>Intune App SDK pro modul plug-in Cordova teď podporuje MAM bez registrace
Vývojáři aplikací můžou teď pomocí modulu plug-in Cordova sady Intune App SDK povolit funkce MAM bez registrace zařízení ve svých aplikacích založených na Cordově pro Android a iOS. Modul plug-in Cordova sady Intune App SDK najdete [tady](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

### <a name="intune-app-sdk-xamarin-component-now-supports-mam-without-enrollment"></a>Komponenta Xamarin sady Intune App SDK teď podporuje MAM bez registrace
Vývojáři aplikací teď můžou pomocí komponenty Xamarin sady Intune App SDK povolit funkce MAM bez registrace zařízení ve svých aplikacích založených na Xamarinu pro Android a iOS. Komponentu Xamarin sady Intune App SDK najdete [tady](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

## <a name="notices"></a>Sdělení

### <a name="symantec-signing-certificate-no-longer-requires-signed-windows-phone-8-company-portal-for-upload"></a>Podpisový certifikát Symantec už k nahrání nevyžaduje podepsanou aplikaci Portál společnosti ve Windows Phonu 8
Nahrání podpisového certifikátu Symantec už nevyžaduje podepsanou aplikaci Portál společnosti ve Windows Phonu 8. Certifikát jde nahrát nezávisle.

## <a name="deprecations"></a>Vyřazení

### <a name="support-for-the-windows-phone-8-company-portal"></a>Podpora Portálu společnosti ve Windows Phonu 8
Podpora Portálu společnosti ve Windows Phonu 8 se přestane nabízet. Podpora pro platformy Windows Phone 8 a WinRT se přestala nabízet v říjnu 2016. Podpora pro Portál společnosti ve Windows Phonu 8 se také přestala nabízet v říjnu 2016.


### <a name="see-also"></a>Viz taky
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plán cloudové platformy](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Předchozí verze Intune](whats-new-archive.md)



<!--HONumber=Dec16_HO1-->


