---
title: "Při pokusu o registraci zařízení s iOS v Intune se zobrazí chyby | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 06/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d3a2daebdb781ce99aa103e7717ffa1b0297cb3a
ms.openlocfilehash: e8b6da8348f9c4d8ba1b85687510388cd40eac8a


---


# Při pokusu o registraci zařízení s iOS v Intune se zobrazí chyby

Následující tabulka obsahuje chyby, které se můžou objevit při registraci zařízení s iOS v Intune. Tento odkaz sdílejte se svým správcem IT. Jeho kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).

|Chybová zpráva|Problém|Co říct správci IT|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|NoEnrollmentPolicy|Žádné zásady registrace|Zkontrolujte, že byly nakonfigurovány všechny požadavky registrace, jako je například certifikát služby APN, a že je povoleno nastavení „iOS jako platforma“. Pokyny najdete v tématu [Nastavení správy zařízení s iOS a Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceCapReached|Možná už máte příliš mnoho registrovaných mobilních zařízení.|Než bude moct uživatel zaregistrovat další mobilní zařízení, musí odebrat jedno ze svých aktuálně zaregistrovaných mobilní zařízení z portálu společnosti. Přečtěte si pokyny pro typ zařízení, který používáte: [Android](unenroll-your-device-from-intune-android.md), [iOS](unenroll-your-device-from-intune-ios.md) nebo [Windows](unenroll-your-device-from-intune-windows.md).|
|APNSCertificateNotValid|Došlo k potížím s certifikátem, který umožňuje komunikaci vašeho mobilního zařízení s podnikovou sítí.<br /><br />Obraťte se na správce IT a sdělte mu, že se vám při pokusu o registraci mobilního zařízení zobrazila zpráva **APNSCertificateNotValid** a že se má podívat na řešení v této tabulce.|APNs (Apple Push Notification Service) představuje kanál umožňující registraci zařízení se systémem iOS. Pokud jste neprovedli kroky k získání certifikátu APNs nebo vypršela platnost certifikátu APNs, pak budou pokusy o registraci neúspěšné a zobrazí se tato zpráva.<br /><br />Přečtěte si informace o nastavení uživatelů v tématu [Synchronizace služby Active Directory a přidání uživatelů do Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) a [Organizace uživatelů a zařízení](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|AccountNotOnboarded|Došlo k potížím s certifikátem, který umožňuje komunikaci vašeho mobilního zařízení s podnikovou sítí.<br /><br />Obraťte se na správce IT a sdělte mu, že se vám při pokusu o registraci mobilního zařízení zobrazila zpráva **APNSNotOnboarded** a že se má podívat na řešení v této tabulce.|APNs (Apple Push Notification Service) představuje kanál umožňující registraci zařízení se systémem iOS. Pokud jste neprovedli kroky k získání certifikátu APNs nebo vypršela platnost certifikátu APNs, pak budou pokusy o registraci neúspěšné a zobrazí se tato zpráva.<br /><br />Další informace najdete v tématu [Nastavení správy iOS a Mac s Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceTypeNotSupported|Možná jste se pokusili registraci zařízení s jiným systémem než iOS. Typ mobilního zařízení, které se pokoušíte registrovat, není podporovaný.<br /><br />Zkontrolujte, jestli na zařízení běží systém iOS verze 7.1 nebo novější.<br /><br />Obraťte se na správce IT a sdělte mu, že se vám při pokusu o registraci mobilního zařízení zobrazila zpráva **DeviceTypeNotSupported** a že se má podívat na řešení v této tabulce.|Zkontrolujte, jestli na zařízení uživatele běží systém iOS verze 7.1 nebo novější.|
|UserLicenseTypeInvalid|Nemůžete registrovat mobilní zařízení, protože váš uživatelský účet ještě není členem požadované skupiny uživatelů.<br /><br />Obraťte se na správce IT a sdělte mu, že se vám při pokusu o registraci mobilního zařízení zobrazila zpráva **UserLicenseTypeInvalid** a že se má podívat na řešení v této tabulce.|Uživatelé můžou registrovat svoje zařízení až potom, co se stanou členy správné skupiny uživatelů. Tato zpráva znamená, že má uživatel špatný typ licence pro určenou autoritu pro správu mobilních zařízení. Pokud je třeba určenou autoritou pro správu mobilních zařízení Intune a uživatel používá licenci nástroje System Center 2012 R2 Configuration Manager, zobrazí se tato chyba.<br /><br />Další informace najdete v těchto zdrojích:<br /><br />Přečtěte si téma [Nastavení správy iOS a Mac pomocí Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) a informace o přidávání uživatelů v tématu [Synchronizace služby Active Directory a přidání uživatelů do Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3 a [Organizace uživatelů a zařízení](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|MdmAuthorityNotDefined|Správce IT musí nakonfigurovat způsob, jakým se spravují mobilní zařízení ve vaší společnosti.<br /><br />Obraťte se na správce IT a sdělte mu, že se vám při pokusu o registraci mobilního zařízení zobrazila zpráva **MdmAuthorityNotDefined** a že se má podívat na řešení v této tabulce.|Autorita pro správu mobilních zařízení není určená v Intune.<br /><br />Projděte si položku č. 1 v části „Krok 6: Registrace mobilních zařízení a instalace aplikace“ v tématu [Začínáme s 30denní zkušební verzí Microsoft Intune](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune).|

### Související témata
[Using your iOS or Mac OS X device with Intune](using-your-ios-or-mac-os-x-device-with-intune.md)



<!--HONumber=Aug16_HO4-->


