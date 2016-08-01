---
title: "Nastavení správy pro zařízení s Windows v Microsoft Intune | Microsoft Intune"
description: "Povolte správu mobilních zařízení (MDM) pro počítače s Windows včetně zařízení s Windows 10 pomocí služby Microsoft Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: 79377078bf5b4c6dad0a3dc4a07a2e84aa2563f8


---

# Nastavení správy pro zařízení Windows
Ve službě Intune můžete pro registraci zařízení počítače s Windows povolit funkci Přineste si vlastní zařízení (BYOD), která zajistí přístup k podnikovým e-mailům a aplikacím. Když se tato funkce použije s Azure Active Directory, poskytuje také rychlý a bezdotykový způsob správy zařízení s Windows 10 a přístup k firemním prostředkům bez nutnosti vytvořit novou image počítače. Po registraci se mohou uživatelů přihlásit a na jejich zařízení se můžou použít zásady, aplikace a nasazení s použitím konzoly pro správu Intune. Může být také vhodné [nastavit správu Windows Phone pomocí Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md) nebo [spravovat počítače s klientským softwarem Intune](manage-windows-pcs-with-microsoft-intune.md) s použitím klienta Intune.

Vytvořením DNS CNAME uživatelům usnadníte připojení a registraci v Intune bez nutnosti zadávat název serveru.

### Nastavení správy pro zařízení Windows

  1.  Vytvořte záznam o prostředcích DNS **CNAME** pro doménu společnosti. Pokud je třeba web vaší společnosti contoso.com, vytvořili byste záznam CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com. Přestože záznam CNAME DNS je pro registraci zařízení Windows volitelný, doporučujeme vytvořit jeden nebo několik záznamů, pokud je to nezbytné, aby se proces registrace zařízení s Windows zjednodušil. Pokud se nenajde žádný záznam CNAME, uživateli se zobrazí výzva k zadání názvu serveru MDM ručně.

  Pokud existuje víc než jedna ověřená doména, vytvořte záznam CNAME pro každou doménu. Záznamy o prostředcích CNAME musí obsahovat tyto informace:

  |TYP|Název hostitele|Odkazuje na|Hodnota TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.doména_společnosti.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hodina|
  |CNAME|EnterpriseRegistration.doména_společnosti.com|EnterpriseRegistration.windows.net|1 hodina|

  Rozšíření změn záznamu DNS můžou trvat až 72 hodin. Před rozšířením záznamu DNS nemůžete v Intune ověřit změny DNS.

  **EnterpriseEnrollment-s.manage.microsoft.com** – Podporuje přesměrování na služby Intune s rozpoznáním domény z doménového názvu e-mailu.

  **EnterpriseRegistration.windows.net** – Podporuje zařízení s Windows 8.1 a Windows 10 Mobile, které se registrují s Azure Active Directory s použitím pracovního nebo školního účtu.

  2.  V [konzole pro správu Intune](http://manage.microsoft.com) klikněte na **Správa** &gt; **Správa mobilních zařízení** &gt; **Windows**.
  ![Dialogové okno správy zařízení s Windows](../media/enroll-intune-winenr.png)
  3.  Zadejte adresu URL ověřené domény webu společnosti do pole **Zadejte název ověřené domény** a klikněte na **Test automatického zjištění**.

### Související témata
[Příprava registrace zařízení v Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


