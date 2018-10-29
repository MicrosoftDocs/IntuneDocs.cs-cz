---
title: Konektor Intune Exchange pro Exchange Online
titleSuffix: ''
description: Připojte Intune ke službě Office 365 Exchange, abyste podporovali správu mobilních zařízení Exchange ActiveSync (MDM).
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 46d28ba8d9d8c6ec2adf2b41adbb9e7336676811
ms.sourcegitcommit: 24d9ae0396ca410f72cc061a3c4c402835ef32a1
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2018
ms.locfileid: "49642972"
---
# <a name="configure-the-exchange-service-connector-for-intune-and-exchange-online"></a>Nakonfigurujte konektor služby Exchange pro Intune a Exchange Online.
Tento článek vám ukáže, jak připojit službu Microsoft Intune k Exchangi Online nebo nové službě Exchange Online Dedicated. Pokud chcete zjistit, jestli máte prostředí Exchange Online Dedicated v **nové** nebo **starší** verzi, kontaktujte svého account manažera.

S konektorem **Service to Service Connector** můžete spravovat protokol Exchange ActiveSync (EAS) a zařízení spravovaná v Intune z jediné konzoly pro správu.  K povolení podmíněného přístupu pro Exchange Online se tento konektor nevyžaduje.

## <a name="service-to-service-connector-requirements"></a>Požadavky na konektor Service to Service Connector
**Konektor Service to Service Connector** podporuje jenom Exchange Online nebo Exchange Online Dedicated a nemá žádné požadavky na místní infrastrukturu. 


|              Požadavek               |                                                                                                            Další informace                                                                                                            |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nakonfigurovaná a spuštěná služba Exchange Online |                                                                                 [Exchange Online](https://technet.microsoft.com/library/jj200580.aspx)                                                                                 |
|   Autorita pro správu mobilních zařízení   |                                                       [Nastavení autority pro správu mobilních zařízení v Microsoft Intune](mdm-authority-set.md)                                                       |
|       Verze Microsoft Exchange       |                                                                                      Exchange Online nebo nová služba Exchange Online Dedicated                                                                                      |
|    Synchronizace se službou Active Directory    | Než použijete některý z konektorů Intune, je potřeba [nastavit synchronizaci služby Active Directory](/intune/users-add) tak, aby byli místní uživatelé a skupiny zabezpečení synchronizovaní s vaší instancí Azure Active Directory. |

### <a name="exchange-cmdlet-requirements"></a>Požadavky rutin systému Exchange

Musíte také vytvořit uživatelský účet Exchange Online, který bude konektor Intune Exchange používat. Tento účet musí mít oprávnění ke spouštění těchto požadovaných rutin prostředí Windows PowerShell:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>Nastavení konektoru Service to Service Connector

1. Přihlaste se k webu [Azure Portal](http://portal.azure.com) uživatelským účtem, který má práva ke správě Exchange, oprávnění pro [výše popsané](#exchange-cmdlet-requirements) rutiny, platnou licenci pro Intune a roli Globální správce. Microsoft Intune používá e-mailovou adresu aktuálně přihlášeného uživatele k nastavení připojení.

2. V nabídce vlevo zvolte **Všechny služby** a do filtru textového pole pak zadejte **Intune**.

3. Výběrem možnosti **Intune** otevřete řídící panel Microsoft Intune. Zvolte **Podmíněný přístup** a potom v části **Nastavení** vyberte **Konektor služby Exchange**.

4.  Na stránce **Podmíněný přístup – Konektor služby Exchange** vyberte **Nastavit konektor Service to Service Connector**. 
   
     ![Obrázek znázorňující výběr odkazu Nastavit konektor Service to Service Connector](media/exchange_service_connector.png)

Konektor Service to Service Connector se automaticky nakonfiguruje a synchronizuje s Exchangem Online nebo novým prostředím Exchange Online Dedicated.

## <a name="validate-your-exchange-connection"></a>Ověření připojení k Exchangi

Po úspěšné konfiguraci konektoru Service to Service Connector služby Exchange ověřte informace Exchange Connector Serveru na stránce **Podmíněný přístup – Konektor služby Exchange**.

Můžete se taky podívat na **Stav připojení** a datum a čas posledního úspěšného pokusu o synchronizaci.

 