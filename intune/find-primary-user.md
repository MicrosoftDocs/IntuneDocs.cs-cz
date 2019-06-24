---
title: Najdete primární uživatele zařízení v Microsoft Intune.
titleSuffix: ''
description: Najdete primární uživatele (nebo spřažení zařízení a uživatele) zařízení s Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b6a20ccec2ef0cbaba87637b3c44c2cc2be094ab
ms.sourcegitcommit: b3a1c5b0b24f0e52cf318defe10f3d27a2770009
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/21/2019
ms.locfileid: "67322871"
---
# <a name="find-the-primary-user-of-an-intune-device"></a>Najít primární uživatele zařízení s Intune

Primární uživatel, označované také jako spřažení uživatelských zařízení, je vlastnost každého zařízení v Intune. Zařízení s Intune může mít žádnou nebo jednu primární uživatele, které jsou přiřazeny k němu. Pokud neexistuje žádný primární uživatel přiřazen, zařízení se označuje jako "Sdílených zařízení".

## <a name="how-to-find-a-devices-primary-user"></a>Jak najít primární uživatele zařízení

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Zvolte **zařízení** > zvolte zařízení.
3. Na **přehled** zvolte **zobrazit další** a zobrazí se vám primárního uživatele uvedené.

## <a name="what-is-the-primary-user"></a>Co je primárním uživatelem?
Vlastnost primárního uživatele se používá k mapování licencovaného uživatele Intune se svými zařízeními v:
- Aplikace portál společnosti
- Koncový uživatel webu
- IT pro prostředí, jako je řešení potíží s stránky na webu Azure Portal. Tyto stránky Mapování uživatelských účtů na zařízení s využitím primárního uživatele.    

### <a name="company-portal-app"></a>Aplikace Portál společnosti
Aplikace portál společnosti očekává, že uživatelský účet, přihlášení k portálu společnosti je primárními uživateli tohoto zařízení. Pokud se jiný uživatel byl přiřazen jako primární uživatele na portálu společnosti se zobrazí upozornění:

"Toto zařízení je už přiřazený k někdo ve vaší organizaci. Kontaktujte firemní podporu o tom, jak primární zařízení uživatele. Můžete dál používat portál společnosti ale funkce budou omezené."

Pokud zařízení s Intune bez primárního uživatele přiřazeny, pak na aplikaci portál společnosti rozpozná jako sdílená zařízení. Sdílená zařízení jsou vizuálně identifikovat s popiskem "sdílené" povolí, na dlaždici dodržování. V tomto režimu portál společnosti stále umožňuje vyžádat a instalovat dostupné aplikace. Samoobslužné služby akce (obnovení a přejmenování nebo vyřazení z provozu) však nejsou k dispozici.  

Zobrazí v aplikaci portál společnosti na sdílených zařízeních, musí mít k dispozici aplikace přiřazenou pro skupinu uživatelů. Budete mít nainstalované v kontextu systému nebo v kontextu uživatele, v závislosti na konfiguraci aplikace správce IT. Další informace o kontextu aplikací, najdete v části [instalace aplikací na zařízeních s Windows 10](apps-windows-10-app-deploy.md#installing-apps-on-windows-10-devices). Verze 10.3.4651.0 portál společnosti nebo novější je nutné tuto funkci používat.


## <a name="who-is-assigned-as-the-primary-user"></a>Kdo je přiřazen jako primární uživatele?
Primární uživatel Intune automaticky přidá do zařízení, během nebo krátce po zápisu. Metodu registrace určuje při přidání primárního uživatele zařízení.

| Platforma | Způsob registrace | Primární uživatel přiřazený | Primární uživatel |
| ---- | ---- | ---- | ---- |
| Windows | Přidat pracovní nebo školní (user driven) | Registrace uživatele | Během registrace |   
| Windows | Moderní aplikace přihlášení (user driven) | Registrace uživatele | Během registrace | 
| Windows | Registrace ve správě mobilních zařízení jenom (user driven) | Registrace uživatele | Během registrace | 
| Windows | Připojení k Azure AD (mimo prostředí) | Registrace uživatele | Během registrace | 
| Windows | Připojení ke službě Azure AD (Autopilot mimo prostředí) | Registrace uživatele | Během registrace | 
| Windows | Pouze registrace v MDM | Registrace uživatele | Během registrace | 
| Windows | Hybridní AADJ + Automatická registrace do objektu zásad skupiny | První uživatel přihlásil | Při prvním přihlášení | 
| Windows | Společná správa | První uživatel přihlásil | Při prvním přihlášení | 
| Windows | Připojení ke službě Azure AD (hromadný token pro zápis) | Žádné | Nelze použít | 
| Windows | Připojení ke službě Azure AD (místním nasazení Autopilot režim) | Žádné | Nelze použít | 
| Různé platformy | Registrace uživatele řízený testy s aplikací portál společnosti | Registrace uživatele | Během registrace |
| Různé platformy | Správce registrace zařízení (DEM) | Registrace uživatele DEM | Během registrace |
| iOS, macOS | Apple automatické registrace zařízení (DEP s přidružením uživatele | Registrace uživatele | Během registrace |
| iOS, macOS | Apple automatické registrace zařízení (DEP bez přidružení uživatele) | Žádné | Nelze použít |
| Android | Vlastněné podniková, vyhrazená zařízení s androidem | Žádné | Nelze použít |

## <a name="primary-user-and-azure-ad-device-owner"></a>Primární uživatel a vlastník zařízení Azure AD
V některých případech může být primárního uživatele Intune liší od Azure AD Device **vlastníka** vlastnosti (zobrazitelné v rámci **zařízení** > **podpora k zařízením Azure AD**). Vlastník zařízení služby Azure AD se přidá během registrace zařízení do služby Azure Active Directory.

## <a name="next-steps"></a>Další postup
[Spravujte vaše zařízení v Intune.](device-management.md)
