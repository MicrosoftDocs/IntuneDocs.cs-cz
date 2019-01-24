---
title: Přidat nebo nakonfigurovat nastavení vzdělávání v Microsoft Intune – Azure | Dokumentace Microsoftu
description: V profilu konfigurace zařízení na Windows 10 a novější zařízení v Microsoft Intune použijte aplikaci zkuste si Test. Vytvořit profil konfigurace pomocí settiings vzdělávání a zadejte adresu URL aplikace testu, zvolte, jak uživatelé přihlásit, monitorování obrazovky během testu a povolit nebo zakázat textové návrhy během testu.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/10/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 1e49e1673e0bebdcdafb8ad7792051c76b80f696
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831450"
---
# <a name="use-the-take-a-test-app-on-windows-10-devices-in-microsoft-intune"></a>Použít na zařízeních s Windows 10 v Microsoft Intune aplikaci zkuste si Test

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Vzdělávací profily v Intune jsou navržené tak, aby studenti mohli vyplňovat testu nebo zkoušku na zařízeních. Tato funkce zahrnuje **zkuste si Test** aplikace a nastavení můžete přidat adresu URL testu, zvolte, jak koncoví uživatelé přihlásit k testu a další. Tato funkce podporuje následující platformy:

- Windows 10 a novější

Když se uživatel přihlásí, aplikaci zkuste si Test se automaticky otevře v testu, které jste zadali. Žádné jiné aplikace můžete spouštět v zařízení během testu. [Používání testů ve Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10) obsahuje další podrobnosti o zkuste aplikaci Test.

V tomto článku jsou uvedené kroky k vytvoření profilu konfigurace zařízení v Microsoft Intune. Obsahuje také informace ke čtení a další informace o nastavení k dispozici vzdělávání pro zařízení s Windows 10.

## <a name="create-a-device-profile"></a>Vytvoření profilu zařízení

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:

    - **Název**: Zadejte popisný název pro nový profil.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: Zvolte **Windows 10 a novější**.
    - **Profil**: Zvolte **vzdělávacího profilu**.

4. Zadejte nastavení, která chcete nakonfigurovat:

    - [Windows 10 a novější](education-settings-windows.md)

5. Vyberte **OK** > **Vytvořit** a změny uložte.

Po zadání nastavení a vytvoření profilu se tento profil zobrazí v seznamu profilů. Dále [tento profil přiřaďte některým skupinám](device-profile-assign.md).

## <a name="next-steps"></a>Další postup

Podívejte se do seznamu [nastavení Windows 10 education](education-settings-windows.md) a jejich popisy.

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).