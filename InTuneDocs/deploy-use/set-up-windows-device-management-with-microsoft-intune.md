---
title: "Nastavení správy pro zařízení s Windows v Microsoft Intune | Microsoft Intune"
description: "Povolte správu mobilních zařízení (MDM) pro počítače s Windows včetně zařízení s Windows 10 pomocí služby Microsoft Intune."
keywords: 
author: staciebarker
manager: stabar
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 13959c1456a0b160ce1fdcb76888d67cd13a5991


---

# <a name="set-up-windows-device-management"></a>Nastavení správy pro zařízení Windows

Správce služby Intune má dvě možnosti, jak povolit registraci a správu počítačů s Windows:

- **[Automatická registrace do Azure Active Directory](#azure-active-directory-enrollment)** – Uživatelé Windows 10 a Windows 10 Mobile si zaregistrují svá zařízení tak, že do nich přidají pracovní nebo školní účet.
- **[Registrace pomocí Portálu společnosti](#company-portal-app-enrollment)** – Uživatelé zařízení s Windows Phone 8.1 a novějším si zaregistrují svá zařízení tak, že si stáhnou a nainstalují aplikaci Portál společnosti a potom v ní zadají přihlašovací údaje ke svému pracovnímu nebo školnímu účtu.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-company-portal-app-enrollment"></a>Nastavení registrace v aplikaci Portál společnosti
Nechte uživatele, ať si nainstalují aplikaci Portál společnosti služby Intune a použijí ji k registraci svých zařízení. Pokud vytvoříte záznamy prostředků DNS CNAME, uživatelé se mohou připojovat k Intune a registrovat se bez zadávání názvu serveru.

1. **Nastavení Intune**<br>
Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení tím, že [nastavíte autoritu pro správu mobilních zařízení (MDM)](prerequisites-for-enrollment.md#set-mobile-device-management-authority) na **Microsoft Intune** a pak nastavte MDM.

2. **Vytváření záznamů CNAME** (volitelné)<br>Vytvořte záznamy o prostředcích DNS **CNAME** pro doménu vaší společnosti. Pokud má třeba vaše společnost web contoso.com, vytvořili byste ve službě DNS záznam CNAME, který přesměruje adresu EnterpriseEnrollment.contoso.com na enterpriseenrollment.manage.microsoft.com.

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

  ![Dialogové okno správy zařízení s Windows](../media/enroll-intune-winenr.png)

4.  **Volitelné kroky**<br>U Windows 10 není třeba provádět krok **Přidat klíče pro zkušební načtení**. Krok **Nahrát na server certifikát pro podpis kódu** je potřeba jen tehdy, když budete distribuovat obchodní aplikace (LOB), které zařízení nemohou získat z Windows Storu.

6.  **Informujte uživatele, jak si mají svá zařízení zaregistrovat a co mohou očekávat od zařazení do systému správy.**

    Postup registrace koncových uživatelů najdete v tématu [Registrace zařízení s Windows v Intune](../enduser/enroll-your-device-in-intune-windows.md).

    Další informace o úlohách koncových uživatelů najdete v článcích:
      - [Materiály o prostředí Microsoft Intune pro koncové uživatele](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Pokyny pro koncové uživatele zařízení s Windows](../enduser/using-your-windows-device-with-intune.md)

### <a name="see-also"></a>Viz taky
[Předpoklady registrace zařízení v Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Nov16_HO5-->


