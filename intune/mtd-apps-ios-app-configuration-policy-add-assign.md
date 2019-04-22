---
title: Přidání a přiřazení aplikací pro ochranu před mobilními hrozbami (MTD) do Microsoft Intune
titleSuffix: Microsoft Intune
description: Pomocí Intune můžete přidat aplikace pro ochranu před mobilními hrozbami (MTD), aplikaci Microsoft Authenticator a zásady konfigurace iOS na portálu Azure Portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a3e9c9c538f9311da4c383b5de24048eb836ab0a
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59899580"
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Přidání a přiřazení aplikací pro ochranu před mobilními hrozbami (MTD) pomocí Intune

> [!NOTE] 
> Toto téma se týká všech partnerů ochrany před mobilními hrozbami.

Intune můžete použít k přidání a nasazení aplikací Mobile Threat Defense (MTD) tak, aby koncoví uživatelé mohli dostávat oznámení, když je v jejich mobilních zařízeních identifikována hrozba a získat pokyny k nápravě těchto hrozeb.


## <a name="before-you-begin"></a>Před zahájením

Níže uvedený postup musíte provést na [portálu Azure Portal](https://portal.azure.com/). Ověřte si, že jste seznámení s těmito postupy:

  -   [Přidání aplikace do služby Intune](apps-add.md)
  -   [Přidání zásad konfigurace aplikace pro iOS do služby Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)
  -   [Přiřazení aplikace pomocí služby Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune)

> [!TIP]
> Aplikace portál společnosti Intune funguje jako zprostředkovatel pro zařízení s Androidem aby mohla být identita uživatelů ověřit ve službě Azure AD uživatelů.

## <a name="configure-microsoft-authenticator-for-ios"></a>Konfigurace aplikace Microsoft Authenticator pro iOS
U zařízení se systémem iOS je potřeba [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), aby mohla být identita uživatelů ověřena pomocí Azure AD. Kromě toho potřebujete zásady Konfigurace aplikace iOS, která nastavuje aplikace MTD pro iOS, které používáte s Intune.

Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](store-apps-ios.md). V **kroku 12** v části **Konfigurace informací o aplikaci** použijte tento [odkaz URL na Microsoft Authenticator v obchodě s aplikacemi](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8).

## <a name="configure-mtd-applications"></a>Konfigurace aplikací MTD

