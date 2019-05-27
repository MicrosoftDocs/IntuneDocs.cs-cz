---
title: Správa zařízení pracovním profilem Androidu Enterprise v Microsoft Intune
titleSuffix: ''
description: Microsoft Intune spravuje zařízení s Androidem Enterprise pracovním profilem poskytnout další možnosti správy a ochrany osobních údajů, když uživatelé používají při práci svoje osobní zařízení s Androidem.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2cc3c960-1fdd-47ca-a693-420d47b403de
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7d66a9ae4d72ef37f39c2017c4351847e8bace46
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66049896"
---
# <a name="manage-android-work-profile-devices-with-intune"></a>Správa zařízení s pracovním profilem Androidu v Intune

Android Enterprise nabízí sadu možností registrace, které uživatelům poskytnout nejaktuálnější a zabezpečené funkce. Registrace s pracovním profilem Androidu Enterprise umožňuje, aby sada funkcí a služeb, které oddělují osobní aplikace a data z pracovním aplikacím a datům. Poskytuje také další možnosti správy a ochrany osobních údajů Pokud uživatelé používají při práci svoje osobní zařízení s Androidem. 

## <a name="supported-devices"></a>Podporovaná zařízení

Android Enterprise možností správy používá funkce, které jsou součástí Androidu novější operační systémy. Pro zařízení, která nepodporují Androidu Enterprise zůstává k dispozici konvenční Správa Androidu. Další informace najdete v tématu [požadavky na Androidu Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="onboarding"></a>Připojení

Před registrací Androidu Enterprise pracovní profil zařízení, je třeba provést některé kroky registrace. Postup připojení mezi vaším tenantem Intune a spravovaný obchod Google Play. Další informace najdete v tématu [povolení registrace zařízení s Androidem Enterprise pracovním profilem](android-work-profile-enroll.md).

## <a name="work-profile-management"></a>Správa pracovních profilů

Při správě zařízení s Android Enterprise pracovního profilu pomocí Intune nespravujete celé zařízení. Možnosti správy mají vliv jenom na pracovní profil, který se vytvoří v zařízení během registrace. Všechny aplikace, které se nasadí na zařízení pomocí Intune, se nainstalují do pracovního profilu. Ikony aplikací v pracovním profilu jsou odlišené od osobních aplikací v zařízení. Všechny aplikace a data Androidu mimo část zařízení vyhrazenou pro Android Enterprise zůstanou osobní a pod kontrolou koncového uživatele. Uživatelé můžou do osobní části zařízení nainstalovat libovolnou aplikaci. Správci můžou spravovat a monitorovat aplikace a akce vymezené pro pracovní profil.

Intune poskytuje řadu předdefinovaných obecných nastavení, která můžete na zařízeních s pracovním profilem Androidu konfigurovat. Další informace najdete v tématu, které se věnuje [nastavení zásad na zařízeních s pracovním profilem Androidu](compliance-policy-create-android-for-work.md).

## <a name="app-publishing-and-distribution"></a>Publikování a distribuce aplikací

Spravovaný obchod Google Play je nedílnou součástí Androidu Enterprise, distribuce a správy aplikací. Všechny aplikace nasazené na zařízení s Androidem Enterprise pracovním profilem v pracovním profilu pocházejí ze služby spravovaný obchod Google Play. Pokud chcete v obchodu Play spravovat a nasazovat aplikace, přihlaste se na web Google Play pomocí přihlašovacích údajů správce vaší společnosti pro správu účtu Google. Můžete schvalovat aplikace pro Android Enterprise nasazení objevily v pracovních profilech zařízení. Tyto aplikace se potom budou synchronizovat s konzolou Intune, kde je pak možné je pomocí služby Intune nasadit a spravovat. Obchodní aplikace vyvinuté ve vaší organizaci se musí publikovat do spravovaného obchodu Google Play pomocí konzoly pro publikování aplikací pro Android od Googlu. Obchodní aplikace se musí nakonfigurovat na konzole pro publikování aplikací pro Android. Omezí se tak přístup do vaší organizace.

Aplikace se můžou instalovat bez interakce uživatelů, kteří ani nemusí povolit **instalaci z neznámých zdrojů**. Uživatelé můžou procházet obchod Play for Work a na svoje zařízení z něj instalovat volitelné nebo dostupné aplikace. Další informace najdete v tématu [přiřazování aplikací pro Android Enterprise pracovní profil zařízení v Intune](apps-add-android-for-work.md).

## <a name="app-configuration"></a>Konfigurace aplikací

Android Enterprise poskytuje infrastrukturu pro nasazení konfiguračních hodnot aplikací do aplikace, které je podporují. Když zadáte konfigurační hodnoty pro pracovní aplikace, zajistíte tak při prvním spuštění aplikace uživatelem jejich správné nastavení. Podpora konfigurace aplikace vyžaduje, aby vývojáři aplikací vytvářeli svoje aplikace výslovně tak, aby podporovaly hodnoty spravované konfigurace. V takovém případě pak můžou použít Intune k zadání a použití tohoto nastavení konfigurace. Další informace najdete v tématu [Přidání zásad konfigurace aplikací pro spravovaná zařízení s Androidem](app-configuration-policies-use-android.md).

## <a name="email-configuration"></a>Konfigurace e-mailu

Android Enterprise neposkytuje výchozí e-mailovou aplikaci ani nativní e-mailové objekt profilu jako poskytuje iOS. Místo toho je možné nastavit konfigurace e-mailu s použitím nastavení konfigurací aplikací u e-mailových aplikací, které je podporují. Gmail a Nine Work jsou dvě protokolu Exchange ActiveSync (EAS) klientské aplikace v Play Store, které podporují konfiguraci pomocí konfigurace aplikace pro Android Enterprise.

Když jsou aplikace Gmail a Nine Work spravované jako pracovní aplikace, služba Intune pro ně poskytuje šablony konfigurace. Jiné e-mailové aplikace, které podporují konfigurační profily aplikací, je možné nakonfigurovat pomocí zásad konfigurace mobilních aplikací.

Pokud používáte Exchange ActiveSync podmíněného přístupu pro zařízení s Androidem Enterprise pracovní profil, zvažte použití e-mailovou aplikaci Gmail nebo Nine Work. Podporuje se také aplikace Microsoft Outlook pro Android nebo kterákoliv jiná e-mailová aplikace, která používá moderní ověřování prostřednictvím ADAL. Další informace najdete v tématu [Jak nakonfigurovat nastavení e-mailu v Microsoft Intune](email-settings-configure.md).

## <a name="app-protection-policies"></a>Zásady ochrany aplikace

Používané zásady ochrany aplikace jsou plně podporované v pracovním i osobním profilu. Obchodní aplikace je možné publikovat na konzole pro publikování aplikací pro Android na adrese https://play.google.com/apps/publish. Tato konzola zahrnuje možnost nastavit pro vaši organizaci aplikace jako soukromé. Další informace najdete v tématu [přidat v Intune zásadu dodržování předpisů pro zařízení s Androidem Enterprise pracovním profilem](compliance-policy-create-android-for-work.md). Obecné informace o zásadách ochrany aplikací najdete v tématu [Co jsou zásady ochrany aplikací](app-protection-policy.md).

## <a name="vpn-profiles"></a>Profily sítě VPN

Podpora sítě VPN je podobná profilům Android VPN. Stejní poskytovatelé VPN i základní možnosti konfigurace jsou k dispozici pro Android Enterprise management s dva rozdíly:

-  **Síť VPN vymezená pro pracovní profil** – připojení VPN jsou omezená jenom na aplikace nasazené do pracovního profilu. Jenom Android Enterprise spravované aplikace můžou používat připojení k síti VPN. Osobní aplikace na zařízení spravované připojení VPN použít nemůžou. Další informace najdete v tématu [nastavení sítě VPN v Androidu Enterprise](vpn-settings-android.md#android-enterprise-vpn-settings).

-  **Síť VPN specifická pro aplikaci** – tuto síť lze v Intune nakonfigurovat, pokud poskytovatel VPN podporuje:
    - Konfiguraci sítě VPN specifické pro aplikaci
    - možnost konfigurace VPN pro aplikaci přes konfigurační profil aplikací Androidu Enterprise.
    Další informace najdete v tématu o [vytvoření profilu VPN pro aplikaci pro zařízení s Androidem pomocí vlastního profilu Microsoft Intune](android-pulse-secure-per-app-vpn.md).

## <a name="certificate-profiles"></a>Profily certifikátů

Stejný certifikát možnosti konfigurace profilu, které jsou k dispozici pro správy systému Android jsou dostupné na zařízeních s Androidem Enterprise pracovní profil. Android Enterprise poskytuje vylepšené certifikátu rozhraní API pro správu. Vylepšená správa certifikátů poskytuje následující funkce:

-  Zajišťuje uživatelům tiché a bezproblémové nasazení.
-  Zajišťuje odebrání nasazených certifikátů po vyřazení zařízení z Intune a odebrání pracovního profilu.
-  Poskytuje vylepšené zasílání zpráv uživatelům s informacemi o tom, že IT oddělení nasadilo a nakonfigurovalo prostřednictvím svojí služby správy certifikát.

Další informace najdete v tématu [Konfigurace profilu certifikátu pro zařízení v Microsoft Intune](certificates-configure.md).

## <a name="wi-fi-profiles"></a>Profily sítě Wi-Fi

Profily Wi-Fi spravuje Android Enterprise se po vyřazení zařízení z Intune a odstranění pracovního profilu odeberou. Další informace najdete v tématu [Jak nakonfigurovat nastavení Wi-Fi v Microsoft Intune](wi-fi-settings-configure.md).

## <a name="next-steps"></a>Další postup
- [Registrace zařízení s Androidem](android-enroll.md)
- [Přiřazení aplikací do zařízení pracovním profilem Androidu s Intune](apps-add-android-for-work.md)
