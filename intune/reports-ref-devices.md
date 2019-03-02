---
title: Zařízení – Datový sklad Intune
titlesuffix: Microsoft Intune
description: Téma referenčních informací ke kategorii Zařízení pro kolekce entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: df018eb433f041da367b6196ba3797e866a2ca49
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2019
ms.locfileid: "57236581"
---
# <a name="reference-for-devices-entities"></a>Referenční informace o entitách zařízení

Kategorie **Zařízení** obsahuje entity pro mobilní zařízení, které sledují informace, například:

  -  Typ zařízení
  -  Stav zápisu a registrace zařízení
  -  Vlastnictví zařízení
  -  Stav správy zařízení
  -  Stav členství zařízení v Azure AD
  -  Stav zápisu
  -  Historické informace o zařízení
  -  Inventář aplikací na daném zařízení

## <a name="devicetypes"></a>DeviceTypes

Entita **DeviceTypes** zastupuje typ zařízení, na který odkazují jiné entity datového skladu. Typ zařízení obvykle popisuje model zařízení, výrobce nebo kombinaci obou těchto možností.

| Vlastnost  | Popis |
|---------|------------|
| DeviceTypeID |Jedinečný identifikátor typu zařízení |
| DeviceTypeKey |Jedinečný identifikátor typu zařízení v datovém skladu – náhradní klíč |
| DeviceTypeName |Typ zařízení |

### <a name="example"></a>Příklad

| deviceTypeID  | Název | Popis |
|---------|------------|--------|
| 0 |Desktop |Zařízení se systémem Windows |
| 1 |WindowsRT |Zařízení se systémem WindowsRT |
| 2 |WinMO6 |Zařízení se systémem Windows Mobile 6.0 |
| 3 |Nokia |Zařízení Nokia |
| 4 |WindowsPhone |Zařízení Windows Phone |
| 5 |Mac |Zařízení Mac |
| 6 |WinCE |Zařízení se systémem Windows CE |
| 7 |WinEmbedded |Zařízení se systémem Windows Embedded |
| 8 |IPhone |Zařízení iPhone |
| 9 |IPad |Zařízení iPad |
| 10 |IPod |Zařízení iPod |
| 11 |Android |Zařízení Android spravované pomocí Správce zařízení |
| 12 |ISocConsumer |Zařízení iSoc Consumer |
| 14 |MacMDM |Zařízení se systémem Mac OS X spravované pomocí integrovaného agenta MDM |
| 15 |HoloLens |Zařízení Holo Lens |
| 16 |SurfaceHub |Zařízení Surface Hub |
| 17 |AndroidForWork |Zařízení Android spravované pomocí vlastníka profilu Androidu |
| 100 |Blackberry |Zařízení Blackberry |
| 101 |Palm |Zařízení Palm |
| 255 |Neznámé |Neznámý typ zařízení |

## <a name="clientregistrationstatetypes"></a>ClientRegistrationStateTypes

Entita **ClientRegistrationStateTypes** zastupuje typ registrace, na který odkazují jiné tabulky datového skladu.

| Vlastnost  | Popis |
|---------|------------|
| clientRegisterationStateID |Jedinečný identifikátor stavu registrace |
| clientRegisterationStateKey |Jedinečný identifikátor stavu registrace v datovém skladu – náhradní klíč |
| clientRegisterationStateName |Stav registrace |

### <a name="example"></a>Příklad

| ClientRegisterationStateID  | Název | Popis |
|---------|------------|--------|
| 0 |NotRegistered |Nezaregistrováno |
| 1 |SMSIDConflict |Konflikt ID SMS |
| 2 |Registrované |Registrované |
| 3 |Odvoláno |Tento stav znamená, že správce IT daného klienta zablokoval a že je možné tohoto klienta odblokovat. Zařízení může mít také stav Odvoláno poté, co se vymaže nebo vyřadí z provozu. |
| 4 |KeyConflict |Konflikt klíčů |
| 5 |ApprovalPending |Čekající schválení |
| 6 |ResetCert |Resetovat certifikát |
| 7 |NotRegisteredPendingEnrollment |Nezaregistrováno, nevyřízená registrace |
| 8 |Neznámé |Neznámý stav |

## <a name="enrollmentactivities"></a>enrollmentActivities 
**EnrollmentActivity** entity indikuje aktivitu registrace zařízení.

