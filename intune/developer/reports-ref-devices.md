---
title: Zařízení – datový sklad Intune
titleSuffix: Microsoft Intune
description: Referenční téma pro kategorii zařízení pro kolekce entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 032b0f8dcc9d4535838b28c8b24247ff6f4a72f1
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71939993"
---
# <a name="reference-for-devices-entities"></a>Referenční informace pro entity zařízení

Kategorie **zařízení** obsahuje entity pro mobilní zařízení, které sledují informace, jako například:

- Typ zařízení
- Registrace zařízení a stav registrace
- Vlastnictví zařízení
- Stav správy zařízení
- Stav členství zařízení pro Azure AD
- Stav registrace
- Historické informace o zařízení
- Inventář aplikací v zařízení

## <a name="devicetypes"></a>DeviceTypes

Entita **deviceTypes** představuje typ zařízení, na který odkazují jiné entity datového skladu. Typ zařízení obvykle popisuje buď model zařízení, výrobce, nebo kombinaci obou.

| Vlastnost  | Popis |
|---------|------------|
| DeviceTypeID |Jedinečný identifikátor typu zařízení |
| DeviceTypeKey |Jedinečný identifikátor typu zařízení v datovém skladu – náhradní klíč |
| DeviceTypeName |Typ zařízení |

### <a name="example"></a>Příklad

| DeviceTypeID  | Name | Popis |
|---------|------------|--------|
| 0,8 |Aplikace klasické pracovní plochy |Stolní zařízení s Windows |
| první |RT |Zařízení RT |
| odst |WinMO6 |Zařízení se systémem Windows Mobile 6,0 |
| 3 |Nokia |Zařízení Nokia |
| 4 |WindowsPhone |Windows Phone zařízení |
| 5 |Mac |Zařízení Mac |
| 6 |WinCE |Systém Windows CE zařízení |
| čl |WinEmbedded |Zařízení se systémem Windows Embedded |
| 8 |IPhone |zařízení iPhone |
| 9 |IPad |zařízení iPad |
| 10pruhový |IPod |iPod zařízení |
| odst |Android |Zařízení s Androidem spravovaná pomocí Správce zařízení |
| 12,5 |ISocConsumer |zařízení příjemce iSoc |
| čtrnáct |MacMDM |Mac OS X zařízení spravované pomocí integrovaného agenta MDM |
| 15 |HoloLens |Zařízení HoloLens |
| 16bitovém |SurfaceHub |Surface Hub zařízení |
| sedmnáct |AndroidForWork |Zařízení s Androidem – spravováno pomocí vlastníka profilu Androidu |
| 100 |BlackBerry |Zařízení BlackBerry |
| 101 |Dlani |Zařízení Palm |
| 255 |Neznámé |Neznámý typ zařízení |

## <a name="enrollmentactivities"></a>enrollmentActivities 
Entita **enrollmentActivity** označuje aktivitu registrace zařízení.

| Vlastnost                      | Popis                                                               |
|-------------------------------|---------------------------------------------------------------------------|
| DateKey                       | Klíč data, kdy se tato aktivita registrace nahrála.               |
| deviceEnrollmentTypeKey       | Klíč typu registrace.                                        |
| DeviceTypeKey                 | Klíč typu zařízení                                                |
| enrollmentEventStatusKey      | Klíč stavu indikující úspěch nebo neúspěch registrace.    |
| enrollmentFailureCategoryKey  | Klíč kategorie selhání registrace (Pokud se registrace nezdařila)        |
| enrollmentFailureReasonKey    | Klíč důvodu selhání registrace (Pokud se registrace nezdařila)          |
| osVersion                     | Verze operačního systému zařízení.                               |
| count                         | Celkový počet aktivit registrace, které odpovídají klasifikacím uvedeným výše.  |

## <a name="enrollmenteventstatuses"></a>enrollmentEventStatuses 
Entita **enrollmentEventStatus** indikuje výsledek registrace zařízení.

