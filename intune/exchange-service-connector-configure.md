---
title: Intune Exchange connector pro Exchange Online | Microsoft Intune
description: Připojte Intune ke službě Office 365 Exchange, abyste podporovali správu mobilních zařízení Exchange ActiveSync (MDM).
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 828cd17c320bd13b1b7fcce6578727015be3a77b
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57460440"
---
# <a name="configure-the-exchange-service-connector-for-intune-and-exchange-online"></a>Nakonfigurujte konektor služby Exchange pro Intune a Exchange Online.
Tento článek vám ukáže, jak připojit službu Microsoft Intune k Exchangi Online nebo nové službě Exchange Online Dedicated. Pokud chcete zjistit, jestli máte prostředí Exchange Online Dedicated v **nové** nebo **starší** verzi, kontaktujte svého account manažera.

S konektorem **Service to Service Connector** můžete ke správě zařízení v Exchange ActiveSync (EAS) a zařízení v Intune použít jedinou konzolu pro správu.  K povolení podmíněného přístupu pro Exchange Online se tento konektor nevyžaduje.

Při plánování zavádění řešení podmíněného přístupu, je často potřeba vysvětlit, kteří uživatelé a počet uživatelů bude obsahovat nové prostředí. Centrum pro správu služeb Microsoft 365 poskytuje to ve formě Exchange Online sestava využití e-mailové aplikace jako součást funkce sestavy aktivit, že tento portál. Tyto sestavy lze použít k pochopení přijetí mobilní e-mailu ve vašem prostředí před a po nasazení podmíněného přístupu.

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

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com) uživatelským účtem, který má práva ke správě Exchange, oprávnění pro [výše popsané](#exchange-cmdlet-requirements) rutiny, platnou licenci pro Intune a roli Globální správce. Microsoft Intune používá e-mailovou adresu aktuálně přihlášeného uživatele k nastavení připojení.

2. V nabídce vlevo zvolte **Všechny služby** a do filtru textového pole pak zadejte **Intune**.

3. Výběrem možnosti **Intune** otevřete řídící panel Microsoft Intune. Vyberte **přístup k Exchangi**a potom v části **nastavení** vyberte **konektor systému Exchange online**.

4.  Na **Exchange přístup – Exchange online connector** zvolte **nastavit konektor Service to Service Connector**. 

Konektor Service to Service Connector se automaticky nakonfiguruje a synchronizuje s Exchangem Online nebo novým prostředím Exchange Online Dedicated.

## <a name="validate-your-exchange-connection"></a>Ověření připojení k Exchangi

Po úspěšné konfiguraci konektoru Service to Service Exchange, ověřit informace o konektoru serveru Exchange na **Exchange přístup – Exchange online connector** stránky.

Můžete se taky podívat na **Stav připojení** a datum a čas posledního úspěšného pokusu o synchronizaci.

 
