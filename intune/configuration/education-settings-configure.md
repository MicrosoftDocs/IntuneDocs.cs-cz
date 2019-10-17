---
title: Přidání nebo konfigurace nastavení vzdělávání v Microsoft Intune – Azure | Microsoft Docs
description: Použijte aplikaci pořizovat test v profilu konfigurace zařízení v zařízení s Windows 10 a novějším v Microsoft Intune. Vytvořte konfigurační profil pomocí nastavení vzdělávání a zadejte adresu URL testovací aplikace, vyberte způsob, jakým se uživatelé přihlásí, monitorovat obrazovku během testu a při testování povolí nebo zakáže návrhy textu.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/10/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f78c628498624b62daf6c3ac597547851697c500
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72493333"
---
# <a name="use-the-take-a-test-app-on-windows-10-devices-in-microsoft-intune"></a>Použití aplikace nabrat na zařízeních s Windows 10 v Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Vzdělávací profily v Intune jsou navržené pro studenty, kteří můžou na zařízeních pořizovat test nebo zkoušku. Tato funkce **zahrnuje testovací URL aplikaci a** nastavení, které umožňují přidat testovací adresu URL, zvolit způsob, jakým se koncoví uživatelé přihlásí k testu, a další. Tato funkce podporuje následující platformu:

- Windows 10 a novější

Když se uživatel přihlásí, automaticky se otevře testovací aplikace se zadaným testem. V zařízení nemůžou běžet žádné jiné aplikace, zatímco probíhá test. [Pořizovat testy ve Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10) poskytují další podrobnosti o aplikaci převzít test.

V tomto článku jsou uvedené kroky pro vytvoření profilu konfigurace zařízení v Microsoft Intune. Obsahuje také informace o dostupných nastaveních vzdělávání pro vaše zařízení s Windows 10.

## <a name="create-a-device-profile"></a>Vytvoření profilu zařízení

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte následující vlastnosti:

    - **Název**: Zadejte popisný název nového profilu.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: Zvolte **Windows 10 a novější**.
    - **Profil**: vyberte **vzdělávací profil**.

4. Zadejte nastavení, která chcete nakonfigurovat:

    - [Windows 10 a novější](education-settings-windows.md)

5. Vyberte **OK** > **Vytvořit** a změny uložte.

Po zadání nastavení a vytvoření profilu se tento profil zobrazí v seznamu profilů. Dále [tento profil přiřaďte některým skupinám](device-profile-assign.md).

## <a name="next-steps"></a>Další kroky

Podívejte se na seznam [Nastavení vzdělávání pro Windows 10](education-settings-windows.md) a jejich popis.

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
