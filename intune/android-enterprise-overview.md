---
title: Správa zařízení s pracovním profilem Androidu v Microsoft Intune
titlesuffix: ''
description: Microsoft Intune spravuje zařízení s pracovním profilem Androidu a poskytuje tak další možnosti správy a ochrany osobních údajů, když uživatelé používají při práci svoje zařízení s Androidem.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2cc3c960-1fdd-47ca-a693-420d47b403de
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: f3bea9b1678669aa568c44e63f57aebd832cf203
ms.sourcegitcommit: 9739a9aab032ebb2c4b52ccfb454a9e0f78b2ee4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54751174"
---
# <a name="manage-android-work-profile-devices-with-intune"></a>Správa zařízení s pracovním profilem Androidu v Intune

Android Enterprise je sada funkcí a služeb, které oddělují osobní aplikace a data od pracovních aplikací a dat. Android Enterprise poskytuje další možnosti správy a ochrany osobních údajů, když uživatelé používají při práci svoje zařízení s Androidem. 

## <a name="supported-devices"></a>Podporovaná zařízení

Možnosti správy Androidu Enterprise závisejí na funkcích, které jsou součástí novějších operačních systémů Android. U zařízení, která Android Enterprise nepodporují, je nadále k dispozici správa konvenčního Androidu. Další informace najdete v tématu [Požadavky na Android Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="onboarding"></a>Připojení

Před registrací zařízení s pracovním profilem Androidu je potřeba provést několik kroků pro připojení. Těmito kroky zajistíte propojení mezi tenantem Intune a službou Google Play for Work. Další informace najdete v tématu o [povolení registrace zařízení s pracovním profilem Androidu](android-work-profile-enroll.md).

## <a name="work-profile-management"></a>Správa pracovních profilů

Při správě zařízení s pracovním profilem Androidu pomocí Intune nespravujete celé zařízení. Možnosti správy mají vliv jenom na pracovní profil, který se vytvoří v zařízení během registrace. Všechny aplikace, které se nasadí na zařízení pomocí Intune, se nainstalují do pracovního profilu. Ikony aplikací v pracovním profilu jsou odlišené od osobních aplikací v zařízení. Všechny aplikace a data Androidu mimo část zařízení vyhrazenou pro Android Enterprise zůstanou osobní a pod kontrolou koncového uživatele. Uživatelé můžou do osobní části zařízení nainstalovat libovolnou aplikaci. Správci můžou spravovat a monitorovat aplikace a akce vymezené pro pracovní profil.

Intune poskytuje řadu předdefinovaných obecných nastavení, která můžete na zařízeních s pracovním profilem Androidu konfigurovat. Další informace najdete v tématu, které se věnuje [nastavení zásad na zařízeních s pracovním profilem Androidu](compliance-policy-create-android-for-work.md).

## <a name="app-publishing-and-distribution"></a>Publikování a distribuce aplikací

Služba Google Play for Work je nedílnou součástí distribuce a správy aplikace Android Enterprise. Všechny aplikace nasazené do pracovního profilu v zařízeních s pracovním profilem Androidu pocházejí ze spravovaného obchodu Google Play. Pokud chcete v obchodu Play spravovat a nasazovat aplikace, přihlaste se na web Google Play pomocí přihlašovacích údajů správce vaší společnosti pro správu účtu Google. Můžete schvalovat nasazení aplikací pro Android Enterprise, které se pak objeví v pracovních profilech zařízení. Tyto aplikace se potom budou synchronizovat s konzolou Intune, kde je pak možné je pomocí služby Intune nasadit a spravovat. Obchodní aplikace vyvinuté ve vaší organizaci se musí publikovat do spravovaného obchodu Google Play pomocí konzoly pro publikování aplikací pro Android od Googlu. Obchodní aplikace se musí nakonfigurovat na konzole pro publikování aplikací pro Android. Omezí se tak přístup do vaší organizace.

Aplikace se můžou instalovat bez interakce uživatelů, kteří ani nemusí povolit **instalaci z neznámých zdrojů**. Uživatelé můžou procházet obchod Play for Work a na svoje zařízení z něj instalovat volitelné nebo dostupné aplikace. Další informace najdete v tématu [Přiřazení aplikací k zařízením s pracovním profilem Androidu pomocí Intune](apps-add-android-for-work.md).

## <a name="app-configuration"></a>Konfigurace aplikací

Android Enterprise poskytuje infrastrukturu pro nasazení konfiguračních hodnot aplikací do aplikací, které je podporují. Když zadáte konfigurační hodnoty pro pracovní aplikace, zajistíte tak při prvním spuštění aplikace uživatelem jejich správné nastavení. Podpora konfigurace aplikace vyžaduje, aby vývojáři aplikací vytvářeli svoje aplikace výslovně tak, aby podporovaly hodnoty spravované konfigurace. V takovém případě pak můžou použít Intune k zadání a použití tohoto nastavení konfigurace. Další informace najdete v tématu [Přidání zásad konfigurace aplikací pro spravovaná zařízení s Androidem](app-configuration-policies-use-android.md).

## <a name="email-configuration"></a>Konfigurace e-mailu

Android Enterprise neposkytuje výchozí e-mailovou aplikaci ani nativní objekt e-mailového profilu jako iOS. Místo toho je možné nastavit konfigurace e-mailu s použitím nastavení konfigurací aplikací u e-mailových aplikací, které je podporují. Konfiguraci pomocí aplikace Android Enterprise podporují dvě klientské aplikace Exchange ActiveSync (EAS) v obchodu Play – Gmail a Nine Work.

Když jsou aplikace Gmail a Nine Work spravované jako pracovní aplikace, služba Intune pro ně poskytuje šablony konfigurace. Jiné e-mailové aplikace, které podporují konfigurační profily aplikací, je možné nakonfigurovat pomocí zásad konfigurace mobilních aplikací.

Pokud pro zařízení s pracovním profilem Androidu používáte podmíněný přístup Exchange ActiveSync, zvažte použití e-mailové aplikace Gmail nebo Nine Work. Podporuje se také aplikace Microsoft Outlook pro Android nebo kterákoliv jiná e-mailová aplikace, která používá moderní ověřování prostřednictvím ADAL. Další informace najdete v tématu [Jak nakonfigurovat nastavení e-mailu v Microsoft Intune](email-settings-configure.md).

## <a name="app-protection-policies"></a>Zásady ochrany aplikace

Používané zásady ochrany aplikace jsou plně podporované v pracovním i osobním profilu. Obchodní aplikace je možné publikovat na konzole pro publikování aplikací pro Android na adrese https://play.google.com/apps/publish. Tato konzola zahrnuje možnost nastavit pro vaši organizaci aplikace jako soukromé. Další informace najdete v tématu [Přidání zásad dodržování předpisů pro zařízení s pracovním profilem Androidu v Intune](compliance-policy-create-android-for-work.md). Obecné informace o zásadách ochrany aplikací najdete v tématu [Co jsou zásady ochrany aplikací](app-protection-policy.md).

## <a name="vpn-profiles"></a>Profily sítě VPN

Podpora sítě VPN je podobná profilům Android VPN. Pro správu Androidu Enterprise jsou k dispozici stejní poskytovatelé sítě VPN a základní možnosti konfigurace, až na dva rozdíly:

-  **Síť VPN vymezená pro pracovní profil** – připojení VPN jsou omezená jenom na aplikace nasazené do pracovního profilu. Připojení VPN můžou používat jen aplikace spravované v rámci Androidu Enterprise. Osobní aplikace na zařízení spravované připojení VPN použít nemůžou. Další informace najdete v tématu o [nastavení sítě VPN v Androidu Enterprise](vpn-settings-android.md#android-enterprise-vpn-settings).

-  **Síť VPN specifická pro aplikaci** – tuto síť lze v Intune nakonfigurovat, pokud poskytovatel VPN podporuje:
    - Konfiguraci sítě VPN specifické pro aplikaci
    - Možnost konfigurace sítě VPN pro aplikaci prostřednictvím konfiguračního profilu aplikace Android Enterprise.
    Další informace najdete v tématu o [vytvoření profilu VPN pro aplikaci pro zařízení s Androidem pomocí vlastního profilu Microsoft Intune](android-pulse-secure-per-app-vpn.md).

## <a name="certificate-profiles"></a>Profily certifikátů

Na zařízeních s pracovním profilem Androidu jsou k dispozici stejné možnosti konfigurace profilů certifikátů, jaké jsou dostupné u správy Androidu. Android Enterprise poskytuje vylepšená rozhraní API pro správu certifikátů. Vylepšená správa certifikátů poskytuje následující funkce:

-  Zajišťuje uživatelům tiché a bezproblémové nasazení.
-  Zajišťuje odebrání nasazených certifikátů po vyřazení zařízení z Intune a odebrání pracovního profilu.
-  Poskytuje vylepšené zasílání zpráv uživatelům s informacemi o tom, že IT oddělení nasadilo a nakonfigurovalo prostřednictvím svojí služby správy certifikát.

Další informace najdete v tématu [Konfigurace profilu certifikátu pro zařízení v Microsoft Intune](certificates-configure.md).

## <a name="wi-fi-profiles"></a>Profily sítě Wi-Fi

Profily sítě Wi-Fi spravované Androidem Enterprise se po vyřazení zařízení z Intune a odstranění pracovního profilu odeberou. Další informace najdete v tématu [Jak nakonfigurovat nastavení Wi-Fi v Microsoft Intune](wi-fi-settings-configure.md).

## <a name="next-steps"></a>Další postup
- [Registrace zařízení s Androidem](android-enroll.md)
- [Přiřazení aplikací k zařízením s pracovním profilem Androidu pomocí Intune](apps-add-android-for-work.md)
