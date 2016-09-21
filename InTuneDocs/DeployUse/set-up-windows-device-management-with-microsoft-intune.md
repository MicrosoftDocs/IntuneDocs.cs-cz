---
title: "Nastavení správy pro zařízení s Windows v Microsoft Intune | Microsoft Intune"
description: "Povolte správu mobilních zařízení (MDM) pro počítače s Windows včetně zařízení s Windows 10 pomocí služby Microsoft Intune."
keywords: 
author: NathBarn
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
ms.sourcegitcommit: ebb1648ab13d31a2ba1ab17615814be8dda8a08c
ms.openlocfilehash: 9b063c1e6b1ff5dcab16fce958ede49303284b18


---

# Nastavení správy pro zařízení Windows

Jako správce služby Intune máte dvě možnosti, jak pro počítače se systémem Windows povolit registraci a správu:

- **[Automatický zápis s Azure AD](#azure-active-directory-enrollment)** – uživatelé Windows 10 a Windows 10 Mobile zaregistrují svá zařízení tak, že do nich přidají pracovní nebo školní účet
- **[Registrace pomocí Portálu společnosti](#company-portal-app-enrollment)** – uživatelé zařízení s Windows 8.1 a novějším se registrují tak, že si stáhnou a nainstalují aplikaci Portál společnosti a následně zadají přihlašovací údaje ke svému pracovnímu nebo školnímu účtu.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Konfigurace registrace aplikace Portál společnosti
Uživatelům můžete umožnit registraci zařízení tak, že nainstalují aplikaci Portál společnosti služby Intune a registrují se jejím prostřednictvím. Vytvořením DNS CNAME uživatelům usnadníte připojení a registraci v Intune bez nutnosti zadávat název serveru.

1. **Nastavení Intune**<br>
Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení [nastavením autority pro správu mobilních zařízení](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) na **Microsoft Intune** a nastavením správy MDM.

2. **Vytváření záznamů CNAME** (volitelné)<br>Pokud vytvoříte záznamy o prostředcích DNS **CNAME** pro doménu vaší společnosti, registrace se tím zjednoduší. Přestože vytvoření položek DNS CNAME je nepovinné, vytvořením záznamů CNAME usnadníte uživatelům registraci. Pokud nebude nalezen žádný záznam CNAME pro registraci, budou uživatelé vyzváni, aby název serveru MDM zadali ručně. `https://manage.microsoft.com`.  Záznamy o prostředcích CNAME musí obsahovat tyto informace:

  |TYP|Název hostitele|Odkazuje na|Hodnota TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.doména_společnosti.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hodina|
  |CNAME|EnterpriseRegistration.doména_společnosti.com|EnterpriseRegistration.windows.net|1 hodina|

  `EnterpriseEnrollment-s.manage.microsoft.com` – Podporuje přesměrování na služby Intune s rozpoznáním domény z doménového názvu e-mailu.

  `EnterpriseRegistration.windows.net` – Podporuje zařízení s Windows 8.1 a Windows 10 Mobile, která se registrují do Azure Active Directory přes pracovní nebo školní účet

  Pokud vaše společnost používá více domén pro přihlašovací údaje uživatelů, vytvořte záznamy CNAME pro každou doménu.

  Pokud je třeba web vaší společnosti contoso.com, vytvořili byste záznam CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com. Rozšíření změn záznamu DNS můžou trvat až 72 hodin. Před rozšířením záznamu DNS nemůžete v Intune ověřit změny DNS.

3.  **Ověření CNAME**<br>V [konzole pro správu Intune](http://manage.microsoft.com) klikněte na **Správa** &gt; **Správa mobilních zařízení** &gt; **Windows**. Zadejte adresu URL ověřené domény webu společnosti do pole **Zadejte název ověřené domény** a klikněte na **Test automatického zjištění**.

  ![Dialogové okno správy zařízení s Windows](../media/enroll-intune-winenr.png)

4.  **Volitelné kroky**<br>U Windows 10 není třeba provádět krok **Přidat klíče pro zkušební načtení**. Krok **Nahrát na server certifikát pro podpis kódu** je nutný pouze v případě, že budete distribuovat obchodní aplikace (LOB) na zařízení, která nejsou k dispozici na Windows Store. [Další informace](set-up-windows-phone-8.0-management-with-microsoft-intune.md)

6.  **Informování uživatelů**<br>Bude třeba sdělit uživatelům, jak mají registrovat svá zařízení a co mají očekávat po začlenění do správy:
      - [Co říct koncovým uživatelům o používání služby Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Pokyny k zařízení s Windows pro koncové uživatele](../enduser/using-your-windows-device-with-intune.md)

### Související témata
[Příprava registrace zařízení v Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


