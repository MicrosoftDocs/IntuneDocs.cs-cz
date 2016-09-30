---
title: Konektor Exchange pro Exchange Online | Microsoft Intune
description: "Připojte Intune ke službě Office 365 Exchange, abyste podporovali správu mobilních zařízení Exchange ActiveSync (MDM)."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: a6438bb3ca21e5c46dca5ebe69266fd9bce9a4b8


---

# Konfigurace konektoru Intune Service to Service Connector pro Exchange Online

Tyto informace vám pomůžou při propojení Microsoft Intune a služby Exchange Online nebo nové služby Exchange Online Dedicated. Pokud chcete zjistit, jestli vaše prostředí Exchange Online Dedicated je **nové** nebo **starší**, kontaktujte vašeho account manažera. Intune podporuje pro každé předplatné jenom jedno připojení konektoru Exchange libovolného typu.

## Požadavky na konektor Service to Service Connector
**Konektor Service to Service Connector** podporuje jenom Exchange Online nebo novou službu Exchange Online Dedicated a nemá žádné požadavky na místní infrastrukturu.

|Požadavek|Další informace|
|---------------|--------------------|
|Nakonfigurovaná a spuštěná služba Exchange Online|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Autorita pro správu mobilních zařízení| [Nastavení autority pro správu mobilních zařízení v Microsoft Intune](prerequisites-for-enrollment.md#set-mobile-device-management-authority)|
|Verze Microsoft Exchange|Exchange Online nebo nová služba Exchange Online Dedicated|
|Synchronizace se službou Active Directory|Než použijete některý z konektorů Intune, je potřeba [nastavit synchronizaci služby Active Directory](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) tak, aby byli místní uživatelé a skupiny zabezpečení synchronizovaní s vaší instancí Azure Active Directory.|

### Požadavky rutin systému Exchange

Musíte taky vytvořit uživatelský účet Exchange Online, který bude konektor Intune Exchange Connector používat. Tento účet musí mít oprávnění k používání konzoly správce Intune a spuštění těchto požadovaných rutin prostředí Windows PowerShell Exchange:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## Nastavení konektoru Service to Service Connector

1. Otevřete [konzolu pro správu Microsoft Intune](http://manage.microsoft.com) s uživatelským účtem s právy a oprávněními správce Exchange pro [výše](#exchange-cmdlet-requirements) uvedené rutiny. Microsoft Intune používá e-mailovou adresu aktuálně přihlášeného uživatele k nastavení připojení.

2.  V podokně zástupců pracovních prostorů zvolte **SPRÁVCE** a přejděte do části **Správa mobilních zařízení** > **Microsoft Exchange** > **Nastavit připojení k systému Exchange**.
![Nastavit konektor Service to Service Connector](../media/intunesa5cservicetoserviceconnector.png)

3.  Na stránce **Nastavit připojení k systému Exchange** vyberte **Nastavit konektor Service to Service Connector**.


Konektor Service to Service Connector se automaticky nakonfiguruje a synchronizuje s Exchangem Online nebo novým prostředím Exchange Online Dedicated.

## Ověření připojení k Exchangi

Po úspěšném nakonfigurování připojení Exchange Connector v [konzole správce Microsoft Intune](http://manage.microsoft.com) zvolte **Správce**, přejděte do části **Správa mobilních zařízení** > **Microsoft Exchange** a ověřte, že se v části **Informace o připojení systému Exchange** zobrazují podrobnosti, které jste zadali.

Můžete se taky podívat na datum a čas posledního úspěšného pokusu o synchronizaci.



<!--HONumber=Sep16_HO4-->


