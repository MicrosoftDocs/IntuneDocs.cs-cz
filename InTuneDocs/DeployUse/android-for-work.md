---
title: O aplikaci Android for Work | Microsoft Intune
description: "Intune spravuje Android for Work. K dispozici jsou tak další možnosti správy a ochrany osobních údajů, když uživatelé používají při práci svoje zařízení s Androidem."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 10/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa0002d9-f5a0-466e-98ac-3970cb77e3a2
translationtype: Human Translation
ms.sourcegitcommit: 0238350139837a06a48d0bff7c53e4c39e07168c
ms.openlocfilehash: aafeb58e28144740540a765ac04de68b41ae5ce5


---

# <a name="manage-android-for-work-devices-with-intune"></a>Správa zařízení s Androidem for Work pomocí Intune

Android for Work je sada funkcí a služeb pro zařízení s Androidem. Tyto funkce a služby přidávají další možnosti správy a ochrany osobních údajů, když uživatelé používají při práci svoje zařízení s Androidem. Intune vám může pomoct s nasazením aplikací a podnikových prostředků do zařízení s Androidem for Work a zajistit tak oddělení pracovních a osobních informací. Po úspěšném nasazení zůstanou aplikace a data, ke kterým budou získávat přístup, výhradně v prostředí Android for Work daného zařízení.

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

## <a name="supported-devices"></a>Podporovaná zařízení

