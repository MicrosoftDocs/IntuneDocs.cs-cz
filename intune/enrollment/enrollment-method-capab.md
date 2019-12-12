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
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 11b93d41ac09f637d6c75a3f2f4b7f4213cecec7
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/05/2019
ms.locfileid: "74819761"
---
# <a name="intune-enrollment-method-capabilities-for-windows-devices"></a>Metoda možnosti registrace Intune pro zařízení s Windows
[!INCLUDE[azure_portal](../includes/azure_portal.md)]

Vaši pracovníci zařízení v Intune registrovat několika způsoby. Každá metoda má jiné osvědčené postupy a možnosti, jak je znázorněno v následujících tabulkách.

## <a name="best-practices-by-enrollment-method"></a>Osvědčené postupy podle metody registrace
| **Osvědčené postupy** | **[Připojené k Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Služba Azure AD připojená k autopilotu (režim založený na uživateli)](enrollment-autopilot.md)** |**[Služba Azure AD připojená k autopilotu (režim nasazení sami)](enrollment-autopilot.md)** |**[Hromadné](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[Uživatelé s vlastním zařízením (BYOD)](device-enrollment.md#bring-your-own-device)** | **[OBJEKT ZÁSAD SKUPINY](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Spoluspráva](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Běžně používané v EDU|![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Zařízení můžou sloužit jako sdílená zařízení.|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Osobní zařízení musí mít přístup k prostředkům společnosti.|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Samoobslužná údržba aplikací|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Možnosti podle metody registrace

| **Možnosti** | **[Připojené k Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Služba Azure AD připojená k autopilotu (režim založený na uživateli)](enrollment-autopilot.md)** |**[Služba Azure AD připojená k autopilotu (režim nasazení sami)](enrollment-autopilot.md)** |**[Hromadné](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[Uživatelé s vlastním zařízením (BYOD)](device-enrollment.md#bring-your-own-device)** | **[OBJEKT ZÁSAD SKUPINY](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Spoluspráva](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Conditional Access                                      |![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)\*\*|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|
|Uživatel je přidružený k zařízení.                    |![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|
|Vyžaduje Azure AD Premium.                               |![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|
|Zařízení můžete pracovat s prostředky chráněnými certifikační autoritou.             |![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|
|Uživatelé nesmí být správci na svých zařízeních.               |![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Schopnost konfigurace procesu nastavení zařízení        |![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Schopnost zaregistrovat zařízení bez zásahu uživatele      |![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|
|Schopnost spouštět powershellové skripty                       |![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/checkmark.png)\*| 
|Podporuje automatickou registraci po připojení k doméně AD.      |![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|
|Podporuje automatickou registraci po připojení k hybridní službě Azure AD.|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|
|Podporuje automatickou registraci po připojení ke službě Azure AD.       |![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![Značka zaškrtnutí](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|

\* úlohy klientských aplikací v Configuration Manager musíte přesunout do pilotního nasazení Intune nebo Intune.

[pro podmíněný přístup se zablokovala \** zařízení s výjimkou Windows 10 1803 +.](device-enrollment-manager-enroll.md)

## <a name="next-steps"></a>Další kroky

[Nastavení registrace pro Windows](windows-enroll.md)