| Vlastnost                      | Popis                                                               |
|-------------------------------|---------------------------------------------------------------------------|
| dateKey                       | Klíč data, když se tato aktivita registrace přihlášení.               |
| deviceEnrollmentTypeKey       | Klíč typu registrace.                                        |
| deviceTypeKey                 | Klíč typu zařízení.                                                |
| enrollmentEventStatusKey      | Klíč stavu indikující úspěch nebo neúspěch registrace.    |
| enrollmentFailureCategoryKey  | Klíč kategorie selhání registrace (pokud registrace nebyla úspěšná.).        |
| enrollmentFailureReasonKey    | Klíč důvod selhání registrace (pokud registrace nebyla úspěšná.).          |
| osVersion                     | Verze operačního systému zařízení.                               |
| count                         | Celkový počet zápisu aktivit odpovídající klasifikace výše.  |

## <a name="enrollmenteventstatuses"></a>enrollmentEventStatuses 
**EnrollmentEventStatus** entity označuje výsledek registrace zařízení.

| Vlastnost                   | Popis                                                                       |
|----------------------------|-----------------------------------------------------------------------------------|
| enrollmentEventStatusKey   | Jedinečný identifikátor stavu registrace v datovém skladu (náhradní klíč)  |
| enrollmentEventStatusName  | Název stavu registrace. Další příklady naleznete níže.                            |

### <a name="example"></a>Příklad

| enrollmentEventStatusName  | Popis                            |
|----------------------------|----------------------------------------|
| Úspěch                    | Registrace úspěšná zařízení         |
| Selhalo                     | Registrace zařízení se nezdařilo             |
| Není k dispozici              | Stav zápisu není k dispozici.  |

## <a name="enrollmentfailurecategories"></a>enrollmentFailureCategories 
**EnrollmentFailureCategory** entity označuje, proč registrace zařízení se nepovedla. 

| Vlastnost                       | Popis                                                                                 |
|--------------------------------|---------------------------------------------------------------------------------------------|
| enrollmentFailureCategoryKey   | Jedinečný identifikátor kategorie selhání registrace v datovém skladu (náhradní klíč)  |
| enrollmentFailureCategoryName  | Název kategorie chyby registrace. Další příklady naleznete níže.                            |

### <a name="example"></a>Příklad

| enrollmentFailureCategoryName   | Popis                                                                                                   |
|---------------------------------|---------------------------------------------------------------------------------------------------------------|
| Nelze použít                  | Kategorie chyby registrace se nedá použít.                                                            |
| Není k dispozici                   | Kategorie chyby registrace není k dispozici.                                                             |
| Neznámé                         | Neznámá chyba                                                                                                |
| Ověřování                  | Ověření se nezdařilo.                                                                                        |
| Autorizace                   | Volání byl ověřen, ale není autorizovaný k registraci.                                                         |
| AccountValidation               | Nepovedlo se ověřit účet pro zápis. (Účet zablokovaný, není povolená registrace)                      |
| UserValidation                  | Nebylo možné ověřit uživatele. (Uživatel neexistuje, chybí licence)                                           |
| DeviceNotSupported              | Zařízení není podporováno pro správu mobilních zařízení.                                                         |
| InMaintenance                   | Účet je ve stavu údržby.                                                                                    |
| Chybného požadavku                      | Klient odešle požadavek, který není srozumitelný/podporované službou.                                        |
| FeatureNotSupported             | Funkce používá tento zápis nejsou podporovány pro tento účet.                                        |
| EnrollmentRestrictionsEnforced  | Omezení registrace nakonfigurované správcem blokované tato registrace.                                          |
| ClientDisconnected              | Vypršel časový limit klienta nebo registrace bylo přerušeno roli.                                                        |
| UserAbandonment                 | Registrace byla opuštěna podle roli. (Koncový uživatel začít registrace, ale se nepodařilo dokončit včas)  |

## <a name="enrollmentfailurereasons"></a>enrollmentFailureReasons  
**EnrollmentFailureReason** entity označuje podrobnější důvod selhání registrace zařízení v kategorii daného selhání.  

| Vlastnost                     | Popis                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------|
| enrollmentFailureReasonKey   | Jedinečný identifikátor důvod selhání registrace v datovém skladu (náhradní klíč)  |
| enrollmentFailureReasonName  | Název registrace důvod selhání. Další příklady naleznete níže.                            |

### <a name="example"></a>Příklad

