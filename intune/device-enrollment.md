---
title: "Co je registrace zařízení v Microsoft Intune?"
titlesuffix: Azure portal
description: "Přečtěte si o registraci zařízení s iOSem, Androidem a Windows."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 12/29/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dc0105bb786d8b1e569b11898b0d3757feba406a
ms.sourcegitcommit: a55a7119a15836b6941fdd5b32b9076139093693
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="what-is-device-enrollment"></a>Co je registrace zařízení?
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune umožňuje spravovat zařízení a aplikace vašich zaměstnanců a způsob, jakým přistupují k firemním datům. Abyste správu mobilních zařízení (MDM) mohli používat, musí být zařízení napřed zaregistrované ve službě Intune. Když je zařízení zaregistrované, vystaví se mu certifikát MDM. Tento certifikát slouží ke komunikaci se službou Intune.

Jak ukazují následující tabulky, registrují se zařízení zaměstnanců několika způsoby. Jednotlivé způsoby závisí na vlastnictví zařízení (osobní nebo firemní), typu zařízení (iOS, Windows, Android) a požadavcích na správu (resetování, spřažení, uzamčení).

## <a name="ios-enrollment-methods"></a>Metody registrace zařízení s iOS

| **Metoda** |  **Vyžadováno resetování** |    [**Přidružení uživatele**](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) |   **Uzamčeno** | **Podrobnosti** |
|:---:|:---:|:---:|:---:|:---:|
| | Během registrace se zařízení resetuje. |  Jednotlivá zařízení se přidruží k uživateli.| Uživatelé nemohou zrušit registraci zařízení.  | |
|**[Uživatelé s vlastním zařízením (BYOD)](#bring-your-own-device)** | Ne|   Ano |   Ne | [Další informace](./apple-mdm-push-certificate-get.md)|
|**[DEM](#device-enrollment-manager)**| Ne |Ne |Ne  | [Další informace](./device-enrollment-program-enroll-ios.md)|
|**[DEP](#apple-device-enrollment-program)**|   Ano |   Volitelné |  Volitelné|[Další informace](./device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Ano |   Volitelné |  Ne| [Další informace](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB (přímo)](#usb-direct)**| Ne |    Ne  | Ne|[Další informace](./apple-configurator-direct-enroll-ios.md)|

## <a name="windows-enrollment-methods"></a>Metody registrace zařízení s Windows

| **Metoda** |  **Vyžadováno resetování** |    **Přidružení uživatele**   |   **Uzamčeno** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#bring-your-own-device)** | Ne |  Ano |   Ne | [Další informace](windows-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Ne |Ne |Ne  |[Další informace](device-enrollment-manager-enroll.md)|
|**Automatická registrace** | Ne |Ano |Ne | [Další informace](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Hromadná registrace** |Ne |Ne |Ne | [Další informace](./windows-bulk-enroll.md) |

## <a name="android-enrollment-methods"></a>Metody registrace zařízení s Androidem

| **Metoda** |  **Vyžadováno resetování** |    **Přidružení uživatele**   |   **Uzamčeno** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#bring-your-own-device)** | Ne|   Ano |   Ne | [Další informace](./android-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Ne |Ne |Ne  |[Další informace](./device-enrollment-manager-enroll.md)|
|**Android for Work**| Ne | Ano | Ne| [Další informace](./android-enroll.md#enable-enrollment-of-android-for-work-devices) |


## <a name="bring-your-own-device"></a>Přineste si vlastní zařízení
Funkce Přineste si vlastní zařízení (BYOD) umožňuje použít osobní telefony, tablety a počítače. Kvůli registraci vlastního zařízení uživatelé nainstalují a používají aplikaci Portál společnosti. Tento program umožňuje uživatelům přístup k firemním prostředkům, jako je třeba e-mail.

## <a name="corporate-owned-device"></a>Zařízení vlastněná společností
Mezi zařízení vlastněná společností patří telefony, tablety a počítače ve vlastnictví organizace, které se přidělují zaměstnancům. Registrace zařízení vlastněných společností umožňuje různé způsoby správy, například v podobě automatické registrace, sdílených zařízení nebo předem autorizovaných požadavků na registraci. Správce nebo manažer používá k registraci takových zařízení nejčastěji Správce registrace zařízení (DEM). Zařízení iOS lze zaregistrovat přímo prostřednictvím nástrojů DEP (Device Enrollment Program), které poskytuje Apple. Zařízení s číslem IMEI se také dají identifikovat a označit jako zařízení vlastněná společností.

### <a name="device-enrollment-manager"></a>správce registrace zařízení
Správce registrace zařízení (DEM) je zvláštní uživatelský účet, který se používá k registraci a správě více zařízení vlastněných společností. Správci pak mohou nainstalovat aplikaci Portál společnosti a zaregistrovat velký počet zařízení bez uživatele. Přečtěte si další informace o [DEM](./device-enrollment-manager-enroll.md).

### <a name="apple-device-enrollment-program"></a>Program Apple Device Enrollment Program
Správa programu DEP společnosti Apple umožňuje vytvářet a bezdrátově nasazovat zásady v zařízeních s iOSem zakoupených a spravovaných prostřednictvím programu DEP. Zařízení se zaregistruje, když ho uživatel poprvé zapne a spustí pomocníka pro nastavení iOS (Setup Assistant). Tato metoda podporuje režim iOSu pod dohledem, který umožňuje v zařízení nakonfigurovat konkrétní funkce.

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
U přímé registrace musí správce každé zařízení zaregistrovat ručně vytvořením zásady registrace, kterou vyexportuje do Apple Configuratoru. Zařízení vlastněná společností, která jsou připojena přes USB, se zaregistrují přímo, a nevyžadují obnovení továrního nastavení. Zařízení se spravují jako zařízení bez uživatele. Nejsou uzamčená ani pod dohledem a nepodporují podmíněný přístup, detekci jailbreaků ani správu mobilních aplikací.

Registrace iOS je podrobněji popsaná zde:

- [Rozhodnutí o způsobu registrace zařízení s iOSem](enrollment-method-choose-ios.md)
- [Registrace zařízení s iOSem pomocí nástroje Configurator a přímé registrace](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Intune
Mobilní zařízení, která nejsou zaregistrovaná, ale připojují se k Exchange ActiveSync (EAS), je možné spravovat pomocí Intune s využitím zásad EAS MDM. Intune používá ke komunikaci s EAS softwarovou funkci Exchange Connector, která může být místní nebo hostovaná v cloudu. Brzy budou k dispozici další informace.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Vyčištění mobilních zařízení po vypršení platnosti certifikátu MDM

Certifikát MDM se obnovuje automaticky, když mobilní zařízení komunikují se službou Intune. Když se mobilní zařízení vymažou nebo se jim po určitou dobu nedaří komunikovat se službou Intune, certifikát MDM se neobnoví. Zařízení se z portálu Azure Portal odebere po uplynutí 180 dnů od vypršení platnosti certifikátu MDM.
