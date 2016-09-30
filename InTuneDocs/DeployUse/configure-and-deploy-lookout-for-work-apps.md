---
title: "Nasazení aplikace Lookout for Work | Microsoft Intune"
description: "Konfigurace a nasazení aplikace Lookout for Work pro Android."
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c4d05b9ba7249e4068d21480b1c9db342277757e
ms.openlocfilehash: 687a102ccb34cb7acfaab1e8a1d4b67cb54b9e92


---

# Konfigurace a nasazení aplikací Lookout for Work
V tomto článku se dozvíte, jak nakonfigurovat a nasadit aplikaci Lookout for Work do registrovaných zařízení se systémem Android 4.1 nebo novějším.

* **Krok 1:** V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) přejděte do části **Aplikace** a vyberte možnost **Přidat aplikace**.   
* **Krok 2:** U vydavatele na stránce **Instalace softwaru** zvolte **Externí odkaz** a zadejte následující adresu URL: https://play.google.com/store/apps/details?id=com.lookout.enterprise
>[!NOTE]
>Nezaškrtávejte políčko, aby byl požadován spravovaný prohlížeč.

* **Krok 3:** Na stránce **Popis softwaru** zadejte následující informace:
  * **Vydavatel:** Lookout Mobile Security
  * **Název:** Lookout for Work
  * **Popis:** Aplikace Lookout nabízí nejlepší ochranu před mobilními hrozbami a udržuje vaše zařízení v bezpečí. Aplikace Lookout po instalaci chrání zařízení před hrozbami a v případě, že nějaké nalezne, upozorní na to vás i správce společnosti.
  * **Kategorie:** Správa počítačů
* **Krok 4:** Po úspěšném dokončení se zobrazí zpráva **Nahrávání dat do Microsoft Intune bylo úspěšně dokončeno**.

Když v konzole správce Intune kliknete na položku **Aplikace**, v seznamu uvidíte aplikaci Lookout for Work ![snímek stránky aplikací v konzole správce Intune zobrazující aplikace Lookout for Work v seznamu](../media/mtp/lookout-app-listed-intune-console.png)

**Pokud chcete aplikaci nasadit uživatelům**, vyberete aplikaci Lookout for Work na obrazovce výše a potom zvolte **Spravovat nasazení**.

Je nutné vybrat stejné uživatele, které jste přidali v možnosti Správa registrací v konzole Lookout MTP.  Další informace o přidávání skupin uživatelů do konzole Lookout MTP naleznete v kroku 3 části [Konfigurace předplatného pro Lookout MTP](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp).
>[!IMPORTANT]
> Průvodce nasazením aplikací služby Intune nezná skupiny uživatelů Azure AD a používá místo toho skupiny uživatelů Intune. Proto je nutné vytvořit novou skupinu uživatelů Intune, která bude založená na skupině uživatelů Azure AD registrované v konzole Lookout MTP, jak je popsáno v [tomto tématu](plan-your-user-and-device-groups.md).

Zvolte možnost **Požadovaná instalace**, aby byla instalace aplikace Lookout v zařízení uživatele povinná.


Když je pro vaše nasazení zvolena možnost **Požadovaná instalace**, Intune odešle aplikaci Lookout for Work do zařízení.   

Když uživatel v zařízení otevře aplikaci Lookout for Work, bude vyzván, aby aplikaci aktivoval a zvolil možnost Přihlásit pomocí Azure Active Directory. Podrobný návod s postupem pro koncového uživatele najdete v následujících tématech:

* [Zobrazí se výzva k instalaci aplikace Lookout for Work na zařízení s Androidem](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Je třeba vyřešit hrozbu, kterou aplikace Lookout for Work objevila na vašem zařízení s Androidem](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Další kroky
* [Povolení pravidla ochrany zařízení před hrozbami v zásadách dodržování předpisů](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Sep16_HO3-->


