---
title: Konfigurace nastavení VPN pro zařízení s Androidem v Microsoft Intune – Azure | Microsoft Docs
description: Při vytváření konfiguračního profilu VPN pro zařízení s Androidem a Androidem for Work zadejte název připojení, IP adresu nebo plně kvalifikovaný název domény serveru VPN, zvolte způsob ověřování uživatelů na serveru VPN a pak zvolte typy připojení Citrix, SonicWall, Check Point Capsule, Pulse Secure a Microsoft Edge.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 666b61eec021fa6a2cdad5126f572234d97b6883
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566093"
---
# <a name="configure-vpn-settings-for-devices-running-android-in-intune"></a>Konfigurace nastavení VPN pro zařízení s Androidem v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek popisuje, jaká nastavení můžete v Intune použít ke konfiguraci připojení VPN na zařízeních s Androidem.

Nastavení sítě VPN můžete nakonfigurovat pro tyto platformy:

- [Android](#android-vpn-settings)
- [Android Enterprise](#android-enterprise-vpn-settings)

V závislosti na tom, jaká nastavení zvolíte, nebudou konfigurovatelné všechny následující hodnoty.

## <a name="android-vpn-settings"></a>Nastavení VPN v Androidu

- **Název připojení**: Zadejte název pro toto připojení. Tento název uživatelé vidí, když na svém zařízení procházejí dostupná připojení VPN.
- **IP adresa nebo plně kvalifikovaný název domény**: Zadejte IP adresu nebo plně kvalifikovaný název domény (FQDN) serveru VPN, který zařízení připojovat. Zadejte například **192.168.1.1** nebo **vpn.contoso.com**.

  - **Metoda ověřování**: Zvolte, jak zařízení ověření vůči serveru VPN. Možnosti:

    - **Certifikáty**: Vyberte existující profil certifikátu SCEP nebo PKCS pro ověření připojení. [Konfigurace certifikátů](certificates-configure.md) obsahuje kroky pro vytvoření profilu certifikátu.
    - **Uživatelské jméno a heslo**: Při přihlašování k serveru VPN, koncovým uživatelům se výzva k zadání uživatelského jména a hesla.

- **Typ připojení**: Vyberte typ připojení VPN. Možnosti:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Citrix**

- **Otisk prstu** (Check Point Capsule VPN pouze): Zadejte řetězec, jako například **kód otisku prstu Contoso**, chcete-li ověřit, že možné serveru VPN důvěřovat. Otisk prstu se může odeslat klientovi, aby věděl, že může důvěřovat jakémukoli serveru, který má při připojování ten samý otisk. Pokud zařízení otisk prstu nemá, vyzve uživatele, aby danému serveru VPN důvěřoval. Současně přitom zobrazuje otisk prstu. Uživatel ho ručně ověří a zvolí důvěryhodnost připojení.
- **Zadejte páry klíč-hodnota pro atributy Citrix VPN** (pouze Citrix): Zadejte páry klíč-hodnota, poskytl Citrix. Tyto hodnoty nakonfigurují vlastnosti připojení VPN.

## <a name="android-enterprise-vpn-settings"></a>Nastavení sítě VPN v androidu enterprise

- **Název připojení**: Zadejte název pro toto připojení. Tento název uživatelé vidí, když na svém zařízení procházejí dostupná připojení VPN.
- **IP adresa nebo plně kvalifikovaný název domény**: Zadejte IP adresu nebo plně kvalifikovaný název domény (FQDN) serveru VPN, který zařízení připojovat. Zadejte například **192.168.1.1** nebo **vpn.contoso.com**.

  - **Metoda ověřování**: Zvolte, jak zařízení ověření vůči serveru VPN. Možnosti:
  
    - **Certifikáty**: Vyberte existující profil certifikátu SCEP nebo PKCS pro ověření připojení. [Konfigurace certifikátů](certificates-configure.md) obsahuje kroky pro vytvoření profilu certifikátu.
    - **Uživatelské jméno a heslo**: Při přihlašování k serveru VPN, koncovým uživatelům se výzva k zadání uživatelského jména a hesla.

- **Typ připojení**: Vyberte typ připojení VPN. Možnosti:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Access**
  - **Pulse Secure**

## <a name="next-steps"></a>Další postup
[Profily VPN v Intune](vpn-settings-configure.md)
