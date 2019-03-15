---
title: Vytvoření profilu zařízení VPN v Microsoft Intune – Azure | Microsoft Docs
description: Přečtěte si, jaké jsou v Microsoft Intune na zařízeních s iOSem typy připojení k virtuální privátní síti (VPN), jak vytvořit profil zařízení VPN na portálu Azure Portal a jaké máte možnosti zabezpečení profilu VPN pomocí certifikátů nebo uživatelského jména a hesla.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/25/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 11684ceea5aafa7de5a2663e5a69bbbe7367b655
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57394046"
---
# <a name="create-vpn-profiles-in-intune"></a>Vytváření profilů sítě VPN v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Virtuální privátní sítě (VPN) umožňují uživatelům zabezpečený vzdálený přístup k firemní síti. Zařízení používají profil připojení VPN k navázání připojení se serverem VPN. Pomocí **profilů VPN** v Microsoft Intune můžete uživatelům a zařízením v organizaci přiřadit nastavení VPN, aby se mohli snadno a bezpečně připojit k síti.

Chcete třeba zřizovat všechna zařízení s iOSem s nastavením požadovaným pro připojení sdílené položky souboru v podnikové síti. Vytvoříte profil VPN, který obsahuje nastavení pro připojení k podnikové síti. Potom tento profil přiřadíte všem uživatelům využívajícím zařízení s iOSem. Uživatelé uvidí připojení VPN v seznamu dostupných sítí a můžou se připojit s minimálním úsilím.

Vlastní zásady konfigurace Intune můžete použít k vytvoření profilů sítě VPN pro tyto platformy:

* Android 4 a novější
* Zaregistrovaná zařízení se systémem Windows 8.1 a novějším
* Windows Phone 8.1 nebo novější
* Zaregistrovaná zařízení s desktopovým systémem Windows 10
* Windows 10 Mobile
* Windows Holographic for Business

## <a name="vpn-connection-types"></a>Typy připojení VPN

Profily VPN můžete vytvářet pomocí následujících typů připojení:

|Typ připojení|Android<br>Pracovní profily Androidu|iOS|macOS|Windows Phone 8.1|Windows 8.1|Windows 10|
|-|-|-|-|-|-|-|
|Automatické|Ne|Ne|Ne|Ne|Ne|Ano|
|Check Point Capsule VPN|Ano|Ano|Ano|Ano|Ano|Ano|
|Cisco AnyConnect|Ano|Ano|Ano|Ne|Ne|Ne|
|SonicWall Mobile Connect|Ano|Ano|Ano|Ano|Ano|Ano|
|F5 Edge Client|Ano|Ano|Ano|Ano|Ano|Ano|
|Palo Alto Networks GlobalProtect|Ne|Ano|Ne|Ne|Ne|Ano|
|Pulse Secure|Ano|Ano|Ano|Ano|Ano|Ano|
|Cisco (IPSec)|Ne|Ano|Ne|Ne|Ne|Ne|
|Citrix|Ano (jen Android)|Ano|Ne|Ne|Ne|Ano|
|IKEv2|Ne|Ne|Ne|Ne|Ne|Ano|
|L2TP|Ne|Ne|Ne|Ne|Ne|Ano|
|PPTP|Ne|Ne|Ne|Ne|Ne|Ano|
|Zscaler|Ne|Ano|Ne|Ne|Ne|Ne|
|Vlastní VPN|Ne|Ano|Ano|Ne|Ne|Ne|

> [!IMPORTANT]
> Před použitím profilů VPN přiřazených nějakému zařízení je nutné nainstalovat příslušnou aplikaci VPN pro profil. S přiřazením aplikace pomocí Intune vám pomůžou informace v článku [Co je správa aplikací v Microsoft Intune](app-management.md).  

Postup vytváření vlastních profilů VPN pomocí nastavení URI najdete v tématu [Vytvoření profilu s vlastním nastavením](custom-settings-configure.md).

## <a name="create-a-device-profile-containing-vpn-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení VPN

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
4. Zadejte **název** a **popis** profilu VPN.
5. V rozevíracím seznamu **Platforma** vyberte platformu zařízení, u které chcete použít nastavení VPN. V současné době můžete pro nastavení VPN na zařízení zvolit jednu z následujících platforem:
   - **Android**
   - **Android Enterprise**
   - **iOS**
   - **macOS**
   - **Windows Phone 8.1**
   - **Windows 8.1 a novější**
   - **Windows 10 a novější**
6. V rozevíracím seznamu **Typ profilu** zvolte **VPN**.
7. Nastavení, která můžete konfigurovat, se liší podle zvolené platformy. Podrobnosti o nastaveních na jednotlivých platformách najdete v následujících tématech:
   - [Nastavení Androidu a pracovního profilu Androidu](vpn-settings-android.md)
   - [Nastavení iOSu](vpn-settings-ios.md)
   - [Nastavení macOS](vpn-settings-macos.md)
   - [Nastavení Windows Phone 8.1](vpn-settings-windows-phone-8-1.md)
   - [Nastavení Windows 8.1](vpn-settings-windows-8-1.md)
   - [Nastavení Windows 10](vpn-settings-windows-10.md) (včetně Windows Holographic for Business)
8. Po dokončení vyberte **Vytvořit**.

Profil se vytvoří a zobrazí se v seznamu profilů. Pokud chcete přiřadit tento profil ke skupinám, podívejte se na téma [Přiřazení profilů zařízení](device-profile-assign.md).

## <a name="methods-of-securing-vpn-profiles"></a>Metody zabezpečení profilů VPN

Profily VPN můžou používat spoustu různých typů připojení a protokoly od různých výrobců. Tato připojení jsou obvykle zabezpečená jedním ze dvou způsobů.

### <a name="certificates"></a>Certifikáty

Při vytváření profilu VPN zvolíte certifikátu SCEP nebo PKCS, který jste předtím vytvořili v Intune. Tento profil se označuje jako certifikát identity. Slouží k ověřování vůči profilu důvěryhodného certifikátu (neboli *kořenového certifikátu*), který vytváříte, aby se mohlo zařízení uživatele připojit. Tento důvěryhodný certifikát se přiřazuje počítači, který ověřuje připojení VPN. Zpravidla se jedná o server VPN.

Další informace o vytváření a používání profilů certifikátů v Intune najdete v tématu [Jak konfigurovat certifikáty pomocí Microsoft Intune](certificates-configure.md).

### <a name="user-name-and-password"></a>Uživatelské jméno a heslo

Uživatel se ověřuje na serveru sítě VPN zadáním uživatelského jména a hesla.
