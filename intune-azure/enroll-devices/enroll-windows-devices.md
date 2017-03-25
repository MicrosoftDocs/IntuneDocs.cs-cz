---
title: "Registrace zařízení s Windows"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Naučte se povolit správu mobilních zařízení (MDM) v Intune pro zařízení s Windows."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 03/15/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: a95aca706a4996d40e268a80c7c334ebb9854df5
ms.openlocfilehash: 6cbaf8414452f11f0aa97616bbed2cf164b49ac0
ms.lasthandoff: 03/15/2017


---

# <a name="enroll-windows-devices"></a>Registrace zařízení s Windows

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

K nastavení registrace zařízení s Windows použijte jednu z následujících metod:

- [**Automatická registrace Windows 10 a Windows 10 Mobile ve službě Azure Active Directory Premium**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Tuto metodu je možné použít jenom pro zařízení s Windows 10 a Windows 10 Mobile.
 -  Abyste mohli tuto metodu použít, musíte mít službu Azure Active Directory Premium. Pokud ji nemáte, použijte metodu registrace určenou pro Windows 8.1 a Windows Phone 8.1.
 -  Pokud se rozhodnete, že nepovolíte automatickou registraci, použijte metodu registrace určenou pro Windows 8.1 a Windows Phone 8.1.

- [**Registrace Windows 8.1 a Windows Phone 8.1 pomocí konfigurace záznamu CNAME**](#simplify-enrollment-by-configuring-cname)
 - K registraci zařízení s Windows 8.1 a Windows Phone 8.1 musíte použít tuto metodu.
 - Tuto metodu můžete také použít, pokud nemáte Azure Active Directory (AD) Premium.


## <a name="prerequisites"></a>Požadavky

Pokud některé z následující požadavků ještě nejde zajistit v Intune Azure Preview, budete je muset zajistit z konzoly pro správu Intune Classic.

- [Konfigurace vlastního názvu domény](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Nastavení autority správy mobilních zařízení (MDM)](set-mdm-authority.md) na **Microsoft Intune**
- [Konfigurace aplikace Portál společnosti](/intune-azure/manage-apps/company-portal-app.md)
- Přiřazení licencí uživatelům

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-workplace-enrollment"></a>Povolení registrace pracoviště Windows

Můžete umožnit, aby si uživatelé svá zařízení instalovali a zaregistrovali bez automatické registrace Azure AD Premium. Pokud vytvoříte záznamy prostředků DNS CNAME, uživatelé se mohou připojovat k Intune a registrovat se bez zadávání názvu serveru.

1. **Vytváření záznamů CNAME** (volitelné)<br>
 Vytvořte záznamy o prostředcích DNS **CNAME** pro doménu vaší společnosti. Pokud má třeba vaše společnost web contoso.com, vytvořili byste ve službě DNS záznam CNAME, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com.

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

2.  **Ověření CNAME**<br>Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**. V okně Intune zvolte **Registrovat zařízení** > **Registrace zařízení s Windows**. Do pole **Zadejte název ověřené domény** zadejte adresu URL ověřené domény webu společnosti a zvolte **Test automatického zjištění**.

3.  **Informujte uživatele, jak si mají svá zařízení zaregistrovat a co mají očekávat, až budou zařízení spravovaná.**

    Postup registrace koncových uživatelů najdete v tématu [Registrace zařízení s Windows v Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). Uživatele můžete také nasměrovat na stránku [Co správce IT uvidí při registraci zařízení v Intune](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

    Další informace o úlohách pro koncové uživatele najdete v tématu [Materiály o prostředí Microsoft Intune pro koncové uživatele](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).

Pokud jste nenasadili Portál společnosti na zařízení, nejsou vyžadované žádné další kroky.  Kroky 2 a 3 v konzole správce můžete ignorovat.

