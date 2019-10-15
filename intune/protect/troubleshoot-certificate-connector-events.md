---
title: Řešení potíží s Microsoft Intune Certificate Connectoru a ID událostí | Microsoft Docs
titleSuffix: Microsoft Intune
description: Poradce při potížích s Microsoft Intune Certificate Connectoru najdete v popisu událostí a popisech a v diagnostických kódech pro službu Intune Connector.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2d798f22ee4e0f11f46626eec01ad3b739d61467
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306725"
---
# <a name="intune-certificate-connector-events-and-diagnostic-codes"></a>Události a diagnostické kódy Intune Certificate Connectoru

Od verze 6.1806. x. x protokoluje služba Intune Connector události v **Prohlížeč událostí** (**protokoly aplikací a služeb** > **Microsoft Intune konektor**). Tyto události použijte k vyřešení potenciálních problémů v konfiguraci konektoru Intune. Tyto události protokolují úspěšné a neúspěšné operace a také obsahují diagnostické kódy se zprávami, které správcům IT pomůžou problém vyřešit.

> [!TIP]  
> Informace o řešení problémů a ověření nastavení konektoru Intune najdete v tématu [ukázky skriptů pro certifikační autoritu](https://aka.ms/intuneconnectorverificationscript).

## <a name="event-ids-and-descriptions"></a>ID a popisy událostí

| ID události      | Název události    | Popis události | Související diagnostické kódy |
| ------------- | ------------- | -------------     | -------------            |
| 10010 | StartedConnectorService  | Služba konektoru byla spuštěna | 0x00000000, 0x0FFFFFFF |
| 10020 | StoppedConnectorService  | Služba konektoru byla zastavena | 0x00000000, 0x0FFFFFFF |
| 10100 | CertificateRenewal_Success  | Certifikát zápisu konektoru se úspěšně obnovil. | 0x00000000, 0x0FFFFFFF |
| 10102 | CertificateRenewal_Failure  | Nepovedlo se obnovit certifikát pro zápis konektoru. Přeinstalujte konektor. | 0x00000000, 0x00000405, 0x0FFFFFFF |
| 10302 | RetrieveCertificate_Error  | Nepovedlo se načíst certifikát zápisu konektoru z registru. Zkontrolujte podrobnosti události pro kryptografický otisk certifikátu související s touto událostí. | 0x00000000, 0x00000404, 0x0FFFFFFF |
| 10301 | RetrieveCertificate_Warning  | Podívejte se na diagnostické informace v podrobnostech události. | 0x00000000, 0x00000403, 0x0FFFFFFF |
| 20100 | PkcsCertIssue_Success  | Certifikát PKCS byl úspěšně vydán. Zkontrolujte podrobnosti události pro ID zařízení, ID uživatele, název certifikační autority, název šablony certifikátu a kryptografický otisk certifikátu související s touto událostí. | 0x00000000, 0x0FFFFFFF |
| 20102 | PkcsCertIssue_Failure  | Nepovedlo se vydat certifikát PKCS. Zkontrolujte podrobnosti události pro ID zařízení, ID uživatele, název certifikační autority, název šablony certifikátu a kryptografický otisk certifikátu související s touto událostí. | 0x00000000, 0x00000400, 0x00000401, 0x0FFFFFFF |
| 20200 | RevokeCert_Success  | Certifikát byl úspěšně odvolán. Zkontrolujte podrobnosti události pro ID zařízení, ID uživatele, název certifikační autority a sériové číslo certifikátu související s touto událostí. | 0x00000000, 0x0FFFFFFF |
| 20202 | RevokeCert_Failure | Certifikát se nepovedlo odvolat. Zkontrolujte podrobnosti události pro ID zařízení, ID uživatele, název certifikační autority a sériové číslo certifikátu související s touto událostí. Další informace najdete v protokolech NDES SVC.   | 0x00000000, 0x00000402, 0x0FFFFFFF |
| 20300 | Upload_Success | Žádost o certifikát nebo data odvolání se úspěšně nahrály. Podrobnosti o nahrání najdete v podrobnostech události. | 0x00000000, 0x0FFFFFFF |
| 20302 | Upload_Failure | Nepovedlo se nahrát data žádosti nebo odvolání certifikátu. Zkontrolujte podrobnosti události > stav nahrávání a určete tak bod selhání.| 0x00000000, 0x0FFFFFFF |
| 20400 | Download_Success | Žádost o podepsání certifikátu se úspěšně stáhla, stáhne se klientský certifikát nebo odvolá certifikát. Podrobnosti o stažení najdete v podrobnostech události.  | 0x00000000, 0x0FFFFFFF |
| 20402 | Download_Failure | Nepovedlo se stáhnout žádost o podepsání certifikátu, stáhnout certifikát klienta nebo odvolat certifikát. Podrobnosti o stažení najdete v podrobnostech události. | 0x00000000, 0x0FFFFFFF |
| 20500 | CRPVerifyMetric_Success  | Bod registrace certifikátu úspěšně ověřil výzvu klienta. | 0x00000000, 0x0FFFFFFF |
| 20501 | CRPVerifyMetric_Warning  | Registrační bod certifikátu byl dokončen, ale zamítl požadavek. Další podrobnosti najdete v diagnostickém kódu a ve zprávě. | 0x00000000, 0x00000411, 0x0FFFFFFF |
| 20502 | CRPVerifyMetric_Failure  | Bod registrace certifikátu nedokázal ověřit výzvu klienta. Další podrobnosti najdete v diagnostickém kódu a ve zprávě. Podrobnosti o ID zařízení, které odpovídá výzvě, najdete v podrobnostech zprávy o událostech. | 0x00000000, 0x00000408, 0x00000409, 0x00000410, 0x0FFFFFFF |
| 20600 | CRPNotifyMetric_Success  | Bod registrace certifikátu úspěšně dokončil proces upozorňování a odeslal certifikát do klientského zařízení. | 0x00000000, 0x0FFFFFFF |
| 20602 | CRPNotifyMetric_Failure  | Bodu registrace certifikátu se nepodařilo dokončit proces upozorňování. Informace o žádosti najdete v podrobnostech zprávy o událostech. Ověřte připojení mezi serverem NDES a certifikační autoritou. | 0x00000000, 0x0FFFFFFF |

## <a name="diagnostic-codes"></a>Diagnostické kódy

| Diagnostický kód | Název diagnostiky | Diagnostická zpráva |
| -------------   | -------------   | -------------      |
| 0x00000000 | Úspěch  | Úspěch |
| 0x00000400 | PKCS_Issue_CA_Unavailable  | Certifikační autorita není platná nebo je nedosažitelná. Ověřte, že je k dispozici certifikační autorita a že server s ním může komunikovat. |
| 0x00000401 | Symantec_ClientAuthCertNotFound  | Certifikát ověřování klientů Symantec se nenašel v místním úložišti certifikátů. Další informace najdete v článku [instalace certifikátu pro autorizaci registrace Symantec](certificates-digicert-configure.md#install-the-digicert-ra-certificate) .  |
| 0x00000402 | RevokeCert_AccessDenied  | Zadaný účet nemá oprávnění k odvolání certifikátu od certifikační autority. Pokud chcete zjistit vydávající certifikační autoritu, podívejte se do pole název certifikační autority v podrobnostech zprávy události.  |
| 0x00000403 | CertThumbprint_NotFound  | Nepovedlo se najít certifikát, který by odpovídal vašemu vstupu. Zaregistrujte Certificate Connector a zkuste to znovu. |
| 0x00000404 | Certificate_NotFound  | Nepodařilo se najít certifikát odpovídající zadanému vstupu. Znovu zaregistrujte Certificate Connector a zkuste to znovu. |
| 0x00000405 | Certificate_Expired  | Platnost certifikátu vypršela. Znovu zaregistrujte Certificate Connector, aby se certifikát obnovil, a zkuste to znovu. |
| 0x00000408 | CRPSCEPCert_NotFound  | CRP šifrovací certifikát se nepovedlo najít. Ověřte, jestli je NDES a konektor Intune správně nastavený. |
| 0x00000409 | CRPSCEPSigningCert_NotFound  | Podpisový certifikát se nepovedlo načíst. Ověřte, že je služba Intune Connector nakonfigurovaná správně a že je spuštěná služba Intune Connector. Ověřte také, že události stahování certifikátu byly úspěšné. |
| 0x00000410 | CRPSCEPDeserialize_Failed  | Nepovedlo se deserializovat žádost SCEP s výzvou. Ověřte, jestli je konektor NDES a Intune správně nastavený. |
| 0x00000411 | CRPSCEPChallenge_Expired  | Požadavek byl zamítnut z důvodu výzvy k vypršení platnosti certifikátu. Po získání nové výzvy od management server může klientské zařízení opakovat akci. |
| 0x0FFFFFFFF | Unknown_Error  | Nepovedlo se nám dokončit vaši žádost, protože došlo k chybě na straně serveru. Zkuste to prosím znovu. |


## <a name="next-steps"></a>Další kroky
Pokud potřebujete další pomoc, použijte [Poradce při potížích s nasazením profilu certifikátu SCEP v Microsoft Intune](https://support.microsoft.com/help/4457481/troubleshooting-scep-certificate-profile-deployment-in-intune) příručce.
