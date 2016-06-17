---
# required metadata

title: Nastavení správy pro zařízení s Windows v Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Nastavení správy pro zařízení Windows
Ve službě Intune můžete pro registraci zařízení počítače s Windows povolit funkci Přineste si vlastní zařízení (BYOD), která zajistí přístup k podnikovým e-mailům a aplikacím. Když se tato funkce použije s Azure Active Directory, poskytuje také rychlý a bezdotykový způsob správy zařízení s Windows 10 a přístup k firemním prostředkům bez nutnosti vytvořit novou image počítače. Po registraci se mohou uživatelů přihlásit a na jejich zařízení se můžou použít zásady, aplikace a nasazení s použitím konzoly pro správu Intune. Může být také vhodné [nastavit správu Windows Phone pomocí Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md) nebo [spravovat počítače s klientským softwarem Intune](manage-windows-pcs-with-microsoft-intune.md) s použitím klienta Intune.

Vytvořením DNS CNAME uživatelům usnadníte připojení a registraci v Intune bez nutnosti zadávat název serveru.

### Nastavení správy pro zařízení Windows

  1.  Vytvořte záznam o prostředcích DNS **CNAME** pro doménu společnosti. Pokud je třeba web vaší společnosti contoso.com, vytvořili byste záznam CNAME ve službě DNS, který přesměruje adresu EnterpriseEnrollment.contoso.com na EnterpriseEnrollment-s.manage.microsoft.com. Pokud existuje víc než jedna ověřená doména, vytvořte záznam CNAME pro každou doménu. Záznamy o prostředcích CNAME musí obsahovat tyto informace:

  |TYP|Název hostitele|Odkazuje na|Hodnota TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.doména_společnosti.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hodina|
  |CNAME|EnterpriseRegistration.doména_společnosti.com|EnterpriseRegistration.windows.net|1 hodina|

    DNS record changes might take up to 72 hours to propagate. You cannot verify the DNS change in Intune until the DNS record propagates.

    **EnterpriseEnrollment-s.manage.microsoft.com** – Supports a redirect to the Intune service with domain recognition from the email’s domain name

    **EnterpriseRegistration.windows.net** – Supports Windows 8.1 and Windows 10 Mobile devices that will register with Azure Active Directory using their work or school account

  2.  V [konzole pro správu Intune](http://manage.microsoft.com) klikněte na **Správa** &gt; **Správa mobilních zařízení** &gt; **Windows**..
  ![Dialogové okno správy zařízení s Windows](../media/enroll-intune-winenr.png)
  3.  Zadejte adresu URL ověřené domény webu společnosti do pole **Zadat název ověřené domény** a klikněte na **Test automatického zjištění**..

### Související témata
[Příprava registrace zařízení v Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


