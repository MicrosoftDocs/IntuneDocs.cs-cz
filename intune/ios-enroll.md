---
title: "Volba způsobu registrace zařízení s Windows v Intune"
titleSuffix: Intune on Azure
description: "Přečtěte si, jak nastavit registraci zařízení s Windows v Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61bdbc7ca68995e23295cf099ce73dfdcaeba37c
ms.sourcegitcommit: 5eb209ae48173ddfdbbab131f12f3ac3498dcd87
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/18/2017
---
# <a name="enroll-ios-devices-in-intune"></a>Registrace zařízení s iOSem v Intune

Intune umožňuje správu mobilních zařízení (MDM) u iPadů a iPhonů, aby mohli jejich uživatelé získat přístup k firemnímu e-mailu a aplikacím.

Jako správce Intune můžete povolit registraci zařízení s iOSem. Můžete uživatelům povolit registraci osobních zařízení, která se označuje jako registrace BYOD (přineste si vlastní zařízení). Můžete povolit také registraci zařízení vlastněných firmou.

## <a name="prerequisites-for-ios-enrollment"></a>Předpoklady pro registraci zařízení s iOSem
Před povolením zařízení s iOSem proveďte následující kroky:
- [Nastavení Intune](setup-steps.md) – tento postup slouží k nastavení infrastruktury Intune. Registrace zařízení vyžaduje zejména [nastavení autority MDM](mdm-authority-set.md).
- [Získání certifikátu Apple MDM Push Certificate](apple-mdm-push-certificate-get.md) – Apple vyžaduje k povolení správy zařízení s iOSem a macOS certifikát.

Po splnění těchto předpokladů si uživatelé mohou nainstalovat aplikaci Portál společnosti, aby mohli zaregistrovat svá osobní zařízení s iOSem. Správce také může nastavit správu zařízení s iOSem patřících společnosti. Správci mohou přiřadit také [správce registrace zařízení](device-enrollment-manager-enroll.md), kteří můžou zaregistrovat velký počet zařízení s jediným účtem správy. Intune podporuje následující způsoby registrace zařízení s iOSem vlastněných společností:

## <a name="device-enrollment-program"></a>Program DEP (Device Enrollment Program)
Organizace můžou nakupovat zařízení s iOSem prostřednictvím Programu registrace zařízení (DEP) společnosti Apple. Program DEP umožňuje vzdáleně (bezdrátově) nasadit registrační profil, který umožní správu těchto zařízení. Přečtěte si další informace o [Programu registrace zařízení](device-enrollment-program-enroll-ios.md).

## <a name="apple-school-manager"></a>Apple School Manager
Apple School Manager je program nákupu a registrace zařízení pro školy. Stejně jako u programu DEP máte možnost nasadit profil pro registraci zařízení pro účely správy. Další informace o [Apple School Manageru](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Apple Configurator
Zařízení s iOSem můžete zaregistrovat pomocí nástroje Apple Configurator spuštěného na počítači Mac. Zařízení připravíte tak, že je připojíte přes USB a nainstalujete registrační profil. Zařízení můžete pomocí Apple Configuratoru registrovat dvěma způsoby:
- Registrace pomocí Pomocníka s nastavením – obnoví tovární nastavení zařízení a připraví ho ke spuštění Pomocníka s nastavením a nainstaluje zásady společnosti pro nového uživatele zařízení.
- Přímá registrace – neobnoví tovární nastavení zařízení a zaregistruje ho s předdefinovanými zásadami. Tato metoda je vhodná pro zařízení bez přidružení uživatele.

Přečtěte si další informace o [registraci pomocí Apple Configuratoru](apple-configurator-setup-assistant-enroll-ios.md).
