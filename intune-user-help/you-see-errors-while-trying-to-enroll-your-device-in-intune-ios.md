---
title: "Při pokusu o registraci zařízení s iOSem v Intune se zobrazí chybové zprávy | Dokumentace Microsoftu"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58
searchScope:
- User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: a87fe0cf9591040f1455d71b1f40cd0705ba8abf
ms.openlocfilehash: 06866b9db458851dbb23d5ccf741cad3e1d4c5d0
ms.lasthandoff: 01/24/2017


---

# <a name="you-see-errors-while-trying-to-enroll-your-ios-device-in-intune"></a>Při pokusu o registraci zařízení s iOSem v Intune se zobrazí chyby

Následující tabulka obsahuje chyby, které se můžou objevit při registraci zařízení s iOSem v Intune. Tento odkaz sdílejte se svým správcem IT. Kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).

|Chybová zpráva|Problém|Co říct správci IT|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|NoEnrollmentPolicy|Žádné zásady registrace|Zkontrolujte, že jsou nastavené všechny požadavky registrace, například certifikát služby APNs (Apple Push Notification Service), a že je povolené nastavení „iOS jako platforma“. Pokyny najdete v tématu [Nastavení správy zařízení s iOSem a MacOS](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceCapReached|Možná už máte příliš mnoho registrovaných mobilních zařízení.|Než bude moct uživatel zaregistrovat další mobilní zařízení, musí odebrat jedno ze svých aktuálně zaregistrovaných mobilní zařízení z Portálu společnosti. Přečtěte si pokyny pro typ zařízení, který používáte: [Android](unenroll-your-device-from-intune-android.md), [iOS](unenroll-your-device-from-intune-ios.md) nebo [Windows](unenroll-your-device-from-intune-windows.md).|
|APNSCertificateNotValid|Došlo k potížím s certifikátem, který umožňuje komunikaci vašeho mobilního zařízení s podnikovou sítí.<br /><br />Obraťte se na správce IT a sdělte mu, že se vám při pokusu o registraci mobilního zařízení zobrazila zpráva **APNSCertificateNotValid** a že se má podívat na řešení v této tabulce.|Služba APNs (Apple Push Notification Service) poskytuje kanál umožňující registraci zařízení s iOSem. Pokud jste neprovedli kroky k získání certifikátu APNs nebo vypršela jeho platnost, pak budou pokusy o registraci neúspěšné a zobrazí se tato zpráva.<br /><br />Přečtěte si informace o nastavení uživatelů v tématu [Synchronizace služby Active Directory a přidání uživatelů do Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) a článku o [uspořádání uživatelů a zařízení](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|AccountNotOnboarded|Došlo k potížím s certifikátem, který umožňuje komunikaci vašeho mobilního zařízení s podnikovou sítí.<br /><br />Obraťte se na správce IT a sdělte mu, že se vám při pokusu o registraci mobilního zařízení zobrazila zpráva **APNSNotOnboarded** a že se má podívat na řešení v této tabulce.|Služba APNs (Apple Push Notification Service) poskytuje kanál umožňující registraci zařízení s iOSem. Pokud jste neprovedli kroky k získání certifikátu APNs nebo vypršela jeho platnost, pak budou pokusy o registraci neúspěšné a zobrazí se tato zpráva.<br /><br />Další informace najdete v tématu [Nastavení správy iOS a Mac s Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceTypeNotSupported|Možná jste se pokusili o registraci zařízení s jiným systémem než iOS. Typ mobilního zařízení, které se pokoušíte registrovat, není podporovaný.<br /><br />Zkontrolujte, jestli na zařízení běží systém iOS verze 8.0 nebo novější.<br /><br />Obraťte se na správce IT a sdělte mu, že se vám při pokusu o registraci mobilního zařízení zobrazila zpráva **DeviceTypeNotSupported** a že se má podívat na řešení v této tabulce.|Zkontrolujte, jestli na zařízení uživatele běží systém iOS verze 8.0 nebo novější.|
|UserLicenseTypeInvalid|Nemůžete registrovat mobilní zařízení, protože váš uživatelský účet ještě není členem požadované skupiny uživatelů.<br /><br />Obraťte se na správce IT a sdělte mu, že se vám při pokusu o registraci mobilního zařízení zobrazila zpráva **UserLicenseTypeInvalid** a že se má podívat na řešení v této tabulce.|Uživatelé můžou svoje zařízení registrovat až potom, co se stanou členy správné skupiny uživatelů. Tato zpráva znamená, že má uživatel špatný typ licence pro určenou autoritu pro správu mobilních zařízení. Pokud je třeba určenou autoritou pro správu mobilních zařízení Intune a uživatel používá licenci nástroje System Center 2012 R2 Configuration Manager, zobrazí se tato chyba.<br /><br />Další informace najdete v těchto zdrojích:<br /><br />Přečtěte si článek [Nastavení správy iOS a Mac pomocí Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) a informace, jak nastavit uživatele, v článku [Synchronizace služby Active Directory a přidání uživatelů do Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) a článku o [uspořádání uživatelů a zařízení](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|MdmAuthorityNotDefined|Správce IT musí nastavit způsob, jakým se spravují mobilní zařízení ve vaší společnosti.<br /><br />Obraťte se na správce IT a sdělte mu, že se vám při pokusu o registraci mobilního zařízení zobrazila zpráva **MdmAuthorityNotDefined** a že se má podívat na řešení v této tabulce.|Autorita pro správu mobilních zařízení není určená v Intune.<br /><br />Projděte si položku č. 1 v části „Krok 6: Registrace mobilních zařízení a instalace aplikace“ v tématu [Začínáme s 30denní zkušební verzí Microsoft Intune](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune).|

