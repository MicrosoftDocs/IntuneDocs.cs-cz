---
title: Nastavení registrace v Intune pro Android Enterprise plně spravovaná zařízení
titlesuffix: Microsoft Intune
description: Zjistěte, jak zaregistrovat zařízení s Androidem Enterprise, plně spravovaná v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 23b6bef0bd1b3bad0c5fc616d6b936bbfcd93e2d
ms.sourcegitcommit: f1681554ad842c22ad3f82f0e6d44d5966e4aa3d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56458820"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-fully-managed-devices-preview"></a>Nastavení Intune registraci Androidu Enterprise plně spravovaná zařízení (Preview)

Jsou zařízení s androidem Enterprise, plně spravovaná zařízení vlastněných společností, které jsou spojené s jeden uživatel a slouží výhradně pro pracovní a ne osobní použití. Správci můžou spravovat celé zařízení a vynucovat pracovat profilů, jako například ovládací prvky zásad:
- Povolit instalaci aplikací pouze z spravovaný obchod Google Play
- Odinstalace bloku spravovaných aplikací
- zabránit uživatelům ve továrního nastavení zařízení a tak dále.

Intune vám pomůže nasadit aplikace a nastavení na zařízení s Androidem Enterprise, včetně Androidu Enterprise plně spravovaná zařízení. Konkrétní podrobnosti o Androidu Enterprise, najdete v části [požadavky na Androidu Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="technical-requirements"></a>Technické požadavky

Musíte mít tenanta samostatné služby Intune ke správě zařízení s Androidem Enterprise, plně spravovaná. Správa plně spravovaná zařízení není k dispozici v hybridní režim (SCCM připojení) nebo v konzole pro správu starší verze Silverlight.

Zařízení musí splňovat tyto požadavky jej lze spravovat jako plně spravovaná zařízení s Androidem Enterprise:

- Verze operačního systému Android 5.1 a vyšší
- Zařízení musí používat sestavení androidu, který má připojení Google Mobile Services (g). Zařízení musí mít dostupnou službu GMS a musí být schopna se k této službě připojit.

Pokud jsou výše uvedené požadavky splněny, neexistuje žádné omezení na výrobce zařízení/výrobce OEM.

## <a name="set-up-android-enterprise-fully-managed-device-management"></a>Nastavení správy pro zařízení s Androidem Enterprise, plně spravovaná

Nastavení Androidu Enterprise plně spravovaná Správa zařízení, postupujte podle těchto kroků:

1. Abyste se připravili na správu mobilních zařízení, je nutné [nastavení mobilních zařízení (MDM) autority pro správu **Microsoft Intune**](mdm-authority-set.md). Tato možnost se nastavuje jenom jednou při prvním nastavování Intune pro správu mobilních zařízení.
2. [Připojení účtu tenanta Intune ke svému účtu Androidu Enterprise](connect-intune-android-enterprise.md).
3. [Povolit zařízení vlastněných společností](#enable-corporate-owned-user-devices)
4. [Tato plně spravovaná zařízení zaregistrovat](#enroll-the-fully-managed-devices).

### <a name="enable-corporate-owned-user-devices"></a>Povolit firemní vlastněné zařízení

1. Přejděte [portál Intune](https://portal.azure.com) a zvolte **registrace zařízení** > **registrace zařízení s Androidem** > **vlastněné společností, plně spravovaná zařízení uživatelů (Preview)**.
2. V části **umožňují uživatelům registraci zařízení vlastněných společností uživatelů**, zvolte **Ano**.

Když toto nastavení je **Ano**, poskytne vám token pro registraci (náhodný řetězec) a kód QR pro vašeho tenanta Intune. Tento token jeden registrace je platná pro všechny uživatele a bez vypršení platnosti. V závislosti na operační systém Android a verze zařízení můžete použít buď tokenu nebo kódu QR registrace zařízení beznabídkového režimu.

## <a name="enroll-the-fully-managed-devices"></a>Tato plně spravovaná zařízení zaregistrovat
Teď můžete [plně spravovaná zařízení registrovat](android-dedicated-devices-fully-managed-enroll.md).

## <a name="considerations-for-this-preview-feature"></a>Důležité informace týkající se této funkce ve verzi preview
Tato veřejná Předběžná verze obsahuje základní sadu funkcí pro Android Enterprise plně spravované řešení. Chceme slyšet o vašich zkušenostech s použitím funkce ve verzi preview pomocí kteréhokoli z vaší aktuální komunikačních kanálů pro tým (třeba [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas?category_id=210853)).

Tato verze preview podporuje následující funkce pro zařízení s Androidem Enterprise plně spravovaná:
- Registrace zařízení pomocí NFC, token položka, kód QR a nula Touch
- Konfigurace zařízení u skupin uživatelů
- Distribuce aplikací a konfigurace pro skupiny uživatelů


Při použití tyto funkce verze preview mějte následující:
- Funkce ve verzi preview se nedoporučuje pro klíčové nebo nasazení v produkčním prostředí. 
- Funkce ve verzi Preview jsou implementovány standardy produkčního prostředí Microsoft Intune. Ne všechny funkce Intune jsou však k dispozici pro použití s podnikových zařízení s Androidem plně spravované uživatele. Funkce ve verzi Preview jsou jasně označené "(preview)" v konzole Intune. 
- Funkce ve verzi preview jsou plně podporované prostřednictvím jsou obvykle kanály podpory Intune.
- Registrace zařízení s Androidem Enterprise, plně spravované pomocí registrace mobilní zařízení Samsung Knox není podporované ve verzi preview. 
- Použití portálu společnosti Intune, aplikace se nepodporuje na Androidu Enterprise plně spravovaných zařízení. 
- Podmíněný přístup, zásady ochrany aplikací a certifikátů nasazení nejsou podporované ve verzi preview, jako jsou funkce Intune. 
- Cílení na skupiny zařízení profilu nebo aplikace se nepodporuje ve verzi preview. Cílení pouze skupiny uživatelů se podporuje. 
- Neexistuje žádné prvotřídní uživatelské rozhraní pro konfiguraci e-mailu, Wi-Fi nebo VPN. Použití zásad Konfigurace aplikací ke konfiguraci nastavení konfigurace podporované aplikací.

## <a name="next-steps"></a>Další postup
- [Plně spravovaná zásady Konfigurace zařízení s Androidem Enterprise, přidáme](device-restrictions-android-for-work.md#device-owner-only)
- [Konfigurace zásady Konfigurace aplikací pro Android Enterprise plně spravovaná zařízení](app-configuration-policies-use-android.md)