| enrollmentFailureReasonName      | Popis                                                                                                                                                                                            |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nelze použít                   | Důvod selhání registrace se nedá použít.                                                                                                                                                       |
| Není k dispozici                    | Důvod selhání registrace není k dispozici.                                                                                                                                                        |
| Neznámé                          | Došlo k neznámé chybě.                                                                                                                                                                                         |
| UserNotLicensed                  | Uživatel se nenašel v Intune nebo nemá platnou licenci.                                                                                                                                     |
| UserUnknown                      | Uživatel není znám do Intune.                                                                                                                                                                           |
| BulkAlreadyEnrolledDevice        | Zařízení může zaregistrovat jenom jeden uživatel. Toto zařízení už zaregistroval někdo jiný uživatel.                                                                                                                |
| EnrollmentOnboardingIssue        | Autoritu pro správu (MDM) Intune mobilního zařízení ještě není nakonfigurovaná.                                                                                                                                 |
| AppleChallengeIssue              | Instalace profilu správy iOS se zpozdila nebo nebyla úspěšná.                                                                                                                                         |
| AppleOnboardingIssue             | Certifikát Apple MDM push certificate se vyžaduje k registraci do Intune.                                                                                                                                       |
| DeviceCap                        | Uživatel se pokusil zaregistrovat víc zařízení, než maximální povolená.                                                                                                                                        |
| AuthenticationRequirementNotMet  | Registrace služby Intune se nepodařilo autorizovat tento požadavek.                                                                                                                                            |
| UnsupportedDeviceType            | Toto zařízení nesplňuje minimální požadavky pro registraci v Intune.                                                                                                                                  |
| EnrollmentCriteriaNotMet         | Toto zařízení se nepodařilo registrovat z důvodu nakonfigurované registrace omezení pravidla.                                                                                                                          |
| BulkDeviceNotPreregistered       | Nenašel se mezinárodní identifikátor mobilního zařízení (IMEI) nebo sériové číslo tohoto zařízení.  Bez tohoto identifikátoru se zařízení rozpoznávají jako zařízení v osobním vlastnictví, které jsou aktuálně zablokovány.  |
| FeatureNotSupported              | Uživatel se pokusil pro přístup k funkci, která ještě není k všem zákazníkům nebo není kompatibilní s vaší konfigurací Intune.                                                            |
| UserAbandonment                  | Registrace byla opuštěna podle roli. (Koncový uživatel začít registrace, ale se nepodařilo dokončit včas)                                                                                           |
| APNSCertificateExpired           | Zařízení Apple nelze spravovat pomocí vypršela platnost certifikátu Apple MDM push certificate.                                                                                                                            |

## <a name="enrollmenttypes"></a>EnrollmentTypes

Entita **EnrollmentTypes** určuje, jak se zařízení zaregistrovalo. Typ registrace zaznamenává metodu registrace. Příklady ukazují různé typy registrace a jejich význam.

| Vlastnost  | Popis |
|---------|------------|
| managementStateID |Jedinečný identifikátor stavu správy |
| managementStateKey |Jedinečný identifikátor stavu správy v datovém skladu – náhradní klíč |
| managementStateName |Určuje stav vzdálené akce použité pro toto zařízení. |

### <a name="example"></a>Příklad

| enrollmentTypeID  | Název | Popis |
|---------|------------|--------|
| 0 |Neznámé |Typ registrace se neshromáždil. |
| 1 |UserEnrollment |Registrace iniciovaná uživatelem |
| 2 |DeviceEnrollment |Registrace zařízení pomocí profilu bez uživatele |
| 3 |DeviceEnrollmentWithUDA |Registrace zařízení pomocí profilu UDA |
| 4 |AzureDomainJoined |Registrace zařízení iniciovaná uživatelem přes Azure Active Directory |
| 5 |UserEnrollmentWithServiceAccount |Registrace iniciovaná uživatelem přes účet služby |
| 6 |DepDeviceEnrollment |Registrace zařízení DEP pomocí profilu bez uživatele |
| 7 |DepDeviceEnrollmentWithUDA |Registrace zařízení DEP pomocí profilu UDA |
| 8 |AutoEnrollment |Kombinovaná registrace DRS a MDM pro scénář BYOD (vlastní zařízení uživatelů) |

## <a name="ownertypes"></a>OwnerTypes

Entita **EnrollmentTypes** určuje, jestli je zařízení firemní, v osobním vlastnictví nebo neznámé.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| ownerTypeID |Jedinečný identifikátor typu vlastníka. | |
| ownerTypeKey |Jedinečný identifikátor typu vlastníka v datovém skladu – náhradní klíč. | |
| ownerTypeName |Představuje typ vlastníka zařízení:  <br>Firemní – zařízení je ve vlastnictví společnosti. <br>Osobní – zařízení je v osobním vlastnictví (BYOD).  <br>Neznámé – žádné informace o tomto zařízení nejsou dostupné. |Podnikové osobní, neznámé |

> [!Note]  
> Pro `ownerTypeName` v Azure AD při vytváření dynamické skupiny zařízení, je nutné nastavit hodnotu filtru `deviceOwnership` jako `Company`. Další informace najdete v tématu [pravidla pro zařízení](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices). 

