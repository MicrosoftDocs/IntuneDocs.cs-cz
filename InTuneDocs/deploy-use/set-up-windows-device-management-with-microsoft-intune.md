---
title: "Nastavení správy pro zařízení s Windows v Microsoft Intune | Dokumentace Microsoftu"
description: "Povolte správu mobilních zařízení (MDM) pro zařízení s Windows pomocí služby Microsoft Intune."
keywords: 
author: staciebarker
manager: stabar
ms.date: 02/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 45c32cf08e4d6fd570af287ed64411edc9d9b394
ms.openlocfilehash: e020ac2a4f600a94e7409e04c4c48f0c405c56cf


---

# <a name="set-up-windows-device-management"></a>Nastavení správy pro zařízení Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

K nastavení registrace zařízení s Windows použijte jednu z následujících metod:

- **[Automatická registrace Windows 10 a Windows 10 Mobile ve službě Azure Active Directory Premium](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)** 
 -  Tuto metodu je možné použít jenom pro zařízení s Windows 10 a Windows 10 Mobile.
 -  Abyste mohli tuto metodu použít, musíte mít službu Azure Active Directory Premium. Pokud ji nemáte, použijte metodu registrace určenou pro Windows 8.1 a Windows Phone 8.1.
 -  Pokud se rozhodnete, že nepovolíte automatickou registraci, použijte metodu registrace určenou pro Windows 8.1 a Windows Phone 8.1.


- **[Registrace Windows 8.1 a Windows Phone 8.1 pomocí konfigurace CNAME](#set-up-windows-8--1-and-windows-phone-8--1-enrollment-by-configuring-cname)** 
 - K registraci zařízení s Windows 8.1 a Windows Phone 8.1 musíte použít tuto metodu.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>Nastavení registrace Windows 8.1 a Windows Phone 8.1 pomocí konfigurace CNAME
Nechte uživatele, ať si nainstalují aplikaci Portál společnosti služby Intune a použijí ji k registraci svých zařízení. Pokud vytvoříte záznamy prostředků DNS CNAME, uživatelé se mohou připojovat k Intune a registrovat se bez zadávání názvu serveru.

1. **Nastavení Intune**<br>
Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení tím, že [nastavíte autoritu pro správu mobilních zařízení (MDM)](prerequisites-for-enrollment.md#step-2-set-mdm-authority) na **Microsoft Intune** a pak nastavte MDM.

2. **Vytváření záznamů CNAME** (volitelné)<br>
Vytvořte záznamy o prostředcích DNS **CNAME** pro doménu vaší společnosti. Pokud má třeba vaše společnost web contoso.com, vytvořili byste ve službě DNS záznam CNAME, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com.

    Vytváření položek CNAME DNS není povinné, ale záznamy CNAME usnadňují uživatelům registraci. Pokud se nenajde žádný záznam CNAME pro registraci, zobrazí se uživatelům výzva, aby ručně zadali název serveru MDM: enrollment.manage.microsoft.com.    

    Pokud máte v současnosti ve službě DNS záznam CNAME, který přesměrovává adresu EnterpriseEnrollment.contoso.com na adresu manage.microsoft.com, doporučujeme nahradit ho záznamem CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na adresu enterpriseenrollment-s.manage.microsoft.com. Tuto změnu doporučujeme, protože koncový bod manage.microsoft.com už bude v budoucí verzi pro registrace zastaralý.

    Záznamy o prostředcích CNAME musí obsahovat následující informace:

  |TYP|Název hostitele|Odkazuje na|Hodnota TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.doména_společnosti.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hodina|
  |CNAME|EnterpriseRegistration.doména_společnosti.com|EnterpriseRegistration.windows.net|1 hodina|

  `EnterpriseEnrollment-s.manage.microsoft.com` – podporuje přesměrování do služby Intune s rozpoznáním domény z názvu domény v e-mailu.

  `EnterpriseRegistration.windows.net` – podporuje zařízení s Windows 8.1 a Windows 10 Mobile, která k registraci do Azure Active Directory použijí pracovní nebo školní účet.

  Pokud vaše společnost používá více domén pro přihlašovací údaje uživatelů, vytvořte záznamy CNAME pro každou doménu.

  Pokud je třeba web vaší společnosti contoso.com, vytvořili byste záznam CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com. Změny záznamů DNS se mohou projevit až po 72 hodinách. Před rozšířením záznamu DNS nemůžete v Intune ověřit změny DNS.

3.  **Ověření CNAME**<br>V [konzole pro správu Intune](http://manage.microsoft.com) zvolte **Správa** &gt; **Správa mobilních zařízení** &gt; **Windows**. Do pole **Zadejte název ověřené domény** zadejte adresu URL ověřené domény webu společnosti a zvolte **Test automatického zjištění**.

4.  **Informujte uživatele, jak si mají svá zařízení zaregistrovat a co mohou očekávat od zařazení do systému správy.**

    Postup registrace koncových uživatelů najdete v tématu [Registrace zařízení s Windows v Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows).

    Další informace o úlohách pro koncové uživatele najdete v tématu [Materiály o prostředí Microsoft Intune pro koncové uživatele](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).


### <a name="see-also"></a>Související témata
[Předpoklady registrace zařízení v Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Feb17_HO2-->


