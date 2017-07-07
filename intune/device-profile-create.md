---
title: "Vytváření profilů konfigurace zařízení v Intune"
titleSuffix: Intune on Azure
description: "Přečtěte si, jak v Intune vytvořit profily konfigurace zařízení."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6df6813667241d3ad5f8768585f2e1a34f0fe6e3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Vytváření profilů konfigurace zařízení v Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Konfigurovat zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
2. V okně se seznamem profilů zvolte **Vytvořit profil**.
3. V okně **Vytvořit profil** zadejte následující položky:
    - **Název** – Zadejte popisný název nového profilu.
    - **Popis** – Zadejte popis profilu (volitelné).
    - **Platforma** – Vyberte typ platformy pro profil, který chcete vytvořit.
    - **Typ profilu** – Vyberte typ profilu, který chcete vytvořit. Seznam dostupných typů se liší v závislosti na zvolené platformě.
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
