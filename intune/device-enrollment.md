---
title: Co je registrace zařízení v Microsoft Intune?
titlesuffix: Microsoft Intune
description: Přečtěte si o registraci zařízení s iOSem, Androidem a Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/11/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.openlocfilehash: 73caf328bd25cb31bacea6b964c1db7601f3aec6
ms.sourcegitcommit: baacdb2c5ee69d0055acad2d64f2bf1a3fc5e02d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/18/2018
ms.locfileid: "53570804"
---
# <a name="what-is-device-enrollment"></a>Co je registrace zařízení?
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune umožňuje spravovat zařízení a aplikace vašich zaměstnanců a způsob, jakým přistupují k firemním datům. Abyste správu mobilních zařízení (MDM) mohli používat, musí být zařízení napřed zaregistrované ve službě Intune. Když je zařízení zaregistrované, vystaví se mu certifikát MDM. Tento certifikát slouží ke komunikaci se službou Intune.

Jak ukazují následující tabulky, registrují se zařízení zaměstnanců několika způsoby. Jednotlivé způsoby závisí na vlastnictví zařízení (osobní nebo firemní), typu zařízení (iOS, Windows, Android) a požadavcích na správu (resetování, spřažení, uzamčení).

Standardně se do Intune můžou registrovat zařízení pro všechny platformy. Můžete však [omezit zařízení podle platformy](enrollment-restrictions-set.md#set-device-type-restrictions).

## <a name="ios-enrollment-methods"></a>Metody registrace zařízení s iOS

| **– Metoda** |  **Vyžadováno resetování** |    [**Přidružení uživatele**](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) |   **Uzamčeno** | **Podrobnosti** |
|:---:|:---:|:---:|:---:|:---:|
| | Zařízení se vymažou při registraci. |  Jednotlivá zařízení se přidruží k uživateli.| Uživatelé nemohou zrušit registraci zařízení.  | |
|**[Uživatelé s vlastním zařízením (BYOD)](#bring-your-own-device)** | Ne|   Ano |   Ne | [Další informace](./apple-mdm-push-certificate-get.md)|
|**[DEM](#device-enrollment-manager)**| Ne |Ne |Ne  | [Další informace](./device-enrollment-program-enroll-ios.md)|
|**[DEP](#apple-device-enrollment-program)**|   Ano |   volitelná, |  volitelná,|[Další informace](./device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Ano |   volitelná, |  Ne| [Další informace](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB (přímo)](#usb-direct)**| Ne |    Ne  | Ne|[Další informace](./apple-configurator-direct-enroll-ios.md)|

## <a name="macos-enrollment-methods"></a>Metody registrace zařízení s macOS
| **– Metoda** |  **Vyžadováno resetování** |  **Přidružení uživatele** | **Uzamčeno** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#bring-your-own-device)** | Ne| Ano | Ne | [Další informace](./macos-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Ne |Ne |Ne  | [Další informace](./device-enrollment-manager-enroll.md)|
|**[DEP](#apple-device-enrollment-program)**|   Ano |   volitelná, |  volitelná,|[Další informace](./device-enrollment-program-enroll-macos.md)|


## <a name="windows-enrollment-methods"></a>Metody registrace zařízení s Windows

| **– Metoda** |  **Vyžadováno resetování** |    **Přidružení uživatele**   |   **Uzamčeno** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#bring-your-own-device)** | Ne |  Ano |   Ne | [Další informace](windows-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Ne |Ne |Ne  |[Další informace](device-enrollment-manager-enroll.md)|
|**Automatická registrace** | Ne |Ano |Ne | [Další informace](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**AutoPilot** |Ano |Ano |Ne | [Další informace](enrollment-autopilot.md)
|**Hromadná registrace** |Ne |Ne |Ne | [Další informace](./windows-bulk-enroll.md) |
|**Společná správa** |Ne |Ano |Ne | [Další informace](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)
|**Objekty zásad skupiny** |Ne |Ano |Ne | [Další informace](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)


## <a name="android-enrollment-methods"></a>Metody registrace zařízení s Androidem

| **– Metoda** |  **Vyžadováno resetování** |    **Přidružení uživatele**   |   **Uzamčeno** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#bring-your-own-device)** | Ne|   Ano |   Ne | [Další informace](./android-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Ne |Ne |Ne  |[Další informace](./device-enrollment-manager-enroll.md)|
|**Pracovní profily Androidu**| Ne | Ano | Ne| [Další informace](./android-work-profile-enroll.md) |


## <a name="bring-your-own-device"></a>Přineste si vlastní zařízení
Funkce Přineste si vlastní zařízení (BYOD) umožňuje použít osobní telefony, tablety a počítače. Kvůli registraci vlastního zařízení uživatelé nainstalují a používají aplikaci Portál společnosti. Tento program umožňuje uživatelům přístup k firemním prostředkům, jako je třeba e-mail.

## <a name="corporate-owned-device"></a>Zařízení vlastněná společností
[Mezi zařízení vlastněná společností](corporate-identifiers-add.md) patří telefony, tablety a počítače ve vlastnictví organizace, které se přidělují zaměstnancům. Registrace zařízení vlastněných společností umožňuje různé způsoby správy, například v podobě automatické registrace, sdílených zařízení nebo předem autorizovaných požadavků na registraci. Správce nebo manažer používá k registraci takových zařízení nejčastěji Správce registrace zařízení (DEM). Zařízení iOS lze zaregistrovat přímo prostřednictvím nástrojů DEP (Device Enrollment Program), které poskytuje Apple. Zařízení s číslem IMEI lze také identifikovat a označit jako zařízení vlastněných společností.

### <a name="device-enrollment-manager"></a>správce registrace zařízení
Správce registrace zařízení (DEM) je zvláštní uživatelský účet, který se používá k registraci a správě více zařízení vlastněných společností. Správci pak mohou nainstalovat aplikaci Portál společnosti a zaregistrovat velký počet zařízení bez uživatele. Tyto typy zařízení se hodí například pro aplikace POS a jednoúčelové aplikace, ale nehodí se pro uživatele, kteří potřebují přístup k e-mailu nebo k prostředkům společnosti. Přečtěte si další informace o [DEM](./device-enrollment-manager-enroll.md). 

### <a name="apple-device-enrollment-program"></a>Program Apple Device Enrollment Program
Správa programu registrace zařízení Apple (DEP) umožňuje vytvořit a nasadit zásady "vzduchem" na zařízení s Iosem a macOS, které zakoupených a spravovaných s DEP Zařízení se zaregistruje, když uživatelé zapněte zařízení poprvé a spustí Pomocníka pro nastavení. Tato metoda podporuje režim iOSu pod dohledem, který umožňuje v zařízení nakonfigurovat konkrétní funkce.

Registrace DEP pro iOS je podrobněji popsaná zde:

- [Volba způsobu registrace zařízení s iOSem](ios-enroll.md)
- [Registrace zařízení s iOSem pomocí Programu registrace zařízení (DEP)](https://docs.microsoft.com/intune/device-restrictions-ios#device-enrollment-program)

### <a name="usb-sa"></a>USB (pomocník pro instalaci)
Správci IT používají k ruční přípravě každého zařízení vlastněného společností pro registraci Apple Configurator (přes USB) a Pomocníka s nastavením. Správce IT vytvoří registrační profil a vyexportuje ho do Apple Configuratoru. Když uživatelé obdrží svá zařízení, budou vyzváni ke spuštění pomocníka pro nastavení a k registraci zařízení. Tato metoda podporuje režim **iOS – Pod dohledem**, který umožňuje následující funkce:
  - Registrace uzamčeného zařízení
  - Beznabídkový režim a další pokročilé konfigurace a omezení

Další informace o registraci pro iOS prostřednictvím Apple Configuratoru a Pomocníka s nastavením:

- [Rozhodnutí o způsobu registrace zařízení s iOSem](enrollment-method-choose-ios.md)
- [Registrace zařízení s iOSem pomocí nástroje Configurator a Průvodce nastavením](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB (přímo)
U přímé registrace musí správce každé zařízení zaregistrovat ručně vytvořením zásady registrace, kterou vyexportuje do Apple Configuratoru. Zařízení vlastněná společností, která jsou připojena přes USB, se zaregistrují přímo a nevyžadují vymazání. Zařízení se spravují jako zařízení bez uživatele. Nejsou uzamčená ani pod dohledem a nepodporují podmíněný přístup, detekci jailbreaků ani správu mobilních aplikací.

Registrace iOS je podrobněji popsaná zde:

- [Rozhodnutí o způsobu registrace zařízení s iOSem](enrollment-method-choose-ios.md)
- [Registrace zařízení s iOSem pomocí nástroje Configurator a přímé registrace](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Intune
Mobilní zařízení, která nejsou zaregistrovaná, ale připojují se k Exchange ActiveSync (EAS), je možné spravovat pomocí Intune s využitím zásad EAS MDM. Intune používá ke komunikaci s EAS softwarovou funkci Exchange Connector, která může být místní nebo hostovaná v cloudu. Brzy budou k dispozici další informace.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Vyčištění mobilních zařízení po vypršení platnosti certifikátu MDM

Certifikát MDM se obnovuje automaticky, když mobilní zařízení komunikují se službou Intune. Když se mobilní zařízení vymažou nebo se jim po určitou dobu nedaří komunikovat se službou Intune, certifikát MDM se neobnoví. Zařízení se z portálu Azure Portal odebere po uplynutí 180 dnů od vypršení platnosti certifikátu MDM.
