---
title: Nastavení beznabídkového režimu pro Windows Holographic for Business v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Vaše Windows Holographic for Business zařízení nakonfigurovat jako veřejné terminály jedné aplikace a s více aplikacemi, přizpůsobení nabídky start, přidejte aplikace, zobrazit na hlavním panelu a konfigurace webového prohlížeče v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.openlocfilehash: ae3672a913229b96198f64c5c587151745d5cf62
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831663"
---
# <a name="windows-holographic-for-business-device-settings-to-run-as-a-kiosk-in-intune"></a>Windows Holographic for Business nastavení zařízení pro spuštění jako veřejný terminál v Intune

Zařízení s Windows Holographic for Business můžete nakonfigurovat tak, aby se spouštěla v režimu veřejného terminálu s jednou aplikací, nebo v režimu veřejného terminálu s více aplikacemi. Některé funkce nejsou na zařízení s Windows Holographic for Business podporované.

Tento článek uvádí a popisuje různá nastavení, které můžete řídit na Windows Holographic for Business zařízení. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete nakonfigurovat váš Windows Holographic for Business zařízení v beznabídkovém režimu spouštět.

Jako správce Intune můžete vytvořit a přiřadit tato nastavení do zařízení.

Další informace o funkci Windows veřejného terminálu v Intune najdete v tématu [nakonfigurovat nastavení beznabídkového režimu](kiosk-settings.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvoření profilu](kiosk-settings.md#create-the-profile).

## <a name="single-full-screen-app-kiosks"></a>Veřejné terminály s jednou aplikací v režimu na celou obrazovku

Když zvolíte beznabídkový režim s jednou aplikací, zadejte následující nastavení:

- **Typ přihlášení uživatele**: Vyberte **místní uživatelský účet** zadat místní (pro zařízení) uživatelský účet nebo účet Microsoft (MSA) účet přidružený k aplikaci veřejného terminálu. Typy uživatelských účtů **Automatické přihlášení** nejsou na zařízení s Windows Holographic for Business podporované.

- **Typ aplikace**: Vyberte **Store app**.

- **Aplikace ale běží v beznabídkovém režimu**: Zvolte **přidání aplikace ze storu**a vyberte aplikaci ze seznamu.

    Nejsou v seznamu žádné aplikace? Přidejte aplikace pomocí postupu v části [Klientské aplikace](apps-add.md).

    Vyberte **OK** uložte provedené změny.

## <a name="multi-app-kiosks"></a>Veřejné terminály s více aplikacemi

Aplikace v tomto režimu jsou k dispozici v nabídce Start. Tyto aplikace jsou jedinými aplikacemi, které může uživatel spustit. Když zvolíte beznabídkový režim s více aplikacemi, zadejte následující nastavení:

- **Cíl v režimu zařízení S Windows 10**: Zvolte **ne**. Režim S není podporován na Windows Holographic for Business.

- **Typ přihlášení uživatele**: Přidejte jeden nebo více uživatelských účtů, které můžou používat aplikace, které přidáte. Možnosti: 

  - **Automatické přihlašování**: Nepodporované na Windows Holographic for Business.
  - **Místní uživatelské účty**: **Přidat** místním (zařízení) uživatelského účtu. Zadaný účet se používá pro přihlášení k veřejnému terminálu.
  - **Azure AD uživateli nebo skupině (Windows 10 verze 1803 nebo novější)**: Vyžaduje přihlašovací údaje uživatele pro přihlášení k zařízení. Vyberte **Přidat** a zvolte uživatele nebo skupiny Azure AD ze seznamu. Můžete vybrat více uživatelů a skupin. Zvolením možnosti **Vybrat** uložte změny.
  - **Návštěvník HoloLens**: Návštěvník účet je účet guest, který nevyžaduje žádné přihlašovací údaje uživatele nebo ověřování, jak je popsáno v [sdílí koncepty režimu PC](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Aplikace**: Přidání aplikací pro spuštění na zařízení beznabídkového režimu. Nezapomeňte, že můžete přidat několik aplikací.

  - **Přidání aplikací pro Store**: Vybrat existující aplikaci jste přidali pomocí [klientské aplikace](apps-add.md). Pokud nejsou zobrazené žádné aplikace, můžete je získat a [přidat do Intune](store-apps-windows.md).
  - **Přidat aplikaci Win32**: Nepodporované na Windows Holographic for Business.
  - **Přidejte podle AUMID**: Tuto možnost použijte k přidání aplikací pro Windows doručené pošty. Zadejte tyto vlastnosti: 

    - **Název aplikace**: Povinný parametr. Zadejte název aplikace.
    - **Uživatelské ID modelu aplikace (AUMID)**: Povinný parametr. Zadejte ID modelu uživatele aplikace (AUMID) aplikace pro Windows. Pokud chcete získat toto ID, přečtěte si článek o tom, [jak u nainstalované aplikace najít ID modelu uživatele aplikace](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Dlaždici velikost**: Povinný parametr. Zvolte velikost dlaždice aplikace – malá, střední, široká nebo velká.

- **Veřejný terminál, nastavení prohlížeče**: Nepodporované na Windows Holographic for Business.

- **Použití alternativní rozložení nabídky Start**: Zvolte **Ano** zadejte soubor XML, který popisuje, jak se mají aplikace zobrazit v nabídce start, včetně pořadí aplikace. Tuto možnost použijte, pokud v nabídce Start potřebujete větší míru přizpůsobení. V článku o [přizpůsobení a exportu rozložení nabídky Start](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) najdete pokyny a ukázkový soubor XML pro zařízení s Windows Holographic for Business.

- **Hlavním panelu Windows**: Nepodporované na Windows Holographic for Business.

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Můžete také vytvořit profily beznabídkového režimu pro [Android](device-restrictions-android.md#kiosk), [Androidu Enterprise](device-restrictions-android-for-work.md#kiosk-settings), a [Windows 10 a novější](kiosk-settings-windows.md) zařízení.