---
title: "Vytváření profilů konfigurace zařízení v Intune | Intune Azure Preview"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Naučte se vytvářet profily konfigurace zařízení v Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 74a905ed2ba9ec04ae14df96fcd3f6b6caf1241c
ms.contentlocale: cs-cz
ms.lasthandoff: 05/10/2017


---

# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Vytváření profilů konfigurace zařízení v Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Konfigurovat zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
2. V okně se seznamem profilů zvolte **Vytvořit profil**.
3. V okně **Vytvořit profil** zadejte následující informace:
    - **Název** – Zadejte popisný název nového profilu.
    - **Popis** – Zadejte popis profilu (volitelné).
    - **Platforma** – Vyberte typ platformy pro profil, který chcete vytvořit.
    - **Typ profilu** – Vyberte typ profilu, který chcete vytvořit. Seznam dostupných typů se bude lišit v závislosti na zvolené platformě.
    - **Nastavení** – Informace o nastaveních pro jednotlivé typy profilů najdete v následujících tématech:
        -  [Nastavení funkce zařízení](how-to-configure-device-features.md)
        -  [Nastavení omezení zařízení](how-to-configure-device-restrictions.md)
        -  [Nastavení e-mailu](how-to-configure-email-settings.md)
        -  [Nastavení VPN](how-to-configure-vpn-settings.md)
        -  [Nastavení Wi-Fi](how-to-configure-wi-fi-settings.md)
        -  [Nastavení upgradu edice Windows 10](how-to-configure-windows-10-edition-upgrade.md)
        -  [Nastavení certifikátu](how-to-configure-certificates.md)
        -  [Nastavení Windows Information Protection](how-to-configure-windows-information-protection.md)
        -  [Nastavení vzdělávání](how-to-configure-education-settings.md)
        -  [Vlastní nastavení](how-to-configure-custom-settings.md)

    ![Vytvoření profilu zařízení](./media/create-device-profile.png)
4. Po dokončení konfigurace nastavení klikněte v okně **Vytvořit profil** na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](how-to-assign-device-profiles.md).


### <a name="next-steps"></a>Další kroky
Informace o přiřazování profilů zařízení najdete v tématu [Jak přiřadit profily zařízení pomocí Microsoft Intune](how-to-assign-device-profiles.md).

