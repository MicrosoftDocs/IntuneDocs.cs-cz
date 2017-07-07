---
title: "Řešení potíží s Exchange Connectorem"
description: "Zde najdete informace k řešení potíží s Intune Exchange Connectorem."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c5cb5465-fd8e-4524-83b9-ccdf3393b6dc
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ebcbcbc36c925b3c3d9600eb9a5039b70d7e056d
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="troubleshoot-the-exchange-connector"></a>Poradce při potížích s Exchange Connectorem

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Toto téma popisuje, jak řešit problémy, které můžou souviset s Intune Exchange Connectorem.

## <a name="steps-for-checking-the-connector-configuration"></a>Postup kontroly konfigurace konektoru 

Zkontrolujte konfiguraci Exchange Connectoru a pak ověřte, jestli je problém už vyřešený.

- V počátečním nastavení Exchange Connectoru je třeba zadat účet pro oznámení.
- Účet služby Exchange Connector musí mít příslušná oprávnění ke spouštění rutin prostředí PowerShell, které využívá Exchange Connector.
- Při konfiguraci Exchange Connectoru zadejte server pro klientský přístup (CAS), který je co nejblíže k hostitelskému serveru Exchange Connectoru. Latence při komunikaci mezi serverem pro klientský přístup a Exchange Connectorem by mohla způsobovat zpoždění při zjišťování zařízení, zejména při použití O365 Dedicated.
- Mějte na paměti, že mezi synchronizacemi Exchange Connectoru se serverem pro klientský přístup Exchange je časová prodleva. Úplná synchronizace se provádí jednou denně a rozdílová (rychlá) synchronizace delta probíhá každé dvě hodiny. Je pravděpodobné, že u uživatele s nově zaregistrovaným zařízením dojde při získávání přístupu ke zpoždění.
- 
## <a name="exchange-activesync-device-not-discovered-from-exchange"></a>Server Exchange nezjistil zařízení s Exchange ActiveSync
Zkontrolujte, jestli se Exchange Connector synchronizuje se serverem Exchange. Uděláte to tak, že vyhledáte protokoly pro úplnou nebo rozdílovou synchronizaci. Nahlédněte do protokolů Exchange Connectoru. Pokud od připojení zařízení úspěšně proběhla úplná nebo rozdílová synchronizace, pak můžete toto nastavení vyloučit jako zdroj problému. Pokud žádná synchronizace neproběhla, shromážděte synchronizační protokoly a připojte je k žádosti o podporu.

- Pokud uživatel nemá licenci pro Intune, Exchange Connector nezjistí jeho zařízení.
- Pokud se primární adresa SMTP uživatele liší od jeho hlavního názvu uživatele (UPN) v AAD, Exchange Connector nezjistí žádná zařízení tohoto uživatele Intune nebo AAD. Opravte primární adresu SMTP.
- Pokud server pro klientský přístup (CAS), s nímž Exchange Connector komunikuje během cyklu zjišťování, představuje CAS pro Exchange 2010 a pokud máte servery poštovních schránek Exchange 2010 i 2013, Exchange Connector nezjistí žádná zařízení uživatelů Exchange 2013. Pokud to chcete vyřešit, nakonfigurujte Exchange Connector tak, aby směroval na CAS pro Exchange 2013.  Ačkoli se tento problém týká především topologie s O365 Dedicated, nasměrování na CAS pro Exchange 2013 doporučujeme jako osvědčený postup i v jiných topologiích.
- V prostředích Exchange Dedicated (O365 Dedicated) je třeba při počátečním nastavení nasměrovat Exchange Connector na server pro klientský přístup (CAS) pro Exchange 2013 (ne 2010) ve vyhrazeném prostředí, protože při provádění rutin PowerShellu bude komunikovat jenom s tímto serverem CAS.


## <a name="using-powershell-to-get-more-data-on-exchange-connector-issues"></a>Získání dalších dat k Exchange Connectoru pomocí PowerShellu
- Pokud chcete získat seznam všech mobilních zařízení pro poštovní schránku, použijte Get-ActiveSyncDeviceStatistics -mailbox mbx.
- Pokud chcete získat seznam adres SMTP pro poštovní schránku, použijte Get-Mailbox -Identity user | select emailaddresses | fl.
- Pokud chcete získat podrobné informace o stavu přístupu k zařízení, použijte Get-CASMailbox <upn> | fl.

### <a name="next-steps"></a>Další kroky
Pokud vám tyto informace o řešení potíží nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
