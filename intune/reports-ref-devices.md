---
title: Zařízení – Datový sklad Intune
titlesuffix: Microsoft Intune
description: Téma referenčních informací ke kategorii Zařízení pro kolekce entit v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/20/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 29213400b5baf9705c188bb45b3666b65262d577
ms.sourcegitcommit: 93286c22426dcb59191a99e3cf2af4ff6ff16522
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2019
ms.locfileid: "58358229"
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
| 15 |HoloLens |Zařízení HoloLens |
| 16 |SurfaceHub |Zařízení Surface Hub |
| 17 |AndroidForWork |Zařízení Android spravované pomocí vlastníka profilu Androidu |
| 100 |Blackberry |Zařízení Blackberry |
| 101 |Palm |Zařízení Palm |
| 255 |Neznámé |Neznámý typ zařízení |

## <a name="enrollmentactivities"></a>enrollmentActivities 
**EnrollmentActivity** entity indikuje aktivitu registrace zařízení.

| Vlastnost                      | Popis                                                               |
|-------------------------------|---------------------------------------------------------------------------|
| dateKey                       | Klíč data, když se tato aktivita registrace přihlášení.               |
| deviceEnrollmentTypeKey       | Klíč typu registrace.                                        |
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
| ClientDisconnected              | Vypršel časový limit klienta nebo registrace byla přerušena koncovým uživatelem.                                                        |
| UserAbandonment                 | Registrace byla opuštěna koncovým uživatelem. (Koncový uživatel začít registrace, ale se nepodařilo dokončit včas)  |

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
| UserAbandonment                  | Registrace byla opuštěna koncovým uživatelem. (Koncový uživatel začít registrace, ale se nepodařilo dokončit včas)                                                                                           |
| APNSCertificateExpired           | Zařízení Apple nelze spravovat pomocí vypršela platnost certifikátu Apple MDM push certificate.                                                                                                                            |
## <a name="ownertypes"></a>OwnerTypes

Entita **EnrollmentTypes** určuje, jestli je zařízení firemní, v osobním vlastnictví nebo neznámé.

| Vlastnost  | Popis | Příklad |
|---------|------------|--------|
| ownerTypeID |Jedinečný identifikátor typu vlastníka. | |
| ownerTypeKey |Jedinečný identifikátor typu vlastníka v datovém skladu – náhradní klíč. | |
| ownerTypeName |Představuje typ vlastníka zařízení:  <br>Firemní – zařízení je ve vlastnictví společnosti. <br>Osobní – zařízení je v osobním vlastnictví (BYOD).  <br>Neznámé – žádné informace o tomto zařízení nejsou dostupné. |Podnikové osobní, neznámé |

> [!Note]  
> Pro `ownerTypeName` v Azure AD při vytváření dynamické skupiny zařízení, je nutné nastavit hodnotu filtru `deviceOwnership` jako `Company`. Další informace najdete v tématu [pravidla pro zařízení](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices). 

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
| OwnerTypeKey | Klíč atributu typu vlastníka pro toto zařízení: podnikový, osobní nebo neznámý. |
| objectSourceKey | Ignorujte tento sloupec. |
| ManagementAgentKey | Klíč agenta správy, který je přidružený k tomuto zařízení |
| ManagementStateKey | Klíč stavu správy, který je přidružený k tomuto zařízení a který udává poslední stav vzdálené akce nebo informaci, jestli jde o zařízení s jailbreakem nebo rootem |
| OSVersion | Verze operačního systému |
| OSMajorVersion | Řetězec hlavní verze v zápisu verze operačního systému (hlavní.podverze.sestavení.revize). |
| OSMinorVersion | Řetězec podverze v zápisu verze operačního systému (hlavní.podverze.sestavení.revize). |
| OSBuildNumber | Řetězec sestavení v zápisu verze operačního systému (hlavní.podverze.sestavení.revize). |
| OSRevisionNumber | Řetězec revize v zápisu verze operačního systému (hlavní.podverze.sestavení.revize). |
| sériové číslo | Sériové číslo zařízení, pokud je dostupné. |
| RowLastModifiedDateTimeUTC | Čas poslední změny tohoto záznamu |
| DeviceAction | Poslední vystavená akce zařízení, zatím ignorujte. |
| Výrobce | Výrobce zařízení. |
| Model | Model zařízení. |
| IsDeleted | Nastaví se na hodnotu True, pokud zařízení už nespravuje Intune. Uchovává poslední známý stav. |
| AndroidSecurityPatchLevel |Datum poslední opravy zabezpečení zařízení. |

## <a name="devicepropertyhistory"></a>DevicePropertyHistory

Entita **DevicePropertyHistory** obsahuje stejné vlastnosti jako tabulka zařízení a denní snímky záznamů jednotlivých zařízení za posledních 90 dnů. Sloupec DateKey označuje den pro každý řádek.

| Vlastnost  | Popis |
|---------|------------|
| DateKey |Odkaz na tabulku kalendářních dat udávající den. |
| DeviceKey |Jedinečný identifikátor zařízení v datovém skladu – náhradní klíč Jedná se o odkaz na tabulku zařízení obsahující ID zařízení v Intune. |
| Název zařízení |Název zařízení na platformách, které umožňují pojmenování zařízení. Na ostatních platformách Intune vytvoří název z dalších vlastností. Tento atribut nemůže být dostupný pro všechna zařízení. |
| OwnerTypeKey |Klíč atributu typu vlastníka pro toto zařízení: podnikový, osobní nebo neznámý. |
| objectSourceKey |Ignorujte tento sloupec. |
| ManagementStateKey |Klíč stavu správy, který je přidružený k tomuto zařízení a který udává poslední stav vzdálené akce nebo informaci, jestli jde o zařízení s jailbreakem nebo rootem |
| OSVersion |Verze operačního systému. |
| OSMajorVersion |Řetězec hlavní verze v zápisu verze operačního systému (hlavní.podverze.sestavení.revize). |
| OSMinorVersion |Řetězec podverze v zápisu verze operačního systému (hlavní.podverze.sestavení.revize). |
| OSBuildNumber |Řetězec sestavení v zápisu verze operačního systému (hlavní.podverze.sestavení.revize). |
| DeviceAction |Poslední vystavená akce zařízení, zatím ignorujte. |

## <a name="applicationinventory"></a>ApplicationInventory

Entita **ApplicationInventory** zobrazuje seznam aplikací, které se na zařízení nacházejí v době shromažďování inventáře.


|      Vlastnost      |                       Popis                        |
|--------------------|----------------------------------------------------------|
|     DeviceKey      |              Odkaz na tabulku zařízení.               |
|   ApplicationKey   | ? (zkopírováno z ExchangeDeviceService\DeviceApplication). |
|  ApplicationName   | ? (zkopírováno z ExchangeDeviceService\DeviceApplication). |
| ApplicationVersion | ? (zkopírováno z ExchangeDeviceService\DeviceApplication). |
|     BundleSize     | ? (zkopírováno z ExchangeDeviceService\DeviceApplication). |

