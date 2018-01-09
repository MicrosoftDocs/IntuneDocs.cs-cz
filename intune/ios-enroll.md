---
title: "Volba způsobu registrace zařízení s Windows v Intune"
titlesuffix: Azure portal
description: "Přečtěte si, jak nastavit registraci zařízení s Windows v Microsoft Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1bcdaa30df09313d3eda96410b6b394f1a0029d3
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/04/2018
---
# <a name="enroll-ios-devices-in-intune"></a>Registrace zařízení s iOSem v Intune

Intune umožňuje správu mobilních zařízení (MDM) u iPadů a iPhonů, aby mohli jejich uživatelé získat přístup k firemnímu e-mailu a aplikacím.

Jako správce Intune můžete povolit registraci zařízení s iOSem. Můžete uživatelům povolit registraci osobních zařízení, která se označuje jako registrace BYOD (přineste si vlastní zařízení). Můžete povolit také registraci zařízení vlastněných firmou.

## <a name="prerequisites-for-ios-enrollment"></a>Předpoklady pro registraci zařízení s iOSem
Před povolením zařízení s iOSem proveďte následující kroky:
- [Nastavení Intune](setup-steps.md) – tento postup slouží k nastavení infrastruktury Intune. Registrace zařízení vyžaduje zejména [nastavení autority MDM](mdm-authority-set.md).
- [Získání certifikátu Apple MDM Push Certificate](apple-mdm-push-certificate-get.md) – Apple vyžaduje k povolení správy zařízení s iOSem a macOS certifikát.

## <a name="user-owned-ios-devices-byod"></a>Zařízení se systémem iOS vlastněné uživatelem (BYOD)

Uživatelům můžete umožnit, aby si zaregistrovali svoje osobní zařízení pro správu Intune. Tato možnost se označuje jako Přineste si vlastní zařízení neboli BYOD. Po splnění požadavků a přiřazení uživatelských licencí si uživatelé budou moct stáhnout aplikaci Portál společnosti pro iOS z App Storu a podle pokynů v aplikaci si zařízení zaregistrovat.

## <a name="company-owned-ios-devices"></a>Zařízení s iOSem patřící společnosti
U organizací, které svým uživatelům zařízení pořizují, Intune podporuje následující způsoby registrace zařízení s iOSem patřící společnosti:

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
- Registrace pomocí Pomocníka s nastavením – obnoví tovární nastavení zařízení a připraví ho ke spuštění Pomocníka s nastavením a nainstaluje zásady společnosti pro nového uživatele zařízení.
- Přímá registrace – neobnoví tovární nastavení zařízení a zaregistruje ho s předdefinovanými zásadami. Tato metoda je vhodná pro zařízení bez přidružení uživatele.

Přečtěte si další informace o [registraci pomocí Apple Configuratoru](apple-configurator-setup-assistant-enroll-ios.md).
