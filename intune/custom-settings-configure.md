---
title: Používání vlastního nastavení zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Přidejte nebo vytvořte profil, abyste mohli v Microsoft Intune použít vlastní nastavení zařízení se systémy Windows Phone, Windows 8.1, Windows 10 a novějšími, Android, Anndroid Enterprise, macOS a iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9dd1ea3b6365cd93d7df78597a2e379ebaec7103
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55836366"
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Vytvoření profilu s vlastním nastavením v Intune

## <a name="what-are-custom-profiles"></a>Co jsou vlastní profily?

Microsoft Intune obsahuje řadu integrovaných nastavení, které umožňují ovládat různé funkce zařízení. Můžete také vytvářet vlastní profily. Vlastní profily jsou praktické, když chcete použít nastavení a funkce zařízení, která nejsou integrovaná do Intune. Tyto profily obsahují funkce a nastavení, která chcete ovládat na zařízeních v organizaci. Můžete třeba vytvořit vlastní profil, který nastaví stejnou funkci u každého zařízení s iOSem.

Další informace o konfiguračních profilech najdete v tématu [Co jsou profily zařízení v Microsoft Intune?](device-profiles.md) 

V tomto článku najdete odkazy na vytvoření vlastních profilů pro Android, Android Enterprise, iOS, macOS a Windows.

## <a name="available-platforms"></a>Dostupné platformy

Vlastní nastavení se konfigurují pro každou platformu jinak. Třeba k ovládání funkcí na zařízeních s Androidem a Windows můžete zadat hodnoty OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Do zařízení Apple můžete importovat soubor vytvořený v [Apple Configuratoru](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) nebo v [Apple Profile Manageru](https://support.apple.com/profile-manager).

Vlastní profily se vytvářejí podobně jako integrované profily a jsou dostupné pro následující platformy:

- [Android](custom-settings-android.md)
- [Android Enterprise](custom-settings-android-for-work.md)
- [iOS](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)

## <a name="next-steps"></a>Další postup

Začněte výběrem platformy:

- [Android](custom-settings-android.md)
- [Android Enterprise](custom-settings-android-for-work.md)
- [iOS](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
