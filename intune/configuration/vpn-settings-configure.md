---
title: Přidání nastavení sítě VPN do zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Pro zařízení s Androidem, Androidem Enterprise, iOS, macOS a Windows můžete pomocí integrovaných nastavení vytvořit připojení k virtuální privátní síti (VPN) v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 59a1b5679b81a8de90e39d6ec13bbe87dac90947
ms.sourcegitcommit: a7c35efb31c4efd816bd4aba29240013965aee92
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/13/2019
ms.locfileid: "73984175"
---
# <a name="create-vpn-profiles-to-connect-to-vpn-servers-in-intune"></a>Vytvoření profilů sítě VPN pro připojení k serverům VPN v Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Virtuální privátní sítě (VPN) poskytují uživatelům zabezpečený vzdálený přístup k síti vaší organizace. Zařízení používají profil připojení VPN ke spuštění připojení se serverem VPN. **Profily sítě VPN** v Microsoft Intune přiřazují uživatelům a zařízením ve vaší organizaci nastavení sítě VPN, aby se mohli snadno a bezpečně připojit k síti vaší organizace.

Chcete například nakonfigurovat všechna zařízení s iOS s požadovaným nastavením pro připojení ke sdílené složce v síti organizace. Vytvoříte profil sítě VPN, který bude obsahovat tato nastavení. Pak tento profil přiřadíte všem uživatelům, kteří mají zařízení s iOS. Uživatelé uvidí připojení VPN v seznamu dostupných sítí a můžou se připojit s minimálním úsilím.

> [!NOTE]
> [Vlastní zásady konfigurace Intune](custom-settings-configure.md) můžete použít k vytvoření profilů sítě VPN pro následující platformy:
>
> * Android 4 a novější
> * Zaregistrovaná zařízení se systémem Windows 8.1 a novějším
> * Windows Phone 8.1 a novější
> * Zaregistrovaná zařízení s desktopovým systémem Windows 10
> * Windows 10 Mobile
> * Windows Holographic for Business

## <a name="vpn-connection-types"></a>Typy připojení VPN

Profily VPN můžete vytvářet pomocí následujících typů připojení:

|Typ připojení|Platforma|
|-|-|
|Automaticky|Windows 10|
|Check Point Capsule VPN|– Android<br/>– Android Enterprise Working Profiles<br/>– iOS<br/>– macOS<br/>– Windows 10<br/>-Windows 8.1<br/>-Windows Phone 8,1|
|Cisco AnyConnect|– Android<br/>– Android Enterprise Working Profiles<br/>– Vlastník zařízení s Androidem Enterprise (plně spravovaný)<br/>– iOS<br/>– macOS|
|Cisco (IPSec)|iOS|
|Citrix SSO|– Android<br/>– Android Enterprise Working Profiles: použití [zásad konfigurace aplikací](../apps/app-configuration-policies-use-android.md)<br/>– Vlastník zařízení s Androidem Enterprise (plně spravovaný): použít [zásady konfigurace aplikací](../apps/app-configuration-policies-use-android.md)<br/>– iOS<br/>– Windows 10|
|Vlastní VPN|– iOS<br/>– macOS|
|F5 Access|– Android<br/>– Android Enterprise Working Profiles<br/>– Vlastník zařízení s Androidem Enterprise (plně spravovaný)<br/>– iOS<br/>– macOS<br/>– Windows 10<br/>-Windows 8.1<br/>-Windows Phone 8,1|
|IKEv2| – iOS<br/>– Windows 10|
|L2TP|Windows 10|
|Palo Alto Networks GlobalProtect|– Android Enterprise Working Profiles: použití [zásad konfigurace aplikací](../apps/app-configuration-policies-use-android.md)<br/>– iOS<br/>– Windows 10|
|PPTP|Windows 10|
|Pulse Secure|– Android<br/>– Android Enterprise Working Profiles<br/>– Vlastník zařízení s Androidem Enterprise (plně spravovaný)<br/>– iOS<br/>– macOS<br/>– Windows 10<br/>-Windows 8.1<br/>-Windows Phone 8,1|
|SonicWall Mobile Connect|– Android<br/>– Android Enterprise Working Profiles<br/>– iOS<br/>– macOS<br/>– Windows 10<br/>-Windows 8.1<br/>-Windows Phone 8,1|
|Zscaler|– Android Enterprise Working Profiles: použití [zásad konfigurace aplikací](../apps/app-configuration-policies-use-android.md)<br/>– iOS|

