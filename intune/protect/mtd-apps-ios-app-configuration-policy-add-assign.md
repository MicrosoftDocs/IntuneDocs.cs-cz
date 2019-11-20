---
title: Přidání a přiřazení aplikací pro ochranu před mobilními hrozbami (MTD) do Microsoft Intune
titleSuffix: Microsoft Intune
description: Pomocí Intune můžete přidat aplikace pro ochranu před mobilními hrozbami (MTD), aplikaci Microsoft Authenticator a zásady konfigurace iOS na portálu Azure Portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04a18befe73ce63f5619c3efc6def4189db9c8df
ms.sourcegitcommit: 13fa1a4a478cb0e03c7f751958bc17d9dc70010d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188486"
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Přidání a přiřazení aplikací pro ochranu před mobilními hrozbami (MTD) pomocí Intune

You can use Intune to add and deploy Mobile Threat Defense (MTD) apps so that end users can receive notifications when a threat is identified in their mobile devices, and to receive guidance to remediate the threats.

> [!NOTE]
> This article applies to all Mobile Threat Defense partners.

## <a name="before-you-begin"></a>Před zahájením

Complete the following steps in Intune. Ověřte si, že jste seznámení s těmito postupy:

- [Přidání aplikace do služby Intune](../apps/apps-add.md)
- [Přidání zásad konfigurace aplikace pro iOS do služby Intune](../apps/app-configuration-policies-use-ios.md)
- [Přiřazení aplikace pomocí služby Intune](../apps/apps-deploy.md)

> [!TIP]
> The Intune Company Portal works as the broker on Android devices so users can have their identities checked by Azure AD.

## <a name="configure-microsoft-authenticator-for-ios"></a>Konfigurace aplikace Microsoft Authenticator pro iOS

U zařízení se systémem iOS je potřeba [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), aby mohla být identita uživatelů ověřena pomocí Azure AD. Additionally, you need an iOS app configuration policy that sets the MTD iOS app you use with Intune.

Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](../apps/store-apps-ios.md). Use this [Microsoft Authenticator app store URL](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) when you configure **App information**.

## <a name="configure-mtd-applications"></a>Konfigurace aplikací MTD

Vyberte část, která odpovídá vašemu poskytovateli MTD:

