---
title: "Referenční informace o zásadách konfigurace | Microsoft Intune"
description: "Informace v tomto tématu vám pomohou rozhodnout, jaké zásady Microsoft Intune byste měli používat ke správě svých zařízení."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d27f2739-9791-4aae-a9db-01a4e59ccfe5
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 50bfa96a334f2253550e1344179dc99b8ac68817


---

# Referenční informace o zásadách Microsoft Intune

Informace v tomto tématu vám pomohou rozhodnout, které zásady konfigurace Microsoft Intune byste měli používat ke správě svých zařízení.

> [!TIP]
> Podrobnější informace o používání zásad najdete v tématu [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).


## Zásady konfigurace pro Android

|Název zásady|Použijte v případě, že chcete|
|---------------|------------------------|
|**Vlastní konfigurace (Android 4 nebo novější, Samsung KNOX Standard 4.0 a novější)**|Nasadit nastavení OMA-URI, třeba nastavení Wi-Fi, která se dají použít k ovládání funkcí na zařízeních. To je užitečné, když nastavení, které potřebujete, není k dispozici v zásadách konfigurace.<br /><br />Podrobnosti najdete v tématu [Nastavení zásad pro Android v Microsoft Intune](android-policy-settings-in-microsoft-intune.md).|
|**E-mailový profil (Samsung KNOX Standard 4.0 a novější)**|Vytvořit, nasadit a monitorovat nastavení e-mailů Exchange ActiveSync na spravovaných zařízeních. Díky tomu mají uživatelé na svých osobních zařízeních přístup k podnikovému e-mailu, bez nutnosti něco nastavovat.<br /><br />Podrobnosti najdete v tématu [Konfigurace přístupu k podnikovému e-mailu pomocí e-mailových profilů v Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Obecná konfigurace (Android 4 nebo novější, Samsung KNOX Standard 4.0 a novější)**|Nakonfigurovat zabezpečení mobilního zařízení a funkční nastavení<br />Zadat aplikace, které jsou (nebo nejsou) v souladu s předpisy, a zobrazit zprávu o jejich používání<br />Nakonfigurovat celoobrazovkový režim, ve kterém můžete zařízení zamknout, a povolit fungování jenom některých funkcí, třeba můžete povolit, aby na zařízení běžela jenom jedna aplikace, nebo můžete zakázat tlačítka hlasitosti.<br /><br />Podrobnosti najdete v tématu [Nastavení zásad pro Android v Microsoft Intune](android-policy-settings-in-microsoft-intune.md).|
|**Profil certifikátu PKCS #12 (.PFX) (Android 4 a novější)**|Použít tento profil k vytvoření a nasazení nastavení PFX pro požadavky certifikátů zařízení.<br /><br />Podrobnosti najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil certifikátu SCEP (Android 4 a novější)**|Nakonfigurujte certifikát protokolu SCEP, který můžete použít společně s certifikátem důvěryhodného mobilního zařízení k ověřování mobilních zařízení a povolení jejich přístupu k síťovým prostředkům, například nakonfigurovaným profily Wi-Fi a VPN.<br /><br />Podrobnosti najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil důvěryhodného certifikátu (Android 4 a novější)**|Nakonfigurujte certifikát důvěryhodného mobilního zařízení, který můžete použít k ověřování mobilních zařízení a povolení jejich přístupu k síťovým prostředkům, například nakonfigurovaným profily Wi-Fi a VPN.<br /><br />Podrobnosti najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil VPN (Android 4 a novější)**|Nakonfigurujte a nasaďte nastavení, která uživatelům umožňují zabezpečený přístup k podnikové síti z jejich mobilních zařízení. Nasazením těchto nastavení minimalizujete úsilí koncových uživatelů potřebné pro připojení k jejich práci.<br /><br />Podrobnosti najdete v tématu [Připojení VPN v Microsoft Intune](vpn-connections-in-microsoft-intune.md).|
|**Profil Wi-Fi (Android 4 a novější)**|Nakonfigurujte a nasaďte nastavení bezdrátové sítě na uživatele ve vaší organizaci. Nasazením těchto nastavení minimalizujete úsilí koncových uživatelů potřebné k připojení k bezdrátové síti.<br /><br />Podrobnosti najdete v tématu [Připojení Wi-Fi v Microsoft Intune](wi-fi-connections-in-microsoft-intune.md).|

## Zásady konfigurace pro iOS

|Název zásady|Použijte v případě, že chcete|
|---------------|------------------------|
|**Vlastní konfigurace (iOS 7.1 a novější)**|Nasaďte konfigurační profily do zařízení s iOS vytvořených pomocí nástroje Apple Configurator. To je užitečné, když nastavení, které potřebujete, není k dispozici v zásadách konfigurace.<br /><br />Podrobnosti najdete v tématu [Nastavení zásad pro iOS v Microsoft Intune](ios-policy-settings-in-microsoft-intune.md).|
|**E-mailový profil (iOS 7.1 a novější)**|Vytvořit, nasadit a monitorovat nastavení e-mailů Exchange ActiveSync na spravovaných zařízeních. Díky tomu mají uživatelé na svých osobních zařízeních přístup k podnikovému e-mailu, bez nutnosti něco nastavovat.<br /><br />Podrobnosti najdete v tématu [Konfigurace přístupu k podnikovému e-mailu pomocí e-mailových profilů v Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Obecná konfigurace (iOS 7.1 a novější)**|Nakonfigurovat zabezpečení mobilního zařízení a funkční nastavení<br />-   Zadat aplikace, které jsou (nebo nejsou) v souladu s předpisy, a zobrazit zprávu o jejich používání<br />Nakonfigurovat celoobrazovkový režim, ve kterém můžete zařízení zamknout, a povolit fungování jenom některých funkcí, třeba můžete povolit, aby na zařízení běžela jenom jedna aplikace, nebo můžete zakázat tlačítka hlasitosti.<br /><br />Podrobnosti najdete v tématu [Nastavení zásad pro iOS v Microsoft Intune](ios-policy-settings-in-microsoft-intune.md).|
|**Zásady konfigurace mobilních aplikací (iOS 7.1 a novější)**|Použít zásady konfigurace mobilních aplikací k automatickému poskytování zásad, které se můžou požadovat, když uživatel spustí aplikaci pro iOS.<br /><br />Podrobnosti najdete v tématu [Konfigurace aplikací pro iOS pomocí zásad konfigurace mobilních aplikací v Microsoft Intune](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).|
|**Zásady mobilních zřizovacích profilů (iOS 7.1 a novější)**|Mobilní obchodní aplikace pro Apple iOS obsahují zřizovací profil a kód podepsaný certifikátem. Když se taková aplikace spustí na zařízení s iOS, iOS potvrdí její integritu a vynutí zásady jejím definované zřizovacím profilem.<br><br>Podpisový certifikát společnosti, který se používá k podepisování aplikací, má obvykle platnost 3 roky. Platnost zřizovacího profilu ale vyprší už po jednom roce. Pomocí těchto zásad můžete proaktivně nasadit nové zásady zřizovacích profilů do zařízení, ve kterých se aplikace blíží vypršení data platnosti, ale certifikát je stále platný.<br><br>Další podrobnosti najdete v tématu [Použití mobilních zásad zřizovacích profilů pro iOS k tomu, aby se zabránilo vypršení platnosti aplikací](ios-mobile-app-provisioning-profiles.md).|
|**Profil certifikátu PKCS #12 (.PFX) (iOS 7.1 a novější)**|Použít tento profil k vytvoření a nasazení nastavení PFX pro požadavky certifikátů zařízení.<br /><br />Podrobnosti najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil certifikátu SCEP (iOS 7.1 a novější)**|Nakonfigurujte certifikát protokolu SCEP, který můžete použít společně s certifikátem důvěryhodného mobilního zařízení k ověřování mobilních zařízení a povolení jejich přístupu k síťovým prostředkům, například nakonfigurovaným profily Wi-Fi a VPN.<br /><br />Podrobnosti najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil důvěryhodného certifikátu (iOS 7.1 a novější)**|Nakonfigurujte certifikát důvěryhodného mobilního zařízení, který můžete použít k ověřování mobilních zařízení a povolení jejich přístupu k síťovým prostředkům, například nakonfigurovaným profily Wi-Fi a VPN.<br /><br />Podrobnosti najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil VPN (iOS 7.1 a novější)**|Nakonfigurujte a nasaďte nastavení, která uživatelům umožňují zabezpečený přístup k podnikové síti z jejich mobilních zařízení. Nasazením těchto nastavení minimalizujete úsilí koncových uživatelů potřebné pro připojení k jejich práci.<br /><br />Podrobnosti najdete v tématu [Připojení VPN v Microsoft Intune](vpn-connections-in-microsoft-intune.md).|
|**Profil Wi-Fi (iOS 7.1 a novější)**|Nakonfigurujte a nasaďte nastavení bezdrátové sítě na uživatele ve vaší organizaci. Nasazením těchto nastavení minimalizujete úsilí koncových uživatelů potřebné k připojení k bezdrátové síti.<br /><br />Podrobnosti najdete v tématu [Připojení Wi-Fi v Microsoft Intune](wi-fi-connections-in-microsoft-intune.md).|


## Zásady konfigurace pro Mac OS X

|Název zásady|Použijte v případě, že chcete|
|---------------|------------------------|
|**Vlastní konfigurace (Mac OS X 10.9 a novější)**|Nasaďte konfigurační profily do počítačů Mac vytvořených pomocí nástroje Apple Configurator. To je užitečné, když nastavení, které potřebujete, není k dispozici v zásadách konfigurace.<br /><br />Podrobnosti najdete v tématu [Nastavení zásad pro Mac OS X v Microsoft Intune](mac-os-x-policy-settings-in-microsoft-intune.md).|
|**Obecná konfigurace (Mac OS X 10.9 a novější)**|Nakonfigurovat zabezpečení mobilního zařízení a funkční nastavení<br />Zadat aplikace, které jsou (nebo nejsou) v souladu s předpisy, a zobrazit zprávu o jejich používání<br /><br />Podrobnosti najdete v tématu [Nastavení zásad pro Mac OS X v Microsoft Intune](mac-os-x-policy-settings-in-microsoft-intune.md).|
|**Profil certifikátu SCEP (Mac OS X 10.9 a novější)**|Nakonfigurujte certifikát protokolu SCEP, který můžete použít společně s certifikátem důvěryhodného mobilního zařízení k ověřování mobilních zařízení a povolení jejich přístupu k síťovým prostředkům, například nakonfigurovaným profily Wi-Fi a VPN.<br /><br />Podrobnosti najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil důvěryhodného certifikátu (Mac OS X 10.9 a novější)**|Nakonfigurujte certifikát důvěryhodného mobilního zařízení, který můžete použít k ověřování mobilních zařízení a povolení jejich přístupu k síťovým prostředkům, například nakonfigurovaným profily Wi-Fi a VPN.<br /><br />Podrobnosti najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil sítě VPN (Mac OS X 10.9 a novější)**|Nakonfigurujte a nasaďte nastavení, která uživatelům umožňují zabezpečený přístup k podnikové síti z jejich mobilních zařízení. Nasazením těchto nastavení minimalizujete úsilí koncových uživatelů potřebné pro připojení k jejich práci.<br /><br />Podrobnosti najdete v tématu [Připojení VPN v Microsoft Intune](vpn-connections-in-microsoft-intune.md).|
|**Profil Wi-Fi (Mac OS X 10.9 a novější)**|Nakonfigurujte a nasaďte nastavení bezdrátové sítě na uživatele ve vaší organizaci. Nasazením těchto nastavení minimalizujete úsilí koncových uživatelů potřebné k připojení k bezdrátové síti.<br /><br />Podrobnosti najdete v tématu [Připojení Wi-Fi v Microsoft Intune](wi-fi-connections-in-microsoft-intune.md).|

## Zásady konfigurace pro Windows
Platí jenom pro Windows Phone a zaregistrovaná zařízení s Windows.

|Název zásady|Použijte v případě, že chcete|
|---------------|------------------------|
|**Vlastní konfigurace (Windows 10 Desktop a Mobile a novější)**|Nasadit nastavení OMA URI, která se dají použít k řízení funkcí zařízení. To je užitečné, když nastavení, které potřebujete, není k dispozici v zásadách konfigurace.<br />    Podrobnosti najdete v tématu [Nastavení zásad pro Windows 10 v Microsoft Intune](windows-10-policy-settings-in-microsoft-intune.md).|
|**Vlastní konfigurace (Windows Phone 8.1 a novější)**|Nasadit nastavení OMA URI, která se dají použít k řízení funkcí zařízení. To je užitečné, když nastavení, které potřebujete, není k dispozici v zásadách konfigurace.<br /><br />Podrobnosti najdete v tématu [Nastavení zásad pro Windows Phone 8.1 v Microsoft Intune](windows-phone-8-1-policy-settings-in-microsoft-intune.md).|
|**Zásady upgradu edice (Windows 10 Desktop nebo novější)**<br><br>**Zásady upgradu edice (Windows 10 Holographic nebo novější)**|Konfigurace a nasazení zásad obsahujících informace o licenčním kódu a kódu Product Key, který se používá k aktualizaci zařízení s Windows 10 na novější verzi<br><br>Podrobnosti najdete v tématu [Nastavení zásad upgradu edice v Microsoft Intune](edition-upgrade-policy-settings-in-microsoft-intune.md).|  
|**E-mailový profil (Windows Phone 8 a novější)**<br /><br />**E-mailový profil (Windows 10 Desktop a Mobile a novější)**|Vytvořit, nasadit a monitorovat nastavení e-mailů Exchange ActiveSync na spravovaných zařízeních. Díky tomu mají uživatelé na svých osobních zařízeních přístup k podnikovému e-mailu, bez nutnosti něco nastavovat.<br /><br />Podrobnosti najdete v tématu [Konfigurace přístupu k podnikovému e-mailu pomocí e-mailových profilů v Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Obecná konfigurace (Windows 10 Desktop a Mobile a novější)**|Konfigurovat zabezpečení mobilních zařízení a funkční nastavení pro zaregistrovaná zařízení s Windows 10 Desktop a Mobile.<br /><br />Podrobnosti najdete v tématu [Nastavení zásad pro Windows 10 v Microsoft Intune](windows-10-policy-settings-in-microsoft-intune.md).|
|**Obecná konfigurace (Windows 10 Team a novější)**|Nakonfigurujte nastavení funkcí a zabezpečení zařízení pro registrovaná zařízení se systémem Windows 10 Team (například zařízení Surface Hub).<br /><br />Podrobnosti najdete v tématu [Nastavení zásad konfigurace pro Windows Team v Microsoft Intune](windows-team-configuration-policy-settings-in-microsoft-intune.md).|
|**Obecná konfigurace (Windows 8.1 a novější)**|Konfigurovat zabezpečení mobilních zařízení a funkční nastavení pro zaregistrovaná zařízení s Windows.<br /><br />Podrobnosti najdete v tématu [Nastavení zásad pro Windows v Microsoft Intune](windows-configuration-policy-settings-in-microsoft-intune.md).|
|**Obecná konfigurace (Windows Phone 8.1 a novější)**|Nakonfigurovat zabezpečení mobilního zařízení a funkční nastavení<br />Zadat aplikace, které uživatelé můžou nebo nemůžou používat a blokovat instalaci nebo použití nevyhovujících aplikací.<br /><br />Podrobnosti najdete v tématu [Nastavení zásad pro Windows Phone 8.1 v Microsoft Intune](windows-phone-8-1-policy-settings-in-microsoft-intune.md).|
|**Profil certifikátu PKCS #12 (.PFX) (Windows 10 Desktop a Mobile a novější)**|Použít tento profil k vytvoření a nasazení nastavení PFX pro požadavky certifikátů zařízení.<br /><br />Podrobnosti najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil certifikátu SCEP (Windows 8.1 a novější)**<br /><br />**Profil certifikátu SCEP (Windows Phone 8.1 a novější)**|Nakonfigurujte certifikát protokolu SCEP, který můžete použít společně s certifikátem důvěryhodného mobilního zařízení k ověřování mobilních zařízení a povolení jejich přístupu k síťovým prostředkům, například nakonfigurovaným profily Wi-Fi a VPN.<br /><br />Podrobnosti najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil důvěryhodného certifikátu (Windows 8.1 a novější)**<br /><br />**Profil důvěryhodného certifikátu (Windows Phone 8.1 a novější)**|Nakonfigurujte certifikát důvěryhodného mobilního zařízení, který můžete použít k ověřování mobilních zařízení a povolení jejich přístupu k síťovým prostředkům, například nakonfigurovaným profily Wi-Fi a VPN.<br /><br />Podrobnosti najdete v tématu [Zabezpečení přístupu k prostředkům pomocí profilů certifikátů v Microsoft Intune](secure-resource-access-with-certificate-profiles.md).|
|**Profil VPN (Windows 10 Desktop a Mobile a novější)**<br /><br />**Profil VPN (Windows Phone 8.1 a novější)**<br /><br />**Profil VPN (Windows Phone 8.1 a novější)**|Nakonfigurujte a nasaďte nastavení, která uživatelům umožňují zabezpečený přístup k podnikové síti z jejich mobilních zařízení. Nasazením těchto nastavení minimalizujete úsilí koncových uživatelů potřebné pro připojení k jejich práci.<br /><br />Podrobnosti najdete v tématu [Připojení VPN v Microsoft Intune](vpn-connections-in-microsoft-intune.md).|
|**Import ve Wi-Fi**|Importujte a nasaďte konfigurace Wi-Fi pro Windows, které jste předtím exportovali do souboru.<br /><br />Podrobnosti najdete v tématu [Připojení Wi-Fi v Microsoft Intune](wi-fi-connections-in-microsoft-intune.md).|
|**Windows Information Protection**<br>(dříve označované jako ochrana podnikových dat)|S nárůstem počtu zařízení vlastněných zaměstnanci, která se v podnicích využívají, vzrůstá také riziko náhodných úniků dat prostřednictvím aplikací a služeb, jako jsou e-mail, sociální média a veřejný cloud, které jsou mimo kontrolu příslušného podniku. Jsou to situace, kdy uživatel například odešle nejnovější technické výkresy ze svého osobního e-mailového účtu, zkopíruje informace o produktu a vloží je do tweetu nebo uloží aktuální zprávu o prodeji do veřejného cloudového úložiště.<br><br>Služba Windows Information Protection pomáhá před těmito potenciálními úniky dat chránit, aniž by jinak zasahovala do činnosti zaměstnanců. Pomáhá také chránit podnikové aplikace a data před náhodnými úniky dat na zařízeních ve vlastnictví společnosti a osobních zařízeních, která si uživatelé přinesou do práce, a nevyžaduje přitom žádné změny prostředí nebo ostatních aplikací.<br><br>Tyto zásady Intune spravují seznam aplikací chráněných službou Windows Information Protection, umístění v podnikové síti, úroveň ochrany a nastavení šifrování.<br><br>Další informace najdete v tématu věnovaném [ochraně podnikových dat pomocí služby Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-edp).|


## Softwarové zásady

|Název zásady|Použijte v případě, že chcete|
|---------------|------------------------|
|**Zásady spravovaného prohlížeče (Android 4 a novější)**<br /><br />**Zásady spravovaného prohlížeče (iOS 7.1 a novější)**|Zadejte weby, ke kterým uživatelé můžou a nemůžou přistupovat pomocí aplikace spravovaného prohlížeče.<br /><br />Podrobnosti najdete v tématu [Správa přístupu k internetu pomocí zásad spravovaného prohlížeče v Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).|
|**Zásady správy mobilních aplikací (Android 4 a novější)**<br /><br />**Zásady správy mobilních aplikací (iOS 7.1 a novější)**|Upravte funkce nasazovaných aplikací tak, aby byly v souladu s předpisy a zásadami zabezpečení vaší společnosti. Můžete například omezit operace vyjmutí, kopírování a vložení v rámci aplikace s omezeným přístupem, nebo aplikaci nakonfigurovat tak, aby všechny webové odkazy otevírala ve spravovaném prohlížeči.<br /><br />Podrobnosti najdete v tématu [Konfigurace a nasazení zásad správy mobilních aplikací v konzole Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).|

## Obecná nastavení mobilních zařízení

|Název zásady|Použijte v případě, že chcete|
|---------------|------------------------|
|**Zásady Exchange ActiveSync**|Konfigurovat nastavení zabezpečení mobilních zařízení a funkční nastavení pro zařízení, která se spravují přes Exchange ActiveSync<br /><br />Podrobnosti najdete v tématu [Nastavení zásad Exchange ActiveSync v Microsoft Intune](exchange-activesync-policy-settings-in-microsoft-intune.md).|
|**Zásady zabezpečení mobilních zařízení**|<ul><li>Konfiguruje nastavení pro mobilní zařízení (všechny platformy), včetně:<br /><br /><ul><li>Zabezpečení</li><li>Šifrování</li><li>Systému</li><li>E-mailu</li><li>Aplikací</li></ul></li></ul> **Důležité:** Microsoft Intune teď nabízí oddělené **zásady konfigurace** pro každou platformu zařízení a tyto zásady obsahují nejaktuálnější nastavení, které můžete použít. Můžete pokračovat v používání zásad zabezpečení mobilních zařízení a všechna existující nasazení budou i nadále fungovat, měli byste ale naplánovat, aby se v co nejbližší době provedla migrace na nové zásady konfigurace.<br />Podrobnosti najdete v tématu [Zásady zabezpečení mobilních zařízení v Microsoft Intune](mobile-device-security-policy-settings-in-microsoft-intune.md).|

## Zásady podmíněného přístupu a zásady dodržování předpisů

### Podmíněný přístup

|Název zásady|Použijte v případě, že chcete|
|---------------|------------------------|
|**Zásady Exchange Online**<br /><br />**Zásady místního systému Exchange**|Spravovat přístup k e-mailům Microsoft Exchange ze zařízení, která nespravuje Intune nebo která nevyhovují vytvořeným zásadám dodržování předpisů.<br /><br />Podrobnosti najdete v tématu [Omezení e-mailového přístupu k Exchangi Online a novému vyhrazenému prostředí Exchange Online s Intune](restrict-access-to-exchange-online-with-microsoft-intune.md).|
|**Zásady SharePointu Online**|Spravovat přístup k SharePointu Online ze zařízení, která nespravuje Intune nebo která nevyhovují vytvořeným zásadám dodržování předpisů.<br /><br />Podrobnosti najdete v tématu [Omezení přístupu k SharePoint Online pomocí Microsoft Intune](restrict-access-to-sharepoint-online-with-microsoft-intune.md).|
|**Skype pro firmy**|Spravovat přístup ke Skypu pro firmy ze zařízení, která nespravuje Intune nebo která nevyhovují vytvořeným zásadám dodržování předpisů.<br /><br />Podrobnosti najdete v tématu [Omezení přístupu k SharePoint Online pomocí Microsoft Intune](restrict-access-to-skype-for-business-online-with-microsoft-intune.md).|
> [!NOTE]
> Zásady podmíněného přístupu nenasazujte na uživatele a zařízení. Namísto toho můžete nakonfigurovat požadované zásady, které se použijí na všechny cílové skupiny v zásadách.

### Zásady slučitelnosti

|Název zásady|Použijte v případě, že chcete|
|---------------|------------------------|
|**Zásady slučitelnosti**|Definovat úroveň souladu s předpisy pro zařízení a vytvářet zprávy o zařízeních, která nejsou v souladu s předpisy. Tyto zásady se společně s podmíněným přístupem používají k vyhodnocení zařízení, u kterých se mají blokovat služby.<br /><br />Podrobnosti najdete v tématu [Zásady dodržování předpisů u zařízení v Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md).|

## Správa počítačů s Windows

|Název zásady|Použijte v případě, že chcete|
|---------------|------------------------|
|**Nastavení agenta Microsoft Intune**|Konfigurovat klienta Intune v počítačích, včetně nastavení pro:<br /><br />-   Endpoint Protection<br />-   Aktualizace softwaru<br />-   Plán kontrol zásad<br /><br />Tento typ zásad se dá nasadit jenom na skupiny zařízení.<br /><br />Klienti Intune stahují nové a aktualizované zásady podle nastavení **Četnost detekce aktualizací a aplikací**. Výchozí nastavení je 8 hodin. Aktualizaci zásad v počítačích ale můžete kdykoli vynutit.<br /><br />Podrobnosti najdete v tématu [Udržování počítačů s Windows v aktuálním stavu díky softwarovým aktualizacím v Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Nastavení centra Microsoft Intune**|Konfigurovat podrobnosti, které se zobrazují v centru Microsoft Intune Center na spravovaných počítačích.<br /><br />Tento typ zásad se dá nasadit jenom na skupiny zařízení.<br /><br />Podrobnosti najdete v tématu [Běžné úlohy správy počítačů s Windows pomocí počítačového klienta Microsoft Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).|
|**Nastavení brány Windows Firewall**|Nakonfiguruje nastavení brány Windows Firewall a výjimky pro běžné síťové komunikace v počítačích, včetně:<br /><br />-   BranchCache<br />-   Vzdálená pomoc<br />-   Sdílení médií<br /><br />Tento typ zásad se dá nasadit jenom na skupiny zařízení.<br /><br />Podrobnosti najdete v tématu [Pomoc se zabezpečením počítačů s Windows pomocí služby Endpoint Protection pro Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).|

### Viz také

[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jul16_HO4-->


