---
title: "Nastavení správy pro zařízení Windows v Microsoft Intune"
description: "Povolte správu mobilních zařízení (MDM) pro zařízení s Windows pomocí služby Microsoft Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: cf77cb313d5a36c5e7975e70d54bf044aa2d30c8
ms.contentlocale: cs-cz
ms.lasthandoff: 06/08/2017


---

# <a name="set-up-windows-device-management"></a>Nastavení správy pro zařízení Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Toto téma pomáhá správcům IT zjednodušit svým uživatelům registraci zařízení s Windows.  Zařízení s Windows se dají zaregistrovat bez dodatečných kroků, ale registraci můžete uživatelům usnadnit.

Způsob zjednodušení registrace zařízení s Windows určují dva faktory:
- **Používáte Azure Active Directory Premium?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) je součástí Enterprise Mobility + Security a dalších plánů licencování.
- **Jaké verze klientů Windows se budou registrovat?** <br>Zařízení s Windows 10 se můžou zaregistrovat automaticky přidáním pracovního nebo školního účtu. Starší verze se musí zaregistrovat pomocí aplikace Portál společnosti.

||**Azure AD Premium**|**Jiné AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Automatická registrace](#enable-windows-10-automatic-enrollment) |[Registrace uživatele](#enable-windows-enrollment-without-azure-ad-premium)|
|**Starší verze Windows**|[Registrace uživatele](#enable-windows-enrollment-without-azure-ad-premium)|[Registrace uživatele](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a>Povolení registrace zařízení s Windows bez automatické registrace
Můžete umožnit, aby si uživatelé svá zařízení zaregistrovali bez automatické registrace Azure AD Premium. Jakmile přiřadíte licence, mohou se uživatelé zaregistrovat poté, co přidají svoje pracovní účty na svoje vlastní zařízení nebo připojí svoje firemní zařízení k Azure AD. Vytvoření aliasu DNS (typ záznamu CNAME) zjednodušuje uživatelům registraci zařízení. Pokud vytvoříte záznamy prostředků DNS CNAME, uživatelé se můžou připojit k Intune a zaregistrovat se, aniž by museli zadávat název serveru Intune.

**Krok 1: Vytvořte záznamy CNAME** (volitelné)<br>
Vytvořte záznamy o prostředcích DNS CNAME pro doménu vaší společnosti. Pokud má třeba vaše společnost web contoso.com, vytvořili byste ve službě DNS záznam CNAME, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com.

Vytváření položek CNAME DNS není povinné, ale záznamy CNAME usnadňují uživatelům registraci. Pokud se nenajde žádný záznam CNAME pro registraci, zobrazí se uživatelům výzva, aby ručně zadali název serveru MDM: enrollment.manage.microsoft.com.

Pokud existuje víc než jedna ověřená doména, vytvořte záznam CNAME pro každou doménu. Záznamy o prostředcích CNAME musí obsahovat tyto informace:

Záznamy o prostředcích CNAME musí obsahovat následující informace:

|TYP|Název hostitele|Odkazuje na|Hodnota TTL|
|--------|-------------|-------------|-------|
|CNAME|EnterpriseEnrollment.doména_společnosti.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hodina|
|CNAME|EnterpriseRegistration.doména_společnosti.com|EnterpriseRegistration.windows.net|1 hodina|

`EnterpriseEnrollment-s.manage.microsoft.com` – podporuje přesměrování do služby Intune s rozpoznáním domény z názvu domény v e-mailu.

Pokud vaše společnost používá více domén pro přihlašovací údaje uživatelů, vytvořte záznamy CNAME pro každou doménu.

Pokud je třeba web vaší společnosti contoso.com, vytvořili byste záznam CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com. Změny záznamů DNS se mohou projevit až po 72 hodinách. Před rozšířením záznamu DNS nemůžete v Intune ověřit změny DNS.

**Krok 2: Ověřte záznamy CNAME** (volitelné)<br>
V [konzole pro správu Intune](https://manage.microsoft.com) zvolte **Správa** &gt; **Správa mobilních zařízení** &gt; **Windows**. Do pole **Zadejte název ověřené domény** zadejte adresu URL ověřené domény webu společnosti a zvolte **Test automatického zjištění**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Informování uživatelů, jak zařízení s Windows zaregistrovat
Informujte uživatele, jak si mají svá zařízení s Windows zaregistrovat a co můžou očekávat od zařazení do systému správy.
Postup registrace koncových uživatelů najdete v tématu [Registrace zařízení s Windows v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Uživatele můžete také nasměrovat na článek [Co správce IT uvidí při registraci zařízení v Intune](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Další informace o úlohách pro koncové uživatele najdete v tématu [Materiály o prostředí Microsoft Intune pro koncové uživatele](/intune/end-user-educate).

### <a name="see-also"></a>Související témata
[Předpoklady registrace zařízení v Microsoft Intune](prerequisites-for-enrollment.md)

