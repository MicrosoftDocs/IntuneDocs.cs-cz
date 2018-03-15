---
title: "Vytvoření profilů zařízení v Microsoft Intune – Azure | Microsoft Docs"
description: "Přidání nebo konfigurace profilu zařízení v Microsoft Intune, včetně výběru typu platformy a konfigurace nastavení na portálu Azure Portal"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e4e1febb5f12de038d2ddd543be883f71ef79005
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Vytvořte profil zařízení v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>Vytvoření profilu
1. Na portálu [Azure Portal](https://portal.azure.com) vyberte **Všechny služby** a vyhledejte **Microsoft Intune**.

2. V **Microsoft Intune** vyberte **Konfigurace zařízení**, **Profily** a pak **Vytvořit profil**.

3. Zadejte následující vlastnosti:

    - **Název** – Zadejte popisný název nového profilu.
    - **Popis**: Volitelné, avšak doporučené: Zadejte popis profilu.
    - **Platforma**: Vyberte typ platformy:  

        - **Androidemem**
        - **Android for Work**
        - **iOS**
        - **macOS**
        - **Windows Phone 8.1**
        - **Windows 8.1 a novější**
        - **Windows 10 a novější**

    - **Typ profilu**: Vyberte typ, který chcete vytvořit. Seznam závisí na platformě, kterou vyberete.
    - **Nastavení**: Informace o nastaveních pro jednotlivé typy profilů najdete v následujících tématech:

        -  [Nastavení funkce zařízení](device-features-configure.md)
        -  [Nastavení omezení zařízení](device-restrictions-configure.md)
        -  [Nastavení e-mailu](email-settings-configure.md)
        -  [Nastavení VPN](vpn-settings-configure.md)
        -  [Nastavení Wi-Fi](wi-fi-settings-configure.md)
        -  [Nastavení upgradu edice Windows 10](edition-upgrade-configure-windows-10.md)
        -  [Nastavení certifikátu](certificates-configure.md)
        -  [Nastavení Windows Information Protection](windows-information-protection-configure.md)
        -  [Nastavení vzdělávání](education-settings-configure.md)
        -  [Vlastní nastavení](custom-settings-configure.md)

    ![Zadejte nastavení pro vytvoření profilu zařízení](./media/create-device-profile.png)

4. Po dokončení vyberte **Vytvořit**.

Profil se vytvoří a zobrazí se v seznamu. Pokud chcete přiřadit tento profil ke skupinám, podívejte se na téma [Přiřazení profilů zařízení](device-profile-assign.md).


## <a name="next-steps"></a>Další kroky
Informace o přiřazování profilů zařízení najdete v tématu [Jak přiřadit profily zařízení pomocí Microsoft Intune](device-profile-assign.md).
