---
title: Registrace zařízení s iOSem v Intune
titleSuffix: Microsoft Intune
description: Nastavení registrace zařízení s iOSem v Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: eef5524cff3ce29e802ca8078ba2b5e104e89775
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59895310"
---
# <a name="enroll-ios-devices-in-intune"></a>Registrace zařízení s iOSem v Intune

Intune umožňuje správu mobilních zařízení (MDM) u iPadů a iPhonů, aby mohli jejich uživatelé získat přístup k firemnímu e-mailu a aplikacím.

Jako správce Intune můžete povolit registraci zařízení s iOSem. Můžete uživatelům umožnit registraci osobních zařízení, která se označuje jako registrace BYOD (přineste si vlastní zařízení). Můžete povolit také registraci zařízení vlastněných firmou.

## <a name="prerequisites-for-ios-enrollment"></a>Předpoklady pro registraci zařízení s iOSem
Před povolením zařízení s iOSem proveďte následující kroky:
- [Nastavení Intune](setup-steps.md) – tento postup slouží k nastavení infrastruktury Intune. Registrace zařízení vyžaduje zejména [nastavení autority MDM](mdm-authority-set.md).
- [Získání certifikátu Apple MDM Push Certificate](apple-mdm-push-certificate-get.md) – Apple vyžaduje k povolení správy zařízení s iOSem a macOS certifikát.

## <a name="user-owned-ios-devices-byod"></a>Zařízení se systémem iOS vlastněné uživatelem (BYOD)

Uživatelům můžete umožnit, aby si zaregistrovali svoje osobní zařízení pro správu Intune. Tato možnost se označuje jako Přineste si vlastní zařízení neboli BYOD. Po splnění požadavků a přiřazení uživatelských licencí si uživatelé můžou stáhnout aplikaci Portál společnosti z App Storu a podle pokynů v aplikaci si zařízení zaregistrovat.

## <a name="company-owned-ios-devices"></a>Zařízení s iOSem patřící společnosti
U organizací, které svým uživatelům zařízení nakupují, Intune podporuje následující způsoby registrace zařízení s iOSem patřících společnosti:

- Program registrace zařízení (DEP) společnosti Apple
- Apple School Manager
- Registrace Průvodce nastavením s Apple Configuratorem
- Přímá registrace pomocí Apple Configuratoru

Zařízení s iOSem, která patří společnosti, můžete také zaregistrovat pomocí účtu [správce registrace zařízení](device-enrollment-manager-enroll.md).

## <a name="device-enrollment-program"></a>Program DEP (Device Enrollment Program)
Organizace můžou nakupovat zařízení s iOSem prostřednictvím Programu registrace zařízení (DEP) společnosti Apple. Program DEP umožňuje vzdáleně (bezdrátově) nasadit registrační profil, který umožní správu těchto zařízení. Přečtěte si další informace o [Programu registrace zařízení](device-enrollment-program-enroll-ios.md).

## <a name="apple-school-manager"></a>Apple School Manager
Apple School Manager je program nákupu a registrace zařízení pro školy. Stejně jako u programu DEP máte možnost nasadit profil pro registraci zařízení pro účely správy. Další informace o [Apple School Manageru](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Apple Configurator
Zařízení s iOSem můžete zaregistrovat pomocí nástroje Apple Configurator spuštěného na počítači Mac. Zařízení připravíte tak, že je připojíte přes USB a nainstalujete registrační profil. Zařízení můžete pomocí Apple Configuratoru registrovat dvěma způsoby:
- Registrace pomocí Pomocníka s nastavením – Vymaže zařízení, připraví ho ke spuštění Pomocníka s nastavením a nainstaluje zásady společnosti pro nového uživatele zařízení.
- Přímá registrace – Nevymaže zařízení a zaregistruje ho s předdefinovanými zásadami. Tato metoda je vhodná pro zařízení bez přidružení uživatele.

Přečtěte si další informace o [registraci pomocí Apple Configuratoru](apple-configurator-setup-assistant-enroll-ios.md).

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>Použití služby Portálu společnosti v zařízeních zaregistrovaných pomocí Programu registrace zařízení nebo nástroje Apple Configurator

Zařízení nakonfigurovaná s přidružením uživatele umožňují instalaci a spuštění aplikace Portál společnosti, která slouží ke stahování aplikací a správě zařízení. Když uživatelé obdrží zařízení, musí provést určitý počet dodatečných kroků, aby dokončili postup Pomocníka s nastavením a nainstalovali aplikaci Portál společnosti.

Přidružení uživatele je nezbytné pro podporu následujících funkcí:
  - Aplikace MAM (správa mobilních aplikací)
  - Podmíněný přístup k e-mailu a firemním datům
  - Aplikace Portál společnosti

**Postup registrace zařízení s iOSem vlastněných společností s přidružením uživatele**
1. Když uživatel zapne své zařízení, zobrazí se výzva k dokončení postupu Pomocníka s nastavením. 
2. Po dokončení nastavení se uživateli zobrazí výzva k zadání Apple ID. Aby mohlo zařízení nainstalovat aplikaci Portál společnosti, musí uživatel zadat Apple ID. 
3. Zařízení s iOSem automaticky nainstaluje aplikaci Portál společnosti z App Storu.
4. Uživatelé by měli aplikaci Portál společnosti spustit a přihlásit se pomocí přihlašovacích údajů (jako je jedinečné osobní jméno nebo hlavní název uživatele), které jsou přidružené k jejich předplatnému v Intune. 
5. Po přihlášení se registrace dokončí. Uživatelé teď můžou na zařízení používat kompletní sadu funkcí.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>O firemních spravovaných zařízeních bez přidružení uživatele

Zařízení nakonfigurovaná bez přidružení uživatele nepodporují aplikaci Portál společnosti a ta by se na ně neměla instalovat. Portál společnosti je určený pro uživatele, kteří mají firemní přihlašovací údaje a potřebují přístup k podnikovým prostředkům podle svých potřeb (třeba k e-mailu). Zařízení zaregistrovaná bez přidružení uživatele nejsou určená k tomu, aby se k nim přihlašoval jeden vyhrazený uživatel. Typickými případy použití zařízení zaregistrovaných bez přidružení uživatele jsou zařízení veřejných terminálů, pokladny nebo sdílená zařízení.

Pokud je požadováno přidružení uživatele, před registrací zařízení zkontrolujte, jestli je u registračního profilu daného zařízení vybraná možnost **Přidružení uživatele**. Pokud chcete stav přidružení zařízení změnit, musíte zařízení nejdřív vyřadit a potom ho znovu zaregistrovat.

