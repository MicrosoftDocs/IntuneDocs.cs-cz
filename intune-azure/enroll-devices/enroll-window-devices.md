---
title: "Registrace zařízení s Windows"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Naučte se povolit správu mobilních zařízení (MDM) v Intune pro zařízení s Windows."
keywords: 
author: staciebarker
manager: stabar
ms.date: 02/15/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 7262093700dab3a7befd5b82ac9f8ee3dde22dcf


---

# <a name="enroll-windows-devices"></a>Registrace zařízení s Windows 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

K nastavení registrace zařízení s Windows použijte jednu z následujících metod:

- [**Automatická registrace Windows 10 a Windows 10 Mobile ve službě Azure Active Directory Premium**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Tuto metodu je možné použít jenom pro zařízení s Windows 10 a Windows 10 Mobile.
 -  Abyste mohli tuto metodu použít, musíte mít službu Azure Active Directory Premium. Pokud ji nemáte, použijte metodu registrace určenou pro Windows 8.1 a Windows Phone 8.1.
 -  Pokud se rozhodnete, že nepovolíte automatickou registraci, použijte metodu registrace určenou pro Windows 8.1 a Windows Phone 8.1.

- [**Registrace Windows 8.1 a Windows Phone 8.1 pomocí konfigurace záznamu CNAME**](#set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname)
 - K registraci zařízení s Windows 8.1 a Windows Phone 8.1 musíte použít tuto metodu.


## <a name="prerequisites"></a>Požadavky

Pokud některé z následující požadavků ještě nejde zajistit v Intune Azure Preview, budete je muset zajistit z konzoly pro správu Intune Classic.

- [Konfigurace vlastního názvu domény](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Nastavení autority správy mobilních zařízení (MDM)](set-mdm-authority.md) na **Microsoft Intune**
- [Konfigurace aplikace Portál společnosti](/intune-azure/manage-apps/company-portal-app.md)
- Přiřazení licencí uživatelům

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>Nastavení registrace Windows 8.1 a Windows Phone 8.1 pomocí konfigurace CNAME

Nechte uživatele, ať si nainstalují aplikaci Portál společnosti služby Intune a použijí ji k registraci svých zařízení. Pokud vytvoříte záznamy prostředků DNS CNAME, uživatelé se mohou připojovat k Intune a registrovat se bez zadávání názvu serveru.

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

  `EnterpriseRegistration.windows.net` – podporuje zařízení s Windows 8.1 a Windows 10 Mobile, která k registraci do Azure Active Directory použijí pracovní nebo školní účet.

  Pokud vaše společnost používá více domén pro přihlašovací údaje uživatelů, vytvořte záznamy CNAME pro každou doménu.

  Pokud je třeba web vaší společnosti contoso.com, vytvořili byste záznam CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com. Změny záznamů DNS se mohou projevit až po 72 hodinách. Před rozšířením záznamu DNS nemůžete v Intune ověřit změny DNS.

2.  **Ověření CNAME**<br>V [konzole pro správu Intune](http://manage.microsoft.com) zvolte **Správa** &gt; **Správa mobilních zařízení** &gt; **Windows Phone**. Do pole **Zadejte název ověřené domény** zadejte adresu URL ověřené domény webu společnosti a zvolte **Test automatického zjištění**.

3.  **Volitelné kroky**<br>U Windows 10 není třeba provádět krok **Přidat klíče pro zkušební načtení**. <br>Krok **Nahrát na server certifikát pro podpis kódu** je potřeba jenom tehdy, když do zařízení distribuujete obchodní aplikace, které zařízení nemůžou získat z Windows Storu.

4.  **Informujte uživatele, jak si mají svá zařízení zaregistrovat a co mají očekávat, až budou zařízení spravovaná.**

    Postup registrace koncových uživatelů najdete v tématu [Registrace zařízení s Windows v Intune](https://docs.microsoft.com/en-us/intune/enduser/enroll-your-device-in-intune-windows). Uživatele můžete také nasměrovat na stránku [Co správce IT uvidí při registraci zařízení v Intune](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

    Další informace o úlohách pro koncové uživatele najdete v tématu [Materiály o prostředí Microsoft Intune pro koncové uživatele](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).

Pokud jste nenasadili Portál společnosti na zařízení, nejsou vyžadované žádné další kroky.  Kroky 2 a 3 v konzole správce můžete ignorovat.



<!--HONumber=Feb17_HO3-->