> [!IMPORTANT]
> Před použitím profilů VPN přiřazených nějakému zařízení je nutné nainstalovat příslušnou aplikaci VPN pro profil. S přiřazením aplikace pomocí Intune vám pomůžou informace v článku [Co je správa aplikací v Microsoft Intune](../apps/app-management.md).  

Postup vytváření vlastních profilů VPN pomocí nastavení URI najdete v tématu [Vytvoření profilu s vlastním nastavením](custom-settings-configure.md).

## <a name="create-a-device-profile"></a>Vytvoření profilu zařízení

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vyberte **zařízení** > **konfiguračních profilech** > **vytvořit profil**.
3. Zadejte následující vlastnosti:

    - **Název**: zadejte popisný název profilu. Své profily pojmenujte, abyste je později mohli snadno identifikovat. Dobrým názvem profilu je například **profil sítě VPN pro celou firmu**.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: vyberte platformu zařízení. Možnosti:

      - **Androidemem**
      - Jenom **Android Enterprise** > **vlastník zařízení**
      - **Jenom pracovní profil** pro **Android Enterprise** > 
      - **iOS/iPadOS**
      - **macOS**
      - **Windows Phone 8.1**
      - **Windows 8.1 a novější**
      - **Windows 10 a novější**

    - **Typ profilu**: vyberte **VPN**.

4. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Podrobné informace o nastaveních na jednotlivých platformách najdete v následujících článcích:

    - [Nastavení Androidu](vpn-settings-android.md)
    - [Nastavení Androidu Enterprise](vpn-settings-android-enterprise.md)
    - [nastavení pro iOS/iPadOS](vpn-settings-ios.md)
    - [Nastavení macOS](vpn-settings-macos.md)
    - [Nastavení Windows Phone 8.1](vpn-settings-windows-phone-8-1.md)
    - [Nastavení Windows 8.1](vpn-settings-windows-8-1.md)
    - [Nastavení Windows 10](vpn-settings-windows-10.md) (včetně Windows Holographic for Business)

5. Až to budete mít, vyberte **OK** > **Vytvořit** a změny uložte.

Profil se vytvoří a zobrazí se v seznamu profilů. Pokud chcete přiřadit tento profil ke skupinám, podívejte se na téma [Přiřazení profilů zařízení](device-profile-assign.md).

## <a name="secure-your-vpn-profiles"></a>Zabezpečení profilů sítě VPN

Profily VPN můžou používat spoustu různých typů připojení a protokoly od různých výrobců. Tato připojení jsou obvykle zabezpečená pomocí následujících metod.

### <a name="certificates"></a>Certifikáty

Při vytváření profilu VPN zvolíte certifikátu SCEP nebo PKCS, který jste předtím vytvořili v Intune. Tento profil se označuje jako certifikát identity. Slouží k ověřování vůči profilu důvěryhodného certifikátu (neboli *kořenového certifikátu*), který vytváříte, aby se mohlo zařízení uživatele připojit. Tento důvěryhodný certifikát se přiřazuje počítači, který ověřuje připojení VPN. Zpravidla se jedná o server VPN.

Další informace o vytváření a používání profilů certifikátů v Intune najdete v tématu [Jak konfigurovat certifikáty pomocí Microsoft Intune](../protect/certificates-configure.md).

### <a name="user-name-and-password"></a>Uživatelské jméno a heslo

Uživatel se ověřuje na serveru sítě VPN zadáním uživatelského jména a hesla.

## <a name="next-steps"></a>Další kroky

Když je profil vytvořený, není ještě aktivní. Pak [Přiřaďte profil](device-profile-assign.md) k některým zařízením.

V zařízeních s [Androidem](android-pulse-secure-per-app-vpn.md) a [iOS](vpn-setting-configure-per-app.md) taky můžete vytvářet a používat sítě VPN pro jednotlivé aplikace.
