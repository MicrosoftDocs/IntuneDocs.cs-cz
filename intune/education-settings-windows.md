---
title: Nastavení vzdělávání pro Windows 10 v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Zobrazit seznam všech nastavení vzdělávání pro zařízení s Windows 10. Pomocí těchto nastavení v profilu konfigurace zařízení s zkuste aplikace pro testy, zvolte uživatele nebo studenty registrace v programu sledování obrazovky během testu a více v Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ae26d35a50ffd2b5b40f262ddebeab8d53d87223
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55846685"
---
# <a name="configure-the-take-a-test-app-on-windows-10-devices-using-intune"></a>Na zařízeních s Windows 10 pomocí Intune nakonfigurovat aplikaci zkuste si Test

V tomto článku se dozvíte vše Microsoft Intune education využít testovací aplikace nastavení, která můžete konfigurovat v zařízeních s Windows 10 a novější. Použití této aplikace, studenty můžete přihlásit k zařízení a zkuste si test.

Tato nastavení jsou přidány do konfiguračního profilu zařízení a potom přiřazené nebo nasazené do zařízení pomocí Microsoft Intune.

[Provést Test aplikace v Intune](education-settings-configure.md) poskytuje další informace o této funkci.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](education-settings-configure.md#create-a-device-profile).

## <a name="take-a-test-settings"></a>Zkuste si test nastavení

- **Typ účtu**: Zvolte, jak se uživatelé přihlašují k testu. Možnosti:
  - Účet Azure AD
  - Účet domény
  - Místní účet
- **Uživatelské jméno účtu**: Zadejte uživatele použít název účtu se zkuste aplikaci Test. Účty můžete zadat v následujícím formátu:
  - `user@contoso.com`
  - `domain\username`
  - `user@contoso.com`
  - `computerName\username`
- **Adresa URL hodnocení**: Zadejte adresu URL testu, který mají uživatelé absolvovat. Další informace o získání adresy URL, najdete v článku [trvat dokumentace k testování](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).
- **Monitorování obrazovky**: Zvolte **povolit** monitorování obrazovky, když uživatelé absolvují test. **Není nakonfigurováno** brání monitorování obrazovky během testu.
- **Návrh textu**: Zvolte **povolit** tak uživatelům vyplňujícím testu můžete zobrazit textové návrhy. **Není nakonfigurováno** blokovat textové návrhy, zatímco uživatelé absolvují test.

## <a name="next-steps"></a>Další postup

Vytvoření profilu, ale to nemusí být teď zrovna nic nedělá ještě. Nezapomeňte [přiřadit profil](device-profile-assign.md), a [monitorování jejího stavu](device-profile-monitor.md).