| Vlastnost                   | Popis                                                                       |
|----------------------------|-----------------------------------------------------------------------------------|
| enrollmentEventStatusKey   | Jedinečný identifikátor stavu registrace v datovém skladu (náhradní klíč)  |
| enrollmentEventStatusName  | Název stavu registrace. Podívejte se na příklady níže.                            |

### <a name="example"></a>Příklad

| enrollmentEventStatusName  | Popis                            |
|----------------------------|----------------------------------------|
| Nástup                    | Úspěšná registrace zařízení         |
| Nepovedlo se                     | Neúspěšná registrace zařízení             |
| Není k dispozici              | Stav registrace není k dispozici.  |

## <a name="enrollmentfailurecategories"></a>enrollmentFailureCategories 
Entita **EnrollmentFailureCategory** indikuje, proč se registrace zařízení nezdařila. 

| Vlastnost                       | Popis                                                                                 |
|--------------------------------|---------------------------------------------------------------------------------------------|
| enrollmentFailureCategoryKey   | Jedinečný identifikátor kategorie selhání registrace v datovém skladu (náhradní klíč)  |
| enrollmentFailureCategoryName  | Název kategorie selhání registrace. Podívejte se na příklady níže.                            |

### <a name="example"></a>Příklad

| enrollmentFailureCategoryName   | Popis                                                                                                   |
|---------------------------------|---------------------------------------------------------------------------------------------------------------|
| Nelze použít                  | Kategorie selhání registrace se nedá použít.                                                            |
| Není k dispozici                   | Kategorie selhání registrace není k dispozici.                                                             |
| Neznámé                         | Neznámá chyba.                                                                                                |
| Ověřování                  | Ověřování se nezdařilo.                                                                                        |
| Autorizace                   | Volání bylo ověřeno, ale není autorizováno k registraci.                                                         |
| AccountValidation               | Nepovedlo se ověřit účet pro registraci. (Účet zablokován, registrace není povolená.)                      |
| UserValidation                  | Uživatele nelze ověřit. (Uživatel neexistuje, chybí licence)                                           |
| DeviceNotSupported              | Zařízení není podporováno pro správu mobilních zařízení.                                                         |
| Inúdržba                   | Účet je v údržbě.                                                                                    |
| Důvodu chybného požadavku                      | Klient odeslal požadavek, který služba nerozpoznala nebo nepodporovala.                                        |
| FeatureNotSupported             | Funkce používané tímto zápisem nejsou pro tento účet podporovány.                                        |
| EnrollmentRestrictionsEnforced  | Omezení registrace nakonfigurovaná správcem zablokovala tuto registraci.                                          |
| ClientDisconnected              | Vypršel časový limit klienta nebo byl zápis přerušen koncovým uživatelem.                                                        |
| UserAbandonment                 | Zápis byl opuštěn koncovým uživatelem. (Koncový uživatel zahájil registraci, ale nedokázal ho dokončit včas)  |

## <a name="enrollmentfailurereasons"></a>enrollmentFailureReasons  
Entita **EnrollmentFailureReason** označuje podrobnější důvod selhání registrace zařízení v dané kategorii selhání.  

| Vlastnost                     | Popis                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------|
| enrollmentFailureReasonKey   | Jedinečný identifikátor důvodu selhání registrace v datovém skladu (náhradní klíč)  |
| enrollmentFailureReasonName  | Název důvodu selhání registrace. Podívejte se na příklady níže.                            |

### <a name="example"></a>Příklad

