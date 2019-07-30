---
title: Nastavení vzdělávání pro Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na seznam všech nastavení vzdělávání pro zařízení s Windows 10. Tato nastavení použijte v profilu konfigurace zařízení pomocí aplikace vzít si test, vyberte, jak se uživatelé nebo studenti přihlásí, monitorovat obrazovku během testu a další v Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d5c78f72e7ffc580cce6cfec7237a3efe3ceb3e5
ms.sourcegitcommit: fd2499df5123758ecb093b4cdd486e35f713b040
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/16/2019
ms.locfileid: "68230105"
---
# <a name="configure-the-take-a-test-app-on-windows-10-devices-using-intune"></a>Konfigurace aplikace pořizovat test na zařízeních s Windows 10 pomocí Intune

V tomto článku se dozvíte, jak se ve Microsoft Intune vzdělávání pořídit nastavení testovací aplikace, která můžete nakonfigurovat na zařízeních s Windows 10 a novějším. Pomocí této aplikace se studenti můžou přihlásit k zařízení a provést test.

Tato nastavení se přidají do konfiguračního profilu zařízení a pak se přiřadí nebo nasadí do zařízení pomocí Microsoft Intune.

Pokud chcete získat další informace o této funkci, [Vyzkoušejte si testovací aplikaci v Intune](education-settings-configure.md) .

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](education-settings-configure.md#create-a-device-profile).

## <a name="take-a-test-settings"></a>Provést nastavení testu  

- **Typ účtu**: Vyberte způsob, jakým se uživatelé přihlásí k testu. Možnosti:
  - Účet Azure AD
  - Účet domény
  - Místní účet
- **Uživatelské jméno účtu**: Zadejte uživatelské jméno účtu, který se používá v aplikaci pořizovat test. Účty můžete zadat v následujícím formátu:
  - `user@contoso.com`
  - `domain\username`
  - `user@contoso.com`
  - `computerName\username`
- **Adresa URL pro vyhodnocení**: Zadejte adresu URL testu, který mají uživatelé provést. Další informace o získání adresy URL najdete v dokumentaci k [provedení testu](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).
- **Sledování obrazovky**: Chcete-li monitorovat aktivitu obrazovky, zatímco uživatelé probíhají testy, vyberte možnost **povoleno** . **Není nakonfigurované** , znemožní vám monitorovat obrazovku během testu.
- **Návrh textu**: Vyberte možnost **umožnit** , takže test uživatelé vyplňující může zobrazit návrhy textu. Nenakonfigurované návrhy textu bloků, zatímco uživatelé probíhají test.

## <a name="next-steps"></a>Další postup

Profil se vytvoří, ale nemusí ještě nic dělat. Nezapomeňte [profil přiřadit](device-profile-assign.md)a [monitorovat jeho stav](device-profile-monitor.md).
