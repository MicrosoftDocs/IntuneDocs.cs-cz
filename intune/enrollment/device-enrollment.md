---
title: Co je Microsoft Intune registrace zařízení
titleSuffix: Microsoft Intune
description: Přečtěte si o registraci zařízení s iOS, Androidem a Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 4/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: e3fb9af260b8fddc78b644b8ede056c90bac24d0
ms.sourcegitcommit: 29b1113dc04534c4c87c33c773c5a0e24266e042
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/07/2019
ms.locfileid: "71999352"
---
# <a name="what-is-device-enrollment"></a>Co je registrace zařízení?
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune umožňuje spravovat zařízení a aplikace vašich zaměstnanců a jejich přístup k firemním datům. Aby bylo možné používat tuto správu mobilních zařízení (MDM), musí být zařízení nejprve zaregistrovaná ve službě Intune. Když je zařízení zaregistrované, vystavuje se certifikát MDM. Tento certifikát se používá ke komunikaci se službou Intune.

Jak vidíte v následujících tabulkách, je k dispozici několik způsobů registrace zařízení zaměstnanců. Každá metoda závisí na vlastnictví zařízení (osobní nebo firemní), typu zařízení (iOS, Windows, Android) a požadavcích na správu (resetování, spřažení, uzamykání).

Ve výchozím nastavení se zařízení pro všechny platformy můžou registrovat v Intune. Zařízení můžete ale [omezit na platformu](enrollment-restrictions-set.md#create-a-device-type-restriction).

## <a name="ios-enrollment-methods"></a>metody registrace zařízení se systémem iOS

| **Metoda** | **Vyžadováno resetování** | [**Přidružení uživatele**](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) | **Uzamčení** | **Zobrazí** |
|:---:|:---:|:---:|:---:|:---:|
| | Při registraci se zařízení vymažou. | Přidružuje každé zařízení k uživateli.| Pokud ano, uživatelé nemůžou zrušit registraci zařízení. | |
|**[BYOD](#bring-your-own-device)** | Ne| Ano | Ne | [Další informace](apple-mdm-push-certificate-get.md)|
|**[DEM](#device-enrollment-manager)**| Ne |Ne |Ne | [Další informace](device-enrollment-program-enroll-ios.md)|
|**[FUNKCÍ](#apple-device-enrollment-program)**| Ano | Nepovinné | Nepovinné|[Další informace](device-enrollment-program-enroll-ios.md)|
|**[USB – SA](#usb-sa)**| Ano | Nepovinné | Ne| [Další informace](apple-configurator-enroll-ios.md)|
|**[USB – Direct](#usb-direct)**| Ne | Ne | Ne|[Další informace](apple-configurator-enroll-ios.md)|

## <a name="macos-enrollment-methods"></a>metody registrace macOS
| **Metoda** |  **Vyžadováno resetování** |  **Přidružení uživatele** | **Uzamčení** | **Zobrazí**|
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | Ne| Ano | Ne | [Další informace](macos-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Ne |Ne |Ne  | [Další informace](device-enrollment-manager-enroll.md)|
|**[FUNKCÍ](#apple-device-enrollment-program)**| Ano | Nepovinné | Nepovinné|[Další informace](device-enrollment-program-enroll-macos.md)|

## <a name="windows-enrollment-methods"></a>Metody registrace Windows

| **Metoda** | **Vyžadováno resetování** | **Přidružení uživatele** | **Uzamčení** | **Zobrazí**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | Ne | Ano | Ne | [Další informace](windows-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Ne |Ne |Ne |[Další informace](device-enrollment-manager-enroll.md)|
|**Automatický zápis** | Ne |Ano |Ne | [Další informace](windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Autopilot** |Ano |Ano |Ne | [Další informace](enrollment-autopilot.md)
|**Hromadný zápis** |Ne |Ne |Ne | [Další informace](windows-bulk-enroll.md) |
|**Spoluspráva** |Ne |Ano |Ne | [Další informace](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)
|**PŘÍSLUŠNÝ** |Ne |Ano |Ne | [Další informace](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)

## <a name="android-enrollment-methods"></a>Metody registrace zařízení s Androidem

| **Individuální** | **Metody registrace** | **Vyžadováno resetování** | **Přidružení uživatele** | **Uzamčení** | **Zobrazí**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**Správce zařízení s Androidem**|**Uživatel inicioval prostřednictvím Portál společnosti** | Ne | Ano | Ne | [Další informace](https://docs.microsoft.com/intune-user-help/enroll-device-android-company-portal)|
|**Pracovní profil Android Enterprise**|**Uživatel inicioval prostřednictvím Portál společnosti**| Ne | Ano | Ne | [Další informace](android-work-profile-enroll.md)|


| **Firmy** | **Metody registrace** | **Vyžadováno resetování** | **Přidružení uživatele** | **Uzamčení** | **Zobrazí**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**Správce zařízení s Androidem**|**[DEM](#device-enrollment-manager) iniciované prostřednictvím portál společnosti**| Ne | Ne | Ne |[Další informace](device-enrollment-manager-enroll.md)|
|**Správce zařízení s Androidem**|**(Předem deklarované IMEI nebo SN) Uživatel inicioval prostřednictvím Portál společnosti**| Ne | Ano | Ne | [Další informace](./../corporate-identifiers-add.md)|
|**Správce zařízení s Androidem s rozšířeními mobility Zebra**|**Uživatel nebo [DEM](#device-enrollment-manager) iniciované prostřednictvím portál společnosti**| Ne | Ano, pokud se uživatel inicioval, ne při zahájení [DEM](#device-enrollment-manager) | Ne | [Další informace](../configuration/android-zebra-mx-overview.md)|
|**Vyhrazená Enterprise v Androidu**|**NFC, token, kód QR, nulové dotykové ovládání**| Ano | Ne | Konfigurovatelné prostřednictvím zásad | [Další informace](android-kiosk-enroll.md)|
|**Plně spravovaná platforma Android Enterprise**|**NFC, token, kód QR, nulové dotykové ovládání**| Ano | Ano | Konfigurovatelné prostřednictvím zásad | [Další informace](android-dedicated-devices-fully-managed-enroll.md)|


## <a name="bring-your-own-device"></a>Přineste si vlastní zařízení
Přineste si vlastní zařízení (BYOD), včetně osobních telefonů, tabletů a počítačů. Uživatelé nainstalují a spustí aplikaci Portál společnosti k registraci BYODs. Tento program umožňuje uživatelům přístup k prostředkům společnosti, jako je e-mail.

## <a name="corporate-owned-device"></a>Zařízení vlastněné společností
[Zařízení vlastněná společností (COD)](corporate-identifiers-add.md) zahrnují telefony, tablety a počítače vlastněné organizací a distribuované pracovníkům. Registrace COD podporuje scénáře, jako je automatická registrace, sdílená zařízení nebo předem autorizované požadavky na registraci. Běžným způsobem, jak zaregistrovat CODs, je použít správce registrace zařízení (DEM) pro správce nebo správce. zařízení se systémem iOS je možné zaregistrovat přímo prostřednictvím nástrojů Program registrace zařízení (DEP) poskytovaných společností Apple. Zařízení s číslem IMEI se také dají identifikovat a označit jako vlastněné firmou.

### <a name="device-enrollment-manager"></a>Správce registrace zařízení
Správce registrace zařízení (DEM) je zvláštní uživatelský účet, který se používá k registraci a správě více zařízení vlastněných společností. Manažeři můžou nainstalovat Portál společnosti a zaregistrovat mnoho zařízení bez uživatelů. Tyto typy zařízení jsou vhodné pro aplikace v prodejnách nebo nástrojích, například ne pro uživatele, kteří potřebují mít přístup k e-mailu nebo firemním prostředkům. Další informace o [DEM](device-enrollment-manager-enroll.md).

### <a name="apple-device-enrollment-program"></a>Apple Program registrace zařízení
Správa Apple Program registrace zařízení (DEP) umožňuje vytvářet a nasazovat zásady "prostřednictvím Air" na zařízení s iOS a macOS, která jsou zakoupená a spravovaná pomocí programu DEP. Zařízení se zaregistruje při prvním zapnutí zařízení uživatelem a spustí se Pomocník s nastavením. Tato metoda podporuje režim iOS pod dohledem, který umožňuje konfigurovat zařízení s konkrétními funkcemi.

Další informace o registraci DEP pro iOS:

- [Volba způsobu registrace zařízení se systémem iOS](ios-enroll.md)
- [Registrace zařízení s iOS pomocí Program registrace zařízení](device-enrollment-program-enroll-ios.md)

### <a name="usb-sa"></a>USB – SA
Správci IT používají Apple Configuratoru přes USB k přípravě každého zařízení vlastněných firmou pro zápis pomocí Pomocníka s nastavením. Správce IT vytvoří profil zápisu a exportuje ho do Apple Configuratoru. Když uživatelé dostanou svá zařízení, zobrazí se jim výzva ke spuštění pomocníka s nastavením pro registraci zařízení. Tato metoda podporuje režim **iOS pod dohledem** , který zase povoluje následující funkce:
- Zamčená registrace
- Celoobrazovkový režim a další pokročilé konfigurace a omezení

Další informace o registraci Apple Configuratoru v iOS pomocí Pomocníka s nastavením:

- [Rozhodnutí o tom, jak zaregistrovat zařízení s iOS](ios-enroll.md)
- [Registrace zařízení s iOS pomocí konfigurátoru a pomocníka s nastavením](apple-configurator-enroll-ios.md)

### <a name="usb-direct"></a>USB – Direct
Pro přímou registraci musí správce zaregistrovat každé zařízení ručně tak, že vytvoří zásadu registrace a exportuje ji do Apple Configuratoru. Zařízení vlastněná společností připojená přes USB se registrují přímo a nevyžadují vymazání. Zařízení se spravují jako zařízení bez uživatele. Nejsou uzamčeny nebo pod dohledem a nemohou podporovat podmíněný přístup, zjišťování jailbreaků nebo správu mobilních aplikací.

Další informace o registraci zařízení se systémem iOS najdete v těchto tématech:

- [Rozhodnutí o tom, jak zaregistrovat zařízení s iOS](ios-enroll.md)
- [Registrace zařízení s iOS pomocí konfigurátoru a přímé registrace](apple-configurator-enroll-ios.md)

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Vyčištění mobilního zařízení po vypršení platnosti certifikátu MDM

Certifikát MDM se obnovuje automaticky, když mobilní zařízení komunikují se službou Intune. Pokud se mobilní zařízení vymažou nebo se po určitou dobu nedaří komunikovat se službou Intune, certifikát MDM se neobnoví. Zařízení se odebere z Azure Portal 180 dnů po vypršení platnosti certifikátu MDM.