## <a name="mdmstatuses"></a>MdmStatuses

Entita **MdmStatuses** označuje stav kompatibility daného zařízení.

| Vlastnost  | Popis |
|---------|------------|
| MdmStatusID |Jedinečný identifikátor stavu dodržování předpisů |
| MdmStatusKey |Jedinečný identifikátor stavu kompatibility v datovém skladu – náhradní klíč | 
| ComplianceStatus |Stav dodržování předpisů zařízením; měl by mít jednu z hodnot z tabulky níže | 


### <a name="example"></a>Příklad

| MdmStatusID  | ComplianceStatus | Popis |
|---------|------------|--------|
| 0 |Neznámé |Stav dodržování předpisů zařízení je neznámý. |
| 1 |Odpovídající |Zařízení dodržuje předpisy. |
| 2 |a nevyhovující |Zařízení nedodržuje předpisy. |
| 3 |Konflikt |Dodržování předpisů zařízení způsobilo konflikt. |
| 4 |Chyba |Při čtení stavu dodržování předpisů zařízením došlo k chybě. |


## <a name="managementstates"></a>ManagementStates

Entita **ManagementStates** poskytuje podrobné informace o stavu daného zařízení. Podrobnosti můžou být užitečné v případech, kdy se používají vzdálené akce, nebo pokud jde o zařízení s jailbreakem nebo rootem.

| Vlastnost  | Popis |
|---------|------------|
| managementStateID | Jedinečný identifikátor stavu správy |
| managementStateKey | Jedinečný identifikátor stavu správy v datovém skladu – náhradní klíč |
| managementStateName | Určuje stav vzdálené akce použité pro toto zařízení. |

### <a name="example"></a>Příklad

| managementStateID  | Název | Popis |
|---------|------------|--------|
| 0 |Spravovaní | Spravováno bez čekajících vzdálených akcí |
| 1 |RetirePending | Pro toto zařízení existuje příkaz pro vyřazení z provozu, který čeká na vyřízení. |
| 2 |RetireFailed | Příkaz pro vyřazení z provozu u tohoto zařízení selhal. |
| 3 |WipePending | Pro toto zařízení existuje příkaz pro vymazání, který čeká na vyřízení. |
| 4 |WipeFailed | Příkaz pro vymazání u tohoto zařízení selhal. |
| 5 |Není v pořádku | Stav Není v pořádku. |
| 6 |DeletePending | Pro toto zařízení existuje příkaz pro odstranění, který čeká na vyřízení. |
| 7 |RetireIssued | Pro toto zařízení se vystavil příkaz pro vyřazení z provozu. |
| 8 |WipeIssued | Příkaz pro vymazání se vystavil. |
| 9 |WipeCanceled | Příkaz pro vymazání se zrušil. |
| 10 |RetireCanceled | Příkaz pro vyřazení z provozu se zrušil. |
| 11 |Zjištěno | Zařízení je v Intune nově zjištěno, po prvním přihlášení přejde do stavu Spravováno. |

## <a name="workplacejoinstatetypes"></a>WorkPlaceJoinStateTypes

Entita **WorkPlaceJoinStateTypes** představuje stav připojení k pracovišti Azure Active Directory pro dané zařízení.  Pracovní postup registrace může k ověřování použít jeden nebo více certifikátů. Když se pracoviště zařízení zaregistruje, použijí se tyto certifikáty k ověření zařízení a uživatele. Vystavení certifikátů se provádí prostřednictvím serveru SCEP (Simple Certificate Enrollment Point). Hodnoty v této entitě udávají různé stavy, ve kterých se toto zařízení může během tohoto procesu nacházet. Některé z těchto stavů zahrnují selhání připojení k pracovišti z důvodu neúspěšného vystavení požadovaného certifikátu (ze serveru SCEP). Pokud zařízení ještě neprošlo tímto pracovním postupem, je tato hodnota nastavená na typ Neznámý.

| Vlastnost  | Popis |
|---------|------------|
| WorkPlaceJoinStateID | Jedinečný identifikátor stavu připojení k pracovišti |
| WorkPlaceJoinStateKey | Jedinečný identifikátor stavu připojení k pracovišti v datovém skladu – náhradní klíč |
| WorkPlaceJoinStateName | Stav připojení k pracovišti |

### <a name="example"></a>Příklad