Vyberte část, která odpovídá vašemu poskytovateli MTD:

  - [Lookout for Work](#configure-lookout-for-work-apps)
  - [Symantec Endpoint Protection Mobile (SEP Mobile)](#configure-symantec-endpoint-protection-mobile-apps)
  - [Check Point SandBlast Mobile](#configure-check-point-sandblast-mobile-apps)
  - [Zimperium](#configure-zimperium-apps)
  - [Pradeo](#configure-pradeo-apps)
  - [Better Mobile](#configure-better-mobile-apps)

### <a name="configure-lookout-for-work-apps"></a>Konfigurace aplikací Lookout for Work

- **Android**
  - Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](store-apps-android.md). V **kroku 7** použijte tento [odkaz URL na Lookout for Work v obchodě s aplikacemi Google](https://play.google.com/store/apps/details?id=com.lookout.enterprise).

- **iOS**

  - Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](store-apps-ios.md). V **kroku 12** v části **Konfigurace informací o aplikaci** použijte tento [odkaz URL na aplikaci Lookout for Work pro iOS v App Storu](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8).

-   **Aplikace Lookout for Work mimo obchod App Store společnosti Apple**
    - Je potřeba, abyste aplikaci Lookout for Word pro iOS znovu podepsali. Lookout distribuuje svou aplikaci Lookout for Work pro iOS mimo obchod App Store. Před distribucí této aplikace ji musíte znovu podepsat pomocí certifikátu podnikového vývojáře pro iOS.
    - Podrobné pokyny k opětovnému podepsání aplikace Lookout for Work pro iOS najdete v článku [o opětovném podepsání aplikace Lookout for Word pro iOS](https://personal.support.lookout.com/hc/articles/114094038714) na webu Lookout.

    - **Povolení ověřování službou Azure AD v aplikaci Lookout for Work pro iOS uživateli**

        1. Přejděte na [portál Azure Portal](https://portal.azure.com), přihlaste se pomocí svých přihlašovacích údajů a přejděte na stránku aplikace.

        2. Přidejte **aplikaci Lookout for Work pro iOS** jako **nativní klientskou aplikaci**.

        3. Text **com.lookout.enterprise.názevfirmy** nahraďte identifikátorem zákaznického balíčku, který jste vybrali při podepisování IPA.

        4.  Přidejte další identifikátor URI pro přesměrování: **&lt;companyportal://code/>** následovaný původním identifikátorem URI pro přesměrování ve verzi kódované v řetězci URL.

        5.  Přidejte k aplikaci **Delegovaná oprávnění**.

        > [!NOTE] 
        > Další podrobnosti najdete v článku o [konfiguraci nativní klientské aplikace pomocí Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

     - **Přidání souboru IPA aplikace Lookout for Work**

        - Podle popisu v tématu [Přidání obchodních aplikací pro iOS do Microsoft Intune](lob-apps-ios.md) nahrajte opětovně podepsaný soubor .ipa. Kromě toho je potřeba nastavit jako minimální verzi operačního systému iOS 8.0 nebo novější.

### <a name="configure-symantec-endpoint-protection-mobile-apps"></a>Konfigurace aplikací Symantec Endpoint Protection Mobile

 - **Android**

    - Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](store-apps-android.md). V **kroku 7** použijte tento [odkaz URL na SEp Mobile v obchodě s aplikacemi](https://play.google.com/store/apps/details?id=com.skycure.skycure).  Jako **Minimální operační systém** vyberte **Android 4.0 (Ice Cream Sandwich)**.

 - **iOS**

    - Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](store-apps-ios.md). V **kroku 12** v části **Konfigurace informací o aplikaci** použijte tento [odkaz URL na SEP Mobile v obchodě s aplikacemi](https://itunes.apple.com/us/app/skycure/id695620821?mt=8).

### <a name="configure-check-point-sandblast-mobile-apps"></a>Konfigurace aplikací Check Point SandBlast Mobile

 - **Android**

    - Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](store-apps-android.md). V **kroku 7** použijte tuto [adresu URL na Check Point SandBlast Mobile v obchodě s aplikacemi](https://play.google.com/store/apps/details?id=com.lacoon.security.fox).

 - **iOS**

    - Pokud chcete získat aplikaci pro iOS, obraťte se na [Check Point SandBlast Mobile](https://www.checkpoint.com/products/sandblast-mobile/). Přečtěte si pokyny pro [přidání aplikací z iOS Storu do Microsoft Intune](store-apps-ios.md), pak v **kroku 12** v části **Konfigurace informací o aplikaci** použijte adresu URL obchodu App Store společnosti Apple.

### <a name="configure-zimperium-apps"></a>Konfigurace aplikací Zimperium

 - **Android**

    - Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](store-apps-android.md). V **kroku 7** použijte tento [odkaz URL na Zimperium v obchodě s aplikacemi](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en).

 - **iOS**

    - Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](store-apps-ios.md). V **kroku 12** v části **Konfigurace informací o aplikaci** použijte tento [odkaz URL na Zimperium v obchodě s aplikacemi](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8).

### <a name="configure-pradeo-apps"></a>Konfigurace aplikací Pradeo

 - **Android**

    - Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](store-apps-android.md). V **kroku 7** použijte tento [odkaz URL na Pradeo v obchodě s aplikacemi](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US).

 - **iOS**

    - Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](store-apps-ios.md). V **kroku 12** v části **Konfigurace informací o aplikaci** použijte tento [odkaz URL na Pradeo v obchodě s aplikacemi](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8).

### <a name="configure-better-mobile-apps"></a>Konfigurace aplikací Better Mobile

 - **Android**

    - Přečtěte si pokyny pro [přidávání aplikací z Android Storu do Microsoft Intune](store-apps-android.md). V **kroku 7** použijte [tento odkaz URL na Active Shield v obchodě s aplikacemi](https://play.google.com/store/apps/details?id=com.better.active.shield.enterprise).

 - **iOS**

    - Přečtěte si pokyny pro [přidávání aplikací z iOS Storu do Microsoft Intune](store-apps-ios.md). V **kroku 12** v části **Konfigurace informací o aplikaci** použijte tento [odkaz URL na ActiveShield v obchodě s aplikacemi](https://itunes.apple.com/us/app/activeshield/id980234260?mt=8&uo=4).

## <a name="configure-your-mtd-apps-with-an-ios-app-configuration-policy"></a>Konfigurace aplikací MTD k zásadám konfigurace aplikace pro iOS

### <a name="lookout-for-work-app-configuration-policy"></a>Zásady konfigurace aplikací pro Lookout for Work

- Jak je popsáno v vytvořte zásady Konfigurace aplikací pro iOS [pomocí zásad Konfigurace aplikace pro iOS](app-configuration-policies-use-ios.md) článku.

### <a name="sep-mobile-app-configuration-policy"></a>Zásady konfigurace aplikace SEP Mobile

-   Účet použijte stejnou službou Azure AD, které jste dříve nakonfigurovali v [konzole pro správu aplikace Symantec Endpoint Protection](https://aad.skycure.com), který by měl být stejný účet použili k přihlášení na klasickém portálu Intune.

-   Musíte **stáhnout** soubor zásad konfigurace aplikace pro iOS: 
    -   Přejděte na [konzoly pro správu Symantec Endpoint Protection](https://aad.skycure.com) a přihlaste se pomocí svých přihlašovacích údajů správce.

    -   Přejděte na **Settings** (Nastavení) a v části **Integrations** (Integrace) zvolte **Intune**. Zvolte **EMM Integration Selection** (Výběr integrace EMM). Zvolte **Microsoft** a pak svůj výběr uložte.

    -   Klikněte na odkaz **Integration setup files** (Integrační soubory nastavení) a vygenerovaný soubor \*.zip uložte. Soubor .zip obsahuje soubor ***.plist**, který se použije k vytvoření zásad konfigurace aplikace pro iOS v Intune.

    -   Pokud chcete přidat zásady konfigurace aplikace SEP Mobile pro iOS, přečtěte si pokyny ohledně [používání zásad konfigurace aplikací služby Microsoft Intune pro iOS](app-configuration-policies-use-ios.md).

    - V **kroku 8** použijte možnost **Zadat XML data**, zkopírujte obsah ze souboru ***.plist** a vložte ho do těla zásad konfigurace.

> [!NOTE]
> Pokud se vám nedaří soubory načíst, obraťte se na [podporu Symantec Endpoint Protection Mobile pro firmy](https://support.symantec.com/en_US/contact-support.html).

### <a name="check-point-sandblast-mobile-app-configuration-policy"></a>Zásady konfigurace aplikace Check Point SandBlast Mobile

- Pokud chcete přidat zásady konfigurace aplikace Check Point SandBlast Mobile pro iOS, přečtěte si pokyny ohledně [používání zásad konfigurace aplikací služby Microsoft Intune pro iOS](app-configuration-policies-use-ios.md).
    - V **kroku 8** použijte možnost **Zadat XML data**, zkopírujte obsah níže a vložte ho do těla zásad konfigurace.

```
<dict><key>MDM</key><string>INTUNE</string></dict>
```

### <a name="zimperium-app-configuration-policy"></a>Zásady konfigurace aplikace Zimperium

- Pokud chcete přidat zásady konfigurace aplikace Zimperium pro iOS, přečtěte si pokyny ohledně [používání zásad konfigurace aplikací služby Microsoft Intune pro iOS](app-configuration-policies-use-ios.md).
    - V **kroku 8** použijte možnost **Zadat XML data**, zkopírujte obsah níže a vložte ho do těla zásad konfigurace.

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

### <a name="better-mobile-app-configuration-policy"></a>Zásady konfigurace aplikace Better Mobile

- Pokud chcete přidat zásady konfigurace aplikace Better Mobile pro iOS, přečtěte si pokyny ohledně [používání zásad konfigurace aplikací služby Microsoft Intune pro iOS](app-configuration-policies-use-ios.md).
    - V **kroku 8** použijte možnost **Zadat XML data**, zkopírujte obsah níže a vložte ho do těla zásad konfigurace. Adresu URL `https://client.bmobi.net` nahraďte příslušnou adresou URL konzoly.

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

## <a name="assign-apps-to-groups"></a>Přiřazení aplikací skupinám

- Tento krok platí pro všechny partnery MTD. Přečtěte si pokyny pro [přiřazení aplikací do skupin pomocí Intune](apps-deploy.md).

## <a name="next-steps"></a>Další postup

- [Konfigurace zásad dodržování předpisů zařízení pro MTD](mtd-device-compliance-policy-create.md)
