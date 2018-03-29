---
title: Nasazení aplikace Lookout for Work
description: Konfigurace a nasazení aplikace Lookout for Work pro Android.
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/21/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5d56dcf54c4f087dbea0dfcd95a2eebbdf384c00
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="configure-and-deploy-lookout-for-work-app"></a>Konfigurace a nasazení aplikace Lookout for Work

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Tento článek vysvětluje, jak nakonfigurovat a nasadit aplikaci Lookout for Work u zařízení s Androidem a iOS.

## <a name="android-google-play-store-app"></a>Android (aplikace v obchodě Google Play)

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) přejděte na **Aplikace** a zvolte **Přidat aplikace**.
2.  Na stránce vydavatele **Instalace softwaru** zvolte **Externí odkaz** a zadejte tuto adresu URL: https://play.google.com/store/apps/details?id=com.lookout.enterprise
  >[!NOTE]
  >Nezaškrtávejte políčko, aby byl požadován spravovaný prohlížeč.

3.  Na stránce **Popis softwaru** zadejte následující informace:
  * **Vydavatel:** Lookout Mobile Security
  * **Název:** Lookout for Work
  * **Popis:** Aplikace Lookout nabízí nejlepší ochranu před mobilními hrozbami a udržuje vaše zařízení v bezpečí. Aplikace Lookout po instalaci zařízení chrání před hrozbami a v případě, že nějaké nalezne, upozorní na to vás i správce společnosti.
  * **Kategorie:** Správa počítačů

4. Po úspěšném dokončení se zobrazí zpráva **Nahrávání dat do Microsoft Intune úspěšně skončilo**.

  V konzole Intune se po kliknutí na **Aplikace** zobrazí v seznamu aplikace **Lookout for Work** ![snímek stránky konzolových aplikací správce Intune zobrazující aplikace Lookout for Work v seznamu](../media/mtp/lookout-app-listed-intune-console.png)

5. Aplikaci nasadíte uživatelům tak, že vyberete aplikaci Lookout for Work a zvolíte **Spravovat nasazení**.

  Je nutné vybrat stejné uživatele, jako jste přidali v možnosti Správa registrací v konzole Lookout MTP.  Další informace o přidávání skupin uživatelů do konzole Lookout MTP naleznete v kroku 3 části [Konfigurace předplatného pro Lookout MTP](configure-deploy-lookout-for-work-app.md).

  >[!IMPORTANT]
  > Průvodce nasazením aplikací služby Intune nezná skupiny uživatelů Azure AD a používá místo toho skupiny uživatelů Intune. Proto je nutné vytvořit novou skupinu uživatelů Intune, které bude založená na skupině uživatelů Azure AD registrované v konzole Lookout MTP, jak je popsáno v [tomto](plan-your-user-and-device-groups.md) tématu.

6. Zvolte možnost **Požadovaná instalace**, aby byla instalace aplikace Lookout v zařízení uživatele povinná.

## <a name="ios-enterprise-signed-version-of-lookout-app"></a>iOS (verze aplikace Lookout podepsaná podnikem)

1. Ověřte, že je na vašem zařízení povolená **Správa iOS**. Pokyny, jak na zařízení povolit správu iOSu, najdete v článku [Nastavení správy zařízení s iOSem a MacOS](set-up-ios-and-mac-management-with-microsoft-intune.md).