| enrollmentFailureReasonName      | Popis                                                                                                                                                                                            |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nelze použít                   | Důvod selhání registrace se nedá použít.                                                                                                                                                       |
| Není k dispozici                    | Důvod selhání registrace není k dispozici.                                                                                                                                                        |
| Neznámé                          | Neznámá chyba.                                                                                                                                                                                         |
| UserNotLicensed                  | Uživatel se v Intune nenašel nebo nemá platnou licenci.                                                                                                                                     |
| UserUnknown                      | Intune nezná uživatele.                                                                                                                                                                           |
| BulkAlreadyEnrolledDevice        | Zařízení může zaregistrovat jenom jeden uživatel. Toto zařízení dřív zaregistroval jiný uživatel.                                                                                                                |
| EnrollmentOnboardingIssue        | Autorita správy mobilních zařízení (MDM) Intune ještě není nakonfigurovaná.                                                                                                                                 |
| AppleChallengeIssue              | Instalace profilu správy iOS byla zpožděna nebo se nezdařila.                                                                                                                                         |
| AppleOnboardingIssue             | K registraci do Intune se vyžaduje certifikát Apple MDM push Certificate.                                                                                                                                       |
| DeviceCap                        | Uživatel se pokusil zaregistrovat více zařízení, než je povolené maximum.                                                                                                                                        |
| AuthenticationRequirementNotMet  | Službě registrace v Intune se nepovedlo autorizovat tuto žádost.                                                                                                                                            |
| UnsupportedDeviceType            | Toto zařízení nesplňuje minimální požadavky na registraci v Intune.                                                                                                                                  |
| EnrollmentCriteriaNotMet         | Registrace tohoto zařízení se nepovedla kvůli nakonfigurovanému pravidlu omezení registrace.                                                                                                                          |
| BulkDeviceNotPreregistered       | Nenašlo se číslo IMEI (International Mobile Equipment Identifier) tohoto zařízení.  Bez tohoto identifikátoru se zařízení rozpoznávají jako zařízení, která jsou v tuto chvíli zablokovaná.  |
| FeatureNotSupported              | Uživatel se pokusil o přístup k funkci, která ještě není vydaná pro všechny zákazníky nebo není kompatibilní s vaší konfigurací Intune.                                                            |
| UserAbandonment                  | Zápis byl opuštěn koncovým uživatelem. (Koncový uživatel zahájil registraci, ale nedokázal ho dokončit včas)                                                                                           |
| APNSCertificateExpired           | Zařízení Apple se nedají spravovat pomocí certifikátu Apple MDM push Certificate s vypršenou platností.                                                                                                                            |
## <a name="ownertypes"></a>OwnerTypes

Entita **enrollmentType** označuje, jestli je zařízení firemní, osobně vlastněné nebo neznámé.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| ownerTypeID |Jedinečný identifikátor typu vlastníka. | |
| ownerTypeKey |Jedinečný identifikátor typu vlastníka v datovém skladu – náhradní klíč | |
| ownerTypeName |Představuje typ vlastníka zařízení:  <br>Podnik – zařízení je ve vlastnictví podniku. <br>Osobní zařízení je osobně vlastněné (BYOD).  <br>Neznámé – na tomto zařízení nejsou žádné informace. |Firemní osobní neznámý |

> [!Note]  
> Pro `ownerTypeName` v AzureAD při vytváření dynamických skupin pro zařízení musíte nastavit hodnotu filtru `deviceOwnership` jako `Company`. Další informace najdete v tématu [pravidla pro zařízení](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices). 

## <a name="managementstates"></a>ManagementStates

Entita **managementStates** poskytuje podrobné informace o stavu zařízení. Podrobnosti mohou být užitečné v případech, kdy se používají vzdálené akce, zařízení má jailbreak nebo root.

| Vlastnost  | Popis |
|---------|------------|
| managementStateID | Jedinečný identifikátor stavu správy. |
| ManagementStateKey | Jedinečný identifikátor stavu správy v datovém skladu – náhradní klíč |
| managementStateName | Určuje stav vzdálené akce použité pro toto zařízení. |

### <a name="example"></a>Příklad

