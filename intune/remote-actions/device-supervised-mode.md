---
title: Zapnutí režimu iOSu Pod dohledem v Microsoft Intune
titleSuffix: ''
description: Přečtěte si, jak lze zapnout režim iOSu Pod dohledem v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8190814-07f0-42d8-9b3a-87c67dd2b7ed
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 79e6ba1541a516b36ae4bd02cf9f60f1a12c8896
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732582"
---
# <a name="turn-on-ios-supervised-mode"></a>Zapnutí režimu iOSu Pod dohledem


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Režim Apple iOSu Pod dohledem poskytuje správcům při správě zařízení Apple další možnosti, které jsou užitečné u větších nasazení firemních zařízení. Můžete například omezit AirDrop nebo můžete uživatelům znemožnit změny názvu zařízení. Seznam nastavení vyžadujících režim Pod dohledem najdete v tématu [Nastavení omezení pro zařízení s iOSem v Intune](../configuration/device-restrictions-ios.md).

Intune podporuje režim Pod dohledem v rámci [Programu registrace zařízení Apple (DEP)](../enrollment/device-enrollment-program-enroll-ios.md).

Seznam ovládacích prvků Apple, které vyžadují dohled, najdete na webu společnosti Apple v [referenčních informacích o nastavení datové části](http://help.apple.com/configurator/mac/2.4/#/cad5370d089).

## <a name="turn-on-supervised-mode-during-enrollment"></a>Zapnutí režimu Pod dohledem během registrace

V Intune můžete zapnout režim Pod dohledem pro zařízení při [vytvoření registračního profilu v programu DEP](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile). V části **Nastavení správy zařízení** zaškrtněte políčko **Pod dohledem**.

## <a name="turn-on-supervised-mode-after-enrollment"></a>Zapnutí režimu Pod dohledem po registraci

Jediným způsobem, jak zapnout režim Pod dohledem po registraci, je připojit zařízení s iOSem k Macu a [použít Apple Configurator](../enrollment/apple-configurator-enroll-ios.md) (zařízení se tímto postupem resetuje). Po registraci není možné nakonfigurovat režim Pod dohledem pro zařízení v Intune.

## <a name="identify-a-supervised-device"></a>Zjištění, jestli je zařízení pod dohledem

Pokud chcete zjistit, jestli je zařízení pod dohledem, zkontrolujte zamykací obrazovku nebo stránku **Informace**:
- Na zamykací obrazovce zařízení bude sdělení **iPhone je ve správě organizace „název společnosti“.**
- Na stránce **o** zařízení bude **Tento iPhone pod dohledem. Název společnosti může sledovat internetový provoz a vyhledat toto zařízení.**

## <a name="next-steps"></a>Další kroky

Další možnosti správy zařízení najdete v tématu [Co je správa zařízení v Microsoft Intune](device-management.md).
