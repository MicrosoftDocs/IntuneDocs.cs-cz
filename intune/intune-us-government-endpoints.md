---
title: Koncové body sítě pro US government nasazení – Microsoft Intune
titleSuffix: ''
description: Projděte si koncové body státní správy USA pro Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7a86069b7f4093fb437171d5699df2302fc6fd2a
ms.sourcegitcommit: df413d1786c9aa0f409424c1e9e102bf230bbe39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2019
ms.locfileid: "66721695"
---
# <a name="us-government-endpoints-for-microsoft-intune"></a>Koncové body státní správy USA pro Microsoft Intune

Tato stránka obsahuje seznam koncových bodů státní správy USA, třeba nastavení proxy serveru v nasazení Intune.

Ke správě zařízení za bránami firewall nebo proxy servery, je nutné povolit komunikaci pro Intune.

- Proxy server musí podporovat **HTTP (80)** i **HTTPS (443)** , protože klienti Intune používají oba protokoly.
- Pro některé úlohy (jako je stahování aktualizace softwaru), vyžaduje Intune přístup k neověřenému proxy serveru na adresu manage.microsoft.com

Můžete upravit nastavení proxy serveru na jednotlivých klientských počítačích. Nastavení zásad skupiny můžete také změnit nastavení pro všechny klientské počítače umístěné za zadaným proxy serverem.

Spravovaná zařízení musí být nakonfigurovaná tak, aby **všichni uživatelé** měli přístup ke službám přes brány firewall.

Následující tabulky obsahují seznam portů a služeb, ke kterým přistupuje klient Intune:

|**Koncový bod**|**IP adresa**|
|---------------------|-----------|
|*.manage.microsoft.us | 52.243.26.209 <br> 52.247.173.11 <br> 52.227.183.12 <br>52.227.180.205 <br> 52.227.178.107 <br> 13.72.185.168 <br> 52.227.173.179 <br> 52.227.175.242 <br> 13.72.39.209 <br> 52.243.26.209 <br> 52.247.173.11 |
| enterpriseregistration.microsoftonline.us | 13.72.188.239 <br> 13.72.55.179 |

## <a name="us-government-customer-designated-endpoints"></a>Koncové body určené zákazníka státní správy USA:
- Azure portal: https://portal.azure.us/ 
- Office 365: https://portal.office365.us/ 
- Portál společnosti Intune: https://portal.manage.microsoft.us/ 

## <a name="partner-service-endpoints-that-intune-depends-on"></a>Partner koncové body služby Intune, na kterých závisí:
- Služba AAD Sync: https://syncservice.gov.us.microsoftonline.com/DirectoryService.svc
- Evo STS: https://login.microsoftonline.us
- Adresář serveru Proxy: https://directoryproxy.microsoftazure.us/DirectoryProxy.svc
- AAD Graph: https://directory.microsoftazure.us a https://graph.microsoftazure.us
- MS Graphu: https://graph.microsoft.us
- ADRS: https://enterpriseregistration.microsoftonline.us
