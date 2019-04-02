---
title: Nastavení registrace pro zařízení s Windows pomocí Microsoft Intune
titleSuffix: ''
description: Nastavte registraci pro zařízení s Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/27/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d7dd4ab5f7cecfa8a765b6dfa038b73015a0c768
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798290"
---
# <a name="set-up-enrollment-for-windows-devices"></a>Nastavení registrace pro zařízení s Windows

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek pomáhá správcům IT zjednodušit svým uživatelům registraci zařízení s Windows. Jakmile [nastavíte Intune](setup-steps.md), mohou uživatelé registrovat svá zařízení s Windows tím, že se [přihlásí](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) pomocí pracovního nebo školního účtu.  

Jako správce Intune můžete registraci zjednodušit. Máte tyto možnosti:
- [Povolit automatickou registraci](#enable-windows-10-automatic-enrollment) (vyžaduje Azure AD Premium)
- [Registrace CNAME](#simplify-windows-enrollment-without-azure-ad-premium)
- [Povolit hromadnou registraci](windows-bulk-enroll.md) (vyžaduje Azure AD Premium a Windows Configuration Designer)

Způsob zjednodušení registrace zařízení s Windows určují dva faktory:

- **Používáte Azure Active Directory Premium?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) je součástí Enterprise Mobility + Security a dalších plánů licencování.
- **Jaké verze klientů Windows si uživatelé budou registrovat?** <br>Zařízení s Windows 10 se můžou zaregistrovat automaticky přidáním pracovního nebo školního účtu. Starší verze se musí zaregistrovat pomocí aplikace Portál společnosti.

||**Azure AD Premium**|**Jiné AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Automatická registrace](#enable-windows-10-automatic-enrollment) |Registrace uživatele|
|**Starší verze Windows**|Registrace uživatele|Registrace uživatele|

Organizace, které mohou používat automatickou registraci, také mohou nakonfigurovat [hromadnou registraci zařízení](windows-bulk-enroll.md) v aplikaci Windows Configuration Designer.

## <a name="multi-user-support"></a>Podpora více uživatelů

Intune podporuje vícenásobnou správu pro zařízení s Windows 10 Creators Updatem připojená k doméně Azure Active Directory. Když standardní uživatelé použijí k přihlášení přihlašovací údaje služby Azure AD, dostanou aplikace a zásady přiřazené ke svému uživatelskému jménu. Uživatelé v současnosti nemůžou používat Portál společnosti pro samoobslužné scénáře, například instalování aplikací.

[!INCLUDE [AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="simplify-windows-enrollment-without-azure-ad-premium"></a>Zjednodušení registrace zařízení s Windows bez služby Azure AD Premium
Pokud chcete uživatelům registraci zjednodušit, vytvořte alias serveru DNS (typu záznamu CNAME), který přesměruje žádosti o registraci na servery Intune. V opačném případě musí uživatelé, kteří se pokoušejí připojit k Intune, zadat během registrace název serveru Intune.

**Krok 1: Vytvořit záznam CNAME** (volitelné)<br>
Vytvořte záznamy o prostředcích DNS CNAME pro doménu vaší společnosti. Pokud má třeba vaše společnost web contoso.com, vytvořili byste ve službě DNS záznam CNAME, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com.

Vytváření položek CNAME DNS není povinné, ale záznamy CNAME usnadňují uživatelům registraci. Pokud se nenajde žádný záznam CNAME pro registraci, zobrazí se uživatelům výzva, aby ručně zadali název serveru MDM: enrollment.manage.microsoft.com.

|Typ|Název hostitele|Odkazuje na|TTL|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.doména_společnosti.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hodina|
|CNAME|EnterpriseRegistration.doména_společnosti.com|EnterpriseRegistration.windows.net|1 hodina|

Pokud podnik používá více než jednu příponu UPN, musíte vytvořit jeden CNAME pro každý název domény a každý z nich odkazovat na EnterpriseEnrollment-s.manage.microsoft.com. Uživatelé v Contosu například používají následující formáty jako svůj e-mail/UPN:

- name@contoso.com
- name@us.contoso.com
- name@eu.contoso.com

Správce DNS Contosa by měl vytvořit následující záznamy CNAME:

|Typ|Název hostitele|Odkazuje na|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hodina|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hodina|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hodina|

`EnterpriseEnrollment-s.manage.microsoft.com` – podporuje přesměrování do služby Intune s rozpoznáním domény z názvu domény v e-mailu.

Změny záznamů DNS se mohou projevit až po 72 hodinách. Před rozšířením záznamu DNS nemůžete v Intune ověřit změnu DNS.

## <a name="additional-endpoints-are-supported-but-not-recommended"></a>Další koncové body jsou podporované, ale nedoporučuje se
EnterpriseEnrollment-s.manage.microsoft.com je upřednostňovaný plně kvalifikovaný název domény pro zápis, ale existují dva další koncové body, které se používají zákazníci v minulosti a jsou podporovány. EnterpriseEnrollment.manage.microsoft.com (bez -s) a manage.microsoft.com oba fungují jako cíl pro automatické zjišťování serveru, ale uživatel se musejí dotýkat OK na potvrzovací zpráva. Pokud přejdete na EnterpriseEnrollment-s.manage.microsoft.com, uživatel nebude mít k tomu jedná se o doporučené konfiguraci dalšího kroku

## <a name="alternate-methods-of-redirection-are-not-supported"></a>Nejsou podporovány alternativní metody pro přesměrování
Pomocí jiné metody než konfigurace CNAME se nepodporuje. Například použití proxy serveru pro přesměrování enterpriseenrollment.contoso.com/EnrollmentServer/Discovery.svc buď enterpriseenrollment-s.manage.microsoft.com/EnrollmentServer/Discovery.svc nebo manage.microsoft.com/EnrollmentServer/Discovery.svc se nepodporuje.

**Krok 2: Ověření CNAME** (volitelné)<br>
1. V [Intune na webu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace zařízení s Windows** > **Ověření CNAME**.
2. Do pole **Doména** zadejte web společnosti a zvolte **Test**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Informování uživatelů, jak zařízení s Windows zaregistrovat
Informujte uživatele, jak si mají svá zařízení s Windows zaregistrovat a co můžou očekávat od zařazení do systému správy.

> [!NOTE]
> Koncoví uživatelé musí k webu Portál společnosti přistupovat přes Microsoft Edge, aby si mohli zobrazit aplikace Windows, které jste přiřadili ke konkrétním verzím Windows. Jiné prohlížeče, včetně Google Chrome, Mozilla Firefoxu a Internet Exploreru, tento typ filtrování nepodporují.

Postup registrace koncových uživatelů najdete v tématu [Registrace zařízení s Windows v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Uživatelům také můžete poradit, aby si přečetli článek o tom, [jaké informace vidí správce IT na zařízení](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

>[!IMPORTANT]
> Pokud není povolená automatická registrace MDM, ale máte zařízení s Windows 10 připojená ke službě Azure AD, zobrazí se v konzole Intune po registraci dva záznamy. Tomuto chování zabráníte tak, že uživatelé se zařízeními připojenými ke službě Azure AD přejdou na **Účty** > **Přístup do práce nebo do školy** a **Připojit** pomocí stejného účtu. 

Další informace o úlohách pro koncové uživatele najdete v tématu [Materiály o prostředí Microsoft Intune pro koncové uživatele](end-user-educate.md).

## <a name="next-steps"></a>Další postup

- [Co je třeba zvážit při správě zařízení Windows pomocí Intune v Azure](intune-legacy-pc-client.md)
