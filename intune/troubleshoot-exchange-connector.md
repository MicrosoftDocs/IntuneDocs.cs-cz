---
title: Řešení problémů s konektorem Exchange
description: Naučte se řešit potíže s místním Intune Exchange Connectorem.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 6/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a7e3c742-295b-40bb-9afa-17f243062500
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 85b4764ef5797ad592744e3c519f82f3f1cdd1bb
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52190049"
---
# <a name="troubleshoot-the-intune-on-premises-exchange-connector"></a>Řešení potíží s místním Intune Exchange Connectorem

V tomto článku se dozvíte, jak řešit problémy spojené s místním Intune Exchange Connectorem.

## <a name="steps-for-checking-the-connector-configuration"></a>Postup kontroly konfigurace konektoru 

Zkontrolujte [nastavení místního Intune Exchange Connectoru](exchange-connector-install.md), abyste ověřili jeho správnou konfiguraci. V tomto článku jsou popsané nejčastější problémy. Opravte, co je potřeba, a podívejte se, jestli se tím problém vyřešil.

 - V dialogovém okně Microsoft Intune Exchange Connectoru zkontrolujte, že jste zadali uživatelský účet s příslušným oprávněním ke spuštění [požadovaných rutin pro Windows PowerShell Exchange](exchange-connector-install.md#exchange-cmdlet-requirements).
- Povolte oznámení a zadejte účet oznámení.
 - Při konfiguraci Exchange Connectoru zadejte server pro klientský přístup (CAS), který je co nejblíže serveru hostujícímu Exchange Connector. Mezi serverem pro klientský přístup (CAS) a Exchange Connectorem dochází při komunikaci k latenci, která může zpožďovat zjišťování zařízení. Platí to zejména při použití služby Exchange Online Dedicated.
 - Uživatel s nově zaregistrovaným zařízením může mít zpomalený přístup, dokud se Exchange Connector nesynchronizuje se serverem pro klientský přístup k Exchange. Úplná synchronizace probíhá jednou denně a rozdílová (rychlá) synchronizace probíhá několikrát denně.  Pokud chcete minimalizovat zpoždění, můžete [ručně vynutit rychlou synchronizaci nebo úplnou synchronizaci](exchange-connector-install.md#manually-force-a-quick-sync-or-full-sync).
 
## <a name="exchange-activesync-device-not-discovered-from-exchange"></a>Server Exchange nezjistil zařízení s Exchange ActiveSync
[Monitorujte aktivitu Exchange Connectoru](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support), abyste zjistili, jestli se synchronizuje s Exchange serverem. Pokud od připojení zařízení proběhla úplná nebo rychlá synchronizace, podívejte se na jiné možné problémy, které jsou uvedené níže. Pokud synchronizace neproběhla, shromážděte synchronizační protokoly a připojte je k žádosti o podporu.

 - Ověřte, že uživatelé mají licenci Intune, jinak Exchange Connector jejich zařízení nezjistí.
 - Pokud se primární adresa SMTP uživatele liší od hlavního názvu uživatele (UPN) v Azure Active Directory (Azure AD), nezjistí Exchange Connector zařízení daného uživatele. Tento problém vyřešíte tím, že opravíte primární adresu SMTP.
 - Pokud máte ve svém prostředí jak poštovní server Exchange 2010, tak Exchange 2013, doporučujeme namířit Exchange Connector na server pro klientský přístup k Exchange 2013. Pokud je Exchange Connector nastaven na komunikaci se serverem pro klientský přístup k Exchange 2010, nezjistí Exchange Connector zařízení uživatelů Exchange 2013. 
- V prostředích Exchange Online Dedicated musíte při počátečním nastavení nasměrovat Exchange Connector na server pro klientský přístup (CAS) k Exchange 2013 (ne na server pro klientský přístup k Exchange 2010), protože při provádění rutin PowerShell bude Exchange Connector komunikovat jenom s tímto serverem CAS.


## <a name="using-powershell-to-get-more-data-on-exchange-connector-issues"></a>Získání dalších dat k Exchange Connectoru pomocí PowerShellu
- K získání seznamu všech mobilních zařízení k poštovní schránce, použijte rutinu Get-ActiveSyncDeviceStatistics -mailbox mbx.
- K získání seznamu adres SMTP k poštovní schránce, použijte rutinu Get-Mailbox -Identity user | select emailaddresses | fl.
- K získání podrobných informací o stavu přístupu k zařízení, použijte rutinu Get-CASMailbox <upn> | fl.

### <a name="next-steps"></a>Další postup
Pokud vám tyto informace nepomohly, můžete také [získat podporu pro Microsoft Intune](get-support.md).
