---
title: "Nastavení správy pro Windows Phone a Windows 10 Mobile | Microsoft Intune"
description: "Povolte správu mobilních zařízení (MDM) pro zařízení s Windows 10 Mobile nebo Windows Phone pomocí služby Microsoft Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: cc928e4facf592ca0f7398b374242a7a07ae193e


---


# Nastavení správy pro Windows Phone a Windows 10 Mobile v Microsoft Intune
Před spravováním zařízení s Windows 10 Mobile nebo Windows Phone s Microsoft Intune musí být zařízení schopné komunikovat s Intune. Pro zjednodušení můžete vytvořit záznam DNS, aby uživatelé nemuseli zadávat adresu serveru. Níže uvedené kroky popisují způsoby zjednodušení registrace pro uživatele.  

Pro většinu scénářů si uživatelé mohou nainstalovat aplikaci Portál společnosti z Windows Storu. Pokud spravujete zařízení s Windows Phone 8.0 nebo potřebujete nasadit portál společnosti na zařízení s Windows Phone, musíte si také stáhnout aplikaci Portál společnosti a podepsat ji. Viz [Nastavení správy pro zařízení Windows Phone 8.0](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Nastavení Intune** Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení [nastavením autority pro správu mobilních zařízení](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) na **Microsoft Intune** a nastavením MDM.

2.  **Nastavení aliasu DNS pro adresu serveru registrace (volitelně)** (optional)

    Vytvoření aliasu DNS (typ záznamu CNAME) zjednodušuje uživatelům registraci zařízení. Přestože záznam CNAME DNS je pro registraci zařízení Windows volitelný, doporučujeme vytvořit jeden nebo několik záznamů, pokud je to nezbytné, aby se proces registrace zařízení s Windows zjednodušil. Pokud se nenajde žádný záznam CNAME, uživateli se zobrazí výzva k zadání názvu serveru MDM ručně.

  1.  Vytvořte záznamy o prostředcích DNS **CNAME** pro doménu vaší společnosti. Pokud je třeba web vaší společnosti contoso.com, vytvořili byste záznam CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na manage.microsoft.com. Pokud existuje víc než jedna ověřená doména, vytvořte záznam CNAME pro každou doménu. Záznamy o prostředcích CNAME musí obsahovat tyto informace:

      |TYP|Název hostitele|Odkazuje na|Hodnota TTL|
      |--------|-------------|-------------|-------|
      |CNAME|EnterpriseEnrollment.doména_společnosti.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hodina|
      |CNAME|EnterpriseRegistration.doména_společnosti.com|EnterpriseRegistration.windows.net|1 hodina|

      Rozšíření změn záznamu DNS můžou trvat až 72 hodin. Před rozšířením záznamu DNS nemůžete v Intune ověřit změny DNS.

      **EnterpriseEnrollment-s.manage.microsoft.com** – Podporuje přesměrování na služby Intune s rozpoznáním domény z doménového názvu e-mailu.

      **EnterpriseRegistration.windows.net** – Podporuje zařízení s Windows 8.1 a Windows 10 Mobile, které se registrují s Azure Active Directory s použitím pracovního nebo školního účtu.

    2.  V [konzole pro správu Intune](http://manage.microsoft.com) klikněte na **Správa** &gt; **Správa mobilních zařízení** &gt; **Windows Phone**.

      ![Dialogové okno Instalace správy mobilního zařízení pro systém Windows](../media/windows-device-enrollment.png)

    3.  Zadejte adresu URL ověřené domény webu společnosti do pole **Zadejte název ověřené domény** a klikněte na **Test automatického zjištění**.



Pokud jste nenasadili portál společnosti na zařízení, nejsou vyžadované žádné další kroky.  Kroky 2 a 3 v konzole správce můžete ignorovat.



<!--HONumber=Jul16_HO4-->


