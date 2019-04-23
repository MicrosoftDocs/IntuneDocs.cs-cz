---
title: Shromažďování údajů v Intune
description: Přečtěte si, jak se v Intune shromažďují osobní údaje.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1171740-936d-46a5-af37-f418bd6fa63e
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: eede87fdca31e8e263d1dea78d766fec59f05f58
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511298"
---
# <a name="data-collection-in-intune"></a>Shromažďování údajů v Intune

Když si uživatelé zaregistrují svá firemní nebo osobní zařízení pomocí Intune, některé z jejich osobních údajů se shromažďují a sdílí. Intune shromažďuje osobní údaje z těchto zdrojů:

- Využití služby Intune na portálu Azure Portal správcem
- Zařízení koncových uživatelů (při registraci ke správě Intune a v průběhu využívání)
- Účty zákazníků u služeb třetích stran (podle pokynů správce)
- Diagnostické informace a informace o výkonu a použití

Z těchto zdrojů shromažďuje Intune informace, které spadají do těchto tří kategorií: [identifikované](#identified-data), [pseudonymizované](#pseudonymized-data) a [agregované](#aggregated-data) údaje.

## <a name="identified-data"></a>Identifikované údaje

Většina osobních údajů shromážděných službou Intune představuje identifikované údaje. Tato data se vážou k uživateli, zařízení nebo aplikaci a pro správu jako takovou jsou nezbytná. Slouží ke správě zařízení a aplikací uživatele a poskytování služby Intune.

Mezi identifikovaná data shromažďovaná službou Intune patří mimo jiné: 

- Údaje uživatele
    - Jméno vlastníka / zobrazované jméno uživatele (jméno uživatele zaregistrované v Azure, které označuje ID uživatele služby Azure)
    - Hlavní název uživatele nebo e-mailová adresa
    - Identifikátory uživatele třetích stran (např. Apple ID)
- Informace o inventáři hardwaru
    - Název zařízení
    - Výrobce
    - Operační systém
    - Sériové číslo
    - Číslo IMEI
    - IP adresa
    - Wi-Fi MacAddress
    - ICCID
    - Telefonní číslo
- Informace z protokolů auditů včetně dat o následujících aktivitách
    - Správa
    - Create
    - Aktualizace (úpravy)
    - Odstranění
    - Assign
    - Vzdálené úlohy
- Informace o podpoře
    - Kontaktní informace (jméno, telefonní číslo, e-mailová adresa)
    - E-mailové diskuze s podporou Microsoftu a členy produktových týmů nebo týmů zaměřených na zkušenosti uživatelů
- Informace o řízení přístupu (Intune tato data využívá ke správě přístupu k rolím a funkcím pro správu prostřednictvím funkcí, jako je [Řízení přístupu založené na rolích](role-based-access-control.md).)
    - Statické ověřovače (heslo zákazníka)
    - Klíče osobních údajů pro certifikáty 
- Informace o správci a účtu
    - Jméno a příjmení uživatele s rolí správce
    - Uživatelské jméno správce
    - Hlavní název uživatele (UPN, e-mail)
    - Telefonní číslo
    - E-mailová adresa vlastníka účtu
    - ID služby Active Directory správce IT každého zákazníka
    - Platební údaje pro fakturaci zákazníka
    - Klíč předplatného
- Inventář aplikací, například
    - Název aplikace
    - Verze
    - ID aplikace
    - Velikost
    - Umístění instalace
    - Data inventáře aplikací se shromažďují pouze tehdy, pokud je správce označí jako zařízení vlastněné společností nebo pokud je zapnutá funkce aplikace dodržující předpisy.  
- Zákaznická ID tenantů třetích stran, jako je Apple ID 

## <a name="pseudonymized-data"></a>Pseudonymizované údaje

Pseudonymizované údaje jsou přidružené k jedinečnému identifikátoru (zpravidla systémem vygenerovanému číslu), který jako takový nedokáže identifikovat jednotlivce, ale slouží k poskytování podnikových služeb uživatelům. 

Mezi pseudonymizované údaje shromažďované službou Intune patří mimo jiné: 

- Diagnostické informace a informace o výkonu a použití svázané s uživatelem a/nebo zařízením
    - Počet použití funkce
    - Příkazy zadané funkci
    - Doba odezvy služby
    - Úspěšnost instalací a dalších procesů
    - Chyby aplikace Portál společnosti Intune
    - Identifikátory uživatele a zařízení
    - Identifikátory pro účely reference, korelace a správy 
- Data zařízení nesvázaná se zařízením nebo uživatelem (jsou-li svázaná se zařízením nebo uživatelem, Intune s nimi nakládá jako s identifikovanými údaji)
    - ID zařízení v Intune
    - ID zařízení v Azure Active Directory
    - ID správy zařízení v Intune
    - ID tenanta
    - ID účtu
    - ID zařízení v EAS
    - ID specifická pro konkrétní platformu
    - Apple ID zařízení s iOSem
    - Adresa MAC zařízení s macOS
    - Windows ID zařízení s Windows
- Informace o spravované aplikaci
    - ID spravované aplikace
    - Značka zařízení spravované aplikace
    - ID správy zařízení v Intune
    - ID zařízení v Azure Active Directory
    - Šifrovací klíče

## <a name="aggregated-data"></a>Agregované údaje

Agregované údaje slouží k poskytování a zlepšování služby Intune. 

Mezi agregované údaje shromažďované službou Intune patří mimo jiné: 

- Údaje o využití správcem ze všech tenantů Intune (například ovládací prvky pro správu zvolené při interakci s konzolou správce)
- Informace o účtu tenanta (tyto údaje jsou dostupné v okně Intune)
    - Počet zaregistrovaných zařízení nebo uživatelů
    - Počet identifikovaných platforem zařízení  
    - Počet nainstalovaných zařízení
    - installedDeviceCount: Počet zařízení, na kterých je aplikace nainstalovaná.
    - notApplicableDeviceCount: Počet zařízení, pro které aplikace se nedá použít.
    - notInstalledDeviceCount: Počet zařízení, u které aplikace použít, ale není nainstalované.
    - pendingInstallDeviceCount: Numberr zařízení, pro které se vztahuje aplikace a instalace čeká na vyřízení.
    
## <a name="next-steps"></a>Další postup

Přečtěte si další informace o tom, jak služba Intune [ukládá a zpracovává](privacy-data-store-process.md) a [sdílí](privacy-data-secure-share.md) osobní údaje. 
