---
title: Metoda možnosti registrace Intune pro zařízení s Windows
titlesuffix: Microsoft Intune
description: Možnosti pro jednotlivé metody registrace pro zařízení s Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e6f3db2034bdc71e656f468913394baf455d47e8
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57528237"
---
# <a name="intune-enrollment-method-capabilities-for-windows-devices"></a>Metoda možnosti registrace Intune pro zařízení s Windows
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Vaši pracovníci zařízení v Intune registrovat několika způsoby. Každá metoda má jiné osvědčené postupy a možnosti, jak je znázorněno v následujících tabulkách.

## <a name="best-practices-by-enrollment-method"></a>Osvědčené postupy podle metody registrace
| **Osvědčené postupy** | **[Připojené k Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Připojená k Azure AD s Autopilot (User driven režim)](enrollment-autopilot.md)** |**[Připojená k Azure AD s Autopilot (vlastní nasazení režimu)](enrollment-autopilot.md)** |**[Hromadné](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[Uživatelé s vlastním zařízením (BYOD)](device-enrollment.md#bring-your-own-device)** | **[OBJEKT ZÁSAD SKUPINY](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Co-management](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Běžně používané v EDU|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Zařízení můžou sloužit jako sdílená zařízení.|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Osobní zařízení musí mít přístup k prostředkům společnosti.|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Samoobslužná údržba aplikací|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Možnosti podle metody registrace

| **Možnosti** | **[Připojené k Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Připojená k Azure AD s Autopilot (User driven režim)](enrollment-autopilot.md)** |**[Připojená k Azure AD s Autopilot (vlastní nasazení režimu)](enrollment-autopilot.md)** |**[Hromadné](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[Uživatelé s vlastním zařízením (BYOD)](device-enrollment.md#bring-your-own-device)** | **[OBJEKT ZÁSAD SKUPINY](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Co-management](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|podmíněný přístup                                      |![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Uživatel je přidružený k zařízení.                    |![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Vyžaduje Azure AD Premium.                               |![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Zařízení můžete pracovat s prostředky chráněnými certifikační autoritou.             |![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Uživatelé nesmí být správci na svých zařízeních.               |![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Schopnost konfigurace procesu nastavení zařízení        |![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Schopnost zaregistrovat zařízení bez zásahu uživatele      |![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Schopnost spouštět powershellové skripty                       |![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)| 
|Podporuje automatickou registraci po připojení k doméně AD.      |![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Podporuje automatickou registraci po připojení k hybridní službě Azure AD.|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Podporuje automatickou registraci po připojení ke službě Azure AD.       |![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|

## <a name="next-steps"></a>Další postup

[Nastavení registrace pro Windows ](windows-enroll.md)

