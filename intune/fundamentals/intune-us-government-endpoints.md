---
title: Koncové body sítě pro nasazení státní správy USA – Microsoft Intune
titleSuffix: ''
description: Přečtěte si koncové body státní správy USA pro Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5f6682cb-5fcd-4018-b7f7-71768ad3152e
ms.reviewer: kerimh
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: a5e52d1967ff6f5cf97334c099bc2b5b854ae87c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502684"
---
# <a name="us-government-endpoints-for-microsoft-intune"></a>Koncové body pro státní správu USA pro Microsoft Intune

Tato stránka obsahuje seznam koncových bodů pro státní správu USA potřebných pro nastavení proxy serveru v nasazeních Intune.

Pokud chcete spravovat zařízení za branami firewall a proxy servery, musíte povolit komunikaci s Intune.

- Proxy server musí podporovat **HTTP (80)** i **HTTPS (443)** , protože klienti Intune používají oba protokoly.
- U některých úloh (například stahování aktualizací softwaru) vyžaduje Intune neověřený proxy server přístup k manage.microsoft.com.

Nastavení proxy server můžete upravit na jednotlivých klientských počítačích. Nastavení Zásady skupiny můžete použít také ke změně nastavení všech klientských počítačů umístěných za zadaným proxy server.

Spravovaná zařízení musí být nakonfigurovaná tak, aby **všichni uživatelé** měli přístup ke službám přes brány firewall.

Následující tabulky obsahují seznam portů a služeb, ke kterým přistupuje klient Intune:

|**Služba**|**IP adresa**|
|---------------------|-----------|
|*. manage.microsoft.us | 52.243.26.209 <br> 52.247.173.11 <br> 52.227.183.12 <br>52.227.180.205 <br> 52.227.178.107 <br> 13.72.185.168 <br> 52.227.173.179 <br> 52.227.175.242 <br> 13.72.39.209 <br> 52.243.26.209 <br> 52.247.173.11 |
| enterpriseregistration.microsoftonline.us | 13.72.188.239 <br> 13.72.55.179 |

## <a name="us-government-customer-designated-endpoints"></a>Zákazník pro státní správu USA určil koncové body:
- Azure Portal: https: \//Portal. Azure. us/ 
- Office 365: https: \//Portal. Office 365. us/ 
- Portál společnosti Intune: https: \//Portal. manage. Microsoft. us/ 

## <a name="partner-service-endpoints-that-intune-depends-on"></a>Koncové body partnerských služeb, na kterých závisí Intune:
- Služba AAD Sync: https: \//SyncService. gov. us. microsoftonline. com/DirectoryService. svc
- Evo STS: https: \//Login. microsoftonline. us
- Proxy adresář: https: \//directoryproxy. MicrosoftAzure. us/DirectoryProxy. svc
- Graf AAD: https: \//Directory. MicrosoftAzure. us a https: \//Graph. MicrosoftAzure. us
- MS Graph: https: \//Graph. Microsoft. us
- PRAVIDLA automatického nasazení: https: \//enterpriseregistration. microsoftonline. us
