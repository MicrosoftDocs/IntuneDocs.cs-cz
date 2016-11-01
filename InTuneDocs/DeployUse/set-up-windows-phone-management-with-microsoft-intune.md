---
title: "Nastavení správy pro Windows Phone a Windows 10 Mobile | Microsoft Intune"
description: "Povolte správu mobilních zařízení (MDM) pro zařízení s Windows 10 Mobile nebo Windows Phone pomocí služby Microsoft Intune."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0b4bf6aa6fa9d693c0458562e7fcb71fc8000bb4
ms.openlocfilehash: 46bd457af51d3fac513cfc36af1766e1e37222cd


---


# Nastavení správy pro Windows Phone a Windows 10 Mobile v Microsoft Intune

Správce služby Intune má dvě možnosti, jak povolit registraci a správu zařízení se systémem Windows 10 Mobile a Windows Phone:

- **[Automatická registrace do Azure Active Directory](#azure-active-directory-enrollment)** – Uživatelé Windows 10 a Windows 10 Mobile si zaregistrují svá zařízení tak, že do nich přidají pracovní nebo školní účet.
- **[Registrace pomocí Portálu společnosti](#company-portal-app-enrollment)** – uživatelé zařízení s Windows Phone 8.1 a novějším si zaregistrují svá zařízení tak, že si stáhnou a nainstalují aplikaci Portál společnosti a potom v ní zadají přihlašovací údaje ke svému pracovnímu nebo školnímu účtu.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Registrace aplikace Portál společnosti
Nechte uživatele, ať si nainstalují aplikaci Portál společnosti služby Intune a použijí ji k registraci svých zařízení. Pokud vytvoříte záznamy prostředků DNS CNAME, uživatelé se mohou připojovat k Intune a registrovat se bez zadávání názvu serveru. Pokud spravujete zařízení s Windows Phone 8.0 nebo potřebujete nasadit portál společnosti na zařízení s Windows Phone, musíte si také stáhnout aplikaci Portál společnosti a podepsat ji. Viz [Nastavení správy pro zařízení Windows Phone 8.0](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Nastavení Intune**<br>Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení tím, že [nastavíte autoritu pro správu mobilních zařízení (MDM)](prerequisites-for-enrollment.md#set-mobile-device-management-authority) na **Microsoft Intune** a pak nastavte MDM.

2.  **Vytváření záznamů CNAME** (volitelné)<br>Vytvořte záznamy o prostředcích DNS **CNAME** pro doménu vaší společnosti. Pokud je třeba web vaší společnosti contoso.com, vytvořili byste záznam CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na manage.microsoft.com. Pokud existuje víc než jedna ověřená doména, vytvořte záznam CNAME pro každou doménu. Záznamy o prostředcích CNAME musí obsahovat tyto informace:

  |TYP|Název hostitele|Odkazuje na|Hodnota TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.doména_společnosti.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hodina|
  |CNAME|EnterpriseRegistration.doména_společnosti.com|EnterpriseRegistration.windows.net|1 hodina|

  `EnterpriseEnrollment-s.manage.microsoft.com` – podporuje přesměrování na služby Intune s rozpoznáním domény z doménového názvu e-mailu.

  `EnterpriseRegistration.windows.net` – podporuje zařízení s Windows 8.1 a Windows 10 Mobile, která k registraci do Azure Active Directory použijí pracovní nebo školní účet.

  Pokud vaše společnost používá více domén pro přihlašovací údaje uživatelů, vytvořte záznamy CNAME pro každou doménu.

  Pokud je třeba web vaší společnosti contoso.com, vytvořili byste záznam CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com. Změny záznamů DNS se mohou projevit až po 72 hodinách. Před rozšířením záznamu DNS nemůžete v Intune ověřit změny DNS.

3.  **Ověření CNAME**<br>V [konzole pro správu Intune](http://manage.microsoft.com) zvolte **Správa** &gt; **Správa mobilních zařízení** &gt; **Windows Phone**. Do pole **Zadejte název ověřené domény** zadejte adresu URL ověřené domény webu společnosti a zvolte **Test automatického zjištění**.

    ![Dialogové okno Instalace správy mobilního zařízení pro systém Windows](../media/windows-phone-enrollment.png)

4.  **Volitelné kroky**<br>U Windows 10 není třeba provádět krok **Přidat klíče pro zkušební načtení**. Krok **Nahrát na server certifikát pro podpis kódu** je potřeba jen tehdy, když budete distribuovat obchodní aplikace (LOB), které zařízení nemohou získat z Windows Storu. [Přečtěte si další informace](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

5.  **Informování uživatelů**<br>Uživatelé budou potřebovat vědět, jak si mají svá zařízení zaregistrovat a co mohou očekávat od zařazení do systému správy.
    - [Co říct koncovým uživatelům o používání služby Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Pokyny k zařízení s Windows pro koncové uživatele](../enduser/using-your-windows-device-with-intune.md)

Pokud jste nenasadili portál společnosti na zařízení, nejsou vyžadované žádné další kroky.  Kroky 2 a 3 v konzole správce můžete ignorovat.



<!--HONumber=Oct16_HO3-->


