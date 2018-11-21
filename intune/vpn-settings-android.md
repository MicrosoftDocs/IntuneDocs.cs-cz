---
title: Konfigurace nastavení VPN pro zařízení s Androidem v Microsoft Intune – Azure | Microsoft Docs
description: Při vytváření konfiguračního profilu VPN pro zařízení s Androidem a Androidem for Work zadejte název připojení, IP adresu nebo plně kvalifikovaný název domény serveru VPN, zvolte způsob ověřování uživatelů na serveru VPN a pak zvolte typy připojení Citrix, SonicWall, Check Point Capsule, Pulse Secure a Microsoft Edge.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: ac4b7821f132c92b247538e4ea6131f517da7698
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187683"
---
# <a name="configure-vpn-settings-for-devices-running-android-in-intune"></a>Konfigurace nastavení VPN pro zařízení s Androidem v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek popisuje, jaká nastavení můžete v Intune použít ke konfiguraci připojení VPN na zařízeních s Androidem.

Nastavení sítě VPN můžete nakonfigurovat pro tyto platformy:

- [Android](#android-vpn-settings)
- [Android for work](#android-for-work-vpn-settings)

V závislosti na tom, jaká nastavení zvolíte, nebudou konfigurovatelné všechny následující hodnoty.

## <a name="android-vpn-settings"></a>Nastavení VPN v Androidu

- **Název připojení**: zadejte název tohoto připojení. Tento název uživatelé vidí, když na svém zařízení procházejí dostupná připojení VPN.
- **IP adresa nebo plně kvalifikovaný název domény**: zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se zařízení připojí. Zadejte například **192.168.1.1** nebo **vpn.contoso.com**.

  - **Metoda ověřování**: Zvolte způsob, kterým se zařízení ověřují vůči serveru VPN. Možnosti:

    - **Certifikáty**: Vyberte existující profil certifikátu SCEP nebo PKCS pro ověřování připojení. [Konfigurace certifikátů](certificates-configure.md) obsahuje kroky pro vytvoření profilu certifikátu.
    - **Uživatelské jméno a heslo**: Při přihlašování k serveru VPN se koncovým uživatelům zobrazí výzva k zadání uživatelského jména a hesla.

- **Typ připojení**: Vyberte typ připojení VPN. Možnosti:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Citrix**

- **Otisk prstu** (pouze Check Point Capsule VPN): Zadejte řetězec, například **Kód otisku prstu Contoso**, který se použije k ověření, že serveru VPN je možné důvěřovat. Otisk prstu se může odeslat klientovi, aby věděl, že může důvěřovat jakémukoli serveru, který má při připojování ten samý otisk. Pokud zařízení otisk prstu nemá, vyzve uživatele, aby danému serveru VPN důvěřoval. Současně přitom zobrazuje otisk prstu. Uživatel ho ručně ověří a zvolí důvěryhodnost připojení.
- **Zadejte páry klíč-hodnota pro atributy Citrix VPN** (pouze Citrix): Zadejte páry klíče a hodnoty, které poskytl Citrix. Tyto hodnoty nakonfigurují vlastnosti připojení VPN.

## <a name="android-for-work-vpn-settings"></a>Nastavení VPN v Androidu for Work

- **Název připojení**: zadejte název tohoto připojení. Tento název uživatelé vidí, když na svém zařízení procházejí dostupná připojení VPN.
- **IP adresa nebo plně kvalifikovaný název domény**: zadejte IP adresu nebo plně kvalifikovaný název domény serveru VPN, ke kterému se zařízení připojí. Zadejte například **192.168.1.1** nebo **vpn.contoso.com**.

  - **Metoda ověřování**: Zvolte způsob, kterým se zařízení ověřují vůči serveru VPN. Možnosti:
  
    - **Certifikáty**: Vyberte existující profil certifikátu SCEP nebo PKCS pro ověřování připojení. [Konfigurace certifikátů](certificates-configure.md) obsahuje kroky pro vytvoření profilu certifikátu.
    - **Uživatelské jméno a heslo**: Při přihlašování k serveru VPN se koncovým uživatelům zobrazí výzva k zadání uživatelského jména a hesla.

- **Typ připojení**: Vyberte typ připojení VPN. Možnosti:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**

## <a name="next-steps"></a>Další postup
[Profily VPN v Intune](vpn-settings-configure.md)
