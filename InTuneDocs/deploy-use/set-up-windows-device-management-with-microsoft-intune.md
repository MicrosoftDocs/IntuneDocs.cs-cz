---
title: "Nastavení správy pro zařízení s Windows v Microsoft Intune | Dokumentace Microsoftu"
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
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: f66bc5a26f137f62defef4a83a36b22247be4ec1
ms.lasthandoff: 03/22/2017


---

# <a name="set-up-windows-device-management"></a>Nastavení správy pro zařízení Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

K nastavení registrace zařízení s Windows použijte jednu z následujících metod:

- [**Automatická registrace Windows 10 a Windows 10 Mobile ve službě Azure Active Directory Premium**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Tuto metodu je možné použít jenom pro zařízení s Windows 10 a Windows 10 Mobile.
 -  Abyste mohli tuto metodu použít, musíte mít službu Azure Active Directory Premium. Pokud ji nemáte, použijte metodu registrace určenou pro Windows 8.1 a Windows Phone 8.1.
 -  Pokud se rozhodnete, že nepovolíte automatickou registraci, použijte metodu registrace určenou pro Windows 8.1 a Windows Phone 8.1.


- [**Registrace Windows 8.1 a Windows Phone 8.1 pomocí konfigurace záznamu CNAME**](#set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname)
 - K registraci zařízení s Windows 8.1 a Windows Phone 8.1 musíte použít tuto metodu.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>Nastavení registrace Windows 8.1 a Windows Phone 8.1 pomocí konfigurace CNAME
Nechte uživatele, ať si nainstalují aplikaci Portál společnosti služby Intune a použijí ji k registraci svých zařízení. Pokud vytvoříte záznamy prostředků DNS CNAME, uživatelé se mohou připojovat k Intune a registrovat se bez zadávání názvu serveru.

### <a name="step-1-set-up-intune"></a>Krok 1: Nastavte Intune

Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení tím, že [nastavíte autoritu pro správu mobilních zařízení (MDM)](prerequisites-for-enrollment.md#step-2-set-mdm-authority) na **Microsoft Intune** a pak nastavte MDM.

### <a name="step-2-create-cnames-optional"></a>Krok 2: Vytvořte záznamy CNAME (volitelné)

Vytvořte záznamy o prostředcích DNS **CNAME** pro doménu vaší společnosti. Pokud má třeba vaše společnost web contoso.com, vytvořili byste ve službě DNS záznam CNAME, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com.


   Vytváření položek CNAME DNS není povinné, ale záznamy CNAME usnadňují uživatelům registraci. Pokud se nenajde žádný záznam CNAME pro registraci, zobrazí se uživatelům výzva, aby ručně zadali název serveru MDM: enrollment.manage.microsoft.com.

   Záznamy o prostředcích CNAME musí obsahovat následující informace:

  |TYP|Název hostitele|Odkazuje na|Hodnota TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.doména_společnosti.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hodina|
  |CNAME|EnterpriseRegistration.doména_společnosti.com|EnterpriseRegistration.windows.net|1 hodina|

  `EnterpriseEnrollment-s.manage.microsoft.com` – podporuje přesměrování do služby Intune s rozpoznáním domény z názvu domény v e-mailu.

  `EnterpriseRegistration.windows.net` – podporuje zařízení s Windows 8.1 a Windows 10 Mobile, která k registraci do Azure Active Directory použijí pracovní nebo školní účet.

  Pokud vaše společnost používá více domén pro přihlašovací údaje uživatelů, vytvořte záznamy CNAME pro každou doménu.

  Pokud je třeba web vaší společnosti contoso.com, vytvořili byste záznam CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com. Změny záznamů DNS se mohou projevit až po 72 hodinách. Před rozšířením záznamu DNS nemůžete v Intune ověřit změny DNS.

### <a name="step-3-verify-cname"></a>Krok 3: Ověřte záznamy CNAME

V [konzole pro správu Intune](http://manage.microsoft.com) zvolte **Správa** &gt; **Správa mobilních zařízení** &gt; **Windows**. Do pole **Zadejte název ověřené domény** zadejte adresu URL ověřené domény webu společnosti a zvolte **Test automatického zjištění**.

### <a name="step-4-tell-your-users-how-to-enroll-their-devices-and-what-to-expect-after-theyre-brought-into-management"></a>Krok 4: Informujte uživatele, jak si mají svá zařízení zaregistrovat a co můžou očekávat od zařazení do systému správy

   Postup registrace koncových uživatelů najdete v tématu [Registrace zařízení s Windows v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows).

   Další informace o úlohách koncových uživatelů najdete v tématu [Co říct koncovým uživatelům o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune) a [Pokyny k zařízení s Windows pro koncové uživatele](https://docs.microsoft.com/intune-user-help/using-your-windows-device-with-intune).

### <a name="see-also"></a>Související témata
[Předpoklady registrace zařízení v Microsoft Intune](prerequisites-for-enrollment.md)

