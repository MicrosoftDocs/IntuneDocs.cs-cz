---
title: "Nastavení správy pro Windows Phone a Windows 10 Mobile | Microsoft Intune"
description: "Povolte správu mobilních zařízení (MDM) pro zařízení s Windows 10 Mobile nebo Windows Phone pomocí služby Microsoft Intune."
keywords: 
author: NathBarn
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
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: d88405e913fe61cef2c297f9d50408e10674cf3f


---


# Nastavení správy pro Windows Phone a Windows 10 Mobile v Microsoft Intune

Jako správce služby Intune máte dvě možnosti, jak pro zařízení se systémem Windows 10 Mobile a Windows Phone povolit zápis a správu:

- **[Automatický zápis s Azure AD](#azure-active-directory-enrollment)** – uživatelé Windows 10 a Windows 10 Mobile zaregistrují svá zařízení tak, že do nich přidají pracovní nebo školní účet
- **[Registrace pomocí Portálu společnosti](#company-portal-app-enrollment)** – uživatelé zařízení s Windows Phone 8.1 a novějším se registrují tak, že si stáhnou a nainstalují aplikaci Portál společnosti a následně zadají přihlašovací údaje ke svému pracovnímu nebo školnímu účtu.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Registrace aplikace Portál společnosti
Uživatelům můžete umožnit registraci zařízení tak, že nainstalují aplikaci Portál společnosti služby Intune a registrují se jejím prostřednictvím. Vytvořením DNS CNAME uživatelům usnadníte připojení a registraci v Intune bez nutnosti zadávat název serveru. Pokud spravujete zařízení s Windows Phone 8.0 nebo potřebujete nasadit portál společnosti na zařízení s Windows Phone, musíte si také stáhnout aplikaci Portál společnosti a podepsat ji. Viz [Nastavení správy pro zařízení Windows Phone 8.0](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Nastavení Intune**<br>Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení [nastavením autority pro správu mobilních zařízení](prerequisites-for-enrollment.md#set-mobile-device-management-authority) na **Microsoft Intune** a nastavením správy MDM.

2.  **Vytváření záznamů CNAME** (volitelné)<br>Vytvořte záznamy o prostředcích DNS **CNAME** pro doménu vaší společnosti. Pokud je třeba web vaší společnosti contoso.com, vytvořili byste záznam CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na manage.microsoft.com. Pokud existuje víc než jedna ověřená doména, vytvořte záznam CNAME pro každou doménu. Záznamy o prostředcích CNAME musí obsahovat tyto informace:

  |TYP|Název hostitele|Odkazuje na|Hodnota TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.doména_společnosti.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hodina|
  |CNAME|EnterpriseRegistration.doména_společnosti.com|EnterpriseRegistration.windows.net|1 hodina|
  Rozšíření změn záznamu DNS můžou trvat až 72 hodin. Před rozšířením záznamu DNS nemůžete v Intune ověřit změny DNS.

  `EnterpriseEnrollment-s.manage.microsoft.com` – Podporuje přesměrování na služby Intune s rozpoznáním domény z doménového názvu e-mailu.

  `EnterpriseRegistration.windows.net` – Podporuje zařízení s Windows 8.1 a Windows 10 Mobile, která se registrují do Azure Active Directory přes pracovní nebo školní účet

  Pokud vaše společnost používá více domén pro přihlašovací údaje uživatelů, vytvořte záznamy CNAME pro každou doménu.

  Pokud je třeba web vaší společnosti contoso.com, vytvořili byste záznam CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com. Rozšíření změn záznamu DNS můžou trvat až 72 hodin. Před rozšířením záznamu DNS nemůžete v Intune ověřit změny DNS.

3.  **Ověření CNAME**<br>V [konzole pro správu Intune](http://manage.microsoft.com) klikněte na **Správa** &gt; **Správa mobilních zařízení** &gt; **Windows Phone**. Zadejte adresu URL ověřené domény webu společnosti do pole **Zadejte název ověřené domény** a klikněte na **Test automatického zjištění**.

    ![Dialogové okno Instalace správy mobilního zařízení pro systém Windows](../media/windows-phone-enrollment.png)

4.  **Volitelné kroky**<br>U Windows 10 není třeba provádět krok **Přidat klíče pro zkušební načtení**. Krok **Nahrát na server certifikát pro podpis kódu** je nutný pouze v případě, že budete distribuovat obchodní aplikace (LOB) na zařízení, která nejsou k dispozici na Windows Store. [Další informace](set-up-windows-phone-8.0-management-with-microsoft-intune.md)

5.  **Informování uživatelů**<br>Uživatelé budou potřebovat vědět, jak mají registrovat svá zařízení a co mají očekávat po začlenění do správy.
    - [Co říct koncovým uživatelům o používání služby Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Pokyny k zařízení s Windows pro koncové uživatele](../enduser/using-your-windows-device-with-intune.md)

Pokud jste nenasadili portál společnosti na zařízení, nejsou vyžadované žádné další kroky.  Kroky 2 a 3 v konzole správce můžete ignorovat.



<!--HONumber=Sep16_HO4-->


