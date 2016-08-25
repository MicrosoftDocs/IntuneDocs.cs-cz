---
title: "Konfigurace konektoru Microsoft Intune Exchange Connector pro hostovaný Exchange | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6951ccdb0e37489217ef939f0cbf6fc1133a6d3c
ms.openlocfilehash: 6cfc532cba2f53034c4c3ef0c2df3d6c1e6e7841


---

# Konfigurace konektoru Intune Service to Service Connector pro Exchange Online

Tyto informace vám pomůžou při propojení Microsoft Intune a služby Exchange Online hostované Office 365.

## Požadavky na konektor Service to Service Connector
**Konektor Service to Service Connector** podporuje jenom hostovaný Exchange a nemá žádné požadavky na místní infrastrukturu.

|Požadavek|Další informace|
|---------------|--------------------|
|Nakonfigurovaný a spuštěný hostovaný Exchange|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Autorita pro správu mobilních zařízení| [Nastavení autority pro správu mobilních zařízení v Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority)|
|Verze Microsoft Exchange|Musíte mít předplatné Office 365 obsahující tenanta Exchange Serveru 2013 nebo novějšího. Pokud je tenant Exchange Server 2013 nebo novější, konektor podporuje Exchange Server 2010 ve stejném prostředí.|
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


Konektor Service to Service Connector se automaticky nakonfiguruje a synchronizuje s prostředím hostovaného Exchange.

## Ověření připojení k Exchangi

Po úspěšném nakonfigurování připojení Exchange Connector v konzole správce Intune zvolte pracovní prostor **SPRÁVCE**, přejděte do části **Správa mobilních zařízení** > **Microsoft Exchange** a ověřte, že se v části **Informace o připojení systému Exchange** zobrazují podrobnosti, které jste zadali.

Můžete se taky podívat na datum a čas posledního úspěšného pokusu o synchronizaci.



<!--HONumber=Jun16_HO4-->


