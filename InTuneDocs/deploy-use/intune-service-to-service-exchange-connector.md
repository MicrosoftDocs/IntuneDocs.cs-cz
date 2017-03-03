---
title: Konektor Exchange pro Exchange Online | Dokumentace Microsoftu
description: "Připojte Intune ke službě Office 365 Exchange, abyste podporovali správu mobilních zařízení Exchange ActiveSync (MDM)."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: b322f368637e39da1ab10b41dd724859fb49e1f2
ms.lasthandoff: 12/10/2016


---

# <a name="configure-the-intune-service-to-service-connector-for-exchange-online"></a>Konfigurace konektoru Intune Service to Service Connector pro Exchange Online

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Tyto informace vám pomůžou při propojení služeb Microsoft Intune a Exchange Online nebo nové služby Exchange Online Dedicated. Pokud chcete zjistit, jestli máte prostředí Exchange Online Dedicated v **nové** nebo **starší** verzi, kontaktujte svého account manažera. Intune podporuje pro každé předplatné jenom jedno připojení konektoru Exchange libovolného typu.

## <a name="service-to-service-connector-requirements"></a>Požadavky na konektor Service to Service Connector
**Konektor Service to Service Connector** podporuje jenom Exchange Online nebo službu Exchange Online Dedicated a nemá žádné požadavky na místní infrastrukturu.

|Požadavek|Další informace|
|---------------|--------------------|
|Nakonfigurovaná a spuštěná služba Exchange Online|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Autorita pro správu mobilních zařízení| [Nastavení autority pro správu mobilních zařízení v Microsoft Intune](prerequisites-for-enrollment.md#step-2-set-mdm-authority)|
|Verze Microsoft Exchange|Exchange Online nebo nová služba Exchange Online Dedicated|
|Synchronizace se službou Active Directory|Než použijete některý z konektorů Intune, je potřeba [nastavit synchronizaci služby Active Directory](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) tak, aby byli místní uživatelé a skupiny zabezpečení synchronizovaní s vaší instancí Azure Active Directory.|

### <a name="exchange-cmdlet-requirements"></a>Požadavky rutin systému Exchange

Musíte taky vytvořit uživatelský účet Exchange Online, který bude konektor Intune Exchange Connector používat. Tento účet musí mít oprávnění k používání konzoly pro správu Intune a spuštění následujících požadovaných rutin prostředí Windows PowerShell Exchange:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>Nastavení konektoru Service to Service Connector

1. Otevřete [konzolu pro správu Microsoft Intune](http://manage.microsoft.com) s uživatelským účtem s právy a oprávněními správce Exchange pro [nahoře popsané](#exchange-cmdlet-requirements) rutiny. Microsoft Intune používá e-mailovou adresu aktuálně přihlášeného uživatele k nastavení připojení.

2.  V podokně zástupců pracovních prostorů zvolte **SPRÁVCE**>**Správa mobilního zařízení** > **Microsoft Exchange** > **Nastavit připojení k systému Exchange**.
![Stránka nastavení konektoru Service to Service Connector](../media/intunesa5cservicetoserviceconnector.png)

3.  Na stránce **Nastavit připojení k systému Exchange** vyberte **Nastavit konektor Service to Service Connector**.


Konektor Service to Service Connector se automaticky nakonfiguruje a synchronizuje s Exchangem Online nebo novým prostředím Exchange Online Dedicated.

## <a name="validate-your-exchange-connection"></a>Ověření připojení k Exchangi

Po úspěšném nakonfigurování Exchange Connectoru přejděte do [konzoly pro správu Microsoft Intune](http://manage.microsoft.com). Zvolte **Správce**> **Správa mobilního zařízení** > **Microsoft Exchange**. Potom ověřte, že se vámi zadané podrobnosti zobrazí v části **Informace o připojení systému Exchange**.

Můžete se taky podívat na datum a čas posledního úspěšného pokusu o synchronizaci.

