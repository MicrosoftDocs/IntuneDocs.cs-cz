---
title: "Nasazení aplikace Lookout for Work | Microsoft Intune"
description: "Konfigurace a nasazení aplikace Lookout for Work pro Android."
author: karthikaraman
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
ms.sourcegitcommit: 99005e15268a60cd801ef1c717088dff2f82927b
ms.openlocfilehash: 8dce0689d5c4a0672b227eedf3ae738217eb17cf


---

# Konfigurace a nasazení aplikací Lookout for Work
Tento článek vysvětluje, jak nakonfigurovat a nasadit aplikaci Lookout for Work u zařízení s Androidem a iOS.

## Android (aplikace v obchodě Google Play)

* **Krok 1:** Nahrajte aplikaci Lookout for Work pro Android do [konzoly pro správce Microsoft Intune](https://manage.microsoft.com) podle popisu v tématu [Přidání aplikací pro mobilní zařízení v Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune).
>[!NOTE]
> Nezaškrtávejte políčko, aby byl požadován spravovaný prohlížeč.

![Snímek obrazovky se stránkou aplikací v konzole pro správce Intune zobrazující v seznamu aplikaci Lookout for Work](../media/mtp/lookout-app-listed-intune-console.png)

* **Krok 2:** Nasaďte aplikaci uživatelům. Vyberte aplikaci Lookout for Work na obrazovce výše a pak vyberte **Spravovat nasazení**.

  Musíte vybrat stejné uživatele, které jste přidali v konzole Lookout v možnosti Správa registrací.  Další informace o přidávání skupin uživatelů do konzole Lookout MTP najdete v kroku 3 části [Konfigurace předplatného pro ochranu zařízení před internetovými útoky ve službě Lookout](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp).
>[!IMPORTANT]
> Průvodce nasazením aplikací služby Intune nezná skupiny uživatelů Azure AD a používá místo toho skupiny uživatelů Intune. Proto je nutné vytvořit novou skupinu uživatelů Intune, která bude založená na skupině uživatelů Azure AD registrované v konzole Lookout, jak je popsáno v [tomto tématu](plan-your-user-and-device-groups.md).

Zvolte možnost **Požadovaná instalace**, aby byla instalace aplikace Lookout v zařízení uživatele povinná.


## iOS (verze aplikace Lookout podepsaná podnikem)

* **Krok 1:** Ověřte, že je na vašem zařízení povolená **Správa iOS**. Pokyny, jak na zařízení povolit správu iOS, najdete v článku [Nastavení správy zařízení s iOS a Mac](Set up iOS and Mac device management.md).

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



<!--HONumber=Oct16_HO2-->


