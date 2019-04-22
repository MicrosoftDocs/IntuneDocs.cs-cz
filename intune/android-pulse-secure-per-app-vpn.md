---
title: Vlastní profil VPN pro jednotlivé aplikace pro Android
titleSuffix: Microsoft Intune
description: Zjistěte, jak pro zařízení s Androidem spravovaná pomocí Microsoft Intune vytvořit profil VPN pro aplikaci.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/05/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 38763d5c16d5cba36220c03e9d74b30a465d752b
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59899597"
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>K vytvoření profilu VPN pro aplikaci pro zařízení s Androidem můžete použít vlastní profil Microsoft Intune.

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pro zařízení s Androidem verze 5.0 a novější spravovaná pomocí Intune můžete vytvořit profil VPN pro jednotlivé aplikace. Nejdříve vytvoříte profil VPN, který používá typ připojení Pulse Secure nebo Citrix. Potom vytvoříte vlastní zásadu konfigurace, která přidruží tento profil ke konkrétním aplikacím.

Po přiřazení zásad pro skupiny zařízení nebo uživatelů Android by uživatelé měli spustit klienta VPN Pulse Secure nebo Citrix. Klient VPN pak umožní provoz jenom z určených aplikací, které budou moct používat otevřené připojení VPN.

> [!NOTE]
>
> Pro tento profil se podporují jenom připojení Pulse Secure a Citrix.


## <a name="step-1-create-a-vpn-profile"></a>Krok 1: Vytvoření profilu sítě VPN


1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Konfigurace zařízení**.
2. V podokně **Konfigurace zařízení** v části **Spravovat** zvolte **Profily**.
2. V podokně se seznamem profilů zvolte **Vytvořit profil**.
3. V podokně **Vytvořit profil** zadejte **Název** a nepovinný **Popis** profilu VPN.
4. V rozevíracím seznamu **Platforma** zvolte **Android**.
5. V rozevíracím seznamu **Typ profilu** zvolte **VPN**.
3. Zvolte **Nastavení** > **Konfigurovat** a nakonfigurujte profil VPN podle nastavení v [Jak konfigurovat nastavení VPN](vpn-settings-configure.md) a [Nastavení Intune VPN pro zařízení s Androidem](vpn-settings-android.md).

Poznamenejte si hodnotu **Název připojení**, kterou zadáváte při vytváření profilu VPN. Tento název bude potřeba v dalším kroku. Příklad: **profil_VPN_pro_moje_aplikace**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Krok 2: Vytvoření vlastní zásady Konfigurace

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Konfigurace zařízení**.
2. V podokně **Konfigurace zařízení** v části **Spravovat** zvolte **Profily**.
3. V podokně s profily klikněte na **Vytvořit profil**.
4. V podokně **Vytvořit profil** zadejte **Název** a **Popis** vlastního profilu.
5. V rozevíracím seznamu **Platforma** zvolte **Android**.
6. V rozevíracím seznamu **Typ profilu** zvolte **Vlastní**.
7. Zvolte **Nastavení** > **Konfigurovat**.
3. V podokně **Vlastní nastavení OMA-URI** zvolte **Přidat**.
    - Zadejte název nastavení.
    - Pro **OMA-URI** zadejte tento řetězec: **./Vendor/MSFT/VPN/Profile/*název*/PackageList**, kde *název* je název připojení, který jste si poznamenali v kroku 1. V tomto příkladu by se použil řetězec **./Vendor/MSFT/VPN/Profile/profil_VPN_pro_moje_aplikace/PackageList**.
    - Jako **Datový typ** určete **String** (Řetězec).
    - Do pole **Hodnota** zadejte seznam balíčků (oddělených středníkem), které mají být k tomuto profilu přidružené. Pokud třeba chcete, aby připojení VPN používal Excel a prohlížeč Google Chrome, zadejte **com.microsoft.office.excel;com.android.chrome**.

![Příklad vlastní zásady VPN pro aplikaci pro Android](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Nastavení seznamu aplikací jako zakázaných nebo povolených (volitelné)
  Pomocí hodnoty *BLACKLIST* můžete určit, že jde o seznam aplikací, pro které **není povoleno** použít připojení VPN. Všechny ostatní aplikace se připojují prostřednictvím VPN.
Další možností je určit pomocí hodnoty **WHITELIST** aplikace, které *jediné* budou moci připojení VPN používat. Aplikace, které nejsou v seznamu, se nepřipojují prostřednictvím VPN.
  1.    V podokně **Vlastní nastavení OMA-URI** zvolte **Přidat**.
  2.    Zadejte název nastavení.
  3.    Pro **OMA-URI** použijte tento řetězec: **./Vendor/MSFT/VPN/Profile/*název*/Mode**, kde *název* je název profilu VPN, který jste si poznamenali v kroku 1. V našem příkladu by se tedy použil řetězec **./Vendor/MSFT/VPN/Profile/profil_VPN_pro_moje_aplikace/Mode**.
  4.    Jako **Datový typ** určete **String** (Řetězec).
  5.    Do pole **Hodnota** zadejte **BLACKLIST** nebo **WHITELIST**.



## <a name="step-3-assign-both-policies"></a>Krok 3: Přiřazení obou zásad

Pomocí pokynů v [Jak přiřadit profily zařízení](device-profile-assign.md) přiřaďte oba profily k požadovaným uživatelům nebo zařízením.