Android for Work vyžaduje novější hardware Android, protože mnoho možností správy používá funkce, které jsou součástí novějšího operačního systému Android. Android for Work se momentálně podporuje na zařízeních se systémem Android 5.0 Lollipop a novějšími systémy a na zařízeních, která podporují pracovní profil. Zařízení, která nemají nativní podporu pro Android for Work, mají dál k dispozici konvenční možnosti správy Androidu. Další informace najdete v tématu [Požadavky pro Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="onboarding"></a>Připojení

Před registrací Androidu for Work je potřeba provést několik kroků pro připojení. Pomocí tohoto postupu připojíte svého tenanta Intune ke Google Play pro službu Work, která je nedílnou součástí distribuce a procesu správy aplikací pro Android for Work. Přečtěte si další informace týkající se [povolení registrace Androidu for Work](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-android-for-work).

## <a name="work-profile-management"></a>Správa pracovních profilů

Při správě zařízení s Androidem for Work pomocí Intune nespravujete celé zařízení. Možnosti správy mají vliv jenom na pracovní profil, který se vytvoří během registrace. Všechny aplikace, které jsou nasazené na zařízení pomocí Intune, jsou součástí tohoto pracovního profilu. U ikon pro aplikace v pracovním profilu se zobrazuje oranžová aktovka. Toto označení odlišuje na zařízení firemní aplikace od osobních. Všechny aplikace pro Android a data mimo oblast Androidu for Work na zařízení budou osobní a pod kontrolou koncového uživatele. Uživatelé můžou do osobní části zařízení nainstalovat libovolnou aplikaci, kterou si vyberou. Správci můžou spravovat a sledovat akce zahrnuté do pracovního profilu.

## <a name="app-publishing-and-distribution"></a>Publikování a distribuce aplikací

Služba Google Play je nedílnou součástí distribuce a správy aplikací. Všechny aplikace nasazené na zařízení s Androidem for Work v pracovním profilu pocházejí ze služby Play for Work. Pokud budete chtít spravovat a nasazovat aplikace ve službě Play Store, přihlásíte se jako správce Intune k webu Play for Work a schválíte aplikace pro tenanta Intune. Tyto aplikace se budou synchronizovat na konzolu Intune, kde je pak možné je pomocí Intune nasadit a spravovat. Obchodní aplikace vyvinuté ve vaší organizaci je potřeba publikovat ve službě Play for Work za použití konzoly pro publikování aplikací pro Android na Googlu. Obchodní aplikace se musí nakonfigurovat na konzole pro publikování aplikací pro Android. Omezí se tak přístup do vaší organizace.

Aplikace se instalují bez interakce uživatelů, kteří ani nemusí povolit **instalaci z neznámých zdrojů**. Uživatelé můžou procházet a na svoje zařízení instalovat volitelné nebo dostupné aplikace z Play Store označené jako pracovní. Přečtěte si další informace o [nasazení aplikací pro Android for Work](https://docs.microsoft.com/en-us/intune/deploy-use/android-for-work-apps).

## <a name="app-configuration"></a>Konfigurace aplikací

Android for Work poskytuje infrastrukturu pro nasazení konfiguračních hodnot aplikací do aplikací, které je podporují. Když zadáte konfigurační hodnoty pro pracovní aplikace, zajistíte tak při prvním spuštění aplikace uživatelem jejich správné nastavení. Podpora konfigurace aplikace vyžaduje, aby vývojáři aplikací vytvářeli svoje aplikace výslovně tak, aby podporovaly hodnoty spravované konfigurace. V takovém případě pak můžou použít Intune k zadání a použití tohoto nastavení konfigurace. Přečtěte si další informace o [nastavení konfigurace aplikace pro Android for Work](deploy-use/afw-app-configuration-policy.md).

## <a name="email-configuration"></a>Konfigurace e-mailu

Android for Work neposkytuje výchozí e-mailovou aplikaci ani nativní objekt e-mailového profilu, jako poskytuje iOS. Místo toho je možné nastavit konfigurace e-mailu s použitím nastavení konfigurací aplikací u e-mailových aplikací, které je podporují. Konfiguraci pomocí konfigurace aplikace pro Android for Work podporují dvě klientské aplikace EAS (Exchange ActiveSync) na webu Play Store – Gmail a Nine Work.

Intune poskytuje pro aplikace Gmail a Nine Work šablony konfigurace. Ostatní e-mailové aplikace, které podporují konfigurační profily aplikací, je možné nakonfigurovat pomocí zásad konfigurace mobilních aplikací.

Pokud pro zařízení s Androidem for Work používáte podmíněný přístup EAS, je nutné použít e-mailovou aplikaci Gmail nebo Nine Work. Podporuje se také aplikace Microsoft Outlook pro Android nebo kterákoliv jiná e-mailová aplikace, která používá moderní ověřování prostřednictvím ADAL. Přečtěte si další informace o [e-mailových profilech pro firemní e-mail](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## <a name="mobile-app-management-policies"></a>Zásady správy mobilních aplikací

V pracovním i osobním profilu se plně podporují zásady omezení použité u aplikací, které jsou povolené pro správu mobilních aplikací (MAM). Obchodní aplikace je možné publikovat na konzole pro publikování aplikací pro Android na adrese https://play.google.com/apps/publish. Tato konzola zahrnuje možnost nastavit pro vaši organizaci aplikace jako soukromé. Přečtěte si další informace o [nastavení zásad dodržování předpisů](afw-compliance-policy-settings-in-microsoft-intune.md). Další informace najdete v tématu o [zásadách správy mobilních aplikací](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

## <a name="vpn-profiles"></a>Profily sítě VPN

Podpora sítě VPN je podobná profilům Android VPN. K dispozici jsou stejní poskytovatelé VPN a základní možnosti konfigurace. Existují dva základní rozdíly:

1.  **Síť VPN určená pro pracovní profil** – připojení VPN jsou určená jenom pro aplikace nasazené do pracovního profilu. Připojení VPN můžou použít jenom aplikace spravované v rámci Androidu for Work. Osobní aplikace na zařízení spravované připojení VPN použít nemůžou.

2.  **Síť VPN pro určité aplikace** – pokud poskytovatel připojení VPN podporuje konfiguraci pro síť VPN pro určitou aplikaci a poskytuje možnost konfigurovat síť VPN pro určitou aplikaci přes konfigurační profil aplikací pro Android for Work, potom je možné v Intune konfigurovat síť VPN pro určité aplikace. Požádejte poskytovatele sítě VPN o informace, jestli podporuje tuto možnost. Přečtěte si další informace o [profilech připojení VPN](vpn-connections-in-microsoft-intune.md).

## <a name="certificate-profiles"></a>Profily certifikátů

Na zařízeních s Androidem for Work jsou k dispozici stejné možnosti konfigurace profilu certifikátu, jako jsou k dispozici u tradiční správy Androidu. Android for Work poskytuje vylepšené rozhraní API pro správu certifikátů. Vylepšená správa certifikátů poskytuje následující funkce:

1.  Zajišťuje uživatelům tiché a bezproblémové nasazení.

2.  Zajišťuje úplné odebrání nasazených certifikátů po vyřazení zařízení z Intune a odebrání pracovního profilu.

3.  Poskytuje vylepšené zasílání zpráv uživatelům s informacemi o tom, že IT oddělení nasadilo a nakonfigurovalo prostřednictvím svojí služby správy certifikát.

Přečtěte si další informace [o profilech certifikátů](secure-resource-access-with-certificate-profiles.md).

## <a name="wifi-profiles"></a>Profily sítě Wi-Fi

U profilů Wi-Fi spravovaných Androidem for Work je zaručené, že se po vyřazení zařízení z Intune a odstranění pracovního profilu odeberou. Přečtěte si další informace o [profilech Wi-Fi](wi-fi-connections-in-microsoft-intune.md).

## <a name="next-steps"></a>Další kroky
[Povolení registrace Androidu for Work](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-android-for-work)
[Nasazení aplikací pro Android for Work](https://docs.microsoft.com/en-us/intune/deploy-use/android-for-work-apps)



<!--HONumber=Nov16_HO1-->


