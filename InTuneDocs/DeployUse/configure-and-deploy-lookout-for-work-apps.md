---
title: "Nasazení aplikace Lookout for Work | Microsoft Intune"
description: "Konfigurace a nasazení aplikace Lookout for Work pro Android."
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 557c1b3b36adf40ec4ad94f22ed7bb9705c6eec4
ms.openlocfilehash: 5c6a5848c447c0eacbdfa166962a47b1299c2b74


---

# Konfigurace a nasazení aplikací Lookout for Work
Tento článek vysvětluje, jak nakonfigurovat a nasadit aplikaci Lookout for Work u zařízení s Androidem a iOS.

## Android (aplikace v obchodě Google Play)

* **Krok 1:** V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) přejděte do části **Aplikace** a vyberte možnost **Přidat aplikace**.   
* **Krok 2:** U vydavatele na stránce **Instalace softwaru** zvolte **Externí odkaz** a zadejte následující adresu URL:  https://play.google.com/store/apps/details?id=com.lookout.enterprise
>[!NOTE]
>Nezaškrtávejte políčko, aby byl požadován spravovaný prohlížeč.

* **Krok 3:** Na stránce **Popis softwaru** zadejte následující informace:
  * **Vydavatel:** Lookout Mobile Security
  * **Název:** Lookout for Work
  * **Popis:** Aplikace Lookout nabízí nejlepší ochranu před mobilními hrozbami a udržuje vaše zařízení v bezpečí. Aplikace Lookout po instalaci zařízení chrání před hrozbami a v případě, že nějaké nalezne, upozorní na to vás i správce společnosti.
  * **Kategorie:** Správa počítačů
* **Krok 4:** Po úspěšném dokončení se zobrazí zpráva **Nahrávání dat do Microsoft Intune úspěšně skončilo.**.

V konzole služby Intune se po kliknutí na položku **Aplikace** v seznamu zobrazí aplikace Lookout for Work ![snímek stránky konzolových aplikací správce Intune zobrazující aplikace Lookout for Work v seznamu](../media/mtp/lookout-app-listed-intune-console.png)

* **Krok 5**: Aplikaci nasadíte uživatelům tak, že vyberete aplikaci Lookout for Work a zvolíte **Spravovat nasazení**.

  Je nutné vybrat stejné uživatele, jako jste přidali v možnosti Správa registrací v konzole Lookout MTP.  Další informace o přidávání skupin uživatelů do konzole Lookout MTP naleznete v kroku 3 části [Konfigurace předplatného pro Lookout MTP](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp).
  >[!IMPORTANT]
  > Průvodce nasazením aplikací služby Intune nezná skupiny uživatelů Azure AD a používá místo toho skupiny uživatelů Intune. Proto je nutné vytvořit novou skupinu uživatelů Intune, které bude založená na skupině uživatelů Azure AD registrované v konzole Lookout MTP, jak je popsáno v [tomto](plan-your-user-and-device-groups.md) tématu.

* **Krok 6**: Zvolte možnost **Požadovaná instalace**, aby byla instalace aplikace Lookout v zařízení uživatele povinná.


## iOS (verze aplikace Lookout podepsaná podnikem)

* **Krok 1:** Ověřte, že je na vašem zařízení povolená **Správa iOS**. Pokyny, jak na zařízení povolit správu iOS, najdete v článku [Nastavení správy zařízení s iOS a Mac](set-up-ios-and-mac-management-with-microsoft-intune.md).

* **Krok 2:** **Znovu podepište** aplikaci Lookout for Work pro iOS. Lookout distribuuje svou aplikaci Lookout for Work pro iOS mimo obchod App Store. **Před distribucí této aplikace** ji musíte znovu podepsat pomocí certifikátu podnikového vývojáře pro iOS. Podrobné pokyny k opětovnému podepsání aplikace Lookout for Work pro iOS najdete v článku [Lookout for Work iOS app re-signing process](https://personal.support.lookout.com/hc/en-us/articles/114094038714) (Postup opětovného podepsání aplikace Lookout for Work pro iOS) na webu Lookout.


* **Krok 3:** Následujícím postupem povolte ověřování uživatelů iOS službou Azure Active Directory:
  1.  Přihlaste se na [portál pro správu služby Azure Active Directory](https://manage.windowsazure.com) a přejděte na stránku s aplikacemi.
  2.  Přidejte **aplikaci Lookout for Work pro iOS** jako **nativní klientskou aplikaci**.
  ![Snímek obrazovky s dialogem pro přidání aplikace zobrazující možnost nativní klientské aplikace](../media/mtp/aad-add-app.png)

  3. Text **com.lookout.enterprise.názevfirmy** nahraďte identifikátorem zákaznického balíčku, který jste vybrali při podepisování IPA.
  4.  Přidejte další identifikátor URI pro přesměrování: **&lt;companyportal://code/>** následovaný původním identifikátorem URI pro přesměrování ve verzi URLencoded.
  5.  Přidejte k aplikaci **Delegovaná oprávnění**.

  Další podrobnosti najdete v článku [Konfigurace nativní klientské aplikace](https://azure.microsoft.com/en-us/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).


* **Krok 4:** Nahrajte opětovně podepsaný soubor .ipa podle popisu v tématu [Přidání aplikace pro mobilní zařízení v Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune). Jako minimální verzi operačního systému nastavte iOS 8.0 nebo novější.

  ![Snímek obrazovky stránky s aplikacemi v konzole pro správce Intune s aplikací Lookout for Work zobrazenou v seznamu aplikací](../media/mtp/ios-app-uploaded-intune.png)

* **Krok 5:** Vytvořte zásady konfigurace spravovaných aplikací podle popisu v tématu [Konfigurace aplikací pro iOS pomocí zásad konfigurace mobilních aplikací v Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

  ![Snímek obrazovky s průvodcem vytvořením nové zásady a zvýrazněnou zásadou konfigurace aplikace pro iOS 8.0 nebo novější](../media/mtp/ios-app-config.png)

* **Krok 6:** **Aplikaci nasadíte uživatelům** tak, že vyberete aplikaci Lookout for Work a zvolíte **Spravovat nasazení**.

  Musíte vybrat stejné uživatele, které jste přidali v konzole Lookout v možnosti Správa registrací.  Další informace o přidávání skupin uživatelů do konzole Lookout MTP najdete v kroku 3 části [Konfigurace předplatného pro ochranu zařízení před internetovými útoky ve službě Lookout](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp).
>[!IMPORTANT]
> Průvodce nasazením aplikací služby Intune nezná skupiny uživatelů Azure AD a používá místo toho skupiny uživatelů Intune. Proto je nutné vytvořit novou skupinu uživatelů Intune, která bude založená na skupině uživatelů Azure AD registrované v konzole Lookout, jak je popsáno v [tomto tématu](plan-your-user-and-device-groups.md).

Zvolte možnost **Požadovaná instalace**, aby byla instalace aplikace Lookout v zařízení uživatele povinná.

## Co se stane, když se nasazená aplikace otevře v zařízení




Když uživatel v zařízení otevře aplikaci Lookout for Work, bude vyzván, aby aplikaci aktivoval a zvolil možnost Přihlásit pomocí Azure Active Directory. Podrobný návod s postupem pro koncového uživatele najdete v následujících tématech:

* [Zobrazí se výzva k instalaci aplikace Lookout for Work na zařízení s Androidem](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Je třeba vyřešit hrozbu, kterou aplikace Lookout for Work objevila na vašem zařízení s Androidem](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Další kroky
* [Povolení pravidla ochrany zařízení před hrozbami v zásadách dodržování předpisů](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Oct16_HO4-->


