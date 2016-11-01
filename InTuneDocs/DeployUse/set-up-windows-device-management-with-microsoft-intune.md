---
title: "Nastavení správy pro zařízení s Windows v Microsoft Intune | Microsoft Intune"
description: "Povolte správu mobilních zařízení (MDM) pro počítače s Windows včetně zařízení s Windows 10 pomocí služby Microsoft Intune."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: dfc5241376033471a232b059ac07fa4488f05514
ms.openlocfilehash: c405408bd6a1e2b0743566e413436aefbaa7018b


---

# Nastavení správy pro zařízení Windows

Správce služby Intune má dvě možnosti, jak povolit registraci a správu počítačů s Windows:

- **[Automatická registrace do Azure Active Directory](#azure-active-directory-enrollment)** – Uživatelé Windows 10 a Windows 10 Mobile si zaregistrují svá zařízení tak, že do nich přidají pracovní nebo školní účet.
- **[Registrace pomocí Portálu společnosti](#company-portal-app-enrollment)** – Uživatelé zařízení s Windows Phone 8.1 a novějším si zaregistrují svá zařízení tak, že si stáhnou a nainstalují aplikaci Portál společnosti a potom v ní zadají přihlašovací údaje ke svému pracovnímu nebo školnímu účtu.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Nastavení registrace v aplikaci Portál společnosti
Nechte uživatele, ať si nainstalují aplikaci Portál společnosti služby Intune a použijí ji k registraci svých zařízení. Pokud vytvoříte záznamy prostředků DNS CNAME, uživatelé se mohou připojovat k Intune a registrovat se bez zadávání názvu serveru.

1. **Nastavení Intune**<br>
Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení tím, že [nastavíte autoritu pro správu mobilních zařízení (MDM)](prerequisites-for-enrollment.md#set-mobile-device-management-authority) na **Microsoft Intune** a pak nastavte MDM.

2. **Vytváření záznamů CNAME** (volitelné)<br>Pokud vytvoříte záznamy o prostředcích DNS **CNAME** pro doménu vaší společnosti, registrace se tím zjednoduší. Vytváření položek CNAME DNS není povinné, ale záznamy CNAME usnadňují uživatelům registraci. Pokud nebude nalezen žádný záznam CNAME pro registraci, budou uživatelé vyzváni, aby název serveru MDM zadali ručně. `https://manage.microsoft.com`. Záznamy o prostředcích CNAME musí obsahovat následující informace:

  |TYP|Název hostitele|Odkazuje na|Hodnota TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.doména_společnosti.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hodina|
  |CNAME|EnterpriseRegistration.doména_společnosti.com|EnterpriseRegistration.windows.net|1 hodina|

  `EnterpriseEnrollment-s.manage.microsoft.com` – podporuje přesměrování na služby Intune s rozpoznáním domény z doménového názvu e-mailu.

  `EnterpriseRegistration.windows.net` – podporuje zařízení s Windows 8.1 a Windows 10 Mobile, která k registraci do Azure Active Directory použijí pracovní nebo školní účet.

  Pokud vaše společnost používá více domén pro přihlašovací údaje uživatelů, vytvořte záznamy CNAME pro každou doménu.

  Pokud je třeba web vaší společnosti contoso.com, vytvořili byste záznam CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com. Změny záznamů DNS se mohou projevit až po 72 hodinách. Před rozšířením záznamu DNS nemůžete v Intune ověřit změny DNS.

3.  **Ověření CNAME**<br>V [konzole pro správu Intune](http://manage.microsoft.com) zvolte **Správa** &gt; **Správa mobilních zařízení** &gt; **Windows**. Do pole **Zadejte název ověřené domény** zadejte adresu URL ověřené domény webu společnosti a zvolte **Test automatického zjištění**.

  ![Dialogové okno správy zařízení s Windows](../media/enroll-intune-winenr.png)

4.  **Volitelné kroky**<br>U Windows 10 není třeba provádět krok **Přidat klíče pro zkušební načtení**. Krok **Nahrát na server certifikát pro podpis kódu** je potřeba jen tehdy, když budete distribuovat obchodní aplikace (LOB), které zařízení nemohou získat z Windows Storu. [Přečtěte si další informace](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

6.  **Informování uživatelů**<br>Budete muset informovat uživatele, jak si mají svá zařízení zaregistrovat a co mohou očekávat od zařazení do systému správy:
      - [Co říct koncovým uživatelům o používání služby Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Pokyny k zařízení s Windows pro koncové uživatele](../enduser/using-your-windows-device-with-intune.md)

### Viz taky
[Předpoklady pro registraci zařízení do Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Oct16_HO3-->