| workPlaceJoinStateID  | Název | Popis |
|---------|------------|--------|
| 0 |Neznámé |Pokud není zařízení připojené k pracovišti, je jeho stav Neznámý. |
| 1 |Úspěšné |Úspěšně připojení k pracovišti |
| 2 |FailureToGetScepMetadata |Nepodařilo se získat metadata SCEP. |
| 3 |FailureToGetScepChallenge |Nepodařilo se získat výzvu SCEP. |
| 4 |DeviceFailureToInstallScepCommand |Na zařízení se nepodařilo nainstalovat příkaz SCEP. |
| 5 |DeviceFailureToGetCertificate |Zařízení se nepodařilo získat certifikát přes SCEP. |
| 6 |DeviceScepPending |Stav čekání na vyřízení, zařízení stále provádí SCEP. |
| 7 |DeviceScepFailed |Zařízení se nepodařilo nainstalovat certifikát přes SCEP. |
| 8 |AADValidationFailed |Nepodařilo se ověřit, že zařízení existuje v AAD. |

## <a name="managementagenttypes"></a>ManagementAgentTypes

Entita **ManagementAgentTypes** představuje agenty používané ke správě zařízení.

| Vlastnost  | Popis |
|---------|------------|
| ManagementAgentTypeID | Jedinečný identifikátor typu agenta správy. |
| ManagementAgentTypeKey | Jedinečný identifikátor typu agenta správy v datovém skladu – náhradní klíč. |
| ManagementAgentTypeName |Určuje typ agenta, který se používá ke správě zařízení. |

### <a name="example"></a>Příklad

| ManagementAgentTypeID  | Název | Popis |
|---------|------------|--------|
| 1 |EAS | Zařízení se spravuje prostřednictvím protokolu Exchange Active Sync. |
| 2 |MDM | Zařízení se spravuje pomocí agenta MDM. |
| 3 |EasMdm | Zařízení se spravuje pomocí protokolu Exchange Active Sync i pomocí agenta MDM. |
| 4 |IntuneClient | Zařízení se spravuje pomocí agenta Intune pro počítače. |
| 5 |EasIntuneClient | Zařízení se spravuje pomocí protokolu Exchange Active Sync i pomocí agenta Intune pro počítače. |
| 8 |ConfigManagerClient | Zařízení se spravuje pomocí agenta produktu System Center Configuration Manager. |
| 16 |Neznámé | Neznámý typ agenta správy |

## <a name="devices"></a>Zařízení

Entita **Zařízení** obsahuje seznam všech zaregistrovaných zařízení ve správě a jejich odpovídající vlastnosti.

| Vlastnost  | Popis |
|---------|------------|
| DeviceKey | Jedinečný identifikátor zařízení v datovém skladu – náhradní klíč |
| DeviceId | Jedinečný identifikátor zařízení. |
| Název zařízení | Název zařízení na platformách, které umožňují pojmenování zařízení. Na ostatních platformách Intune vytvoří název z dalších vlastností. Tento atribut nemůže být dostupný pro všechna zařízení. |
| DeviceTypeKey | Klíč atributu typu zařízení pro toto zařízení. |
| ClientRegisterationStateKey | Klíč atributu stavu registrace klienta pro toto zařízení. |
| OwnerTypeKey | Klíč atributu typu vlastníka pro toto zařízení: podnikový, osobní nebo neznámý. |
| objectSourceKey | Ignorujte tento sloupec. |
| CreatedDate | Datum, kdy se zařízení zaregistrovalo. |
| LastContact | Poslední známé přihlášení zařízení k Intune. |
| LastContactNotification | Čas posledního upozornění Intune, aby se zařízení přihlásilo k Intune. |
| LastContactWorkplaceJoin | Časové razítko označující poslední známý stav připojení k pracovišti pro toto zařízení |
| ManagementAgentKey | Klíč agenta správy, který je přidružený k tomuto zařízení |
| ManagementStateKey | Klíč stavu správy, který je přidružený k tomuto zařízení a který udává poslední stav vzdálené akce nebo informaci, jestli jde o zařízení s jailbreakem nebo rootem |
| ReferenceId | ID zařízení v Azure Active Directory. |
| WorkPlaceJoinStateKey | Klíč stavu připojení k pracovišti, který je přidružený k tomuto zařízení |
| CategoryId | Ignorujte tento sloupec. |
| EnrollmentTypeKey | Klíč typu registrace, který je přidružený k tomuto zařízení a který udává metodu registrace |
| CertExpirationDate | Datum vypršení platnosti certifikátu pro správu MDM |
| MdmStatusKey | Klíč stavu MDM. |
| OSFamily | Řada operačního systému (Windows, iOS, Android atd.) |
| OSVersion | Verze operačního systému |
| OSMajorVersion | Řetězec hlavní verze v zápisu verze operačního systému (hlavní.podverze.sestavení.revize). |
| OSMinorVersion | Řetězec podverze v zápisu verze operačního systému (hlavní.podverze.sestavení.revize). |
| OSBuildNumber | Řetězec sestavení v zápisu verze operačního systému (hlavní.podverze.sestavení.revize). |
| OSRevisionNumber | Řetězec revize v zápisu verze operačního systému (hlavní.podverze.sestavení.revize). |
| EasID | ID EAS tohoto zařízení, pokud se zařízení spravuje pomocí protokolu Exchange Active Sync |
| GraphDeviceIsManaged | Poslední stav správy, který Intune nastavil v Azure AD. |
| GraphDeviceIsCompliant | Poslední stav kompatibility, který Intune nastavil v Azure AD. |
| sériové číslo | Sériové číslo zařízení, pokud je dostupné. |
| EnrolledByUser | ID uživatele, který toto zařízení zaregistroval, odkazující na sloupec userId v tabulce Uživatel |
| RowLastModifiedDateTimeUTC | Čas poslední změny tohoto záznamu |
| ProcessorArchitecture | Architektura procesoru. |
| DeviceAction | Poslední vystavená akce zařízení, zatím ignorujte. |
| Výrobce | Výrobce zařízení. |
| Model | Model zařízení. |
| LastPolicyUpdateUtc | Čas poslední aktualizace zásad na daném zařízení. |
| LastExchangeStatusUtc | Čas poslední synchronizace zařízení s Exchange |
| IsDeleted | Nastaví se na hodnotu True, pokud zařízení už nespravuje Intune. Uchovává poslední známý stav. |
| AndroidSecurityPatchLevel |Datum poslední opravy zabezpečení zařízení. |

