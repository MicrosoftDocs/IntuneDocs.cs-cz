---
title: "Volba způsobu registrace zařízení s iOSem v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si, jak nastavit registraci zařízení se systémem iOS v Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ee0ecf26a333ec441eb95e79473a9bf405e4120c
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="choose-how-to-enroll-ios-devices"></a>Volba způsobu registrace zařízení se systémem iOS

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Toto téma popisuje metody, které se dají použít k registraci zařízení se systémem iOS, a předpoklady pro registraci.

S použitím následujících informací rozhodněte, která metoda se má použít pro zaregistrování zařízení se systémem iOS. Všechny následující metody, s výjimkou použití vlastních zařízení (BYOD), jsou určené pro registraci zařízení vlastněných firmami.

**Předpoklad:** Je vyžadován [certifikát služby Apple Push Notification](apple-mdm-push-certificate-get.md).

## <a name="user-owned-ios-devices-byod"></a>Zařízení se systémem iOS vlastněné uživatelem (BYOD)

Pokud si chtějí uživatelé zaregistrovat svoje vlastní zařízení (BYOD), je jediná možnost, jak si svoje zařízení můžou zaregistrovat, stažení aplikace Portál společnosti pro iOS z obchodu s aplikacemi. Dále je potřeba postupovat podle pokynů v aplikaci. Po registraci se uživatelé můžou připojit k síti společnosti, k doméně nebo Azure Active Directory a získat přístup k podnikovým prostředkům. Registraci osobně vlastněných zařízení s iOSem je možné blokovat. Pokyny najdete v tématu [Nastavení omezení typu zařízení](enrollment-restrictions-set.md#set-device-type-restrictions).

## <a name="apple-configurator"></a>Apple Configurator

Zařízení se systémem iOS můžete registrovat na základě exportu podnikového registračního profilu a následného připojení těchto mobilních zařízení k počítači Mac, na kterém běží [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017). Apple Configurator podporuje dva způsoby registrace:

- **Registrace pomocí Pomocníka s nastavením:** Obnoví tovární nastavení a připraví zařízení k nastavení jeho novým uživatelem. Tato metoda vyžaduje, aby správce pomocí USB připojil zařízení se systémem iOS k počítači Mac, na kterém je spuštěný Apple Configurator, a předem nakonfiguroval registraci. Zařízení se pak doručí jejich uživatelům, kteří spustí proces Pomocníka s nastavením. Tento proces v zařízení nakonfiguruje pracovní nebo školní přihlašovací údaje uživatele a dokončí proces registrace. Další informace najdete v tématu [Registrace zařízení se systémem iOS pomocí Apple Configuratoru a Pomocníka s nastavením](apple-configurator-setup-assistant-enroll-ios.md).

- **Přímá registrace**: Vytvoří soubor kompatibilní s nástrojem Apple Configurator, který můžete použít při přípravě zařízení. U zaregistrovaného zařízení se neobnoví tovární nastavení a zařízení nemá žádného přiřazeného uživatele. Aby bylo možné zaregistrovat zařízení, je potřeba, aby správce připojil zařízení se systémem iOS kabelem USB k počítači Mac, na kterém je spuštěný Apple Configurator. Další informace najdete v článku [Registrace zařízení s iOSem pomocí přímé registrace nástroje Apple Configurator](apple-configurator-direct-enroll-ios.md).

## <a name="use-the-device-enrollment-program-dep"></a>Použití Programu registrace zařízení (DEP)

DEP nasazuje registrační profil bezdrátově do zařízení, která jste prostřednictvím tohoto programu nakoupili. Když uživatel na zařízení spustí Pomocníka s nastavením, zařízení se zaregistruje do Intune. U zařízení zaregistrovaných prostřednictvím Programu registrace zařízení nemůžou uživatelé registraci zrušit. Další informace najdete v tématu [Registrace zařízení se systémem iOS pomocí Programu registrace zařízení](device-enrollment-program-enroll-ios.md).

## <a name="use-the-device-enrollment-manager-dem"></a>Použití správce registrace zařízení (DEM)
Správce registrace zařízení je typ uživatelského účtu, který může zaregistrovat a spravovat až 1000 zařízení. Do účtu DEM přidáte existující uživatele a přidělíte jim tak příslušné možnosti. Každé zařízení, které uživatel DEM zaregistruje, používá jednu licenci Intune. Další informace najdete v tématu [Registrace zařízení pomocí správce registrace zařízení](device-enrollment-manager-enroll.md).