2. **Znovu podepište** aplikaci Lookout for Work pro iOS. Lookout distribuuje svou aplikaci Lookout for Work pro iOS mimo obchod App Store. **Před distribucí této aplikace** ji musíte znovu podepsat pomocí certifikátu podnikového vývojáře pro iOS. Podrobné pokyny k opětovnému podepsání aplikace Lookout for Work pro iOS najdete v článku [Lookout for Work iOS app re-signing process](https://personal.support.lookout.com/hc/articles/114094038714) (Postup opětovného podepsání aplikace Lookout for Work pro iOS) na webu Lookout.

3. Následujícím postupem povolte ověřování uživatelů iOS službou Azure Active Directory:
  1.  Přihlaste se na [portál pro správu služby Azure Active Directory](https://manage.windowsazure.com) a přejděte na stránku s aplikacemi.
  2.  Přidejte **aplikaci Lookout for Work pro iOS** jako **nativní klientskou aplikaci**.
  ![snímek obrazovky s dialogem pro přidání aplikace zobrazující možnost nativní klientské aplikace](../media/mtp/aad-add-app.png)
  3. Text **com.lookout.enterprise.názevfirmy** nahraďte identifikátorem zákaznického balíčku, který jste vybrali při podepisování IPA.
  4.  Přidejte další identifikátor URI pro přesměrování: **&lt;companyportal://code/>** následovaný původním identifikátorem URI pro přesměrování ve verzi URLencoded.
  5.  Přidejte k aplikaci **Delegovaná oprávnění**.

  Další podrobnosti najdete v článku [Konfigurace nativní klientské aplikace](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

4. Podle popisu v tématu [Přidání aplikace pro mobilní zařízení v Microsoft Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) nahrajte opětovně podepsaný soubor .ipa. Jako minimální verzi operačního systému nastavte iOS 8.0 nebo novější.

  ![Snímek obrazovky stránky s aplikacemi v konzole pro správce Intune s aplikací Lookout for Work zobrazenou v seznamu aplikací](../media/mtp/ios-app-uploaded-intune.png)

5. Vytvořte zásady konfigurace spravovaných aplikací podle popisu v tématu [Konfigurace aplikací pro iOS pomocí zásad konfigurace mobilních aplikací v Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

  ![Snímek obrazovky s průvodcem vytvořením nové zásady a zvýrazněnou zásadou konfigurace aplikace pro iOS 8.0 nebo novější](../media/mtp/ios-app-config.png)

6. **Aplikaci nasadíte uživatelům** tak, že vyberete aplikaci Lookout for Work a zvolíte **Spravovat nasazení**.

  Musíte vybrat stejné uživatele, které jste přidali v konzole Lookout v možnosti Správa registrací.  Další informace o přidávání skupin uživatelů do konzoly Lookout MTP naleznete v kroku 3 části [Konfigurace předplatného Lookout](https://docs.microsoft.com/sccm/protect/deploy-use/configure-and-deploy-lookout-for-work-apps).

  >[!IMPORTANT]
  > Průvodce nasazením aplikací služby Intune nezná skupiny uživatelů Azure AD a používá místo toho skupiny uživatelů Intune. Proto je nutné vytvořit novou skupinu uživatelů Intune, která bude založená na skupině uživatelů Azure AD registrované v konzole Lookout, jak je popsáno v [tomto tématu](plan-your-user-and-device-groups.md).

  Zvolte možnost **Požadovaná instalace**, aby byla instalace aplikace Lookout v zařízení uživatele povinná.

## <a name="what-happens-when-the-deployed-app-is-opened-on-the-device"></a>Co se stane, když se nasazená aplikace otevře v zařízení
https://github.com/Microsoft/Docs/blob/master/ContributorGuide/index.md Když uživatel v zařízení otevře aplikaci Lookout for Work, bude vyzván, aby aplikaci aktivoval a zvolil možnost Přihlásit pomocí Azure Active Directory. Podrobný návod s postupem pro koncového uživatele najdete v následujících tématech:

* [Zobrazuje se výzva k instalaci aplikace Lookout for Work na zařízení s Androidem](https://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android)

* [Je třeba vyřešit hrozbu, kterou objevila aplikace Lookout for Work na zařízení s Androidem](https://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## <a name="next-steps"></a>Další kroky
* [Vytváření zásad dodržování předpisů zařízením pro službu Lookout ve službě Intune](https://docs.microsoft.com/sccm/protect/deploy-use/enable-device-threat-protection-rule-compliance-policy)