## <a name="devicepropertyhistory"></a>DevicePropertyHistory

Entita **DevicePropertyHistory** obsahuje stejné vlastnosti jako tabulka zařízení a denní snímky záznamů jednotlivých zařízení za posledních 90 dnů. Sloupec DateKey označuje den pro každý řádek.

| Vlastnost  | Popis |
|---------|------------|
| DateKey |Odkaz na tabulku kalendářních dat udávající den. |
| DeviceKey |Jedinečný identifikátor zařízení v datovém skladu – náhradní klíč Jedná se o odkaz na tabulku zařízení obsahující ID zařízení v Intune. |
| Název zařízení |Název zařízení na platformách, které umožňují pojmenování zařízení. Na ostatních platformách Intune vytvoří název z dalších vlastností. Tento atribut nemůže být dostupný pro všechna zařízení. |
| DeviceTypeKey |Klíč atributu typu zařízení pro toto zařízení. |
| ClientRegisterationStateKey |Klíč atributu stavu registrace klienta pro toto zařízení. |
| OwnerTypeKey |Klíč atributu typu vlastníka pro toto zařízení: podnikový, osobní nebo neznámý. |
| objectSourceKey |Ignorujte tento sloupec. |
| CreatedDate |Datum, kdy se zařízení zaregistrovalo. |
| LastContact |Poslední známé přihlášení zařízení k Intune. |
| LastContactNotification |Čas posledního upozornění Intune, aby se zařízení přihlásilo k Intune. |
| LastContactWorkplaceJoin |Časové razítko označující poslední známý stav připojení k pracovišti pro toto zařízení |
| ManagementAgentKey |Klíč agenta správy, který je přidružený k tomuto zařízení |
| ManagementStateKey |Klíč stavu správy, který je přidružený k tomuto zařízení a který udává poslední stav vzdálené akce nebo informaci, jestli jde o zařízení s jailbreakem nebo rootem |
| ReferenceId |ID zařízení v Azure Active Directory. |
| WorkPlaceJoinStateKey |Klíč stavu připojení k pracovišti, který je přidružený k tomuto zařízení |
| CategoryId |Ignorujte tento sloupec. |
| EnrollmentTypeKey |Klíč typu registrace, který je přidružený k tomuto zařízení a který udává metodu registrace |
| CertExpirationDate |Datum vypršení platnosti certifikátu pro správu MDM |
| MdmStatusKey |Klíč stavu MDM. |
| OSFamily |Řada operačního systému (Windows, iOS, Android atd.) |
| OSVersion |Verze operačního systému. |
| OSMajorVersion |Řetězec hlavní verze v zápisu verze operačního systému (hlavní.podverze.sestavení.revize). |
| OSMinorVersion |Řetězec podverze v zápisu verze operačního systému (hlavní.podverze.sestavení.revize). |
| OSBuildNumber |Řetězec sestavení v zápisu verze operačního systému (hlavní.podverze.sestavení.revize). |
| OSRevisionNumber |Řetězec revize v zápisu verze operačního systému (hlavní.podverze.sestavení.revize). |
| EasID |ID EAS tohoto zařízení, pokud se zařízení spravuje pomocí protokolu Exchange Active Sync |
| GraphDeviceIsManaged |Poslední stav správy, který Intune nastavil v Azure AD. |
| GraphDeviceIsCompliant |Poslední stav kompatibility, který Intune nastavil v Azure AD. |
| sériové číslo |Sériové číslo zařízení, pokud je dostupné. |
| EnrolledByUser |ID uživatele, který toto zařízení zaregistroval, odkazující na sloupec userId v tabulce Uživatel |
| RowLastModifiedDateTimeUTC |Čas poslední změny tohoto záznamu |
| ProcessorArchitecture |Architektura procesoru. |
| DeviceAction |Poslední vystavená akce zařízení, zatím ignorujte. |
| Výrobce |Výrobce zařízení. |
| Model |Model zařízení. |
| LastPolicyUpdateUtc |Čas poslední aktualizace zásad na daném zařízení. |
| LastExchangeStatusUtc |Čas poslední synchronizace zařízení s Exchange |