- [Lookout for Work](#configure-lookout-for-work-apps)
- [Symantec Endpoint Protection Mobile (SEP Mobile)](#configure-symantec-endpoint-protection-mobile-apps)
- [Check Point SandBlast Mobile](#configure-check-point-sandblast-mobile-apps)
- [Zimperium](#configure-zimperium-apps)
- [Pradeo](#configure-pradeo-apps)
- [Better Mobile](#configure-better-mobile-apps)
- [Sophos Mobile](#configure-sophos-apps)
- [Wandera](#configure-wandera-apps)

### <a name="configure-lookout-for-work-apps"></a>Konfigurace aplikací Lookout for Work

- **Androidemem**
  - Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](../apps/store-apps-android.md). Use this [Lookout for work Google app store URL](https://play.google.com/store/apps/details?id=com.lookout.enterprise) for the **Appstore URL**.

- **iOS**
  - Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](../apps/store-apps-ios.md). Use this [Lookout for Work iOS app store URL](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) for the **Appstore URL**.

- **Aplikace Lookout for Work mimo obchod App Store společnosti Apple**
  - You must re-sign the Lookout for Work iOS app. Lookout distribuuje svou aplikaci Lookout for Work pro iOS mimo obchod App Store. Před distribucí této aplikace ji musíte znovu podepsat pomocí certifikátu podnikového vývojáře pro iOS.  
  - Podrobné pokyny k opětovnému podepsání aplikace Lookout for Work pro iOS najdete v článku [o opětovném podepsání aplikace Lookout for Word pro iOS](https://personal.support.lookout.com/hc/articles/114094038714) na webu Lookout.

  - **Povolení ověřování službou Azure AD v aplikaci Lookout for Work pro iOS uživateli**

    1. Přejděte na [portál Azure Portal](https://portal.azure.com), přihlaste se pomocí svých přihlašovacích údajů a přejděte na stránku aplikace.

    2. Přidejte **aplikaci Lookout for Work pro iOS** jako **nativní klientskou aplikaci**.

    3. Text **com.lookout.enterprise.názevfirmy** nahraďte identifikátorem zákaznického balíčku, který jste vybrali při podepisování IPA.

    4. Přidejte další identifikátor URI pro přesměrování: **&lt;companyportal://code/>** následovaný původním identifikátorem URI pro přesměrování ve verzi kódované v řetězci URL.

    5. Přidejte k aplikaci **Delegovaná oprávnění**.

    > [!NOTE]
    > Další podrobnosti najdete v článku o [konfiguraci nativní klientské aplikace pomocí Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

  - **Přidání souboru IPA aplikace Lookout for Work**

    - Upload the re-signed .ipa file as described in the [Add iOS LOB apps with Intune](../apps/lob-apps-ios.md) article. Kromě toho je potřeba nastavit jako minimální verzi operačního systému iOS 8.0 nebo novější.

### <a name="configure-symantec-endpoint-protection-mobile-apps"></a>Konfigurace aplikací Symantec Endpoint Protection Mobile

- **Androidemem**
  - Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](../apps/store-apps-android.md). Use this [SEP Mobile app store URL](https://play.google.com/store/apps/details?id=com.skycure.skycure) for the **Appstore URL**.  Jako **Minimální operační systém** vyberte **Android 4.0 (Ice Cream Sandwich)** .

- **iOS**
  - Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](../apps/store-apps-ios.md). Use this [SEP Mobile app store URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) for the **Appstore URL**.

### <a name="configure-check-point-sandblast-mobile-apps"></a>Konfigurace aplikací Check Point SandBlast Mobile

- **Androidemem**  
  - Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](../apps/store-apps-android.md). Use this [Check Point SandBlast Mobile app store URL](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) for the **Appstore URL**.

- **iOS**
  - Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](../apps/store-apps-ios.md). Use this [Check Point SandBlast Mobile app store URL](https://apps.apple.com/us/app/sandblast-mobile-protect/id1006390797) for the **Appstore URL**.  

### <a name="configure-zimperium-apps"></a>Konfigurace aplikací Zimperium

- **Androidemem**
  - Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](../apps/store-apps-android.md). Use this [Zimperium app store URL](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) for the **Appstore URL**.

- **iOS**
  - Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](../apps/store-apps-ios.md). Use this [Zimperium app store URL](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) for the **Appstore URL**.  
 
### <a name="configure-pradeo-apps"></a>Konfigurace aplikací Pradeo

- **Androidemem**
  - Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](../apps/store-apps-android.md). Use this [Pradeo app store URL](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US) for the **Appstore URL**.

- **iOS**
  - Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](../apps/store-apps-ios.md). Use this [Pradeo app store URL](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8) for the **Appstore URL**.

### <a name="configure-better-mobile-apps"></a>Konfigurace aplikací Better Mobile

- **Androidemem**
  - Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](../apps/store-apps-android.md). Use this [Active Shield app store URL](https://play.google.com/store/apps/details?id=com.better.active.shield.enterprise) for the **Appstore URL**.

- **iOS**
  - Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](../apps/store-apps-ios.md). Use this [ActiveShield app store URL](https://itunes.apple.com/us/app/activeshield/id980234260?mt=8&uo=4) for the **Appstore URL**.

### <a name="configure-sophos-apps"></a>Configure Sophos apps

- **Androidemem**
  - Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](../apps/store-apps-android.md). Use this [Sophos app store URL](https://play.google.com/store/apps/details?id=com.sophos.smsec) for the **Appstore URL**.

- **iOS**
  - Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](../apps/store-apps-ios.md). Use this [ActiveShield app store URL](https://itunes.apple.com/us/app/sophos-mobile-security/id1086924662?mt=8) for the **Appstore URL**.

### <a name="configure-wandera-apps"></a>Configure Wandera apps

- **Androidemem**
  - Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](../apps/store-apps-android.md). Use this [Wandera Mobile app store URL](https://play.google.com/store/apps/details?id=com.wandera.android) for the **Appstore URL**. For **Minimum operating system**, select **Android 5.0**.

- **iOS**
  - Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](../apps/store-apps-ios.md). Use this [Wandera Mobile app store URL](https://itunes.apple.com/app/wandera/id605469330) for the **Appstore URL**.

## <a name="configure-your-mtd-apps-with-an-ios-app-configuration-policy"></a>Konfigurace aplikací MTD k zásadám konfigurace aplikace pro iOS

### <a name="lookout-for-work-app-configuration-policy"></a>Zásady konfigurace aplikací pro Lookout for Work

Create the iOS app configuration policy as described in the [using iOS app configuration policy](../apps/app-configuration-policies-use-ios.md) article.

### <a name="sep-mobile-app-configuration-policy"></a>Zásady konfigurace aplikace SEP Mobile

Use the same Azure AD account previously configured in the [Symantec Endpoint Protection Management console](https://aad.skycure.com), which should be the same account used to sign in to the Intune.

- **Download** the iOS app configuration policy file:
  - Přejděte na [konzoly pro správu Symantec Endpoint Protection](https://aad.skycure.com) a přihlaste se pomocí svých přihlašovacích údajů správce.

  - Přejděte na **Settings** (Nastavení) a v části **Integrations** (Integrace) zvolte **Intune**. Zvolte **EMM Integration Selection** (Výběr integrace EMM). Zvolte **Microsoft** a pak svůj výběr uložte.

  - Klikněte na odkaz **Integration setup files** (Integrační soubory nastavení) a vygenerovaný soubor \*.zip uložte. Soubor .zip obsahuje soubor * **.plist**, který se použije k vytvoření zásad konfigurace aplikace pro iOS v Intune.

  - Pokud chcete přidat zásady konfigurace aplikace SEP Mobile pro iOS, přečtěte si pokyny ohledně [používání zásad konfigurace aplikací služby Microsoft Intune pro iOS](../apps/app-configuration-policies-use-ios.md).

    - For **Configuration settings format**, select **Enter XML data**, copy the content from the * **.plist** file, and paste its content into the configuration policy body.

> [!NOTE]
> Pokud se vám nedaří soubory načíst, obraťte se na [podporu Symantec Endpoint Protection Mobile pro firmy](https://support.symantec.com/en_US/contact-support.html).

### <a name="check-point-sandblast-mobile-app-configuration-policy"></a>Zásady konfigurace aplikace Check Point SandBlast Mobile

Pokud chcete přidat zásady konfigurace aplikace Check Point SandBlast Mobile pro iOS, přečtěte si pokyny ohledně [používání zásad konfigurace aplikací služby Microsoft Intune pro iOS](../apps/app-configuration-policies-use-ios.md).

- For **Configuration settings format**, select **Enter XML data**, copy the following content and paste it into the configuration policy body.

  `<dict><key>MDM</key><string>INTUNE</string></dict>`


### <a name="zimperium-app-configuration-policy"></a>Zásady konfigurace aplikace Zimperium

Pokud chcete přidat zásady konfigurace aplikace Zimperium pro iOS, přečtěte si pokyny ohledně [používání zásad konfigurace aplikací služby Microsoft Intune pro iOS](../apps/app-configuration-policies-use-ios.md).

- For **Configuration settings format**, select **Enter XML data**, copy the following content and paste it into the configuration policy body.

   ```
   <dict>
   <key>provider</key><string>Intune</string>
   <key>userprincipalname</key><string>{{userprincipalname}}</string>
   <key>deviceid</key>
   <string>{{deviceid}}</string>
   <key>serialnumber</key>
   <string>{{serialnumber}}</string>
   <key>udidlast4digits</key>
   <string>{{udidlast4digits}}</string>
   </dict>
   ```

### <a name="pradeo-app-configuration-policy"></a>Pradeo app configuration policy

Pradeo doesn't support application configuration policy on iOS.  Instead, to get a configured app, work with Pradeo to implement custom IPA or APK files that are preconfigured with the settings you want.

### <a name="better-mobile-app-configuration-policy"></a>Zásady konfigurace aplikace Better Mobile

Pokud chcete přidat zásady konfigurace aplikace Better Mobile pro iOS, přečtěte si pokyny ohledně [používání zásad konfigurace aplikací služby Microsoft Intune pro iOS](../apps/app-configuration-policies-use-ios.md).

- For **Configuration settings format**, select **Enter XML data**, copy the following content and paste it into the configuration policy body. Adresu URL `https://client.bmobi.net` nahraďte příslušnou adresou URL konzoly.

   ```
    <dict>
   <key>better_server_url</key>
   <string>https://client.bmobi.net</string>
   <key>better_udid</key>
   <string>{{aaddeviceid}}</string>
   <key>better_user</key>
   <string>{{userprincipalname}}</string>
   </dict>
   ```

### <a name="sophos-mobile-app-configuration-policy"></a>Sophos Mobile app configuration policy

Create the iOS app configuration policy as described in the [using iOS app configuration policy](../apps/app-configuration-policies-use-ios.md) article.

### <a name="wandera-app-configuration-policy"></a>Wandera app configuration policy

See the instructions for [using Microsoft Intune app configuration policies for iOS](../apps/app-configuration-policies-use-ios.md) to add the Wandera iOS app configuration policy.

- For **Configuration settings format**, select **Enter XML data**.

Sign in to your RADAR Wandera portal and browse to **Settings** > **EMM Integration** > **App Push**. Select **Intune**, and then copy the content below and paste it into the configuration policy body.  

  ```
  <dict><key>secretKey</key>
  <string>SeeRADAR</string>
  <key>apiKey</key>
  <string> SeeRADAR </string>
  <key>customerId</key>
  <string> SeeRADAR </string>
  <key>email</key>
  <string>{{mail}}</string>
  <key>firstName</key>
  <string>{{username}}</string>
  <key>lastName</key>
  <string></string>
  <key>activationType</key>
  <string>PROVISION_THEN_AWP</string></dict>
  ```

## <a name="assign-apps-to-groups"></a>Přiřazení aplikací skupinám

Tento krok platí pro všechny partnery MTD. Přečtěte si pokyny pro [přiřazení aplikací do skupin pomocí Intune](../apps/apps-deploy.md).

## <a name="next-steps"></a>Další kroky

- [Konfigurace zásad dodržování předpisů zařízení pro MTD](mtd-device-compliance-policy-create.md)
