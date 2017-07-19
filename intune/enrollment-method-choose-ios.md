---
title: "Volba způsobu registrace zařízení s iOSem v Intune"
titleSuffix: Intune on Azure
description: "Přečtěte si, jak nastavit registraci zařízení s iOSem v Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 092f582cf30210858bd8cdd3879edfa873523ccb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="choose-how-to-enroll-ios-and-macos-devices"></a>Volba způsobu registrace zařízení se systémy iOS a macOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Toto téma popisuje metody, kterými může správce IT povolit registraci zařízení s iOSem v Intune.

S použitím následujících informací rozhodněte, která metoda se má použít pro zaregistrování zařízení se systémem iOS. Všechny následující metody, s výjimkou použití vlastních zařízení (BYOD), jsou určené pro registraci zařízení vlastněných firmami.

**Předpoklad:** Je vyžadován [certifikát služby Apple Push Notification](apple-mdm-push-certificate-get.md).

## <a name="user-owned-ios-devices-byod"></a>Zařízení se systémem iOS vlastněné uživatelem (BYOD)

Pokud si chtějí uživatelé zaregistrovat svoje vlastní zařízení (BYOD), můžou si stáhnout aplikaci Portál společnosti pro iOS z App Storu a postupovat podle pokynů pro registraci v této aplikaci. Po registraci se uživatelé můžou připojit k síti společnosti, k doméně nebo Azure Active Directory a získat přístup k podnikovým prostředkům. Jediným požadavkem pro povolení vlastních zařízení uživatelů (BYOD) je [certifikát služby Apple Push Notification](apple-mdm-push-certificate-get.md). Registraci osobně vlastněných zařízení s iOSem je možné také blokovat. Pokyny najdete v tématu [Nastavení omezení typu zařízení](enrollment-restrictions-set.md).

## <a name="user-owned-macos-devices-byod"></a>Zařízení se systémem macOS vlastněná uživatelem (BYOD)

Registraci zařízení se systémem macOS můžete povolit. Jediným požadavkem pro povolení registrace zařízení se systémem macOS je [certifikát služby Apple Push Notification](apple-mdm-push-certificate-get.md). Další informace najdete v tématu [Registrace zařízení se systémem macOS](./macos-enroll.md).

## <a name="enrollment-program-with-apple"></a>Program registrace přes Apple
Apple nabízí programy pro zakoupení zařízení, které zahrnují infrastrukturu pro registraci a správu zařízení. Zařízení zakoupená prostřednictvím některého z těchto programů můžete bezdrátově hromadně zaregistrovat přiřazením sériových čísel zařízení pro správu Intune.

- **Program registrace zařízení (DEP)** – program registrace zařízení Apple pro organizace a podniky. Další informace najdete v tématu [Registrace zařízení se systémem iOS pomocí Programu registrace zařízení](device-enrollment-program-enroll-ios.md).
- **Apple School Manager** – program registrace zařízení Apple pro školy. Další informace najdete v tématu [Povolení registrace zařízení s iOSem pomocí Apple School Manageru](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Apple Configurator

Zařízení s iOSem můžete registrovat exportováním podnikového registračního profilu a následným připojením těchto mobilních zařízení k počítači Mac, na které běží nástroj Apple Configurator. Apple Configurator podporuje dva způsoby registrace:

- **Registrace pomocí Pomocníka s nastavením:** Obnoví tovární nastavení a připraví zařízení k nastavení jeho novým uživatelem. Tato metoda vyžaduje, aby správce pomocí USB připojil zařízení se systémem iOS k počítači Mac, na kterém je spuštěný Apple Configurator, a předem nakonfiguroval registraci. Zařízení se pak doručí jejich uživatelům, kteří při prvním spuštění zařízení spustí Pomocníka s nastavením. Tento proces v zařízení nakonfiguruje pracovní nebo školní přihlašovací údaje uživatele a dokončí proces registrace. Další informace najdete v tématu [Registrace zařízení se systémem iOS pomocí Apple Configuratoru a Pomocníka s nastavením](apple-configurator-setup-assistant-enroll-ios.md).

- **Přímá registrace**: Vytvoří soubor kompatibilní s nástrojem Apple Configurator, který můžete použít při přípravě zařízení. U zaregistrovaného zařízení se neobnoví tovární nastavení a zařízení nemá žádného přiřazeného uživatele. Aby bylo možné zaregistrovat zařízení, je potřeba, aby správce připojil zařízení se systémem iOS kabelem USB k počítači Mac, na kterém je spuštěný Apple Configurator. Další informace najdete v článku [Registrace zařízení s iOSem pomocí přímé registrace nástroje Apple Configurator](apple-configurator-direct-enroll-ios.md).

## <a name="use-the-device-enrollment-program-dep"></a>Použití Programu registrace zařízení (DEP)

DEP nasazuje registrační profil bezdrátově do zařízení, která jste prostřednictvím tohoto programu nakoupili. Když uživatel na zařízení při prvním spuštění spustí Pomocníka s nastavením, zařízení se zaregistruje do Intune. Další informace najdete v tématu [Registrace zařízení se systémem iOS pomocí Programu registrace zařízení](device-enrollment-program-enroll-ios.md).

## <a name="use-the-device-enrollment-manager-dem"></a>Použití správce registrace zařízení (DEM)
Správce registrace zařízení je obecný uživatelský účet, který může zaregistrovat a spravovat až 1 000 zařízení. Zařízení spravovaná pomocí DEM nemůžou mít přidružení uživatele, takže zařízení nemá žádného vlastníka. Uživatelům Intune poskytujete oprávnění DEM, která jim dávají tyto možnosti. Každé zařízení, které uživatel DEM zaregistruje, používá licenci Intune. Další informace najdete v tématu [Registrace zařízení pomocí správce registrace zařízení](device-enrollment-manager-enroll.md).