| managementStateID  | Name | Popis |
|---------|------------|--------|
| 0,8 |Starosti | Spravované bez nedokončených vzdálených akcí. |
| první |RetirePending | K dispozici je příkaz k vyřazení z provozu zařízení. |
| odst |RetireFailed | Na zařízení se nepodařilo provést příkaz k vyřazení. |
| 3 |WipePending | Pro zařízení existuje příkaz k vymazání. |
| 4 |WipeFailed | V zařízení se nezdařilo příkaz vymazání. |
| 5 |Není v pořádku | Stav není v pořádku. |
| 6 |DeletePending | K dispozici je příkaz pro odstranění, který je na zařízení čeká. |
| čl |RetireIssued | K tomuto zařízení byl vydán příkaz k vyřazení. |
| 8 |WipeIssued | Byl vydán příkaz k vymazání. |
| 9 |WipeCanceled | Příkaz vymazání byl zrušen. |
| 10pruhový |RetireCanceled | Příkaz k vyřazení byl zrušen. |
| odst |Zjistil | Zařízení je nově zjištěné službou Intune a při prvním přesunu do stavu spravováno. |

## <a name="managementagenttypes"></a>ManagementAgentTypes

Entita **ManagementAgentType** představuje agenty používané ke správě zařízení.

| Vlastnost  | Popis |
|---------|------------|
| ManagementAgentTypeID | Jedinečný identifikátor typu agenta pro správu. |
| ManagementAgentTypeKey | Jedinečný identifikátor typu agenta správy v datovém skladu – náhradní klíč |
| ManagementAgentTypeName |Označuje, jaký typ agenta se používá ke správě zařízení. |

### <a name="example"></a>Příklad

| ManagementAgentTypeID  | Name | Popis |
|---------|------------|--------|
| první |EA | Zařízení se spravuje prostřednictvím Exchange Active Sync |
| odst |PRODUKTU | Zařízení se spravuje pomocí agenta MDM. |
| 3 |EasMdm | Zařízení se spravuje pomocí Exchange Active Sync i agenta MDM. |
| 4 |IntuneClient | Zařízení se spravuje pomocí agenta Intune pro počítače. |
| 5 |EasIntuneClient | Zařízení spravuje jak Exchange Active Sync, tak i agenta Intune pro počítače. |
| 8 |ConfigManagerClient | Zařízení spravuje Agent System Center Configuration Manager. |
| 16bitovém |Neznámé | Neznámý typ agenta pro správu |

## <a name="devices"></a>signalizac

Entita **zařízení** obsahuje seznam všech zaregistrovaných zařízení, která jsou pod správou, a jejich odpovídající vlastnosti.

