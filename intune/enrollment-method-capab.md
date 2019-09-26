---
title: Metoda možnosti registrace Intune pro zařízení s Windows
titleSuffix: Microsoft Intune
description: Možnosti pro jednotlivé metody registrace pro zařízení s Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2b9c427cb019093bdfbf9fe27bbf3b05a48ef6d8
ms.sourcegitcommit: bc3450fc7f19006b500edf5b395c01559b483ea4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/02/2019
ms.locfileid: "71301989"
---
# <a name="intune-enrollment-method-capabilities-for-windows-devices"></a>Metoda možnosti registrace Intune pro zařízení s Windows
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Vaši pracovníci zařízení v Intune registrovat několika způsoby. Každá metoda má jiné osvědčené postupy a možnosti, jak je znázorněno v následujících tabulkách.

## <a name="best-practices-by-enrollment-method"></a>Osvědčené postupy podle metody registrace
| **Osvědčené postupy** | **[Připojené k Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Služba Azure AD připojená k autopilotu (režim založený na uživateli)](enrollment-autopilot.md)** |**[Služba Azure AD připojená k autopilotu (režim nasazení sami)](enrollment-autopilot.md)** |**[Hromadné](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[Uživatelé s vlastním zařízením (BYOD)](device-enrollment.md#bring-your-own-device)** | **[OBJEKT ZÁSAD SKUPINY](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Spoluspráva](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Běžně používané v EDU|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Zařízení můžou sloužit jako sdílená zařízení.|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Osobní zařízení musí mít přístup k prostředkům společnosti.|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Samoobslužná údržba aplikací|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Možnosti podle metody registrace

| **Možnosti** | **[Připojené k Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Služba Azure AD připojená k autopilotu (režim založený na uživateli)](enrollment-autopilot.md)** |**[Služba Azure AD připojená k autopilotu (režim nasazení sami)](enrollment-autopilot.md)** |**[Hromadné](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[Uživatelé s vlastním zařízením (BYOD)](device-enrollment.md#bring-your-own-device)** | **[OBJEKT ZÁSAD SKUPINY](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Spoluspráva](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Podmíněný přístup                                      |![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Uživatel je přidružený k zařízení.                    |![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Vyžaduje Azure AD Premium.                               |![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Zařízení můžete pracovat s prostředky chráněnými certifikační autoritou.             |![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Uživatelé nesmí být správci na svých zařízeních.               |![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Schopnost konfigurace procesu nastavení zařízení        |![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Schopnost zaregistrovat zařízení bez zásahu uživatele      |![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Schopnost spouštět powershellové skripty                       |![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/checkmark.png)\*| 
|Podporuje automatickou registraci po připojení k doméně AD.      |![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Podporuje automatickou registraci po připojení k hybridní službě Azure AD.|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Podporuje automatickou registraci po připojení ke službě Azure AD.       |![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|

\*Úlohy klientských aplikací v Configuration Manager musí být přesunuté do pilotního nasazení Intune nebo do Intune.

## <a name="next-steps"></a>Další kroky

[Nastavení registrace pro Windows](windows-enroll.md)

