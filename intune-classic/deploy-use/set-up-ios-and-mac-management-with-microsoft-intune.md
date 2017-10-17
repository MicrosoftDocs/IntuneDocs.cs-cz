---
title: Set up iOS and Mac management
description: "Povolte správu mobilních zařízení (MDM) pro zařízení s iOSem včetně zařízení iPad a iPhone a zařízení s Mac OS X pomocí Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3dccbc4bc4e300aa5d2e804e2bf500826c0bdb8e
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2017
---
# <a name="set-up-ios-and-mac-device-management"></a>Nastavení správy zařízení s iOSem a MacOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

V Intune můžete spravovat tato mobilní zařízení: iPady, iPhony a zařízení se systémem macOS. Intune uživatelům nabízí přístup k firemnímu e-mailu a aplikacím. Intune potřebuje pro správu zařízení s iOSem a MacOS certifikát APNs (Apple Push Notification service) od společnosti Apple. Po přidání certifikátu do Intune si uživatelé mohou nainstalovat aplikaci Portál společnosti, aby mohli zaregistrovat svá zařízení. Správce také může nastavit [správu zařízení s iOSem patřících společnosti](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

1.  **Nastavení Intune**<br>
    Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení [nastavením autority pro správu mobilních zařízení](prerequisites-for-enrollment.md#step-2-set-mdm-authority) na **Microsoft Intune** a nastavením správy MDM.

2.  **Získání žádosti o podepsání certifikátu**<br>
    Přihlaste se jako uživatel s oprávněním správce a otevřete [konzolu pro správu Microsoft Intune](https://manage.microsoft.com), přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **iOS a Mac OS X** &gt; **Nahrát certifikát APNs** a zvolte **Stáhnout žádost o certifikát služby APN**. Uložte soubor žádosti o podepsání certifikátu (.csr) místně. Soubor .csr slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Push Certificates Portal.

    ![Dialogové okno nahrání certifikátu služby APN](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Získání certifikátu APNs (Apple Push Notification Service)**<br>
    Přejděte na portál [Apple Push Certificates Portal](http://go.microsoft.com/fwlink/?LinkId=269844) a přihlaste se pod Apple ID vaší společnosti, abyste mohli vytvořit certifikát APN pomocí souboru .csr. Když na portálu Apple Push Certificate Portal zvolíte **Nahrát**, získáte soubor .json, který se nedá použít pro služby APN. Dokončete stahování a vraťte se na portál Apple Push Certificates Portal do nabídky **Certifikáty pro servery třetích stran** a zvolte **Stáhnout**.

    Stáhněte si certifikát služby APN ( soubor .pem) a uložte ho místně.

    > [!NOTE]
    > Tento certifikát APNs je potřeba každý rok obnovit (ne nahradit). Přihlaste se pod stejným Apple ID na portál Apple Push Certificate a obnovte certifikát. Potom si podle stejných pokynů, které jsou uvedené v tomto tématu, stáhněte certifikát a nahrajte ho do Intune.

4.  **Přidání certifikátu APNs do služby Intune**<br>
    V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **iOS a Mac OS X** &gt; **Nahrát na server certifikát služby APN** a zvolte **Nahrát na server certifikát služby APN**. Přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a zadejte své **Apple ID**. S certifikátem APNs může Intune registrovat a spravovat zařízení se systémem iOS vynucením zásady registrace mobilních zařízení.

5.  **Informujte uživatele, jak můžou svá zařízení zaregistrovat, aby získali přístup k firemním prostředkům.**

    Pokyny k registraci koncových uživatelů najdete v tématech [Registrace zařízení se systémem iOS v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) a [Registrace zařízení se systémem macOS v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos). Proces registrace uživatele informuje, co můžou očekávat a co správci IT na jejich zařízeních uvidí a neuvidí.

    Informace o dalších úlohách koncových uživatelů najdete v článcích:
    - [Materiály o prostředí Microsoft Intune pro koncové uživatele](/intune/end-user-educate)
    - [Pokyny pro koncové uživatele zařízení s iOSem a Mac OS](https://docs.microsoft.com/intune-user-help/using-your-ios-or-macOS-device-with-intune)

Pokud společnost nebo organizace koupí uživatelům zařízení s iOS, může je také zaregistrovat pro správu jako [zařízení s iOSem patřící společnosti](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### <a name="see-also"></a>Viz také
[Předpoklady registrace zařízení do Microsoft Intune](prerequisites-for-enrollment.md)
