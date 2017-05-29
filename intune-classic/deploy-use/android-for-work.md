---
title: O aplikaci Android for Work | Dokumentace Microsoftu
description: "Intune spravuje Android for Work. K dispozici jsou tak další možnosti správy a ochrany osobních údajů, když uživatelé používají při práci svoje zařízení s Androidem."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa0002d9-f5a0-466e-98ac-3970cb77e3a2
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: b5651e311bc3cd6619f9d7fd8782de4d5db4630c
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="manage-android-for-work-devices-with-intune"></a>Správa zařízení s Androidem for Work pomocí Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Android for Work je sada funkcí a služeb pro zařízení s Androidem, které oddělují osobní aplikace a data od pracovního profilu obsahujícího pracovní aplikace a data. Android for Work poskytuje další možnosti správy a ochrany osobních údajů, když uživatelé používají při práci svoje zařízení s Androidem. Intune vám pomůže nasadit aplikace a podnikové prostředky do zařízení s Androidem for Work a zajistí oddělení pracovních a osobních informací. Po úspěšném nasazení zůstanou aplikace a data, ke kterým budou získávat přístup, výhradně v prostředí Android for Work daného zařízení.

## <a name="supported-devices"></a>Podporovaná zařízení

Možnosti správy v Androidu for Work využívají funkce, které jsou součástí novějšího operačního systému Android. Android for Work je momentálně podporovaný na zařízeních se systémem Android 5.0 Lollipop a novějšími systémy, které podporují pracovní profil. U zařízení, která Android for Work nepodporují, je dál k dispozici konvenční správa Androidu. Další informace najdete v tématu [Požadavky pro Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="onboarding"></a>Připojení

Před registrací Androidu for Work je potřeba provést několik kroků pro připojení. Pomocí tohoto postupu připojíte svého tenanta Intune ke Google Play pro službu Work, která je nedílnou součástí distribuce a procesu správy aplikací pro Android for Work. Přečtěte si další informace týkající se [povolení registrace Androidu for Work](/intune-classic/deploy-use/set-up-android-for-work).

## <a name="work-profile-management"></a>Správa pracovních profilů

Při správě zařízení s Androidem for Work pomocí Intune nespravujete celé zařízení. Možnosti správy mají vliv jenom na pracovní profil, který se vytvoří v zařízení během registrace. Všechny aplikace, které se nasadí na zařízení pomocí Intune, se nainstalují do pracovního profilu. Kvůli odlišení pracovních aplikací od osobních aplikací v zařízení se u aplikací v pracovním profilu zobrazuje ikona oranžové aktovky. Všechny aplikace pro Android a data mimo oblast Androidu for Work na zařízení budou osobní a pod kontrolou koncového uživatele. Uživatelé můžou do osobní části zařízení nainstalovat libovolnou aplikaci, kterou si vyberou. Správci můžou spravovat a sledovat aplikace a akce zahrnuté do pracovního profilu.

Intune poskytuje řadu předdefinovaných obecných nastavení, která můžete konfigurovat na zařízeních s Androidem for Work. Přečtěte si další informace o [nastavení zásad pro Android for Work](android-for-work-policy-settings-in-microsoft-intune.md).

## <a name="app-publishing-and-distribution"></a>Publikování a distribuce aplikací

Služba Google Play for Work je nedílnou součástí distribuce a správy aplikací na zařízeních s Androidem for Work. Všechny aplikace nasazené na zařízení s Androidem for Work v pracovním profilu pocházejí ze služby Play for Work. Pokud chcete v obchodu Google Play spravovat a nasazovat aplikace, přihlaste se na web Google Play pomocí přihlašovacích údajů správce vaší společnosti pro správu účtu Google. Můžete schvalovat nasazení aplikací Androidu for Work, aby se objevily v pracovních profilech zařízení. Tyto aplikace se potom budou synchronizovat s konzolou Intune, kde je pak možné je pomocí služby Intune nasadit a spravovat. Obchodní aplikace vyvinuté ve vaší organizaci je potřeba publikovat ve službě Play for Work za použití konzoly pro publikování aplikací pro Android na Googlu. Obchodní aplikace se musí nakonfigurovat na konzole pro publikování aplikací pro Android. Omezí se tak přístup do vaší organizace.

Aplikace se můžou instalovat bez interakce uživatelů, kteří ani nemusí povolit **instalaci z neznámých zdrojů**. Uživatelé můžou procházet obchod Play for Work a na svoje zařízení z něj instalovat volitelné nebo dostupné aplikace. Přečtěte si další informace o [nasazení aplikací pro Android for Work](/intune-classic/deploy-use/android-for-work-apps).

## <a name="app-configuration"></a>Konfigurace aplikací

Android for Work poskytuje infrastrukturu pro nasazení konfiguračních hodnot aplikací do aplikací, které je podporují. Když zadáte konfigurační hodnoty pro pracovní aplikace, zajistíte tak při prvním spuštění aplikace uživatelem jejich správné nastavení. Podpora konfigurace aplikace vyžaduje, aby vývojáři aplikací vytvářeli svoje aplikace výslovně tak, aby podporovaly hodnoty spravované konfigurace. V takovém případě pak můžou použít Intune k zadání a použití tohoto nastavení konfigurace. Přečtěte si další informace o [nastavení konfigurace aplikace pro Android for Work](afw-app-configuration-policy.md).

## <a name="email-configuration"></a>Konfigurace e-mailu

Android for Work neposkytuje výchozí e-mailovou aplikaci ani nativní objekt e-mailového profilu, který iOS poskytuje. Místo toho je možné nastavit konfigurace e-mailu s použitím nastavení konfigurací aplikací u e-mailových aplikací, které je podporují. Konfiguraci pomocí konfigurace aplikace pro Android for Work podporují dvě klientské aplikace EAS (Exchange ActiveSync) na webu Play Store – Gmail a Nine Work.

Když jsou aplikace Gmail a Nine Work spravované jako pracovní aplikace, služba Intune pro ně poskytuje šablony konfigurace. Ostatní e-mailové aplikace, které podporují konfigurační profily aplikací, je možné nakonfigurovat pomocí zásad konfigurace mobilních aplikací.

Pokud pro zařízení s Androidem for Work používáte podmíněný přístup Exchange ActiveSync, je nutné použít e-mailovou aplikaci Gmail nebo Nine Work. Podporuje se také aplikace Microsoft Outlook pro Android nebo kterákoliv jiná e-mailová aplikace, která používá moderní ověřování prostřednictvím ADAL. Přečtěte si další informace o [e-mailových profilech pro firemní e-mail](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## <a name="app-protection-policies"></a>Zásady ochrany aplikace

Používané zásady ochrany aplikace jsou plně podporované v pracovním i osobním profilu. Obchodní aplikace je možné publikovat na konzole pro publikování aplikací pro Android na adrese https://play.google.com/apps/publish. Tato konzola zahrnuje možnost nastavit pro vaši organizaci aplikace jako soukromé. Přečtěte si další informace o [nastavení zásad dodržování předpisů pro zařízení s Androidem for Work](afw-compliance-policy-settings-in-microsoft-intune.md). Obecné informace o zásadách ochrany aplikace najdete v článku o [zásadách aplikací](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

## <a name="vpn-profiles"></a>Profily sítě VPN

Podpora sítě VPN je podobná profilům Android VPN. U správy s Androidem for Work jsou k dispozici stejní poskytovatelé VPN i základní možnosti konfigurace, až na dva rozdíly:

-  **Síť VPN vymezená pro pracovní profil** – připojení VPN jsou omezená jenom na aplikace nasazené do pracovního profilu. Připojení VPN můžou použít jenom aplikace spravované v rámci Androidu for Work. Osobní aplikace na zařízení spravované připojení VPN použít nemůžou.

-  **Síť VPN pro určité aplikace** – pokud poskytovatel připojení VPN podporuje konfiguraci pro síť VPN pro určitou aplikaci a poskytuje možnost konfigurovat síť VPN pro určitou aplikaci přes konfigurační profil aplikací pro Android for Work, potom je možné v Intune konfigurovat síť VPN pro určité aplikace. Požádejte poskytovatele sítě VPN o informace, jestli podporuje tuto možnost. Přečtěte si další informace o [profilech připojení VPN](vpn-connections-in-microsoft-intune.md).

## <a name="certificate-profiles"></a>Profily certifikátů

Na zařízeních s Androidem for Work jsou k dispozici stejné možnosti konfigurace profilů certifikátů, jaké jsou dostupné u správy Androidu. Android for Work poskytuje vylepšené rozhraní API pro správu certifikátů. Vylepšená správa certifikátů poskytuje následující funkce:

- Zajišťuje uživatelům tiché a bezproblémové nasazení.
-  Zajišťuje úplné odebrání nasazených certifikátů po vyřazení zařízení z Intune a odebrání pracovního profilu.
-  Poskytuje vylepšené zasílání zpráv uživatelům s informacemi o tom, že IT oddělení nasadilo a nakonfigurovalo prostřednictvím svojí služby správy certifikát.

Přečtěte si další informace [o profilech certifikátů](secure-resource-access-with-certificate-profiles.md).

## <a name="wi-fi-profiles"></a>Profily sítě Wi-Fi

Profily Wi-Fi spravované Androidem for Work se po vyřazení zařízení z Intune a odstranění pracovního profilu odeberou. Přečtěte si další informace o [profilech Wi-Fi](wi-fi-connections-in-microsoft-intune.md).

## <a name="next-steps"></a>Další kroky
[Povolení registrace Androidu for Work](/intune-classic/deploy-use/set-up-android-for-work)

[Nasazení aplikací pro Android for Work](/intune-classic/deploy-use/android-for-work-apps)

