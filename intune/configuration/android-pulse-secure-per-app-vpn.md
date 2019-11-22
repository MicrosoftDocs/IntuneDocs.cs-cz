---
title: Vlastní profil VPN pro jednotlivé aplikace pro Android
titleSuffix: Microsoft Intune
description: Zjistěte, jak pro zařízení s Androidem spravovaná pomocí Microsoft Intune vytvořit profil VPN pro aplikaci.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 62f418e396c5030a47ea0bcb31914cd4e1069c40
ms.sourcegitcommit: eb2e420b304c7da9d3be5ef49a676cba66766d2b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74319845"
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>K vytvoření profilu VPN pro aplikaci pro zařízení s Androidem můžete použít vlastní profil Microsoft Intune.

Pro zařízení s Androidem verze 5.0 a novější spravovaná pomocí Intune můžete vytvořit profil VPN pro jednotlivé aplikace. Nejdříve vytvoříte profil VPN, který používá typ připojení Pulse Secure nebo Citrix. Potom vytvoříte vlastní zásadu konfigurace, která přidruží tento profil ke konkrétním aplikacím.

> [!NOTE]
> To use per-app VPN on Android Enterprise devices, you can also use these steps. But, it's recommended to use an [app configuration policy](../apps/app-configuration-policies-use-android.md) for your VPN client app.

Po přiřazení zásad pro skupiny zařízení nebo uživatelů Android by uživatelé měli spustit klienta VPN Pulse Secure nebo Citrix. Klient VPN pak umožní provoz jenom z určených aplikací, které budou moct používat otevřené připojení VPN.

> [!NOTE]
>
> Pro tento profil se podporují jenom připojení Pulse Secure a Citrix.

## <a name="step-1-create-a-vpn-profile"></a>Krok 1: Vytvoření profilu sítě VPN

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Select **Devices** > **Configuration profiles** > **Create profile**.
3. Zadejte následující vlastnosti:

    - **Name**: Enter a descriptive name for the profile. Name your profiles so you can easily identify them later. For example, a good profile name is **Android per-app VPN profile for entire company**.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platform**: Select **Android**.
    - **Profile type**: Select **VPN**.

4. Zvolte **Nastavení** > **Konfigurovat**. Then, configure the VPN profile. For more information, see [How to configure VPN settings](vpn-settings-configure.md) and [Intune VPN settings for Android devices](vpn-settings-android.md).

Poznamenejte si hodnotu **Název připojení**, kterou zadáváte při vytváření profilu VPN. Tento název bude potřeba v dalším kroku. Příklad: **profil_VPN_pro_moje_aplikace**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Krok 2: Vytvoření vlastní zásady konfigurace

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Select **Devices** > **Configuration profiles** > **Create profile**.
3. Zadejte následující vlastnosti:

    - **Name**: Enter a descriptive name for the custom profile. Name your profiles so you can easily identify them later. For example, a good profile name is **Custom OMA-URI Android VPN profile for entire company**.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platform**: Select **Android**.
    - **Profile type**: Select **Custom**.

4. Zvolte **Nastavení** > **Konfigurovat**.
5. V podokně **Vlastní nastavení OMA-URI** zvolte **Přidat**.
    - **Name**: Enter a name for your setting.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **OMA-URI**: Enter `./Vendor/MSFT/VPN/Profile/*Name*/PackageList`, where *Name* is the connection name you noted in Step 1. In this example, the string is `./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList`.
    - **Data type**: Enter **String**.
    - **Value**: Enter a semicolon-separated list of packages to associate with the profile. For example, if you want Excel and the Google Chrome browser to use the VPN connection, enter `com.microsoft.office.excel;com.android.chrome`.

![Příklad vlastní zásady VPN pro aplikaci pro Android](./media/android-pulse-secure-per-app-vpn/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Nastavení seznamu aplikací jako zakázaných nebo povolených (volitelné)

Use the **BLACKLIST** value to enter a list of apps that *cannot* use the VPN connection. Všechny ostatní aplikace se připojují prostřednictvím VPN. Or, use the **WHITELIST** value to enter a list of apps that *can* use the VPN connection. Apps that aren't on the list don't connect through the VPN.

1. V podokně **Vlastní nastavení OMA-URI** zvolte **Přidat**.
2. Zadejte název nastavení.
3. In **OMA-URI**, enter `./Vendor/MSFT/VPN/Profile/*Name*/Mode`, where *Name* is the VPN profile name you noted in Step 1. In our example, the string is `./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode`.
4. In **Data type**, enter **String**.
5. Do pole **Hodnota** zadejte **BLACKLIST** nebo **WHITELIST**.

## <a name="step-3-assign-both-policies"></a>Krok 3: Přiřazení obou zásad

[Assign both device profiles](device-profile-assign.md) to the required users or devices.
