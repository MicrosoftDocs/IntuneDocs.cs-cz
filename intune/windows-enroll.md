---
title: "Registrace zařízení s Windows"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Naučte se povolit správu mobilních zařízení (MDM) v Intune pro zařízení s Windows."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 687be18cedd063b3c2701937f2522e801e51644b
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-windows-devices"></a>Registrace zařízení s Windows

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Toto téma pomáhá správcům IT zjednodušit svým uživatelům registraci zařízení s Windows.  Zařízení s Windows se dají zaregistrovat bez dodatečných kroků, ale registraci můžete uživatelům usnadnit.

Zařízení se systémem Windows 10 Creators Update připojená k doméně Azure Active Directory mají teď podporu správy více uživatelů pomocí Intune. To znamená, že když se k zařízení přihlásí různí standardní uživatelé pomocí svých přihlašovacích údajů Azure AD, dostanou všechny aplikace a zásady přiřazené jejich uživatelskému jménu. Uživatelé v současnosti nemůžou používat Portál společnosti pro samoobslužné scénáře, například instalování aplikací.

Způsob zjednodušení registrace zařízení s Windows určují dva faktory:

- **Používáte Azure Active Directory Premium?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) je součástí Enterprise Mobility + Security a dalších plánů licencování.
- **Jaké verze klientů Windows se budou registrovat?** <br>Zařízení s Windows 10 se můžou zaregistrovat automaticky přidáním pracovního nebo školního účtu. Starší verze se musí zaregistrovat pomocí aplikace Portál společnosti.

||**Azure AD Premium**|**Jiné AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Automatická registrace](#enable-windows-10-automatic-enrollment) |[Registrace uživatele](#enable-windows-enrollment-without-azure-ad-premium)|
|**Starší verze Windows**|[Registrace uživatele](#enable-windows-enrollment-without-azure-ad-premium)|[Registrace uživatele](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-azure-ad-premium"></a>Povolení registrace zařízení se systémem Windows bez Azure AD Premium
Můžete umožnit, aby si uživatelé svá zařízení zaregistrovali bez automatické registrace Azure AD Premium. Jakmile přiřadíte licence, mohou se uživatelé zaregistrovat poté, co přidají svoje pracovní účty na svoje vlastní zařízení nebo připojí svoje firemní zařízení k Azure AD. Vytvoření aliasu DNS (typ záznamu CNAME) zjednodušuje uživatelům registraci zařízení. Pokud vytvoříte záznamy prostředků DNS CNAME, uživatelé se můžou připojit k Intune a zaregistrovat se, aniž by museli zadávat název serveru Intune.

**Krok 1: Vytvořte záznamy CNAME** (volitelné)<br>
Vytvořte záznamy o prostředcích DNS CNAME pro doménu vaší společnosti. Pokud má třeba vaše společnost web contoso.com, vytvořili byste ve službě DNS záznam CNAME, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com.

Vytváření položek CNAME DNS není povinné, ale záznamy CNAME usnadňují uživatelům registraci. Pokud se nenajde žádný záznam CNAME pro registraci, zobrazí se uživatelům výzva, aby ručně zadali název serveru MDM: enrollment.manage.microsoft.com.

|Typ|Název hostitele|Odkazuje na|Hodnota TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.doména_společnosti.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hodina|

Pokud máte více než jednu příponu UPN, musíte vytvořit jeden CNAME pro každý název domény a každý z nich odkazovat na EnterpriseEnrollment-s.manage.microsoft.com. Pokud třeba uživatelé ve společnosti Contoso jako svůj e-mail/UPN používají name@contoso.com, ale také name@us.contoso.com a name@eu.constoso.com, správce DNS společnosti Contoso musí vytvořit následující záznamy CNAME.

|Typ|Název hostitele|Odkazuje na|Hodnota TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hodina|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 hodina|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 hodina|

`EnterpriseEnrollment-s.manage.microsoft.com` – podporuje přesměrování do služby Intune s rozpoznáním domény z názvu domény v e-mailu.

Změny záznamů DNS se mohou projevit až po 72 hodinách. Před rozšířením záznamu DNS nemůžete v Intune ověřit změny DNS.

**Krok 2: Ověřte záznamy CNAME** (volitelné)<br>
Na portálu Azure Intune zvolte **Další služby** > **Monitorování + správa** > **Intune**. V okně Intune zvolte **Registrovat zařízení** > **Registrace zařízení s Windows**. Do pole **Zadejte název ověřené domény** zadejte adresu URL ověřené domény webu společnosti a zvolte **Test automatického zjištění**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Informování uživatelů, jak zařízení s Windows zaregistrovat
Informujte uživatele, jak si mají svá zařízení s Windows zaregistrovat a co můžou očekávat od zařazení do systému správy. Postup registrace koncových uživatelů najdete v tématu [Registrace zařízení s Windows v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Uživatele můžete také informovat, [co správce IT uvidí při registraci zařízení v Intune](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Další informace o úlohách pro koncové uživatele najdete v tématu [Materiály o prostředí Microsoft Intune pro koncové uživatele](https://docs.microsoft.com/intune-classic/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