## <a name="mdmdeviceinventoryhistories"></a>MdmDeviceInventoryHistories

Entita **MdmDeviceInventoryHistories** obsahuje denní snímky dat inventáře pro zařízení spravovaná pomocí MDM za posledních 90 dnů. Sloupec DateKey označuje den pro daný řádek. U některých zařízení se nemusí některé vlastnosti používat nebo vyplňovat. Další podrobnosti najdete na této stránce. Další informace najdete v tématu [Seznámení se zařízeními s inventářem v Microsoft Intune](device-inventory.md).

| Vlastnost  | Popis |
|---------|------------|
| DateKey | Odkaz na tabulku kalendářních dat udávající den. |
| DeviceKey |Jedinečný identifikátor zařízení v datovém skladu – náhradní klíč Jedná se o odkaz na tabulku zařízení obsahující ID zařízení v Intune. |
| DeviceModel |Model zařízení. |
| Operační systém |Operační systém zařízení. |
| Název zařízení |Název zařízení na platformách, které umožňují pojmenování zařízení. Na ostatních platformách Intune vytvoří název z dalších vlastností. Tento atribut nemůže být dostupný pro všechna zařízení. |
| SoftwareVersion |Toto je ve většině případů verze operačního systému, kromě platforem Apple, kde se tato hodnota neshoduje s verzí operačního systému |
| Imei |Číslo IMEI |
| HardwareInventoryTimeUtc |Čas prvního nahlášení inventáře pro toto zařízení |
| InventoryModifiedTimeUtc |Čas posledního uložení inventáře při pořízení tohoto snímku. |
| InventoryReportingTimeUtc |Čas posledního shromáždění inventáře pro toto zařízení |
| ExchangeActiveSyncId |ID zařízení protokolu Exchange ActiveSync. |
| ComputerSystemDescription |Popis systému. |
| ComputerSystemName |Název systému. |
| ComputerSystemManufacturer |Výrobce systému. |
| ComputerSystemModel |Model systému. |
| UserName |Uživatelské jméno. |
| OSType |Typ operačního systému. |
| OSCaption |Popisek operačního systému. |
| OSName |Název operačního systému. |
| OSManufacturer |Výrobce operačního systému. |
| OSProductSuite |Sada produktů operačního systému. |
| OSProductType |Typ produktu operačního systému. |
| Národní prostředí |Národní prostředí operačního systému. |
| PhysicalMemoryCapacity |Kapacita fyzické paměti (v bajtech). |
| PhysicalMemoryRemovable |Fyzická vyměnitelná paměť (v bajtech). |
| SystemEnclosureChassisTypesInnerText |Definuje typ skříně systému pro toto zařízení. Čísla udávají tyto hodnoty:  <br>0 nebo prázdné = Neznámý   <br>1 = Jde o stolní počítač   <br>2 = Jde o notebook  <br>3 = Jde o pracovní stanici  <br>4 = Jde o podnikový server  <br>100 = Jde o telefon  <br>101 = Jde o tablet  <br>102/103 = Jiný neznámý typ mobilního zařízení |
| SystemEnclosureModel |Model počítačové skříně. |
| SystemEnclosureSerialNumber |Sériové číslo počítačové skříně. |
| NetworkAdapterConfigurationText |Text konfigurace ze síťového adaptéru. |
| MacAddress |Adresa MAC. |
| SmsID |ID zařízení v Intune. |
| CertExpiry |Datum vypršení platnosti certifikátu pro správu MDM |
| DeviceClientAgentVersion |Verze agenta klienta. |
| DeviceClientID |ID klienta zařízení. |
| sériové číslo |Sériové číslo. |
| DeviceManufacturer |Výrobce zařízení. |
| DMVersion |Verze DM. |
| FirmwareVersion |Verze firmwaru. |
| HardwareVersion |Verze hardwaru. |
| PlatformType |Typ platformy. |
| ProcessorLevel |Úroveň procesoru. |
| ProcessorRevision |Revize procesoru. |
| Produkt |Produkt. |
| ProductVersion |Verze produktu. |
| OEM |Výrobce OEM. |
| DeviceBuildVersion |Verze sestavení zařízení. |
| Meid |Identifikátor mobilního zařízení |
| PhoneNumber |Telefonní číslo. |
| SubscriberCarrierNetwork |Název sítě telefonního operátora. |
| CellularTechnology |Typ sítě telefonního operátora (CDMA/GSM). |
| Imsi |Číslo IMSI. |
| JailBroken |Hodnota True, pokud se jedná o zařízení s jailbreakem nebo rootem |
| IsActivationLockEnabled |Hodnota True znamená, že zámek aktivace je povolený. |
| DeviceType |Typ zařízení |
| IsSupervised |Je pod dohledem. |
| DeviceDisplayNumberOfColors |Počet barev zobrazení zařízení |
| HorizontalResolution |Horizontální rozlišení obrazovky zařízení |
| VerticalResolution |Vertikální rozlišení obrazovky zařízení |
| StorageFree |Volné místo úložiště (v bajtech) |
| StorageTotal |Celková velikost úložiště (v bajtech) |
| ProgramFree |Volná paměť pro programy (v bajtech) |
| ProgramTotal |Celková velikost paměti pro programy (v bajtech) |
| RemovableStorageFree |Volné vyměnitelné úložiště (v bajtech) |
| RemovableStorageTotal |Celková velikost vyměnitelného úložiště (v bajtech) |
| DeviceMemoryDeviceCapacity |Kapacita paměti zařízení |
| DeviceMemoryAvailableDeviceCapacity |Dostupná kapacita paměti zařízení |
| DeviceOSVersion |Verze operačního systému |
| DeviceOSPlatform |Platforma operačního systému |
| DeviceOSLanguage |Jazyk operačního systému |
| PasswordMaxAttemptsBeforeWipe |Maximální povolený počet pokusů o zadání hesla před vymazáním zařízení |
| PasswordMinComplexChars |Minimální požadovaný počet složitých znaků v hesle |
| PasswordMinLength |Minimální požadovaná délka hesla |
| PasswordHistory |Heslo – minimální počet nepřijatých historických hesel |
| PasswordEnabled |Heslo – povolené? |
| PasswordExpiration |Heslo – datum vypršení platnosti. |
| AllowRecoveryPassword |Povolit obnovení hesla. |
| PasswordAutoLockTimeout |Heslo – časový limit pro automatické zamykání. |
| PasswordType |Typ hesla. |
| BacklightACTimeout |Časový limit podsvícení při připojení ke zdroji napájení. |
| BacklightBatTimeout |Časový limit podsvícení při používání baterie. |
| PowerBackupPercent |Procento zálohy napájení. |
| BatteryPercent |Zbývající procento baterie |
| PlatformID |ID platformy. |
| ExchangeDeviceID |ID výměny zařízení. |
| SmsProcessorDescription |Popis procesoru. |
| OwnerEmailAddress |E-mailová adresa vlastníka. |
| DeviceOSName |Název operačního systému. |
| WifiMac |Wi-Fi adresa MAC. |
| EthernetMac |Ethernetová adresa MAC. |
| RequireEncryption |Určuje, jestli zařízení je nebo není zašifrované. |
| ActivationLockBypassCode |Kód pro překonání zámku aktivace. |

## <a name="applicationinventory"></a>ApplicationInventory

Entita **ApplicationInventory** zobrazuje seznam aplikací, které se na zařízení nacházejí v době shromažďování inventáře.


|      Vlastnost      |                       Popis                        |
|--------------------|----------------------------------------------------------|
|     DeviceKey      |              Odkaz na tabulku zařízení.               |
|   ApplicationKey   | ? (zkopírováno z ExchangeDeviceService\DeviceApplication). |
|  ApplicationName   | ? (zkopírováno z ExchangeDeviceService\DeviceApplication). |
| ApplicationVersion | ? (zkopírováno z ExchangeDeviceService\DeviceApplication). |
|     BundleSize     | ? (zkopírováno z ExchangeDeviceService\DeviceApplication). |

