---
title: "Přidání a přiřazení aplikací MTD do Intune"
titleSuffix: Intune on Azure
description: "Přidání aplikací MTD, aplikace Microsoft Authenticator a zásad konfigurace pro iOS do Intune ve službě Azure"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7b3fb86648a86b161eadfc071bdacbfd4ea0222f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Přidání a přiřazení aplikací pro ochranu před mobilními hrozbami (MTD) pomocí Intune

Pokud chcete přidat a nasadit aplikace MTD, aby koncoví uživatelé mohli dostávat oznámení, když je v jejich mobilních zařízeních identifikována hrozba, a získat pokyny k nápravě těchto hrozeb, můžete použít službu Intune.

U zařízení se systémem iOS je potřeba [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), aby mohla být identita uživatelů ověřena pomocí Azure AD. Kromě toho potřebujete zásady konfigurace pro aplikaci iOS, aby bylo zřejmé, která aplikace MTD pro iOS se má v Intune použít.

> [!TIP]
> Portál společnosti Intune funguje jako zprostředkovatel pro zařízení s Androidem, aby mohla být identita uživatelů ověřena pomocí Azure AD.

## <a name="before-you-begin"></a>Před zahájením

-   Níže uvedený postup musíte provést na [portálu Azure Portal](https://portal.azure.com/).

-   Ověřte si, že jste seznámení s těmito postupy:

    -   [Přidání aplikace do služby Intune](apps-add.md)

    -   [Přidání zásad konfigurace aplikace pro iOS do služby Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

    -   [Přiřazení aplikace pomocí služby Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune)

    -   [Přidání zásad konfigurace aplikace pro iOS](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

## <a name="to-add-apps"></a>Přidání aplikací

### <a name="skycure-app-for-android"></a>Aplikace Skycure pro Android

- Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](store-apps-android.md). V **kroku 7** použijte tento [odkaz URL na Skycure v obchodě s aplikacemi](https://play.google.com/store/apps/details?id=com.skycure.skycure).

### <a name="skycure-app-for-ios"></a>Aplikace Skycure pro iOS

- Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](store-apps-ios.md). V **kroku 5** v části **Konfigurace informací o aplikaci** použijte tento [odkaz URL na Skycure v obchodě s aplikacemi](https://itunes.apple.com/us/app/skycure/id695620821?mt=8).

### <a name="microsoft-authenticator-app-for-ios"></a>Aplikace Microsoft Authenticator pro iOS

- Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](store-apps-ios.md). V **kroku 5** v části **Konfigurace informací o aplikaci** použijte tento [odkaz URL na Microsoft Authenticator v obchodě s aplikacemi](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8).

### <a name="lookout-for-work-android-app"></a>Aplikace Lookout for Work pro Android

- Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](store-apps-android.md). V **kroku 7** použijte tento [odkaz URL na Lookout for Work v obchodě s aplikacemi Google](https://play.google.com/store/apps/details?id=com.lookout.enterprise).

### <a name="lookout-for-work-ios-app"></a>Aplikace Lookout for Work pro iOS

- Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](store-apps-ios.md). V **kroku 5** v části **Konfigurace informací o aplikaci** použijte tento [odkaz URL na aplikaci Lookout for Work pro iOS v App Storu](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8).

### <a name="lookout-for-work-app-outside-the-apple-store"></a>Aplikace Lookout for Work mimo obchod App Store společnosti Apple

Je potřeba, abyste aplikaci Lookout for Word pro iOS znovu podepsali. Lookout distribuuje svou aplikaci Lookout for Work pro iOS mimo obchod App Store. Před distribucí této aplikace ji musíte znovu podepsat pomocí certifikátu podnikového vývojáře pro iOS.

Podrobné pokyny k opětovnému podepsání aplikace Lookout for Work pro iOS najdete v článku [o opětovném podepsání aplikace Lookout for Word pro iOS](https://personal.support.lookout.com/hc/articles/114094038714) na webu Lookout.

#### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a>Povolení ověřování službou Azure AD v aplikaci Lookout for Work pro iOS

Následujícím postupem povolte ověřování uživatelů iOS službou Azure Active Directory:

1. Přejděte na [portál Azure Portal](https://portal.sazure.com), přihlaste se pomocí svých přihlašovacích údajů a přejděte na stránku aplikace.
  
2. Přidejte **aplikaci Lookout for Work pro iOS** jako **nativní klientskou aplikaci**.

3. Text **com.lookout.enterprise.názevfirmy** nahraďte identifikátorem zákaznického balíčku, který jste vybrali při podepisování IPA.

4.  Přidejte další identifikátor URI pro přesměrování: **&lt;companyportal://code/>** následovaný původním identifikátorem URI pro přesměrování ve verzi kódované v řetězci URL.

5.  Přidejte k aplikaci **Delegovaná oprávnění**.

    > [!NOTE] 
    > Další podrobnosti najdete v článku o [konfiguraci nativní klientské aplikace pomocí Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

#### <a name="add-the-lookout-for-work-ipa-file"></a>Přidání souboru .ipa pro aplikaci Lookout for Work

- Podle popisu v tématu [Přidání obchodních aplikací pro iOS do Microsoft Intune](lob-apps-ios.md) nahrajte opětovně podepsaný soubor .ipa. Kromě toho je potřeba nastavit jako minimální verzi operačního systému iOS 8.0 nebo novější.

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a>Přidružení aplikace MTD k zásadám konfigurace aplikace pro iOS

### <a name="for-skycure"></a>Pro Skycure

-   K přihlášení do klasické konzoly Intune použijte stejný účet Azure AD, který jste dříve nakonfigurovali v konzole pro správu Skycure.

-   Musíte mít připravený integrační soubor Skycure. Je to soubor .zip, který jste v předchozím kroku stáhli z konzoly pro správu Skycure a který obsahoval soubor **skycure\_configuration.plist** s parametry zásad konfigurace aplikace pro iOS.

- Pokud chcete přidat zásady konfigurace aplikace Skycure pro iOS, přečtěte si pokyny ohledně [používání zásad konfigurace aplikací služby Microsoft Intune pro iOS](app-configuration-policies-use-ios.md).
    - V kroku 8 použijte možnost **Zadat XML data**, zkopírujte obsah ze souboru **skycure_configuration.plist** a vložte ho do těla zásad konfigurace.

Obsah souboru **skycure_configuration.plist** můžete zkopírovat i odsud:

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>

```
### <a name="for-lookout"></a>Pro Lookout

- Vytvořte zásady konfigurace aplikace pro iOS pomocí tématu [o použití zásad konfigurace aplikace pro iOS](app-configuration-policies-use-ios.md).

## <a name="to-assign-mtd-apps"></a>Přiřazení aplikací MTD

- Přečtěte si pokyny pro [přiřazení aplikací do skupin pomocí Intune](apps-deploy.md).

## <a name="next-steps"></a>Další kroky

[Nastavení integrace služby Skycure se službou Intune](skycure-mtd-connector-integration.md)
[Nastavení integrace služby Lookout se službou Incure](lookout-mtd-connector-integration.md)
