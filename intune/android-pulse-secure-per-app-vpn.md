---
title: "Profil VPN pro jednotlivé aplikace pro Android – Pulse Secure"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Informace o tom, jak pro zařízení s Androidem spravovaná pomocí Intune vytvořit profil VPN pro aplikaci"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: babeaa13da863ca3335c3a05dbabb4a9ac7889ce
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>K vytvoření profilu VPN pro aplikaci pro zařízení s Androidem můžete použít vlastní profil Microsoft Intune.

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Pro zařízení s Androidem verze 5.0 a novější spravovaná pomocí Intune můžete vytvořit profil VPN pro jednotlivé aplikace. Nejdřív vytvoříte profil VPN, který používá typ připojení Pulse Secure. Potom vytvoříte vlastní zásadu konfigurace, která přidruží tento profil ke konkrétním aplikacím.

Po přiřazení této zásady skupinám zařízení nebo uživatelů Android by uživatelé měli spustit PulseSecure VPN. PulseSecure pak umožní provoz pouze z určených aplikací, které budou moci používat otevřené připojení VPN.

> [!NOTE]
>
> Pro tento profil se podporuje jenom připojení Pulse Secure.


## <a name="step-1-create-a-vpn-profile"></a>Krok 1: Vytvoření profilu sítě VPN


1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
2. V okně seznamu profilů zvolte **Vytvořit profil**.
3. V okně **Vytvořit profil** zadejte **Název** a nepovinný **Popis** profilu VPN.
4. V rozevíracím seznamu **Platforma** zvolte **Android**.
5. V rozevíracím seznamu **Typ profilu** zvolte **VPN**.
3. Zvolte **Nastavení** > **Konfigurovat** a nakonfigurujte profil VPN podle nastavení v [Jak konfigurovat nastavení VPN](vpn-settings-configure.md) a [Nastavení Intune VPN pro zařízení s Androidem](vpn-settings-android.md).

Poznamenejte si název profilu sítě VPN pro použití v dalším kroku. Příklad: **profil_VPN_pro_moje_aplikace**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Krok 2: Vytvoření vlastní zásady konfigurace

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
3. V okně s profily zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **název** a **popis** vlastního profilu.
5. V rozevíracím seznamu **Platforma** zvolte **Android**.
6. V rozevíracím seznamu **Typ profilu** zvolte **Vlastní**.
7. Zvolte **Nastavení** > **Konfigurovat**.
3. V okně **Vlastní nastavení OMA-URI** zvolte **Přidat**.
    - Zadejte název nastavení.
    - Jako **Datový typ** určete **String** (Řetězec).
    - Pro **OMA-URI** zadejte tento řetězec: **./Vendor/MSFT/VPN/Profile/*název*/PackageList**, kde *název* je název profilu VPN, který jste si poznamenali v kroku 1. V tomto příkladu by se použil řetězec **./Vendor/MSFT/VPN/Profile/profil_VPN_pro_moje_aplikace/PackageList**.
    - Do pole **Hodnota** zadejte seznam balíčků (oddělených středníkem), které mají být k tomuto profilu přidružené. Pokud třeba chcete, aby připojení VPN používal Excel a prohlížeč Google Chrome, zadejte **com.microsoft.office.excel;com.android.chrome**.

![Příklad vlastní zásady VPN pro aplikaci pro Android](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Nastavení seznamu aplikací jako zakázaných nebo povolených (volitelné)
  Pomocí hodnoty *BLACKLIST* můžete určit, že jde o seznam aplikací, pro které **není povoleno** použít připojení VPN. Ostatní aplikace se budou připojovat prostřednictvím VPN.
Další možností je určit pomocí hodnoty **WHITELIST** aplikace, které *jediné* budou moci připojení VPN používat. Aplikace, které nejsou v seznamu, se nebudou připojovat prostřednictvím VPN.
  1.    V okně **Vlastní nastavení OMA-URI** zvolte **Přidat**.
  2.    Zadejte název nastavení.
  3.    Jako **Datový typ** určete **String** (Řetězec).
  4.    Pro **OMA-URI** použijte tento řetězec: **./Vendor/MSFT/VPN/Profile/*název*/Mode**, kde *název* je název profilu VPN, který jste si poznamenali v kroku 1. V našem příkladu by se tedy použil řetězec **./Vendor/MSFT/VPN/Profile/profil_VPN_pro_moje_aplikace/Mode**.
  5.    Do pole **Hodnota** zadejte **BLACKLIST** nebo **WHITELIST**.



## <a name="step-3-assign-both-policies"></a>Krok 3: Přiřazení obou zásad

Pomocí pokynů v [Jak přiřadit profily zařízení](device-profile-assign.md) přiřaďte oba profily k požadovaným uživatelům nebo zařízením.

