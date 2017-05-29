---
title: "Konfigurace nastavení sítě VPN v Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Naučte se pomocí Intune nakonfigurovat připojení VPN pro zařízení, která spravujete."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 8a8742d0b579fec734dd8335e2a610d126db21fa
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-configure-vpn-settings-in-microsoft-intune"></a>Konfigurace nastavení sítě VPN v Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Virtuální privátní sítě (VPN) umožňují uživatelům zabezpečený vzdálený přístup k firemní síti. Zařízení používají profil připojení VPN k navázání připojení se serverem VPN. Pomocí **profilů VPN** v Microsoft Intune můžete uživatelům a zařízením v organizaci přiřadit nastavení VPN, aby se mohli snadno a bezpečně připojit k síti.

Chcete třeba zřizovat všechna zařízení s iOSem s nastavením požadovaným pro připojení sdílené položky souboru v podnikové síti. Vytvoříte profil sítě VPN s nastaveními potřebnými pro připojování k podnikové síti a potom tento profil přiřadíte všem uživatelům se zařízeními s iOSem. Uživatelé uvidí připojení VPN v seznamu dostupných sítí a můžou se připojit s minimálním úsilím.

## <a name="vpn-connection-types"></a>Typy připojení VPN

Profily VPN můžete vytvářet pomocí následujících typů připojení:

||||||||
|-|-|-|-|-|-|-|
|Typ připojení|Android|iOS|macOS|Windows Phone 8.1|Windows 8.1|Windows 10|
|Pulse Secure|Ano|Ano|Ano|Ano|Ano|Ano|
|Cisco (IPSec)|Ne|Ano|Ne|Ne|Ne|Ne|
|Citrix|Ano|Ano|Ne|Ne|Ne|Ne|
|F5 Edge Client|Ano|Ano|Ano|Ano|Ano|Ano|
|Dell SonicWALL Mobile Connect|Ano|Ano|Ano|Ano|Ano|Ano|
|Check Point Capsule VPN|Ano|Ano|Ano|Ano|Ano|Ano|
|Cisco AnyConnect|Ano|Ano|Ano|Ne|Ne|Ne|
|Automaticky|Ne|Ne|Ne|Ne|Ne|Ano|
|IKEv2|Ne|Ne|Ne|Ne|Ne|Ano|
|L2TP|Ne|Ne|Ne|Ne|Ne|Ano|
|PPTP|Ne|Ne|Ne|Ne|Ne|Ano|
|Vlastní|Ne|Ano|Ano|Ne|Ne|Ne|


> [!IMPORTANT]
> Před použitím profilů VPN přiřazených nějakému zařízení je nutné nainstalovat příslušnou aplikaci VPN pro profil. S přiřazením aplikace pomocí Intune vám pomůžou informace v článku [Co je správa aplikací v Microsoft Intune](app-management.md).  

Postup vytváření vlastních profilů VPN pomocí nastavení URI najdete v tématu [Vytvoření vlastních profilů VPN](custom-vpn-profiles-create.md).     

## <a name="create-a-device-profile-containing-vpn-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení VPN

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
3. V okně profilů zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **Název** a **Popis** profilu VPN.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete použít nastavení VPN. V současné době můžete pro nastavení VPN na zařízení zvolit jednu z následujících platforem:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 a novější**
    - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **VPN**.
7. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Podrobnosti o nastaveních na jednotlivých platformách najdete v následujících tématech:
    - [Nastavení Androidu](vpn-settings-android.md)
    - [Nastavení iOSu](vpn-settings-ios.md)
    - [Nastavení macOS](vpn-settings-macos.md)
    - [Nastavení Windows Phone 8.1](vpn-settings-windows-phone-8-1.md)
    - [Nastavení Windows 8.1](vpn-settings-windows-8-1.md)
    - [Nastavení Windows 10](vpn-settings-windows-10.md)
8. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).


## <a name="methods-of-securing-vpn-profiles"></a>Metody zabezpečení profilů VPN

Profily VPN můžou používat spoustu různých typů připojení a protokoly od různých výrobců. Tato připojení jsou obvykle zabezpečená jedním ze dvou způsobů.

### <a name="certificates"></a>Certifikáty

Při vytváření profilu VPN zvolíte certifikátu SCEP nebo PKCS, který jste předtím vytvořili v Intune. Označuje se jako certifikát identity. Slouží k ověřování vůči profilu důvěryhodného certifikátu (neboli *kořenového certifikátu*), jehož vytvořením jste potvrdili, že se zařízení uživatele může připojit. Tento důvěryhodný certifikát se přiřazuje počítači, který ověřuje připojení VPN. Zpravidla se jedná o server VPN.

Další informace o vytváření a používání profilů certifikátů v Intune najdete v tématu [Jak konfigurovat certifikáty pomocí Microsoft Intune](certificates-configure.md).

### <a name="user-name-and-password"></a>Uživatelské jméno a heslo

Uživatel se ověřuje na serveru sítě VPN zadáním uživatelského jména a hesla.

