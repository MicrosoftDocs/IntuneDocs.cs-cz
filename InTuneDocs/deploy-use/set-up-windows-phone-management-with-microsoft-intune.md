---
title: "Nastavení správy pro Windows Phone a Windows 10 Mobile | Microsoft Intune"
description: "Povolte správu mobilních zařízení (MDM) pro zařízení s Windows 10 Mobile nebo Windows Phone pomocí služby Microsoft Intune."
keywords: 
author: staciebarker
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c59707ba2967b069dc30aee71d2642e91d71b23b
ms.openlocfilehash: 3141d4b2ad1a21e2ac5ba7b6cafb74f567d07f7a


---


# <a name="set-up-windows-phone-and-windows-10-mobile-management-with-microsoft-intune"></a>Nastavení správy pro Windows Phone a Windows 10 Mobile v Microsoft Intune

Správce služby Intune má dvě možnosti, jak povolit registraci a správu zařízení se systémem Windows 10 Mobile a Windows Phone:

- **[Automatická registrace do Azure Active Directory](#azure-active-directory-enrollment)** – Uživatelé Windows 10 a Windows 10 Mobile si zaregistrují svá zařízení tak, že do nich přidají pracovní nebo školní účet.
- **[Registrace pomocí Portálu společnosti](#company-portal-app-enrollment)** – uživatelé zařízení s Windows Phone 8.1 a novějším si zaregistrují svá zařízení tak, že si stáhnou a nainstalují aplikaci Portál společnosti a potom v ní zadají přihlašovací údaje ke svému pracovnímu nebo školnímu účtu.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="company-portal-app-enrollment"></a>Registrace aplikace Portál společnosti
Nechte uživatele, ať si nainstalují aplikaci Portál společnosti služby Intune a použijí ji k registraci svých zařízení. Pokud vytvoříte záznamy prostředků DNS CNAME, uživatelé se mohou připojovat k Intune a registrovat se bez zadávání názvu serveru.

1.  **Nastavení Intune**<br>Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení tím, že [nastavíte autoritu pro správu mobilních zařízení (MDM)](prerequisites-for-enrollment.md#step-2-set-mdm-authority) na **Microsoft Intune** a pak nastavte MDM.

2.  **Vytváření záznamů CNAME** (volitelné)<br>Vytvořte záznamy o prostředcích DNS **CNAME** pro doménu vaší společnosti. Pokud má třeba vaše společnost web contoso.com, vytvořili byste ve službě DNS záznam CNAME, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com.

    Vytváření položek CNAME DNS není povinné, ale záznamy CNAME usnadňují uživatelům registraci. Pokud nebude nalezen žádný záznam CNAME pro registraci, budou uživatelé vyzváni, aby zadali ručně název serveru MDM, https://manage.microsoft.com.

    Pokud máte v současnosti ve službě DNS záznam CNAME, který přesměrovává adresu EnterpriseEnrollment.contoso.com na adresu manage.microsoft.com, doporučujeme nahradit ho záznamem CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na adresu enterpriseenrollment-s.manage.microsoft.com. Tuto změnu doporučujeme, protože koncový bod manage.microsoft.com už bude v budoucí verzi pro registrace zastaralý.

    Pokud existuje víc než jedna ověřená doména, vytvořte záznam CNAME pro každou doménu. Záznamy o prostředcích CNAME musí obsahovat tyto informace:

  |TYP|Název hostitele|Odkazuje na|Hodnota TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.doména_společnosti.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hodina|
  |CNAME|EnterpriseRegistration.doména_společnosti.com|EnterpriseRegistration.windows.net|1 hodina|

  `EnterpriseEnrollment-s.manage.microsoft.com` – podporuje přesměrování do služby Intune s rozpoznáním domény z názvu domény v e-mailu.

  `EnterpriseRegistration.windows.net` – podporuje zařízení s Windows 8.1 a Windows 10 Mobile, která k registraci do Azure Active Directory použijí pracovní nebo školní účet.

  Pokud vaše společnost používá více domén pro přihlašovací údaje uživatelů, vytvořte záznamy CNAME pro každou doménu.

  Pokud je třeba web vaší společnosti contoso.com, vytvořili byste záznam CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com. Změny záznamů DNS se mohou projevit až po 72 hodinách. Před rozšířením záznamu DNS nemůžete v Intune ověřit změny DNS.

3.  **Ověření CNAME**<br>V [konzole pro správu Intune](http://manage.microsoft.com) zvolte **Správa** &gt; **Správa mobilních zařízení** &gt; **Windows Phone**. Do pole **Zadejte název ověřené domény** zadejte adresu URL ověřené domény webu společnosti a zvolte **Test automatického zjištění**.

    ![Dialogové okno Instalace správy mobilního zařízení pro systém Windows](../media/windows-phone-enrollment.png)

4.  **Volitelné kroky**<br>U Windows 10 není třeba provádět krok **Přidat klíče pro zkušební načtení**. Krok **Nahrát na server certifikát pro podpis kódu** je potřeba jenom tehdy, když distribuujete obchodní aplikace (LOB), které zařízení nemůžou získat z Windows Storu.

5.  **Informujte uživatele, jak můžou svá zařízení zaregistrovat, aby získali přístup k firemním prostředkům.**

    Postup registrace koncových uživatelů najdete v tématu [Registrace zařízení s Windows v Intune](../enduser/enroll-your-device-in-intune-windows.md). Můžete také uživatele odkázat na téma [Co správce IT uvidí při registraci zařízení v Intune](../enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

    Informace o dalších úlohách koncových uživatelů najdete v článcích:
    - [Co říct koncovým uživatelům o používání služby Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Pokyny pro koncové uživatele zařízení s Windows](../enduser/using-your-windows-device-with-intune.md)

Pokud jste nenasadili Portál společnosti na zařízení, nejsou vyžadované žádné další kroky.  Kroky 2 a 3 v konzole správce můžete ignorovat.



<!--HONumber=Dec16_HO2-->


