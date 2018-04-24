---
title: Vytvoření vlastních profilů VPN s Microsoft Intune
titleSuffix: ''
description: Vlastní konfigurace slouží k vytvoření profilů VPN v Intune.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ec9b959d086051985287a62f7d10fe8d4cbad7e9
ms.sourcegitcommit: 28ed8902a11500b195fff839d59b90c16af6e743
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/29/2018
---
# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Vytvoření vlastních profilů VPN v Microsoft Intune

Zásady vlastní konfigurace Intune můžete použít k vytvoření profilů VPN pro tyto platformy:

* Android 4 a novější
* Zaregistrovaná zařízení se systémem Windows 8.1 a novějším
* Windows Phone 8.1 nebo novější
* Zaregistrovaná zařízení s desktopovým systémem Windows 10 
* Windows 10 Mobile

Tento typ zásad může být užitečný v případě, že standardní zásady Intune VPN nemají nastavení, která chcete použít.

## <a name="to-create-a-custom-configuration-policy"></a>Vytvoření vlastní zásady konfigurace:

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Konfigurace zařízení**.
2. V podokně **Konfigurace zařízení** v části **Spravovat** zvolte **Profily**.
5. V podokně profilů zvolte **Vytvořit profil**.
6. V podokně **Vytvořit profil** zadejte **Název** a **Popis** profilu VPN.
7. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete použít nastavení VPN. V současné době můžete pro vlastní nastavení zařízení zvolit jednu z následujících platforem:
    - **Androidemem**
    - **Android for Work**
    - **iOS** (konfigurace pomocí souboru, který jste exportovali z Apple Configuratoru)
    - **macOS** (konfigurace pomocí souboru, který jste exportovali z Apple Configuratoru)
    - **Windows Phone 8.1**
    - **Windows 8.1 a novější**
    - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **Vlastní**.
7. V podokně **Vlastní nastavení OMA-URI** zvolte pro každé nastavení URI, které chcete zadat, možnost **Přidat**, zadejte požadované informace a zvolte **OK**. Tady je příklad:

   ![Dialogové okno vlastní konfigurace profilu VPN](./media/Intune_Add_VPN_URI.png)

4.  Po zadání všech potřebných nastavení URI zvolte **OK** a pak v podokně **Vytvořit profil** zvolte **Vytvořit**.

Profil se vytvoří a zobrazí se v podokně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).




