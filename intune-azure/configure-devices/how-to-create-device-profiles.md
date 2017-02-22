---
title: "Vytváření profilů konfigurace zařízení v Intune | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Naučte se vytvářet profily konfigurace zařízení v Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: 6c6ac8112a6b6413df635607a24d0d06466c0b88


---

# <a name="how-to-create-device-configuration-profiles"></a>Jak vytvářet profily konfigurace zařízení 

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
        -  [Nastavení omezení zařízení](/intune-azure/configure-devices/how-to-configure-device-restrictions)
        -  [Nastavení e-mailu](/intune-azure/configure-devices/how-to-configure-email-settings)
        -  [Nastavení VPN](/intune-azure/configure-devices/how-to-configure-vpn-settings)
        -  [Nastavení Wi-Fi](/intune-azure/configure-devices/how-to-configure-wi-fi-settings)
        -  [Nastavení upgradu edice Windows 10](/intune-azure/configure-devices/how-to-configure-windows-10-edition-upgrade)
        -  [Nastavení certifikátu](/intune-azure/configure-devices/how-to-configure-certificates)
        -  [Nastavení Windows Information Protection](/intune-azure/configure-devices/how-to-configure-windows-information-protection)
        -  [Nastavení vzdělávání](/intune-azure/configure-devices/education-settings-for-ios.md)
        -  [Vlastní nastavení](/intune-azure/configure-devices/how-to-configure-custom-settings)

    ![Vytvoření profilu zařízení](./media/create-device-profile.png)
4. Po dokončení konfigurace nastavení klikněte v okně **Vytvořit profil** na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](how-to-assign-device-profiles.md).


### <a name="next-steps"></a>Další kroky
Informace o přiřazování profilů zařízení najdete v tématu [Jak přiřadit profily zařízení pomocí Microsoft Intune](/intune-azure/configure-devices/how-to-assign-device-profiles).



<!--HONumber=Feb17_HO1-->