|          Vlastnost          |                                                                                       Popis                                                                                      |
|:--------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| DeviceKey                  | Jedinečný identifikátor zařízení v datovém skladu – náhradní klíč                                                                                                               |
| DeviceId                   | Jedinečný identifikátor zařízení                                                                                                                                                     |
| DeviceName                 | Název zařízení na platformách, které umožňují pojmenování zařízení. Na jiných platformách Intune vytvoří název z dalších vlastností. Tento atribut nemůže být k dispozici pro všechna zařízení. |
| DeviceTypeKey              | Klíč atributu typu zařízení pro toto zařízení.                                                                                                                                    |
| DeviceRegistrationState    | Klíč atributu stavu registrace klienta pro toto zařízení.                                                                                                                      |
| ownerTypeKey               | Klíč atributu typu vlastníka pro toto zařízení: podniková, osobní nebo neznámá.                                                                                                    |
| EnrolledDateTime           | Datum a čas registrace tohoto zařízení.                                                                                                                                         |
| LastSyncDateTime           | Poslední známé vrácení se změnami zařízení s Intune                                                                                                                                              |
| ManagementAgentKey         | Klíč agenta pro správu přidruženého k tomuto zařízení.                                                                                                                             |
| ManagementStateKey         | Klíč stavu správy přidruženého k tomuto zařízení, který označuje poslední stav vzdálené akce nebo má jailbreak/root.                                                |
| AzureADDeviceId            | DeviceID Azure pro toto zařízení.                                                                                                                                                  |
| AzureADRegistered          | Zda je zařízení Azure Active Directory zaregistrováno.                                                                                                                             |
| DeviceCategoryKey          | Klíč kategorie přidružené k tomuto zařízení                                                                                                                                     |
| DeviceEnrollmentType       | Klíč typu registrace, který je přidružený k tomuto zařízení a který označuje způsob registrace.                                                                                             |
| ComplianceStateKey         | Klíč stavu dodržování předpisů, který je přidružený k tomuto zařízení.                                                                                                                             |
| osVersion                  | Verze operačního systému zařízení.                                                                                                                                                |
| EasDeviceId                | ID protokolu Exchange ActiveSync zařízení.                                                                                                                                                  |
| Sériové               | Sériové                                                                                                                                                                           |
| userId                     | Jedinečný identifikátor uživatele přidruženého k zařízení.                                                                                                                           |
| RowLastModifiedDateTimeUTC | Datum a čas ve standardu UTC, kdy se toto zařízení v datovém skladu naposledy změnilo                                                                                                       |
| výrobců               | Výrobce zařízení                                                                                                                                                             |
| model                      | Model zařízení                                                                                                                                                                    |
| OperatingSystem            | Operační systém zařízení. Windows, iOS atd.                                                                                                                                   |
| IsDeleted                  | Binární soubor, který ukazuje, jestli se zařízení odstranilo nebo ne.                                                                                                                                 |
| AndroidSecurityPatchLevel  | Úroveň opravy zabezpečení Androidu                                                                                                                                                           |
| MEID                       | MEID                                                                                                                                                                                   |
| Pod dohledem               | Stav zařízení pod dohledem                                                                                                                                                               |
| FreeStorageSpaceInBytes    | Volné úložiště v bajtech                                                                                                                                                                 |
| TotalStorageSpaceInBytes   | Celková velikost úložiště v bajtech                                                                                                                                                                |
| EncryptionState            | Stav šifrování na zařízení.                                                                                                                                                      |
| SubscriberCarrier          | Operátor předplatitele zařízení                                                                                                                                                       |
| PhoneNumber                | Telefonní číslo zařízení                                                                                                                                                             |
| IMEI                       | IMEI                                                                                                                                                                                   |
| CellularTechnology         | Mobilní technologie zařízení                                                                                                                                                    |
| WiFiMacAddress             | Síť MAC pro Wi-Fi                                                                                                                                                                              |
| ICCD                       | Identifikátor karty integrovaného okruhu                                                                                                                                                     |

## <a name="devicepropertyhistories"></a>devicePropertyHistories

Entita **devicePropertyHistory** má stejné vlastnosti jako tabulka zařízení a denní snímky každého záznamu zařízení za den v posledních 90 dnech. Sloupec DateKey označuje den pro každý řádek.

|          Vlastnost          |                                                                                      Popis                                                                                     |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| DateKey                    | Odkaz na tabulku kalendářních dat udávající den                                                                                                                                          |
| DeviceKey                  | Jedinečný identifikátor zařízení v datovém skladu – náhradní klíč Toto je odkaz na tabulku zařízení obsahující ID zařízení v Intune.                               |
| DeviceName                 | Název zařízení na platformách, které umožňují pojmenování zařízení. Na jiných platformách Intune vytvoří název z dalších vlastností. Tento atribut nemůže být k dispozici pro všechna zařízení. |
| DeviceRegistrationStateKey | Klíč atributu stavu registrace zařízení pro toto zařízení.                                                                                                                    |
| ownerTypeKey               | Klíč atributu typu vlastníka pro toto zařízení: podniková, osobní nebo neznámá.                                                                                                  |
| ManagementStateKey         | Klíč stavu správy přidruženého k tomuto zařízení, který označuje poslední stav vzdálené akce nebo má jailbreak/root.                                                |
| AzureADRegistered          | Zda je zařízení Azure Active Directory zaregistrováno.                                                                                                                             |
| ComplianceStateKey         | Klíč, který se má ComplianceState                                                                                                                                                            |
| OSVersion                  | Verze operačního systému                                                                                                                                                                          |
| Jailbreak                 | Zda je zařízení jailbreak nebo rootem.                                                                                                                                         |
| DeviceCategoryKey          | Klíč kategorie zařízení pro toto zařízení 

