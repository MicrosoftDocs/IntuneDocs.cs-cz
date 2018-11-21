---
title: Možnosti Intune podle metody registrace pro zařízení s Windows
titlesuffix: Microsoft Intune
description: Podívejte se na možnosti, které každá metoda registrace podporuje pro zařízení s Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 38bb88015261aa50d6c27aec026614f1205aebe8
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189805"
---
# <a name="capabilities-by-enrollment-method-for-windows-devices"></a>Možnosti podle metody registrace pro zařízení s Windows
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune umožňuje spravovat zařízení a aplikace vašich zaměstnanců a způsob, jakým přistupují k firemním datům. Zařízení musí být nejprve registrovaná ve službě Intune. Zařízení pracovníků lze registrovat několika způsoby. Každá metoda má jiné osvědčené postupy a možnosti, jak je znázorněno v následujících tabulkách.

## <a name="best-practices-by-enrollment-method"></a>Osvědčené postupy podle metody registrace
| **Osvědčené postupy** | **[Připojené k Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Připojené k Azure AD s Autopilotem](enrollment-autopilot.md)** |**[Hromadné](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[Uživatelé s vlastním zařízením (BYOD)](device-enrollment.md#bring-your-own-device)** | **[OBJEKT ZÁSAD SKUPINY](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Běžně používané v EDU|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Zařízení můžou sloužit jako sdílená zařízení.|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Osobní zařízení musí mít přístup k prostředkům společnosti.|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|
|Samoobslužná údržba aplikací|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Možnosti podle metody registrace

| **Možnosti** | **[Připojené k Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Připojené k Azure AD s Autopilotem](enrollment-autopilot.md)** |**[Hromadné](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[Uživatelé s vlastním zařízením (BYOD)](device-enrollment.md#bring-your-own-device)** | **[OBJEKT ZÁSAD SKUPINY](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|podmíněný přístup                                      |![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Uživatel je přidružený k zařízení.                    |![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Vyžaduje Azure AD Premium.                               |![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Zařízení můžete pracovat s prostředky chráněnými certifikační autoritou.             |![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Uživatelé nesmí být správci na svých zařízeních.               |![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Schopnost konfigurace procesu nastavení zařízení        |![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Schopnost zaregistrovat zařízení bez zásahu uživatele      |![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Schopnost spouštět powershellové skripty                       |![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)| 
|Podporuje automatickou registraci po připojení k doméně AD.      |![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Podporuje automatickou registraci po připojení k hybridní službě Azure AD.|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Značka zaškrtnutí](media/checkmark.png)|
|Podporuje automatickou registraci po připojení ke službě Azure AD.       |![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![Značka zaškrtnutí](media/checkmark.png)|![X](media/xmark.png)|

## <a name="next-steps"></a>Další postup

[Nastavení registrace pro Windows ](windows-enroll.md)

