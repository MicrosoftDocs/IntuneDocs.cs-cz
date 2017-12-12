---
title: "Registrace zařízení s Windows"
titlesuffix: Azure portal
description: "Naučte se povolit správu mobilních zařízení (MDM) v Intune pro zařízení s Windows."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 11/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0c4c245829a7819c9427a8ebe8ad9e166b58da97
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/01/2017
---
# <a name="enroll-windows-devices"></a>Registrace zařízení s Windows

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Toto téma pomáhá správcům IT zjednodušit svým uživatelům registraci zařízení s Windows. Jakmile [nastavíte Intune](setup-steps.md), mohou uživatelé registrovat svá zařízení s Windows tím, že se [přihlásí](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) pomocí pracovního nebo školního účtu.  

Jako správce Intune můžete registraci zjednodušit. Máte tyto možnosti:
- [Povolit automatickou registraci](#enable-windows-10-automatic-enrollment) (vyžaduje Azure AD Premium)
- [Registrace CNAME](#simplify-windows-enrollment-without-azure-ad-premium)
- [Povolit hromadnou registraci](windows-bulk-enroll.md) (vyžaduje Azure AD Premium a Windows Configuration Designer)
- [Přidat vlastní zprávu](windows-enrollment-status.md), abyste pozdravili uživatele, když se registrují, a aby viděli průběh použití nastavení zásad

Způsob zjednodušení registrace zařízení s Windows určují dva faktory:

- **Používáte Azure Active Directory Premium?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) je součástí Enterprise Mobility + Security a dalších plánů licencování.
- **Jaké verze klientů Windows si uživatelé budou registrovat?** <br>Zařízení s Windows 10 se můžou zaregistrovat automaticky přidáním pracovního nebo školního účtu. Starší verze se musí zaregistrovat pomocí aplikace Portál společnosti.

||**Azure AD Premium**|**Jiné AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Automatická registrace](#enable-windows-10-automatic-enrollment) |[Registrace uživatele](#enable-windows-enrollment-without-azure-ad-premium)|
|**Starší verze Windows**|[Registrace uživatele](#enable-windows-enrollment-without-azure-ad-premium)|[Registrace uživatele](#enable-windows-enrollment-without-azure-ad-premium)|

Organizace, které mohou používat automatickou registraci, také mohou nakonfigurovat [hromadnou registraci zařízení](windows-bulk-enroll.md) v aplikaci Windows Configuration Designer.

**Podpora více uživatelů**<br>
Zařízení se systémem Windows 10 Creators Update připojená k doméně Azure Active Directory mají teď podporu správy více uživatelů pomocí Intune. Když standardní uživatelé použijí k přihlášení přihlašovací údaje služby Azure AD, dostanou aplikace a zásady přiřazené ke svému uživatelskému jménu. Uživatelé v současnosti nemůžou používat Portál společnosti pro samoobslužné scénáře, například instalování aplikací.

[!INCLUDE[AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="simplify-windows-enrollment-without-azure-ad-premium"></a>Zjednodušení registrace zařízení s Windows bez služby Azure AD Premium
Registraci můžete uživatelům zjednodušit vytvořením aliasu serveru DNS (záznamu typu CNAME), který automaticky přesměruje žádosti o registraci na servery Intune. Pokud záznam o prostředcích DNS CNAME nevytvoříte, musí uživatelé, kteří se pokouší připojit k Intune, při registraci zadat název serveru Intune.

**Krok 1: Vytvořte záznamy CNAME** (volitelné)<br>
Vytvořte záznamy o prostředcích DNS CNAME pro doménu vaší společnosti. Pokud má třeba vaše společnost web contoso.com, vytvořili byste ve službě DNS záznam CNAME, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com.

Vytváření položek CNAME DNS není povinné, ale záznamy CNAME usnadňují uživatelům registraci. Pokud se nenajde žádný záznam CNAME pro registraci, zobrazí se uživatelům výzva, aby ručně zadali název serveru MDM: enrollment.manage.microsoft.com.

|Typ|Název hostitele|Odkazuje na|Hodnota TTL|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.doména_společnosti.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hodina|
|CNAME|EnterpriseRegistration.doména_společnosti.com|EnterpriseRegistration.windows.net|1 hodina|

Pokud máte více než jednu příponu UPN, musíte vytvořit jeden CNAME pro každý název domény a každý z nich odkazovat na EnterpriseEnrollment-s.manage.microsoft.com. Pokud uživatelé ve společnosti Contoso používají e-mail / hlavní název uživatele (UPN) name@contoso.com, ale používají také name@us.contoso.com a name@eu.constoso.com, měl by správce DNS společnosti Contoso vytvořit následující záznamy CNAME:

|Typ|Název hostitele|Odkazuje na|Hodnota TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hodina|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hodina|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hodina|

`EnterpriseEnrollment-s.manage.microsoft.com` – podporuje přesměrování do služby Intune s rozpoznáním domény z názvu domény v e-mailu.

Změny záznamů DNS se mohou projevit až po 72 hodinách. Před rozšířením záznamu DNS nemůžete v Intune ověřit změny DNS.

**Krok 2: Ověřte záznamy CNAME** (volitelné)<br>
Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**. V okně Intune zvolte **Registrovat zařízení** > **Registrace zařízení s Windows**. Do pole **Zadejte název ověřené domény** zadejte adresu URL webu společnosti a zvolte **Test automatického zjištění**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Informování uživatelů, jak zařízení s Windows zaregistrovat
Informujte uživatele, jak si mají svá zařízení s Windows zaregistrovat a co můžou očekávat od zařazení do systému správy.

> [!NOTE]
> Koncoví uživatelé musí k webu Portál společnosti přistupovat přes Microsoft Edge, aby si mohli zobrazit aplikace Windows, které jste přiřadili ke konkrétním verzím Windows. Jiné prohlížeče, včetně Google Chrome, Mozilla Firefoxu a Internet Exploreru, tento typ filtrování nepodporují.

Postup registrace koncových uživatelů najdete v tématu [Registrace zařízení s Windows v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Uživatelům také můžete poradit, aby si přečetli článek o tom, [jaké informace vidí správce IT na zařízení](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Další informace o úlohách pro koncové uživatele najdete v tématu [Materiály o prostředí Microsoft Intune pro koncové uživatele](end-user-educate.md).

## <a name="next-steps"></a>Další kroky

- [Co je třeba zvážit při správě zařízení Windows pomocí Intune v Azure](/intune-classic/deploy-use/intune-on-azure.md)
