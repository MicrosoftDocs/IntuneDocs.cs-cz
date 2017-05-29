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
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: a719b3f53076a55f1e888a9ddf8e98c7074dd25f
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Vytváření profilů konfigurace zařízení v Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]


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

    ![Vytvoření profilu zařízení](./media/create-device-profile.png)
4. Po dokončení konfigurace nastavení klikněte v okně **Vytvořit profil** na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).


### <a name="next-steps"></a>Další kroky
Informace o přiřazování profilů zařízení najdete v tématu [Jak přiřadit profily zařízení pomocí Microsoft Intune](device-profile-assign.md).

