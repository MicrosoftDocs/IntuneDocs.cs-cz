---
title: Shromažďování dat v Intune
titleSuffix: Microsoft Intune
description: Přečtěte si, jak se v Intune shromažďují osobní údaje.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1171740-936d-46a5-af37-f418bd6fa63e
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cd1d0de4b1ae930ebeff07539f9cfa8848f0b7ce
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306908"
---
# <a name="data-collection-in-intune"></a>Shromažďování dat v Intune

Když uživatelé registrují svoje firemní nebo osobní zařízení pomocí Intune, Intune shromažďuje a sdílí některá osobní data. Intune shromažďuje osobní údaje z následujících zdrojů:

- Použití Intune v Azure Portal pro správce.
- Zařízení koncových uživatelů (při zápisu do správy Intune a při jejich používání).
- Zákaznické účty na službách třetích stran (podle pokynů správce).
- Informace o diagnostice, výkonu a využití.

Z těchto zdrojů Intune shromažďuje informace, které spadají do následujících tří kategorií: [identifikované](#identified-data), [pseudonymované](#pseudonymized-data)a [agregované](#aggregated-data).

> [!NOTE]
> Žádná data shromážděná naší službou neprodávají z jakéhokoli důvodu žádné třetí straně.

## <a name="identified-data"></a>Identifikovaná data

Většina osobních údajů shromažďovaných službou Intune je identifikovaná data. Tato data jsou vázaná na uživatele, zařízení nebo aplikaci a jsou zásadní pro povahu správy. Identifikovaná data se používají ke správě zařízení a aplikací uživatele a k zajištění služby Intune.

Identifikovaná data shromážděná službou Intune můžou zahrnovat, ale nejsou omezená na tyto: 

- Informace o uživateli
  - Jméno vlastníka/zobrazení uživatele (název zaregistrovaný v Azure, který identifikoval uživatel theAzureUserID)
  - Hlavní název uživatele nebo e-mailová adresa
  - Identifikace uživatele třetí strany (například AppleID)
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
- Informace protokolu auditování, včetně dat o následujících činnostech
  - Spravujte
  - Vytváření
  - Aktualizovat (Upravit)
  - Odstranit
  - Přiřazení
  - Vzdálené úlohy
- Informace pro získání podpory
  - Kontaktní informace (jméno, telefonní číslo, e-mailová adresa)
  - E-mailová diskuze s členy týmu podpory Microsoftu, produktů a/nebo zkušeností zákazníků
- Informace o řízení přístupu (Intune tato data používá ke správě přístupu k rolím a funkcím pro správu prostřednictvím funkcí jako [Access Control na základě rolí](../fundamentals/role-based-access-control.md).
  - Statické ověřovatele (heslo zákazníka)
  - Klíče ochrany osobních údajů pro certifikáty 
- Informace o Správci a účtu
  - Křestní jméno a příjmení uživatele správce
  - Uživatelské jméno správce
  - Hlavní název uživatele (e-mail)
  - Telefonní číslo
  - E-mailová adresa vlastníka účtu
  - ID služby Active Directory každého zákazníka, který správce IT
  - Platební údaje pro fakturaci zákazníkovi
  - Klíč předplatného
- Inventář aplikací, například
  - Název aplikace
  - version
  - ID aplikace
  - Hodnota
  - umístění instalace
  - Data inventáře aplikací se shromažďují jenom v případě, že je označí správce jako zařízení ve vlastnictví firmy nebo je zapnutá funkce kompatibilní aplikace.  
- ID tenantů zákaznických třetích stran, jako je Apple ID. 

## <a name="pseudonymized-data"></a>Pseudonymovaná data

Pseudonymovaná data jsou asociována s jedinečným identifikátorem, obvykle číslem vygenerovaným systémem, který nemůže sám o sobě identifikovat jednotlivou osobu, ale používá se k poskytování podnikových služeb uživatelům. 

Pseudonymovaná data shromážděná službou Intune mohou zahrnovat, ale nejsou omezená na: 

- Data o diagnostice, výkonu a využití vázaná na uživatele nebo zařízení
  - Počet, kolikrát se funkce používá
  - Příkazy, které jsou součástí funkce
  - Doba odezvy služby
  - Míry úspěšnosti instalací a dalších procesů
  - Chyby aplikace Portál společnosti služby Intune
  - Identifikátory uživatelů a zařízení
  - Identifikátory pro reference, korelace, účely správy 
- Data zařízení nejsou vázaná na zařízení nebo uživatele (pokud jsou tato data vázaná na zařízení nebo uživatele, Intune je považuje za identifikovaná data).
  - ID zařízení v Intune
  - ID zařízení Azure Active Directory
  - ID správy zařízení v Intune
  - ID tenanta
  - Account ID
  - ID zařízení EAS
  - ID specifická pro platformu
  - AppleID pro zařízení s iOS
  - Adresa MAC pro zařízení Mac
  - ID Windows pro zařízení s Windows
- Informace o spravované aplikaci
  - ID spravované aplikace
  - Značka zařízení spravované aplikace
  - ID správy zařízení v Intune
  - ID zařízení Azure Active Directory
  - Šifrovací klíče

## <a name="aggregated-data"></a>Agregovaná data

Agregovaná data se používají ke zřízení a vylepšení služby Intune. 

Agregovaná data shromážděná službou Intune mohou zahrnovat, ale nejsou omezená na: 

- Data o využití správce ze všech tenantů Intune (například ovládací prvky pro správu vybrané při interakci s konzolou správce)
- Informace o účtu klienta (Tato data jsou k dispozici v okně Intune)
  - Počet zaregistrovaných zařízení nebo uživatelů
  - Počet identifikovaných platforem zařízení  
  - Počet nainstalovaných zařízení
  - installedDeviceCount: počet zařízení, na kterých je aplikace nainstalována.
  - notApplicableDeviceCount: počet zařízení, pro která se aplikace nedá použít.
  - notInstalledDeviceCount: počet zařízení, pro která je aplikace platná, ale není nainstalovaná.
  - pendingInstallDeviceCount: počet zařízení, pro která je aplikace k dispozici, a čeká na instalaci.

## <a name="next-steps"></a>Další kroky

Přečtěte si další informace o tom, jak Intune [ukládá a zpracovává](privacy-data-store-process.md) a [sdílí](privacy-data-secure-share.md) osobní údaje. 
