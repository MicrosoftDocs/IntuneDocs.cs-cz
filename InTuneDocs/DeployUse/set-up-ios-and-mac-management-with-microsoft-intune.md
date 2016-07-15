---
# required metadata

title: Nastavení správy iOS a Mac pomocí Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Nastavení správy zařízení s iOS a Mac
Pomocí Microsoft Intune můžete povolit funkci Přineste si vlastní zařízení (BYOD) pro registraci zařízení s iOS a Mac OS X a umožnit tak přístup k firemnímu e-mailu a aplikacím uživatelům používajícím iPhone, iPad a Mac. Po registraci si mohou uživatelé nainstalovat aplikaci Portál společnosti Intune a na jejich zařízení se mohou použít zásady použitím konzoly pro správu Intune.

Než budete moci v Intune spravovat zařízení s iOS, musí být zařízení schopné s Intune komunikovat. Apple vyžaduje vztah důvěryhodnosti s Intune vytvořený importováním certifikátu služby APN.

1.  **Nastavení Intune**<br>
    Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení [nastavením autority pro správu mobilních zařízení](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) na **Microsoft Intune** a nastavením správy MDM.

2.  **Získání žádosti o podepsání certifikátu**<br>
    Jako uživatel s oprávněním správce otevřete [konzolu pro správu Microsoft Intune](http://manage.microsoft.com), přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **iOS a Mac OS X** &gt; **Nahrát certifikát služby APN** a klikněte na **Stáhnout žádost certifikátu služby APN**. Uložte soubor žádosti o podepsání certifikátu (.csr) místně. Soubor .csr slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Push Certificates Portal.

    ![Dialogové okno nahrání certifikátu služby APN](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Získání certifikátu služby Apple Push Notification**<br>
    Přejděte na portál [Apple Push Certificates Portal](http://go.microsoft.com/fwlink/?LinkId=269844) a přihlaste se pomocí Apple ID vaší společnosti, abyste mohli vytvořit certifikát služby APN pomocí souboru .csr. Po kliknutí na tlačítko **Nahrát** na portálu Apple Push Certificate Portal obdržíte soubor .json, který nelze použít pro služby APN. Dokončete stahování a vraťte se na portál Apple Push Certificates Portal pro **Certifikáty pro servery třetích stran** a klikněte na **Stáhnout**..

    Stáhněte certifikát APNs (.pem) a uložte soubor místně. Toto Apple ID bude v budoucnu potřeba při obnovení certifikátu APNs.

4.  **Přidání certifikátu APNs do služby Intune**<br>
    V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **iOS a Mac OS X** &gt; **Nahrát certifikát služby APN** a klikněte na **Nahrát certifikát služby APN**. **Vyberte** soubor certifikátu (.pem), klikněte na**Otevřít** a vyplňte svoje **Apple ID**. S certifikátem APNs může Intune registrovat a spravovat zařízení se systémem iOS vynucením zásady registrace mobilních zařízení.

5.  **Informování uživatelů, jak pomocí portálu společnosti získat přístup k firemním prostředkům**<br>
    Uživatelé budou potřebovat vědět, jak mají registrovat svá zařízení a co mají očekávat po začlenění do správy. [Co říct koncovým uživatelům o používání služby Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)

Pokud vaše společnost nebo organizace zakoupí pro uživatele zařízení s iOS, mohou být zaregistrovaná ke správě jako [zařízení s iOS vlastněná společností](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)..

### Viz také
[Příprava registrace zařízení v Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


