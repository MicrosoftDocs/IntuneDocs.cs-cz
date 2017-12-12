---
title: "Vytvoření vlastních profilů VPN s Microsoft Intune"
titleSuffix: Azure portal
description: "Vlastní konfigurace slouží k vytvoření profilů VPN v Intune."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cc1374c3ccb60ed5a3dc57449f5c772963b8efc7
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/12/2017
---
# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Vytvoření vlastních profilů VPN v Microsoft Intune

## <a name="create-a-custom-configuration"></a>Vytvoření vlastní konfigurace
Vlastní konfigurace Intune můžete použít k vytvoření profilů VPN pro:

* Zařízení se systémem Android 4 nebo novější verzí
* Zaregistrovaná zařízení se systémem Windows 8.1 a novějším
* Zařízení s Windows Phone 8.1 a novějším
* Zaregistrovaná zařízení s desktopovým systémem Windows 10 
* Zařízení, která používají Windows 10 Mobile

Tento typ zásad může být užitečný v případě, že standardní zásady Intune VPN neobsahují nastavení, které chcete použít.

## <a name="to-create-a-custom-configuration-policy"></a>Vytvoření vlastní zásady konfigurace:

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
4. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
5. V okně profilů zvolte **Vytvořit profil**.
6. V okně **Vytvořit profil** zadejte **Název** a **Popis** profilu VPN.
7. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete použít nastavení VPN. V současné době můžete pro vlastní nastavení zařízení zvolit jednu z následujících platforem:
    - **Android**
    - **iOS** (konfigurace pomocí souboru, který jste exportovali z Apple Configuratoru)
    - **macOS** (konfigurace pomocí souboru, který jste exportovali z Apple Configuratoru)
    - **Windows Phone 8.1**
    - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **Vlastní**.
7. V okně **Vlastní nastavení OMA-URI** zvolte pro každé nastavení URI, které chcete zadat, možnost **Přidat**, zadejte požadované informace a zvolte **OK**. Tady je příklad:

   ![Dialogové okno vlastní konfigurace profilu VPN](./media/Intune_Add_VPN_URI.png)

4.  Po zadání všech potřebných nastavení URI zvolte **OK** a pak v okně **Vytvořit profil** zvolte **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).




