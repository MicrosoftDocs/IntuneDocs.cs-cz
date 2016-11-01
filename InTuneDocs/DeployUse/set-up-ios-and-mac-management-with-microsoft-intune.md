---
title: "Nastavení správy pro iOS a Mac | Microsoft Intune"
description: "Povolte správu mobilních zařízení (MDM) pro zařízení s iOS včetně zařízení iPad a iPhone a zařízení s Mac OS X pomocí Microsoft Intune."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b3f6323912707d56d23380217a07e6474593d83f
ms.openlocfilehash: f93f7bfe99e878691dccd24c124a781c8607e7c6


---

# Nastavení správy zařízení s iOS a Mac
Nápovědu k nastavení zařízení s iOS nebo zařízení Mac najdete v tématu [Použití zařízení s iOS nebo Mac OS X s Intune](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md).

V Intune můžete spravovat tato mobilní zařízení: iPady, iPhony a zařízení s Mac OS X. Intune uživatelům nabízí přístup k firemnímu e-mailu a aplikacím. Intune potřebuje pro správu zařízení s iOS a Mac certifikát APNs (Apple Push Notification service) od společnosti Apple. Po přidání certifikátu do Intune si uživatelé mohou nainstalovat aplikaci Portál společnosti, aby mohli zaregistrovat svá zařízení. Správce také může nastavit [správu zařízení s iOS patřících společnosti](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

1.  **Nastavení Intune**<br>
    Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení [nastavením autority pro správu mobilních zařízení](prerequisites-for-enrollment.md#set-mobile-device-management-authority) na **Microsoft Intune** a nastavením správy MDM.

2.  **Získání žádosti o podepsání certifikátu**<br>
    Přihlaste se jako uživatel s oprávněním správce a otevřete [konzolu pro správu Microsoft Intune](http://manage.microsoft.com), přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **iOS a Mac OS X** &gt; **Nahrát certifikát APNs** a zvolte **Stáhnout žádost o certifikát služby APN**. Uložte soubor žádosti o podepsání certifikátu (.csr) místně. Soubor .csr slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Push Certificates Portal.

    ![Dialogové okno nahrání certifikátu služby APN](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Získání certifikátu služby Apple Push Notification**<br>
    Přejděte na portál [Apple Push Certificates Portal](http://go.microsoft.com/fwlink/?LinkId=269844) a přihlaste se pod Apple ID vaší společnosti, abyste mohli vytvořit certifikát APN pomocí souboru .csr. Když na portálu Apple Push Certificate Portal zvolíte **Nahrát**, získáte soubor .json, který se nedá použít pro služby APN. Dokončete stahování a vraťte se na portál Apple Push Certificates Portal do nabídky **Certifikáty pro servery třetích stran** a zvolte **Stáhnout**.

    Stáhněte si certifikát služby APN ( soubor .pem) a uložte ho místně. Toto Apple ID musíte později použít k obnovení certifikátu služby APN.

4.  **Přidání certifikátu APNs do služby Intune**<br>
    V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **iOS a Mac OS X** &gt; **Nahrát na server certifikát služby APN** a zvolte **Nahrát na server certifikát služby APN**. Přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a zadejte své **Apple ID**. S certifikátem APNs může Intune registrovat a spravovat zařízení se systémem iOS vynucením zásady registrace mobilních zařízení.

5.  **Informování uživatelů, jak pomocí portálu společnosti získat přístup k firemním prostředkům**<br>
    Uživatelé budou potřebovat vědět, jak si mají svá zařízení zaregistrovat a co mohou očekávat od zařazení do systému správy.
    - [Co říct koncovým uživatelům o používání služby Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Pokyny k zařízení s iOS a Mac pro koncové uživatele](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md)

Pokud společnost nebo organizace koupí uživatelům zařízení s iOS, může je také zaregistrovat pro správu jako [zařízení s iOS patřící společnosti](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### Viz také
[Předpoklady pro registraci do Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Oct16_HO3-->


