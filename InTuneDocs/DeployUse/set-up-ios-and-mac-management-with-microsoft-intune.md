---
title: "Nastavení správy pro iOS a Mac | Microsoft Intune"
description: "Povolte správu mobilních zařízení (MDM) pro zařízení s iOS včetně zařízení iPad a iPhone a zařízení s Mac OS X pomocí Microsoft Intune."
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26ac7d52c0ad3e37e517b60d448a94849c0f4b30
ms.openlocfilehash: f393f2f34658d9c4c341f1c961e9dd527fcec4b1


---

# Nastavení správy zařízení s iOS a Mac
Intune poskytuje správu mobilních zařízení pro zařízení iPad a iPhone a zařízení s Mac OS X a přístup k firemním e-mailům a aplikacím. Intune potřebuje pro správu zařízení s iOS a Mac certifikát APNs (Apple Push Notification service) od společnosti Apple. Jakmile se certifikát do služby Intune přidá, uživatelé mohou nainstalovat aplikaci Portál společnosti a registrovat svá zařízení, nebo správce může nastavit [správu zařízení s iOS vlastněných společností](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

1.  **Nastavení Intune**<br>
    Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení [nastavením autority pro správu mobilních zařízení](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) na **Microsoft Intune** a nastavením správy MDM.

2.  **Získání žádosti o podepsání certifikátu**<br>
    Jako uživatel s oprávněním správce otevřete [konzolu pro správu Microsoft Intune](http://manage.microsoft.com), přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **iOS a Mac OS X** &gt; **Nahrát na server certifikát služby APN** a klikněte na **Stáhnout žádost certifikátu služby APN**. Uložte soubor žádosti o podepsání certifikátu (.csr) místně. Soubor .csr slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Push Certificates Portal.

    ![Dialogové okno nahrání certifikátu služby APN](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Získání certifikátu služby Apple Push Notification**<br>
    Přejděte na portál [Apple Push Certificates Portal](http://go.microsoft.com/fwlink/?LinkId=269844) a přihlaste se pomocí Apple ID vaší společnosti, abyste mohli vytvořit certifikát služby APN pomocí souboru .csr. Po kliknutí na tlačítko **Nahrát** na portálu Apple Push Certificate Portal obdržíte soubor .json, který nelze použít pro služby APN. Dokončete stahování a vraťte se na portál Apple Push Certificates Portal pro **Certifikáty pro servery třetích stran** a klikněte na **Stáhnout**.

    Stáhněte certifikát APNs (.pem) a uložte soubor místně. Toto Apple ID bude v budoucnu potřeba při obnovení certifikátu APNs.

4.  **Přidání certifikátu APNs do služby Intune**<br>
    V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **iOS a Mac OS X** &gt; **Nahrát na server certifikát služby APN** a klikněte na **Nahrát certifikát služby APN**. **Vyhledejte** soubor certifikátu (.pem), klikněte na **Otevřít** a pak zadejte svoje **Apple ID**. S certifikátem APNs může Intune registrovat a spravovat zařízení se systémem iOS vynucením zásady registrace mobilních zařízení.

5.  **Informování uživatelů, jak pomocí portálu společnosti získat přístup k firemním prostředkům**<br>
    Uživatelé budou potřebovat vědět, jak mají registrovat svá zařízení a co mají očekávat po začlenění do správy. [Co říct koncovým uživatelům o používání služby Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)

Pokud vaše společnost nebo organizace zakoupí pro uživatele zařízení s iOS, mohou být zaregistrovaná ke správě jako [zařízení s iOS vlastněná společností](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### Viz také
[Příprava registrace zařízení v Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


